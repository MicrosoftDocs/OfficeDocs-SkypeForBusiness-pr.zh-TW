---
title: 在 Microsoft 團隊中通話駐留與取回
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 04/12/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 使用 [呼叫駐留] 和 [檢索], 在雲端的小組服務中保留通話。
ms.openlocfilehash: fc33ef6c36a9764e39840f384dc70aa1a692579c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36182274"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="9fe8f-103">在 Microsoft 團隊中通話駐留與取回</span><span class="sxs-lookup"><span data-stu-id="9fe8f-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="9fe8f-104">通話駐留與取回功能可讓使用者在雲端的小組服務中保留通話。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="9fe8f-105">當通話停用時, 服務會產生唯一的呼叫檢索程式碼。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="9fe8f-106">停用通話的使用者, 或其他人可以使用該程式碼和支援的 app 或裝置來檢索通話。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="9fe8f-107">使用通話駐留的一些常見案例如下:</span><span class="sxs-lookup"><span data-stu-id="9fe8f-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="9fe8f-108">[接待員] 負責在工廠中使用某個人的通話。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="9fe8f-109">然後, 接待員會宣佈通話, 並將代碼編號放在公用位址系統上。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="9fe8f-110">通話的使用者可以在工廠中挑選 [團隊電話], 然後輸入程式碼來檢索通話。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="9fe8f-111">使用者在行動裝置上公園通話, 因為裝置電池已用完電源。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="9fe8f-112">然後, 使用者可以輸入程式碼來從小組的手機中檢索通話。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="9fe8f-113">支援代表會公園客戶通話, 並在小組頻道上傳送公告, 讓專家來取得通話並協助客戶。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="9fe8f-114">專家在 [團隊用戶端] 中輸入程式碼來檢索通話</span><span class="sxs-lookup"><span data-stu-id="9fe8f-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9fe8f-115">此功能僅適用于 [僅限團隊部署模式]。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="9fe8f-116">如需有關團隊部署模式的詳細資訊, 請參閱[瞭解 Microsoft 團隊及商務用 Skype 共存與互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="9fe8f-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="9fe8f-117">需要授權</span><span class="sxs-lookup"><span data-stu-id="9fe8f-117">License required</span></span>

