---
title: 外線通話限制 - PSTN 通話&音訊會議
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
description: 系統管理員可以控制使用者可撥打的音訊會議和使用者 PSTN 通話類型。
ms.openlocfilehash: 86622b493fbb8d31f98f600acb7158afc82e15e5
ms.sourcegitcommit: 02703e8f9a512848e158a3a4f38d84501ad5f633
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52526726"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="ad09d-103">音訊會議和使用者 PSTN 通話的撥出通話限制原則</span><span class="sxs-lookup"><span data-stu-id="ad09d-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="ad09d-104">做為系統管理員，您可以使用輸出通話控制項來限制貴組織中使用者可以撥打的音訊會議和使用者公用交換電話網路 (PSTN) 電話類型。</span><span class="sxs-lookup"><span data-stu-id="ad09d-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end-user Public Switched Telephone Network (PSTN) calls that can be made by users in your organization.</span></span>

<span data-ttu-id="ad09d-105">外發通話控制項可以依據每個使用者或租使用者來使用，並提供下列兩種控制項來獨立限制每種類型的外發通話。</span><span class="sxs-lookup"><span data-stu-id="ad09d-105">Outbound call controls can be applied on a per-user basis or on a tenant basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="ad09d-106">根據預設，這兩個控制項都設定為允許國際和國內外發通話。</span><span class="sxs-lookup"><span data-stu-id="ad09d-106">By default, both controls are set to allow international and domestic outbound calls.</span></span>

