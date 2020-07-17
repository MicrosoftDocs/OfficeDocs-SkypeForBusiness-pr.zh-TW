---
title: 呼出通話限制-語音會議 & PSTN 通話
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 系統管理員可以控制使用者可以發出的音訊會議和使用者 PSTN 呼叫類型。
ms.openlocfilehash: fd7c30a7561c06dd237bb72b405c8fc5b7b68dcd
ms.sourcegitcommit: c8b5d4dd70d183f7ca480fb735a19290a3457b30
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2020
ms.locfileid: "45077668"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="e9bd1-103">音訊會議和使用者 PSTN 通話的撥出通話限制原則</span><span class="sxs-lookup"><span data-stu-id="e9bd1-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="e9bd1-104">身為系統管理員，您可以使用撥出通話控制來限制組織中的使用者可進行的音訊會議類型和終端使用者 PSTN 通話類型。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="e9bd1-105">輸出呼叫控制可以在每位使用者的基礎上套用，並提供下列兩個控制項來單獨限制每個輸出呼叫類型。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="e9bd1-106">根據預設，兩個控制項都設定為允許國際和國內呼出通話。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="e9bd1-107">控制權</span><span class="sxs-lookup"><span data-stu-id="e9bd1-107">Control</span></span>|<span data-ttu-id="e9bd1-108">描述</span><span class="sxs-lookup"><span data-stu-id="e9bd1-108">Description</span></span>|<span data-ttu-id="e9bd1-109">控制選項</span><span class="sxs-lookup"><span data-stu-id="e9bd1-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e9bd1-110">音訊會議 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="e9bd1-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="e9bd1-111">限制輸出類型</span><span class="sxs-lookup"><span data-stu-id="e9bd1-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="e9bd1-112">內部允許的通話</span><span class="sxs-lookup"><span data-stu-id="e9bd1-112">calls that are allowed from within</span></span> </br><span data-ttu-id="e9bd1-113">由使用者組織的會議。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-113">meetings organized by a user.</span></span>|<span data-ttu-id="e9bd1-114">任何目的地（預設）</span><span class="sxs-lookup"><span data-stu-id="e9bd1-114">Any destination (default)</span></span></br><span data-ttu-id="e9bd1-115">在與 organizor 相同的國家或地區</span><span class="sxs-lookup"><span data-stu-id="e9bd1-115">In the same country or region as the organizor</span></span> </br> </br><span data-ttu-id="e9bd1-116">僅限區域中的國家或地區</span><span class="sxs-lookup"><span data-stu-id="e9bd1-116">Zone A countries or regions only</span></span> </br><span data-ttu-id="e9bd1-117">不允許</span><span class="sxs-lookup"><span data-stu-id="e9bd1-117">Don't allow</span></span>|
|<span data-ttu-id="e9bd1-118">最終使用者 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="e9bd1-118">End user PSTN calls</span></span>|<span data-ttu-id="e9bd1-119">限制通話類型</span><span class="sxs-lookup"><span data-stu-id="e9bd1-119">Restricts the type of calls</span></span> </br><span data-ttu-id="e9bd1-120">使用者可以進行的工作。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-120">that can be made by a user.</span></span>|<span data-ttu-id="e9bd1-121">國際和國內（預設）</span><span class="sxs-lookup"><span data-stu-id="e9bd1-121">International and Domestic (default)</span></span></br><span data-ttu-id="e9bd1-122">家用</span><span class="sxs-lookup"><span data-stu-id="e9bd1-122">Domestic</span></span></br><span data-ttu-id="e9bd1-123">無</span><span class="sxs-lookup"><span data-stu-id="e9bd1-123">None</span></span>|

