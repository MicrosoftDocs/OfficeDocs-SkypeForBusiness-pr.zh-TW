---
title: Microsoft Teams First 推出
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
ms.localizationpriority: medium
search.appverid: MET150
description: 使用此指導方針將Microsoft Teams作為您的第一個Microsoft 365或Office 365工作負載。
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: f6dba57003aaa58b9d0b72e7e866da261bed578e
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922684"
---
# <a name="roll-out-microsoft-teams-first"></a>Microsoft Teams First 推出

Microsoft Teams可協助您的員工保持聯繫並彼此共同作業，尤其是在目前前所未有的時間，遠端工作是世界各地的員工實境。 能夠在Teams中聊天、進行視訊會議，以及在Office檔上共同作業，有助於公司保持生產力。 無論您是小型企業、非營利組織或大型組織，在部署任何其他Office 應用程式或服務之前，都可以先開始使用Teams做為Microsoft 365或Office 365套件中的第一個工作負載。

本文詳細說明您必須以「Teams第一」方法考慮的事項。

> [!IMPORTANT]
> 雖然Teams可以是貴組織的第一個雲端部署工作負載，但部署Teams應為整體雲端部署策略的一部分。

如果您已經推出其他Microsoft 365或Office 365服務，而Teams是您下一次推行 (的工作量，而不是第一個) ，請從[如何推出Teams](./deploy-overview.md)開始。

## <a name="start-here"></a>從這裡開始

若要開始使用Teams首先部署，您必須至少符合一些先決條件。 下列清單將顯示您在啟用Teams之前必須具備的組織功能：

1.  使用您的功能變數名稱設定的Microsoft 365或Office 365組織

2.  Azure Active Directory連線 (AAD連線) 或類似的雲端身分識別同步處理解決方案 –與您的租使用者同步處理所有必要屬性  
    若要瞭解與AAD同步處理的屬性，請閱讀[Azure AD 連線同步處理：與Azure Active Directory同步的屬性](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

3.  為Teams指派適當的使用者授權  
    若要瞭解Teams授權，請閱讀[Microsoft Teams服務說明](/office365/servicedescriptions/teams-service-description)。

4.  組織網路已針對Teams做好準備  
    若要瞭解網路準備，請閱讀[準備貴組織的網路Teams](prepare-network.md)。

5.  允許網路存取 Microsoft 365 或 Office 365 中的Exchange、SharePoint和商務用 OneDrive：[Office 365 URL 和 IP 位址範圍](/office365/enterprise/urls-and-ip-address-ranges)。

> [!NOTE]
> 在 2019 年 9 月 1 日之後建立的租使用者會以僅Teams模式布建。
> 
> [!IMPORTANT]
> 如果您已部署商務用 Skype Server，而且您的租使用者已于 2019 年 9 月 1 日之後布建，請連絡客戶支援以啟用 Teams 的共存功能。 在指派任何Teams授權給使用者<span class="underline">之前</span>，請先確認您的「全組織升級原則」已設定為「島島模式」。

## <a name="migration-starting-points"></a>移轉起點

根據您的起點和內部部署商務用 Skype或 Lync 伺服器的存在，您在 Teams 中Microsoft 365或Office 365及功能的旅程。 除了上述先決條件之外，下列各節將詳細說明基本功能和組態選項。 我們已將起點案例細分為下列主題：

**租使用者Teams設定**：租使用者和使用者模式是用來控制收件者的行為。 您可以在組織中的租使用者層級或使用者層級上指派這些設定。 若要深入瞭解，請閱讀[與商務用 Skype共存](coexistence-chat-calls-presence.md)。

**聊天/Teams中的外部通訊**：聊天服務是指與組織內部或組織外部的對等或群組聊天交談。 外部通訊在 商務用 Skype 中也稱為同盟。

**在Teams中建立及檢視會議**：一旦授權使用者，使用者隨時可以透過Outlook Teams增益集建立線上會議，且一旦授權使用者，所有案例中皆可使用 PSTN 撥入。 Teams和商務用 Skype將行事曆資訊儲存在使用者的Exchange信箱中。 內部部署Exchange伺服器必須Exchange Server 2016 CU3 或更新版本，Teams用戶端才能與使用者的信箱互動。 若沒有Exchange信箱存取Teams中的行事曆圖示將不會出現，使用者也無法在Teams用戶端中檢視、建立或修改會議。

**Teams 中的通話功能 VoIP / PSTN**：通話可以是透過 IP (VoIP) 或公用交換電話網路 (PSTN) 。 VoIP 連線會在Teams用戶端之間原生髮生，而 PSTN 連線會在使用者撥打外部電話號碼時發生。  

Teams支援兩種類型的 PSTN 連線。 Microsoft 通話方案：當 Microsoft 提供電話語音基礎結構，包括使用者的電話號碼或直接路由設定時，客戶會透過會話框線控制器 (SBC) 為Teams使用者提供電話語音連線。  
若要深入瞭解，請參閱[哪一個通話方案適合您？](calling-plan-landing-page.md)[並電話系統直接路由]](direct-routing-landing-page.md)。

