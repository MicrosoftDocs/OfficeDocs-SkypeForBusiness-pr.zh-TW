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
ms.openlocfilehash: 89fb1ac43e199b3c8081735705a7d05bfcae710b
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587362"
---
# <a name="roll-out-microsoft-teams-first"></a>首先Microsoft Teams推出

Microsoft Teams能協助員工保持聯繫並彼此共同作業，尤其是在目前前所未有的時間，遠端工作已讓世界各地的員工實作。 能夠在公司內聊天、進行視訊會議，以及Office檔Teams協助公司保持生產力。 無論您是小型企業、非營利組織或大型組織，都可以在部署任何其他 Microsoft 365 或 Office 365 套件中，先開始使用 Teams 做為第一個工作負載Office 應用程式。

本文詳細說明您必須使用「第一Teams考慮事項。

> [!IMPORTANT]
> 雖然Teams是貴組織的第一個雲端部署工作負載，但部署Teams應成為您整體雲端部署策略的一部分。

如果您已經推出其他 Microsoft 365 或 Office 365 服務和 Teams 是下一個要推出 (的工作量，而不是第一個) ，請從如何推出 Teams[開始](./deploy-overview.md)。

## <a name="start-here"></a>從這裡開始

若要開始使用您的Teams部署，您至少必須滿足一些先決條件。 下列清單會顯示您必須先為貴組織就地擁有哪些專案，Teams啟用：

1.  使用Microsoft 365或Office 365網功能變數名稱稱所配置的組織

2.  Azure Active Directory連接 (AAD) 或類似的雲端身分識別同步處理解決方案 -所有所需的屬性都與租使用者同步處理  
    若要瞭解與 AAD 同步處理同步處理的屬性，請閱讀[Azure AD 連線同步處理：](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)同步處理Azure Active Directory

3.  指派適當的使用者授權Teams  
    若要瞭解Teams授權，請閱讀[Microsoft Teams描述](/office365/servicedescriptions/teams-service-description)。

4.  為組織網路做好準備Teams  
    若要瞭解網路準備，請參閱準備貴組織的網路[以Teams。](prepare-network.md)

5.  允許網路存取 Exchange、Sharepoint 和 商務用 OneDrive 或 Microsoft 365 中的 Office 365：Office 365 URL 和[IP 位址範圍](/office365/enterprise/urls-and-ip-address-ranges)。

> [!NOTE]
> 2019 年 9 月 1 日之後建立Teams模式。
> 
> [!IMPORTANT]
> 如果您已經商務用 Skype Server，而且您的租使用者是在 2019 年 9 月 1 日之後部署，請聯絡支援人員，以啟用 Teams。 將任何授權指派給使用者之前，請確定您的'全組織升級Teams設定<span class="underline"></span>為'島模式'。

## <a name="migration-starting-points"></a>移移起點

您前往 Microsoft 365或Office 365可用功能Teams視您的起點，以及內部部署或 Lync 伺服器商務用 Skype使用。 下列各節將詳述基本功能和組組選項，以及上述先決條件。 我們已將起點案例細分為下列主題：

**租Teams組** 態：租使用者和使用者模式是用來控制收件者的行為。 這些設定可以在租使用者層級或組織的使用者層級指派。 若要深入瞭解，請參閱[使用 商務用 Skype。](coexistence-chat-calls-presence.md)

**聊天/外部通訊** Teams：聊天服務是指與組織內部或組織外部的對等或群組聊天交談。 外部通訊也稱為在 商務用 Skype。

**在 Teams** 中建立和查看會議：一旦使用者獲得授權，使用者隨時都可以透過 Outlook Teams 附加元件和 PSTN 撥入功能建立線上會議。 Teams商務用 Skype將日曆資訊儲存在使用者的信箱Exchange中。 內部Exchange伺服器必須Exchange Server 2016 CU3 或更新Teams用戶端才能與使用者的信箱互動。 沒有Exchange信箱，系統將不會顯示 Teams 中的日曆圖示，使用者將無法在用戶端中查看、建立或修改Teams會議。

**通話功能 VoIP / PSTN** 在 Teams： 通話可以是語音 ip (VoIP) 或公用交換電話網絡 (PSTN) 。 VoIP 連接會原生地Teams用戶端之間，而 PSTN 連接則發生在使用者撥打外部電話號碼時。  

