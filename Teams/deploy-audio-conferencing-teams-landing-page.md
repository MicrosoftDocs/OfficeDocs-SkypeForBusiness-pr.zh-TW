---
title: 設定音訊會議設定 - Microsoft Teams
ms.reviewer: ''
description: 使用這些部署資源幫助您在 Microsoft Teams中，將音訊會議做為會議工作負載的一部分推出。
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: admin
ms.date: 01/28/2019
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
ms.custom: seo-marvel-mar2020
f1.keywords:
- NOCSH
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: c706fdde4f9634cc67b334cf19d0e9d3325f6ec8
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776578"
---
# <a name="learn-how-to-deploy-audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="adc32-103">了解如何在 Microsoft Teams 中部署音訊會議</span><span class="sxs-lookup"><span data-stu-id="adc32-103">Learn how to deploy audio conferencing in Microsoft Teams</span></span>

<span data-ttu-id="adc32-104">音訊會議是由一般電話加入 Teams 會議，並由會議撥出電話號碼的功能。</span><span class="sxs-lookup"><span data-stu-id="adc32-104">Audio Conferencing is the ability to join a Teams meeting from a regular phone and dial out from a meeting to a phone number.</span></span> <span data-ttu-id="adc32-105">請確認您已在組織中檢閱[會議推出](deploy-meetings-microsoft-teams-landing-page.md)做為推出音訊會議的一部分。</span><span class="sxs-lookup"><span data-stu-id="adc32-105">Be sure you've reviewed [Meetings rollout](deploy-meetings-microsoft-teams-landing-page.md) as part of rolling out Audio Conferencing in your organization.</span></span>

## <a name="audio-conferencing-deployment-decisions"></a><span data-ttu-id="adc32-106">音訊會議部署決策</span><span class="sxs-lookup"><span data-stu-id="adc32-106">Audio Conferencing deployment decisions</span></span>

