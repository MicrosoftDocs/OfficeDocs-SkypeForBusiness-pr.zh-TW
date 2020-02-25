---
title: PowerShell 腳本範例-建立並指派訊息原則
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: 使用此 PowerShell 腳本在團隊中建立訊息原則，並將其指派給組織中的使用者。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 07efc7b86045de9e76669d4ffbf185aba9d94d1f
ms.sourcegitcommit: 73518a589db1a9883fc97827f0ddb9132995fbfa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42236803"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="1838b-103">PowerShell 腳本範例-建立並指派訊息原則</span><span class="sxs-lookup"><span data-stu-id="1838b-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="1838b-104">使用此 PowerShell 腳本在 Microsoft 團隊中建立訊息原則，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="1838b-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="1838b-105">如需有關使用此 PowerShell 腳本的詳細資訊，請參閱[快速入門-教育版團隊](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)。</span><span class="sxs-lookup"><span data-stu-id="1838b-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="1838b-106">如果您是 PowerShell 新手，且需要開始協助，請參閱[Azure PowerShell 的概覽](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1)。</span><span class="sxs-lookup"><span data-stu-id="1838b-106">If you're new to PowerShell and need help getting started, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span></span>


## <a name="sample-script"></a><span data-ttu-id="1838b-107">範例腳本</span><span class="sxs-lookup"><span data-stu-id="1838b-107">Sample script</span></span>

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


