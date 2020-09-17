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
ms.openlocfilehash: 2f7acdfb092e74ae5e10e818b4007c4e22762a36
ms.sourcegitcommit: e773823a3f71efb6eee3bcbc928f1fee24c9381c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950859"
---
# <a name="roll-out-microsoft-teams-first"></a>先推出 Microsoft 團隊

Microsoft 團隊可以協助您的員工彼此保持聯繫並共同作業，特別是在目前空前的時間裡，我們的遠端工作是世界各地員工的實際員工。 在團隊中，您可以在 Office 檔上進行聊天、進行影片會議與共同作業，協助公司維持生產力。 無論您是小型企業、非盈利性或大型組織，您都可以在部署任何其他 Office app 或服務之前，先開始將團隊做為 Microsoft 365 或 Office 365 套件中的第一個工作負載。

本文詳細說明您必須使用「團隊優先」做法所做的考慮。

> [!IMPORTANT]
> 當團隊可以是貴組織的第一個雲端部署工作負載時，部署團隊應該是整個雲端部署策略的一部分。

如果您已推出其他 Microsoft 365 或 Office 365 服務，且小組是您下次要 (推出的工作負載，而不是第一個) ，請從 [如何推出團隊](How-to-roll-out-teams.md)開始。

## <a name="start-here"></a>從這裡開始

若要開始使用您的小組第一次部署，您必須至少滿足一些必備元件。 下列清單會顯示您在啟用團隊之前必須針對貴組織進行的動作：

1.  使用您的功能變數名稱設定的 Microsoft 365 或 Office 365 組織

