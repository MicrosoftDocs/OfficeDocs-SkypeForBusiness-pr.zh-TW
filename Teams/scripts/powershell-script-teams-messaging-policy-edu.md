---
title: PowerShell 腳本範例 - 建立&訊息策略
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: 使用此 PowerShell 腳本在 Teams 中建立訊息策略，並將其指派給貴組織的使用者。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c665b96c0c44c2ea763c343bb2857d4c2b9dbb26
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117271"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell 腳本範例 - 建立及指派訊息策略

使用此 PowerShell 腳本在 Microsoft Teams 中建立訊息策略，並將其指派給使用者。 

有關使用此 PowerShell 腳本的資訊，請參閱[快速入門 - Teams 教育用 。](../teams-quick-start-edu.yml)

此腳本使用位於商務用 Skype Online PowerShell 模組中的 [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) Cmdlet。 請參閱 [Teams PowerShell 概觀](../teams-powershell-overview.md) ，深入瞭解使用 PowerShell 管理 Teams。


## <a name="before-you-start"></a>在您開始之前

下載並安裝商務用 [Skype Online PowerShell 模組](https://www.microsoft.com/download/details.aspx?id=39366)，然後在系統提示時重新開機電腦。

若要精簡更多內容，請參閱使用 [Office 365 PowerShell 管理商務](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)用 Skype Online 。

## <a name="sample-script"></a>範例腳本

```powershell
<#
.SYNOPSIS
This script creates a messaging policy in Teams and assigns it to users.
.DESCRIPTION
Use this script to create a messaging policy and assign it to users in your organization.
#>

$dataSetFilePath = "<csv file with user ids for newly provisioned students> "
 $dataSet = Import-Csv "$($dataSetFilePath)" -Header UserId –delimiter ","
 foreach($line in $dataSet)
 {
    $userId = $line.UserId
    Write-Host $userId
    Grant-CsTeamsMessagingPolicy -PolicyName "<<PolicyName for a policy created with Chat Off>>" -Identity $userId

 }
```

> [!NOTE]
> 您也可以透過批次策略指派，將訊息策略直接指派給使用者，或指派給使用者為成員的群組。 詳細資訊請參閱指派[策略給學校](../batch-group-policy-assignment-edu.md)中的大量使用者，以及將策略指派[給使用者至 Teams。](../assign-policies.md)