|<span data-ttu-id="ad09d-107">控制</span><span class="sxs-lookup"><span data-stu-id="ad09d-107">Control</span></span>|<span data-ttu-id="ad09d-108">描述</span><span class="sxs-lookup"><span data-stu-id="ad09d-108">Description</span></span>|<span data-ttu-id="ad09d-109">控制項選項</span><span class="sxs-lookup"><span data-stu-id="ad09d-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ad09d-110">音訊會議 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="ad09d-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="ad09d-111">限制外發類型</span><span class="sxs-lookup"><span data-stu-id="ad09d-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="ad09d-112">內允許的通話</span><span class="sxs-lookup"><span data-stu-id="ad09d-112">calls that are allowed from within</span></span> </br><span data-ttu-id="ad09d-113">使用者組織的會議。</span><span class="sxs-lookup"><span data-stu-id="ad09d-113">meetings organized by a user.</span></span>|<span data-ttu-id="ad09d-114">任何目的地 (預設) </span><span class="sxs-lookup"><span data-stu-id="ad09d-114">Any destination (default)</span></span></br><span data-ttu-id="ad09d-115">與召集人在同一個國家/地區</span><span class="sxs-lookup"><span data-stu-id="ad09d-115">In the same country or region as the organizer</span></span> </br> <span data-ttu-id="ad09d-116">[區域 A 國家/地區或區域](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="ad09d-116">[Zone A countries or regions](audio-conferencing-zones.md) only</span></span> </br><span data-ttu-id="ad09d-117">不允許</span><span class="sxs-lookup"><span data-stu-id="ad09d-117">Don't allow</span></span>|
|<span data-ttu-id="ad09d-118">使用者 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="ad09d-118">End-user PSTN calls</span></span>|<span data-ttu-id="ad09d-119">限制通話類型</span><span class="sxs-lookup"><span data-stu-id="ad09d-119">Restricts the type of calls</span></span> </br><span data-ttu-id="ad09d-120">使用者可以進行。</span><span class="sxs-lookup"><span data-stu-id="ad09d-120">that can be made by a user.</span></span>|<span data-ttu-id="ad09d-121">國際和國內 (預設) </span><span class="sxs-lookup"><span data-stu-id="ad09d-121">International and Domestic (default)</span></span></br><span data-ttu-id="ad09d-122">國內</span><span class="sxs-lookup"><span data-stu-id="ad09d-122">Domestic</span></span></br><span data-ttu-id="ad09d-123">無</span><span class="sxs-lookup"><span data-stu-id="ad09d-123">None</span></span>|

<span data-ttu-id="ad09d-124">若要瞭解哪些國家和地區被視為區域 A，請參閱音訊會議的國家和地區 [區域](audio-conferencing-zones.md)。</span><span class="sxs-lookup"><span data-stu-id="ad09d-124">To find out which countries and regions are considered Zone A, see [Country and region zones for Audio Conferencing](audio-conferencing-zones.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="ad09d-125">如果撥打的號碼位於為會議 (的召集人設定 Microsoft 365 或 Office 365) 的同一個國家/地區，或使用者 (在使用者 PSTN 通話) 的情況下，則電話會視為國內通話。</span><span class="sxs-lookup"><span data-stu-id="ad09d-125">A call is considered domestic if the number dialed is in the same country where Microsoft 365 or Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="ad09d-126">限制音訊會議輸出通話</span><span class="sxs-lookup"><span data-stu-id="ad09d-126">Restrict audio conferencing outbound calls</span></span>

<span data-ttu-id="ad09d-127">![Microsoft Teams ](media/teams-logo-30x30.png) **標誌 使用 Microsoft Teams系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="ad09d-127">![the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ad09d-128">在左側導覽中， **選取使用者**，然後從可用使用者清單中選取使用者的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="ad09d-128">In the left navigation, select **Users**, and then select the display name of the user from the list of available users.</span></span>

3. <span data-ttu-id="ad09d-129">在音訊 **會議旁邊，選取\*\*\*\*編輯**。</span><span class="sxs-lookup"><span data-stu-id="ad09d-129">Next to **Audio Conferencing**, select **Edit**.</span></span>

4. <span data-ttu-id="ad09d-130">在 **會議撥出下**，選取您想要的撥出限制選項。</span><span class="sxs-lookup"><span data-stu-id="ad09d-130">Under **Dial-out from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="ad09d-131">選取 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="ad09d-131">Select **Save**.</span></span>

<span data-ttu-id="ad09d-132">![商務用 Skype 標誌圖示](media/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="ad09d-132">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="ad09d-133">在 商務用 Skype **系統** 管理中心，在左側導覽中，前往音訊會議使用者，然後從可用  >  使用者清單中選取使用者。</span><span class="sxs-lookup"><span data-stu-id="ad09d-133">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="ad09d-134">在動作窗格中 **，選取** 編輯 。</span><span class="sxs-lookup"><span data-stu-id="ad09d-134">In the Action pane, select **Edit**.</span></span>

3.  <span data-ttu-id="ad09d-135">在 **此使用者會議** 撥出的限制下，選取您想要的撥出限制選項。</span><span class="sxs-lookup"><span data-stu-id="ad09d-135">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

      ![撥出限制選項](media/restrictions-to-dial-outs.png)

4. <span data-ttu-id="ad09d-137">選取 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="ad09d-137">Select **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="ad09d-138">**使用 PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ad09d-138">**Using PowerShell**</span></span>

<span data-ttu-id="ad09d-139">輸出通話限制是由稱為 OnlineDialOutPolicy 的單一策略控制，每個策略都有一個限制屬性。</span><span class="sxs-lookup"><span data-stu-id="ad09d-139">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy, which has a restriction attribute for each.</span></span> <span data-ttu-id="ad09d-140">無法自訂該策略，而是每個設定組合都有預先定義的策略實例。</span><span class="sxs-lookup"><span data-stu-id="ad09d-140">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span>

<span data-ttu-id="ad09d-141">您可以使用 Get-CSOnlineDialOutPolicy Cmdlet 來查看外寄通話政策，並使用下列命令進行設定。</span><span class="sxs-lookup"><span data-stu-id="ad09d-141">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and use the following command for the setup.</span></span>

<span data-ttu-id="ad09d-142">**使用下列 Cmdlet** 將策略設定為每個使用者層級。</span><span class="sxs-lookup"><span data-stu-id="ad09d-142">**Set the policy on a per-user level with the following cmdlet**.</span></span> <span data-ttu-id="ad09d-143"> (Grant Cmdlet 不包含 「線上」一詞，就像 Get Cmdlet 一樣。) </span><span class="sxs-lookup"><span data-stu-id="ad09d-143">(The Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span>

```
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

<span data-ttu-id="ad09d-144">**使用下列 Cmdlet 在租使用者層級設定策略**。</span><span class="sxs-lookup"><span data-stu-id="ad09d-144">**Set the policy on the tenant level with the following cmdlet**.</span></span>

```
Grant-CsDialoutPolicy  -Tenant <guid> -PolicyName <policy name>  -Global 
```

<span data-ttu-id="ad09d-145">未指派任何撥出策略的租使用者所有使用者都會取得此策略。</span><span class="sxs-lookup"><span data-stu-id="ad09d-145">All users of the tenant who don't have any dialout policy assigned will get this policy.</span></span> <span data-ttu-id="ad09d-146">其他使用者會維持目前的政策。</span><span class="sxs-lookup"><span data-stu-id="ad09d-146">Other users remain with their current policy.</span></span>

<span data-ttu-id="ad09d-147">下表提供每個策略的概覽。</span><span class="sxs-lookup"><span data-stu-id="ad09d-147">The following table provides an overview of each policy.</span></span>

|<span data-ttu-id="ad09d-148">PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="ad09d-148">PowerShell cmdlet</span></span>|<span data-ttu-id="ad09d-149">描述</span><span class="sxs-lookup"><span data-stu-id="ad09d-149">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="ad09d-150">Identity='tag：DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="ad09d-150">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="ad09d-151">會議中的使用者可以撥出國際和國內號碼，而且這個使用者也可以撥打國際和國內號碼。</span><span class="sxs-lookup"><span data-stu-id="ad09d-151">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="ad09d-152">Identity='tag：DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="ad09d-152">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="ad09d-153">會議中的使用者只能撥出國內號碼，而此使用者可以撥打國際和國內號碼。</span><span class="sxs-lookup"><span data-stu-id="ad09d-153">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="ad09d-154">Identity='tag：DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="ad09d-154">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="ad09d-155">會議中的使用者無法撥出。此使用者可以撥打國際和國內號碼。</span><span class="sxs-lookup"><span data-stu-id="ad09d-155">User in the conference can't dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="ad09d-156">Identity='tag：DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="ad09d-156">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="ad09d-157">會議中的使用者可以撥出國際和國內號碼，而且此使用者只能撥打國內 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="ad09d-157">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="ad09d-158">Identity='tag：DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="ad09d-158">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="ad09d-159">會議中的使用者可以撥出國際和國內號碼，而且除了緊急號碼之外，此使用者無法撥打任何外撥 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="ad09d-159">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="ad09d-160">Identity='tag：DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="ad09d-160">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="ad09d-161">會議中的使用者只能撥出國內號碼，而且此使用者只能撥打國內 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="ad09d-161">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="ad09d-162">Identity='tag：DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="ad09d-162">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="ad09d-163">會議中的使用者只能撥出到國內號碼，而且除了緊急號碼之外，此使用者無法撥打任何撥出的 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="ad09d-163">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="ad09d-164">Identity='tag：DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="ad09d-164">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="ad09d-165">會議中的使用者無法撥出，而且此使用者只能撥打國內 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="ad09d-165">User in the conference can't dial out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="ad09d-166">Identity='tag：DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="ad09d-166">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="ad09d-167">會議中的使用者無法撥出，而且除了緊急號碼之外，此使用者無法撥打任何外撥 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="ad09d-167">User in the conference can't dial out, and this user can't make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="ad09d-168">Identity='tag：DialoutCPCZoneAPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="ad09d-168">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="ad09d-169">會議中的使用者只能撥出到 [區域 A](audio-conferencing-zones.md)國家/地區，而且此使用者可以撥打國際和國內號碼。</span><span class="sxs-lookup"><span data-stu-id="ad09d-169">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="ad09d-170">Identity='tag：DialoutCPCZoneAPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="ad09d-170">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="ad09d-171">會議中的使用者只能撥出到 [區域 A](audio-conferencing-zones.md)國家/地區，而且此使用者只能撥打國內 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="ad09d-171">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="ad09d-172">Identity='tag：DialoutCPCZoneAPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="ad09d-172">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="ad09d-173">會議中的使用者只能撥出到 [區域 A](audio-conferencing-zones.md)國家/地區，而且除了緊急號碼之外，此使用者無法撥打任何 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="ad09d-173">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can't make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
