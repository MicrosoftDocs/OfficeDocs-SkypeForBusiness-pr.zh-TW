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
description: 使用本指導方針將 Microsoft 團隊作為您的第一份 Microsoft 365 或 Office 365 工作負載來推出。
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: a30d5bed9443df3077ab7384cd8266d2f049148d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909477"
---
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="9f009-103">先推出 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="9f009-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="9f009-104">Microsoft 團隊可以協助您的員工彼此保持聯繫並共同作業，特別是在目前空前的時間裡，我們的遠端工作是世界各地員工的實際員工。</span><span class="sxs-lookup"><span data-stu-id="9f009-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="9f009-105">在團隊中，您可以在 Office 檔上進行聊天、進行影片會議與共同作業，協助公司維持生產力。</span><span class="sxs-lookup"><span data-stu-id="9f009-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="9f009-106">無論您是小型企業、非盈利性或大型組織，您都可以在部署任何其他 Office app 或服務之前，先開始將團隊做為 Microsoft 365 或 Office 365 套件中的第一個工作負載。</span><span class="sxs-lookup"><span data-stu-id="9f009-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Microsoft 365 or Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="9f009-107">本文詳細說明您必須使用「團隊優先」做法所做的考慮。</span><span class="sxs-lookup"><span data-stu-id="9f009-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f009-108">當團隊可以是貴組織的第一個雲端部署工作負載時，部署團隊應該是整個雲端部署策略的一部分。</span><span class="sxs-lookup"><span data-stu-id="9f009-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="9f009-109">如果您已推出其他 Microsoft 365 或 Office 365 服務，且小組是您下次要 (推出的工作負載，而不是第一個) ，請從 [如何推出團隊](How-to-roll-out-teams.md)開始。</span><span class="sxs-lookup"><span data-stu-id="9f009-109">If you have already rolled out other Microsoft 365 or Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out Teams](How-to-roll-out-teams.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="9f009-110">從這裡開始</span><span class="sxs-lookup"><span data-stu-id="9f009-110">Start here</span></span>

<span data-ttu-id="9f009-111">若要開始使用您的小組第一次部署，您必須至少滿足一些必備元件。</span><span class="sxs-lookup"><span data-stu-id="9f009-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="9f009-112">下列清單會顯示您在啟用團隊之前必須針對貴組織進行的動作：</span><span class="sxs-lookup"><span data-stu-id="9f009-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="9f009-113">使用您的功能變數名稱設定的 Microsoft 365 或 Office 365 組織</span><span class="sxs-lookup"><span data-stu-id="9f009-113">A Microsoft 365 or Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="9f009-114">Azure Active Directory 連線 (AAD connect) 或類似的雲端身分識別同步處理方案，包括與您的租使用者同步處理的所有必要屬性</span><span class="sxs-lookup"><span data-stu-id="9f009-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="9f009-115">若要瞭解與 AAD 同步處理的屬性，請閱讀 [AZURE AD Connect 同步處理：屬性已同步處理到 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span><span class="sxs-lookup"><span data-stu-id="9f009-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="9f009-116">指派給小組的適當使用者授權</span><span class="sxs-lookup"><span data-stu-id="9f009-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="9f009-117">若要瞭解團隊授權，請參閱 [Microsoft 團隊服務說明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="9f009-117">To understand Teams licensing, read [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