Teams兩種類型的 PSTN 連接。 Microsoft 通話方案：當 Microsoft 提供電話基礎結構 ，包括使用者的電話號碼或直接路由組式時，客戶會以會話邊界控制器 (SBC) 為 Teams 使用者提供電話連接。  
若要深入瞭解，請參閱哪一種通話方案適合[您？電話系統](calling-plan-landing-page.md)[路由](direct-routing-landing-page.md)。

**Teams和** 頻道共同作業Teams：Teams團隊是一群為了工作、專案或共同興趣而共同作業的人。 Teams由頻道所決定。 每個頻道都是圍繞主題建立，例如「小組活動」、部門名稱，或只是為了好玩。 頻道是您可以召開會議、進行交談，以及共同處理檔案的地方。 在共同合作期間

**商務用 OneDrive (p2P** 檔案共用) 在 Teams： Teams 和 Channels 之外，Teams 使用者可以使用 OneDrive 商務用或其他 P2P 共用檔案程式 ，例如思克檔案、DropBox、Box 和 Google 雲端硬碟 進行對等共用檔案。 針對OneDrive，使用者必須擁有SharePoint線上授權。

**應用程式平臺**：應用程式提供開箱即用的工具，讓貴組織能更Teams。 這些應用程式結合由 Microsoft、協力廠商或貴組織的開發人員提供的定位停駐點、訊息擴充功能、連接器和 Bot 功能。

安全性 **與** 合規性功能：Teams 提供豐富的資訊，可協助您處理合規性領域，包括保留政策、資料遺失保護 (DLP) 、電子檔探索和頻道、聊天和檔案的法律保留、稽核記錄搜尋。 若要深入瞭解，請參閱安全性與合規性[Microsoft Teams。](security-compliance-overview.md)  

> [!NOTE]
> 進一步電子探索功能需要 E5 授權。

