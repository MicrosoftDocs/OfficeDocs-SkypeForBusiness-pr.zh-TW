---
title: 在 Microsoft 團隊中通話駐留與取回
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 04/12/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: 瞭解如何使用通話駐留及取回功能，在雲端的小組服務中保持通話。
ms.openlocfilehash: 1fddc7acb6d670515fd5903731fab7cacd319f80
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255536"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a><span data-ttu-id="b5ecc-103">在 Microsoft 團隊中通話駐留與取回</span><span class="sxs-lookup"><span data-stu-id="b5ecc-103">Call park and retrieve in Microsoft Teams</span></span>

<span data-ttu-id="b5ecc-104">通話駐留與取回功能可讓使用者在雲端的小組服務中保留通話。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-104">Call park and retrieve is a feature that lets a user place a call on hold in the Teams service in the cloud.</span></span> <span data-ttu-id="b5ecc-105">當通話停用時，服務會產生唯一的呼叫檢索程式碼。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-105">When a call is parked, the service generates a unique code for call retrieval.</span></span> <span data-ttu-id="b5ecc-106">停用通話的使用者，或其他人可以使用該程式碼和支援的 app 或裝置來檢索通話。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-106">The user who parked the call or someone else can then use that code and a supported app or device to retrieve the call.</span></span> 

<span data-ttu-id="b5ecc-107">使用通話駐留的一些常見案例如下：</span><span class="sxs-lookup"><span data-stu-id="b5ecc-107">Some of the common scenarios for using call park are:</span></span> 

- <span data-ttu-id="b5ecc-108">[接待員] 負責在工廠中使用某個人的通話。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-108">A receptionist parks a call for someone working in a factory.</span></span> <span data-ttu-id="b5ecc-109">然後，接待員會宣佈通話，並將代碼編號放在公用位址系統上。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-109">The receptionist then announces the call and the code number over the public address system.</span></span> <span data-ttu-id="b5ecc-110">通話的使用者可以在工廠中挑選 [團隊電話]，然後輸入程式碼來檢索通話。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-110">The user who the call is for can then pick up a Teams phone on the factory floor and enter the code to retrieve the call.</span></span>
- <span data-ttu-id="b5ecc-111">使用者在行動裝置上公園通話，因為裝置電池已用完電源。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-111">A user parks a call on a mobile device because the device battery is running out of power.</span></span> <span data-ttu-id="b5ecc-112">然後，使用者可以輸入程式碼來從小組的手機中檢索通話。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-112">The user can then enter the code to retrieve the call from a Teams desk phone.</span></span>
- <span data-ttu-id="b5ecc-113">支援代表會公園客戶通話，並在小組頻道上傳送公告，讓專家來取得通話並協助客戶。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-113">A support representative parks a customer call and sends an announcement on a Teams channel for an expert to retrieve the call and help the customer.</span></span> <span data-ttu-id="b5ecc-114">專家在 [團隊用戶端] 中輸入程式碼來檢索通話</span><span class="sxs-lookup"><span data-stu-id="b5ecc-114">An expert enters the code in Teams clients to retrieve the call</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b5ecc-115">此功能僅適用于 [僅限團隊部署模式]。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-115">This feature is only available in Teams Only deployment mode.</span></span> <span data-ttu-id="b5ecc-116">如需有關團隊部署模式的詳細資訊，請參閱 [瞭解 Microsoft 團隊及商務用 Skype 共存與互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="b5ecc-116">For more information about Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="b5ecc-117">需要授權</span><span class="sxs-lookup"><span data-stu-id="b5ecc-117">License required</span></span>

<span data-ttu-id="b5ecc-118">若要寄存與取回通話，使用者必須是企業語音使用者，且系統管理員必須為使用者授予通話駐留原則。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-118">To park and retrieve calls, a user must be an Enterprise Voice user, and an administrator must grant the user a call park policy.</span></span> <span data-ttu-id="b5ecc-119">如需授權模型的詳細資訊，請參閱 [Microsoft 團隊服務說明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-119">For more information about the licensing model, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="call-park-and-retrieve-feature-availability"></a><span data-ttu-id="b5ecc-120">通話駐留及取得功能可用性</span><span class="sxs-lookup"><span data-stu-id="b5ecc-120">Call park and retrieve feature availability</span></span>

<span data-ttu-id="b5ecc-121">下列用戶端和裝置目前支援通話駐留和取回。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-121">Call park and retrieve is currently supported by the following clients and devices.</span></span> <span data-ttu-id="b5ecc-122">在只有 PSTN 連線的情況下，在 [僅限團隊] 模式中支援 (。 ) </span><span class="sxs-lookup"><span data-stu-id="b5ecc-122">(Supported in Teams Only mode, with or without PSTN connectivity.)</span></span>

