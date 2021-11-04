---
title: PowerShell 腳本範例 - 建立&訊息策略
author: serdars
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: 使用此 PowerShell 腳本在 Teams中建立訊息Teams並將它指派給貴組織的使用者。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 922bbd88f8a470a19edf799b737a349043ebfeed
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741549"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell 腳本範例 - 建立及指派訊息策略

使用此 PowerShell 腳本在郵件中建立訊息Microsoft Teams並指派給使用者。 

有關使用此 PowerShell 腳本的資訊，請參閱快速入門[- Teams 教育版。](../teams-quick-start-edu.yml)

此腳本使用[Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) Cmdlet，商務用 Skype Online PowerShell 模組中。 請參閱[Teams PowerShell 概](../teams-powershell-overview.md)觀，進一Teams PowerShell 管理應用程式。


## <a name="before-you-start"></a>在您開始之前

下載並安裝[商務用 Skype PowerShell 模組](https://www.microsoft.com/download/details.aspx?id=39366)，然後在系統提示時重新開機電腦。

若要精簡更多內容，[請參閱使用 PowerShell 商務用 Skype管理Office 365 Online](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

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
> 您也可以透過批次策略指派，將訊息策略直接指派給使用者，或是指派給使用者的成員群組。 詳細資訊請參閱將[策略指派給學校](../batch-group-policy-assignment-edu.md)中的大量使用者，以及指派[Teams。](../policy-assignment-overview.md)