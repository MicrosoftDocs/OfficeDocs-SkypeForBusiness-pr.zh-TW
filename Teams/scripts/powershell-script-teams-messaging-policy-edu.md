---
title: PowerShell 腳本範例-建立 & 指派訊息傳遞原則
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: 使用此 PowerShell 腳本在團隊中建立訊息原則，並將其指派給組織中的使用者。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e3d1fa3ebe45785c088852c518ac5490263fa6aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804653"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell 腳本範例-建立並指派訊息原則

使用此 PowerShell 腳本在 Microsoft 團隊中建立訊息原則，並將它指派給使用者。 

如需有關使用此 PowerShell 腳本的詳細資訊，請參閱 [快速入門-教育版團隊](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)。

此腳本使用商務用 Skype Online PowerShell 模組中的 [Grant CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) Cmdlet。 若要深入瞭解如何使用 PowerShell 管理團隊，請參閱 [團隊 PowerShell 概覽](../teams-powershell-overview.md) 。


## <a name="before-you-start"></a>開始之前

下載並安裝 [商務用 Skype Online PowerShell 模組](https://www.microsoft.com/download/details.aspx?id=39366)，然後在出現提示時重新開機電腦。

若要進一步瞭解，請參閱 [使用 Office 365 PowerShell 管理商務用 Skype Online](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

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
> 您也可以將訊息原則直接指派給使用者，以進行批原則分派或使用者是其成員的群組。 如需詳細資訊，請參閱 [將原則指派給學校中的大型使用者](../batch-group-policy-assignment-edu.md) ，然後 [將原則指派給您的小組中的使用者](../assign-policies.md)。