<span data-ttu-id="e9bd1-124">若要找出哪些國家/地區被視為區域 A，請參閱[區域國家/地區](https://docs.microsoft.com/microsoftteams/calling-plans-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-124">To find out which countries/regions are considered Zone A, see [Zone A countries/regions](https://docs.microsoft.com/microsoftteams/calling-plans-for-office-365).</span></span>

   > [!NOTE]
   > <span data-ttu-id="e9bd1-125">如果撥打的電話號碼位於與會議召集人設定的 Microsoft 365 或 Office 365 （在音訊會議中）或使用者（在使用者 PSTN 呼叫中），則會被視為國內通話。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-125">A call is considered domestic if the number dialed is in the same country where Microsoft 365 or Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="e9bd1-126">限制音訊會議撥出通話</span><span class="sxs-lookup"><span data-stu-id="e9bd1-126">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="e9bd1-127">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="e9bd1-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="e9bd1-128">在左側導覽中，按一下 [**使用者**]，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-128">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="e9bd1-129">按一下頁面頂端的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-129">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="e9bd1-130">按一下 [**音訊會議**] 旁的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-130">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="e9bd1-131">在 [**從會議撥出許可權**] 底下，選取您想要的撥出限制選項。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-131">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="e9bd1-132">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-132">Click **Save**.</span></span> 

<span data-ttu-id="e9bd1-133">![商務用 Skype 標誌圖示](media/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="e9bd1-133">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.    <span data-ttu-id="e9bd1-134">在**商務用 Skype 系統管理中心**的左導覽中，前往 [**音訊會議**  >  **使用者**]，然後從可用使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-134">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.    <span data-ttu-id="e9bd1-135">在 [動作] 窗格中，按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-135">In the Action pane, click **Edit**.</span></span>

3.    <span data-ttu-id="e9bd1-136">在 [**限制使用此使用者的會議進行撥**出] 底下，選取您想要的撥出限制選項。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-136">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![撥出選項的限制](/Skype/SfbOnline/images/restrictions-to-dial-outs.png)

5. <span data-ttu-id="e9bd1-138">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-138">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="e9bd1-139">**使用 PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e9bd1-139">**Using PowerShell**</span></span>

<span data-ttu-id="e9bd1-140">出站通話限制是由名為 OnlineDialOutPolicy 的單一原則所控制，每個策略都有一個限制屬性。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-140">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="e9bd1-141">原則無法自訂，而是針對每個設定組合提供預先定義的原則實例。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-141">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="e9bd1-142">您可以使用 CSOnlineDialOutPolicy Cmdlet 來查看輸出通話原則，並使用授與 CSDialOutPolicy Cmdlet 將其指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-142">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="e9bd1-143">（請注意，Grant Cmdlet 不會包含「線上」一詞，因為取得 Cmdlet 一樣。）</span><span class="sxs-lookup"><span data-stu-id="e9bd1-143">(Please note that the Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span> 

<span data-ttu-id="e9bd1-144">下表提供每個原則的概覽。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-144">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e9bd1-145">身分識別 = "tag： DialoutCPCandPSTNInternational"</span><span class="sxs-lookup"><span data-stu-id="e9bd1-145">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="e9bd1-146">會議中的使用者可以撥出到國際和國內號碼，此使用者也可以撥出電話給國際和國內電話號碼。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-146">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="e9bd1-147">身分識別 = "tag： DialoutCPCDomesticPSTNInternational"</span><span class="sxs-lookup"><span data-stu-id="e9bd1-147">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="e9bd1-148">會議中的使用者只能撥出至國內號碼，而這個使用者可以撥出電話給國際和國內號碼。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-148">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="e9bd1-149">身分識別 = "tag： DialoutCPCDisabledPSTNInternational"</span><span class="sxs-lookup"><span data-stu-id="e9bd1-149">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="e9bd1-150">會議中的使用者無法進行任何撥出。此使用者可以撥出電話給國際和國內號碼。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-150">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="e9bd1-151">身分識別 = "tag： DialoutCPCInternationalPSTNDomestic"</span><span class="sxs-lookup"><span data-stu-id="e9bd1-151">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="e9bd1-152">會議中的使用者可以撥出到國際和國內電話號碼，而且這個使用者只能撥打出站通話至國內 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-152">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="e9bd1-153">身分識別 = "tag： DialoutCPCInternationalPSTNDisabled"</span><span class="sxs-lookup"><span data-stu-id="e9bd1-153">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="e9bd1-154">會議中的使用者可以撥出到國際和國內號碼，而這個使用者就無法撥打緊急電話號碼以外的 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-154">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="e9bd1-155">身分識別 = "tag： DialoutCPCandPSTNDomestic"</span><span class="sxs-lookup"><span data-stu-id="e9bd1-155">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="e9bd1-156">會議中的使用者只能撥出至國內號碼，而且這個使用者只能撥打外線電話給國內 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-156">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="e9bd1-157">身分識別 = "tag： DialoutCPCDomesticPSTNDisabled"</span><span class="sxs-lookup"><span data-stu-id="e9bd1-157">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="e9bd1-158">會議中的使用者只能撥出至國內號碼，而這個使用者就無法撥打緊急電話號碼以外的 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-158">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="e9bd1-159">身分識別 = "tag： DialoutCPCDisabledPSTNDomestic"</span><span class="sxs-lookup"><span data-stu-id="e9bd1-159">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="e9bd1-160">會議中的使用者無法進行撥出，而且這個使用者只能撥打外線電話給國內 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-160">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="e9bd1-161">身分識別 = "tag： DialoutCPCandPSTNDisabled"</span><span class="sxs-lookup"><span data-stu-id="e9bd1-161">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="e9bd1-162">會議中的使用者無法撥出任何電話，而且除了緊急數位以外，此使用者無法進行任何出站呼叫 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-162">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="e9bd1-163">身分識別 = "tag： DialoutCPCZoneAPSTNInternational"</span><span class="sxs-lookup"><span data-stu-id="e9bd1-163">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="e9bd1-164">會議中的使用者只能撥出以對國家和地區進行分區，而且這個使用者可以撥出電話給國際和國內號碼。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-164">User in the conference can only dial out to Zone A countries and regions, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="e9bd1-165">身分識別 = "tag： DialoutCPCZoneAPSTNDomestic"</span><span class="sxs-lookup"><span data-stu-id="e9bd1-165">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="e9bd1-166">會議中的使用者只能撥出以對國家和地區進行分區，而且這個使用者只能撥打出站通話至國內 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-166">User in the conference can only dial out to Zone A countries and regions, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="e9bd1-167">身分識別 = "tag： DialoutCPCZoneAPSTNDisabled"</span><span class="sxs-lookup"><span data-stu-id="e9bd1-167">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="e9bd1-168">會議中的使用者只能撥出以對國家和地區進行分區，而這個使用者就無法撥打緊急電話號碼以外的 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="e9bd1-168">User in the conference can only dial out to Zone A countries and regions, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
