---
title: PowerShell 腳本範例 - 建立&指派訊息原則
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: 使用此 PowerShell 腳本在 Teams 中建立訊息原則，並將它指派給組織中的使用者。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 764de690bbf743991536416c7fed08d0b88e7e97
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825887"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell 腳本範例 - 建立及指派訊息原則

使用此 PowerShell 腳本在 Microsoft Teams 中建立訊息原則，並將它指派給使用者。 

如需使用此 PowerShell 腳本的詳細資訊，請參閱[快速入門 - Teams 教育版](../teams-quick-start-edu.yml)。

此腳本使用 商務用 Skype Online PowerShell 模組中的[Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) Cmdlet。 若要深入瞭解如何使用 PowerShell 管理 Teams，請參閱 [Teams PowerShell 概觀](../teams-powershell-overview.md) 。


## <a name="before-you-start"></a>開始之前

下載並安裝[商務用 Skype Online PowerShell 模組](https://www.microsoft.com/download/details.aspx?id=54616)，然後在出現提示時重新開機電腦。

若要深入瞭解，請參閱[使用 Office 365 PowerShell 管理 商務用 Skype Online](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

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
> 您也可以透過批次處理原則指派或使用者為其成員的群組，以縮放比例直接指派訊息原則給使用者。 如需詳細資訊，請參閱 [指派原則給學校中的大型使用者群](../batch-group-policy-assignment-edu.md) 組和 [在 Teams 中指派原則給使用者](../policy-assignment-overview.md)。