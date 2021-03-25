---
title: 先推出 Microsoft Teams
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
description: 使用此指南將 Microsoft Teams 推出為您的第一個 Microsoft 365 或 Office 365 工作負載。
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
# <a name="roll-out-microsoft-teams-first"></a>首先推出 Microsoft Teams

Microsoft Teams 可協助員工保持聯繫並彼此共同作業，尤其是在目前前所未有的時間，遠端工作已讓世界各地的員工實作。 在 Teams 中聊天、進行視訊會議，以及共同處理 Office 檔，可協助公司保持生產力。 無論您是小型企業、非營利組織或大型組織，在部署任何其他 Office App 或服務之前，都可以開始使用 Teams 做為 Microsoft 365 或 Office 365 套件內的第一個工作負載。

本文詳細說明您必須使用「Teams 第一」方法進行考慮。

> [!IMPORTANT]
> 雖然 Teams 可以是貴組織第一個雲端部署的工作量，但部署 Teams 應該是您整體雲端部署策略的一部分。

如果您已經推出其他 Microsoft 365 或 Office 365 服務和 Teams 是下一個要推出 (的工作量，而不是第一個) ，請從如何推出 [Teams](./deploy-overview.md)開始。

## <a name="start-here"></a>從這裡開始

若要開始使用 Teams First 部署，您至少必須滿足一些先決條件。 下列清單會顯示在啟用 Teams 之前，貴組織必須擁有的位置：

1.  以您的功能變數名稱配置的 Microsoft 365 或 Office 365 組織

2.  Azure Active Directory (AAD) 或類似的雲端身分識別同步處理解決方案 -所有必要的屬性都與租使用者同步處理  
    若要瞭解與 AAD 同步處理同步處理的屬性，請閱讀[Azure AD Connect 同步處理：同步](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)處理至 Azure Active Directory 的屬性

3.  為 Teams 指派適當的使用者授權  
    若要瞭解 Teams 授權，請閱讀 [Microsoft Teams 服務描述](/office365/servicedescriptions/teams-service-description)。

4.  為 Teams 準備的組織網路  
    若要瞭解網路準備，請參閱 [準備貴組織的](prepare-network.md)Teams 網路。

5.  允許 Microsoft 365 或 Office 365 中的 Exchange、Sharepoint 和商務用 OneDrive 的網路存取權 [：Office 365 URL](/office365/enterprise/urls-and-ip-address-ranges)和 IP 位址範圍 。

> [!NOTE]
> 在 2019 年 9 月 1 日之後建立租使用者會以 Teams Only 模式進行配置。
> 
> [!IMPORTANT]
> 如果您部署商務用 Skype Server，且您的租使用者是在 2019 年 9 月 1 日之後部署，請聯絡支援人員，為 Teams 啟用共存功能。 將任何 Teams 授權指派給使用者之前，請確定您的'全組織<span class="underline"></span>升級政策'已設定為'島模式」。

## <a name="migration-starting-points"></a>移移起點

您前往 Microsoft 365 或 Office 365 以及 Teams 中可用的功能，取決於您的起點，以及內部部署商務用 Skype 或 Lync 伺服器的存在。 下列各節將詳述基本功能和組組選項，以及上述先決條件。 我們已將起點案例細分為下列主題：

**租使用者團隊組** 態：租使用者和使用者模式是用來控制收件者的行為。 這些設定可以在租使用者層級或組織的使用者層級指派。 若要深入瞭解，請參閱 [使用商務](coexistence-chat-calls-presence.md)用 Skype 共存。