**Teams中的Teams和頻道共同** 作業：在Teams中，團隊是針對工作、專案或共同興趣而聚在一起的一群人。 Teams由頻道組成。 每個頻道都是圍繞著主題而建置，例如「團隊活動」、部門名稱，或只是為了好玩而已。 頻道是您主持會議、進行交談，以及一起處理檔案的地方。 共同作業期間

**在 Teams 中商務用 OneDrive (P2P 檔案共用) ：除了** Teams和通道之外，Teams使用者可以使用商務用 OneDrive 或其他 P2P 共用檔案程式來共用檔案，例如 Citrix 檔案、DropBox、Box 和 Google 雲端硬碟。 對於商務用 OneDrive，使用者必須已指派SharePoint線上授權。

**應用程式平臺**：應用程式提供立即可用的工具，讓貴組織能充分發揮Teams。 這些應用程式結合了 Microsoft、由協力廠商或貴組織開發人員所建置之索引標籤、訊息延伸模組、連接器和 Bot 的功能。

**安全性與合規性功能：** Teams提供各種資訊以協助您處理合規性領域，包括保留原則、資料外泄防護 (DLP) 、頻道的電子檔探索和法律保留、聊天和檔案、稽核記錄搜尋。 若要深入瞭解，請閱讀[Microsoft Teams 中的安全性和合規性](security-compliance-overview.md)。  

> [!NOTE]
> 進階電子檔探索功能需要 E5 授權。

