---
title: 先推出 Microsoft 團隊
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
description: 使用本指導方針將 Microsoft 團隊作為您的第一份 Office 365 工作負載來推出。
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 647f6879f7892c1a65599832e48deb67e183fae0
ms.sourcegitcommit: bdafa1f4146e615d325e27a50352f10c0d51ef1a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/01/2020
ms.locfileid: "44472344"
---
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="2971a-103">先推出 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="2971a-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="2971a-104">Microsoft 團隊可以協助您的員工彼此保持聯繫並共同作業，特別是在目前空前的時間裡，我們的遠端工作是世界各地員工的實際員工。</span><span class="sxs-lookup"><span data-stu-id="2971a-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="2971a-105">在團隊中，您可以在 Office 檔上進行聊天、進行影片會議與共同作業，協助公司維持生產力。</span><span class="sxs-lookup"><span data-stu-id="2971a-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="2971a-106">無論您是小型企業、非盈利性或大型組織，您都可以在部署任何其他 Office app 或服務之前，先開始將團隊作為 Office 365 套件中的第一個工作負載。</span><span class="sxs-lookup"><span data-stu-id="2971a-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="2971a-107">本文詳細說明您必須使用「團隊優先」做法所做的考慮。</span><span class="sxs-lookup"><span data-stu-id="2971a-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2971a-108">當團隊可以是貴組織的第一個雲端部署工作負載時，部署團隊應該是整個雲端部署策略的一部分。</span><span class="sxs-lookup"><span data-stu-id="2971a-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="2971a-109">如果您已經推出其他 Office 365 服務，而團隊是您下次要推出的工作負載（而不是第一個），請先從[如何推出小組](How-to-roll-out-teams.md)開始。</span><span class="sxs-lookup"><span data-stu-id="2971a-109">If you have already rolled out other Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out  Teams](How-to-roll-out-teams.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="2971a-110">從這裡開始</span><span class="sxs-lookup"><span data-stu-id="2971a-110">Start here</span></span>

<span data-ttu-id="2971a-111">若要開始使用您的小組第一次部署，您必須至少滿足一些必備元件。</span><span class="sxs-lookup"><span data-stu-id="2971a-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="2971a-112">下列清單會顯示您在啟用團隊之前必須針對貴組織進行的動作：</span><span class="sxs-lookup"><span data-stu-id="2971a-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="2971a-113">使用您的功能變數名稱設定的 Office 365 組織</span><span class="sxs-lookup"><span data-stu-id="2971a-113">An Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="2971a-114">Azure Active Directory 連線（AAD 連線）或類似的雲端身分識別同步處理方案（含與您的租使用者同步處理的所有必要屬性）</span><span class="sxs-lookup"><span data-stu-id="2971a-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="2971a-115">若要瞭解與 AAD 同步處理的屬性，請閱讀[AZURE AD Connect 同步處理：屬性已同步處理到 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span><span class="sxs-lookup"><span data-stu-id="2971a-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="2971a-116">指派給小組的適當使用者授權</span><span class="sxs-lookup"><span data-stu-id="2971a-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="2971a-117">若要瞭解團隊授權，請參閱[Microsoft 團隊服務說明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="2971a-117">To understand Teams licensing, read [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

