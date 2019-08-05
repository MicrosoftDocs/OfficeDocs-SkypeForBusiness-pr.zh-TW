---
title: 為 Microsoft 團隊設定雲端影片互通性
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: srividhc
description: 本文說明如何規劃及設定貴組織使用者的雲端視頻互通性。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b171b3fb5e73561ea5aea54e6e4f25bfabe6b0dc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "36180577"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="bf33e-103">為 Microsoft 團隊設定雲端影片互通性</span><span class="sxs-lookup"><span data-stu-id="bf33e-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="bf33e-104">在[雲端視頻 Interop 合作夥伴上選取](cloud-video-interop.md)之後, 您將需要規劃您的部署、使用提供詳細資料與合作夥伴租使用者金鑰的設定, 以及同意您組織中的視頻互通性應用程式。</span><span class="sxs-lookup"><span data-stu-id="bf33e-104">After you have [chosen on your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="bf33e-105">下圖概述此程式。</span><span class="sxs-lookup"><span data-stu-id="bf33e-105">The following diagram outlines the process.</span></span> 

![在組織中部署 CVI](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="bf33e-107">平面圖</span><span class="sxs-lookup"><span data-stu-id="bf33e-107">Plan</span></span>

<span data-ttu-id="bf33e-108">請參閱[Microsoft 團隊的雲端影片交互操作](cloud-video-interop.md), 以取得有關如何識別貴組織中要使用的合作夥伴或合作夥伴的資訊。</span><span class="sxs-lookup"><span data-stu-id="bf33e-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="bf33e-109">規劃使用者的基礎/並行/網站範圍啟用:</span><span class="sxs-lookup"><span data-stu-id="bf33e-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="bf33e-110">挑選部署模型/託管模型供您使用</span><span class="sxs-lookup"><span data-stu-id="bf33e-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="bf33e-111">選取適用于貴組織的授權方案。</span><span class="sxs-lookup"><span data-stu-id="bf33e-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="bf33e-112">針對 Vm 的容量進行規劃是您要裝載的是您的影片基礎結構。</span><span class="sxs-lookup"><span data-stu-id="bf33e-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="bf33e-113">設定</span><span class="sxs-lookup"><span data-stu-id="bf33e-113">Configure</span></span> 

<span data-ttu-id="bf33e-114">若要設定雲端視頻互通性, 請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="bf33e-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="bf33e-115">從您所選的合作夥伴/合作夥伴取得配置資訊 (租使用者金鑰、appIds ...)。</span><span class="sxs-lookup"><span data-stu-id="bf33e-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="bf33e-116">您可以在組織中使用一或多個視頻互通性合作夥伴</span><span class="sxs-lookup"><span data-stu-id="bf33e-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="bf33e-117">確定您的網路已正確設定。</span><span class="sxs-lookup"><span data-stu-id="bf33e-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="bf33e-118">針對您的周邊網路遍歷設定您的標準視頻防火牆以支援。</span><span class="sxs-lookup"><span data-stu-id="bf33e-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="bf33e-119">例如：</span><span class="sxs-lookup"><span data-stu-id="bf33e-119">For example:</span></span> 
    - <span data-ttu-id="bf33e-120">Cisco VCS-e</span><span class="sxs-lookup"><span data-stu-id="bf33e-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="bf33e-121">Polycom RPAD</span><span class="sxs-lookup"><span data-stu-id="bf33e-121">Polycom RPAD</span></span>

3. <span data-ttu-id="bf33e-122">使用 exchange 和 OTD 設定整合的會議室。</span><span class="sxs-lookup"><span data-stu-id="bf33e-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="bf33e-123">在大多數情況下, 需要在您的環境中設定和設定額外的轉接。</span><span class="sxs-lookup"><span data-stu-id="bf33e-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="bf33e-124">布建</span><span class="sxs-lookup"><span data-stu-id="bf33e-124">Provision</span></span>
 
<span data-ttu-id="bf33e-125">租使用者金鑰就是向合作夥伴服務撥出。</span><span class="sxs-lookup"><span data-stu-id="bf33e-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="bf33e-126">在下列範例中, 813878896@t.plcm.vc 是租使用者金鑰。</span><span class="sxs-lookup"><span data-stu-id="bf33e-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![租使用者金鑰範例](media/tenant-key-example.png) 

<span data-ttu-id="bf33e-128">您必須執行下列 Cmdlet 來設定租使用者金鑰, 也可讓 [選取使用者] 或整個組織建立含影片交互操作座標的會議。</span><span class="sxs-lookup"><span data-stu-id="bf33e-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="bf33e-129">\*\* [CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):\*\* Microsoft 會針對我們支援的每個合作夥伴提供預先構造的原則, 讓您指定要用於雲端影片互通性的合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="bf33e-129">**[Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="bf33e-130">這個 Cmdlet 可讓您識別您可以在組織中使用的預先構造原則。</span><span class="sxs-lookup"><span data-stu-id="bf33e-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="bf33e-131">您可以利用 Grant CsTeamsVideoInteropServicePolicy Cmdlet, 將此原則指派給一或多個使用者。</span><span class="sxs-lookup"><span data-stu-id="bf33e-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="bf33e-132">**[授與 CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** Grant CsTeamsVideoInteropServicePolicy Cmdlet 可讓您指派預先構造的原則供貴組織使用, 或將原則指派給特定的使用者。</span><span class="sxs-lookup"><span data-stu-id="bf33e-132">**[Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="bf33e-133">**[新-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** 使用新-CsVideoInteropServiceProvider 指定貴組織想要使用之受支援之 CVI 合作夥伴的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bf33e-133">**[New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="bf33e-134">\*\* [CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):\*\* 使用 CsVideoInteropServiceProvider, 更新貴組織使用之受支援之 CVI 夥伴的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="bf33e-134">**[Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="bf33e-135">\*\* [CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):\*\* 取得已設定為在組織內使用的所有提供者。</span><span class="sxs-lookup"><span data-stu-id="bf33e-135">**[Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="bf33e-136">**[移除-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** 使用 [移除-CsVideoInteropServiceProvider], 移除貴組織不再使用之提供者的所有提供者資訊。</span><span class="sxs-lookup"><span data-stu-id="bf33e-136">**[Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="bf33e-137">同意</span><span class="sxs-lookup"><span data-stu-id="bf33e-137">Consent</span></span>

<span data-ttu-id="bf33e-138">您必須為影片 teleconferencing 裝置 (VTCs) 提供許可權, 才能透過合作夥伴服務加入貴組織的會議。</span><span class="sxs-lookup"><span data-stu-id="bf33e-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="bf33e-139">您的合作夥伴也會提供此同意連結。</span><span class="sxs-lookup"><span data-stu-id="bf33e-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="bf33e-140">完成這些步驟後, 透過上述授權 Cmdlet 或組織中的所有使用者 (如果已啟用租使用者), 會在排程的所有團隊會議中擁有 VTC 座標。</span><span class="sxs-lookup"><span data-stu-id="bf33e-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="bf33e-141">任何 VTC 都可以透過這些座標加入這些會議。</span><span class="sxs-lookup"><span data-stu-id="bf33e-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="bf33e-142">名稱</span><span class="sxs-lookup"><span data-stu-id="bf33e-142">Name</span></span>|<span data-ttu-id="bf33e-143">應用程式許可權簡短描述</span><span class="sxs-lookup"><span data-stu-id="bf33e-143">Application Permission Short Description</span></span>| <span data-ttu-id="bf33e-144">說明</span><span class="sxs-lookup"><span data-stu-id="bf33e-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="bf33e-145">JoinGroupCall。</span><span class="sxs-lookup"><span data-stu-id="bf33e-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="bf33e-146">以應用程式 (預覽) 加入群組通話與會議</span><span class="sxs-lookup"><span data-stu-id="bf33e-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="bf33e-147">允許 app 在您的組織中加入群組通話和排程會議, 而無需登入的使用者。</span><span class="sxs-lookup"><span data-stu-id="bf33e-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="bf33e-148">App 將會以目錄使用者的許可權加入到您租使用者的會議中。</span><span class="sxs-lookup"><span data-stu-id="bf33e-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="bf33e-149">JoinGroupCallasGuest。</span><span class="sxs-lookup"><span data-stu-id="bf33e-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="bf33e-150">以來賓使用者身分加入群組通話和會議 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="bf33e-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="bf33e-151">允許 app 在沒有登入使用者的情況下, 以匿名方式加入組織中的群組通話和排程會議。</span><span class="sxs-lookup"><span data-stu-id="bf33e-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="bf33e-152">App 會以來賓身分加入到您租使用者的會議中。</span><span class="sxs-lookup"><span data-stu-id="bf33e-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="bf33e-153">AccessMedia。</span><span class="sxs-lookup"><span data-stu-id="bf33e-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="bf33e-154">以應用程式 (預覽) 存取通話中的媒體資料流程</span><span class="sxs-lookup"><span data-stu-id="bf33e-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="bf33e-155">允許 app 直接存取通話中的媒體資料流程, 無需登入的使用者。</span><span class="sxs-lookup"><span data-stu-id="bf33e-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="bf33e-156">OnlineMeetings. 全部閱讀. 全部</span><span class="sxs-lookup"><span data-stu-id="bf33e-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="bf33e-157">閱讀線上會議詳細資料 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="bf33e-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="bf33e-158">允許 app 在您的組織中讀取線上會議詳細資料, 不需要登入的使用者。</span><span class="sxs-lookup"><span data-stu-id="bf33e-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="bf33e-159">表</span><span class="sxs-lookup"><span data-stu-id="bf33e-159">Schedule</span></span>

<span data-ttu-id="bf33e-160">接下來, 使用影片交互操作座標排程團隊會議。</span><span class="sxs-lookup"><span data-stu-id="bf33e-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="bf33e-161">已啟用的使用者可以透過以下方式排程團隊會議:</span><span class="sxs-lookup"><span data-stu-id="bf33e-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="bf33e-162">Outlook 的團隊會議增益集</span><span class="sxs-lookup"><span data-stu-id="bf33e-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="bf33e-163">團隊用戶端桌面及行動裝置</span><span class="sxs-lookup"><span data-stu-id="bf33e-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="bf33e-164">起來</span><span class="sxs-lookup"><span data-stu-id="bf33e-164">Join</span></span>

<span data-ttu-id="bf33e-165">您可以透過下列方式, 與您的 VTC 裝置加入團隊會議:</span><span class="sxs-lookup"><span data-stu-id="bf33e-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="bf33e-166">IVR (互動式語音回復)</span><span class="sxs-lookup"><span data-stu-id="bf33e-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="bf33e-167">您可以使用 tenantkey @ 網域撥入合作夥伴的 IVR。</span><span class="sxs-lookup"><span data-stu-id="bf33e-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="bf33e-168">在您進入合作夥伴 IVR 之後, 系統會提示您輸入 VTC conferenceId, 這會將您連線至 [團隊會議]。</span><span class="sxs-lookup"><span data-stu-id="bf33e-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="bf33e-169">直接撥號</span><span class="sxs-lookup"><span data-stu-id="bf33e-169">Direct dial</span></span>
    - <span data-ttu-id="bf33e-170">您可以直接撥入小組會議, 而不需與夥伴的 IVR 互動, 只要使用 [直接撥號] 功能 tenantkey 的完整字串即可。VTC ConferenceId @ 網域。</span><span class="sxs-lookup"><span data-stu-id="bf33e-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="bf33e-171">單點觸控撥號</span><span class="sxs-lookup"><span data-stu-id="bf33e-171">One-touch dial</span></span>
    - <span data-ttu-id="bf33e-172">如果您有整合的小組聊天室, 您可以使用合作夥伴提供的單一觸控式撥號功能 (不需要輸入任何撥號字串)。</span><span class="sxs-lookup"><span data-stu-id="bf33e-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="bf33e-173">最後, 在會議中使用音訊、影片和內容共用與團隊使用者接洽。</span><span class="sxs-lookup"><span data-stu-id="bf33e-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span> 