<span data-ttu-id="9fe8f-118">若要寄存與取回通話, 使用者必須是企業語音使用者, 且系統管理員必須為使用者授予通話駐留原則。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="9fe8f-119">如需授權模型的詳細資訊, 請參閱[Microsoft 團隊適用的 Office 365 授權](office-365-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-119">For more information about the licensing model, see [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="9fe8f-120">通話駐留及取得功能可用性</span><span class="sxs-lookup"><span data-stu-id="9fe8f-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="9fe8f-121">下列用戶端和裝置目前支援通話駐留和取回。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="9fe8f-122">(在 [僅限小組] 模式中支援, 有或沒有 PSTN 連接)。)</span><span class="sxs-lookup"><span data-stu-id="9fe8f-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="9fe8f-123">功能</span><span class="sxs-lookup"><span data-stu-id="9fe8f-123">Capability</span></span> | <span data-ttu-id="9fe8f-124">團隊桌面</span><span class="sxs-lookup"><span data-stu-id="9fe8f-124">Teams Desktop</span></span> | <span data-ttu-id="9fe8f-125">團隊 Mac 應用程式</span><span class="sxs-lookup"><span data-stu-id="9fe8f-125">Teams Mac App</span></span> | <span data-ttu-id="9fe8f-126">小組 Web App (邊緣)</span><span class="sxs-lookup"><span data-stu-id="9fe8f-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="9fe8f-127">團隊行動 iOS/Android 應用程式</span><span class="sxs-lookup"><span data-stu-id="9fe8f-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="9fe8f-128">團隊 IP 電話</span><span class="sxs-lookup"><span data-stu-id="9fe8f-128">Teams IP phone</span></span> | <span data-ttu-id="9fe8f-129">商務用 Skype IP 電話</span><span class="sxs-lookup"><span data-stu-id="9fe8f-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="9fe8f-130">寄存通話</span><span class="sxs-lookup"><span data-stu-id="9fe8f-130">Park a call</span></span> | <span data-ttu-id="9fe8f-131">是的</span><span class="sxs-lookup"><span data-stu-id="9fe8f-131">Yes</span></span> | <span data-ttu-id="9fe8f-132">是的</span><span class="sxs-lookup"><span data-stu-id="9fe8f-132">Yes</span></span> | <span data-ttu-id="9fe8f-133">是的</span><span class="sxs-lookup"><span data-stu-id="9fe8f-133">Yes</span></span> | <span data-ttu-id="9fe8f-134">是的</span><span class="sxs-lookup"><span data-stu-id="9fe8f-134">Yes</span></span> | <span data-ttu-id="9fe8f-135">即將推出</span><span class="sxs-lookup"><span data-stu-id="9fe8f-135">Coming soon</span></span>| <span data-ttu-id="9fe8f-136">不</span><span class="sxs-lookup"><span data-stu-id="9fe8f-136">No</span></span> |
| <span data-ttu-id="9fe8f-137">檢索寄存通話</span><span class="sxs-lookup"><span data-stu-id="9fe8f-137">Retrieve a parked call</span></span> | <span data-ttu-id="9fe8f-138">是的</span><span class="sxs-lookup"><span data-stu-id="9fe8f-138">Yes</span></span> | <span data-ttu-id="9fe8f-139">是的</span><span class="sxs-lookup"><span data-stu-id="9fe8f-139">Yes</span></span> | <span data-ttu-id="9fe8f-140">是的</span><span class="sxs-lookup"><span data-stu-id="9fe8f-140">Yes</span></span> | <span data-ttu-id="9fe8f-141">是的</span><span class="sxs-lookup"><span data-stu-id="9fe8f-141">Yes</span></span> | <span data-ttu-id="9fe8f-142">即將推出</span><span class="sxs-lookup"><span data-stu-id="9fe8f-142">Coming soon</span></span>| <span data-ttu-id="9fe8f-143">不</span><span class="sxs-lookup"><span data-stu-id="9fe8f-143">No</span></span> |
| <span data-ttu-id="9fe8f-144">Unretrieved 電話鈴聲傳回</span><span class="sxs-lookup"><span data-stu-id="9fe8f-144">Unretrieved call ring back</span></span> | <span data-ttu-id="9fe8f-145">是的</span><span class="sxs-lookup"><span data-stu-id="9fe8f-145">Yes</span></span> | <span data-ttu-id="9fe8f-146">是的</span><span class="sxs-lookup"><span data-stu-id="9fe8f-146">Yes</span></span> | <span data-ttu-id="9fe8f-147">是的</span><span class="sxs-lookup"><span data-stu-id="9fe8f-147">Yes</span></span> | <span data-ttu-id="9fe8f-148">是的</span><span class="sxs-lookup"><span data-stu-id="9fe8f-148">Yes</span></span> | <span data-ttu-id="9fe8f-149">即將推出</span><span class="sxs-lookup"><span data-stu-id="9fe8f-149">Coming soon</span></span>| <span data-ttu-id="9fe8f-150">不</span><span class="sxs-lookup"><span data-stu-id="9fe8f-150">No</span></span> |

## <a name="configuring-call-park-and-retrieve"></a><span data-ttu-id="9fe8f-151">設定通話寄存與取回</span><span class="sxs-lookup"><span data-stu-id="9fe8f-151">Configuring call park and retrieve</span></span>

<span data-ttu-id="9fe8f-152">您必須是系統管理員, 才能設定通話駐留和取回, 而且預設是停用此功能。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-152">You must be an administrator to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="9fe8f-153">您可以為使用者啟用它, 並使用通話駐留原則來建立使用者群組。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="9fe8f-154">當您將相同的原則套用到一組使用者時, 他們可以在自己的情況下寄存和取回通話。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="9fe8f-155">若要設定使用者的通話駐留, 並建立通話駐留使用者群組, 請遵循下列的[指派通話駐留原則](#assign-a-call-park-policy)程式。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="9fe8f-156">如需如何使用通話公園和取得功能的相關資訊, 請參閱[在團隊中寄存通話](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="9fe8f-157">啟用通話駐留原則</span><span class="sxs-lookup"><span data-stu-id="9fe8f-157">Enable a call park policy</span></span>

<span data-ttu-id="9fe8f-158">請依照下列步驟來啟用通話駐留原則:</span><span class="sxs-lookup"><span data-stu-id="9fe8f-158">Follow these steps to enable a call park policy:</span></span>

