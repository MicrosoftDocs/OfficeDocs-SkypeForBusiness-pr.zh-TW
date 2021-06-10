---
title: 管理語音和通話Teams
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: 瞭解語音Teams通話政策。
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9056c9b81fcda9c0e7408c63b4af00c1aabbffd0
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460583"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a><span data-ttu-id="4360d-103">管理語音和通話Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4360d-103">Manage voice and calling policies in Microsoft Teams</span></span>

<span data-ttu-id="4360d-104">語音和通話政策是用來控制語音和通話Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="4360d-104">Voice and calling policies are used to control voice and calling in Microsoft Teams.</span></span>

## <a name="emergency-calling-policies"></a><span data-ttu-id="4360d-105">緊急通話政策</span><span class="sxs-lookup"><span data-stu-id="4360d-105">Emergency calling policies</span></span>

<span data-ttu-id="4360d-106">您可以使用 [緊急通話政策](manage-emergency-calling-policies.md) 來設定當貴組織的使用者撥打緊急電話時會發生什麼情況。</span><span class="sxs-lookup"><span data-stu-id="4360d-106">You use [emergency calling policies](manage-emergency-calling-policies.md) to configure what happens when a user in your organization makes an emergency call.</span></span> <span data-ttu-id="4360d-107">這些策略在系統管理中心Teams使用Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4360d-107">These policies are managed in the Teams admin center or using Windows PowerShell.</span></span>