| <span data-ttu-id="b5ecc-123">功能</span><span class="sxs-lookup"><span data-stu-id="b5ecc-123">Capability</span></span> | <span data-ttu-id="b5ecc-124">團隊桌面</span><span class="sxs-lookup"><span data-stu-id="b5ecc-124">Teams Desktop</span></span> | <span data-ttu-id="b5ecc-125">團隊 Mac 應用程式</span><span class="sxs-lookup"><span data-stu-id="b5ecc-125">Teams Mac App</span></span> | <span data-ttu-id="b5ecc-126">團隊 Web App (邊緣) </span><span class="sxs-lookup"><span data-stu-id="b5ecc-126">Teams Web App (Edge)</span></span> |<span data-ttu-id="b5ecc-127">團隊行動 iOS/Android 應用程式</span><span class="sxs-lookup"><span data-stu-id="b5ecc-127">Teams mobile iOS/Android App</span></span> | <span data-ttu-id="b5ecc-128">團隊 IP 電話</span><span class="sxs-lookup"><span data-stu-id="b5ecc-128">Teams IP phone</span></span> | <span data-ttu-id="b5ecc-129">商務用 Skype IP 電話</span><span class="sxs-lookup"><span data-stu-id="b5ecc-129">Skype for Business IP phone</span></span> |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| <span data-ttu-id="b5ecc-130">寄存通話</span><span class="sxs-lookup"><span data-stu-id="b5ecc-130">Park a call</span></span> | <span data-ttu-id="b5ecc-131">是</span><span class="sxs-lookup"><span data-stu-id="b5ecc-131">Yes</span></span> | <span data-ttu-id="b5ecc-132">是</span><span class="sxs-lookup"><span data-stu-id="b5ecc-132">Yes</span></span> | <span data-ttu-id="b5ecc-133">是</span><span class="sxs-lookup"><span data-stu-id="b5ecc-133">Yes</span></span> | <span data-ttu-id="b5ecc-134">是</span><span class="sxs-lookup"><span data-stu-id="b5ecc-134">Yes</span></span> | <span data-ttu-id="b5ecc-135">是</span><span class="sxs-lookup"><span data-stu-id="b5ecc-135">Yes</span></span> | <span data-ttu-id="b5ecc-136">否</span><span class="sxs-lookup"><span data-stu-id="b5ecc-136">No</span></span> |
| <span data-ttu-id="b5ecc-137">檢索寄存通話</span><span class="sxs-lookup"><span data-stu-id="b5ecc-137">Retrieve a parked call</span></span> | <span data-ttu-id="b5ecc-138">是</span><span class="sxs-lookup"><span data-stu-id="b5ecc-138">Yes</span></span> | <span data-ttu-id="b5ecc-139">是</span><span class="sxs-lookup"><span data-stu-id="b5ecc-139">Yes</span></span> | <span data-ttu-id="b5ecc-140">是</span><span class="sxs-lookup"><span data-stu-id="b5ecc-140">Yes</span></span> | <span data-ttu-id="b5ecc-141">是</span><span class="sxs-lookup"><span data-stu-id="b5ecc-141">Yes</span></span> | <span data-ttu-id="b5ecc-142">是</span><span class="sxs-lookup"><span data-stu-id="b5ecc-142">Yes</span></span> | <span data-ttu-id="b5ecc-143">否</span><span class="sxs-lookup"><span data-stu-id="b5ecc-143">No</span></span> |
| <span data-ttu-id="b5ecc-144">Unretrieved 電話鈴聲傳回</span><span class="sxs-lookup"><span data-stu-id="b5ecc-144">Unretrieved call ring back</span></span> | <span data-ttu-id="b5ecc-145">是</span><span class="sxs-lookup"><span data-stu-id="b5ecc-145">Yes</span></span> | <span data-ttu-id="b5ecc-146">是</span><span class="sxs-lookup"><span data-stu-id="b5ecc-146">Yes</span></span> | <span data-ttu-id="b5ecc-147">是</span><span class="sxs-lookup"><span data-stu-id="b5ecc-147">Yes</span></span> | <span data-ttu-id="b5ecc-148">是</span><span class="sxs-lookup"><span data-stu-id="b5ecc-148">Yes</span></span> | <span data-ttu-id="b5ecc-149">是</span><span class="sxs-lookup"><span data-stu-id="b5ecc-149">Yes</span></span> | <span data-ttu-id="b5ecc-150">否</span><span class="sxs-lookup"><span data-stu-id="b5ecc-150">No</span></span> |

## <a name="configure-call-park-and-retrieve"></a><span data-ttu-id="b5ecc-151">設定通話寄存與取回</span><span class="sxs-lookup"><span data-stu-id="b5ecc-151">Configure call park and retrieve</span></span>

