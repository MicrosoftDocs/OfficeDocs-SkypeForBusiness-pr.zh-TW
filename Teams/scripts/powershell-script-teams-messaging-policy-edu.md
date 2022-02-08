---
title: PowerShell 腳本範例 - 建立&訊息策略
author: serdars
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: 使用此 PowerShell 腳本，在 Teams中建立訊息Teams並將它指派給貴組織的使用者。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c6c1faaff2ce252b1363fab149c7d168c5e042e5
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390835"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell 腳本範例 - 建立及指派訊息策略

使用此 PowerShell 腳本在郵件中建立訊息Microsoft Teams並指派給使用者。 

有關使用此 PowerShell 腳本的資訊，請參閱[快速入門 - Teams 教育版](../teams-quick-start-edu.yml)。

此腳本使用[Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) Cmdlet，商務用 Skype Online PowerShell 模組中。 請參閱[Teams PowerShell 概](../teams-powershell-overview.md)觀，進一Teams PowerShell 管理應用程式。


## <a name="before-you-start"></a>在您開始之前

下載並安裝[商務用 Skype PowerShell 模組](https://www.microsoft.com/download/details.aspx?id=39366)，然後重新開機電腦 ，如果系統提示。

若要精簡更多內容，請參閱使用[PowerShell 商務用 Skype管理Office 365線上](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

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
> 您也可以透過批次策略指派，將訊息策略直接指派給使用者，或指派給使用者為成員的群組。 詳細資訊請參閱指派[策略給學校](../batch-group-policy-assignment-edu.md)中的大量使用者，以及指派[Teams。](../policy-assignment-overview.md)