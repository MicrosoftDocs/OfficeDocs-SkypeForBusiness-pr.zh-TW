---
title: 使用 PowerShell 腳本變更資訊障礙模式
description: 部署資訊障礙之後，請使用此 PowerShell 腳本，針對租使用者中的所有群組，將模式從開放式更新為隱含模式。
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
ms.reviewer: smahadevan
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- tier2
- purview-compliance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63403c5e5ee495a7a110aa9239868fd6a9bb5803
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/27/2022
ms.locfileid: "68047123"
---
# <a name="change-information-barriers-modes-with-a-powershell-script"></a>使用 PowerShell 腳本變更資訊障礙模式

使用此 PowerShell 腳本來更新租使用者中所有已連線 Teams 的群組 (IB) 模式的資訊障礙。 部署資訊障礙之後，您必須更新這些群組的模式。 在您啟用 IB 之前布建的群組會被指派為 *[開* 啟] 模式。 在 *[開* 啟模式] 中，沒有任何適用的 IB 原則。 啟用 IB 之後， *隱含* 會成為您建立之任何新群組的預設模式。 不過，現有的群組仍會保留 *Open* 模式設定。 執行此腳本以將這些現有群組變更為 *隱含* 模式。

在此腳本中，您將使用[Get-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) Cmdlet，這是在 powerShell Exchange Online模組中更新模式。 若要深入瞭解如何使用 PowerShell 管理 Teams，請參閱 [Teams PowerShell 概觀](./teams-powershell-overview.md)。

## <a name="sample-script"></a>範例腳本

您必須使用已獲指派租使用者全域系統管理員角色的公司或學校帳戶，才能執行此腳本。

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