![緊急通話策略的螢幕擷取畫面。](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a><span data-ttu-id="4360d-109">緊急通話路由策略</span><span class="sxs-lookup"><span data-stu-id="4360d-109">Emergency call routing policies</span></span>

<span data-ttu-id="4360d-110">如果貴組織已部署 **電話系統** 路由，您可以使用緊急電話路由策略來 [](manage-emergency-call-routing-policies.md)判斷緊急電話的路由位置、是否已啟用增強的緊急服務，以及用於緊急服務的號碼。</span><span class="sxs-lookup"><span data-stu-id="4360d-110">If your organization has deployed **Phone System Direct Routing**, you can use [emergency call routing policies](manage-emergency-call-routing-policies.md) to determine where emergency calls are routed, whether enhanced emergency services are enabled, and which numbers are used for emergency services.</span></span> <span data-ttu-id="4360d-111">這些策略是使用 PowerShell 或系統管理Microsoft Teams管理中心管理。</span><span class="sxs-lookup"><span data-stu-id="4360d-111">These policies are managed using PowerShell or in the Microsoft Teams admin center.</span></span>

![緊急通話路由策略的螢幕擷取畫面。](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a><span data-ttu-id="4360d-113">本機號碼政策</span><span class="sxs-lookup"><span data-stu-id="4360d-113">Caller ID policies</span></span>

<span data-ttu-id="4360d-114">[本機號碼政策](caller-id-policies.md) 是用來變更或封鎖本機號碼。</span><span class="sxs-lookup"><span data-stu-id="4360d-114">[Caller ID policies](caller-id-policies.md) are used to change or block caller ID.</span></span>

![本機號碼策略的螢幕擷取畫面。](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a><span data-ttu-id="4360d-116">語音路由策略</span><span class="sxs-lookup"><span data-stu-id="4360d-116">Voice routing policies</span></span>

<span data-ttu-id="4360d-117">語音 [路由策略](manage-voice-routing-policies.md) 是公用交換電話網絡 (PSTN) 容器。</span><span class="sxs-lookup"><span data-stu-id="4360d-117">A [voice routing policy](manage-voice-routing-policies.md) is a container for Public Switched Telephone Network (PSTN) usage records.</span></span> <span data-ttu-id="4360d-118">如果您的組織已部署直接路由，您可以使用 **電話系統策略**。</span><span class="sxs-lookup"><span data-stu-id="4360d-118">You can use these policies if your organization has deployed **Phone System Direct Routing**.</span></span> <span data-ttu-id="4360d-119">語音路由策略可以使用 PowerShell 或系統管理中心Teams管理。</span><span class="sxs-lookup"><span data-stu-id="4360d-119">Voice routing policies can be managed with PowerShell or in the Teams admin center.</span></span>

![語音路由策略的螢幕擷取畫面。](media/voice-routing-policy.png)

## <a name="calling-policies"></a><span data-ttu-id="4360d-121">通話原則</span><span class="sxs-lookup"><span data-stu-id="4360d-121">Calling policies</span></span>

<span data-ttu-id="4360d-122">[通話政策](teams-calling-policy.md) 可控制哪些通話和呼叫轉寄功能可供使用者使用，包括使用者是否可以撥打私人電話、將通話傳送給通話群組，以及將通話路由至語音信箱。</span><span class="sxs-lookup"><span data-stu-id="4360d-122">[Calling policies](teams-calling-policy.md) control which calling and call forwarding features are available to users including whether a user can make private calls, send calls to call groups, and route calls to voicemail.</span></span>

![通話策略的螢幕擷取畫面。](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a><span data-ttu-id="4360d-124">呼叫停駐和取回策略</span><span class="sxs-lookup"><span data-stu-id="4360d-124">Call park and retrieve policies</span></span>

<span data-ttu-id="4360d-125">[呼叫保留和取回](call-park-and-retrieve.md) 可讓使用者將其他使用者置於保留狀態，並可讓同一個使用者或其他人繼續通話。</span><span class="sxs-lookup"><span data-stu-id="4360d-125">[Call park and retrieve](call-park-and-retrieve.md) lets users put other users on hold and enables the same user or someone else to continue the call.</span></span>

![呼叫停駐和取回策略的螢幕擷取畫面。](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a><span data-ttu-id="4360d-127">建立和管理撥號對應表</span><span class="sxs-lookup"><span data-stu-id="4360d-127">Create and manage dial plans</span></span>

<span data-ttu-id="4360d-128">[撥號方案](create-and-manage-dial-plans.md) 會翻譯撥號電話號碼，以用於通話授權和路由。</span><span class="sxs-lookup"><span data-stu-id="4360d-128">[Dial plans](create-and-manage-dial-plans.md) translate dialed phone numbers for call authorization and routing.</span></span> <span data-ttu-id="4360d-129">您可以透過 PowerShell 或系統管理中心建立Microsoft Teams方案。</span><span class="sxs-lookup"><span data-stu-id="4360d-129">You can create and manage dial plans through PowerShell or in the Microsoft Teams admin center.</span></span>

![撥號方案螢幕擷取畫面。](media/dial-plans.png)

## <a name="related-topics"></a><span data-ttu-id="4360d-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="4360d-131">Related topics</span></span>

* [<span data-ttu-id="4360d-132">在 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4360d-132">Manage emergency calling policies in Microsoft Teams</span></span>](manage-emergency-calling-policies.md)
* [<span data-ttu-id="4360d-133">管理緊急電話路由原則</span><span class="sxs-lookup"><span data-stu-id="4360d-133">Manage emergency call routing policies</span></span>](manage-emergency-call-routing-policies.md)
* <span data-ttu-id="4360d-134">[管理 Microsoft Teams 中的來電顯示原則](caller-id-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="4360d-134">[Manage caller ID policies in Microsoft Teams](caller-id-policies.md)</span></span>
* [<span data-ttu-id="4360d-135">管理語音路由策略</span><span class="sxs-lookup"><span data-stu-id="4360d-135">Manage voice routing policies</span></span>](manage-voice-routing-policies.md)
* [<span data-ttu-id="4360d-136">通話中Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4360d-136">Calling policies in Microsoft Teams</span></span>](teams-calling-policy.md)
* [<span data-ttu-id="4360d-137">呼叫停駐和Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4360d-137">Call park and retrieve in Microsoft Teams</span></span>](call-park-and-retrieve.md)
* [<span data-ttu-id="4360d-138">建立和管理撥號對應表</span><span class="sxs-lookup"><span data-stu-id="4360d-138">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)
* [<span data-ttu-id="4360d-139">使用Teams管理</span><span class="sxs-lookup"><span data-stu-id="4360d-139">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