4.  <span data-ttu-id="9f009-118">組織為團隊準備的網路</span><span class="sxs-lookup"><span data-stu-id="9f009-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="9f009-119">若要瞭解網路準備，請閱讀 [針對團隊準備貴組織的網路](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="9f009-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="9f009-120">在 Microsoft 365 或 Office 365 中允許網路存取 Exchange、Sharepoint 和商務用 OneDrive： [office 365 url 與 IP 位址範圍](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="9f009-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Microsoft 365 or Office 365: [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="9f009-121">在2019年9月1日之後建立的租使用者僅限 [小組] 模式提供。</span><span class="sxs-lookup"><span data-stu-id="9f009-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="9f009-122">如果您已部署商務用 Skype Server 且您的租使用者已于2019年9月1日之後預配，請聯絡支援人員來啟用團隊的共存功能。</span><span class="sxs-lookup"><span data-stu-id="9f009-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="9f009-123">將任何團隊授權指派給使用者 <span class="underline">之前</span> ，請確定您的 [組織範圍升級原則] 已設定為 [孤島模式]。</span><span class="sxs-lookup"><span data-stu-id="9f009-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="9f009-124">遷移開始點</span><span class="sxs-lookup"><span data-stu-id="9f009-124">Migration Starting points</span></span>

<span data-ttu-id="9f009-125">您在 Microsoft 365 或 Office 365 中的旅程，以及小組中提供的功能，取決於您的起點，以及現有的內部部署商務用 Skype 或 Lync server。</span><span class="sxs-lookup"><span data-stu-id="9f009-125">Your journey to Microsoft 365 or Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="9f009-126">除了上述必備元件之外，下列各節將詳細說明基本功能和配置選項。</span><span class="sxs-lookup"><span data-stu-id="9f009-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="9f009-127">我們已將起點案例分解成下列主題：</span><span class="sxs-lookup"><span data-stu-id="9f009-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="9f009-128">**租使用者小組** 設定：租使用者和使用者模式是用來控制收件者的行為。</span><span class="sxs-lookup"><span data-stu-id="9f009-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="9f009-129">您可以在租使用者層級或組織中的使用者層級指派這些設定。</span><span class="sxs-lookup"><span data-stu-id="9f009-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="9f009-130">若要深入瞭解，請參閱 [與商務用 Skype 共存](coexistence-chat-calls-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="9f009-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="9f009-131">**團隊中的聊天/外部通訊**：聊天服務會參照對等與組織內或外部的對等或群組聊天交談。</span><span class="sxs-lookup"><span data-stu-id="9f009-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="9f009-132">外部通訊也稱為商務用 Skype 中的同盟。</span><span class="sxs-lookup"><span data-stu-id="9f009-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="9f009-133">**在團隊中建立及查看會議**：使用者隨時都可以透過 Outlook 團隊增益集和 PSTN 撥入來建立線上會議（在使用者獲得授權後，所有案例都會提供）。</span><span class="sxs-lookup"><span data-stu-id="9f009-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="9f009-134">[小組] 和 [商務用 Skype] 會在使用者的 Exchange 信箱中儲存行事曆資訊。</span><span class="sxs-lookup"><span data-stu-id="9f009-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="9f009-135">在內部部署 Exchange server 必須是 Exchange Server 2016 CU3 或更新版本，小組用戶端才能與使用者的信箱互動。</span><span class="sxs-lookup"><span data-stu-id="9f009-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="9f009-136">若沒有 Exchange 信箱存取，小組中的行事曆圖示就不會出現，而且使用者將無法在團隊用戶端中查看、建立或修改會議。</span><span class="sxs-lookup"><span data-stu-id="9f009-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="9f009-137">**在團隊中通話功能 voip/PSTN**：通話可以是經由 IP 語音 (VoIP) 或公開交換電話網絡 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="9f009-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="9f009-138">VoIP 連線會在團隊用戶端之間固有進行，而 PSTN 連線則會在使用者撥打外線連線號碼時發生。</span><span class="sxs-lookup"><span data-stu-id="9f009-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="9f009-139">團隊支援兩種類型的 PSTN 連線。</span><span class="sxs-lookup"><span data-stu-id="9f009-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="9f009-140">Microsoft 通話方案： Microsoft 提供電話結構，包括使用者的電話號碼，或直接路由設定，客戶可以在其中為團隊使用者提供電話語音連線 (SBC) 。</span><span class="sxs-lookup"><span data-stu-id="9f009-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="9f009-141">若要深入瞭解，請閱讀適合 [您的通話方案](calling-plan-landing-page.md) ，以及 [電話系統直接路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="9f009-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="9f009-142">團隊中的 **團隊和頻道** 共同作業：團隊中的團隊是共同作業、專案或共同興趣的人員群組。</span><span class="sxs-lookup"><span data-stu-id="9f009-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="9f009-143">團隊是由頻道組成。</span><span class="sxs-lookup"><span data-stu-id="9f009-143">Teams are made up of channels.</span></span> <span data-ttu-id="9f009-144">每個頻道都是圍繞主題建立，例如「團隊活動」、部門名稱或只是有趣的。</span><span class="sxs-lookup"><span data-stu-id="9f009-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="9f009-145">頻道是您在其中召開會議、進行交談及共同處理檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="9f009-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="9f009-146">在共同作業期間</span><span class="sxs-lookup"><span data-stu-id="9f009-146">During collaboration</span></span>

<span data-ttu-id="9f009-147">**小組中的商務用 onedrive (P2P 檔案) 共用**：團隊和頻道以外的團隊使用者可以使用商務用 OneDrive 或其他 P2P 共用檔案程式（例如 Citrix 檔案、DropBox、Box 和 Google 雲端硬碟）來共用檔案對等。</span><span class="sxs-lookup"><span data-stu-id="9f009-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="9f009-148">針對商務用 OneDrive，使用者必須已指派 SharePoint Online 授權。</span><span class="sxs-lookup"><span data-stu-id="9f009-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="9f009-149">**應用程式平臺**： app 提供現成的工具供貴組織用來充分發揮團隊的效用。</span><span class="sxs-lookup"><span data-stu-id="9f009-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="9f009-150">這些 app 結合由 Microsoft （由協力廠商或由貴組織的開發人員建立）所提供的索引標籤、訊息擴充、連接器和 bot 功能。</span><span class="sxs-lookup"><span data-stu-id="9f009-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="9f009-151">**安全性與合規性功能：** 小組提供大量的資訊，可協助您處理合規性區域，包括保留原則、資料遺失保護 (DLP) 、eDiscovery 和法律封存等頻道、聊天及檔案、審核記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="9f009-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="9f009-152">若要深入瞭解，請參閱 [Microsoft 團隊中的安全性與合規性](security-compliance-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="9f009-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="9f009-153">預先探索的 eDiscovery 功能需要 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="9f009-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="9f009-154">[比較授權選項](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。</span><span class="sxs-lookup"><span data-stu-id="9f009-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="9f009-155">閱讀 [Exchange 與 Microsoft 團隊如何互動](exchange-teams-interact.md) ，瞭解您的案例中提供哪些規範功能。</span><span class="sxs-lookup"><span data-stu-id="9f009-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="9f009-156">**<span class="underline">沒有</span>** 商務用 Skype 或 Lync Server 的組織</span><span class="sxs-lookup"><span data-stu-id="9f009-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync Server</span></span>

<span data-ttu-id="9f009-157">這個起點假設貴組織不使用商務用 Skype 或 Lync Server，目前與團隊將是您在 Microsoft 365 或 Office 365 中的第一個應用程式。</span><span class="sxs-lookup"><span data-stu-id="9f009-157">This starting point assumes that your organization does not utilize Skype for Business or Lync Server currently and Teams will be your first application in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="9f009-158">下表詳細說明適用于核心服務之團隊的高層次設定和使用者功能。</span><span class="sxs-lookup"><span data-stu-id="9f009-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="9f009-159">項目</span><span class="sxs-lookup"><span data-stu-id="9f009-159">Item</span></span></th>
<th><span data-ttu-id="9f009-160">注釋</span><span class="sxs-lookup"><span data-stu-id="9f009-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9f009-161">租使用者小組配置</span><span class="sxs-lookup"><span data-stu-id="9f009-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="9f009-162">[僅限團隊] 模式，所有聊天和通話功能只適用于團隊中。</span><span class="sxs-lookup"><span data-stu-id="9f009-162">Teams Only mode, all chat and calling features are in Teams Only.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f009-163">團隊中的聊天/外部通訊</span><span class="sxs-lookup"><span data-stu-id="9f009-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="9f009-164">在 Microsoft 365 或 Office 365 組織內部 () 與團隊間可能的外部聊天通訊。</span><span class="sxs-lookup"><span data-stu-id="9f009-164">Internal (intra Microsoft 365 or Office 365 organization) and external chat communication possible from Teams.</span></span></p>
<p><span data-ttu-id="9f009-165"><em>注意： DNS 專案必須針對外部存取進行設定。</span><span class="sxs-lookup"><span data-stu-id="9f009-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="9f009-166">您也可以使用商務用 skype DNS 記錄，即使您沒有商務用 skype 內部部署，或是在 Microsoft 365 或 Office 365 中，允許與 Lync 和商務用 Skype 環境進行聯盟：</span><span class="sxs-lookup"><span data-stu-id="9f009-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises, or in Microsoft 365 or Office 365, to allow federation with Lync and Skype for Business environments:</span></span><br /><span data-ttu-id="9f009-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">外部網域名稱系統記錄</a></em></span><span class="sxs-lookup"><span data-stu-id="9f009-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">External Domain Name System records</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9f009-168">在團隊中建立及查看會議</span><span class="sxs-lookup"><span data-stu-id="9f009-168">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="9f009-169">可透過 Outlook 增益集建立內部和外部會議。</span><span class="sxs-lookup"><span data-stu-id="9f009-169">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="9f009-170">支援 PSTN 撥入和撥出功能（含音訊會議授權）。</span><span class="sxs-lookup"><span data-stu-id="9f009-170">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="9f009-171">團隊行事曆存取需要已建立 exchange 2016 CU3 + 內部部署的 exchange：<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">使用混合</a>式設定向導來建立混合式部署。 </span><span class="sxs-lookup"><span data-stu-id="9f009-171">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a> </span></span></p>
<p><span data-ttu-id="9f009-172">除了 Exchange 混合式設定之外，請建立 Exchange OAuth 驗證： <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> 設定 exchange 與 Exchange Online 組織之間的 OAuth 驗證。</span><span class="sxs-lookup"><span data-stu-id="9f009-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations".</span></span></p>

</p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f009-173">通話功能</span><span class="sxs-lookup"><span data-stu-id="9f009-173">Calling Features</span></span><br />
<span data-ttu-id="9f009-174">團隊中的 VoIP/PSTN</span><span class="sxs-lookup"><span data-stu-id="9f009-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="9f009-175">可在內部和外部 VoIP 至租使用者。</span><span class="sxs-lookup"><span data-stu-id="9f009-175">VoIP internally and externally to the tenant is available.</span></span></p>
<p><span data-ttu-id="9f009-176">PSTN 服務可以透過 Microsoft Phone System 進行設定，以及新增 Microsoft 通話方案或直接路由。</span><span class="sxs-lookup"><span data-stu-id="9f009-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9f009-177">團隊中的團隊和頻道共同作業</span><span class="sxs-lookup"><span data-stu-id="9f009-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="9f009-178">如需全面體驗（包括規範功能），必須將 SharePoint Online 授權指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="9f009-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="9f009-179">不需要遷移現有的內部部署 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="9f009-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f009-180">商務用 OneDrive (P2P 檔案共用) </span><span class="sxs-lookup"><span data-stu-id="9f009-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="9f009-181">商務用 OneDrive 需要有指派 SharePoint Online 授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="9f009-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="9f009-182">如果沒有這個授權對等檔案共用，就不可能了。</span><span class="sxs-lookup"><span data-stu-id="9f009-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9f009-183">應用程式平臺</span><span class="sxs-lookup"><span data-stu-id="9f009-183">Application platform</span></span></td>
<td><span data-ttu-id="9f009-184">使用者將能夠根據您的公司原則，使用指派給他們的 app。</span><span class="sxs-lookup"><span data-stu-id="9f009-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="9f009-185">深入瞭解： <a href="https://docs.microsoft.com/microsoftteams/admin-settings">在團隊中應用程式的系統管理設定</a></span><span class="sxs-lookup"><span data-stu-id="9f009-185">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f009-186">安全性與合規性功能</span><span class="sxs-lookup"><span data-stu-id="9f009-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="9f009-187">保留原則可供使用。</span><span class="sxs-lookup"><span data-stu-id="9f009-187">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="9f009-188">支援針對通道訊息的規範進行 eDiscovery 和法律封存。</span><span class="sxs-lookup"><span data-stu-id="9f009-188">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="9f009-189">您可以使用 (DLP) 的資料遺失防護原則。</span><span class="sxs-lookup"><span data-stu-id="9f009-189">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="9f009-190">Exchange Online 提供完整的功能集;Exchange 內部部署支援這些功能中的大部分。</span><span class="sxs-lookup"><span data-stu-id="9f009-190">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="9f009-191">如需完整清單，請參閱 <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Exchange 與團隊如何互動</a>。</span><span class="sxs-lookup"><span data-stu-id="9f009-191">For a full list, see <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a>.</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="9f009-192">沒有商務用 Skype 或 Lync Server 的組織啟用步驟</span><span class="sxs-lookup"><span data-stu-id="9f009-192">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="9f009-193">在上方的 [從這裡開始] 區段中，符合先決條件的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="9f009-193">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="9f009-194">只有) [設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)時，才會將租使用者切換到 [僅限 (的使用者] 模式。</span><span class="sxs-lookup"><span data-stu-id="9f009-194">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="9f009-195">依照貴公司的商務/公司原則來設定您的租使用者： [管理貴組織的 Microsoft 團隊設定](enable-features-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="9f009-195">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="9f009-196">將團隊用戶端部署至您的使用者： [取得團隊用戶端](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="9f009-196">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="9f009-197">推動您的採納計畫</span><span class="sxs-lookup"><span data-stu-id="9f009-197">Drive your adoption program</span></span>  
    [<span data-ttu-id="9f009-198">採納 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="9f009-198">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="9f009-199">Microsoft 團隊採用快速入門檢查清單</span><span class="sxs-lookup"><span data-stu-id="9f009-199">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="9f009-200">開始規劃將其他工作負載移至 Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="9f009-200">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="9f009-201">**<span class="underline">擁有商務用</span>** Skype 或 Lync server 的組織</span><span class="sxs-lookup"><span data-stu-id="9f009-201">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="9f009-202">這個起點假設您的組織使用商務用 Skype 2019 或 2015 + 或 Lync 2013 + 伺服器內部部署。</span><span class="sxs-lookup"><span data-stu-id="9f009-202">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="9f009-203">我們已經有許多從內部部署伺服器遷移至小組的組織的指導方針，而且應該遵循這些案例。</span><span class="sxs-lookup"><span data-stu-id="9f009-203">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="9f009-204">本指南專為團隊是您在 Microsoft 365 或 Office 365 中所使用的第一個應用程式的案例所特有。</span><span class="sxs-lookup"><span data-stu-id="9f009-204">This guidance is specific to the scenario that Teams is the first application you utilize in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="9f009-205">下表詳細說明適用于核心服務之團隊的高層次設定和使用者功能。</span><span class="sxs-lookup"><span data-stu-id="9f009-205">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="9f009-206">項目</span><span class="sxs-lookup"><span data-stu-id="9f009-206">Item</span></span></th>
<th><span data-ttu-id="9f009-207">注釋</span><span class="sxs-lookup"><span data-stu-id="9f009-207">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9f009-208">租使用者小組配置</span><span class="sxs-lookup"><span data-stu-id="9f009-208">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="9f009-209">孤島模式。</span><span class="sxs-lookup"><span data-stu-id="9f009-209">Islands mode.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f009-210">團隊中的聊天/外部通訊</span><span class="sxs-lookup"><span data-stu-id="9f009-210">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="9f009-211">在您自己的租使用者內部，外部通訊 (同盟) 是透過您的商務用 Skype 或 Lync server 部署。</span><span class="sxs-lookup"><span data-stu-id="9f009-211">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9f009-212">在團隊中建立及查看會議</span><span class="sxs-lookup"><span data-stu-id="9f009-212">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="9f009-213">可透過 Outlook 增益集建立內部和外部會議。</span><span class="sxs-lookup"><span data-stu-id="9f009-213">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="9f009-214">支援 PSTN 撥入和撥出功能（含音訊會議授權）。</span><span class="sxs-lookup"><span data-stu-id="9f009-214">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="9f009-215">團隊行事曆存取需要 exchange 2016 CU3 + 內部部署，且已建立 Exchange 混合式部署：</span><span class="sxs-lookup"><span data-stu-id="9f009-215">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="9f009-216">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">使用混合式設定精靈建立混合式部署。</a></span><span class="sxs-lookup"><span data-stu-id="9f009-216">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a></span></span></p>
<p><span data-ttu-id="9f009-217">系統管理員可以透過團隊會議原則的 PreferredMeetingProviderForIslandsMode 屬性來控制商務用 Skype Outlook 增益集：<a href="https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>。</span><span class="sxs-lookup"><span data-stu-id="9f009-217">Administrator can control the Skype for Business Outlook add-in via the Teams meeting policy’s PreferredMeetingProviderForIslandsMode attribute:<a href="https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</span></span></p> 
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f009-218">通話功能</span><span class="sxs-lookup"><span data-stu-id="9f009-218">Calling Features</span></span><br />
<span data-ttu-id="9f009-219">團隊中的 VoIP/PSTN</span><span class="sxs-lookup"><span data-stu-id="9f009-219">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="9f009-220">提供租使用者內部的 VoIP。</span><span class="sxs-lookup"><span data-stu-id="9f009-220">VoIP internally to the tenant is available.</span></span></p>
<p><span data-ttu-id="9f009-221">PSTN 或通話方案服務無法使用，除非使用者移至 [只有小組] 的體驗。</span><span class="sxs-lookup"><span data-stu-id="9f009-221">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9f009-222">團隊中的團隊和頻道共同作業</span><span class="sxs-lookup"><span data-stu-id="9f009-222">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="9f009-223">如需全面體驗（包括規範功能），必須將 SharePoint Online 授權指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="9f009-223">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="9f009-224">不需要遷移現有的內部部署 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="9f009-224">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f009-225">商務用 OneDrive (P2P 檔案共用) </span><span class="sxs-lookup"><span data-stu-id="9f009-225">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="9f009-226">商務用 OneDrive 需要有指派 SharePoint Online 授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="9f009-226">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="9f009-227">不可能有此授權的每對等檔案共用。</span><span class="sxs-lookup"><span data-stu-id="9f009-227">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="9f009-228">應用程式平臺</span><span class="sxs-lookup"><span data-stu-id="9f009-228">Application platform</span></span></td>
<td><span data-ttu-id="9f009-229">使用者將能夠根據您的公司原則，使用指派給他們的 app。</span><span class="sxs-lookup"><span data-stu-id="9f009-229">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="9f009-230">深入瞭解： <a href="https://docs.microsoft.com/microsoftteams/admin-settings">在團隊中應用程式的系統管理設定</a></span><span class="sxs-lookup"><span data-stu-id="9f009-230">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="9f009-231">安全性與合規性功能</span><span class="sxs-lookup"><span data-stu-id="9f009-231">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="9f009-232">保留原則可供使用。</span><span class="sxs-lookup"><span data-stu-id="9f009-232">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="9f009-233">支援針對通道訊息的規範進行 eDiscovery 和法律封存。</span><span class="sxs-lookup"><span data-stu-id="9f009-233">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="9f009-234">您可以使用 (DLP) 的資料遺失防護原則。</span><span class="sxs-lookup"><span data-stu-id="9f009-234">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="9f009-235">Exchange Online 提供完整的功能集;Exchange 內部部署支援這些功能中的大部分。</span><span class="sxs-lookup"><span data-stu-id="9f009-235">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="9f009-236">如需完整清單，請參閱 <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Exchange 與團隊如何互動。</a></span><span class="sxs-lookup"><span data-stu-id="9f009-236">For a complete list, see <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact.</a></span></span></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="9f009-237">商務用 Skype Server 的組織啟用步驟</span><span class="sxs-lookup"><span data-stu-id="9f009-237">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="9f009-238">符合上述 [從這裡開始] 區段中的先決條件。</span><span class="sxs-lookup"><span data-stu-id="9f009-238">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="9f009-239">在9/1/2019 之後，將租使用者切換至 [孤島模式] (，請與支援人員聯繫，以進行此變更) </span><span class="sxs-lookup"><span data-stu-id="9f009-239">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact support to make this change)</span></span>  
    [<span data-ttu-id="9f009-240">設定您的共存與升級設定</span><span class="sxs-lookup"><span data-stu-id="9f009-240">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="9f009-241">根據公司的商務/公司原則設定您的租使用者</span><span class="sxs-lookup"><span data-stu-id="9f009-241">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="9f009-242">管理組織的 Microsoft Teams 設定</span><span class="sxs-lookup"><span data-stu-id="9f009-242">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="9f009-243">部署團隊用戶端</span><span class="sxs-lookup"><span data-stu-id="9f009-243">Deploy the Teams client</span></span>  
    [<span data-ttu-id="9f009-244">取得 Teams 用戶端</span><span class="sxs-lookup"><span data-stu-id="9f009-244">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="9f009-245">推動您的採納計畫</span><span class="sxs-lookup"><span data-stu-id="9f009-245">Drive your adoption program</span></span>  
    [<span data-ttu-id="9f009-246">採納 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="9f009-246">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)<br/>
    [<span data-ttu-id="9f009-247">Microsoft 團隊採用快速入門檢查清單</span><span class="sxs-lookup"><span data-stu-id="9f009-247">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="9f009-248">開始規劃將其他工作負載移至 Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="9f009-248">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

7.  <span data-ttu-id="9f009-249">建立商務用 Skype 混合式，並遵循針對商務用 Skype 和 Lync server 所建議的升級路徑</span><span class="sxs-lookup"><span data-stu-id="9f009-249">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="9f009-250">從商務用 Skype 內部部署升級至團隊</span><span class="sxs-lookup"><span data-stu-id="9f009-250">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="9f009-251">落款語句</span><span class="sxs-lookup"><span data-stu-id="9f009-251">Closing statement</span></span>

<span data-ttu-id="9f009-252">Microsoft 團隊可以是您組織的啟用程式，將所有員工、資訊工作者及第一線工作人員放在單一平臺上。</span><span class="sxs-lookup"><span data-stu-id="9f009-252">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Frontline workers, together on a single platform.</span></span> <span data-ttu-id="9f009-253">您現在可以 [開始](https://products.office.com/microsoft-teams/group-chat-software) 使用。</span><span class="sxs-lookup"><span data-stu-id="9f009-253">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="9f009-254">您可以在 [這裡](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)與所有最新的宣告及每月產品更新保持聯繫。</span><span class="sxs-lookup"><span data-stu-id="9f009-254">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="9f009-255">此外，隨著世界各地的公司所管理的是目前的 COVID-19，我們已建立一系列的內容，協助您利用團隊來取得貴組織的最大影響。</span><span class="sxs-lookup"><span data-stu-id="9f009-255">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="9f009-256">我們 [在 COVID 期間對客戶的承諾-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span><span class="sxs-lookup"><span data-stu-id="9f009-256">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="9f009-257">2周內：我們已瞭解遠端作業的相關資訊</span><span class="sxs-lookup"><span data-stu-id="9f009-257">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="9f009-258">傳送線上會議與活動</span><span class="sxs-lookup"><span data-stu-id="9f009-258">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - <span data-ttu-id="9f009-259">[協助中小型企業能夠使用 Teams 遠端工作](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/) (英文)</span><span class="sxs-lookup"><span data-stu-id="9f009-259">[Helping small and medium-sized businesses work remotely with Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)</span></span>

  - [<span data-ttu-id="9f009-260">即時事件的數位轉換：王俊元從第一線 Bejan 的觀測值</span><span class="sxs-lookup"><span data-stu-id="9f009-260">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - <span data-ttu-id="9f009-261">[Microsoft IT 為其員工啟用遠端作業的最熱門 9 種方式](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/) (英文)</span><span class="sxs-lookup"><span data-stu-id="9f009-261">[The top 9 ways Microsoft IT is enabling remote work for its employees](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)</span></span>

  - [<span data-ttu-id="9f009-262">遠端工作、保持安全（CISOs 的秘訣）</span><span class="sxs-lookup"><span data-stu-id="9f009-262">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="9f009-263">協助教師與學生進行遠端學習</span><span class="sxs-lookup"><span data-stu-id="9f009-263">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="9f009-264">使用 Microsoft 團隊進行遠端作業時保持生產力</span><span class="sxs-lookup"><span data-stu-id="9f009-264">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="9f009-265">支援服務參考</span><span class="sxs-lookup"><span data-stu-id="9f009-265">Support Services reference</span></span>

<span data-ttu-id="9f009-266">團隊依賴 Exchange Online、SharePoint Online、商務用 OneDrive 和 Microsoft 365 群組，為您的使用者提供完全整合的 Microsoft 365 或 Office 365 體驗。</span><span class="sxs-lookup"><span data-stu-id="9f009-266">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Microsoft 365 or Office 365 experience.</span></span> <span data-ttu-id="9f009-267">如上述所述，小組將能正常運作，而不需全面部署這些服務-並提供有限的功能。</span><span class="sxs-lookup"><span data-stu-id="9f009-267">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="9f009-268">您可以在這裡閱讀更多關於團隊及其必備專案的資訊： [歡迎使用團隊](teams-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="9f009-268">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="9f009-269">如需上述各項服務的詳細資訊，請遵循下列連結：</span><span class="sxs-lookup"><span data-stu-id="9f009-269">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="9f009-270">Exchange Online 用於行事曆功能，並將對等的訊息儲存在團隊中。</span><span class="sxs-lookup"><span data-stu-id="9f009-270">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="9f009-271">若要深入瞭解，請閱讀 [Exchange 與團隊互動的方式](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="9f009-271">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f009-272">針對使用 Exchange 內部部署的團隊互通性，您必須按照 [設定 exchange 與 Exchange Online 組織之間的 OAuth 驗證](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)中所述的方式來設定新的 Exchange OAuth 驗證通訊協定。</span><span class="sxs-lookup"><span data-stu-id="9f009-272">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="9f009-273">SharePoint 是用於頻道中的檔案共用，而商務用/OneDrive 則用於1:1 或群組聊天中的檔案共用。</span><span class="sxs-lookup"><span data-stu-id="9f009-273">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="9f009-274">若要深入瞭解，請參閱 [SharePoint Online 與商務用 OneDrive 與 Microsoft 團隊互動的方式](sharepoint-onedrive-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="9f009-274">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="9f009-275">[Microsoft 365 群組](office-365-groups.md) 用於小組和通道建立/管理。</span><span class="sxs-lookup"><span data-stu-id="9f009-275">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="9f009-276">相關主題</span><span class="sxs-lookup"><span data-stu-id="9f009-276">Related topics</span></span>

[<span data-ttu-id="9f009-277">Microsoft Teams IT 架構設計人員與電話語音解決方案海報</span><span class="sxs-lookup"><span data-stu-id="9f009-277">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="9f009-278">規劃商務用 Skype Server 和 Office 365 之間的混合式連線</span><span class="sxs-lookup"><span data-stu-id="9f009-278">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="9f009-279">使用團隊支援遠端工作人員</span><span class="sxs-lookup"><span data-stu-id="9f009-279">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="9f009-280">使用 Microsoft 365 遠端作業</span><span class="sxs-lookup"><span data-stu-id="9f009-280">Work remotely with Microsoft 365</span></span>](https://aka.ms/remote-work)