[比較授權選項](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。

請閱讀[Exchange和Microsoft Teams如何互動](exchange-teams-interact.md)，以瞭解案例中提供哪些合規性功能。

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>**<span class="underline">沒有</span>** 商務用 Skype 或 Lync Server 的組織

此起點假設貴組織目前不會使用 商務用 Skype 或 Lync Server，且Teams會是您在 Microsoft 365 或 Office 365 中的第一個應用程式。 下表詳述核心服務Teams的高層級設定和使用者功能。

<table>
<thead>
<tr class="header">
<th>項目</th>
<th>注釋</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>租使用者Teams設定</td>
<td>Teams只有模式，所有聊天和通話功能僅Teams。</td>
</tr>
<tr class="even">
<td>Teams中的聊天/外部通訊</td>
<td><p>內部 (內部Microsoft 365或Office 365組織) 與外部聊天通訊可能來自Teams。</p>
<p><em>注意：必須針對外部存取設定 DNS 專案。 即使您沒有內部部署商務用 Skype，或在Microsoft 365或Office 365中允許與 Lync 和 商務用 Skype 環境建立同盟，也需要商務用 Skype DNS 記錄：<br />
<a href="/office365/enterprise/external-domain-name-system-records">外部網域名稱系統記錄</a></em></p></td>
</tr>
<tr class="odd">
<td>在 Teams 中建立和檢視會議</td>
<td><p>可以透過增益集建立內部和外部會議Outlook。</p>
<p>PSTN 撥入和撥出功能可在音訊會議授權中使用。</p>
<p>Teams行事曆存取需要Exchange 2016 CU3+ 內部部署且已建立Exchange混合式：<a href="/exchange/hybrid-deployment/deploy-hybrid">使用混合式組態精靈建立混合式部署。</a> </p>

除了Exchange混合式設定，請建立 Exchange OAuth 驗證：在[Exchange和Exchange Online組織之間設定 OAuth 驗證](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)。 

</p></td>
</tr>
<tr class="even">
<td>通話功能<br />
Teams 中的 VoIP / PSTN</td>
<td><p>可在租使用者內部和外部使用 VoIP。</p>
<p>PSTN 服務可透過Microsoft 電話系統進行設定，以及新增 Microsoft 通話方案或直接路由。</p></td>
</tr>
<tr class="odd">
<td>Teams 中的Teams與通道共同作業</td>
<td><p>如需完整體驗，包括合規性功能，必須將SharePoint線上授權指派給使用者。</p>
<p>不需要移轉現有的內部部署SharePoint網站。</p></td>
</tr>
<tr class="even">
<td>商務用 OneDrive (P2P 檔案共用) </td>
<td>商務用 OneDrive要求使用者指派SharePoint線上授權。 如果沒有此授權，就無法進行對等檔案共用。</td>
</tr>
<tr class="odd">
<td>應用程式平臺</td>
<td>使用者將能夠根據貴公司的原則，使用指定的應用程式。<br />
在這裡深入瞭解：<a href="/microsoftteams/admin-settings">Teams 中應用程式的</a>系統管理設定</td>
</tr>
<tr class="even">
<td>安全性與合規性功能</td>
<td><ul>
<li><p>您可以使用保留原則。</p></li>
<li><p>支援電子檔探索和頻道訊息合規性的法律保留。</p></li>
<li><p>提供 DLP)  (資料外泄防護原則。</p></li>
</ul>
<p>完整功能集可與 Exchange Online 搭配使用;Exchange內部部署支援這些功能的大部分。 如需完整清單，請參閱<a href="/MicrosoftTeams/exchange-teams-interact">如何Exchange與Teams互動</a>。</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>適用于沒有 商務用 Skype 或 Lync Server 的組織啟用步驟

1.  如需詳細資訊，請參閱上述一節

2.   (現有租使用者將租使用者切換為僅限Teams模式) ：[設定您的共存及升級設定](setting-your-coexistence-and-upgrade-settings.md)。

3.  根據貴公司的商務/公司原則來設定租使用者：[管理貴組織的Microsoft Teams設定](enable-features-office-365.md)。

4.  將Teams用戶端部署到您的使用者：[取得Teams用戶端](get-clients.md)

5.  推動您的採用計畫  
    [採用Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Microsoft Teams採用快速入門檢查清單](teams-adoption-quick-start-checklist.md)

6.  開始規劃將其他工作量移至Microsoft 365或Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>**<span class="underline">擁有 商務用 Skype</span>** 或 Lync 伺服器的組織

這個起點假設貴組織使用內部部署的 商務用 Skype 2019 或 2015+ 或 Lync 2013+ 伺服器。 我們已針對從內部部署伺服器移轉到Teams的組織提供廣泛的指導方針，這些案例應遵循這些指導方針。 本指引是針對您在Microsoft 365或Office 365中使用的第一個應用程式Teams案例所專屬的。 下表詳述核心服務Teams的高層級設定和使用者功能。

<table>
<thead>
<tr class="header">
<th>項目</th>
<th>注釋</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>租使用者Teams設定</td>
<td>[島嶼模式]。</td>
</tr>
<tr class="even">
<td>Teams中的聊天/外部通訊</td>
<td>僅在您自己的租使用者內部，外部通訊 (同盟) 是透過您的商務用 Skype或 Lync 伺服器部署。</td>
</tr>
<tr class="odd">
<td>在 Teams 中建立和檢視會議</td>
<td><p>可以透過增益集建立內部和外部會議Outlook。</p>
<p>PSTN 撥入和撥出功能可在音訊會議授權中使用。</p>
<p>Teams行事曆存取需要Exchange 2016 CU3+ 內部部署，並已建立Exchange混合式：<br />
<a href="/exchange/hybrid-deployment/deploy-hybrid">使用混合式組態精靈建立混合式部署。</a></p>
<p>系統管理員可以透過Teams會議原則的 PreferredMeetingProviderForIslandsMode 屬性來控制商務用 Skype Outlook增益集：<a href="/powershell/module/skype/set-csteamsmeetingpolicy">set-csteamsmeetingpolicy</a>。</p> 
</td>
</tr>
<tr class="even">
<td>通話功能<br />
Teams 中的 VoIP / PSTN</td>
<td><p>我們可在租使用者內部使用 VoIP。</p>
<p>在使用者移至僅Teams體驗之前，PSTN 或通話方案服務無法使用。</p></td>
</tr>
<tr class="odd">
<td>Teams 中的Teams與通道共同作業</td>
<td><p>如需完整體驗，包括合規性功能，必須將SharePoint線上授權指派給使用者。</p>
<p>不需要移轉現有的內部部署SharePoint網站。</p></td>
</tr>
<tr class="even">
<td>商務用 OneDrive (P2P 檔案共用) </td>
<td>商務用 OneDrive要求使用者指派SharePoint線上授權。 若沒有此授權，就無法進行個別檔案共用。</td>
</tr>
<tr class="odd">
<td>應用程式平臺</td>
<td>使用者將能夠根據貴公司的原則，使用指定的應用程式。<br />
在這裡深入瞭解：<a href="/microsoftteams/admin-settings">Teams 中應用程式的</a>系統管理設定</td>
</tr>
<tr class="even">
<td>安全性與合規性功能</td>
<td><ul>
<li><p>您可以使用保留原則。</p></li>
<li><p>支援電子檔探索和頻道訊息合規性的法律保留。</p></li>
<li><p>您可以使用 DLP)  (防止資料外泄原則。</p></li>
</ul>
<p>完整功能集可與 Exchange Online 搭配使用;Exchange內部部署支援這些功能的大部分。 如需完整清單，請參閱<a href="/MicrosoftTeams/exchange-teams-interact">如何Exchange和Teams互動。</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>適用于商務用 Skype Server組織的啟用步驟  

1.  如需詳細資訊，請參閱上述一節。

2.  針對在 2019 年 9 月 1 日之後布建的租使用者，將租使用者切換到群島模式 (，請連絡客戶支援以進行此變更)   
    [設定您的共存與升級設定](setting-your-coexistence-and-upgrade-settings.md)

3.  根據貴公司的商務/公司原則設定租使用者  
    [管理組織的 Microsoft Teams 設定](enable-features-office-365.md)

4.  部署Teams用戶端  
    [取得 Teams 用戶端](get-clients.md)

5.   推動您的採用計畫  
    [採用Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Microsoft Teams採用快速入門檢查清單](teams-adoption-quick-start-checklist.md)

6.  開始規劃將其他工作量移至Microsoft 365或Office 365

7.  建立商務用 Skype混合式，並遵循商務用 Skype和 Lync 伺服器的建議升級路徑  
    [從商務用 Skype內部部署升級至Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>結語

Microsoft Teams可讓貴組織在單一平臺上將所有員工、資訊工作者和前線員工整合在一起。 您現在可以 [開始使用](https://products.office.com/microsoft-teams/group-chat-software) 。 您可以 [在這裡](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)與我們所有最新的公告和每月產品更新保持聯繫。

此外，由於世界各地的公司都在管理目前的 COVID-19 情況，因此我們建立了一系列內容，可協助您運用Teams，以獲得組織中的最大影響。

  - 我們在 [COVID-19 期間對客戶的承諾](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2 周後：我們從遠端工作學到的知識](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [提供線上會議和活動](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [協助中小型企業能夠使用 Teams 遠端工作](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [即時活動的數位轉換：Bob Bejan 對前線的觀察](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Microsoft IT 為其員工啟用遠端作業的最熱門 9 種方式](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/) (英文)

  - [遠端工作、保持安全— CISO 的秘訣](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [協助教師和學生切換到遠端學習](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [使用 Microsoft Teams 遠端工作時保持生產力](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>支援服務參考

Teams仰賴Exchange Online、SharePoint Online、商務用 OneDrive和Microsoft 365 群組，為使用者提供完全整合的Microsoft 365或Office 365體驗。 如上所述，Teams不會完全部署這些服務，但功能有限。 您可以在這裡深入瞭解Teams及其先決條件：[歡迎使用Teams](teams-overview.md)。

如需上述每個服務的特定資訊，請遵循下列連結：

  - Exchange Online用於行事曆功能，並將對等郵件儲存在Teams中。 若要深入瞭解，請閱讀[如何Exchange與Teams互動](exchange-teams-interact.md)

> [!IMPORTANT]
> 若要Teams內部部署Exchange，您必須按照在Exchange[與Exchange Online組織之間設定 OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)驗證中所述，設定新的 Exchange OAuth 驗證通訊協定。

  - SharePoint用於頻道中的檔案共用，而 /商務用 OneDrive 則用於 1：1 或群組聊天中的檔案共用。 若要深入瞭解，請閱讀[SharePoint線上與商務用 OneDrive如何與Microsoft Teams互動](sharepoint-onedrive-interact.md)。

  - [Microsoft 365 群組](office-365-groups.md)用於團隊和頻道建立/管理。


## <a name="related-topics"></a>相關主題

[Microsoft Teams IT 架構設計人員與電話語音解決方案海報](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[規劃商務用 Skype Server 和 Office 365 之間的混合式連線](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[支援使用Teams的遠端工作者](support-remote-work-with-teams.md)

[使用 Microsoft 365 遠端工作](https://aka.ms/remote-work)
