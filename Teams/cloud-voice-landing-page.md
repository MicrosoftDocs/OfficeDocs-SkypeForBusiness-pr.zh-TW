---
title: Microsoft 團隊中的雲端語音
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
ms.reviewer: crowe
f1keywords:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
search.appverid: MET150
description: 在小組中部署雲端語音的登陸頁面
appliesto:
- Microsoft Teams
ms.openlocfilehash: 969d55f41226d1c6effaf4c183992f15bf48e385
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925574"
---
# <a name="cloud-voice-in-microsoft-teams"></a><span data-ttu-id="9611c-103">Microsoft 團隊中的雲端語音</span><span class="sxs-lookup"><span data-stu-id="9611c-103">Cloud voice in Microsoft Teams</span></span>

<span data-ttu-id="9611c-104">您已完成[快速入門](get-started-with-teams-quick-start.md)。</span><span class="sxs-lookup"><span data-stu-id="9611c-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="9611c-105">您已在整個組織中利用[聊天、團隊、頻道、& 應用程式](deploy-chat-teams-channels-microsoft-teams-landing-page.md)來推出小組。</span><span class="sxs-lookup"><span data-stu-id="9611c-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="9611c-106">也許您已將[會議 & 會議](deploy-meetings-microsoft-teams-landing-page.md)已部署。</span><span class="sxs-lookup"><span data-stu-id="9611c-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="9611c-107">現在您已經準備好為使用者新增雲端語音功能。</span><span class="sxs-lookup"><span data-stu-id="9611c-107">Now you're ready to add cloud voice capabilities for your users.</span></span> 