<span data-ttu-id="adc32-107">本文可協助您決定是否要根據組織的設定檔和商務需求來變更任何預設音訊會議設定，並逐步引導您完成每個變更。</span><span class="sxs-lookup"><span data-stu-id="adc32-107">This article helps you decide whether to change any of the default Audio Conferencing settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="adc32-108">我們已將設定分割成兩個群組，從[您最可能進行的變更](#core-deployment-decisions)的核心集開始。</span><span class="sxs-lookup"><span data-stu-id="adc32-108">We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="adc32-109">根據組織的需求，第二個群組包括您可能想要設定的[其他設定](#additional-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="adc32-109">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="adc32-110">您只需要為打算排程或主持會議的人員設定音訊會議即可。</span><span class="sxs-lookup"><span data-stu-id="adc32-110">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="adc32-111">撥入的會議出席者不需獲得任何指派的授權或進行任何其他設定。</span><span class="sxs-lookup"><span data-stu-id="adc32-111">Meeting attendees who dial in don't need any licenses assigned to them or any other setup.</span></span> <span data-ttu-id="adc32-112">撥入 (撥號) 會議對於不在現場且無法在其筆記本電腦或行動裝置上使用商務用 Skype 或 Teams 應用程式的使用者而言，是很實用的功能。</span><span class="sxs-lookup"><span data-stu-id="adc32-112">Dialing in (calling in) to meetings is very useful for users who are on the road and can't attend a meeting using the Skype for Business or Teams app on their laptops or mobile devices.</span></span> 


## <a name="audio-conferencing-prerequisites"></a><span data-ttu-id="adc32-113">音訊會議的必要條件</span><span class="sxs-lookup"><span data-stu-id="adc32-113">Audio Conferencing prerequisites</span></span> 

<span data-ttu-id="adc32-114">您必須先考量下列問題，才可推出 Teams 的音訊會議：</span><span class="sxs-lookup"><span data-stu-id="adc32-114">Before you can roll out Audio Conferencing for Teams, consider the following:</span></span>

|<span data-ttu-id="adc32-115">問問自己</span><span class="sxs-lookup"><span data-stu-id="adc32-115">Ask yourself</span></span>|<span data-ttu-id="adc32-116">動作</span><span class="sxs-lookup"><span data-stu-id="adc32-116">Action</span></span> |
|------------|-------|
|<span data-ttu-id="adc32-117">我所在的國家/地區是否可使用音訊會議？</span><span class="sxs-lookup"><span data-stu-id="adc32-117">Is Audio Conferencing available for my country/region?</span></span>|<span data-ttu-id="adc32-118">若要了解您的國家/地區是否可使用音訊會議，請參閱[音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="adc32-118">To find out if Audio Conferencing is available for your country/region, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>|
|<span data-ttu-id="adc32-119">我的使用者是否具有 Teams 音訊會議的適當授權？</span><span class="sxs-lookup"><span data-stu-id="adc32-119">Do my users have the proper licensing for Teams Audio Conferencing?</span></span>|<span data-ttu-id="adc32-120">音訊會議授權可隨 Office 365 E5 訂閱取得，或是從 Microsoft 365 商務標準版、E1 或 E3 訂閱的附加服務取得。</span><span class="sxs-lookup"><span data-stu-id="adc32-120">Audio Conferencing licenses are available as part of an Office 365 E5 subscription or as an add-on service for an Microsoft 365 Business Standard, E1 or E3 subscription.</span></span> <ul><li><span data-ttu-id="adc32-121">若要取得並指派授權，請參閱[試用或購買 Office 365 中的音訊會議](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)和[指派或移除商務用 Office 365 的授權](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="adc32-121">To get and assign licenses, see [Try or purchase Audio Conferencing in Office 365](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365) and [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span></li><li> <span data-ttu-id="adc32-122">若要深入了解，請參閱 [Microsoft Teams 附加元件授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="adc32-122">To learn more, read [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span> </li><li><span data-ttu-id="adc32-123">若要查看每個包含在 Office 365 方案中的雲端功能，請參閱[根據您方案的授權選項](teams-add-on-licensing/office-365-business-premium.md)文章。</span><span class="sxs-lookup"><span data-stu-id="adc32-123">To see what cloud features are included in each Office 365 plan, see the [License options based on your plan](teams-add-on-licensing/office-365-business-premium.md) articles.</span></span></li></ul>|
|<span data-ttu-id="adc32-124">對於獲得音訊會議授權的使用者，我是否需要為他們購買通訊點數？</span><span class="sxs-lookup"><span data-stu-id="adc32-124">Do I need to purchase Communications Credits for the users who are assigned Audio Conferencing licenses?</span></span>|<span data-ttu-id="adc32-125">若要深入了解，請參閱[什麼是通訊點數](what-are-communications-credits.md)，然後查看下方的[通訊點數](#communications-credits) 一節。</span><span class="sxs-lookup"><span data-stu-id="adc32-125">To learn more, read [What are Communications Credits](what-are-communications-credits.md), then check out the [Communications Credits](#communications-credits) section below.</span></span>|
|||


## <a name="core-deployment-decisions"></a><span data-ttu-id="adc32-126">核心部署決策</span><span class="sxs-lookup"><span data-stu-id="adc32-126">Core deployment decisions</span></span>

<span data-ttu-id="adc32-127">符合音訊會議先決條件之後，請完成下列工作以為您的使用者設定音訊會議。</span><span class="sxs-lookup"><span data-stu-id="adc32-127">After you meet the Audio Conferencing prerequisites, complete the following tasks to configure Audio Conferencing for your users.</span></span>


### <a name="teams-administrators"></a><span data-ttu-id="adc32-128">Teams 系統管理員</span><span class="sxs-lookup"><span data-stu-id="adc32-128">Teams administrators</span></span>

<span data-ttu-id="adc32-129">Teams 提供了一組自訂管理員角色，可用來為組織管理 Teams。</span><span class="sxs-lookup"><span data-stu-id="adc32-129">Teams provides a set of custom administrator roles that can be used to manage Teams for your organization.</span></span> <span data-ttu-id="adc32-130">這些角色為系統管理員提供各種能力。</span><span class="sxs-lookup"><span data-stu-id="adc32-130">The roles provide various capabilities to administrators.</span></span> 

| <span data-ttu-id="adc32-131">問問自己</span><span class="sxs-lookup"><span data-stu-id="adc32-131">Ask yourself</span></span> | <span data-ttu-id="adc32-132">動作</span><span class="sxs-lookup"><span data-stu-id="adc32-132">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="adc32-133">誰將獲指派 Teams 通訊系統管理員角色？</span><span class="sxs-lookup"><span data-stu-id="adc32-133">Who will be assigned the Teams Communications Administrator role?</span></span>|<span data-ttu-id="adc32-134">若要深入了解 Teams 系統管理員角色，請參閱[使用 Microsoft Teams 系統管理員角色管理來管理 Teams](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="adc32-134">To learn more about Teams administrator roles see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>|
|<span data-ttu-id="adc32-135">誰將獲指派 Teams 通訊支援工程師角色？</span><span class="sxs-lookup"><span data-stu-id="adc32-135">Who will be assigned the Teams Communications Support Engineer role?</span></span>|<span data-ttu-id="adc32-136">若要指派系統管理員角色，[使用 Azure Active Directory 將系統管理員和非系統管理員角色指派給使用者](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="adc32-136">To assign admin roles, see [Assign administrator and non-administrator roles to users with Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>|
|<span data-ttu-id="adc32-137">誰將獲指派 Teams 通訊支援專員角色？</span><span class="sxs-lookup"><span data-stu-id="adc32-137">Who will be assigned the Teams Communications Support Specialist role?</span></span>||
|||

### <a name="conferencing-bridges-and-phone-numbers"></a><span data-ttu-id="adc32-138">會議橋接器和電話號碼</span><span class="sxs-lookup"><span data-stu-id="adc32-138">Conferencing bridges and phone numbers</span></span>

<span data-ttu-id="adc32-139">會議橋接器可讓與會者使用電話撥入會議。</span><span class="sxs-lookup"><span data-stu-id="adc32-139">Conferencing bridges let people dial into meetings using a phone.</span></span> <span data-ttu-id="adc32-140">您可以使用會議橋接器的預設設定，或變更電話號碼 (付費和免付費) 以及其他設定，例如 PIN 或使用的語言。</span><span class="sxs-lookup"><span data-stu-id="adc32-140">You can use the default settings for a conferencing bridge or change the phone numbers (toll and toll-free) and other settings, such as the PIN or the languages that are used.</span></span>

<span data-ttu-id="adc32-141">如需詳細資訊，請參閱[Office 365 的音訊會議](audio-conferencing-in-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="adc32-141">See [Audio Conferencing in Office 365](audio-conferencing-in-office-365.md) to learn more.</span></span>

|<span data-ttu-id="adc32-142">問問自己</span><span class="sxs-lookup"><span data-stu-id="adc32-142">Ask yourself</span></span>|<span data-ttu-id="adc32-143">動作</span><span class="sxs-lookup"><span data-stu-id="adc32-143">Action</span></span> |
|------------|-------|
|<span data-ttu-id="adc32-144">是否需要新增新的會議橋接器號碼？</span><span class="sxs-lookup"><span data-stu-id="adc32-144">Do I need to add new conferencing bridge numbers?</span></span>| <span data-ttu-id="adc32-145">若要新增新號碼，請參閱[取得服務電話號碼](/microsoftteams/getting-service-phone-numbers)。</span><span class="sxs-lookup"><span data-stu-id="adc32-145">To add new numbers, see [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>|
|<span data-ttu-id="adc32-146">需要修改橋接器設定嗎？</span><span class="sxs-lookup"><span data-stu-id="adc32-146">Will I need to modify the bridge settings?</span></span>|<span data-ttu-id="adc32-147">若要修改橋接器設定，請參閱[變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="adc32-147">To modify the bridge settings, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>|
|<span data-ttu-id="adc32-148">需要連接埠號碼搭配音訊會議使用嗎？</span><span class="sxs-lookup"><span data-stu-id="adc32-148">Do I need to port numbers to use with audio conferencing?</span></span>|<span data-ttu-id="adc32-149">如需連接埠號碼的詳細資訊，請參閱[將電話號碼移轉至 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="adc32-149">To learn about porting phone numbers, read [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>|
|||


### <a name="default-and-alternate-languages"></a><span data-ttu-id="adc32-150">預設和替代語言</span><span class="sxs-lookup"><span data-stu-id="adc32-150">Default and alternate languages</span></span>

<span data-ttu-id="adc32-151">Teams 音訊會議可讓您設定會議橋接器的預設和替代語言。</span><span class="sxs-lookup"><span data-stu-id="adc32-151">Teams Audio Conferencing lets you set up default and alternate languages for a conferencing bridge.</span></span>

|<span data-ttu-id="adc32-152">問問自己</span><span class="sxs-lookup"><span data-stu-id="adc32-152">Ask yourself</span></span>|<span data-ttu-id="adc32-153">動作</span><span class="sxs-lookup"><span data-stu-id="adc32-153">Action</span></span> |
|------------|-------|
| <span data-ttu-id="adc32-154">自動語音應答問候語應選擇哪些語言？</span><span class="sxs-lookup"><span data-stu-id="adc32-154">Which languages should I choose for auto attendant greetings?</span></span> | <span data-ttu-id="adc32-155">若要選擇語言，請參閱[設定音訊會議的自動語音應答語言](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)。</span><span class="sxs-lookup"><span data-stu-id="adc32-155">To choose languages, see [Set auto attendant languages for Audio Conferencing](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span>|
|||

### <a name="conferencing-bridge-settings"></a><span data-ttu-id="adc32-156">會議橋接器設定</span><span class="sxs-lookup"><span data-stu-id="adc32-156">Conferencing bridge settings</span></span> 

<span data-ttu-id="adc32-157">設定會議橋接 (包括預設和替代語言) 後，您應確認預設設定 (例如，進入/退出通知和 PIN 長度) 就是您要使用的設定。</span><span class="sxs-lookup"><span data-stu-id="adc32-157">After setting up your conferencing bridge, including default and alternate languages, you should verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use.</span></span> <span data-ttu-id="adc32-158">如果不是，您可加以變更。</span><span class="sxs-lookup"><span data-stu-id="adc32-158">If they're not, you can change them.</span></span> 

|<span data-ttu-id="adc32-159">問問自己</span><span class="sxs-lookup"><span data-stu-id="adc32-159">Ask yourself</span></span>|<span data-ttu-id="adc32-160">動作</span><span class="sxs-lookup"><span data-stu-id="adc32-160">Action</span></span> |
|------------|-------|
| <span data-ttu-id="adc32-161">使用者加入或離開會議時，出席者是否會聽到通知？</span><span class="sxs-lookup"><span data-stu-id="adc32-161">Will attendees hear a notification when a user joins or exits a meeting?</span></span> | <span data-ttu-id="adc32-162">若要變更這些設定，請參閱[變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)。</span><span class="sxs-lookup"><span data-stu-id="adc32-162">To change these settings, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>|
|<span data-ttu-id="adc32-163">會議召集人用來開始會議的 PIN 所需長度為何？</span><span class="sxs-lookup"><span data-stu-id="adc32-163">What is the required length of the PIN that a meeting organizer uses to start the meeting?</span></span>||
|||

### <a name="dial-in-phone-number-settings-for-users-who-lead-meetings"></a><span data-ttu-id="adc32-164">會議主持使用者的撥入電話號碼設定</span><span class="sxs-lookup"><span data-stu-id="adc32-164">Dial-in phone number settings for users who lead meetings</span></span>

<span data-ttu-id="adc32-165">在建立音訊會議橋接器之後，您必須設定主持會議的使用者所將使用的付費和/或免付費電話號碼。</span><span class="sxs-lookup"><span data-stu-id="adc32-165">After you create your Audio Conferencing bridge, you need to set the toll and/or toll-free numbers that users who lead meetings will use.</span></span>

|<span data-ttu-id="adc32-166">問問自己</span><span class="sxs-lookup"><span data-stu-id="adc32-166">Ask yourself</span></span>|<span data-ttu-id="adc32-167">動作</span><span class="sxs-lookup"><span data-stu-id="adc32-167">Action</span></span> |
|------------|-------|
| <span data-ttu-id="adc32-168">要指派給每位主持會議使用者之會議橋接器電話號碼為何？</span><span class="sxs-lookup"><span data-stu-id="adc32-168">Which conference bridge numbers will I assign to each user who leads meetings?</span></span> | <span data-ttu-id="adc32-169">若要為使用者指派撥入電話號碼，請參閱[步驟7：為主持會議使用者指派撥入電話號碼](set-up-audio-conferencing-in-teams.md#step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings)。</span><span class="sxs-lookup"><span data-stu-id="adc32-169">To assign a dial-in phone number to a user, see [Step 7: Assign dial-in phone numbers for users who lead meetings](set-up-audio-conferencing-in-teams.md#step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings).</span></span> |
|||

### <a name="communications-credits"></a><span data-ttu-id="adc32-170">通訊點數</span><span class="sxs-lookup"><span data-stu-id="adc32-170">Communications Credits</span></span>

<span data-ttu-id="adc32-171">若要提供免付費會議橋接器電話號碼，以及支援電話會議撥出的國際電話號碼，您必須為組織設定通訊點數。</span><span class="sxs-lookup"><span data-stu-id="adc32-171">To provide toll-free conference bridge phone numbers and to support conferencing dial-out to international phone numbers, you must set up Communications Credits for your organization.</span></span> <span data-ttu-id="adc32-172">若要深入了解通訊點數，請參閱[什麼是通訊點數？](what-are-communications-credits.md)。</span><span class="sxs-lookup"><span data-stu-id="adc32-172">To learn more about Communications Credits, see [What are Communications Credits?](what-are-communications-credits.md).</span></span>

|<span data-ttu-id="adc32-173">問問自己</span><span class="sxs-lookup"><span data-stu-id="adc32-173">Ask yourself</span></span>|<span data-ttu-id="adc32-174">動作</span><span class="sxs-lookup"><span data-stu-id="adc32-174">Action</span></span> |
|------------|-------|
|<span data-ttu-id="adc32-175">我的語音會議實作是否需要通訊點數？</span><span class="sxs-lookup"><span data-stu-id="adc32-175">Are Communications Credits required for my Audio Conferencing implementation?</span></span> |<span data-ttu-id="adc32-176">若要了解您是否需要設定通訊點數，請參閱[設定貴組織的通訊點數](set-up-communications-credits-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="adc32-176">To find out if you need to set up Communications Credits, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>|
|<span data-ttu-id="adc32-177">如果通訊點數為必須，應該花費多少購買？</span><span class="sxs-lookup"><span data-stu-id="adc32-177">If they're required, how much should I purchase?</span></span>|<span data-ttu-id="adc32-178">若要決定通訊點數金額，請參閱[建議的資金金額](what-are-communications-credits.md#recommended-funding-amounts)。</span><span class="sxs-lookup"><span data-stu-id="adc32-178">To determine the Communications Credits amount, see [Recommended funding amounts](what-are-communications-credits.md#recommended-funding-amounts).</span></span>|
|<span data-ttu-id="adc32-179">需要設定自動儲值金額嗎？</span><span class="sxs-lookup"><span data-stu-id="adc32-179">Do I want to configure an auto-recharge amount?</span></span>|<span data-ttu-id="adc32-180">若要設定自動儲值金額，請參閱[設定貴組織的通訊點數](set-up-communications-credits-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="adc32-180">To configure an auto-recharge amount, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>|
|||



## <a name="additional-deployment-decisions"></a><span data-ttu-id="adc32-181">其他部署決策</span><span class="sxs-lookup"><span data-stu-id="adc32-181">Additional deployment decisions</span></span>

<span data-ttu-id="adc32-182">根據組織的需求和組態而定，您可能會想要變更這些設定。</span><span class="sxs-lookup"><span data-stu-id="adc32-182">You may want to change these settings, based on your organization's needs and configuration.</span></span>

### <a name="outbound-calling-restriction-policies"></a><span data-ttu-id="adc32-183">撥出通話限制原則</span><span class="sxs-lookup"><span data-stu-id="adc32-183">Outbound calling restriction policies</span></span> 

<span data-ttu-id="adc32-184">身為系統管理員，您可以使用撥出通話控制來限制組織中的使用者可進行的音訊會議類型和終端使用者 PSTN 通話類型。</span><span class="sxs-lookup"><span data-stu-id="adc32-184">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span>

|<span data-ttu-id="adc32-185">問問自己</span><span class="sxs-lookup"><span data-stu-id="adc32-185">Ask yourself</span></span>|<span data-ttu-id="adc32-186">動作</span><span class="sxs-lookup"><span data-stu-id="adc32-186">Action</span></span> |
|------------|-------|
| <span data-ttu-id="adc32-187">要限制允許的撥出通話類型嗎？</span><span class="sxs-lookup"><span data-stu-id="adc32-187">Will I limit the type of outbound calls that are allowed?</span></span> | <span data-ttu-id="adc32-188">若要限制撥出通話，請參閱[音訊會議和使用者 PSTN 通話的撥出通話限制原則](outbound-calling-restriction-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="adc32-188">To restrict outbound calls, see [Outbound calling restriction policies for Audio Conferencing and user PSTN calls](outbound-calling-restriction-policies.md).</span></span>|
|||


### <a name="dial-plans"></a><span data-ttu-id="adc32-189">撥號對應表</span><span class="sxs-lookup"><span data-stu-id="adc32-189">Dial plans</span></span>

<span data-ttu-id="adc32-190">撥號對應表包含在 Office 365 的電話系統中，是可將撥打的電話號碼轉換為替代格式 (通常是 E.164 格式)，以進行通話授權和通話路由的正規化規則集合。</span><span class="sxs-lookup"><span data-stu-id="adc32-190">A dial plan, as part of Phone System in Office 365, is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="adc32-191">如需撥號對應表的相關資訊，請參閱[什麼是撥號對應表？](what-are-dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="adc32-191">For more information about dial plans, see [What are dial plans?](what-are-dial-plans.md)</span></span>

|<span data-ttu-id="adc32-192">問問自己</span><span class="sxs-lookup"><span data-stu-id="adc32-192">Ask yourself</span></span>|<span data-ttu-id="adc32-193">動作</span><span class="sxs-lookup"><span data-stu-id="adc32-193">Action</span></span> |
|------------|-------|
|<span data-ttu-id="adc32-194">我的組織需要自訂的撥號對應表？</span><span class="sxs-lookup"><span data-stu-id="adc32-194">Does my organization need a customized dial plan?</span></span>|<span data-ttu-id="adc32-195">若要幫助決定是否需要自訂的撥號對應表，請參閱[規劃租用戶撥號對應表](what-are-dial-plans.md#planning-for-tenant-dial-plans)。</span><span class="sxs-lookup"><span data-stu-id="adc32-195">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans).</span></span> |
|<span data-ttu-id="adc32-196">哪些使用者需要自訂的撥號對應表，以及應指派給每個使用者何種租用戶撥號對應表？</span><span class="sxs-lookup"><span data-stu-id="adc32-196">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span>|<span data-ttu-id="adc32-197">若要使用 PowerShell 將使用者新增至自訂撥號對應表，請參閱 [建立及管理撥號對應表](create-and-manage-dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="adc32-197">To add users to a customized dial plan using PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>|
|||

### <a name="troubleshoot-meeting-and-call-quality"></a><span data-ttu-id="adc32-198">對會議和通話品質進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="adc32-198">Troubleshoot meeting and call quality</span></span> 

<span data-ttu-id="adc32-199">Teams 有兩種方式可供您監視和疑難排解通話品質問題：[通話分析和通話品質儀表板](difference-between-call-analytics-and-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="adc32-199">Teams gives you two ways to monitor and troubleshoot call quality problems: [Call Analytics and Call Quality Dashboard](difference-between-call-analytics-and-call-quality-dashboard.md).</span></span> <span data-ttu-id="adc32-200">通話分析能顯示每位使用者在特定通話和會議的裝置、網路和連線詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="adc32-200">Call Analytics shows detailed information about the devices, networks, and connectivity related to the specific calls and meetings for each user.</span></span> <span data-ttu-id="adc32-201">通話分析的設計目的在於協助系統管理員和支援人員疑難排解特定通話的通話品質問題，而通話品質儀表板的設計目的則是在協助系統管理員和網路工程師最佳化網路。</span><span class="sxs-lookup"><span data-stu-id="adc32-201">Call Analytics is designed to help admins and helpdesk agents troubleshoot call quality problems with specific calls, whereas the Call Quality Dashboard is designed to help admins and network engineers optimize a network.</span></span> <span data-ttu-id="adc32-202">通話品質儀表板的重點不在特定使用者身上，而是會查看整個 Teams 組織的匯彙資訊。</span><span class="sxs-lookup"><span data-stu-id="adc32-202">Call Quality Dashboard shifts focus from specific users and instead looks at aggregate information for an entire Teams organization.</span></span> 

|<span data-ttu-id="adc32-203">問問自己</span><span class="sxs-lookup"><span data-stu-id="adc32-203">Ask yourself</span></span>|<span data-ttu-id="adc32-204">動作</span><span class="sxs-lookup"><span data-stu-id="adc32-204">Action</span></span> |
|------------|-------|
| <span data-ttu-id="adc32-205">誰會負責監視及疑難排解通話品質問題？</span><span class="sxs-lookup"><span data-stu-id="adc32-205">Who will be responsible for monitoring and troubleshooting call quality issues?</span></span> | <span data-ttu-id="adc32-206">如需疑難排解通話品質問題所需權限等級的相關資訊，請參閱[使用通話分析來疑難排解低劣的通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="adc32-206">See [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md) for information about permission levels required to troubleshoot call quality issues.</span></span>|
|||


## <a name="next-steps"></a><span data-ttu-id="adc32-207">後續步驟</span><span class="sxs-lookup"><span data-stu-id="adc32-207">Next steps</span></span>
- <span data-ttu-id="adc32-208">組織中音訊會議的[驅動採用率](adopt-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="adc32-208">[Drive adoption](adopt-microsoft-teams-landing-page.md) of audio conferencing in your organization.</span></span>
- [<span data-ttu-id="adc32-209">推出雲端語音</span><span class="sxs-lookup"><span data-stu-id="adc32-209">Roll out cloud voice</span></span>](cloud-voice-landing-page.md)
- <span data-ttu-id="adc32-210">在您的 Teams 初始推出中包含精選應用程式，例如 Planner。</span><span class="sxs-lookup"><span data-stu-id="adc32-210">Include featured apps - such as Planner - in your initial Teams rollout.</span></span> <span data-ttu-id="adc32-211">在開始推動 Teams 的採用時，則新增其他[應用程式、Bot 和連接器](deploy-apps-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="adc32-211">Add other [apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md) as you drive Teams adoption.</span></span>
