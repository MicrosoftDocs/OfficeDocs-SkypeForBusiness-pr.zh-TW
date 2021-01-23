---
title: Microsoft Teams 中的會議和召集會議
ms.reviewer: ''
description: 使用這些部署資源可協助您在 Microsoft Teams 中推出會議和音訊會議。
ms.topic: article
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
- m365initiative-meetings
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 48ec728921f545f4e8c383b16a9bc4e82c22b363
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918679"
---
# <a name="meetings-and-conferencing-in-microsoft-teams"></a><span data-ttu-id="bfdae-103">Microsoft Teams 中的會議和召集會議</span><span class="sxs-lookup"><span data-stu-id="bfdae-103">Meetings and conferencing in Microsoft Teams</span></span>

> [!NOTE]
> - <span data-ttu-id="bfdae-104">如需轉換至遠端學習和資源以協助您開始使用的概觀，請參閱我們的 [**遠端學習首頁**](https://www.microsoft.com/education/remote-learning)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-104">For an overview of making the transition to remote learning and resources to help you get started, see our [**remote learning home page**](https://www.microsoft.com/education/remote-learning).</span></span>
> - <span data-ttu-id="bfdae-105">可在 [**Office 365 教育版中的遠端教學和學習**](https://support.office.com/article/remote-teaching-and-learning-in-office-365-education-f651ccae-7b65-478b-8366-51bb884025c4)中取得協助教育人員和學生進行遠端學習的資源。</span><span class="sxs-lookup"><span data-stu-id="bfdae-105">Resources to assist educators and students with remote learning are available in [**Remote teaching and learning in Office 365 Education**](https://support.office.com/article/remote-teaching-and-learning-in-office-365-education-f651ccae-7b65-478b-8366-51bb884025c4).</span></span>


<span data-ttu-id="bfdae-106">您已完成[開始使用](get-started-with-teams-quick-start.md)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-106">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="bfdae-107">您已使用[聊天、團隊、頻道和應用程式](deploy-chat-teams-channels-microsoft-teams-landing-page.md)在組織中推出 Teams。</span><span class="sxs-lookup"><span data-stu-id="bfdae-107">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="bfdae-108">現在您已準備好要新增會議工作負載，包括[音訊會議](deploy-audio-conferencing-teams-landing-page.md)、視訊和共用。</span><span class="sxs-lookup"><span data-stu-id="bfdae-108">Now you're ready to add the meetings workload, including [audio conferencing](deploy-audio-conferencing-teams-landing-page.md), video, and sharing.</span></span> <span data-ttu-id="bfdae-109">本文將逐步引導您完成會議與音訊會議的推出。</span><span class="sxs-lookup"><span data-stu-id="bfdae-109">This article walks you through the rollout of meetings and audio conferencing.</span></span> <span data-ttu-id="bfdae-110">請從觀看我們的 Teams 會議、召集會議和裝置影片開始 (3 分 28 秒)：</span><span class="sxs-lookup"><span data-stu-id="bfdae-110">Start by watching our Teams meetings, conferencing, and devices video (3:28 minutes):</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE46ZdQ]

<span data-ttu-id="bfdae-111">若要深入了解使用者的會議體驗，請參閱 [會議和通話](https://support.office.com/article/meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-111">To learn more about the meetings experience for your users, see [Meetings and calls](https://support.office.com/article/meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span> 


<span data-ttu-id="bfdae-112">*2020 年 4 月新增功能*：會議召集人可以在會議期間按一下會議控制項中的 [結束會議]，結束 Teams 中所有會議參與者的會議。</span><span class="sxs-lookup"><span data-stu-id="bfdae-112">*New in April 2020*: Meeting organizers can end a meeting for all meeting participants in Teams by clicking **End meeting** in the meeting controls within the meeting.</span></span>  

<span data-ttu-id="bfdae-113">*2019 年 11 月中的新功能*：您現在可以 [使用 Advisor for Teams (預覽) 協助您推出 Microsoft Teams](use-advisor-teams-roll-out.md)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-113">*New in November 2019*: You can now [use Advisor for Teams (preview) to help you roll out Microsoft Teams](use-advisor-teams-roll-out.md).</span></span> <span data-ttu-id="bfdae-114">Advisor for Teams (預覽) 會引導您完成 Teams 的推出，包括會議和召集會議。</span><span class="sxs-lookup"><span data-stu-id="bfdae-114">Advisor for Teams (preview) walks you through your Teams rollout, including meetings and conferencing.</span></span> <span data-ttu-id="bfdae-115">在您於 Teams 中成功推出會議和召集會議之前，它會評估您的 Office 365 環境，找出可能需要更新或修改的最常用設定。</span><span class="sxs-lookup"><span data-stu-id="bfdae-115">It assesses your Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out meetings and conferencing in Teams.</span></span>

 > [!Note]
> <span data-ttu-id="bfdae-116">如需 Teams 會議與不同平台上的會議的詳細資訊，請參閱 [按平台區別的 Teams 功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-116">For details about Teams meetings and conferencing on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="meetings-and-conferencing-deployment-decisions"></a><span data-ttu-id="bfdae-117">會議和召集會議部署決策</span><span class="sxs-lookup"><span data-stu-id="bfdae-117">Meetings and conferencing deployment decisions</span></span>

<span data-ttu-id="bfdae-118">Teams 為您的組織提供絕佳的現成體驗，而大部分組織認為預設設定就能滿足其需求。</span><span class="sxs-lookup"><span data-stu-id="bfdae-118">Teams provides a great out-of-the-box experience for your organization, and most organizations find that the default settings work for them.</span></span> <span data-ttu-id="bfdae-119">本文可協助您決定是否要根據組織的設定檔和商務需求來變更任何預設設定，並逐步引導您完成每個變更。</span><span class="sxs-lookup"><span data-stu-id="bfdae-119">This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="bfdae-120">我們已將設定分割成兩個群組，從[您最可能進行的變更](#core-deployment-decisions)的核心集開始。</span><span class="sxs-lookup"><span data-stu-id="bfdae-120">We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="bfdae-121">根據組織的需求，第二個群組包括您可能想要設定的[其他設定](#additional-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-121">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

> [!Tip]
> <span data-ttu-id="bfdae-122">請觀看下列部分以深入了解會議：[IT 專業人員適用的 Microsoft Teams 中的會議簡介](https://aka.ms/teams-meetings-intro)</span><span class="sxs-lookup"><span data-stu-id="bfdae-122">Watch the following session to learn more about Meetings: [Introduction to Meetings in Microsoft Teams for IT Pros](https://aka.ms/teams-meetings-intro)</span></span>


## <a name="meetings-and-conferencing-prerequisites"></a><span data-ttu-id="bfdae-123">會議和召集會議必要條件</span><span class="sxs-lookup"><span data-stu-id="bfdae-123">Meetings and conferencing prerequisites</span></span>

<span data-ttu-id="bfdae-124">在組織中擴展您的會議部署之前，請用一些時間來檢閱並確認您的環境已備妥，可為使用者提供最佳的體驗。</span><span class="sxs-lookup"><span data-stu-id="bfdae-124">Before scaling your meetings deployment across your organization, take time to review and confirm that your environment is ready to provide users with the best possible experience.</span></span> <span data-ttu-id="bfdae-125">請檢閱下列資訊，並視需要對您的環境進行任何必要的變更。</span><span class="sxs-lookup"><span data-stu-id="bfdae-125">Review the following information and make any required changes to your environment as needed.</span></span>

<span data-ttu-id="bfdae-126">若要獲得 Teams 的最佳體驗，組織必須已部署 Exchange Online 和 SharePoint Online，並且必須具有 O365 經驗證的網域，例如 *contoso.com*。</span><span class="sxs-lookup"><span data-stu-id="bfdae-126">To get the best experience on Teams, your organization must have deployed Exchange Online and SharePoint Online, and you must have a verified domain for O365 such as *contoso.com*.</span></span>

<span data-ttu-id="bfdae-127">若要將會議擴及整個組織，您應確保所有使用者位置都擁有網際網路存取權，可連線至 Office 365 服務。</span><span class="sxs-lookup"><span data-stu-id="bfdae-127">To scale meetings across your organization you should ensure that all user locations have internet access to connect to the Office 365 Services.</span></span> <span data-ttu-id="bfdae-128">您應至少確保已從使用者的位置，將下列常見連接埠設為對網際網路開放：</span><span class="sxs-lookup"><span data-stu-id="bfdae-128">At a minimum you should make sure that the following common ports are open to the internet from your user's locations:-</span></span>

- <span data-ttu-id="bfdae-129">從將使用 Teams 的用戶端傳出的 TCP 連接埠 80 和 443</span><span class="sxs-lookup"><span data-stu-id="bfdae-129">TCP ports 80 and 443 outgoing from clients that will use Teams</span></span>
- <span data-ttu-id="bfdae-130">從將使用 Teams 的用戶端傳出的 UDP 連接埠 3478 到 3481</span><span class="sxs-lookup"><span data-stu-id="bfdae-130">UDP ports 3478 through 3481 outgoing from clients that will use Teams</span></span>

| <span data-ttu-id="bfdae-131">問問自己</span><span class="sxs-lookup"><span data-stu-id="bfdae-131">Ask yourself</span></span> | <span data-ttu-id="bfdae-132">動作</span><span class="sxs-lookup"><span data-stu-id="bfdae-132">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="bfdae-133">我的網路是否已準備好進行 Teams 會議部署？</span><span class="sxs-lookup"><span data-stu-id="bfdae-133">Is my network ready for Teams meetings deployment?</span></span> | <span data-ttu-id="bfdae-134">若要確認您的網路已準備就緒，請參閱：</span><span class="sxs-lookup"><span data-stu-id="bfdae-134">To verify that your network is ready, see:</span></span><ul><li>[<span data-ttu-id="bfdae-135">針對 Microsoft Teams 準備組織的網路</span><span class="sxs-lookup"><span data-stu-id="bfdae-135">Prepare your organization's network for Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</li><li>[<span data-ttu-id="bfdae-136">URL 和 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="bfdae-136">URLs and IP address ranges</span></span>](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)</li></ul> |
|||

## <a name="core-deployment-decisions"></a><span data-ttu-id="bfdae-137">核心部署決策</span><span class="sxs-lookup"><span data-stu-id="bfdae-137">Core deployment decisions</span></span>

<span data-ttu-id="bfdae-138">這些是大部分組織想要變更的設定 (如果 Teams 的預設設定不符合組織的需求)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-138">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

### <a name="teams-administrators"></a><span data-ttu-id="bfdae-139">Teams 系統管理員</span><span class="sxs-lookup"><span data-stu-id="bfdae-139">Teams administrators</span></span>

<span data-ttu-id="bfdae-p106">Teams 提供了一組自訂管理員角色，可用來為組織管理 Teams。這些角色為系統管理員提供了多種能力。</span><span class="sxs-lookup"><span data-stu-id="bfdae-p106">Teams provides a set of custom administrator roles that can be used to manage Teams for your organization. The roles provide various capabilities to administrators.</span></span> 

| <span data-ttu-id="bfdae-142">問問自己</span><span class="sxs-lookup"><span data-stu-id="bfdae-142">Ask yourself</span></span> | <span data-ttu-id="bfdae-143">動作</span><span class="sxs-lookup"><span data-stu-id="bfdae-143">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="bfdae-144">誰將獲指派 Teams 通訊系統管理員角色？</span><span class="sxs-lookup"><span data-stu-id="bfdae-144">Who will be assigned the Teams Communications Administrator role?</span></span>|<span data-ttu-id="bfdae-145">若要深入了解 Teams 系統管理員角色，請參閱[使用 Microsoft Teams 系統管理員角色管理來管理 Teams](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-145">To learn more about Teams administrator roles see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>|
|<span data-ttu-id="bfdae-146">誰將獲指派 Teams 通訊支援工程師角色？</span><span class="sxs-lookup"><span data-stu-id="bfdae-146">Who will be assigned the Teams Communications Support Engineer role?</span></span>|<span data-ttu-id="bfdae-147">若要指派系統管理員角色，[使用 Azure Active Directory 將系統管理員和非系統管理員角色指派給使用者](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-147">To assign admin roles, see [Assign administrator and non-administrator roles to users with Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>|
|<span data-ttu-id="bfdae-148">誰將獲指派 Teams 通訊支援專員角色？</span><span class="sxs-lookup"><span data-stu-id="bfdae-148">Who will be assigned the Teams Communications Support Specialist role?</span></span>||
|||

### <a name="meetings-settings"></a><span data-ttu-id="bfdae-149">會議設定</span><span class="sxs-lookup"><span data-stu-id="bfdae-149">Meetings settings</span></span> 

<span data-ttu-id="bfdae-150">會議設定可用於控制匿名使用者是否可以加入 Teams 會議、設定會議邀請，以及針對即時流量設定連接埠 (如果您要開啟服務品質，即 QoS)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-150">Meetings settings are used to control whether anonymous users can join Teams meetings, set up meeting invitations, and if you want to turn on Quality of Service (QoS), set the ports for real-time traffic.</span></span> <span data-ttu-id="bfdae-151">這些設定會用於使用者在組織中排程的所有 Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="bfdae-151">These settings will be used for all of the Teams meetings that users schedule in your organization.</span></span> 

| <span data-ttu-id="bfdae-152">問問自己</span><span class="sxs-lookup"><span data-stu-id="bfdae-152">Ask yourself</span></span> | <span data-ttu-id="bfdae-153">動作</span><span class="sxs-lookup"><span data-stu-id="bfdae-153">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="bfdae-154">我要自訂初始會議設定嗎？</span><span class="sxs-lookup"><span data-stu-id="bfdae-154">Will I customize the initial meeting settings?</span></span> |<span data-ttu-id="bfdae-155">若要深入了解會議設定，請參閱 [Teams 中的會議教學課程](tutorial-meetings-in-teams.yml)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-155">See the [Meetings in Teams tutorial](tutorial-meetings-in-teams.yml) to learn more about meetings settings.</span></span>|
|<span data-ttu-id="bfdae-156">我要實作 QoS 嗎？</span><span class="sxs-lookup"><span data-stu-id="bfdae-156">Will I implement QoS?</span></span>|<span data-ttu-id="bfdae-157">如需 QoS 概念的相關資訊，請參閱 [Microsoft Teams 中的服務品質](qos-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-157">See [Quality of Service in Microsoft Teams](qos-in-teams.md) for information about QoS concepts.</span></span> <span data-ttu-id="bfdae-158">案例和實作。</span><span class="sxs-lookup"><span data-stu-id="bfdae-158">scenarios, and implementation.</span></span>|
|||

### <a name="meeting-policies"></a><span data-ttu-id="bfdae-159">會議原則</span><span class="sxs-lookup"><span data-stu-id="bfdae-159">Meeting policies</span></span>

<span data-ttu-id="bfdae-160">會議原則用於控制使用者加入 Teams 會議時可使用的功能。</span><span class="sxs-lookup"><span data-stu-id="bfdae-160">Meeting policies are used to control what features are available to users when they join Teams meetings.</span></span> <span data-ttu-id="bfdae-161">您可以使用預設原則或是為組織中舉辦會議的人員建立一或多個自訂會議原則。</span><span class="sxs-lookup"><span data-stu-id="bfdae-161">You can use the default policy or create one or more custom meeting policies for people that host meetings in your organization.</span></span> <span data-ttu-id="bfdae-162">若要深入了解，請參閱 [Microsoft Teams 中的會議教學課程](tutorial-meetings-in-teams.yml)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-162">To learn more, see the [Meetings in Microsoft Team tutorial](tutorial-meetings-in-teams.yml).</span></span>

| <span data-ttu-id="bfdae-163">問問自己</span><span class="sxs-lookup"><span data-stu-id="bfdae-163">Ask yourself</span></span> | <span data-ttu-id="bfdae-164">動作</span><span class="sxs-lookup"><span data-stu-id="bfdae-164">Action</span></span> |
|--------------|--------|
|<ul><li><span data-ttu-id="bfdae-165">我要自訂初始會議原則嗎？</span><span class="sxs-lookup"><span data-stu-id="bfdae-165">Will I customize the initial meeting policies?</span></span></li><li><span data-ttu-id="bfdae-166">我需要多個會議原則嗎？</span><span class="sxs-lookup"><span data-stu-id="bfdae-166">Do I require multiple meeting policies?</span></span></li><li><span data-ttu-id="bfdae-167">我如何判斷哪些使用者群組會套用哪些會議原則？</span><span class="sxs-lookup"><span data-stu-id="bfdae-167">How will I determine which groups of users get which meetings policy applied?</span></span></li></ul>|<br><span data-ttu-id="bfdae-168">請閱讀[在 Teams 中管理會議原則](meeting-policies-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-168">Read [Manage meeting policies in Teams](meeting-policies-in-teams.md).</span></span>|
|||

### <a name="audio-conferencing"></a><span data-ttu-id="bfdae-169">音訊會議</span><span class="sxs-lookup"><span data-stu-id="bfdae-169">Audio Conferencing</span></span>

<span data-ttu-id="bfdae-170">音訊會議能讓會議參與者使用傳統有線電話、專用交換機 (PBX) 或行動電話撥入，透過公用交換電話網路 (PSTN) 加入會議，為組織提供任何會議 (臨機操作或排程) 的其他進入點。</span><span class="sxs-lookup"><span data-stu-id="bfdae-170">Audio Conferencing provides organizations with additional entry points to any meeting (ad hoc or scheduled) by allowing meeting participants to join via public switched telephone network (PSTN) by dialing in using a traditional land line, private branch exchange (PBX), or mobile phone.</span></span> 

<span data-ttu-id="bfdae-171">當您準備好要推出音訊會議時，請參閱深入的[音訊會議推出](deploy-audio-conferencing-teams-landing-page.md)指導方針。</span><span class="sxs-lookup"><span data-stu-id="bfdae-171">When you're ready to roll out Audio Conferencing, see the in-depth [Audio Conferencing rollout](deploy-audio-conferencing-teams-landing-page.md) guidance.</span></span>

### <a name="meeting-room-and-personal-devices"></a><span data-ttu-id="bfdae-172">會議室和個人裝置</span><span class="sxs-lookup"><span data-stu-id="bfdae-172">Meeting room and personal devices</span></span>

<span data-ttu-id="bfdae-173">若要在 Teams 中獲得最佳會議體驗，請考慮使用 Teams 裝置，例如會議室系統、電話、耳機和相機。</span><span class="sxs-lookup"><span data-stu-id="bfdae-173">For an optimal meeting experience in Teams, consider using Teams devices such as room systems, phones, headsets, and cameras.</span></span> <span data-ttu-id="bfdae-174">若要深入了解，請參閱[適用於智慧型通訊的 Microsoft Teams 裝置](https://products.office.com/microsoft-teams/across-devices)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-174">To learn more, see [Teams devices for intelligent communications](https://products.office.com/microsoft-teams/across-devices).</span></span>

| <span data-ttu-id="bfdae-175">問問自己</span><span class="sxs-lookup"><span data-stu-id="bfdae-175">Ask yourself</span></span> | <span data-ttu-id="bfdae-176">動作</span><span class="sxs-lookup"><span data-stu-id="bfdae-176">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="bfdae-177">我要為使用者購買個人裝置嗎？</span><span class="sxs-lookup"><span data-stu-id="bfdae-177">Will I purchase personal devices for my users?</span></span> |<span data-ttu-id="bfdae-178">請閱讀[在 Teams 中管理裝置](devices/device-management.md)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-178">Read [Manage your devices in Teams](devices/device-management.md).</span></span> |
|<span data-ttu-id="bfdae-179">我要為會議室購買並部署會議室系統裝置嗎？</span><span class="sxs-lookup"><span data-stu-id="bfdae-179">Will I purchase and deploy room system devices for my conference rooms?</span></span>|<span data-ttu-id="bfdae-180">請閱讀[會議室裝置和解決方案](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-180">Read [Meeting room devices and solutions](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span>|
|||

### <a name="reporting"></a><span data-ttu-id="bfdae-181">報告</span><span class="sxs-lookup"><span data-stu-id="bfdae-181">Reporting</span></span>

<span data-ttu-id="bfdae-182">使用活動報告來查看組織中的使用者如何使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="bfdae-182">Use activity reports to see how users in your organization are using Teams.</span></span> <span data-ttu-id="bfdae-183">例如，如果有人還沒使用 Teams，可能是他們不知道如何開始，或不了解如何使用 Teams 提高生產力和共同作業。</span><span class="sxs-lookup"><span data-stu-id="bfdae-183">For example, if some don't use Teams yet, they might not know how to get started or understand how they can use Teams to be more productive and collaborative.</span></span> <span data-ttu-id="bfdae-184">組織可以使用活動報告來決定要優先進行訓練和溝通的方面。</span><span class="sxs-lookup"><span data-stu-id="bfdae-184">Your organization can use the activity reports to decide where to prioritize training and communication efforts.</span></span> 


| <span data-ttu-id="bfdae-185">問問自己</span><span class="sxs-lookup"><span data-stu-id="bfdae-185">Ask yourself</span></span> | <span data-ttu-id="bfdae-186">動作</span><span class="sxs-lookup"><span data-stu-id="bfdae-186">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="bfdae-187">誰將負責報告？</span><span class="sxs-lookup"><span data-stu-id="bfdae-187">Who will be responsible for reporting?</span></span>|<span data-ttu-id="bfdae-188">請閱讀[對 Teams 使用活動報告](teams-activity-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-188">Read [Use activity reports for Teams](teams-activity-reports.md).</span></span>  |
|<span data-ttu-id="bfdae-189">誰將負責監視使用情況？</span><span class="sxs-lookup"><span data-stu-id="bfdae-189">Who will be responsible for monitoring usage?</span></span>|<span data-ttu-id="bfdae-190">請閱讀[在 Teams 中監視使用情況和意見反應](get-started-with-teams-monitor-usage-and-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-190">Read [Monitor usage and feedback in Teams](get-started-with-teams-monitor-usage-and-feedback.md).</span></span>|
|||

## <a name="additional-deployment-decisions"></a><span data-ttu-id="bfdae-191">其他部署決策</span><span class="sxs-lookup"><span data-stu-id="bfdae-191">Additional deployment decisions</span></span>

<span data-ttu-id="bfdae-192">根據組織的需求和組態而定，您可能會想要變更這些設定。</span><span class="sxs-lookup"><span data-stu-id="bfdae-192">You may want to change these settings, based on your organization's needs and configuration.</span></span>

### <a name="bandwidth-planning"></a><span data-ttu-id="bfdae-193">頻寬規劃</span><span class="sxs-lookup"><span data-stu-id="bfdae-193">Bandwidth planning</span></span> 

<span data-ttu-id="bfdae-194">頻寬規劃可讓組織估計在其廣域網路和網際網路連結上支援會議所需的頻寬，讓他們能夠確認網路已正確佈建，可支援向外擴充的會議服務。</span><span class="sxs-lookup"><span data-stu-id="bfdae-194">Bandwidth planning lets organizations estimate the bandwidth that will be required to support meetings across their wide area networks and internet links so they can confirm that the network is correctly provisioned to support a scaled out meeting service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bfdae-195">當使用者離線或以有限頻寬執行時，Teams 不會讓使用者排程會議或即時活動。</span><span class="sxs-lookup"><span data-stu-id="bfdae-195">Teams won't let users schedule meetings or live events when they're offline or running with limited bandwidth.</span></span> 

| <span data-ttu-id="bfdae-196">問問自己</span><span class="sxs-lookup"><span data-stu-id="bfdae-196">Ask yourself</span></span> | <span data-ttu-id="bfdae-197">動作</span><span class="sxs-lookup"><span data-stu-id="bfdae-197">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="bfdae-198">我是否需要在會議推出之前和期間進行頻寬規劃？</span><span class="sxs-lookup"><span data-stu-id="bfdae-198">Do I need to do bandwidth planning prior to and during my Meetings rollout?</span></span> |<span data-ttu-id="bfdae-199">如需詳細資訊和可簡化規劃程序的工具連結，請參閱[網路整備](3-envision-evaluate-my-environment.md#network-readiness)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-199">See [Network Readiness](3-envision-evaluate-my-environment.md#network-readiness) for more information and links to tools to simplify your planning process.</span></span>|
|||

### <a name="meeting-recording-and-archiving"></a><span data-ttu-id="bfdae-200">會議錄製和封存</span><span class="sxs-lookup"><span data-stu-id="bfdae-200">Meeting recording and archiving</span></span>

<span data-ttu-id="bfdae-201">使用者可以記錄其會議和群組通話，以擷取音訊、視訊和螢幕共用的活動。</span><span class="sxs-lookup"><span data-stu-id="bfdae-201">Users can record their meetings and group calls to capture audio, video, and screen sharing activity.</span></span> <span data-ttu-id="bfdae-202">您也可以使用自動轉錄的錄製選項，便於使用者播放具有隱藏式輔助字幕的會議錄製，並在文字記錄中搜尋重要的討論項目。</span><span class="sxs-lookup"><span data-stu-id="bfdae-202">There is also an option for recordings to have automatic transcription, so that users can play back meeting recordings with closed captions and search for important discussion items in the transcript.</span></span> <span data-ttu-id="bfdae-203">錄製會在雲端中進行，並儲存到 Microsoft Stream，因此使用者可以安全地在整個組織內共用檔案。</span><span class="sxs-lookup"><span data-stu-id="bfdae-203">The recording happens in the cloud and is saved in Microsoft Stream, so users can share it securely across their organization.</span></span> <span data-ttu-id="bfdae-204">若要尋找會議的錄製，請前往會議交談。</span><span class="sxs-lookup"><span data-stu-id="bfdae-204">To find the recording for a meeting, go to the meeting conversation.</span></span>

>[!Note]
> <span data-ttu-id="bfdae-p113">從使用 Microsoft Stream 變更為使用[商務用 OneDrive 和 SharePoint 來進行會議錄製](tmr-meeting-recording-change.md)，將會採取階段性的方式。推出時您將可以加入此體驗。在 11 月，如果您想要繼續使用 Stream，則必須退出體驗。在 2021 年初的某個時候，我們將要求所有客戶對新會議錄製使用商務用 OneDrive 和 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="bfdae-p113">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

<span data-ttu-id="bfdae-207">若要深入了解，請參閱 [Teams 雲端會議錄製](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-207">To learn more, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

| <span data-ttu-id="bfdae-208">問問自己</span><span class="sxs-lookup"><span data-stu-id="bfdae-208">Ask yourself</span></span> | <span data-ttu-id="bfdae-209">動作</span><span class="sxs-lookup"><span data-stu-id="bfdae-209">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="bfdae-210">我將開啟會議轉錄服務嗎？</span><span class="sxs-lookup"><span data-stu-id="bfdae-210">Will I turn on the meeting transcription service?</span></span>|<span data-ttu-id="bfdae-211">請參閱[開啟或關閉錄製轉錄](cloud-recording.md#turn-on-or-turn-off-cloud-recording)</span><span class="sxs-lookup"><span data-stu-id="bfdae-211">See [Turn on or turn off recording transcription](cloud-recording.md#turn-on-or-turn-off-cloud-recording)</span></span>|
|||


### <a name="live-events-policies"></a><span data-ttu-id="bfdae-212">即時事件原則</span><span class="sxs-lookup"><span data-stu-id="bfdae-212">Live events policies</span></span>

<span data-ttu-id="bfdae-213">Teams 即時事件原則用於管理使用者群組的事件設定。</span><span class="sxs-lookup"><span data-stu-id="bfdae-213">Teams live events policies are used to manage event settings for groups of users.</span></span> <span data-ttu-id="bfdae-214">您可以使用預設原則或建立可指派給組織內舉辦活動的使用者的額外原則。</span><span class="sxs-lookup"><span data-stu-id="bfdae-214">You can use the default policy or create additional policies that can be assigned to users who hold live events within your organization.</span></span> 

| <span data-ttu-id="bfdae-215">問問自己</span><span class="sxs-lookup"><span data-stu-id="bfdae-215">Ask yourself</span></span> | <span data-ttu-id="bfdae-216">動作</span><span class="sxs-lookup"><span data-stu-id="bfdae-216">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="bfdae-217">我的組織是否會使用 Teams 即時事件？</span><span class="sxs-lookup"><span data-stu-id="bfdae-217">Will my organization use Teams live events?</span></span>| <span data-ttu-id="bfdae-218">如需規劃、設定及設定 Teams 即時事件的詳細資訊，請參閱[即時事件文章](teams-live-events/what-are-teams-live-events.md)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-218">See the [live events articles](teams-live-events/what-are-teams-live-events.md) for more information about planning for, setting up, and configuring Teams live events.</span></span>|
|||

### <a name="conference-room-systems-rollout"></a><span data-ttu-id="bfdae-219">會議室系統推出</span><span class="sxs-lookup"><span data-stu-id="bfdae-219">Conference room systems rollout</span></span>

<span data-ttu-id="bfdae-220">擁有多個會議室的組織可能需要使用結構化的方法來清查其會議室、找出適當的裝置，然後將它們推出。</span><span class="sxs-lookup"><span data-stu-id="bfdae-220">Organizations with many conference rooms may want to consider a structured approach to inventorying their rooms, identifying the appropriate devices, and then rolling them out.</span></span> 



| <span data-ttu-id="bfdae-221">問問自己</span><span class="sxs-lookup"><span data-stu-id="bfdae-221">Ask yourself</span></span> | <span data-ttu-id="bfdae-222">動作</span><span class="sxs-lookup"><span data-stu-id="bfdae-222">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="bfdae-223">要推出會議室系統，我需要做什麼？</span><span class="sxs-lookup"><span data-stu-id="bfdae-223">What do I need to do to roll out conference room systems?</span></span>|<span data-ttu-id="bfdae-224">請查看[規劃 Microsoft Teams 會議室](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)文章。</span><span class="sxs-lookup"><span data-stu-id="bfdae-224">Check out the [Plan Microsoft Teams Rooms](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) articles.</span></span>|
|||

### <a name="cloud-video-interop"></a><span data-ttu-id="bfdae-225">雲端視訊 Interop</span><span class="sxs-lookup"><span data-stu-id="bfdae-225">Cloud video interop</span></span>

<span data-ttu-id="bfdae-226">雲端視訊 Interop 可讓第三方會議室裝置加入 Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="bfdae-226">Cloud video interop makes it possible for third-party meeting room devices to join Teams meetings.</span></span> 

<span data-ttu-id="bfdae-227">具有內容共同作業的視訊電話會議可協助您充分利用會議。</span><span class="sxs-lookup"><span data-stu-id="bfdae-227">Video teleconferencing with content collaboration helps you make the most out of meetings.</span></span> <span data-ttu-id="bfdae-228">不過，會議室系統和裝置的升級成本過於高昂。</span><span class="sxs-lookup"><span data-stu-id="bfdae-228">However, meeting room systems and devices are expensive to upgrade.</span></span> <span data-ttu-id="bfdae-229">適用於 Teams 的雲端視訊 Interop 可搭配第三方系統使用，並可為所有參與者 (會議室中或 Teams 用戶端內) 提供原生的會議體驗。</span><span class="sxs-lookup"><span data-stu-id="bfdae-229">Cloud video interop for Teams works with third-party systems and delivers a native meeting experience for all participants – in meeting rooms or inside Teams clients.</span></span> 

| <span data-ttu-id="bfdae-230">問問自己</span><span class="sxs-lookup"><span data-stu-id="bfdae-230">Ask yourself</span></span> | <span data-ttu-id="bfdae-231">動作</span><span class="sxs-lookup"><span data-stu-id="bfdae-231">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="bfdae-232">我將隨著會議室系統部署使用雲端視訊 Interop 解決方案嗎？</span><span class="sxs-lookup"><span data-stu-id="bfdae-232">Will I use a cloud video interop solution as part of my room systems deployment?</span></span> | <span data-ttu-id="bfdae-233">請閱讀 [Teams 雲端視訊 Interop](cloud-video-interop.md)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-233">Read [Cloud Video Interop for Teams](cloud-video-interop.md).</span></span>|
|||


### <a name="personal-device-rollout"></a><span data-ttu-id="bfdae-234">個人裝置推出</span><span class="sxs-lookup"><span data-stu-id="bfdae-234">Personal device rollout</span></span>

<span data-ttu-id="bfdae-235">當規劃推出大量個人裝置以支援會議或語音部署時，請考慮使用可重複執行的站對站推出程序，以提供相同的品質。</span><span class="sxs-lookup"><span data-stu-id="bfdae-235">When planning a larger rollout of personal devices to support meetings or voice deployments, consider using a repeatable site-by-site rollout process that delivers repeatable quality.</span></span>

| <span data-ttu-id="bfdae-236">問問自己</span><span class="sxs-lookup"><span data-stu-id="bfdae-236">Ask yourself</span></span> | <span data-ttu-id="bfdae-237">動作</span><span class="sxs-lookup"><span data-stu-id="bfdae-237">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="bfdae-238">我要使用站對站方法來推出會議嗎？</span><span class="sxs-lookup"><span data-stu-id="bfdae-238">Will I use a site-by-site approach to roll out Meetings?</span></span> |  <span data-ttu-id="bfdae-239">[Teams 的網站啟用語音手冊](3-onboard-deploy-my-service.md#site-enablement-playbook-for-microsoft-teams-voice-workloads)可提供良好的基礎，供您用於自己的部署。</span><span class="sxs-lookup"><span data-stu-id="bfdae-239">The [Site enablement playbook for Teams](3-onboard-deploy-my-service.md#site-enablement-playbook-for-microsoft-teams-voice-workloads) provides a good foundation that you can use for your own deployments.</span></span> <span data-ttu-id="bfdae-240">本指南著重於語音，但是裝置交付、帳戶整備、採用及訓練的一般原則亦適用大型會議部署。</span><span class="sxs-lookup"><span data-stu-id="bfdae-240">The guide is focused on voice, but the general principles of device delivery, account readiness, adoption, and training apply to a large meeting deployment.</span></span> |
|||

### <a name="troubleshoot-meeting-and-call-quality"></a><span data-ttu-id="bfdae-241">對會議和通話品質進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="bfdae-241">Troubleshoot meeting and call quality</span></span> 

<span data-ttu-id="bfdae-242">Teams 有兩種方式可供您監視和疑難排解通話品質問題：[通話分析和通話品質儀表板](monitor-call-quality-qos.md)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-242">Teams gives you two ways to monitor and troubleshoot call quality problems: [Call Analytics and Call Quality Dashboard](monitor-call-quality-qos.md).</span></span> <span data-ttu-id="bfdae-243">通話分析能顯示每位使用者在特定通話和會議的裝置、網路和連線詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="bfdae-243">Call Analytics shows detailed information about the devices, networks, and connectivity related to the specific calls and meetings for each user.</span></span> <span data-ttu-id="bfdae-244">通話分析的設計目的在於協助系統管理員和支援人員疑難排解特定通話的通話品質問題，而通話品質儀表板的設計目的則是在協助系統管理員和網路工程師最佳化網路。</span><span class="sxs-lookup"><span data-stu-id="bfdae-244">Call Analytics is designed to help admins and helpdesk agents troubleshoot call quality problems with specific calls, whereas the Call Quality Dashboard is designed to help admins and network engineers optimize a network.</span></span> <span data-ttu-id="bfdae-245">通話品質儀表板的重點不在特定使用者身上，而是會查看整個 Teams 組織的匯彙資訊。</span><span class="sxs-lookup"><span data-stu-id="bfdae-245">Call Quality Dashboard shifts focus from specific users and instead looks at aggregate information for an entire Teams organization.</span></span> 

|<span data-ttu-id="bfdae-246">問問自己</span><span class="sxs-lookup"><span data-stu-id="bfdae-246">Ask yourself</span></span>|<span data-ttu-id="bfdae-247">動作</span><span class="sxs-lookup"><span data-stu-id="bfdae-247">Action</span></span> |
|------------|-------|
| <span data-ttu-id="bfdae-248">誰會負責監視及疑難排解通話品質問題？</span><span class="sxs-lookup"><span data-stu-id="bfdae-248">Who will be responsible for monitoring and troubleshooting call quality issues?</span></span> | <span data-ttu-id="bfdae-249">如需疑難排解通話品質問題所需權限等級的相關資訊，請閱讀[使用通話分析來疑難排解不良通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-249">Read [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md) for information about permission levels required to troubleshoot call quality issues.</span></span>|
|||

### <a name="operate-your-meetings-service"></a><span data-ttu-id="bfdae-250">操作會議服務</span><span class="sxs-lookup"><span data-stu-id="bfdae-250">Operate your meetings service</span></span>

<span data-ttu-id="bfdae-251">請務必了解 Teams 服務的整體運作狀況，這樣才能主動提醒在組織中的其他人會影響服務的任何活動。</span><span class="sxs-lookup"><span data-stu-id="bfdae-251">It's important that you understand the overall health of the Teams service so that you can proactively alert others in your organization of any event that affects the service.</span></span> <span data-ttu-id="bfdae-252">[營運我的服務](1-drive-value-operate-my-service.md)文章提供服務作業的深入指引。</span><span class="sxs-lookup"><span data-stu-id="bfdae-252">The [Operate my service](1-drive-value-operate-my-service.md) articles provide in-depth guidance for service operations.</span></span>

|<span data-ttu-id="bfdae-253">問問自己</span><span class="sxs-lookup"><span data-stu-id="bfdae-253">Ask yourself</span></span>|<span data-ttu-id="bfdae-254">動作</span><span class="sxs-lookup"><span data-stu-id="bfdae-254">Action</span></span> |
|------------|-------|
|<span data-ttu-id="bfdae-255">我的組織中的哪些人員將負責管理會議服務？</span><span class="sxs-lookup"><span data-stu-id="bfdae-255">Who in my organization will be responsible for managing the meetings service?</span></span> | <span data-ttu-id="bfdae-256">請確定這個人員擁有管理您的會議服務所需的 Teams 系統管理員權限。</span><span class="sxs-lookup"><span data-stu-id="bfdae-256">Make sure this person has the Teams admin permissions they need in order to manage your meetings service.</span></span> <span data-ttu-id="bfdae-257">若要深入了解 Teams 系統管理員角色，請參閱[使用 Microsoft Teams 系統管理員角色管理來管理 Teams](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-257">To learn more about Teams administrator roles see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>|
|||


## <a name="next-steps"></a><span data-ttu-id="bfdae-258">後續步驟</span><span class="sxs-lookup"><span data-stu-id="bfdae-258">Next steps</span></span>
- <span data-ttu-id="bfdae-259">在您的組織中推動會議和召集會議的[採用](adopt-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-259">[Drive adoption](adopt-microsoft-teams-landing-page.md) of meetings & conferencing throughout your organization.</span></span>
- [<span data-ttu-id="bfdae-260">新增音訊會議</span><span class="sxs-lookup"><span data-stu-id="bfdae-260">Add audio conferencing</span></span>](deploy-audio-conferencing-teams-landing-page.md)
- [<span data-ttu-id="bfdae-261">推出雲端語音</span><span class="sxs-lookup"><span data-stu-id="bfdae-261">Roll out cloud voice</span></span>](cloud-voice-landing-page.md)
- <span data-ttu-id="bfdae-262">在您的 Teams 初始推出中包含精選應用程式，例如 Planner。</span><span class="sxs-lookup"><span data-stu-id="bfdae-262">Include featured apps - such as Planner - in your initial Teams rollout.</span></span> <span data-ttu-id="bfdae-263">在開始推動 Teams 的採用時，則新增其他[應用程式、Bot 和連接器](deploy-apps-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="bfdae-263">Add other [apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md) as you drive Teams adoption.</span></span>
