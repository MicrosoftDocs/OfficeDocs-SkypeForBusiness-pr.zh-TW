---
title: 音訊會議與使用者 PSTN 通話的輸出通話限制原則
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 系統管理員可以控制使用者可以發出的音訊會議和使用者 PSTN 呼叫類型。
ms.openlocfilehash: 84601ed50d265bcd48b48b05e5625fcf86c34c7c
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2019
ms.locfileid: "36183726"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="e928a-103">音訊會議與使用者 PSTN 通話的輸出通話限制原則</span><span class="sxs-lookup"><span data-stu-id="e928a-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="e928a-104">在管理員中, 您可以使用出站通話控制來限制您組織中的使用者可以進行的音訊會議和使用者 PSTN 通話類型。</span><span class="sxs-lookup"><span data-stu-id="e928a-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="e928a-105">輸出呼叫控制可以在每位使用者的基礎上套用, 並提供下列兩個控制項來單獨限制每個輸出呼叫類型。</span><span class="sxs-lookup"><span data-stu-id="e928a-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="e928a-106">根據預設, 兩個控制項都設定為允許國際和國內呼出通話。</span><span class="sxs-lookup"><span data-stu-id="e928a-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="e928a-107">控制權</span><span class="sxs-lookup"><span data-stu-id="e928a-107">Control</span></span>|<span data-ttu-id="e928a-108">說明</span><span class="sxs-lookup"><span data-stu-id="e928a-108">Description</span></span>|<span data-ttu-id="e928a-109">控制選項</span><span class="sxs-lookup"><span data-stu-id="e928a-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e928a-110">音訊會議 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="e928a-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="e928a-111">限制輸出類型</span><span class="sxs-lookup"><span data-stu-id="e928a-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="e928a-112">內部允許的通話</span><span class="sxs-lookup"><span data-stu-id="e928a-112">calls that are allowed from within</span></span> </br><span data-ttu-id="e928a-113">由使用者組織的會議。</span><span class="sxs-lookup"><span data-stu-id="e928a-113">meetings organized by a user.</span></span>|<span data-ttu-id="e928a-114">國際和國內 (預設)</span><span class="sxs-lookup"><span data-stu-id="e928a-114">International and Domestic (default)</span></span></br><span data-ttu-id="e928a-115">家用</span><span class="sxs-lookup"><span data-stu-id="e928a-115">Domestic</span></span></br><span data-ttu-id="e928a-116">無</span><span class="sxs-lookup"><span data-stu-id="e928a-116">None</span></span>|
|<span data-ttu-id="e928a-117">最終使用者 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="e928a-117">End user PSTN calls</span></span>|<span data-ttu-id="e928a-118">限制通話類型</span><span class="sxs-lookup"><span data-stu-id="e928a-118">Restricts the type of calls</span></span> </br><span data-ttu-id="e928a-119">使用者可以進行的工作。</span><span class="sxs-lookup"><span data-stu-id="e928a-119">that can be made by a user.</span></span>|<span data-ttu-id="e928a-120">國際和國內 (預設)</span><span class="sxs-lookup"><span data-stu-id="e928a-120">International and Domestic (default)</span></span></br><span data-ttu-id="e928a-121">家用</span><span class="sxs-lookup"><span data-stu-id="e928a-121">Domestic</span></span></br><span data-ttu-id="e928a-122">無</span><span class="sxs-lookup"><span data-stu-id="e928a-122">None</span></span>|

   > [!NOTE]
   > <span data-ttu-id="e928a-123">如果撥打的電話號碼位於與會議召集人 (在音訊會議中) 設定的 Office 365, 或使用者 (在使用者 PSTN 呼叫的情況下), 則會被視為國內通話。</span><span class="sxs-lookup"><span data-stu-id="e928a-123">A call is considered domestic if the number dialed is in the same country where Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="e928a-124">限制音訊會議撥出通話</span><span class="sxs-lookup"><span data-stu-id="e928a-124">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="e928a-125">![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="e928a-125">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="e928a-126">在左側導覽中, 按一下 [**使用者**], 然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="e928a-126">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="e928a-127">按一下頁面頂端的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="e928a-127">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="e928a-128">按一下 [**音訊會議**] 旁的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="e928a-128">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="e928a-129">在 [**從會議撥出許可權**] 底下, 選取您想要的撥出限制選項。</span><span class="sxs-lookup"><span data-stu-id="e928a-129">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="e928a-130">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="e928a-130">Click **Save**.</span></span> 

<span data-ttu-id="e928a-131">![](media/sfb-logo-30x30.png) **使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="e928a-131">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.  <span data-ttu-id="e928a-132">在**商務用 Skype 系統管理中心**的左導覽中, 前往 [**音訊會議** > **使用者**], 然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="e928a-132">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.  <span data-ttu-id="e928a-133">在 [動作] 窗格中, 按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="e928a-133">In the Action pane, click **Edit**.</span></span>

3.  <span data-ttu-id="e928a-134">在 [**限制使用此使用者的會議進行撥**出] 底下, 選取您想要的撥出限制選項。</span><span class="sxs-lookup"><span data-stu-id="e928a-134">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![撥出選項的限制](media/restrictions-to-dial-outs.png)

5. <span data-ttu-id="e928a-136">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="e928a-136">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="e928a-137">**使用 PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e928a-137">**Using PowerShell**</span></span>

<span data-ttu-id="e928a-138">出站通話限制是由名為 OnlineDialOutPolicy 的單一原則所控制, 每個策略都有一個限制屬性。</span><span class="sxs-lookup"><span data-stu-id="e928a-138">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="e928a-139">原則無法自訂, 而是針對每個設定組合提供預先定義的原則實例。</span><span class="sxs-lookup"><span data-stu-id="e928a-139">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="e928a-140">您可以使用 CSOnlineDialOutPolicy Cmdlet 來查看輸出通話原則, 並使用授與 CSDialOutPolicy Cmdlet 將其指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="e928a-140">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="e928a-141">(請注意, Grant Cmdlet 不會包含「線上」一詞, 因為取得 Cmdlet 一樣。)</span><span class="sxs-lookup"><span data-stu-id="e928a-141">(Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.)</span></span> 

<span data-ttu-id="e928a-142">下表提供每個原則的概覽。</span><span class="sxs-lookup"><span data-stu-id="e928a-142">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e928a-143">身分識別 = "tag: DialoutCPCandPSTNInternational"</span><span class="sxs-lookup"><span data-stu-id="e928a-143">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="e928a-144">會議中的使用者可以撥出到國際和國內號碼, 此使用者也可以撥出電話給國際和國內電話號碼。</span><span class="sxs-lookup"><span data-stu-id="e928a-144">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="e928a-145">身分識別 = "tag: DialoutCPCDomesticPSTNInternational"</span><span class="sxs-lookup"><span data-stu-id="e928a-145">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="e928a-146">會議中的使用者只能撥出至國內號碼, 而這個使用者可以撥出電話給國際和國內號碼。</span><span class="sxs-lookup"><span data-stu-id="e928a-146">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="e928a-147">身分識別 = "tag: DialoutCPCDisabledPSTNInternational"</span><span class="sxs-lookup"><span data-stu-id="e928a-147">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="e928a-148">會議中的使用者無法進行任何撥出。此使用者可以撥出電話給國際和國內號碼。</span><span class="sxs-lookup"><span data-stu-id="e928a-148">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="e928a-149">身分識別 = "tag: DialoutCPCInternationalPSTNDomestic"</span><span class="sxs-lookup"><span data-stu-id="e928a-149">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="e928a-150">會議中的使用者可以撥出到國際和國內電話號碼, 而且這個使用者只能撥打出站通話至國內 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="e928a-150">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="e928a-151">身分識別 = "tag: DialoutCPCInternationalPSTNDisabled"</span><span class="sxs-lookup"><span data-stu-id="e928a-151">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="e928a-152">會議中的使用者可以撥出到國際和國內號碼, 而這個使用者就無法撥打緊急電話號碼以外的 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="e928a-152">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="e928a-153">身分識別 = "tag: DialoutCPCandPSTNDomestic"</span><span class="sxs-lookup"><span data-stu-id="e928a-153">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="e928a-154">會議中的使用者只能撥出至國內號碼, 而且這個使用者只能撥打外線電話給國內 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="e928a-154">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="e928a-155">身分識別 = "tag: DialoutCPCDomesticPSTNDisabled"</span><span class="sxs-lookup"><span data-stu-id="e928a-155">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="e928a-156">會議中的使用者只能撥出至國內號碼, 而這個使用者就無法撥打緊急電話號碼以外的 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="e928a-156">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="e928a-157">身分識別 = "tag: DialoutCPCDisabledPSTNDomestic"</span><span class="sxs-lookup"><span data-stu-id="e928a-157">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="e928a-158">會議中的使用者無法進行撥出, 而且這個使用者只能撥打外線電話給國內 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="e928a-158">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="e928a-159">身分識別 = "tag: DialoutCPCandPSTNDisabled"</span><span class="sxs-lookup"><span data-stu-id="e928a-159">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="e928a-160">會議中的使用者無法撥出任何電話, 而且除了緊急數位以外, 此使用者無法進行任何出站呼叫 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="e928a-160">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