**Teams 中的聊天/** 外部通訊：聊天服務是指與組織內部或組織外部的對等或群組聊天交談。 外部通訊也稱為商務用 Skype 中的聯合。

**在 Teams** 中建立和查看會議：使用者一旦獲得授權，隨時都可以透過 Outlook Teams 附加元件建立線上會議，而且 PSTN 撥入功能可在所有情況下使用。 Teams 和商務用 Skype 會儲存使用者的 Exchange 信箱中的日曆資訊。 內部部署 Exchange 伺服器必須是 Exchange Server 2016 CU3 或以上，Teams 用戶端才能與使用者的信箱互動。 沒有 Exchange 信箱存取，Teams 中的日曆圖示將不會顯示，使用者將無法在 Teams 用戶端中查看、建立或修改會議。

**Teams 中的通話功能 VoIP/ PSTN：** 通話可以是語音語音 (VoIP) 或公用交換電話網絡 (PSTN) 。 VoIP 連接在 Teams 用戶端之間原生髮生，而 PSTN 連接則發生在使用者撥打外部電話號碼時。  

Teams 支援兩種類型的 PSTN 連接。 Microsoft 通話方案：當 Microsoft 提供電話基礎結構 ，包括使用者的電話號碼或直接路由組式時，客戶會以會話邊界控制器 (SBC) 為 Teams 使用者提供電話連接。  
若要深入瞭解，請閱讀 [哪一種通話方案適合您？](calling-plan-landing-page.md) 以及 [電話系統直接路由](direct-routing-landing-page.md)。

**Teams 中的團隊和** 頻道共同作業：在 Teams 中，團隊是一群為了工作、專案或共同興趣而彙集在一起的人。 Teams 是由頻道所決定。 每個頻道都是圍繞主題建立，例如「小組活動」、部門名稱，或只是為了好玩。 頻道是您可以召開會議、進行交談，以及共同處理檔案的地方。 在共同合作期間

**商務用 OneDrive (P2P** 檔案共用) 在 Teams 中：在 Teams 和頻道之外，Teams 使用者可以使用商務用 OneDrive 或其他 P2P 共用檔案程式 ，例如 [黃盒檔案、DropBox、Box 和 Google 雲端硬碟等，以對等方式共用檔案。 對於商務用 OneDrive，使用者必須已指派 SharePoint Online 授權。

**應用程式平臺**：應用程式提供開箱即用的工具，讓貴組織從 Teams 中取得更多功能。 這些應用程式結合由 Microsoft、協力廠商或貴組織的開發人員提供的定位停駐點、訊息擴充功能、連接器和 Bot 功能。

**安全性與合規性功能：** Teams 提供各式各樣的資訊，可協助您處理合規性領域，包括保留政策、資料遺失防護 (DLP) 、電子檔探索和頻道、聊天和檔案的法律保留、稽核記錄搜尋。 若要深入瞭解，請參閱 [Microsoft Teams 中的安全性與合規性](security-compliance-overview.md)。  

> [!NOTE]
> 進一步電子探索功能需要 E5 授權。

[比較授權選項](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。

閱讀 [Exchange 與 Microsoft Teams 互動](exchange-teams-interact.md) 的方式，以瞭解您的案例提供哪些合規性功能。

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>沒有 **<span class="underline">商務</span>** 用 Skype 或 Lync Server 的組織

此起點假設您的組織目前並未使用商務用 Skype 或 Lync Server，而 Teams 是 Microsoft 365 或 Office 365 的第一個應用程式。 下表詳細列出 Teams 核心服務的高層級組配置和使用者功能。

<table>
<thead>
<tr class="header">
<th>項目</th>
<th>注釋</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>租使用者團隊組組</td>
<td>只有 Teams 模式，所有聊天和通話功能均在 Teams Only 中。</td>
</tr>
<tr class="even">
<td>Teams 中的聊天/外部通訊</td>
<td><p>內部 (Microsoft 365 或 Office 365 組織內部) Teams 進行外部聊天通訊。</p>
<p><em>注意：DNS 專案必須針對外部存取進行配置。 即使您在內部部署或 Microsoft 365 或 Office 365 中沒有商務用 Skype，也還是需要商務用 Skype DNS 記錄，才能與 Lync 和商務用 Skype 環境進行聯合：<br />
<a href="/office365/enterprise/external-domain-name-system-records">外部網域名稱系統記錄</a></em></p></td>
</tr>
<tr class="odd">
<td>在 Teams 中建立及查看會議</td>
<td><p>能透過 Outlook 附加元件建立內部和外部會議。</p>
<p>PSTN 電話撥入和撥出功能與音訊會議授權一起提供。</p>
<p>Teams 日曆存取需要已建立 Exchange 混合式部署的 Exchange 2016 CU3+ 內部部署：使用混合式組調精靈建立 <a href="/exchange/hybrid-deployment/deploy-hybrid">混合式部署。</a> </p>
<p>除了 Exchange 混合式設定之外，建立 Exchange OAuth 驗證：設定 Exchange 與 Exchange Online 組織之間的 <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> OAuth 驗證」。</p>

</p></td>
</tr>
<tr class="even">
<td>通話功能<br />
Teams 中的 VoIP / PSTN</td>
<td><p>租使用者可在內部和外部使用 VoIP。</p>
<p>PSTN 服務可透過 Microsoft Phone System 進行配置，以及新增 Microsoft 通話方案或直接路由。</p></td>
</tr>
<tr class="odd">
<td>Teams 中的團隊和頻道共同合作</td>
<td><p>若要獲得完整體驗 ，包括合規性功能，必須指派 SharePoint Online 授權給使用者。</p>
<p>不需要移移現有的內部部署 SharePoint 網站。</p></td>
</tr>
<tr class="even">
<td>商務用 OneDrive (P2P 檔案共用) </td>
<td>商務用 OneDrive 需要使用者指派 SharePoint Online 授權。 沒有此授權，將無法進行對等檔案共用。</td>
</tr>
<tr class="odd">
<td>應用程式平臺</td>
<td>使用者將能夠使用根據貴公司政策所指定的應用程式。<br />
深入瞭解 <a href="/microsoftteams/admin-settings">：Teams 中的 App 系統管理設定</a></td>
</tr>
<tr class="even">
<td>安全性與合規性功能</td>
<td><ul>
<li><p>保留政策可供使用。</p></li>
<li><p>支援 eDiscovery 和法律保留功能，以確保頻道訊息的合規性。</p></li>
<li><p>資料外遺失防護 (DLP) 可用。</p></li>
</ul>
<p>Exchange Online 提供的完整功能集;Exchange 內部部署支援大部分的功能。 有關完整清單，請參閱 <a href="/MicrosoftTeams/exchange-teams-interact">Exchange 與 Teams 互動的方式</a>。</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>針對沒有商務用 Skype 或 Lync Server 的組織啟用步驟

1.  符合上述開始這裡區段詳述的先決條件

2.  將租使用者切換成僅適用于現有租 (的 Teams 模式) ： [設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)。

3.  根據貴公司的企業/公司政策設定您的租使用者： [管理貴](enable-features-office-365.md)組織的 Microsoft Teams 設定。

4.  將 Teams 用戶端部署到您的使用者： [取得 Teams 的用戶端](get-clients.md)

5.  推動您的採用計畫  
    [採用 Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Microsoft Teams 採用快速入門檢查清單](teams-adoption-quick-start-checklist.md)

6.  開始規劃將其他工作負載移往 Microsoft 365 或 Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>使用 **<span class="underline">商務</span>** 用 Skype 或 Lync 伺服器的組織

此起點假設您的組織在內部部署使用商務用 Skype 2019 或 2015+ 或 Lync 2013+ 伺服器。 我們已針對組織從內部部署伺服器移向 Teams 提供廣泛指引，這些案例應該會遵循。 此指南是 Microsoft 365 或 Office 365 中您第一次使用 Teams 時所特有的案例。 下表詳細列出 Teams 核心服務的高層級組配置和使用者功能。

<table>
<thead>
<tr class="header">
<th>項目</th>
<th>注釋</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>租使用者團隊組組</td>
<td>群島模式。</td>
</tr>
<tr class="even">
<td>Teams 中的聊天/外部通訊</td>
<td>只有在您自己的租使用者內部，外部通訊 (聯) 會透過商務用 Skype 或 Lync 伺服器部署進行。</td>
</tr>
<tr class="odd">
<td>在 Teams 中建立及查看會議</td>
<td><p>能透過 Outlook 附加元件建立內部和外部會議。</p>
<p>PSTN 電話撥入和撥出功能與音訊會議授權一起提供。</p>
<p>Teams 日曆存取需要部署 Exchange 混合式部署的 Exchange 2016 CU3+ 內部部署：<br />
<a href="/exchange/hybrid-deployment/deploy-hybrid">使用混合式群組原則建立混合式部署。</a></p>
<p>系統管理員可以透過 Teams 會議策略的 PreferredMeetingProviderForIslandsMode 屬性控制商務用 Skype Outlook 附加<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> 元件：set-csteamsmeetingpolicy</a>。</p> 
</td>
</tr>
<tr class="even">
<td>通話功能<br />
Teams 中的 VoIP / PSTN</td>
<td><p>可在租使用者內部使用 VoIP。</p>
<p>在將使用者移至 Teams Only 體驗之前，PSTN 或通話方案服務無法提供。</p></td>
</tr>
<tr class="odd">
<td>Teams 中的團隊和頻道共同合作</td>
<td><p>若要獲得完整體驗 ，包括合規性功能，必須指派 SharePoint Online 授權給使用者。</p>
<p>不需要移移現有的內部部署 SharePoint 網站。</p></td>
</tr>
<tr class="even">
<td>商務用 OneDrive (P2P 檔案共用) </td>
<td>商務用 OneDrive 需要使用者指派 SharePoint Online 授權。 沒有此授權，無法進行每對對等檔案共用。</td>
</tr>
<tr class="odd">
<td>應用程式平臺</td>
<td>使用者將能夠使用根據貴公司政策所指定的應用程式。<br />
深入瞭解 <a href="/microsoftteams/admin-settings">：Teams 中的 App 系統管理設定</a></td>
</tr>
<tr class="even">
<td>安全性與合規性功能</td>
<td><ul>
<li><p>保留政策可供使用。</p></li>
<li><p>支援 eDiscovery 和法律保留功能，以確保頻道訊息的合規性。</p></li>
<li><p>資料外遺失防護 (DLP) 可用。</p></li>
</ul>
<p>Exchange Online 提供的完整功能集;Exchange 內部部署支援大部分的功能。 有關完整清單，請參閱 <a href="/MicrosoftTeams/exchange-teams-interact">Exchange 與 Teams 互動的方式。</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>使用商務用 Skype Server 的組織啟用步驟  

1.  符合上述 <從這裡開始> 一節中詳述的先決條件。

2.  針對 2019/9/1 (租使用者，請將租使用者切換為群島模式，請與支援人員聯繫，)   
    [設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)

3.  根據貴公司的企業/公司政策設定租使用者  
    [管理組織的 Microsoft Teams 設定](enable-features-office-365.md)

4.  部署 Teams 用戶端  
    [取得 Teams 用戶端](get-clients.md)

5.   推動您的採用計畫  
    [採用 Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Microsoft Teams 採用快速入門檢查清單](teams-adoption-quick-start-checklist.md)

6.  開始規劃將其他工作負載移往 Microsoft 365 或 Office 365

7.  建立商務用 Skype 混合式，並遵循商務用 Skype 和 Lync 伺服器的建議升級路徑  
    [從商務用 Skype 內部部署升級至 Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>結束語句

Microsoft Teams 可以是貴組織在單一平臺上將所有員工、資訊工作者和前線工作人員彙集在一起的啟用器。 您 [今天就可以開始使用](https://products.office.com/microsoft-teams/group-chat-software) 。 您可以在這裡與我們所有的最新公告和每月產品更新 [保持聯繫](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)。

此外，由於世界各地的公司正在管理目前的 COVID-19 情況，我們建立了一系列內容，可協助您將 Teams 運用到組織中的最大影響。

  - 我們在[COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)期間與客戶的承諾

  - [2 周後：我們已瞭解遠端工作](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [提供線上會議和活動](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [協助中小型企業能夠使用 Teams 遠端工作](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [即時活動的數位轉換：Bob Bejan 從前線觀察](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Microsoft IT 為其員工啟用遠端作業的最熱門 9 種方式](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/) (英文)

  - [遠端工作、保持安全 —適用于CISOS 的秘訣](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [協助教師和學生切換到遠端學習](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [在遠端使用 Microsoft Teams 時保持生產力](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>支援服務參考

Teams 仰賴 Exchange Online、SharePoint Online、商務用 OneDrive 和 Microsoft 365 群組，為使用者提供完全整合的 Microsoft 365 或 Office 365 體驗。 如上所述，Teams 在未完整部署這些服務的情況下，將會使用有限的功能。 您可以在這裡閱讀有關 Teams 及其先決條件的更多資訊： [歡迎使用 Teams](teams-overview.md)。

如需上述每項服務的詳細資訊，請遵循下列連結：

  - Exchange Online 可用於在 Teams 中建立日曆功能，以及儲存對等郵件。 若要深入瞭解，請參閱 [Exchange 與 Teams 互動的方式](exchange-teams-interact.md)

> [!IMPORTANT]
> 針對 Teams 與 Exchange 內部部署之間的交互操作，您必須設定新的 Exchange OAuth 驗證通訊協定，如在 Exchange 和 Exchange Online 組織之間設定 [OAuth 驗證](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)中所述。

  - SharePoint 用於頻道中的檔案共用，而商務用 /OneDrive 則用於 1：1 或群組聊天中的檔案共用。 若要深入瞭解，請參閱 [SharePoint Online](sharepoint-onedrive-interact.md)和商務用 OneDrive 如何與 Microsoft Teams 互動。

  - [Microsoft 365 群組](office-365-groups.md) 用於團隊和頻道建立/管理。


## <a name="related-topics"></a>相關主題

[Microsoft Teams IT 架構設計人員與電話語音解決方案海報](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[規劃商務用 Skype Server 和 Office 365 之間的混合式連線](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[使用 Teams 支援遠端工作人員](support-remote-work-with-teams.md)

[使用 Microsoft 365 進行遠端工作](https://aka.ms/remote-work)