---
title: 在 Teams 中管理語音和通話政策
author: karlistites
ms.author: kastites
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: ''
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7d0ea4db57fbfdc3ab76e8c6c9991e032103b260
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347998"
---
# <a name="manage-voice-and-calling-policies-in-microsoft-teams"></a><span data-ttu-id="321a7-102">在 Microsoft Teams 中管理語音和通話政策</span><span class="sxs-lookup"><span data-stu-id="321a7-102">Manage voice and calling policies in Microsoft Teams</span></span>

<span data-ttu-id="321a7-103">在 Microsoft Teams 中，語音和通話政策可用來控制語音和通話。</span><span class="sxs-lookup"><span data-stu-id="321a7-103">Voice and calling policies are used to control voice and calling in Microsoft Teams.</span></span>

## <a name="emergency-calling-policies"></a><span data-ttu-id="321a7-104">緊急通話政策</span><span class="sxs-lookup"><span data-stu-id="321a7-104">Emergency calling policies</span></span>

<span data-ttu-id="321a7-105">您可以使用 [緊急通話政策](manage-emergency-calling-policies.md) 來設定當貴組織的使用者撥打緊急電話時會發生什麼情況。</span><span class="sxs-lookup"><span data-stu-id="321a7-105">You use [emergency calling policies](manage-emergency-calling-policies.md) to configure what happens when a user in your organization makes an emergency call.</span></span> <span data-ttu-id="321a7-106">這些策略在 Teams 系統管理中心或 Windows PowerShell 中管理。</span><span class="sxs-lookup"><span data-stu-id="321a7-106">These policies are managed in the Teams admin center or using Windows PowerShell.</span></span>

![緊急通話政策螢幕擷取畫面。](media/emergency-calling-policy2.png)

## <a name="emergency-call-routing-policies"></a><span data-ttu-id="321a7-108">緊急電話路由規則</span><span class="sxs-lookup"><span data-stu-id="321a7-108">Emergency call routing policies</span></span>

<span data-ttu-id="321a7-109">如果貴組織已部署電話 **系統直接路由**，您可以使用緊急電話路由 [](manage-emergency-call-routing-policies.md)策略來判斷緊急電話的路由位置、是否已啟用增強的緊急服務，以及緊急服務會使用哪些號碼。</span><span class="sxs-lookup"><span data-stu-id="321a7-109">If your organization has deployed **Phone System Direct Routing**, you can use [emergency call routing policies](manage-emergency-call-routing-policies.md) to determine where emergency calls are routed, whether enhanced emergency services are enabled, and which numbers are used for emergency services.</span></span> <span data-ttu-id="321a7-110">這些策略是使用 PowerShell 或 Microsoft Teams 系統管理中心管理。</span><span class="sxs-lookup"><span data-stu-id="321a7-110">These policies are managed using PowerShell or in the Microsoft Teams admin center.</span></span>

![緊急電話路由策略的螢幕擷取畫面。](media/emergency-call-routing-policy.png)

## <a name="caller-id-policies"></a><span data-ttu-id="321a7-112">本機號碼政策</span><span class="sxs-lookup"><span data-stu-id="321a7-112">Caller ID policies</span></span>

<span data-ttu-id="321a7-113">[本機號碼政策](caller-id-policies.md) 是用來變更或封鎖本機號碼。</span><span class="sxs-lookup"><span data-stu-id="321a7-113">[Caller ID policies](caller-id-policies.md) are used to change or block caller ID.</span></span>

![本機號碼政策螢幕擷取畫面。](media/caller-id-policy.png)

## <a name="voice-routing-policies"></a><span data-ttu-id="321a7-115">語音路由策略</span><span class="sxs-lookup"><span data-stu-id="321a7-115">Voice routing policies</span></span>

<span data-ttu-id="321a7-116">語音 [路由策略](manage-voice-routing-policies.md) 是公用交換電話網路的容器 (PSTN) 記錄。</span><span class="sxs-lookup"><span data-stu-id="321a7-116">A [voice routing policy](manage-voice-routing-policies.md) is a container for Public Switched Telephone Network (PSTN) usage records.</span></span> <span data-ttu-id="321a7-117">如果您的組織已部署電話系統直接路由 **，您可以使用這些策略**。</span><span class="sxs-lookup"><span data-stu-id="321a7-117">You can use these policies if your organization has deployed **Phone System Direct Routing**.</span></span> <span data-ttu-id="321a7-118">語音路由策略可以使用 PowerShell 或 Teams 系統管理中心管理。</span><span class="sxs-lookup"><span data-stu-id="321a7-118">Voice routing policies can be managed with PowerShell or in the Teams admin center.</span></span>

