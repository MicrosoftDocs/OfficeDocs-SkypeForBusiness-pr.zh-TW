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
ms.openlocfilehash: 318a430f6f59cbb28ffeda4336c36ae07533615b
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533738"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="a53e6-103">PowerShell 腳本範例-建立並指派訊息原則</span><span class="sxs-lookup"><span data-stu-id="a53e6-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="a53e6-104">使用此 PowerShell 腳本在 Microsoft 團隊中建立訊息原則，並將它指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="a53e6-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="a53e6-105">如需有關使用此 PowerShell 腳本的詳細資訊，請參閱[快速入門-教育版團隊](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)。</span><span class="sxs-lookup"><span data-stu-id="a53e6-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="a53e6-106">此腳本使用商務用 Skype Online PowerShell 模組中的[Grant CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a53e6-106">This script uses the [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet which is in the Skype for Business Online PowerShell module.</span></span> <span data-ttu-id="a53e6-107">若要深入瞭解如何使用 PowerShell 管理團隊，請參閱[團隊 PowerShell 概覽](../teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a53e6-107">See [Teams PowerShell overview](../teams-powershell-overview.md) to learn more about managing Teams using PowerShell.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="a53e6-108">開始之前</span><span class="sxs-lookup"><span data-stu-id="a53e6-108">Before you start</span></span>

<span data-ttu-id="a53e6-109">下載並安裝[商務用 Skype Online PowerShell 模組](https://www.microsoft.com/download/details.aspx?id=39366)，然後在出現提示時重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="a53e6-109">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="a53e6-110">若要進一步瞭解，請參閱[使用 Office 365 PowerShell 管理商務用 Skype Online](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a53e6-110">To lean more, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="sample-script"></a><span data-ttu-id="a53e6-111">範例腳本</span><span class="sxs-lookup"><span data-stu-id="a53e6-111">Sample script</span></span>

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
> <span data-ttu-id="a53e6-112">您也可以將訊息原則直接指派給使用者，以進行批原則分派或使用者是其成員的群組。</span><span class="sxs-lookup"><span data-stu-id="a53e6-112">You can also assign a messaging policy directly to users at scale through a batch policy assignment or to a group that the users are members of.</span></span> <span data-ttu-id="a53e6-113">如需詳細資訊，請參閱[將原則指派給學校中的大型使用者](../batch-group-policy-assignment-edu.md)，然後[將原則指派給您的小組中的使用者](../assign-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a53e6-113">For more information see [Assign policies to large sets of users in your school](../batch-group-policy-assignment-edu.md) and [Assign policies to your users in Teams](../assign-policies.md).</span></span>