4.  <span data-ttu-id="2971a-118">組織為團隊準備的網路</span><span class="sxs-lookup"><span data-stu-id="2971a-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="2971a-119">若要瞭解網路準備，請閱讀[針對團隊準備貴組織的網路](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="2971a-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="2971a-120">允許在 Office 365 中存取 Exchange、Sharepoint 和商務用 OneDrive 的網路： [office 365 url 與 IP 位址範圍](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="2971a-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Office 365: [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="2971a-121">在2019年9月1日之後建立的租使用者僅限 [小組] 模式提供。</span><span class="sxs-lookup"><span data-stu-id="2971a-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="2971a-122">如果您已部署商務用 Skype Server 且您的租使用者已于2019年9月1日之後預配，請聯絡支援人員來啟用團隊的共存功能。</span><span class="sxs-lookup"><span data-stu-id="2971a-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="2971a-123">將任何團隊授權指派給使用者<span class="underline">之前</span>，請確定您的 [組織範圍升級原則] 已設定為 [孤島模式]。</span><span class="sxs-lookup"><span data-stu-id="2971a-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="2971a-124">遷移開始點</span><span class="sxs-lookup"><span data-stu-id="2971a-124">Migration Starting points</span></span>

<span data-ttu-id="2971a-125">根據您的起點以及現有的內部部署商務用 Skype 或 Lync server，您可以在小組中使用 Office 365 和功能。</span><span class="sxs-lookup"><span data-stu-id="2971a-125">Your journey to Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="2971a-126">除了上述必備元件之外，下列各節將詳細說明基本功能和配置選項。</span><span class="sxs-lookup"><span data-stu-id="2971a-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="2971a-127">我們已將起點案例分解成下列主題：</span><span class="sxs-lookup"><span data-stu-id="2971a-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="2971a-128">**租使用者小組**設定：租使用者和使用者模式是用來控制收件者的行為。</span><span class="sxs-lookup"><span data-stu-id="2971a-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="2971a-129">您可以在租使用者層級或組織中的使用者層級指派這些設定。</span><span class="sxs-lookup"><span data-stu-id="2971a-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="2971a-130">若要深入瞭解，請參閱[與商務用 Skype 共存](coexistence-chat-calls-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="2971a-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="2971a-131">**團隊中的聊天/外部通訊**：聊天服務會參照對等與組織內或外部的對等或群組聊天交談。</span><span class="sxs-lookup"><span data-stu-id="2971a-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="2971a-132">外部通訊也稱為商務用 Skype 中的同盟。</span><span class="sxs-lookup"><span data-stu-id="2971a-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="2971a-133">**在團隊中建立及查看會議**：使用者隨時都可以透過 Outlook 團隊增益集和 PSTN 撥入來建立線上會議（在使用者獲得授權後，所有案例都會提供）。</span><span class="sxs-lookup"><span data-stu-id="2971a-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="2971a-134">[小組] 和 [商務用 Skype] 會在使用者的 Exchange 信箱中儲存行事曆資訊。</span><span class="sxs-lookup"><span data-stu-id="2971a-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="2971a-135">在內部部署 Exchange server 必須是 Exchange Server 2016 CU3 或更新版本，小組用戶端才能與使用者的信箱互動。</span><span class="sxs-lookup"><span data-stu-id="2971a-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="2971a-136">若沒有 Exchange 信箱存取，小組中的行事曆圖示就不會出現，而且使用者將無法在團隊用戶端中查看、建立或修改會議。</span><span class="sxs-lookup"><span data-stu-id="2971a-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="2971a-137">**在團隊中通話功能 VoIP/PSTN**：通話可以是經由 IP 語音（VoIP）或公用交換電話網絡（PSTN）。</span><span class="sxs-lookup"><span data-stu-id="2971a-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="2971a-138">VoIP 連線會在團隊用戶端之間固有進行，而 PSTN 連線則會在使用者撥打外線連線號碼時發生。</span><span class="sxs-lookup"><span data-stu-id="2971a-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="2971a-139">團隊支援兩種類型的 PSTN 連線。</span><span class="sxs-lookup"><span data-stu-id="2971a-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="2971a-140">Microsoft 通話方案： Microsoft 提供電話結構，包括使用者的電話號碼，或直接路由設定，客戶可在團隊使用者的會話邊界控制器（SBC）上提供電話連線。</span><span class="sxs-lookup"><span data-stu-id="2971a-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="2971a-141">若要深入瞭解，請閱讀適合[您的通話方案](calling-plan-landing-page.md)，以及[電話系統直接路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="2971a-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="2971a-142">團隊中的**團隊和頻道**共同作業：團隊中的團隊是共同作業、專案或共同興趣的人員群組。</span><span class="sxs-lookup"><span data-stu-id="2971a-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="2971a-143">團隊是由頻道組成。</span><span class="sxs-lookup"><span data-stu-id="2971a-143">Teams are made up of channels.</span></span> <span data-ttu-id="2971a-144">每個頻道都是圍繞主題建立，例如「團隊活動」、部門名稱或只是有趣的。</span><span class="sxs-lookup"><span data-stu-id="2971a-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="2971a-145">頻道是您在其中召開會議、進行交談及共同處理檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="2971a-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="2971a-146">在共同作業期間</span><span class="sxs-lookup"><span data-stu-id="2971a-146">During collaboration</span></span>

<span data-ttu-id="2971a-147">**小組中的商務用 onedrive （P2P 檔案共用）**：團隊使用者可以使用商務用 OneDrive 或其他 P2P 共用檔案程式（例如 Citrix 檔案、DropBox、Box 和 Google 雲端硬碟）來共用檔案對等。</span><span class="sxs-lookup"><span data-stu-id="2971a-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="2971a-148">針對商務用 OneDrive，使用者必須已指派 SharePoint Online 授權。</span><span class="sxs-lookup"><span data-stu-id="2971a-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="2971a-149">**應用程式平臺**： app 提供現成的工具供貴組織用來充分發揮團隊的效用。</span><span class="sxs-lookup"><span data-stu-id="2971a-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="2971a-150">這些 app 結合由 Microsoft （由協力廠商或由貴組織的開發人員建立）所提供的索引標籤、訊息擴充、連接器和 bot 功能。</span><span class="sxs-lookup"><span data-stu-id="2971a-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="2971a-151">**安全性與合規性功能：** 團隊有一系列的資訊可協助您處理合規性區域，包括保留原則、資料遺失保護（DLP）、eDiscovery 和法律封存（適用于頻道、聊天和檔案）、審核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="2971a-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="2971a-152">若要深入瞭解，請參閱[Microsoft 團隊中的安全性與合規性](security-compliance-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="2971a-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="2971a-153">預先探索的 eDiscovery 功能需要 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="2971a-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="2971a-154">[比較授權選項](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。</span><span class="sxs-lookup"><span data-stu-id="2971a-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="2971a-155">閱讀[Exchange 與 Microsoft 團隊如何互動](exchange-teams-interact.md)，瞭解您的案例中提供哪些規範功能。</span><span class="sxs-lookup"><span data-stu-id="2971a-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="2971a-156">**<span class="underline">沒有</span>** 商務用 Skype 或 Lync server 的組織</span><span class="sxs-lookup"><span data-stu-id="2971a-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="2971a-157">這個起點假設貴組織不使用商務用 Skype 或 Lync server，目前與團隊將是 Office 365 中的第一個應用程式。</span><span class="sxs-lookup"><span data-stu-id="2971a-157">This starting point assumes that your organization does not utilize Skype for Business or Lync server currently and Teams will be your first application in Office 365.</span></span> <span data-ttu-id="2971a-158">下表詳細說明適用于核心服務之團隊的高層次設定和使用者功能。</span><span class="sxs-lookup"><span data-stu-id="2971a-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="2971a-159">項目</span><span class="sxs-lookup"><span data-stu-id="2971a-159">Item</span></span></th>
<th><span data-ttu-id="2971a-160">筆記</span><span class="sxs-lookup"><span data-stu-id="2971a-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="2971a-161">租使用者小組配置</span><span class="sxs-lookup"><span data-stu-id="2971a-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="2971a-162">[僅限團隊] 模式，所有聊天和通話功能只適用于團隊</span><span class="sxs-lookup"><span data-stu-id="2971a-162">Teams Only mode, all chat and calling features are in Teams Only</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2971a-163">團隊中的聊天/外部通訊</span><span class="sxs-lookup"><span data-stu-id="2971a-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="2971a-164">內部（Office 365 組織內）及來自團隊的外部聊天通訊</span><span class="sxs-lookup"><span data-stu-id="2971a-164">Internal (intra Office 365 organization) and external chat communication possible from Teams</span></span></p>
<p><span data-ttu-id="2971a-165"><em>注意： DNS 專案必須針對外部存取進行設定。</span><span class="sxs-lookup"><span data-stu-id="2971a-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="2971a-166">您也可以使用商務用 skype DNS 記錄，即使您沒有商務用 skype 內部部署或 Office 365，才能允許與 Lync 和商務用 Skype 環境進行同盟。</span><span class="sxs-lookup"><span data-stu-id="2971a-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises or in Office 365 to allow federation with Lync and Skype for Business environments.</span></span><br /><span data-ttu-id="2971a-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">Office 365 的外部網域名稱系統記錄</a></em></span><span class="sxs-lookup"><span data-stu-id="2971a-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">External Domain Name System records for Office 365</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2971a-168"><em>在團隊中建立及查看會議</em></span><span class="sxs-lookup"><span data-stu-id="2971a-168"><em>Create and view Meetings in Teams</em></span></span></td>
<td><p><span data-ttu-id="2971a-169"><em>能夠透過 Outlook 增益集建立會議</em></span><span class="sxs-lookup"><span data-stu-id="2971a-169"><em>Able to create meetings via Outlook add-in</em></span></span></p>
<p><span data-ttu-id="2971a-170"><em>支援 PSTN 撥入和撥出功能（含音訊會議授權）。</span><span class="sxs-lookup"><span data-stu-id="2971a-170"><em>PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span><br />
<span data-ttu-id="2971a-171">注意：團隊行事曆存取需要已建立 exchange 2016 的 Exchange CU3 + 內部部署：<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">使用混合</a>式設定向導建立混合式部署</span><span class="sxs-lookup"><span data-stu-id="2971a-171">Note: Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard</a></span></span><br />
<span data-ttu-id="2971a-172">除了 Exchange 混合式設定之外，請建立 Exchange OAuth 驗證：<a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">設定 exchange 與 Exchange Online 組織之間的 OAuth 驗證</a></em></span><span class="sxs-lookup"><span data-stu-id="2971a-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations</a></em></span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2971a-173">通話功能</span><span class="sxs-lookup"><span data-stu-id="2971a-173">Calling Features</span></span><br />
<span data-ttu-id="2971a-174">團隊中的 VoIP/PSTN</span><span class="sxs-lookup"><span data-stu-id="2971a-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="2971a-175">可在內部和外部 VoIP 至租使用者</span><span class="sxs-lookup"><span data-stu-id="2971a-175">VoIP internally and externally to the tenant is available</span></span></p>
<p><span data-ttu-id="2971a-176">PSTN 服務可以透過 Microsoft Phone System 進行設定，以及新增 Microsoft 通話方案或直接路由。</span><span class="sxs-lookup"><span data-stu-id="2971a-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2971a-177">團隊中的團隊和頻道共同作業</span><span class="sxs-lookup"><span data-stu-id="2971a-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="2971a-178">如需全面體驗（包括規範功能），必須將 SharePoint Online 授權指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="2971a-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="2971a-179">不需要遷移現有的內部部署 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="2971a-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2971a-180">商務用 OneDrive （P2P 檔案共用）</span><span class="sxs-lookup"><span data-stu-id="2971a-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="2971a-181">商務用 OneDrive 需要有指派 SharePoint Online 授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="2971a-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="2971a-182">如果沒有這個授權對等檔案共用，就不可能了。</span><span class="sxs-lookup"><span data-stu-id="2971a-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2971a-183">應用程式平臺</span><span class="sxs-lookup"><span data-stu-id="2971a-183">Application platform</span></span></td>
<td><span data-ttu-id="2971a-184">使用者將能夠根據您的公司原則，使用指派給他們的 app。</span><span class="sxs-lookup"><span data-stu-id="2971a-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="2971a-185">深入瞭解：<a href="https://docs.microsoft.com/microsoftteams/admin-settings">在團隊中應用程式的系統管理設定</a></span><span class="sxs-lookup"><span data-stu-id="2971a-185">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2971a-186">安全性與合規性功能</span><span class="sxs-lookup"><span data-stu-id="2971a-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="2971a-187">保留原則可供使用</span><span class="sxs-lookup"><span data-stu-id="2971a-187">Retention policies are available</span></span></p></li>
<li><p><span data-ttu-id="2971a-188">支援針對通道訊息遵循的 eDiscovery 與法律封存</span><span class="sxs-lookup"><span data-stu-id="2971a-188">eDiscovery and Legal Hold for compliance on channel messages is supported</span></span></p></li>
<li><p><span data-ttu-id="2971a-189">可使用資料遺失防護原則（DLP）</span><span class="sxs-lookup"><span data-stu-id="2971a-189">Data Loss Prevention policies (DLP) are available</span></span></p></li>
</ul>
<p><span data-ttu-id="2971a-190">完整的功能集可在 Exchange Online 中使用，Exchange 內部部署支援大多數這些功能，請參閱<a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">exchange 與團隊如何與</a>您的完整清單互動。</span><span class="sxs-lookup"><span data-stu-id="2971a-190">Full feature set available with Exchange Online, Exchange on-premises supports most of these features, see <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a> for full list.</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="2971a-191">沒有商務用 Skype 或 Lync Server 的組織啟用步驟</span><span class="sxs-lookup"><span data-stu-id="2971a-191">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="2971a-192">在上方的 [從這裡開始] 區段中，符合先決條件的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="2971a-192">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="2971a-193">僅限將租使用者切換至 [只適用于現有租使用者] 模式：[設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="2971a-193">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="2971a-194">依照貴公司的商務/公司原則來設定您的租使用者：[管理貴組織的 Microsoft 團隊設定](enable-features-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="2971a-194">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="2971a-195">將團隊用戶端部署至您的使用者：[取得團隊用戶端](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="2971a-195">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="2971a-196">推動您的採納計畫</span><span class="sxs-lookup"><span data-stu-id="2971a-196">Drive your adoption program</span></span>  
    [<span data-ttu-id="2971a-197">採納 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="2971a-197">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="2971a-198">Microsoft 團隊採用快速入門檢查清單</span><span class="sxs-lookup"><span data-stu-id="2971a-198">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="2971a-199">開始規劃將其他工作負載移至 Office 365</span><span class="sxs-lookup"><span data-stu-id="2971a-199">Begin planning moving other workloads to Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="2971a-200">**<span class="underline">擁有商務用</span>** Skype 或 Lync server 的組織</span><span class="sxs-lookup"><span data-stu-id="2971a-200">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="2971a-201">這個起點假設您的組織使用商務用 Skype 2019 或 2015 + 或 Lync 2013 + 伺服器內部部署。</span><span class="sxs-lookup"><span data-stu-id="2971a-201">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="2971a-202">我們已經有許多從內部部署伺服器遷移至小組的組織的指導方針，而且應該遵循這些案例。</span><span class="sxs-lookup"><span data-stu-id="2971a-202">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="2971a-203">本指南是專門針對團隊是您在 Office 365 中使用的第一個應用程式的情況。</span><span class="sxs-lookup"><span data-stu-id="2971a-203">This guidance is specific to the scenario that Teams is the first application you utilize in Office 365.</span></span> <span data-ttu-id="2971a-204">下表詳細說明適用于核心服務之團隊的高層次設定和使用者功能。</span><span class="sxs-lookup"><span data-stu-id="2971a-204">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="2971a-205">項目</span><span class="sxs-lookup"><span data-stu-id="2971a-205">Item</span></span></th>
<th><span data-ttu-id="2971a-206">筆記</span><span class="sxs-lookup"><span data-stu-id="2971a-206">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="2971a-207">租使用者小組配置</span><span class="sxs-lookup"><span data-stu-id="2971a-207">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="2971a-208">孤島模式</span><span class="sxs-lookup"><span data-stu-id="2971a-208">Islands mode</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2971a-209">團隊中的聊天/外部通訊</span><span class="sxs-lookup"><span data-stu-id="2971a-209">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="2971a-210">在您自己的租使用者內，外部通訊（同盟）是透過您的商務用 Skype 或 Lync server 部署所內部進行</span><span class="sxs-lookup"><span data-stu-id="2971a-210">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2971a-211">在團隊中建立及查看會議</span><span class="sxs-lookup"><span data-stu-id="2971a-211">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="2971a-212">能夠透過 Outlook 增益集建立會議</span><span class="sxs-lookup"><span data-stu-id="2971a-212">Able to create meetings via Outlook add-in</span></span></p>
<p><span data-ttu-id="2971a-213">支援 PSTN 撥入和撥出功能（含音訊會議授權）。</span><span class="sxs-lookup"><span data-stu-id="2971a-213">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span><br />
<span data-ttu-id="2971a-214">團隊行事曆存取需要 exchange 2016 CU3 + 內部部署，且已建立 Exchange 混合式部署：</span><span class="sxs-lookup"><span data-stu-id="2971a-214">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="2971a-215">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">使用混合式設定精靈建立混合式部署</a></span><span class="sxs-lookup"><span data-stu-id="2971a-215">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard</a></span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2971a-216">通話功能</span><span class="sxs-lookup"><span data-stu-id="2971a-216">Calling Features</span></span><br />
<span data-ttu-id="2971a-217">團隊中的 VoIP/PSTN</span><span class="sxs-lookup"><span data-stu-id="2971a-217">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="2971a-218">提供租使用者內部的 VoIP</span><span class="sxs-lookup"><span data-stu-id="2971a-218">VoIP internally to the tenant is available</span></span></p>
<p><span data-ttu-id="2971a-219">在使用者移至團隊只有經驗之後，才能使用 PSTN 或通話方案服務</span><span class="sxs-lookup"><span data-stu-id="2971a-219">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2971a-220">團隊中的團隊和頻道共同作業</span><span class="sxs-lookup"><span data-stu-id="2971a-220">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="2971a-221">如需全面體驗（包括規範功能），必須將 SharePoint Online 授權指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="2971a-221">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="2971a-222">不需要遷移現有的內部部署 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="2971a-222">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2971a-223">商務用 OneDrive （P2P 檔案共用）</span><span class="sxs-lookup"><span data-stu-id="2971a-223">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="2971a-224">商務用 OneDrive 需要有指派 SharePoint Online 授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="2971a-224">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="2971a-225">不可能有此授權的每對等檔案共用。</span><span class="sxs-lookup"><span data-stu-id="2971a-225">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2971a-226">應用程式平臺</span><span class="sxs-lookup"><span data-stu-id="2971a-226">Application platform</span></span></td>
<td><span data-ttu-id="2971a-227">使用者將能夠根據您的公司原則，使用指派給他們的 app。</span><span class="sxs-lookup"><span data-stu-id="2971a-227">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="2971a-228">深入瞭解：<a href="https://docs.microsoft.com/microsoftteams/admin-settings">在團隊中應用程式的系統管理設定</a></span><span class="sxs-lookup"><span data-stu-id="2971a-228">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2971a-229">安全性與合規性功能</span><span class="sxs-lookup"><span data-stu-id="2971a-229">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="2971a-230">保留原則可供使用</span><span class="sxs-lookup"><span data-stu-id="2971a-230">Retention policies are available</span></span></p></li>
<li><p><span data-ttu-id="2971a-231">支援針對通道訊息遵循的 eDiscovery 與法律封存</span><span class="sxs-lookup"><span data-stu-id="2971a-231">eDiscovery and Legal Hold for compliance on channel messages is supported</span></span></p></li>
<li><p><span data-ttu-id="2971a-232">可使用資料遺失防護原則（DLP）</span><span class="sxs-lookup"><span data-stu-id="2971a-232">Data Loss Prevention policies (DLP) are available</span></span></p></li>
</ul>
<p><span data-ttu-id="2971a-233">完整的功能集可在 Exchange Online 中使用，Exchange 內部部署支援這些功能的大部分，請參閱</span><span class="sxs-lookup"><span data-stu-id="2971a-233">Full feature set available with Exchange Online, Exchange on-premises supports most of these features, see</span></span></p>
<p><span data-ttu-id="2971a-234"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Exchange 和 Teams 如何互動</a></span><span class="sxs-lookup"><span data-stu-id="2971a-234"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a></span></span></p>
<ul>
<li><p><span data-ttu-id="2971a-235">若要取得完整清單</span><span class="sxs-lookup"><span data-stu-id="2971a-235">for full list</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="2971a-236">商務用 Skype Server 的組織啟用步驟</span><span class="sxs-lookup"><span data-stu-id="2971a-236">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="2971a-237">符合上述 [從這裡開始] 區段中的先決條件。</span><span class="sxs-lookup"><span data-stu-id="2971a-237">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="2971a-238">將租使用者切換到孤島模式（在9/1/2019 之後，請與支援人員聯繫以進行變更）</span><span class="sxs-lookup"><span data-stu-id="2971a-238">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact support to make this change)</span></span>  
    [<span data-ttu-id="2971a-239">設定您的共存與升級設定</span><span class="sxs-lookup"><span data-stu-id="2971a-239">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="2971a-240">根據公司的商務/公司原則設定您的租使用者</span><span class="sxs-lookup"><span data-stu-id="2971a-240">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="2971a-241">管理組織的 Microsoft Teams 設定</span><span class="sxs-lookup"><span data-stu-id="2971a-241">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="2971a-242">部署團隊用戶端</span><span class="sxs-lookup"><span data-stu-id="2971a-242">Deploy the Teams client</span></span>  
    [<span data-ttu-id="2971a-243">取得 Teams 用戶端</span><span class="sxs-lookup"><span data-stu-id="2971a-243">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="2971a-244">推動您的採納計畫</span><span class="sxs-lookup"><span data-stu-id="2971a-244">Drive your adoption program</span></span>  
    [<span data-ttu-id="2971a-245">採納 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="2971a-245">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)<br/>
    [<span data-ttu-id="2971a-246">Microsoft 團隊採用快速入門檢查清單</span><span class="sxs-lookup"><span data-stu-id="2971a-246">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="2971a-247">開始規劃將其他工作負載移至 Office 365</span><span class="sxs-lookup"><span data-stu-id="2971a-247">Begin planning moving other workloads to Office 365</span></span>

7.  <span data-ttu-id="2971a-248">建立商務用 Skype 混合式，並遵循針對商務用 Skype 和 Lync server 所建議的升級路徑</span><span class="sxs-lookup"><span data-stu-id="2971a-248">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="2971a-249">從商務用 Skype 內部部署升級至團隊</span><span class="sxs-lookup"><span data-stu-id="2971a-249">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="2971a-250">落款語句</span><span class="sxs-lookup"><span data-stu-id="2971a-250">Closing statement</span></span>

<span data-ttu-id="2971a-251">Microsoft 團隊可以是您組織的啟用程式，將所有員工、資訊工作者及第一線員工工作人員放在單一平臺上。</span><span class="sxs-lookup"><span data-stu-id="2971a-251">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Firstline workers, together on a single platform.</span></span> <span data-ttu-id="2971a-252">您現在可以[開始](https://products.office.com/microsoft-teams/group-chat-software)使用。</span><span class="sxs-lookup"><span data-stu-id="2971a-252">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="2971a-253">您可以在[這裡](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)與所有最新的宣告及每月產品更新保持聯繫。</span><span class="sxs-lookup"><span data-stu-id="2971a-253">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="2971a-254">此外，隨著世界各地的公司所管理的是目前的 COVID-19，我們已建立一系列的內容，協助您利用團隊來取得貴組織的最大影響。</span><span class="sxs-lookup"><span data-stu-id="2971a-254">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="2971a-255">我們[在 COVID 期間對客戶的承諾-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span><span class="sxs-lookup"><span data-stu-id="2971a-255">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="2971a-256">2周內：我們已瞭解遠端作業的相關資訊</span><span class="sxs-lookup"><span data-stu-id="2971a-256">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="2971a-257">傳送線上會議與活動</span><span class="sxs-lookup"><span data-stu-id="2971a-257">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - <span data-ttu-id="2971a-258">[協助中小型企業能夠使用 Teams 遠端工作](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/) (英文)</span><span class="sxs-lookup"><span data-stu-id="2971a-258">[Helping small and medium-sized businesses work remotely with Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)</span></span>

  - [<span data-ttu-id="2971a-259">即時事件的數位轉換：王俊元從第一線 Bejan 的觀測值</span><span class="sxs-lookup"><span data-stu-id="2971a-259">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - <span data-ttu-id="2971a-260">[Microsoft IT 為其員工啟用遠端作業的最熱門 9 種方式](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/) (英文)</span><span class="sxs-lookup"><span data-stu-id="2971a-260">[The top 9 ways Microsoft IT is enabling remote work for its employees](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)</span></span>

  - [<span data-ttu-id="2971a-261">遠端工作、保持安全（CISOs 的秘訣）</span><span class="sxs-lookup"><span data-stu-id="2971a-261">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="2971a-262">協助教師與學生進行遠端學習</span><span class="sxs-lookup"><span data-stu-id="2971a-262">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="2971a-263">使用 Microsoft 團隊進行遠端作業時保持生產力</span><span class="sxs-lookup"><span data-stu-id="2971a-263">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="2971a-264">支援服務參考</span><span class="sxs-lookup"><span data-stu-id="2971a-264">Support Services reference</span></span>

<span data-ttu-id="2971a-265">團隊依賴 Exchange Online、SharePoint Online、商務用 OneDrive 和 Microsoft 365 群組，為您的使用者提供完全整合的 Office 365 體驗。</span><span class="sxs-lookup"><span data-stu-id="2971a-265">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Office 365 experience.</span></span> <span data-ttu-id="2971a-266">如上述所述，小組將能正常運作，而不需全面部署這些服務-並提供有限的功能。</span><span class="sxs-lookup"><span data-stu-id="2971a-266">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="2971a-267">您可以在這裡閱讀更多關於團隊及其必備專案的資訊：[歡迎使用團隊](teams-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="2971a-267">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="2971a-268">如需上述各項服務的詳細資訊，請遵循下列連結：</span><span class="sxs-lookup"><span data-stu-id="2971a-268">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="2971a-269">Exchange Online 用於行事曆功能，並將對等的訊息儲存在團隊中。</span><span class="sxs-lookup"><span data-stu-id="2971a-269">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="2971a-270">若要深入瞭解，請閱讀[Exchange 與團隊互動的方式](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="2971a-270">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2971a-271">針對使用 Exchange 內部部署的團隊互通性，您必須按照 [設定 exchange 與 Exchange Online 組織之間的 OAuth 驗證](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)中所述的方式來設定新的 Exchange OAuth 驗證通訊協定。</span><span class="sxs-lookup"><span data-stu-id="2971a-271">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="2971a-272">SharePoint 是用於頻道中的檔案共用，而商務用/OneDrive 則用於1:1 或群組聊天中的檔案共用。</span><span class="sxs-lookup"><span data-stu-id="2971a-272">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="2971a-273">若要深入瞭解，請參閱[SharePoint Online 與商務用 OneDrive 與 Microsoft 團隊互動的方式](sharepoint-onedrive-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="2971a-273">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="2971a-274">[Microsoft 365 群組](office-365-groups.md)用於小組和通道建立/管理。</span><span class="sxs-lookup"><span data-stu-id="2971a-274">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="2971a-275">相關主題</span><span class="sxs-lookup"><span data-stu-id="2971a-275">Related topics</span></span>

[<span data-ttu-id="2971a-276">Microsoft Teams IT 架構設計人員與電話語音解決方案海報</span><span class="sxs-lookup"><span data-stu-id="2971a-276">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="2971a-277">規劃商務用 Skype Server 和 Office 365 之間的混合式連線</span><span class="sxs-lookup"><span data-stu-id="2971a-277">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="2971a-278">使用團隊支援遠端工作人員</span><span class="sxs-lookup"><span data-stu-id="2971a-278">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="2971a-279">使用 Office 365 遠端作業</span><span class="sxs-lookup"><span data-stu-id="2971a-279">Work remotely with Office 365</span></span>](https://aka.ms/remote-work)
