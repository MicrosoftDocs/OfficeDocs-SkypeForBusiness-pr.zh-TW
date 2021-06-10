---
title: 首先Microsoft Teams推出
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
localization_priority: Normal
search.appverid: MET150
description: 使用此指南，將Microsoft Teams作為您的第一Microsoft 365或Office 365工作量。
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 81ecf9a0f963a1be577149c585424c140df2abd5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119352"
---
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="86acc-103">首先Microsoft Teams推出</span><span class="sxs-lookup"><span data-stu-id="86acc-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="86acc-104">Microsoft Teams能協助員工保持聯繫並彼此共同作業，尤其是在目前前所未有的時間，遠端工作已讓世界各地的員工實作。</span><span class="sxs-lookup"><span data-stu-id="86acc-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="86acc-105">能夠在公司內部聊天、進行視訊會議，以及Office檔Teams協助公司保持生產力。</span><span class="sxs-lookup"><span data-stu-id="86acc-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="86acc-106">無論您是小型企業、非營利組織或大型組織，都可以在部署任何其他 Microsoft 365 或 Office 365 套件中，先開始使用 Teams 做為第一個工作負載Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="86acc-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Microsoft 365 or Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="86acc-107">本文詳細說明您必須使用「第一Teams考慮事項。</span><span class="sxs-lookup"><span data-stu-id="86acc-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="86acc-108">雖然Teams是貴組織的第一個雲端部署工作負載，但部署Teams應成為您整體雲端部署策略的一部分。</span><span class="sxs-lookup"><span data-stu-id="86acc-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="86acc-109">如果您已經推出其他 Microsoft 365 或 Office 365 服務和 Teams 是下一個要推出 (的工作量，而不是第一個) ，請從如何推出 Teams[開始](./deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="86acc-109">If you have already rolled out other Microsoft 365 or Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out Teams](./deploy-overview.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="86acc-110">從這裡開始</span><span class="sxs-lookup"><span data-stu-id="86acc-110">Start here</span></span>

<span data-ttu-id="86acc-111">若要開始使用您的Teams部署，您至少必須滿足一些先決條件。</span><span class="sxs-lookup"><span data-stu-id="86acc-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="86acc-112">下列清單會顯示貴組織必須擁有的位置，Teams啟用：</span><span class="sxs-lookup"><span data-stu-id="86acc-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="86acc-113">使用Microsoft 365或Office 365功能變數名稱所配置的組織</span><span class="sxs-lookup"><span data-stu-id="86acc-113">A Microsoft 365 or Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="86acc-114">Azure Active Directory連接 (AAD) 或類似的雲端身分識別同步處理解決方案 -所有所需的屬性都與租使用者同步處理</span><span class="sxs-lookup"><span data-stu-id="86acc-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="86acc-115">若要瞭解與 AAD 同步處理同步處理的屬性，請閱讀[Azure AD 連線同步處理：](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)同步處理Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="86acc-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="86acc-116">指派適當的使用者授權Teams</span><span class="sxs-lookup"><span data-stu-id="86acc-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="86acc-117">若要瞭解Teams授權，請閱讀Microsoft Teams[描述](/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="86acc-117">To understand Teams licensing, read [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

4.  <span data-ttu-id="86acc-118">為組織網路做好準備Teams</span><span class="sxs-lookup"><span data-stu-id="86acc-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="86acc-119">若要瞭解網路準備，請參閱準備貴組織的網路[以Teams。](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="86acc-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="86acc-120">允許網路存取 Exchange、Sharepoint 和 商務用 OneDrive 或 Microsoft 365 中的Office 365：Office 365 URL 和 IP[位址範圍](/office365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="86acc-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Microsoft 365 or Office 365: [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="86acc-121">在 2019 年 9 月 1 日之後建立租使用者會以 Teams 模式進行配置。</span><span class="sxs-lookup"><span data-stu-id="86acc-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="86acc-122">如果您已經商務用 Skype Server，而且您的租使用者是在 2019 年 9 月 1 日之後部署，請聯絡支援人員，以啟用 Teams。</span><span class="sxs-lookup"><span data-stu-id="86acc-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="86acc-123">將任何授權指派給使用者之前，請確定您的'全組織升級Teams設定<span class="underline"></span>為'島模式'。</span><span class="sxs-lookup"><span data-stu-id="86acc-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="86acc-124">移移起點</span><span class="sxs-lookup"><span data-stu-id="86acc-124">Migration Starting points</span></span>

<span data-ttu-id="86acc-125">您前往 Microsoft 365或Office 365可用功能Teams視您的起點，以及內部部署或 Lync 伺服器商務用 Skype使用。</span><span class="sxs-lookup"><span data-stu-id="86acc-125">Your journey to Microsoft 365 or Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="86acc-126">下列各節將詳述基本功能和組組選項，以及上述先決條件。</span><span class="sxs-lookup"><span data-stu-id="86acc-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="86acc-127">我們已將起點案例細分為下列主題：</span><span class="sxs-lookup"><span data-stu-id="86acc-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="86acc-128">**租Teams組** 態：租使用者和使用者模式是用來控制收件者的行為。</span><span class="sxs-lookup"><span data-stu-id="86acc-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="86acc-129">這些設定可以在租使用者層級或組織的使用者層級指派。</span><span class="sxs-lookup"><span data-stu-id="86acc-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="86acc-130">若要深入瞭解，請參閱[使用 商務用 Skype。](coexistence-chat-calls-presence.md)</span><span class="sxs-lookup"><span data-stu-id="86acc-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="86acc-131">**聊天/外部通訊** Teams：聊天服務是指與組織內部或組織外部的對等或群組聊天交談。</span><span class="sxs-lookup"><span data-stu-id="86acc-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="86acc-132">外部通訊也稱為在 商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="86acc-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="86acc-133">**在 Teams** 中建立和查看會議：一旦使用者獲得授權，使用者隨時都可以透過 Outlook Teams 附加元件和 PSTN 撥入功能建立線上會議。</span><span class="sxs-lookup"><span data-stu-id="86acc-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="86acc-134">Teams商務用 Skype將日曆資訊儲存在使用者的信箱Exchange中。</span><span class="sxs-lookup"><span data-stu-id="86acc-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="86acc-135">內部Exchange伺服器必須Exchange Server 2016 CU3 或更新Teams用戶端才能與使用者的信箱互動。</span><span class="sxs-lookup"><span data-stu-id="86acc-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="86acc-136">沒有Exchange信箱，系統將不會顯示 Teams 中的日曆圖示，使用者將無法在用戶端中查看、建立或修改Teams會議。</span><span class="sxs-lookup"><span data-stu-id="86acc-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="86acc-137">**通話功能 VoIP / PSTN** 在 Teams： 通話可以是語音 ip (VoIP) 或公用交換電話網絡 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="86acc-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="86acc-138">VoIP 連接會原生地Teams用戶端之間，而 PSTN 連接則發生在使用者撥打外部電話號碼時。</span><span class="sxs-lookup"><span data-stu-id="86acc-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="86acc-139">Teams兩種類型的 PSTN 連接。</span><span class="sxs-lookup"><span data-stu-id="86acc-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="86acc-140">Microsoft 通話方案：當 Microsoft 提供電話基礎結構 ，包括使用者的電話號碼或直接路由組式時，客戶會以會話邊界控制器 (SBC) 為 Teams 使用者提供電話連接。</span><span class="sxs-lookup"><span data-stu-id="86acc-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="86acc-141">若要深入瞭解，請參閱哪一種通話方案適合[您？電話系統](calling-plan-landing-page.md)[路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="86acc-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="86acc-142">**Teams和** 頻道共同作業Teams：在 Teams 中，團隊是一群為了工作、專案或共同興趣而彙集在一起的人。</span><span class="sxs-lookup"><span data-stu-id="86acc-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="86acc-143">Teams是由頻道所決定。</span><span class="sxs-lookup"><span data-stu-id="86acc-143">Teams are made up of channels.</span></span> <span data-ttu-id="86acc-144">每個頻道都是圍繞主題建立，例如「小組活動」、部門名稱，或只是為了好玩。</span><span class="sxs-lookup"><span data-stu-id="86acc-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="86acc-145">頻道是您可以召開會議、進行交談，以及共同處理檔案的地方。</span><span class="sxs-lookup"><span data-stu-id="86acc-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="86acc-146">在共同合作期間</span><span class="sxs-lookup"><span data-stu-id="86acc-146">During collaboration</span></span>

<span data-ttu-id="86acc-147">**商務用 OneDrive (p2P** 檔案共用) 在 Teams： Teams 和 Channels 之外，Teams 使用者可以使用 OneDrive 商務用或其他 P2P 共用檔案程式 ，例如思克檔案、DropBox、Box 和 Google 雲端硬碟 進行對等共用檔案。</span><span class="sxs-lookup"><span data-stu-id="86acc-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="86acc-148">針對OneDrive，使用者必須擁有SharePoint線上授權。</span><span class="sxs-lookup"><span data-stu-id="86acc-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="86acc-149">**應用程式平臺**：應用程式提供開箱即用的工具，讓貴組織獲得更多Teams。</span><span class="sxs-lookup"><span data-stu-id="86acc-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="86acc-150">這些應用程式結合由 Microsoft、協力廠商或貴組織的開發人員提供的定位停駐點、訊息擴充功能、連接器和 Bot 功能。</span><span class="sxs-lookup"><span data-stu-id="86acc-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="86acc-151">安全性 **與** 合規性功能：Teams 提供豐富的資訊，可協助您處理合規性領域，包括保留政策、資料遺失保護 (DLP) 、電子檔探索和頻道、聊天和檔案的法律保留、稽核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="86acc-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="86acc-152">若要深入瞭解，請參閱在 Microsoft Teams 中的安全性[Microsoft Teams。](security-compliance-overview.md)</span><span class="sxs-lookup"><span data-stu-id="86acc-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="86acc-153">進一步電子探索功能需要 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="86acc-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="86acc-154">[比較授權選項](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。</span><span class="sxs-lookup"><span data-stu-id="86acc-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="86acc-155">請參閱[Exchange Microsoft Teams](exchange-teams-interact.md)互動，以瞭解哪些合規性功能可在您的案例使用。</span><span class="sxs-lookup"><span data-stu-id="86acc-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="86acc-156">沒有 **<span class="underline">或</span>** Lync server 商務用 Skype組織</span><span class="sxs-lookup"><span data-stu-id="86acc-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync Server</span></span>

<span data-ttu-id="86acc-157">此起點假設您的組織目前並未使用 商務用 Skype Lync Server，Teams將成為您Microsoft 365或Office 365。</span><span class="sxs-lookup"><span data-stu-id="86acc-157">This starting point assumes that your organization does not utilize Skype for Business or Lync Server currently and Teams will be your first application in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="86acc-158">下表詳細列出適用于核心服務之Teams高層級的組Teams及使用者功能。</span><span class="sxs-lookup"><span data-stu-id="86acc-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="86acc-159">項目</span><span class="sxs-lookup"><span data-stu-id="86acc-159">Item</span></span></th>
<th><span data-ttu-id="86acc-160">注釋</span><span class="sxs-lookup"><span data-stu-id="86acc-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="86acc-161">租Teams組</span><span class="sxs-lookup"><span data-stu-id="86acc-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="86acc-162">Teams只有在模式中，所有聊天和通話功能都Teams使用。</span><span class="sxs-lookup"><span data-stu-id="86acc-162">Teams Only mode, all chat and calling features are in Teams Only.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="86acc-163">聊天/外部通訊Teams</span><span class="sxs-lookup"><span data-stu-id="86acc-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="86acc-164">內部 (內部Microsoft 365組織Office 365內部) 或外部聊天通訊Teams。</span><span class="sxs-lookup"><span data-stu-id="86acc-164">Internal (intra Microsoft 365 or Office 365 organization) and external chat communication possible from Teams.</span></span></p>
<p><span data-ttu-id="86acc-165"><em>注意：DNS 專案必須針對外部存取進行配置。</span><span class="sxs-lookup"><span data-stu-id="86acc-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="86acc-166">商務用 Skype即使您沒有內部部署或 商務用 Skype 或 Microsoft 365 或 Office 365，也需要 DNS 記錄，才能允許與 Lync 商務用 Skype環境：</span><span class="sxs-lookup"><span data-stu-id="86acc-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises, or in Microsoft 365 or Office 365, to allow federation with Lync and Skype for Business environments:</span></span><br /><span data-ttu-id="86acc-167">
<a href="/office365/enterprise/external-domain-name-system-records">外部網域名稱系統記錄</a></em></span><span class="sxs-lookup"><span data-stu-id="86acc-167">
<a href="/office365/enterprise/external-domain-name-system-records">External Domain Name System records</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="86acc-168">在會議中建立及Teams</span><span class="sxs-lookup"><span data-stu-id="86acc-168">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="86acc-169">能透過您的Outlook建立內部和外部會議。</span><span class="sxs-lookup"><span data-stu-id="86acc-169">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="86acc-170">PSTN 電話撥入和撥出功能與音訊會議授權一起提供。</span><span class="sxs-lookup"><span data-stu-id="86acc-170">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="86acc-171">Teams存取時，Exchange 2016 CU3+ 內部部署，並Exchange混合式部署：使用混合式組調精靈建立混合式<a href="/exchange/hybrid-deployment/deploy-hybrid">部署。</a> </span><span class="sxs-lookup"><span data-stu-id="86acc-171">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a> </span></span></p>
<p><span data-ttu-id="86acc-172">除了混合式Exchange之外，Exchange OAuth 驗證：設定組織Exchange與Exchange Online <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> 驗證」。</span><span class="sxs-lookup"><span data-stu-id="86acc-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations".</span></span></p>

</p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="86acc-173">通話功能</span><span class="sxs-lookup"><span data-stu-id="86acc-173">Calling Features</span></span><br />
<span data-ttu-id="86acc-174">VoIP / PSTN Teams</span><span class="sxs-lookup"><span data-stu-id="86acc-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="86acc-175">租使用者可在內部和外部使用 VoIP。</span><span class="sxs-lookup"><span data-stu-id="86acc-175">VoIP internally and externally to the tenant is available.</span></span></p>
<p><span data-ttu-id="86acc-176">PSTN 服務可透過系統Microsoft 電話，以及新增 Microsoft 通話方案或直接路由。</span><span class="sxs-lookup"><span data-stu-id="86acc-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="86acc-177">Teams頻道共同Teams</span><span class="sxs-lookup"><span data-stu-id="86acc-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="86acc-178">若要獲得完整體驗 ，包括合規性功能，SharePoint線上授權必須指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="86acc-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="86acc-179">不需要移SharePoint內部部署網站。</span><span class="sxs-lookup"><span data-stu-id="86acc-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="86acc-180">商務用 OneDrive (P2P 檔案共用) </span><span class="sxs-lookup"><span data-stu-id="86acc-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="86acc-181">商務用 OneDrive使用者必須指派線上SharePoint授權。</span><span class="sxs-lookup"><span data-stu-id="86acc-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="86acc-182">沒有此授權，將無法進行對等檔案共用。</span><span class="sxs-lookup"><span data-stu-id="86acc-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="86acc-183">應用程式平臺</span><span class="sxs-lookup"><span data-stu-id="86acc-183">Application platform</span></span></td>
<td><span data-ttu-id="86acc-184">使用者將能夠使用根據貴公司政策所指定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="86acc-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="86acc-185">如需深入瞭解，請<a href="/microsoftteams/admin-settings">在這裡：在</a>Teams</span><span class="sxs-lookup"><span data-stu-id="86acc-185">Learn more here: <a href="/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="86acc-186">安全性與合規性功能</span><span class="sxs-lookup"><span data-stu-id="86acc-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="86acc-187">保留政策可供使用。</span><span class="sxs-lookup"><span data-stu-id="86acc-187">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="86acc-188">支援電子檔探索和法律保留功能，以規範頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="86acc-188">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="86acc-189">資料外遺失防護 (DLP) 可用。</span><span class="sxs-lookup"><span data-stu-id="86acc-189">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="86acc-190">完整功能集可供Exchange Online;Exchange內部部署支援大部分的功能。</span><span class="sxs-lookup"><span data-stu-id="86acc-190">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="86acc-191">有關完整清單，請參閱<a href="/MicrosoftTeams/exchange-teams-interact">Exchange Teams互動</a>。</span><span class="sxs-lookup"><span data-stu-id="86acc-191">For a full list, see <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a>.</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="86acc-192">適用于沒有安裝或 Lync Server 商務用 Skype啟用步驟</span><span class="sxs-lookup"><span data-stu-id="86acc-192">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="86acc-193">符合上述開始這裡區段詳述的先決條件</span><span class="sxs-lookup"><span data-stu-id="86acc-193">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="86acc-194">將租使用者切換到Teams模式 (現有租使用者) ：[設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="86acc-194">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="86acc-195">根據貴公司的企業/公司政策設定您的租使用者：管理Microsoft Teams[的設定](enable-features-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="86acc-195">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="86acc-196">將Teams用戶端部署給使用者：[取得用戶端Teams](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="86acc-196">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="86acc-197">推動您的採用計畫</span><span class="sxs-lookup"><span data-stu-id="86acc-197">Drive your adoption program</span></span>  
    [<span data-ttu-id="86acc-198">採用Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="86acc-198">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="86acc-199">Microsoft Teams採用快速入門檢查清單</span><span class="sxs-lookup"><span data-stu-id="86acc-199">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="86acc-200">開始規劃將其他工作負載移Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="86acc-200">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="86acc-201">使用 **<span class="underline">商務用 Skype</span>** Lync 伺服器的組織</span><span class="sxs-lookup"><span data-stu-id="86acc-201">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="86acc-202">此起點假設貴組織使用內部商務用 Skype 2019 或 2015+ 或 Lync 2013+ 伺服器。</span><span class="sxs-lookup"><span data-stu-id="86acc-202">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="86acc-203">我們已針對組織從內部部署伺服器移Teams提供廣泛指引，這些案例應該會遵循。</span><span class="sxs-lookup"><span data-stu-id="86acc-203">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="86acc-204">此指南是特定案例，Teams是您用來執行或Microsoft 365 Office 365。</span><span class="sxs-lookup"><span data-stu-id="86acc-204">This guidance is specific to the scenario that Teams is the first application you utilize in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="86acc-205">下表詳細列出適用于核心服務之Teams高層級的組Teams及使用者功能。</span><span class="sxs-lookup"><span data-stu-id="86acc-205">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="86acc-206">項目</span><span class="sxs-lookup"><span data-stu-id="86acc-206">Item</span></span></th>
<th><span data-ttu-id="86acc-207">注釋</span><span class="sxs-lookup"><span data-stu-id="86acc-207">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="86acc-208">租Teams組</span><span class="sxs-lookup"><span data-stu-id="86acc-208">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="86acc-209">群島模式。</span><span class="sxs-lookup"><span data-stu-id="86acc-209">Islands mode.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="86acc-210">聊天/外部通訊Teams</span><span class="sxs-lookup"><span data-stu-id="86acc-210">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="86acc-211">只有在您自己的租使用者內部，外部通訊 (聯) 會透過您的商務用 Skype Lync 伺服器部署。</span><span class="sxs-lookup"><span data-stu-id="86acc-211">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="86acc-212">在會議中建立及Teams</span><span class="sxs-lookup"><span data-stu-id="86acc-212">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="86acc-213">能透過您的Outlook建立內部和外部會議。</span><span class="sxs-lookup"><span data-stu-id="86acc-213">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="86acc-214">PSTN 電話撥入和撥出功能與音訊會議授權一起提供。</span><span class="sxs-lookup"><span data-stu-id="86acc-214">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="86acc-215">Teams使用混合式Exchange部署 2016 CU3+ 內部部署，Exchange存取：</span><span class="sxs-lookup"><span data-stu-id="86acc-215">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="86acc-216">
<a href="/exchange/hybrid-deployment/deploy-hybrid">使用混合式群組原則建立混合式部署。</a></span><span class="sxs-lookup"><span data-stu-id="86acc-216">
<a href="/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a></span></span></p>
<p><span data-ttu-id="86acc-217">系統管理員可以透過 Teams 商務用 Skype Outlook 會議策略的 PreferredMeetingProviderForIslandsMode 屬性<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps">：set-csteamsmeetingpolicy</a>控制該附加元件。</span><span class="sxs-lookup"><span data-stu-id="86acc-217">Administrator can control the Skype for Business Outlook add-in via the Teams meeting policy’s PreferredMeetingProviderForIslandsMode attribute:<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</span></span></p> 
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="86acc-218">通話功能</span><span class="sxs-lookup"><span data-stu-id="86acc-218">Calling Features</span></span><br />
<span data-ttu-id="86acc-219">VoIP / PSTN Teams</span><span class="sxs-lookup"><span data-stu-id="86acc-219">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="86acc-220">可在租使用者內部使用 VoIP。</span><span class="sxs-lookup"><span data-stu-id="86acc-220">VoIP internally to the tenant is available.</span></span></p>
<p><span data-ttu-id="86acc-221">在將使用者移至 [僅體驗Teams PSTN 或通話方案服務。</span><span class="sxs-lookup"><span data-stu-id="86acc-221">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="86acc-222">Teams和頻道共同Teams</span><span class="sxs-lookup"><span data-stu-id="86acc-222">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="86acc-223">若要獲得完整體驗 ，包括合規性功能，SharePoint線上授權必須指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="86acc-223">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="86acc-224">不需要移SharePoint內部部署網站。</span><span class="sxs-lookup"><span data-stu-id="86acc-224">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="86acc-225">商務用 OneDrive (P2P 檔案共用) </span><span class="sxs-lookup"><span data-stu-id="86acc-225">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="86acc-226">商務用 OneDrive使用者必須指派線上SharePoint授權。</span><span class="sxs-lookup"><span data-stu-id="86acc-226">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="86acc-227">沒有此授權，無法進行每對對等檔案共用。</span><span class="sxs-lookup"><span data-stu-id="86acc-227">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="86acc-228">應用程式平臺</span><span class="sxs-lookup"><span data-stu-id="86acc-228">Application platform</span></span></td>
<td><span data-ttu-id="86acc-229">使用者將能夠使用根據貴公司政策所指定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="86acc-229">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="86acc-230">如需深入瞭解，請<a href="/microsoftteams/admin-settings">在這裡：在</a>Teams</span><span class="sxs-lookup"><span data-stu-id="86acc-230">Learn more here: <a href="/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="86acc-231">安全性與合規性功能</span><span class="sxs-lookup"><span data-stu-id="86acc-231">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="86acc-232">保留政策可供使用。</span><span class="sxs-lookup"><span data-stu-id="86acc-232">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="86acc-233">支援電子檔探索和法律保留功能，以規範頻道訊息。</span><span class="sxs-lookup"><span data-stu-id="86acc-233">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="86acc-234">資料外遺失防護 (DLP) 可用。</span><span class="sxs-lookup"><span data-stu-id="86acc-234">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="86acc-235">完整功能集可供Exchange Online;Exchange內部部署支援大部分的功能。</span><span class="sxs-lookup"><span data-stu-id="86acc-235">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="86acc-236">有關完整清單，請參閱<a href="/MicrosoftTeams/exchange-teams-interact">Exchange Teams互動。</a></span><span class="sxs-lookup"><span data-stu-id="86acc-236">For a complete list, see <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact.</a></span></span></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="86acc-237">適用于具有下列功能之組織的啟用商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="86acc-237">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="86acc-238">符合上述 <從這裡開始> 一節中詳述的先決條件。</span><span class="sxs-lookup"><span data-stu-id="86acc-238">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="86acc-239">針對 2019/9/1 (租使用者，請將租使用者切換為群島模式，請與支援人員聯繫，) </span><span class="sxs-lookup"><span data-stu-id="86acc-239">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact support to make this change)</span></span>  
    [<span data-ttu-id="86acc-240">設定您的共存和升級設定</span><span class="sxs-lookup"><span data-stu-id="86acc-240">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="86acc-241">根據貴公司的企業/公司政策設定租使用者</span><span class="sxs-lookup"><span data-stu-id="86acc-241">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="86acc-242">管理組織的 Microsoft Teams 設定</span><span class="sxs-lookup"><span data-stu-id="86acc-242">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="86acc-243">部署 Teams用戶端</span><span class="sxs-lookup"><span data-stu-id="86acc-243">Deploy the Teams client</span></span>  
    [<span data-ttu-id="86acc-244">取得 Teams 用戶端</span><span class="sxs-lookup"><span data-stu-id="86acc-244">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="86acc-245">推動您的採用計畫</span><span class="sxs-lookup"><span data-stu-id="86acc-245">Drive your adoption program</span></span>  
    [<span data-ttu-id="86acc-246">採用Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="86acc-246">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)<br/>
    [<span data-ttu-id="86acc-247">Microsoft Teams採用快速入門檢查清單</span><span class="sxs-lookup"><span data-stu-id="86acc-247">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="86acc-248">開始規劃將其他工作負載移Microsoft 365或Office 365</span><span class="sxs-lookup"><span data-stu-id="86acc-248">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

7.  <span data-ttu-id="86acc-249">建立商務用 Skype混合式，並遵循適用于 商務用 Skype Lync 伺服器的建議升級路徑</span><span class="sxs-lookup"><span data-stu-id="86acc-249">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="86acc-250">從內部商務用 Skype升級至Teams</span><span class="sxs-lookup"><span data-stu-id="86acc-250">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="86acc-251">結束語句</span><span class="sxs-lookup"><span data-stu-id="86acc-251">Closing statement</span></span>

<span data-ttu-id="86acc-252">Microsoft Teams成為貴組織在單一平臺上將所有員工、資訊工作者和前線工作人員彙集在一起的啟用器。</span><span class="sxs-lookup"><span data-stu-id="86acc-252">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Frontline workers, together on a single platform.</span></span> <span data-ttu-id="86acc-253">您 [今天就可以開始使用](https://products.office.com/microsoft-teams/group-chat-software) 。</span><span class="sxs-lookup"><span data-stu-id="86acc-253">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="86acc-254">您可以在這裡與我們所有的最新公告和每月產品更新 [保持聯繫](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)。</span><span class="sxs-lookup"><span data-stu-id="86acc-254">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="86acc-255">此外，由於世界各地的公司正在管理目前的 COVID-19 情況，我們已建立一系列內容，可協助您利用 Teams，以在組織中發揮最大影響。</span><span class="sxs-lookup"><span data-stu-id="86acc-255">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="86acc-256">我們在[COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)期間與客戶的承諾</span><span class="sxs-lookup"><span data-stu-id="86acc-256">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="86acc-257">2 周後：我們已瞭解遠端工作</span><span class="sxs-lookup"><span data-stu-id="86acc-257">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="86acc-258">提供線上會議和活動</span><span class="sxs-lookup"><span data-stu-id="86acc-258">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="86acc-259">協助中小型企業能夠使用 Teams 遠端工作</span><span class="sxs-lookup"><span data-stu-id="86acc-259">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="86acc-260">即時活動的數位轉換：Bob Bejan 從前線觀察</span><span class="sxs-lookup"><span data-stu-id="86acc-260">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - <span data-ttu-id="86acc-261">[Microsoft IT 為其員工啟用遠端作業的最熱門 9 種方式](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/) (英文)</span><span class="sxs-lookup"><span data-stu-id="86acc-261">[The top 9 ways Microsoft IT is enabling remote work for its employees](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)</span></span>

  - [<span data-ttu-id="86acc-262">遠端工作、保持安全 —適用于CISOS 的秘訣</span><span class="sxs-lookup"><span data-stu-id="86acc-262">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="86acc-263">協助教師和學生切換到遠端學習</span><span class="sxs-lookup"><span data-stu-id="86acc-263">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="86acc-264">在遠端使用電腦時保持生產力Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="86acc-264">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="86acc-265">支援服務參考</span><span class="sxs-lookup"><span data-stu-id="86acc-265">Support Services reference</span></span>

<span data-ttu-id="86acc-266">Teams仰賴 Exchange Online、SharePoint Online、商務用 OneDrive 和 Microsoft 365 群組，為使用者提供完全整合Microsoft 365或Office 365體驗。</span><span class="sxs-lookup"><span data-stu-id="86acc-266">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Microsoft 365 or Office 365 experience.</span></span> <span data-ttu-id="86acc-267">如上所述，Teams完全部署這些服務 ，但功能有限。</span><span class="sxs-lookup"><span data-stu-id="86acc-267">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="86acc-268">您可以在這裡閱讀更多Teams及其先決條件：[歡迎使用 Teams。](teams-overview.md)</span><span class="sxs-lookup"><span data-stu-id="86acc-268">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="86acc-269">如需上述每項服務的詳細資訊，請遵循下列連結：</span><span class="sxs-lookup"><span data-stu-id="86acc-269">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="86acc-270">Exchange Online用於日曆功能，以及將對等郵件儲存到 Teams。</span><span class="sxs-lookup"><span data-stu-id="86acc-270">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="86acc-271">若要深入瞭解，請參閱[Exchange Teams互動](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="86acc-271">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="86acc-272">若要Teams與 Exchange 內部部署進行交互操作，您必須設定新的 Exchange OAuth 驗證通訊協定，如在 Exchange 和 Exchange Online 組織之間設定[OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)驗證中所述。</span><span class="sxs-lookup"><span data-stu-id="86acc-272">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="86acc-273">SharePoint用於頻道中的檔案共用，而 /商務用 OneDrive 則用於 1：1 或群組聊天中的檔案共用。</span><span class="sxs-lookup"><span data-stu-id="86acc-273">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="86acc-274">若要深入瞭解，請參閱如何[SharePoint線上商務用 OneDrive與 Microsoft Teams。](sharepoint-onedrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="86acc-274">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="86acc-275">[Microsoft 365群組](office-365-groups.md)用於團隊和頻道建立/管理。</span><span class="sxs-lookup"><span data-stu-id="86acc-275">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="86acc-276">相關主題</span><span class="sxs-lookup"><span data-stu-id="86acc-276">Related topics</span></span>

[<span data-ttu-id="86acc-277">Microsoft Teams IT 架構設計人員與電話語音解決方案海報</span><span class="sxs-lookup"><span data-stu-id="86acc-277">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="86acc-278">規劃商務用 Skype Server 和 Office 365 之間的混合式連線</span><span class="sxs-lookup"><span data-stu-id="86acc-278">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="86acc-279">支援使用遠端Teams</span><span class="sxs-lookup"><span data-stu-id="86acc-279">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="86acc-280">遠端處理Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="86acc-280">Work remotely with Microsoft 365</span></span>](https://aka.ms/remote-work)