[比較授權選項](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。

請參閱[Exchange Microsoft Teams](exchange-teams-interact.md)互動，以瞭解哪些合規性功能可在您的案例使用。

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>沒有 **<span class="underline">或</span>** Lync server 商務用 Skype組織

此起點假設您的組織目前並未使用 商務用 Skype Lync Server，Teams將成為您Microsoft 365或Office 365。 下表詳細列出適用于核心服務之Teams高層級的組Teams及使用者功能。

<table>
<thead>
<tr class="header">
<th>項目</th>
<th>注釋</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>租Teams組</td>
<td>Teams只有在模式中，所有聊天和通話功能都Teams使用。</td>
</tr>
<tr class="even">
<td>聊天/外部通訊Teams</td>
<td><p>內部 (內部Microsoft 365組織Office 365內部) 或外部聊天通訊Teams。</p>
<p><em>注意：DNS 專案必須針對外部存取進行配置。 商務用 Skype即使您沒有內部部署或 商務用 Skype 或 Microsoft 365 或 Office 365，也需要 DNS 記錄，才能允許與 Lync 和 商務用 Skype 環境進行聯合：<br />
<a href="/office365/enterprise/external-domain-name-system-records">外部網域名稱系統記錄</a></em></p></td>
</tr>
<tr class="odd">
<td>在會議中建立及Teams</td>
<td><p>能透過您的Outlook建立內部和外部會議。</p>
<p>PSTN 電話撥入和撥出功能與音訊會議授權一起提供。</p>
<p>Teams存取時，Exchange 2016 CU3+ 內部部署，並Exchange混合式部署：使用混合式組調精靈建立混合式<a href="/exchange/hybrid-deployment/deploy-hybrid">部署。</a> </p>

除了混合式Exchange，請Exchange OAuth 驗證：設定組織Exchange與Exchange Online[驗證](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)。 

</p></td>
</tr>
<tr class="even">
<td>通話功能<br />
VoIP / PSTN Teams</td>
<td><p>租使用者可在內部和外部使用 VoIP。</p>
<p>PSTN 服務可透過系統Microsoft 電話，以及新增 Microsoft 通話方案或直接路由。</p></td>
</tr>
<tr class="odd">
<td>Teams和頻道共同Teams</td>
<td><p>若要獲得完整體驗 ，包括合規性功能，SharePoint線上授權必須指派給使用者。</p>
<p>不需要移SharePoint內部部署網站。</p></td>
</tr>
<tr class="even">
<td>商務用 OneDrive (P2P 檔案共用) </td>
<td>商務用 OneDrive使用者必須指派線上SharePoint授權。 沒有此授權，無法進行對等檔案共用。</td>
</tr>
<tr class="odd">
<td>應用程式平臺</td>
<td>使用者將能夠使用根據貴公司政策所指定的應用程式。<br />
如需深入瞭解，請<a href="/microsoftteams/admin-settings">在這裡：在</a>Teams</td>
</tr>
<tr class="even">
<td>安全性與合規性功能</td>
<td><ul>
<li><p>保留政策可供使用。</p></li>
<li><p>支援 eDiscovery 和法律保留功能，以確保頻道訊息的合規性。</p></li>
<li><p>資料外遺失防護 (DLP) 可用。</p></li>
</ul>
<p>完整功能集可供Exchange Online;Exchange內部部署支援大部分的功能。 有關完整清單，請參閱<a href="/MicrosoftTeams/exchange-teams-interact">Exchange Teams互動</a>。</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>適用于沒有或 Lync Server 商務用 Skype啟用步驟

1.  符合上述開始這裡區段詳述的先決條件

2.  將租使用者切換到Teams模式 (現有租使用者) ：[設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)。

3.  根據貴公司的企業/公司政策設定您的租使用者：管理Microsoft Teams[的設定](enable-features-office-365.md)。

4.  將Teams用戶端部署到您的使用者：[取得用戶端Teams](get-clients.md)

5.  推動您的採用計畫  
    [採用Microsoft Teams](adopt-microsoft-teams-landing-page.md)
    
    [Microsoft Teams採用快速入門檢查清單](teams-adoption-quick-start-checklist.md)

6.  開始規劃將其他工作負載移Microsoft 365或Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>使用 **<span class="underline">商務用 Skype</span>** Lync 伺服器的組織

此起點假設貴組織使用內部商務用 Skype 2019 或 2015+ 或 Lync 2013+ 伺服器。 我們已針對組織從內部部署伺服器移Teams提供廣泛指引，這些案例應遵循此指南。 此指南是特定案例，Teams是您用來執行或Microsoft 365 Office 365。 下表詳細列出適用于核心服務之Teams高層級的組Teams及使用者功能。

<table>
<thead>
<tr class="header">
<th>項目</th>
<th>注釋</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>租Teams組</td>
<td>群島模式。</td>
</tr>
<tr class="even">
<td>聊天/外部通訊Teams</td>
<td>只有在您自己的租使用者內部，外部通訊 (聯) 會透過您的商務用 Skype Lync 伺服器部署。</td>
</tr>
<tr class="odd">
<td>在會議中建立及Teams</td>
<td><p>能透過您的Outlook建立內部和外部會議。</p>
<p>PSTN 電話撥入和撥出功能與音訊會議授權一起提供。</p>
<p>Teams使用混合式Exchange部署 2016 CU3+ 內部部署，Exchange存取：<br />
<a href="/exchange/hybrid-deployment/deploy-hybrid">使用混合式群組原則建立混合式部署。</a></p>
<p>系統管理員可以透過 Teams 商務用 Skype Outlook 會議策略的 PreferredMeetingProviderForIslandsMode 屬性<a href="/powershell/module/skype/set-csteamsmeetingpolicy">：set-csteamsmeetingpolicy</a>控制該附加元件。</p> 
</td>
</tr>
<tr class="even">
<td>通話功能<br />
VoIP / PSTN Teams</td>
<td><p>可在租使用者內部使用 VoIP。</p>
<p>在將使用者移至 [僅體驗Teams PSTN 或通話方案服務。</p></td>
</tr>
<tr class="odd">
<td>Teams和頻道共同Teams</td>
<td><p>若要獲得完整體驗 ，包括合規性功能，SharePoint線上授權必須指派給使用者。</p>
<p>不需要移SharePoint內部部署網站。</p></td>
</tr>
<tr class="even">
<td>商務用 OneDrive (P2P 檔案共用) </td>
<td>商務用 OneDrive使用者必須指派線上SharePoint授權。 沒有此授權，無法進行每對對等檔案共用。</td>
</tr>
<tr class="odd">
<td>應用程式平臺</td>
<td>使用者將能夠使用根據貴公司政策所指定的應用程式。<br />
如需深入瞭解，請<a href="/microsoftteams/admin-settings">在這裡：在</a>Teams</td>
</tr>
<tr class="even">
<td>安全性與合規性功能</td>
<td><ul>
<li><p>保留政策可供使用。</p></li>
<li><p>支援 eDiscovery 和法律保留功能，以確保頻道訊息的合規性。</p></li>
<li><p>資料外遺失防護 (DLP) 可用。</p></li>
</ul>
<p>完整功能集可供Exchange Online;Exchange內部部署支援大部分的功能。 有關完整清單，請參閱<a href="/MicrosoftTeams/exchange-teams-interact">Exchange Teams互動。</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>適用于具有下列功能之組織的啟用商務用 Skype Server  

1.  符合上述 <從這裡開始> 一節中詳述的先決條件。

2.  針對 2019/9/1 (租使用者，請將租使用者切換為群島模式，請與支援人員聯繫，)   
    [設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)

3.  根據貴公司的企業/公司政策設定租使用者  
    [管理組織的 Microsoft Teams 設定](enable-features-office-365.md)

4.  部署Teams用戶端  
    [取得 Teams 用戶端](get-clients.md)

5.   推動您的採用計畫  
    [採用Microsoft Teams](adopt-microsoft-teams-landing-page.md)<br/>
    [Microsoft Teams採用快速入門檢查清單](teams-adoption-quick-start-checklist.md)

6.  開始規劃將其他工作負載移Microsoft 365或Office 365

7.  建立商務用 Skype混合式，並遵循適用于 商務用 Skype Lync 伺服器的建議升級路徑  
    [從內部商務用 Skype升級至Teams](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>結束語句

Microsoft Teams成為貴組織在單一平臺上將所有員工、資訊工作者和前線工作人員彙集在一起的啟用器。 您 [今天就可以開始使用](https://products.office.com/microsoft-teams/group-chat-software) 。 您可以在這裡與我們所有的最新公告和每月產品更新 [保持聯繫](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)。

此外，由於世界各地的公司正在管理目前的 COVID-19 情況，我們已建立一系列內容，可協助您利用 Teams，以在組織中發揮最大影響。

  - 我們在[COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)期間與客戶的承諾

  - [2 周後：我們已瞭解遠端工作](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [提供線上會議和活動](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [協助中小型企業能夠使用 Teams 遠端工作](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [即時活動的數位轉換：Bob Bejan 從前線觀察](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Microsoft IT 為其員工啟用遠端作業的最熱門 9 種方式](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/) (英文)

  - [遠端工作、保持安全 —適用于CISOS 的秘訣](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [協助教師和學生切換到遠端學習](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [在遠端使用電腦時保持Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>支援服務參考

Teams仰賴 Exchange Online、SharePoint Online、商務用 OneDrive 和 Microsoft 365 群組，為使用者提供完全整合Microsoft 365或Office 365體驗。 如上所述，Teams完全部署這些服務 ，但功能有限。 您可以在這裡閱讀更多Teams及其先決條件：[歡迎使用 Teams。](teams-overview.md)

如需上述每項服務的詳細資訊，請遵循下列連結：

  - Exchange Online用於日曆功能，以及將對等郵件儲存Teams。 若要深入瞭解，請參閱[Exchange Teams互動](exchange-teams-interact.md)

> [!IMPORTANT]
> 若要Teams與 Exchange 內部部署進行交互操作，您必須設定新的 Exchange OAuth 驗證通訊協定，如在 Exchange 和 Exchange Online 組織之間設定[OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)驗證中所述。

  - SharePoint用於頻道中的檔案共用，而 /商務用 OneDrive 則用於 1：1 或群組聊天中的檔案共用。 若要深入瞭解，請參閱如何[SharePoint線上商務用 OneDrive與 Microsoft Teams。](sharepoint-onedrive-interact.md)

  - [Microsoft 365群組](office-365-groups.md)用於團隊和頻道建立/管理。


## <a name="related-topics"></a>相關主題

[Microsoft Teams IT 架構設計人員與電話語音解決方案海報](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[規劃商務用 Skype Server 和 Office 365 之間的混合式連線](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[支援使用遠端Teams](support-remote-work-with-teams.md)

[遠端處理Microsoft 365](https://aka.ms/remote-work)