<span data-ttu-id="9611c-108">雲端語音提供私人分支 Exchange （PBX）功能，以及連線至公用交換電話網絡（PSTN）的選項。</span><span class="sxs-lookup"><span data-stu-id="9611c-108">Cloud voice provides Private Branch Exchange (PBX) capabilities, and options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="9611c-109">本文可協助您決定是否需要根據貴組織的設定檔和業務需求變更任何預設雲端語音設定，然後逐步引導您完成每項變更。</span><span class="sxs-lookup"><span data-stu-id="9611c-109">This article helps you decide whether you need to change any of the default cloud voice settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="9611c-110">我們已將這些設定分割成兩個群組，從[您更容易進行](#core-deployment-decisions)的核心變更集合開始。</span><span class="sxs-lookup"><span data-stu-id="9611c-110">We've split the settings into two groups, starting with the core set of [changes you are more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="9611c-111">根據組織的需求，第二個群組包括您可能想要設定的[其他設定](#additional-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="9611c-111">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="9611c-112">我們建議所有組織都在核心決策中運作，然後，如果您的組織有其他需求，請參閱下列資料。</span><span class="sxs-lookup"><span data-stu-id="9611c-112">We recommend that all organizations work through the core decisions and then, if your organization has additional requirements, review the following material.</span></span>



## <a name="learn-more-about-cloud-voice"></a><span data-ttu-id="9611c-113">深入瞭解雲端語音</span><span class="sxs-lookup"><span data-stu-id="9611c-113">Learn more about cloud voice</span></span>

<span data-ttu-id="9611c-114">下列文章提供在小組中部署和使用雲端語音功能的詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="9611c-114">The following articles provide more information about deploying and using cloud voice features in Teams:</span></span>

- [<span data-ttu-id="9611c-115">Office 365 中的電話系統</span><span class="sxs-lookup"><span data-stu-id="9611c-115">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="9611c-116">含有通話方案的電話系統</span><span class="sxs-lookup"><span data-stu-id="9611c-116">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="9611c-117">電話系統直接路由</span><span class="sxs-lookup"><span data-stu-id="9611c-117">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="9611c-118">雲端語音部署</span><span class="sxs-lookup"><span data-stu-id="9611c-118">Cloud voice deployment</span></span>](cloud-voice-deployment.md)
- [<span data-ttu-id="9611c-119">Microsoft 電話解決方案</span><span class="sxs-lookup"><span data-stu-id="9611c-119">Microsoft telephony solutions</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)
- <span data-ttu-id="9611c-120">請觀看下列會話，深入瞭解手機系統： [Microsoft 團隊中的電話系統簡介](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="9611c-120">Watch the following session to learn more about Phone System: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>


## <a name="core-deployment-decisions"></a><span data-ttu-id="9611c-121">核心部署決策</span><span class="sxs-lookup"><span data-stu-id="9611c-121">Core deployment decisions</span></span>

<span data-ttu-id="9611c-122">這些是大多陣列織想要變更的設定（如果小組預設設定不適用於組織）。</span><span class="sxs-lookup"><span data-stu-id="9611c-122">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

## <a name="phone-system-office-365"></a><span data-ttu-id="9611c-123">電話系統（Office 365）</span><span class="sxs-lookup"><span data-stu-id="9611c-123">Phone System (Office 365)</span></span>

<span data-ttu-id="9611c-124">[電話系統] 是 Microsoft 的技術，可在 Office 365 雲端啟用呼叫控制和私人分支 Exchange （PBX）功能。</span><span class="sxs-lookup"><span data-stu-id="9611c-124">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Office 365 cloud.</span></span> <span data-ttu-id="9611c-125">[電話系統] 可讓您將現有的私人分支 Exchange （PBX）系統取代為直接從 Office 365 提供的一組功能，並緊密整合至公司的雲端生產力體驗。</span><span class="sxs-lookup"><span data-stu-id="9611c-125">Phone System allows you to replace your existing Private Branch Exchange (PBX) system with a set of features directly delivered from Office 365 and tightly integrated into the company’s cloud productivity experience.</span></span>


|<span data-ttu-id="9611c-126">問問自己</span><span class="sxs-lookup"><span data-stu-id="9611c-126">Ask yourself</span></span>|<span data-ttu-id="9611c-127">動作</span><span class="sxs-lookup"><span data-stu-id="9611c-127">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="9611c-128">我要在哪個使用者位置或辦公室實現電話系統？</span><span class="sxs-lookup"><span data-stu-id="9611c-128">In which user locations or offices will I implement Phone System?</span></span> |<span data-ttu-id="9611c-129">如需電話系統的詳細資訊，請參閱[Office 365 中的 [什麼是電話系統](what-is-phone-system-in-office-365.md)]。</span><span class="sxs-lookup"><span data-stu-id="9611c-129">For more information about Phone System, see [What is Phone System in Office 365](what-is-phone-system-in-office-365.md).</span></span></li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a><span data-ttu-id="9611c-130">連線到公用交換電話網絡（PSTN）</span><span class="sxs-lookup"><span data-stu-id="9611c-130">Connection to the Public Switched Telephone Network (PSTN)</span></span>

<span data-ttu-id="9611c-131">若要將電話系統連線至公用的交換電話網絡（PSTN），讓使用者可以撥打世界各地的電話，您可以根據業務需求選擇一些選項。</span><span class="sxs-lookup"><span data-stu-id="9611c-131">To connect Phone System to the Public Switched Telephone Network (PSTN) so that users can make phone calls around the world, you have options based on your business need.</span></span>  <span data-ttu-id="9611c-132">請自問下列事項：</span><span class="sxs-lookup"><span data-stu-id="9611c-132">Ask yourself the following:</span></span>


|<span data-ttu-id="9611c-133">問問自己</span><span class="sxs-lookup"><span data-stu-id="9611c-133">Ask yourself</span></span>|<span data-ttu-id="9611c-134">動作</span><span class="sxs-lookup"><span data-stu-id="9611c-134">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="9611c-135">我要使用 Microsoft 通話方案做為我的電話語音運營商嗎？</span><span class="sxs-lookup"><span data-stu-id="9611c-135">Do I want to use Microsoft Calling Plan as my telephony carrier?</span></span> | <span data-ttu-id="9611c-136">如需詳細資訊，請參閱[含有通話方案的電話系統](calling-plan-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="9611c-136">For more information, see [Phone System with Calling Plans](calling-plan-landing-page.md).</span></span>|
| <span data-ttu-id="9611c-137">我需要使用自己的電話運營商嗎？</span><span class="sxs-lookup"><span data-stu-id="9611c-137">Do I need to use my own telephony carrier?</span></span> | <span data-ttu-id="9611c-138">如需詳細資訊，請參閱[直接路由的電話系統](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="9611c-138">For more information, see [Phone System with Direct Routing](direct-routing-landing-page.md).</span></span>
|||


## <a name="additional-deployment-decisions"></a><span data-ttu-id="9611c-139">其他部署決策</span><span class="sxs-lookup"><span data-stu-id="9611c-139">Additional deployment decisions</span></span>

<span data-ttu-id="9611c-140">根據貴組織的需求和設定，您可能會想要變更下列專案的設定：</span><span class="sxs-lookup"><span data-stu-id="9611c-140">You may want to change settings for the following, based on your organization's needs and configuration:</span></span>

- <span data-ttu-id="9611c-141">語音信箱</span><span class="sxs-lookup"><span data-stu-id="9611c-141">Voicemail</span></span>
- <span data-ttu-id="9611c-142">通話身分識別</span><span class="sxs-lookup"><span data-stu-id="9611c-142">Calling identity</span></span>
- <span data-ttu-id="9611c-143">Microsoft 的電話號碼</span><span class="sxs-lookup"><span data-stu-id="9611c-143">Phone numbers from Microsoft</span></span>
- <span data-ttu-id="9611c-144">撥號方案</span><span class="sxs-lookup"><span data-stu-id="9611c-144">Dial plans</span></span>
- <span data-ttu-id="9611c-145">通話佇列</span><span class="sxs-lookup"><span data-stu-id="9611c-145">Call queues</span></span>
- <span data-ttu-id="9611c-146">自動語音應答</span><span class="sxs-lookup"><span data-stu-id="9611c-146">Auto attendants</span></span>

### <a name="voicemail"></a><span data-ttu-id="9611c-147">語音信箱</span><span class="sxs-lookup"><span data-stu-id="9611c-147">Voicemail</span></span>

<span data-ttu-id="9611c-148">雲端語音信箱（由 Azure 語音信箱服務提供支援）只支援將語音信箱存款至 Exchange 信箱，且不支援協力廠商電子郵件系統。</span><span class="sxs-lookup"><span data-stu-id="9611c-148">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn’t support third-party email systems.</span></span> <span data-ttu-id="9611c-149">雲端語音信箱包括語音信箱，預設會針對貴組織中的所有使用者啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="9611c-149">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="9611c-150">您的公司需求可能需要您針對特定使用者或整個組織中的所有人停用語音信箱。</span><span class="sxs-lookup"><span data-stu-id="9611c-150">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

|<span data-ttu-id="9611c-151">問問自己</span><span class="sxs-lookup"><span data-stu-id="9611c-151">Ask yourself</span></span>|<span data-ttu-id="9611c-152">動作</span><span class="sxs-lookup"><span data-stu-id="9611c-152">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="9611c-153">我想要啟用雲端語音信箱嗎？</span><span class="sxs-lookup"><span data-stu-id="9611c-153">Do I want to enable Cloud Voicemail?</span></span> | <span data-ttu-id="9611c-154">如需語音信箱設定程式，請參閱[設定雲端語音信箱](set-up-phone-system-voicemail.md)。</span><span class="sxs-lookup"><span data-stu-id="9611c-154">For voicemail setup procedures, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>
| <span data-ttu-id="9611c-155">我想要針對部分或所有使用者啟用語音信箱功能嗎？</span><span class="sxs-lookup"><span data-stu-id="9611c-155">Do I want to enable voicemail transcription for some or all of my users?</span></span> | <span data-ttu-id="9611c-156">若要關閉語音信箱，請參閱[設定貴組織中的語音信箱原則](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="9611c-156">To turn off voicemail transcription, see [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span></span></li></ul>|
|||

### <a name="calling-identity"></a><span data-ttu-id="9611c-157">通話身分識別</span><span class="sxs-lookup"><span data-stu-id="9611c-157">Calling identity</span></span>

<span data-ttu-id="9611c-158">根據預設，所有出站通話都會將指派的電話號碼做為呼叫身分識別（來電者識別碼）。</span><span class="sxs-lookup"><span data-stu-id="9611c-158">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="9611c-159">通話的收件者可以快速識別來電者，決定是否要接受或拒絕通話。</span><span class="sxs-lookup"><span data-stu-id="9611c-159">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="9611c-160">問問自己</span><span class="sxs-lookup"><span data-stu-id="9611c-160">Ask yourself</span></span>|<span data-ttu-id="9611c-161">動作</span><span class="sxs-lookup"><span data-stu-id="9611c-161">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="9611c-162">我想要遮罩或停用本機號碼嗎？</span><span class="sxs-lookup"><span data-stu-id="9611c-162">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="9611c-163">若要變更或封鎖本機號碼，請參閱[設定使用者的本機號碼](set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="9611c-163">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||

### <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="9611c-164">Microsoft 的電話號碼</span><span class="sxs-lookup"><span data-stu-id="9611c-164">Phone numbers from Microsoft</span></span>

<span data-ttu-id="9611c-165">Microsoft 提供兩種電話號碼類型：可指派給貴組織中的使用者的*訂閱者*（使用者）號碼，以及*服務*號碼（以付費和免付費服務號碼提供），這些號碼都有較高的同時通話容量比訂閱者號碼還可以指派給諸如音訊會議、自動語音應答或通話佇列等服務。</span><span class="sxs-lookup"><span data-stu-id="9611c-165">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers, which have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

|<span data-ttu-id="9611c-166">問問自己</span><span class="sxs-lookup"><span data-stu-id="9611c-166">Ask yourself</span></span>|<span data-ttu-id="9611c-167">動作</span><span class="sxs-lookup"><span data-stu-id="9611c-167">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="9611c-168">哪些使用者位置需要來自 Microsoft 的新電話號碼？</span><span class="sxs-lookup"><span data-stu-id="9611c-168">Which user locations need new phone numbers from Microsoft?</span></span> | <span data-ttu-id="9611c-169">如需取得電話號碼的相關資訊，請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)，以及[為使用者取得電話號碼](getting-phone-numbers-for-your-users.md)。</span><span class="sxs-lookup"><span data-stu-id="9611c-169">For information about getting phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) and [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span> 
| <span data-ttu-id="9611c-170">我需要哪一種類型的電話號碼（訂閱者或服務）？</span><span class="sxs-lookup"><span data-stu-id="9611c-170">Which type of telephone number (subscriber or service) do I need?</span></span> | <span data-ttu-id="9611c-171">若要協助您挑選所需的電話號碼類型，請參閱[通話方案所用的不同類型的電話號碼](different-kinds-of-phone-numbers-used-for-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="9611c-171">To help you pick the type of phone number you need, see [Different kinds of phone numbers used for Calling Plans](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span></span>
<span data-ttu-id="9611c-172">我要如何將現有的電話號碼移植至團隊？</span><span class="sxs-lookup"><span data-stu-id="9611c-172">How do I port existing phone numbers to Teams?</span></span>|<span data-ttu-id="9611c-173">如需詳細資訊，請參閱[將電話號碼轉移至 Microsoft 團隊](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="9611c-173">For more information, see [Transfer phone numbers to Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>
|||

### <a name="dial-plans"></a><span data-ttu-id="9611c-174">撥號方案</span><span class="sxs-lookup"><span data-stu-id="9611c-174">Dial plans</span></span>

<span data-ttu-id="9611c-175">Office 365 的 [電話系統] 功能中的撥號方案是一組正常化規則，可將撥打的電話號碼轉換成替代格式（通常是164個格式），用於呼叫授權及呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="9611c-175">A dial plan in the Phone System feature of Office 365 is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="9611c-176">如需撥號方案的詳細資訊，請參閱[什麼是撥號方案？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="9611c-176">For more information about dial plans, see [What are dial plans?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span></span>

|<span data-ttu-id="9611c-177">問問自己</span><span class="sxs-lookup"><span data-stu-id="9611c-177">Ask yourself</span></span>|<span data-ttu-id="9611c-178">動作</span><span class="sxs-lookup"><span data-stu-id="9611c-178">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="9611c-179">我的組織是否需要自訂的撥號方案？</span><span class="sxs-lookup"><span data-stu-id="9611c-179">Does my organization need a customized dial plan?</span></span> | <span data-ttu-id="9611c-180">若要協助判斷您是否需要自訂撥號方案，請參閱[規劃租使用者撥號方案](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="9611c-180">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span></span>|
<span data-ttu-id="9611c-181">哪些使用者需要自訂的撥號方案，以及應該將哪些租使用者撥號方案指派給每個使用者？</span><span class="sxs-lookup"><span data-stu-id="9611c-181">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span> | <span data-ttu-id="9611c-182">若要將使用者新增至 PowerShell 中的自訂撥號方案，請參閱[建立及管理撥號方案](create-and-manage-dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="9611c-182">To add users to a customized dial plan in PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span> |
|||

### <a name="call-queues"></a><span data-ttu-id="9611c-183">通話佇列</span><span class="sxs-lookup"><span data-stu-id="9611c-183">Call queues</span></span>

<span data-ttu-id="9611c-184">雲端通話佇列包括某人撥入您組織的電話號碼時所使用的問候語、自動保留通話的功能，以及在通話時搜尋下一個可用的呼叫代理程式來處理通話的功能在暫停時聆聽音樂。</span><span class="sxs-lookup"><span data-stu-id="9611c-184">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="9611c-185">您可以為組織建立單一或多個通話佇列。</span><span class="sxs-lookup"><span data-stu-id="9611c-185">You can create single or multiple call queues for your organization.</span></span> 


|<span data-ttu-id="9611c-186">問問自己</span><span class="sxs-lookup"><span data-stu-id="9611c-186">Ask yourself</span></span>|<span data-ttu-id="9611c-187">動作</span><span class="sxs-lookup"><span data-stu-id="9611c-187">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="9611c-188">我的組織是否需要呼叫佇列？</span><span class="sxs-lookup"><span data-stu-id="9611c-188">Does my organization need call queues?</span></span> | <span data-ttu-id="9611c-189">如需詳細資訊，請參閱[建立雲端通話佇列](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)及[設定您的電話系統](setting-up-your-phone-system.md)。</span><span class="sxs-lookup"><span data-stu-id="9611c-189">For more information, see [Create a Cloud call queue](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) and [Setting up your Phone System](setting-up-your-phone-system.md).</span></span> |

### <a name="auto-attendants"></a><span data-ttu-id="9611c-190">自動語音應答</span><span class="sxs-lookup"><span data-stu-id="9611c-190">Auto attendants</span></span>

<span data-ttu-id="9611c-191">雲端自動語音應答可用來為您的組織建立功能表系統，讓外部和內部呼叫者在功能表系統間移動，以找出電話，並將來電放到貴組織中的公司使用者或部門中。</span><span class="sxs-lookup"><span data-stu-id="9611c-191">Cloud auto attendants can be used to create a menu system for your organization that lets external and internal callers move through a menu system to locate and place or transfer calls to company users or departments in your organization.</span></span>

|<span data-ttu-id="9611c-192">問問自己</span><span class="sxs-lookup"><span data-stu-id="9611c-192">Ask yourself</span></span>|<span data-ttu-id="9611c-193">動作</span><span class="sxs-lookup"><span data-stu-id="9611c-193">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="9611c-194">我的組織是否需要自動語音應答？</span><span class="sxs-lookup"><span data-stu-id="9611c-194">Does my organization need auto attendants?</span></span> | <span data-ttu-id="9611c-195">如需詳細資訊，請參閱[什麼是雲端自動](what-are-phone-system-auto-attendants.md)語音應答，以及[設定雲端自動](create-a-phone-system-auto-attendant.md)語音應答。</span><span class="sxs-lookup"><span data-stu-id="9611c-195">For more information, see [What are Cloud auto attendants](what-are-phone-system-auto-attendants.md) and [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> |

### <a name="devices"></a><span data-ttu-id="9611c-196">台</span><span class="sxs-lookup"><span data-stu-id="9611c-196">Devices</span></span>

<span data-ttu-id="9611c-197">如需支援的裝置的詳細資訊，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="9611c-197">For more information about supported devices, see the following:</span></span>

- [<span data-ttu-id="9611c-198">在 Microsoft 團隊中管理您的裝置</span><span class="sxs-lookup"><span data-stu-id="9611c-198">Manage your devices in Microsoft Teams</span></span>](device-management.md)
- [<span data-ttu-id="9611c-199">IP 電話</span><span class="sxs-lookup"><span data-stu-id="9611c-199">IP Phones</span></span>](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="9611c-200">USB 音訊和視訊裝置</span><span class="sxs-lookup"><span data-stu-id="9611c-200">USB audio and video devices</span></span>](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="9611c-201">裝置的智慧通訊</span><span class="sxs-lookup"><span data-stu-id="9611c-201">Intelligent communications for devices</span></span>](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