2.  Azure Active Directory 連線 (AAD connect) 或類似的雲端身分識別同步處理方案，包括與您的租使用者同步處理的所有必要屬性  
    若要瞭解與 AAD 同步處理的屬性，請閱讀 [AZURE AD Connect 同步處理：屬性已同步處理到 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

3.  指派給小組的適當使用者授權  
    若要瞭解團隊授權，請參閱 [Microsoft 團隊服務說明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。

4.  組織為團隊準備的網路  
    若要瞭解網路準備，請閱讀 [針對團隊準備貴組織的網路](prepare-network.md)。

5.  在 Microsoft 365 或 Office 365 中允許網路存取 Exchange、Sharepoint 和商務用 OneDrive： [office 365 url 與 IP 位址範圍](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。

> [!NOTE]
> 在2019年9月1日之後建立的租使用者僅限 [小組] 模式提供。
> 
> [!IMPORTANT]
> 如果您已部署商務用 Skype Server 且您的租使用者已于2019年9月1日之後預配，請聯絡支援人員來啟用團隊的共存功能。 將任何團隊授權指派給使用者 <span class="underline">之前</span> ，請確定您的 [組織範圍升級原則] 已設定為 [孤島模式]。

## <a name="migration-starting-points"></a>遷移開始點

您在 Microsoft 365 或 Office 365 中的旅程，以及小組中提供的功能，取決於您的起點，以及現有的內部部署商務用 Skype 或 Lync server。 除了上述必備元件之外，下列各節將詳細說明基本功能和配置選項。 我們已將起點案例分解成下列主題：

**租使用者小組**設定：租使用者和使用者模式是用來控制收件者的行為。 您可以在租使用者層級或組織中的使用者層級指派這些設定。 若要深入瞭解，請參閱 [與商務用 Skype 共存](coexistence-chat-calls-presence.md)。

**團隊中的聊天/外部通訊**：聊天服務會參照對等與組織內或外部的對等或群組聊天交談。 外部通訊也稱為商務用 Skype 中的同盟。

**在團隊中建立及查看會議**：使用者隨時都可以透過 Outlook 團隊增益集和 PSTN 撥入來建立線上會議（在使用者獲得授權後，所有案例都會提供）。 [小組] 和 [商務用 Skype] 會在使用者的 Exchange 信箱中儲存行事曆資訊。 在內部部署 Exchange server 必須是 Exchange Server 2016 CU3 或更新版本，小組用戶端才能與使用者的信箱互動。 若沒有 Exchange 信箱存取，小組中的行事曆圖示就不會出現，而且使用者將無法在團隊用戶端中查看、建立或修改會議。

**在團隊中通話功能 voip/PSTN**：通話可以是經由 IP 語音 (VoIP) 或公開交換電話網絡 (PSTN) 。 VoIP 連線會在團隊用戶端之間固有進行，而 PSTN 連線則會在使用者撥打外線連線號碼時發生。  

團隊支援兩種類型的 PSTN 連線。 Microsoft 通話方案： Microsoft 提供電話結構，包括使用者的電話號碼，或直接路由設定，客戶可以在其中為團隊使用者提供電話語音連線 (SBC) 。  
若要深入瞭解，請閱讀適合 [您的通話方案](calling-plan-landing-page.md) ，以及 [電話系統直接路由](direct-routing-landing-page.md)。

團隊中的**團隊和頻道**共同作業：團隊中的團隊是共同作業、專案或共同興趣的人員群組。 團隊是由頻道組成。 每個頻道都是圍繞主題建立，例如「團隊活動」、部門名稱或只是有趣的。 頻道是您在其中召開會議、進行交談及共同處理檔案的位置。 在共同作業期間

**小組中的商務用 onedrive (P2P 檔案) 共用**：團隊和頻道以外的團隊使用者可以使用商務用 OneDrive 或其他 P2P 共用檔案程式（例如 Citrix 檔案、DropBox、Box 和 Google 雲端硬碟）來共用檔案對等。 針對商務用 OneDrive，使用者必須已指派 SharePoint Online 授權。

**應用程式平臺**： app 提供現成的工具供貴組織用來充分發揮團隊的效用。 這些 app 結合由 Microsoft （由協力廠商或由貴組織的開發人員建立）所提供的索引標籤、訊息擴充、連接器和 bot 功能。

**安全性與合規性功能：** 小組提供大量的資訊，可協助您處理合規性區域，包括保留原則、資料遺失保護 (DLP) 、eDiscovery 和法律封存等頻道、聊天及檔案、審核記錄搜尋。 若要深入瞭解，請參閱 [Microsoft 團隊中的安全性與合規性](security-compliance-overview.md)。  

> [!NOTE]
> 預先探索的 eDiscovery 功能需要 E5 授權。

[比較授權選項](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)。

閱讀 [Exchange 與 Microsoft 團隊如何互動](exchange-teams-interact.md) ，瞭解您的案例中提供哪些規範功能。

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a>**<span class="underline">沒有</span>** 商務用 Skype 或 Lync Server 的組織

這個起點假設貴組織不使用商務用 Skype 或 Lync Server，目前與團隊將是您在 Microsoft 365 或 Office 365 中的第一個應用程式。 下表詳細說明適用于核心服務之團隊的高層次設定和使用者功能。

<table>
<thead>
<tr class="header">
<th>項目</th>
<th>筆記</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>租使用者小組配置</td>
<td>[僅限團隊] 模式，所有聊天和通話功能只適用于團隊中。</td>
</tr>
<tr class="even">
<td>團隊中的聊天/外部通訊</td>
<td><p>在 Microsoft 365 或 Office 365 組織內部 () 與團隊間可能的外部聊天通訊。</p>
<p><em>注意： DNS 專案必須針對外部存取進行設定。 您也可以使用商務用 skype DNS 記錄，即使您沒有商務用 skype 內部部署，或是在 Microsoft 365 或 Office 365 中，允許與 Lync 和商務用 Skype 環境進行聯盟：<br />
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">外部網域名稱系統記錄</a></em></p></td>
</tr>
<tr class="odd">
<td>在團隊中建立及查看會議</td>
<td><p>可透過 Outlook 增益集建立內部和外部會議。</p>
<p>支援 PSTN 撥入和撥出功能（含音訊會議授權）。</p>
<p>團隊行事曆存取需要已建立 exchange 2016 CU3 + 內部部署的 exchange：<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">使用混合</a>式設定向導來建立混合式部署。 </p>
<p>除了 Exchange 混合式設定之外，請建立 Exchange OAuth 驗證： <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> 設定 exchange 與 Exchange Online 組織之間的 OAuth 驗證。</p>

</p></td>
</tr>
<tr class="even">
<td>通話功能<br />
團隊中的 VoIP/PSTN</td>
<td><p>可在內部和外部 VoIP 至租使用者。</p>
<p>PSTN 服務可以透過 Microsoft Phone System 進行設定，以及新增 Microsoft 通話方案或直接路由。</p></td>
</tr>
<tr class="odd">
<td>團隊中的團隊和頻道共同作業</td>
<td><p>如需全面體驗（包括規範功能），必須將 SharePoint Online 授權指派給使用者。</p>
<p>不需要遷移現有的內部部署 SharePoint 網站。</p></td>
</tr>
<tr class="even">
<td>商務用 OneDrive (P2P 檔案共用) </td>
<td>商務用 OneDrive 需要有指派 SharePoint Online 授權的使用者。 如果沒有這個授權對等檔案共用，就不可能了。</td>
</tr>
<tr class="odd">
<td>應用程式平臺</td>
<td>使用者將能夠根據您的公司原則，使用指派給他們的 app。<br />
深入瞭解： <a href="https://docs.microsoft.com/microsoftteams/admin-settings">在團隊中應用程式的系統管理設定</a></td>
</tr>
<tr class="even">
<td>安全性與合規性功能</td>
<td><ul>
<li><p>保留原則可供使用。</p></li>
<li><p>支援針對通道訊息的規範進行 eDiscovery 和法律封存。</p></li>
<li><p>您可以使用 (DLP) 的資料遺失防護原則。</p></li>
</ul>
<p>Exchange Online 提供完整的功能集;Exchange 內部部署支援這些功能中的大部分。 如需完整清單，請參閱 <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Exchange 與團隊如何互動</a>。</p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a>沒有商務用 Skype 或 Lync Server 的組織啟用步驟

1.  在上方的 [從這裡開始] 區段中，符合先決條件的詳細資訊

2.  只有) [設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)時，才會將租使用者切換到 [僅限 (的使用者] 模式。

3.  依照貴公司的商務/公司原則來設定您的租使用者： [管理貴組織的 Microsoft 團隊設定](enable-features-office-365.md)。

4.  將團隊用戶端部署至您的使用者： [取得團隊用戶端](get-clients.md)

5.  推動您的採納計畫  
    [採納 Microsoft 團隊](adopt-microsoft-teams-landing-page.md)
    
    [Microsoft 團隊採用快速入門檢查清單](teams-adoption-quick-start-checklist.md)

6.  開始規劃將其他工作負載移至 Microsoft 365 或 Office 365

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a>**<span class="underline">擁有商務用</span>** Skype 或 Lync server 的組織

這個起點假設您的組織使用商務用 Skype 2019 或 2015 + 或 Lync 2013 + 伺服器內部部署。 我們已經有許多從內部部署伺服器遷移至小組的組織的指導方針，而且應該遵循這些案例。 本指南專為團隊是您在 Microsoft 365 或 Office 365 中所使用的第一個應用程式的案例所特有。 下表詳細說明適用于核心服務之團隊的高層次設定和使用者功能。

<table>
<thead>
<tr class="header">
<th>項目</th>
<th>筆記</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>租使用者小組配置</td>
<td>孤島模式。</td>
</tr>
<tr class="even">
<td>團隊中的聊天/外部通訊</td>
<td>在您自己的租使用者內部，外部通訊 (同盟) 是透過您的商務用 Skype 或 Lync server 部署。</td>
</tr>
<tr class="odd">
<td>在團隊中建立及查看會議</td>
<td><p>可透過 Outlook 增益集建立內部和外部會議。</p>
<p>支援 PSTN 撥入和撥出功能（含音訊會議授權）。</p>
<p>團隊行事曆存取需要 exchange 2016 CU3 + 內部部署，且已建立 Exchange 混合式部署：<br />
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">使用混合式設定精靈建立混合式部署。</a></p>
<p>系統管理員可以透過團隊會議原則的 PreferredMeetingProviderForIslandsMode 屬性來控制商務用 Skype Outlook 增益集：<a href="https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>。</p> 
</td>
</tr>
<tr class="even">
<td>通話功能<br />
團隊中的 VoIP/PSTN</td>
<td><p>提供租使用者內部的 VoIP。</p>
<p>PSTN 或通話方案服務無法使用，除非使用者移至 [只有小組] 的體驗。</p></td>
</tr>
<tr class="odd">
<td>團隊中的團隊和頻道共同作業</td>
<td><p>如需全面體驗（包括規範功能），必須將 SharePoint Online 授權指派給使用者。</p>
<p>不需要遷移現有的內部部署 SharePoint 網站。</p></td>
</tr>
<tr class="even">
<td>商務用 OneDrive (P2P 檔案共用) </td>
<td>商務用 OneDrive 需要有指派 SharePoint Online 授權的使用者。 不可能有此授權的每對等檔案共用。</td>
</tr>
<tr class="odd">
<td>應用程式平臺</td>
<td>使用者將能夠根據您的公司原則，使用指派給他們的 app。<br />
深入瞭解： <a href="https://docs.microsoft.com/microsoftteams/admin-settings">在團隊中應用程式的系統管理設定</a></td>
</tr>
<tr class="even">
<td>安全性與合規性功能</td>
<td><ul>
<li><p>保留原則可供使用。</p></li>
<li><p>支援針對通道訊息的規範進行 eDiscovery 和法律封存。</p></li>
<li><p>您可以使用 (DLP) 的資料遺失防護原則。</p></li>
</ul>
<p>Exchange Online 提供完整的功能集;Exchange 內部部署支援這些功能中的大部分。 如需完整清單，請參閱 <a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Exchange 與團隊如何互動。</a></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a>商務用 Skype Server 的組織啟用步驟  

1.  符合上述 [從這裡開始] 區段中的先決條件。

2.  在9/1/2019 之後，將租使用者切換至 [孤島模式] (，請與支援人員聯繫，以進行此變更)   
    [設定您的共存與升級設定](setting-your-coexistence-and-upgrade-settings.md)

3.  根據公司的商務/公司原則設定您的租使用者  
    [管理組織的 Microsoft Teams 設定](enable-features-office-365.md)

4.  部署團隊用戶端  
    [取得 Teams 用戶端](get-clients.md)

5.   推動您的採納計畫  
    [採納 Microsoft 團隊](adopt-microsoft-teams-landing-page.md)<br/>
    [Microsoft 團隊採用快速入門檢查清單](teams-adoption-quick-start-checklist.md)

6.  開始規劃將其他工作負載移至 Microsoft 365 或 Office 365

7.  建立商務用 Skype 混合式，並遵循針對商務用 Skype 和 Lync server 所建議的升級路徑  
    [從商務用 Skype 內部部署升級至團隊](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a>落款語句

Microsoft 團隊可以是您組織的啟用程式，將所有員工、資訊工作者及第一線員工工作人員放在單一平臺上。 您現在可以 [開始](https://products.office.com/microsoft-teams/group-chat-software) 使用。 您可以在 [這裡](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog)與所有最新的宣告及每月產品更新保持聯繫。

此外，隨著世界各地的公司所管理的是目前的 COVID-19，我們已建立一系列的內容，協助您利用團隊來取得貴組織的最大影響。

  - 我們 [在 COVID 期間對客戶的承諾-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)

  - [2周內：我們已瞭解遠端作業的相關資訊](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [傳送線上會議與活動](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [協助中小型企業能夠使用 Teams 遠端工作](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/) (英文)

  - [即時事件的數位轉換：王俊元從第一線 Bejan 的觀測值](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [Microsoft IT 為其員工啟用遠端作業的最熱門 9 種方式](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/) (英文)

  - [遠端工作、保持安全（CISOs 的秘訣）](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [協助教師與學生進行遠端學習](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [使用 Microsoft 團隊進行遠端作業時保持生產力](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a>支援服務參考

團隊依賴 Exchange Online、SharePoint Online、商務用 OneDrive 和 Microsoft 365 群組，為您的使用者提供完全整合的 Microsoft 365 或 Office 365 體驗。 如上述所述，小組將能正常運作，而不需全面部署這些服務-並提供有限的功能。 您可以在這裡閱讀更多關於團隊及其必備專案的資訊： [歡迎使用團隊](teams-overview.md)。

如需上述各項服務的詳細資訊，請遵循下列連結：

  - Exchange Online 用於行事曆功能，並將對等的訊息儲存在團隊中。 若要深入瞭解，請閱讀 [Exchange 與團隊互動的方式](exchange-teams-interact.md)

> [!IMPORTANT]
> 針對使用 Exchange 內部部署的團隊互通性，您必須按照 [設定 exchange 與 Exchange Online 組織之間的 OAuth 驗證](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)中所述的方式來設定新的 Exchange OAuth 驗證通訊協定。

  - SharePoint 是用於頻道中的檔案共用，而商務用/OneDrive 則用於1:1 或群組聊天中的檔案共用。 若要深入瞭解，請參閱 [SharePoint Online 與商務用 OneDrive 與 Microsoft 團隊互動的方式](sharepoint-onedrive-interact.md)。

  - [Microsoft 365 群組](office-365-groups.md) 用於小組和通道建立/管理。


## <a name="related-topics"></a>相關主題

[Microsoft Teams IT 架構設計人員與電話語音解決方案海報](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[規劃商務用 Skype Server 和 Office 365 之間的混合式連線](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[使用團隊支援遠端工作人員](support-remote-work-with-teams.md)

[使用 Microsoft 365 遠端作業](https://aka.ms/remote-work)