<span data-ttu-id="b5ecc-152">您必須是系統管理員，才能設定通話駐留和取回，而且預設是停用此功能。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-152">You must be an admin to configure call park and retrieve, and the feature is disabled by default.</span></span> <span data-ttu-id="b5ecc-153">您可以為使用者啟用它，並使用通話駐留原則來建立使用者群組。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-153">You can enable it for users and create user groups using the call park policy.</span></span> <span data-ttu-id="b5ecc-154">當您將相同的原則套用到一組使用者時，他們可以在自己的情況下寄存和取回通話。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-154">When you apply the same policy to a set of users, they can park and retrieve calls among themselves.</span></span> <span data-ttu-id="b5ecc-155">若要設定使用者的通話駐留，並建立通話駐留使用者群組，請遵循下列的 [指派通話駐留原則](#assign-a-call-park-policy) 程式。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-155">To configure call park for users and create call park user groups, follow the [Assign a call park policy](#assign-a-call-park-policy) procedure below.</span></span>

<span data-ttu-id="b5ecc-156">如需如何使用通話公園和取得功能的相關資訊，請參閱 [在團隊中寄存通話](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-156">For information about how to use the call park and retrieve feature, see [Park a call in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).</span></span>

### <a name="enable-a-call-park-policy"></a><span data-ttu-id="b5ecc-157">啟用通話駐留原則</span><span class="sxs-lookup"><span data-stu-id="b5ecc-157">Enable a call park policy</span></span>

1. <span data-ttu-id="b5ecc-158">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音**  >  **通話寄存原則**]。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-158">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="b5ecc-159">選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-159">Select **Add**.</span></span>
3. <span data-ttu-id="b5ecc-160">為原則命名，然後將 [ **允許通話駐留** ] 切換為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-160">Give the policy a name, and then switch **Allow call park** to **On**.</span></span>
4. <span data-ttu-id="b5ecc-161">選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-161">Select **Save**.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="b5ecc-162">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5ecc-162">Using PowerShell</span></span>

<span data-ttu-id="b5ecc-163">請參閱 [新-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-163">See [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps).</span></span>

### <a name="edit-a-call-park-policy"></a><span data-ttu-id="b5ecc-164">編輯通話寄存原則</span><span class="sxs-lookup"><span data-stu-id="b5ecc-164">Edit a call park policy</span></span>

1. <span data-ttu-id="b5ecc-165">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音**  >  **通話寄存原則**]。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-165">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Call park policies**.</span></span>
2. <span data-ttu-id="b5ecc-166">按一下原則名稱左邊的，然後按一下 [ **編輯**]，選取原則。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-166">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="b5ecc-167">[ **允許通話駐留** ] 切換為 [ **關閉** ] 或 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-167">Switch **Allow call park** to **Off** or **On**.</span></span>
4. <span data-ttu-id="b5ecc-168">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-168">Click **Save**.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="b5ecc-169">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5ecc-169">Using PowerShell</span></span>

<span data-ttu-id="b5ecc-170">請參閱 [設定 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-170">See [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps).</span></span> <span data-ttu-id="b5ecc-171">例如，若要變更預設設定，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b5ecc-171">For example, to change the default setting, run the following:</span></span>

  ```PowerShell
  Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true
  ```

### <a name="assign-a-call-park-policy"></a><span data-ttu-id="b5ecc-172">指派通話駐留原則</span><span class="sxs-lookup"><span data-stu-id="b5ecc-172">Assign a call park policy</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]
 
<span data-ttu-id="b5ecc-173">另請參閱 [授與 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-173">See also [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b5ecc-174">疑難排解</span><span class="sxs-lookup"><span data-stu-id="b5ecc-174">Troubleshooting</span></span>

<span data-ttu-id="b5ecc-175">如果使用者看不到 [寄存] 或 [取得] 按鈕：</span><span class="sxs-lookup"><span data-stu-id="b5ecc-175">If users can't see the park or retrieve button:</span></span> 

- <span data-ttu-id="b5ecc-176">檢查使用者是否已啟用通話駐留原則。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-176">Check that the user has the Call Park policy enabled.</span></span> 

<span data-ttu-id="b5ecc-177">如果使用者嘗試檢索通話，但卻失敗，請檢查下列專案：</span><span class="sxs-lookup"><span data-stu-id="b5ecc-177">If a user attempts to retrieve a call and is unsuccessful, check the following:</span></span>

- <span data-ttu-id="b5ecc-178">確認使用者使用的是 [團隊用戶端] 或 [小組啟用的裝置/電話]</span><span class="sxs-lookup"><span data-stu-id="b5ecc-178">Verify that the user is using the Teams client or a Teams-enabled device/Phone</span></span>
- <span data-ttu-id="b5ecc-179">[群組]-使用者是 [呼叫駐留] 群組的成員，而這是以擁有相同的小組通話駐留原則指派的方式為基礎。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-179">Grouping – is the user a member of the call park group, which is based on having the same Teams Call Park policy assigned.</span></span> 
- <span data-ttu-id="b5ecc-180">孤島模式–在團隊安全島模式中無法使用通話駐留與取回功能。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-180">Island mode – Call park and retrieve is unavailable in Teams island mode.</span></span>
- <span data-ttu-id="b5ecc-181">通話已被檢索或終止。</span><span class="sxs-lookup"><span data-stu-id="b5ecc-181">The call has already been retrieved or terminated.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b5ecc-182">相關主題</span><span class="sxs-lookup"><span data-stu-id="b5ecc-182">Related topics</span></span>

[<span data-ttu-id="b5ecc-183">在團隊中寄存通話</span><span class="sxs-lookup"><span data-stu-id="b5ecc-183">Park a call in Teams</span></span>](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[<span data-ttu-id="b5ecc-184">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="b5ecc-184">Assign policies to your users in Teams</span></span>](assign-policies.md)