1. <span data-ttu-id="9fe8f-159">移至**Microsoft 團隊系統管理中心** > 的 [**語音** > **通話] 寄存原則**。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-159">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="9fe8f-160">選取 [**新增原則**]。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-160">Select **New policy**.</span></span>
3. <span data-ttu-id="9fe8f-161">為原則命名, 然後將 [**允許通話駐留**] 切換為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-161">Give the policy a name, and then switch **Allow Call park** to **On**.</span></span>
4. <span data-ttu-id="9fe8f-162">選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-162">Select **Save**.</span></span>

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="9fe8f-163">指派通話駐留原則</span><span class="sxs-lookup"><span data-stu-id="9fe8f-163">Assign a call park policy</span></span>

<span data-ttu-id="9fe8f-164">請依照下列步驟, 將通話駐留原則指派給一或多位使用者:</span><span class="sxs-lookup"><span data-stu-id="9fe8f-164">Follow these steps to assign a call park policy to one or more users:</span></span>

1. <span data-ttu-id="9fe8f-165">移至**Microsoft 團隊系統管理中心** > 的 [**語音** > **通話] 寄存原則**。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-165">Go to **Microsoft Teams admin center** > **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="9fe8f-166">按一下原則名稱左方, 選取原則。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-166">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="9fe8f-167">選取 [**管理使用者**]。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-167">Select **Manage users**.</span></span>
4. <span data-ttu-id="9fe8f-168">在 [**管理使用者**] 窗格中, 依 [顯示名稱] 或 [使用者名稱] 搜尋使用者, 選取名稱, 然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-168">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="9fe8f-169">針對您要新增的每個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-169">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="9fe8f-170">完成新增使用者後, 請選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-170">When you are finished adding users, select **Save**.</span></span>
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a><span data-ttu-id="9fe8f-171">使用 PowerShell 設定通話駐留及檢索</span><span class="sxs-lookup"><span data-stu-id="9fe8f-171">Configure call park and retrieve with PowerShell</span></span>

<span data-ttu-id="9fe8f-172">使用[新的-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell Cmdlet 來建立通話駐留原則。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-172">Use the [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to create a call park policy.</span></span>

<span data-ttu-id="9fe8f-173">使用[授與 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell Cmdlet 來授與來電寄存原則。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-173">Use the [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet to grant a call park policy.</span></span>

<span data-ttu-id="9fe8f-174">您可以使用 [[設定] CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)來變更預設設定, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="9fe8f-174">You can change the default setting by using [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) as follows:</span></span>

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a><span data-ttu-id="9fe8f-175">疑難排解</span><span class="sxs-lookup"><span data-stu-id="9fe8f-175">Troubleshooting</span></span>

<span data-ttu-id="9fe8f-176">如果使用者看不到 [寄存] 或 [取得] 按鈕:</span><span class="sxs-lookup"><span data-stu-id="9fe8f-176">If users can’t see the park or retrieve button:</span></span> 

- <span data-ttu-id="9fe8f-177">檢查使用者是否已啟用通話駐留原則。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-177">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="9fe8f-178">如果使用者嘗試檢索通話, 但卻失敗, 請檢查下列專案:</span><span class="sxs-lookup"><span data-stu-id="9fe8f-178">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="9fe8f-179">確認使用者使用的是 [團隊用戶端] 或 [小組啟用的裝置/電話]</span><span class="sxs-lookup"><span data-stu-id="9fe8f-179">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="9fe8f-180">群組–使用者是否為通話駐留群組的成員？</span><span class="sxs-lookup"><span data-stu-id="9fe8f-180">Grouping – is the user a member of the call park group?</span></span>
- <span data-ttu-id="9fe8f-181">孤島模式–在團隊安全島模式中無法使用通話駐留與取回功能。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-181">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="9fe8f-182">通話已被檢索或終止。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-182">The call has already been retrieved or terminated.</span></span>

## <a name="more-information"></a><span data-ttu-id="9fe8f-183">其他資訊</span><span class="sxs-lookup"><span data-stu-id="9fe8f-183">More information</span></span>

<span data-ttu-id="9fe8f-184">[在團隊中寄存通話](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)。</span><span class="sxs-lookup"><span data-stu-id="9fe8f-184">[Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>