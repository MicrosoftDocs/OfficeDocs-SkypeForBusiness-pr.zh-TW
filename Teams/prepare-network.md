---
title: 針對 Teams 準備組織的網路
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: 瞭解如何為 Microsoft 團隊準備貴組織的網路，包括網路需求、網路優化和頻寬需求。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: d0ce589ef972639928e4c8696f3ed23146126086
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583885"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>針對 Microsoft Teams 準備組織的網路 

## <a name="network-requirements"></a>網路需求

如果您已經針對[microsoft 365 或 Office 365 優化您的網路](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity)，您可能已經準備好開始進行 microsoft 團隊。 在任何情況下，特別是如果您是在第一份 Microsoft 365 或 Office 365 工作負載快速推出，以支援**遠端工作人員**，請先檢查下列專案，然後再開始進行團隊推出：

1.  您的所有位置都有網際網路存取權 (，讓他們可以連線至 Microsoft 365 或 Office 365) 嗎？ 除了標準的網路流量之外，請確定您已針對團隊中的媒體開啟下列專案（適用于所有位置）：

    |  |  |
    |---------|---------|
    |埠     |UDP 埠<strong>3478</strong>到<strong>3481</strong>        |
    |[IP 位址](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<strong>13.107.64.0/18</strong>、 <strong>52.112.0.0/14</strong>和<strong>52.120.0.0/14</strong>         |

> [!IMPORTANT]
> 如果您需要與商務用 Skype （內部部署或線上）聯盟，您將需要設定一些額外的 DNS 記錄。
>
>|CNAME 記錄/主機名稱  |TTL  |指向 [位址] 或 [值]  |
>|---------|---------|---------|
>|呼吸     |    3600     |    sipdir.online.lync.com     |
>|lyncdiscover     |   3600      |    webdir.online.lync.com     |
>


    
2.  您是否有驗證的網域供 Microsoft 365 或 Office 365 (例如，contoso.com) ？
    
      - 如果您的組織尚未推出 Microsoft 365 或 Office 365，請參閱[快速入門](https://docs.microsoft.com/microsoft-365/admin/admin-overview/get-started-with-office-365)。
      - 如果您的組織尚未新增或設定 Microsoft 365 或 Office 365 的驗證網域，請參閱[網域常見問題](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)。

3.  貴組織已部署 Exchange Online 和 SharePoint Online 嗎？
    
      - 如果您的組織沒有 Exchange Online，請參閱[瞭解 exchange 與 Microsoft 團隊互動的方式](exchange-teams-interact.md)。
      - 如果您的組織沒有 SharePoint Online，請參閱[瞭解 Sharepoint online 與商務用 OneDrive 與 Microsoft 團隊互動的方式](sharepoint-onedrive-interact.md)。

確認符合這些網路需求之後，您就可以準備好要[推出小組](How-to-roll-out-teams.md)。 如果您是大型的跨國公司，或者如果您知道您有一些網路限制，請繼續閱讀以瞭解如何為團隊評估及優化您的網路。

> [!IMPORTANT]
> **針對教育機構**：如果您的組織是教育機構，且您是使用學生資訊系統 (SIS) ，請在推出小組之前先[部署學校資料同步](https://docs.microsoft.com/schooldatasync/)處理。
>  
> 執行**內部部署商務用 Skype server**：如果您的組織正在執行內部部署商務用 skype server (或 Lync Server) ，您必須[設定 Azure AD Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) ，才能將您的內部部署目錄與 Microsoft 365 或 Office 365 同步處理。

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>最佳做法：使用 CQD 和通話分析監控您的網路 

使用[通話品質儀表板 (CQD) ](turning-on-and-using-call-quality-dashboard.md) ，深入瞭解團隊中的通話和會議品質。 CQD 可協助您保持密切留意品質、可靠性和使用者體驗，以協助您優化網路。 CQD 會在整個組織中查看匯總遙測，在這種情況下，整體模式會變得明顯，讓您找出問題並規劃修正。 此外，CQD 提供豐富的度量報告，可讓您深入瞭解整體品質、可靠性及使用者體驗。 

您將使用[呼叫分析](set-up-call-analytics.md)來調查個別使用者的通話與會議問題。

## <a name="network-optimization"></a>網路優化

如果您是小型企業版且已推出 Microsoft 365 或 Office 365，則下列工作是選擇性的，而且不是必要的。 使用本指導方針來優化您的網路與團隊效能，或者您知道您有一些網路限制。

在下列情況中，您可能會想要執行額外的網路優化動作：

  - 團隊執行速度緩慢 (可能是您沒有足夠的頻寬) 
  - 通話保留 (可能是由防火牆或 proxy 封鎖者所造成) 
  - 通話有靜態和剪下，或諸如機器人 (可能是抖動或資料包遺失) 

如需網路優化的深入討論，包括識別及修正網路障礙的指導方針，請參閱[Microsoft 365 和 Office 365 網路連線原則](https://aka.ms/pnc)。

<table>
<thead>
<tr class="header">
<th><strong>網路優化工作</strong></th>
<th><strong>詳細資料</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>網路 planner</td>
<td><p>如需評估網路的協助，包括貴組織之物理位置的頻寬計算和網路需求，請查看 [<a href="https://admin.teams.microsoft.com">小組管理中心</a>] 中的 [<a href="https://docs.microsoft.com/microsoftteams/network-planner">網路 Planner</a>工具]。 當您提供您的網路詳細資料和團隊使用量時，網路 Planner 會計算您的網路需求，以便在整個組織的物理位置部署團隊和雲端語音。</p>
<p>如需範例案例，請參閱<a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">使用網路 Planner-範例案例</a>。</p></td>
</tr>
<tr class="even">
<td>團隊顧問</td>
<td><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">團隊的 Advisor</a>是<a href="https://admin.teams.microsoft.com">團隊系統管理中心</a>的一部分。 在您成功推出 Teams 前，它會評估您的 Microsoft 365 或 Office 365 環境，找出可能需要更新或修改的最常用設定。</td>
</tr>
<tr class="odd">
<td>外部名稱解析</td>
<td>請確定執行團隊用戶端的所有電腦都可以解析外部 DNS 查詢，以探索 Microsoft 365 或 Office 365 提供的服務，而且您的防火牆無法防止存取。 如需設定防火牆埠的相關資訊，請移至<a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 和 Office 365 url 與 IP 範圍</a>。</td>
</tr>
<tr class="odd">
<td>維護會話暫留</td>
<td>請確定您的防火牆沒有將對應的網路位址轉譯 (NAT) 位址或埠，以進行 UDP。</td>
</tr><tr class="odd">
<td>驗證 NAT 池子大小</td>
<td>驗證網路位址轉譯 (NAT) 使用者連線所需的池大小。 當多個使用者與 365 365 裝置使用<a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">網路位址轉譯 (NAT) 或埠位址轉換 (PAT) </a>時，您必須確保隱藏在每個公開路由的 IP 位址後面的裝置不會超過支援的數量。 確保已將足夠的公用 IP 位址指派給 NAT 池，以避免埠耗盡。 埠耗盡會影響內部使用者和裝置無法連線至 Microsoft 365 或 Office 365 服務的情況。</td>
</tr>
<tr class="even">
<td>路由至 Microsoft 資料中心</td>
<td><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">實施最有效率的路由至 Microsoft 資料中心</a>。 找出可使用當地或地區出口點數盡可能高效地連線至 Microsoft 網路的位置。</td>
</tr>
<tr class="odd">
<td>入侵偵測與防範指導方針</td>
<td>如果您的環境有<a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">入侵偵測</a>或防護系統 (IDS/IPS) 是針對輸出連線的額外安全層級部署，請務必允許所有 Microsoft 365 或 Office 365 url。</td>
</tr>
<tr class="even">
<td>設定分割隧道 VPN</td>
<td><p>我們建議您為小組流量提供備用路徑，以繞過虛擬私人網路 (VPN) （通常稱為[分割隧道 VPN](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing)）。 分割隧道意味著 Microsoft 365 或 Office 365 的流量不會透過 VPN，而是直接移至 Microsoft 365 或 Office 365。 略過您的 VPN 會對團隊品質產生正面影響，並減少從 VPN 裝置與組織網路的載入。 若要實現分割隧道 VPN，請與您的 VPN 廠商合作。</p>
<p>我們建議您避開 VPN 的其他原因：
<ul>
<li><p>Vpn 通常不會設計或設定為支援即時媒體。</p></li> 
<li><p>某些 Vpn 可能也不支援 () 的小組所需的 UDP。</p></li> 
<li><p>Vpn 也會在已加密的媒體流量上方引入額外的加密層級。</p></li> 
<li><p>由於將流量釘選到 VPN 裝置上，因此可能無法有效地連接至團隊。</p></li></td>
</tr>
<tr class="odd">
<td>實施 QoS</td>
<td><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">使用服務品質 (QoS) </a>來設定資料包優先順序。 這將改善團隊中的通話品質，並協助您監控通話品質並進行問題的疑難排解。 QoS 應該在受管理的網路的所有區段上執行。 即使已針對頻寬充分提供網路，QoS 也會在事件發生時，在發生意外的網路事件時，降低風險。 透過 QoS，語音流量的優先順序會使這些意外事件不會對品質造成負面影響。</td>
</tr>
<tr class="even">
<td>優化 WiFi</td>
<td><p>與 VPN 類似，WiFi 網路不一定設計或設定為支援即時媒體。 規劃或優化 WiFi 網路以支援小組是高品質部署的重要考慮。 請考慮下列因素：</p>
<ul>
<li><p>實施 QoS 或 WiFi 多媒體 (WMM) ，以確保媒體流量在您的 WiFi 網路上適當地進行優先順序設定。</p></li>
<li><p>規劃及優化 WiFi 區段和存取點的位置。 2.4 GHz 範圍可能會根據存取點位置提供適當的體驗，但存取點通常會受到在該範圍中運作的其他消費者裝置的影響。 5 GHz 的範圍更適合用於即時媒體，因為它有大量的功能，但需要更多存取點才能取得足夠的覆蓋範圍。 端點也需要支援該範圍，並將其設定為可據此加以設定以利用這些區段。</p></li>
<li><p>如果您使用的是雙頻帶 WiFi 網路，請考慮執行頻帶控制。 [<em>樂隊</em>控制] 是由 WiFi 廠家提供的技術，可影響雙頻帶用戶端使用 5 GHz 範圍。</p></li>
<li><p>當同一個頻道的存取點太靠近時，可能會導致信號重迭，並無意間爭奪，從而導致使用者無法正常使用。 確定彼此連續的存取點位於沒有交疊的頻道上。</p></li>
</ul>
<p>每個無線廠商都有自己的部署其無線解決方案的建議。 請諮詢您的 WiFi 供應商以取得特定指導方針。</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>頻寬需求

無論您的網路狀況為何，小組都會設計為提供最佳的音訊、影片和內容共用體驗。 如此一來，當頻寬不足時，小組會將音訊品質與影片品質進行優先順序。

在頻寬*不*受限制的情況下，小組會優化媒體質量，包括高達1080p 的影片解析度、30fps 影片和15fps 內容，以及高保真音訊。 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a>相關主題

[Microsoft 365 和 Office 365 網路連接原則](https://aka.ms/pnc)

[全球端點：商務用 Skype Online 與團隊](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[小組的 Proxy 伺服器](proxy-servers-for-skype-for-business-online.md)

[團隊中的媒體：為什麼會議很簡單](https://aka.ms/teams-media)

[團隊中的媒體：深入瞭解媒體流程](https://aka.ms/teams-media-flows)

[Teams 中的身分識別和驗證](identify-models-authentication.md)

[如何推出 Teams](How-to-roll-out-teams.md)

[Teams 疑難排解](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