![語音路由策略的螢幕擷取畫面。](media/voice-routing-policy.png)

## <a name="calling-policies"></a><span data-ttu-id="321a7-120">通話原則</span><span class="sxs-lookup"><span data-stu-id="321a7-120">Calling policies</span></span>

<span data-ttu-id="321a7-121">[通話政策](teams-calling-policy.md) 可控制使用者可以使用哪些通話和呼叫轉寄功能，包括使用者是否可以撥打私人電話、將通話傳送給通話群組，以及將通話路由至語音信箱。</span><span class="sxs-lookup"><span data-stu-id="321a7-121">[Calling policies](teams-calling-policy.md) control which calling and call forwarding features are available to users including whether a user can make private calls, send calls to call groups, and route calls to voicemail.</span></span>

![通話政策螢幕擷取畫面。](media/calling-policy.png)

## <a name="call-park-and-retrieve-policies"></a><span data-ttu-id="321a7-123">通話停駐和取回政策</span><span class="sxs-lookup"><span data-stu-id="321a7-123">Call park and retrieve policies</span></span>

<span data-ttu-id="321a7-124">[通話保留和取回](call-park-and-retrieve.md) 功能可讓使用者保留其他使用者，並可讓同一個使用者或其他人繼續通話。</span><span class="sxs-lookup"><span data-stu-id="321a7-124">[Call park and retrieve](call-park-and-retrieve.md) lets users put other users on hold and enables the same user or someone else to continue the call.</span></span>

![通話停駐和取回策略的螢幕擷取畫面。](media/call-park-policy.png)

## <a name="create-and-manage-dial-plans"></a><span data-ttu-id="321a7-126">建立和管理撥號對應表</span><span class="sxs-lookup"><span data-stu-id="321a7-126">Create and manage dial plans</span></span>

<span data-ttu-id="321a7-127">[撥號方案](create-and-manage-dial-plans.md) 會翻譯撥號電話號碼，以用於通話授權和路由。</span><span class="sxs-lookup"><span data-stu-id="321a7-127">[Dial plans](create-and-manage-dial-plans.md) translate dialed phone numbers for call authorization and routing.</span></span> <span data-ttu-id="321a7-128">您可以透過 PowerShell 或 Microsoft Teams 系統管理中心建立和管理撥號表。</span><span class="sxs-lookup"><span data-stu-id="321a7-128">You can create and manage dial plans through PowerShell or in the Microsoft Teams admin center.</span></span>

![撥號盤案的螢幕擷取畫面。](media/dial-plans.png)

## <a name="related-topics"></a><span data-ttu-id="321a7-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="321a7-130">Related topics</span></span>

* [<span data-ttu-id="321a7-131">在 Microsoft Teams 中管理緊急通話政策</span><span class="sxs-lookup"><span data-stu-id="321a7-131">Manage emergency calling policies in Microsoft Teams</span></span>](manage-emergency-calling-policies.md)
* [<span data-ttu-id="321a7-132">管理緊急電話路由原則</span><span class="sxs-lookup"><span data-stu-id="321a7-132">Manage emergency call routing policies</span></span>](manage-emergency-call-routing-policies.md)
* [<span data-ttu-id="321a7-133">在 Microsoft Teams 中管理本機號碼政策</span><span class="sxs-lookup"><span data-stu-id="321a7-133">Manage caller ID policies in Microsoft Teams</span></span>](caller-id-policies.md)
* [<span data-ttu-id="321a7-134">管理語音路由策略</span><span class="sxs-lookup"><span data-stu-id="321a7-134">Manage voice routing policies</span></span>](manage-voice-routing-policies.md)
* [<span data-ttu-id="321a7-135">Microsoft Teams 中的通話政策</span><span class="sxs-lookup"><span data-stu-id="321a7-135">Calling policies in Microsoft Teams</span></span>](teams-calling-policy.md)
* [<span data-ttu-id="321a7-136">Microsoft Teams 中的通話停駐和取回</span><span class="sxs-lookup"><span data-stu-id="321a7-136">Call park and retrieve in Microsoft Teams</span></span>](call-park-and-retrieve.md)
* [<span data-ttu-id="321a7-137">建立和管理撥號對應表</span><span class="sxs-lookup"><span data-stu-id="321a7-137">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)
* [<span data-ttu-id="321a7-138">使用策略管理 Teams</span><span class="sxs-lookup"><span data-stu-id="321a7-138">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
