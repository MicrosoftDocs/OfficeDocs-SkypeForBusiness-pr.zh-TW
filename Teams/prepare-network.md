---
title: 針對 Teams 準備組織的網路
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: 瞭解如何為 Microsoft Teams 準備貴組織的網路，包括網路需求、網路優化和頻寬需求。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 1c84a753146899011fa34be56e0746cc0c600b31
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117751"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>針對 Microsoft Teams 準備組織的網路 

## <a name="network-requirements"></a>網路需求

如果您已經針對 [Microsoft 365 或 Office 365](/Office365/Enterprise/assessing-network-connectivity)優化您的網路，您可能已準備好使用 Microsoft Teams。 在任何情況下 ，尤其是當您將 Teams 快速推出為第一個 Microsoft 365 或 Office 365工作負載以支援遠端員工時，在開始推出 Teams 之前，請檢查下列事項：

1.  您的所有位置是否都有網際網路 (，以便他們連接到 Microsoft 365 或 Office 365) ？ 除了一般 Web 流量之外，請至少針對 Teams 中的媒體，針對所有位置開啟下列專案：

    |  |  |
    |---------|---------|
    |港口     |UDP 埠 <strong>3478</strong> 到 <strong>3481</strong>        |
    |[IP 位址](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<strong>13.107.64.0/18、52.112.0.0/14</strong>和<strong>52.120.0.0/14</strong> <strong></strong>         |

    > [!IMPORTANT]
    > 如果您需要與商務用 Skype 進行內部部署或線上聯合，則需要設定一些額外的 DNS 記錄。
    >
    >|CNAME 記錄 / 主機名稱  |Ttl  |指向位址或值  |
    >|---------|---------|---------|
    >|Sip     |    3600     |    sipdir.online.lync.com     |
    >|lyncdiscover     |   3600      |    webdir.online.lync.com     |
    
2.  您是否有 Microsoft 365 或 Office 365 (驗證網域，例如 contoso.com) ？
    
    - 如果貴組織尚未推出 Microsoft 365 或 Office 365，請參閱 [開始使用](/microsoft-365/admin/admin-overview/get-started-with-office-365)。
    - 如果貴組織尚未新增或已針對 Microsoft 365 或 Office 365 新增或已驗證網域，請參閱 [網域常見問題](/microsoft-365/admin/setup/domains-faq)。

3.  您的組織是否部署 Exchange Online 和 SharePoint Online？
    
    - 如果貴組織沒有 Exchange Online，請參閱瞭解 Exchange 與 [Microsoft Teams 的互動方式](exchange-teams-interact.md)。
    - 如果貴組織沒有 SharePoint Online，請參閱瞭解 [SharePoint Online](sharepoint-onedrive-interact.md)和商務用 OneDrive 如何與 Microsoft Teams 互動。

確認您符合這些網路需求之後，就可以開始 [推出 Teams 了](./deploy-overview.md)。 如果您是大型跨國企業，或如果您知道自己有一些網路限制，請繼續閱讀以瞭解如何評估及優化 Teams 的網路。

> [!IMPORTANT]
> **適用于教育機構**：如果貴組織是教育機構，而且您使用學生資訊系統 (SIS) ，請部署學校資料同步處理，[](/schooldatasync/)然後再推出 Teams。
>  
> **執行內部部署商務用 Skype Server：** 如果貴組織執行的是內部部署商務用 Skype Server (或 Lync Server) ，您必須設定 [Azure AD Connect，](/skypeforbusiness/hybrid/configure-azure-ad-connect) 以同步處理您的內部部署目錄與 Microsoft 365 或 Office 365。

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>最佳做法：使用 CQD 和通話分析監控您的網路 

使用 [CQD (儀表板 ](turning-on-and-using-call-quality-dashboard.md)) 以深入瞭解 Teams 中的通話和會議品質。 CQD 可密切注意品質、可靠性及使用者體驗，協助優化您的網路。 CQD 會查看整個組織的匯總遙測，其中整體模式可能會變得明顯，這可讓您找出問題並規劃補救。 此外，CQD 還提供豐富的度量報表，可提供整體品質、可靠性及使用者體驗的深入見解。 

您將使用通話 [分析](set-up-call-analytics.md) 來調查個別使用者的通話和會議問題。

## <a name="network-optimization"></a>網路優化

下列工作是選擇性的，且不需要用於推出 Teams，尤其是如果您是小型企業，而且已經推出 Microsoft 365 或 Office 365 時。 請使用本指南來優化您的網路和 Teams 績效，或者如果您知道自己有一些網路限制。

如果：

  - 團隊執行速度緩慢 (可能您沒有足夠的頻寬) 
  - 通話持續 (可能是防火牆或 Proxy 封鎖) 
  - 通話具有靜態和中斷，或語音聽起來像機器人 (可能會抖動或封包遺失) 

請參閱 Microsoft [365 和 Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)網路連接原則，以深入瞭解網路優化，包括識別及修正網路障礙的指南。

<table>
<thead>
<tr class="header">
<th><strong>網路優化工作</strong></th>
<th><strong>詳細資料</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>網路規劃中心</td>
<td><p>如要協助評估您的網路，包括整個組織實體位置的頻寬計算和網路需求，請查看 Teams 系統管理中心的網路規劃<a href="/microsoftteams/network-planner"></a><a href="https://admin.teams.microsoft.com">工具</a>。 當您提供您的網路詳細資料及 Teams 使用方式時，網路規劃工具會計算您在整個組織實體位置部署 Teams 和雲端語音的網路需求。</p>
<p>針對範例案例，請參閱 <a href="/microsoftteams/tutorial-network-planner-example">使用網路規劃工具 - 範例案例</a>。</p></td>
</tr>
<tr class="even">
<td>Teams 顧問</td>
<td><a href="/microsoftteams/use-advisor-teams-roll-out">Teams 的顧問</a> 是 <a href="https://admin.teams.microsoft.com">Teams 系統管理中心的一部分</a>。 在您成功推出 Teams 前，它會評估您的 Microsoft 365 或 Office 365 環境，找出可能需要更新或修改的最常用設定。</td>
</tr>
<tr class="odd">
<td>外部名稱解析</td>
<td>請確定執行 Teams 用戶端的所有電腦都可以解決外部 DNS 查詢，以探索 Microsoft 365 或 Office 365 所提供的服務，而且您的防火牆並未阻止存取。 若要瞭解防火牆埠的組組資訊，請前往 <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 和 Office 365 URL 和 IP 範圍</a>。</td>
</tr>
<tr class="odd">
<td>維持會話持續性</td>
<td>請確定防火牆不會變更對應網路位址翻譯 (UDP) 位址或埠。</td>
</tr><tr class="odd">
<td>驗證 NAT 資料庫大小</td>
<td>驗證網路位址翻譯 (NAT) 使用者連接所需的資料庫大小。 當多個使用者和裝置使用網路位址翻譯 (NAT) 或埠位址翻譯 <a href="/office365/enterprise/nat-support-with-office-365"> (PAT) </a>存取 Microsoft 365 或 Office 365 時，您必須確保隱藏在每個公開可路由 IP 位址後面的裝置不會超過支援的數量。 確保將適當的公用 IP 位址指派給 NAT 資料庫，以防止埠用盡。 埠用盡會導致內部使用者和裝置無法連接到 Microsoft 365 或 Office 365 服務。</td>
</tr>
<tr class="even">
<td>路由至 Microsoft 資料中心</td>
<td><a href="/office365/enterprise/client-connectivity">以最有效率的方式路由至 Microsoft 資料中心</a>。 找出可使用當地或地區出口點盡可能有效率地連接到 Microsoft 網路的位置。</td>
</tr>
<tr class="odd">
<td>入侵偵測與防護指南</td>
<td>如果您的環境已部署入侵<a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools"></a>偵測或防護系統 (IDS/IPS) ，為出站連接部署額外一層安全性，請務必允許所有 Microsoft 365 或 Office 365 URL。</td>
</tr>
<tr class="even">
<td>設定分割線 VPN</td>
<td><p>我們建議您為 Teams 流量提供替代路徑，以避開虛擬私人網路絡或 VPN (VPN) 通常稱為<a href="/windows/security/identity-protection/vpn/vpn-routing">分割式 VPN。</a> 分割管道表示 Microsoft 365 或 Office 365 的流量不會經過 VPN，而是直接進入 Microsoft 365 或 Office 365。 忽略您的 VPN 將會對 Teams 品質產生正面影響，而且會減少 VPN 裝置和組織網路的負載。 若要執行分割式 VPN，請與 VPN 廠商合作。</p>
<p>建議忽略 VPN 的其他原因：
<ul>
<li><p>VPN 通常未設計或配置為支援即時媒體。</p></li> 
<li><p>某些 VPN 可能也不支援 Teams (所需的 UDP) 。</p></li> 
<li><p>VPN 也會在已加密的媒體流量上引入額外的加密層。</p></li> 
<li><p>透過 VPN 裝置將流量釘在一起，因此與 Teams 的連接可能沒有效率。</p></li></td>
</tr>
<tr class="odd">
<td>實現 QoS</td>
<td><a href="/microsoftteams/qos-in-teams">使用 QoS (服務品質) </a> 設定封包優先順序。 這將改善 Teams 中的通話品質，並説明您監控和疑難排解通話品質。 QoS 應在受管理網路的所有區段上執行。 即使網路已充分配置頻寬，QoS 在發生非意外的網路事件時，也能夠降低風險。 使用 QoS 時，語音流量會優先處理，這樣這些非意外的事件不會對品質造成負面影響。</td>
</tr>
<tr class="even">
<td>優化 WiFi</td>
<td><p>與 VPN 類似，WiFi 網路不一定要經過設計或配置，以支援即時媒體。 規劃或優化支援 Teams 的 WiFi 網路是高品質部署的重要考慮。 請考慮以下因素：</p>
<ul>
<li><p>在 WMM 中 (QoS 或 WiFi 多媒體) ，以確保媒體流量在 WiFi 網路上獲得適當的優先順序。</p></li>
<li><p>規劃並優化 WiFi 頻帶和存取點位置。 2.4 GHz 範圍可能會根據訪問點位置提供適當的體驗，但訪問點通常會受到該範圍內運作的其他消費者裝置影響。 5 GHz 範圍較適合即時媒體，因為範圍較廣，但需要更多存取點才能獲得足夠的覆蓋。 端點也需要支援該範圍，並據此進行配置以運用這些頻帶。</p></li>
<li><p>如果您使用的是雙頻 WiFi 網路，請考慮使用帶式轉向。 <em>頻帶轉向</em> 是 WiFi 廠商所執行的一項技術，可影響雙頻用戶端使用 5 GHz 範圍。</p></li>
<li><p>當同一個通道的存取點太接近時，可能會導致訊號重迭，以及不小心相互競爭，給使用者造成不良的體驗。 請確保彼此旁邊的訪問點位於不重迭的頻道上。</p></li>
</ul>
<p>每個無線廠商都有自己的無線解決方案部署建議。 請查閱您的 WiFi 廠商以尋求特定指引。</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>頻寬需求

無論您的網路條件如何，Teams 都能提供最佳的音訊、視像和內容共用體驗。 也就是說，當頻寬不足時，Teams 會優先處理音訊品質與視音訊品質。

在頻寬沒有限制的地方，Teams 會優化媒體質量，包括高達 1080p 影片解析度、最多 30fps 視音訊和 15fps 內容，以及高逼真度音訊。 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a>相關主題

[Microsoft 365 和 Office 365 網路連接原則](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[全球端點：商務用 Skype Online 和 Teams](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Teams 的 Proxy 伺服器](proxy-servers-for-skype-for-business-online.md)

[Teams 中的媒體：為什麼會議簡單](https://aka.ms/teams-media)

[Teams 中的媒體：深入探討媒體流程](https://aka.ms/teams-media-flows)

[Teams 中的身分識別和驗證](identify-models-authentication.md)

[如何推出 Teams](./deploy-overview.md)

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)