---
title: 使用 PowerShell 腳本變更資訊障礙模式
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
ms.reviewer: smahadevan
ms.service: msteams
audience: admin
description: 部署資訊障礙之後，請使用這個 PowerShell 腳本，將租使用者中所有群組的模式從開啟更新為隱含模式。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3030f40ed61eb2e0e86967132d9575de8334a6c6
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767546"
---
# <a name="change-information-barriers-modes-with-a-powershell-script"></a>使用 PowerShell 腳本變更資訊障礙模式

使用此 PowerShell 腳本來更新租使用者中 (中) 所有已Teams群組之IB 和IB 模式的資訊障礙。 部署資訊障礙之後，您必須更新這些群組的模式。 啟用IB 前布備的群組會指派 [ *開啟模式* 。 在 *開啟* 模式中，沒有任何適用的IB 政策。 啟用IB 之後， *隱含* 會變成您建立的任何新群組的預設模式。 不過，現有的群組仍然保留 *開啟* 模式組式。 執行此腳本，將這些現有的群組變更為 *隱含* 模式。

在此腳本中，您將使用[Get-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) Cmdlet，Exchange Online PowerShell 模組來更新模式。 若要深入瞭解使用 PowerShell 管理Teams，請參閱[PowerShell Teams概觀](./teams-powershell-overview.md)。

## <a name="sample-script"></a>範例腳本

您必須使用已指派全域系統管理員角色的公司或學校帳戶，讓租使用者執行此腳本。

```powershell
<#
.SYNOPSIS
This script updates the information barrier mode for all Teams-connected groups in your tenant at the same time.
.DESCRIPTION
Use this script to update the info barrier mode from open to implicit across the groups in your tenant.
#>

$teams = Get-UnifiedGroup -Filter {ResourceProvisioningOptions -eq "Team"} -ResultSize Unlimited

Write-Output ([string]::Format("Number of Teams = {0}", @($teams).Length))

$teamsToUpdate = New-Object System.Collections.ArrayList

foreach($team in $teams)
{
  if ($team.InformationBarrierMode -eq "Open")
  {
    $teamsToUpdate.Add($team.ExternalDirectoryObjectId) | out-null
  }
}

Write-Output ([string]::Format("Number of Teams to be backfilled = {0}", @($teamsToUpdate).Length))

$outfile = "BackfillFailedTeams.csv"

if (!(Test-Path "$outfile"))
{
  $newcsv = {} | Select "ExternalDirectoryObjectId", "ExceptionDetails" | Export-Csv $outfile -NoTypeInformation  
}
else
{
  $dateTime = Get-Date
  $newEntry = "{0},{1}" -f "New session started", $dateTime
  $newEntry | add-content $outfile
}

$SuccessfullyBackfilledGroup = 0

for($i = 0; $i -lt @($teamsToUpdate).Length; $i++)
{
  Invoke-Command { Set-UnifiedGroup $teamsToUpdate[$i] -InformationBarrierMode "Implicit" } -ErrorVariable ErrorOutput

  if ($ErrorOutput)
  {
    # saving the errors in a csv file
    $errorBody = $ErrorOutput[0].ToString() -replace "`n"," " -replace "`r"," " -replace ",", " "
    $newEntry = "{0},{1}" -f $teamsToUpdate[$i].ToString(), '"' + $errorBody + '"'
    $newEntry | add-content $outfile
  }
  else
  {
    $SuccessfullyBackfilledGroup++
  }

  if (($i+1) % 100 -eq 0)
  {
    # print the number of teams backfilled after the batch of 100 updates
    Write-Output ([string]::Format("Number of Teams processed= {0}", $i+1)) 
  }
}

Write-Output ([string]::Format("Backfill completed. Groups backfilled: {0}, Groups failed to backfill: {1}", $SuccessfullyBackfilledGroup, @($teamsToUpdate).Length - $SuccessfullyBackfilledGroup))

if (!($SuccessfullyBackfilledGroup -eq @($teamsToUpdate).Length))
{
  Write-Output ([string]::Format("Check the failed teams in BackfillFailedTeams.csv, retry to backfill the failed teams.")) 
}

```