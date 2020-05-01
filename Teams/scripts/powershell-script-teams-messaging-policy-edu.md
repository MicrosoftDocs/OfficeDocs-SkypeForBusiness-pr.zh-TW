---
title: PowerShell 腳本範例-建立 & 指派訊息傳遞原則
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
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 748167dc8e03b53fc07611df0ff464d984fb5678
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2020
ms.locfileid: "43951058"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="9f391-103">PowerShell 腳本範例-建立並指派訊息原則</span><span class="sxs-lookup"><span data-stu-id="9f391-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="9f391-104">使用此 PowerShell 腳本在 Microsoft 團隊中建立訊息原則，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="9f391-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="9f391-105">如需有關使用此 PowerShell 腳本的詳細資訊，請參閱[快速入門-教育版團隊](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)。</span><span class="sxs-lookup"><span data-stu-id="9f391-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="9f391-106">此腳本使用商務用 Skype Online PowerShell 模組中的[Grant CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9f391-106">This script uses the [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet which is in the Skype for Business Online PowerShell module.</span></span> <span data-ttu-id="9f391-107">若要深入瞭解如何使用 PowerShell 管理團隊，請參閱[團隊 PowerShell 概覽](../teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="9f391-107">See [Teams PowerShell overview](../teams-powershell-overview.md) to learn more about managing Teams using PowerShell.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="9f391-108">開始之前</span><span class="sxs-lookup"><span data-stu-id="9f391-108">Before you start</span></span>

<span data-ttu-id="9f391-109">下載並安裝[商務用 Skype Online PowerShell 模組](https://www.microsoft.com/download/details.aspx?id=39366)，然後在出現提示時重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="9f391-109">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="9f391-110">若要進一步瞭解，請參閱[使用 Office 365 PowerShell 管理商務用 Skype Online](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="9f391-110">To lean more, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>


## <a name="sample-script"></a><span data-ttu-id="9f391-111">範例腳本</span><span class="sxs-lookup"><span data-stu-id="9f391-111">Sample script</span></span>

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
> <span data-ttu-id="9f391-112">您也可以使用批次原則指派，將訊息原則指派給大型使用者組。</span><span class="sxs-lookup"><span data-stu-id="9f391-112">You can also use batch policy assignment to assign a messaging policy to large sets of users.</span></span> <span data-ttu-id="9f391-113">如需詳細資訊，請參閱[將原則指派給學校中的大型使用者](../batch-policy-assignment-edu.md)，然後[將原則指派給您的小組中的使用者](../assign-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9f391-113">For more information see [Assign policies to large sets of users in your school](../batch-policy-assignment-edu.md) and [Assign policies to your users in Teams](../assign-policies.md).</span></span>
