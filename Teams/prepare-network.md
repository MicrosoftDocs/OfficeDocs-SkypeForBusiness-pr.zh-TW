---
title: 針對 Teams 準備組織的網路
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: 了解如何針對 Microsoft Teams 準備組織的網路，包括網路需求、網路最佳化和頻寬需求。
ms.localizationpriority: high
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
ms.openlocfilehash: 13bc12d5df1139bc76afa48751e7a7cb3c6197c0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621965"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>針對 Microsoft Teams 準備組織的網路 

## <a name="network-requirements"></a>網路需求

如果您已[針對 Microsoft 365 或 Office 365 最佳化您的網路](/Office365/Enterprise/assessing-network-connectivity)，則可能已準備好使用 Microsoft Teams。 在任何情況下，尤其是如果您要快速推出 Teams 做為第一個 Microsoft 365 或 Office 365 工作負載以支援 **遠端工作者** - 請在開始推出 Teams 之前，檢查下列項目：

1.  您的所有位置是否都有網際網路存取權 (以便它們可以連線到 Microsoft 365 或 Office 365)？ 除了正常網路流量之外，請確定您已開啟 [Office 365 URL 和 IP 位址範圍中列入 Teams 的 TCP 埠和 IP 位址](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)。

    > [!IMPORTANT]
    > 如果需要與商務用 Skype (內部部署或線上) 進行同盟，您必須設定額外的 DNS 記錄。
    >
    >|DNS 記錄  |服務  |Protocol (通訊協定)  |Priority (優先順序)  |Weight (權數)  |Port (連接埠)  |Target (目標)  |
    >|---------|---------|---------|---------|---------|---------|---------|
    >|SRV     |sipfederationtls     |TCP     |100     |1     |5061     |sipfed.online.lync.com     |
    
2.  您是否有 Microsoft 365 或 Office 365 的經驗證網域 (例如，contoso.com)？
    
    - 如果您的組織尚未推出 Microsoft 365 或 Office 365，請參閱[開始使用](/microsoft-365/admin/admin-overview/get-started-with-office-365)。
    - 如果您的組織尚未為 Microsoft 365 或 Office 365 新增或設定經驗證的網域，請參閱[網域常見問題集](/microsoft-365/admin/setup/domains-faq)。

3.  您的組織是否已部署 Exchange Online 和 SharePoint Online？
    
    - 如果您的組織沒有 Exchange Online，請參閱[了解 Exchange 和 Microsoft Teams 如何互動](exchange-teams-interact.md)。
    - 如果您的組織沒有 SharePoint Online，請參閱[了解 SharePoint Online 和商務用 OneDrive 如何與 Microsoft Teams 互動](sharepoint-onedrive-interact.md)。

一旦確認您符合這些網路需求，就可以開始[推出 Teams](./deploy-overview.md)。 如果您是大型的多國企業，或如果您知道有一些網路限制，請繼續閱讀以了解如何評估及最佳化 Teams 的網路。

> [!IMPORTANT]
> **適用於教育機構**：如果您的組織是教育機構，且您使用學生資訊系統 (SIS)，請在推出 Teams 之前 [部署學校資料同步處理](/schooldatasync/)。
>  
> **執行內部部署商務用 Skype Server**：如果您的組織執行的是內部部署商務用 Skype Server (或 Lync Server)，您必須 [設定 Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect)，以與 Microsoft 365 或 Office 365 同步處理您的內部部署目錄。

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>最佳做法：使用 CQD 和通話分析監視您的網路 

使用[通話品質儀表板 (CQD)](turning-on-and-using-call-quality-dashboard.md) 以深入了解 Teams 中的通話和會議品質。 CQD 會透過持續注意品質、可靠性和使用者體驗，協助您最佳化您的網路。 CQD 會查看整個組織整體模式可能變得明顯處的彙總遙測，這可讓您識別問題並規劃補救。 此外，CQD 會提供豐富的計量報告，其提供整體品質、可靠性和使用者體驗的深入見解。 

您將使用[通話分析](set-up-call-analytics.md)來調查個別使用者的通話和會議問題。

## <a name="network-optimization"></a>網路​​最佳化

下列工作是選用的，且並非推出 Teams 時的必要項目，特別是如果您是小型企業，而且已經推出 Microsoft 365 或 Office 365。 使用此指引來最佳化您的網路和 Teams 的效能，或如果您知道您有一些網路限制，也請參考此指引。

您可能會想要執行其他網路最佳化，前提是：

  - Teams 執行速度緩慢 (可能是您的頻寬不足)
  - 通話持續斷線 (可能是防火牆或 Proxy 封鎖程式所導致)
  - 通話有停滯和中斷，或聲音聽起來像機器人 (可能是抖動或封包遺失)

如需網路最佳化的深入討論，包括識別和修正網路減損的指引，請參閱 [Microsoft 365 和 Office 365 網路連線原則](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)。

<table>
<thead>
<tr class="header">
<th>網路​​最佳化工作</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>網路規劃中心</td>
<td><p>如需評估您的網路 (包括組織實體位置的頻寬計算和網路需求) 的協助，請查看 <a href="https://admin.teams.microsoft.com">Teams 系統管理中心</a>中的<a href="/microsoftteams/network-planner">網路規劃中心</a>工具。 提供網路詳細資料和 Teams 使用狀況時，網路規劃中心會計算在組織的實體位置間部署 Teams 與雲端語音的網路需求。</p>
<p>如需範例案例，請參閱<a href="/microsoftteams/tutorial-network-planner-example">網路規劃中心 - 範例案例</a>。</p></td>
</tr>
<tr class="even">
<td>適用於 Teams 的建議程式</td>
<td><a href="/microsoftteams/use-advisor-teams-roll-out">適用於 Teams 的建議程式</a>是 <a href="https://admin.teams.microsoft.com">Teams 系統管理中心</a>的一部分。 在您成功推出 Teams 前，它會評估您的 Microsoft 365 或 Office 365 環境，找出可能需要更新或修改的最常用設定。</td>
</tr>
<tr class="odd">
<td>外部名稱解析</td>
<td>請確定執行 Teams 用戶端的所有電腦都可以解析外部 DNS 查詢，以探索 Microsoft 365 或 Office 365 提供的服務，而且您的防火牆不會阻止存取。 如需設定防火牆連接埠的詳細資訊，請前往 <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 和 Office 365 與 IP 範圍</a>。</td>
</tr>
<tr class="odd">
<td>維護工作階段持續性</td>
<td>請確定您的防火牆不會變更對應的網路位址轉譯 (NAT) 位址或 UDP 的連接埠。</td>
</tr><tr class="odd">
<td>驗證 NAT 集區大小</td>
<td>驗證使用者連線所需的網路位址轉譯 (NAT) 集區大小。 多個使用者和裝置使用<a href="/office365/enterprise/nat-support-with-office-365">網路位址轉譯 (NAT) 或連接埠位址轉譯 (PAT)</a> 存取 Microsoft 365 或 Office 365 時，您必須確保隱藏於每個可路由 IP 位址後方的裝置不超過支援的數量。 確保將充足的公用 IP 位址指派到 NAT 集區，以防止連接埠耗盡。 連接埠耗盡會導致內部使用者和裝置無法連線到 Microsoft 365 或 Office 365 服務。</td>
</tr>
<tr class="even">
<td>路由至 Microsoft 資料中心</td>
<td><a href="/office365/enterprise/client-connectivity">對 Microsoft 資料中心實作最有效率的路由</a>。 盡可能有效率地識別可使用本機或區域出口點來連線至 Microsoft 網路的位置。</td>
</tr>
<tr class="odd">
<td>入侵偵測與預防指引</td>
<td>如果您的環境已部署<a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">入侵偵測</a>或預防系統 (IDS/IPS)，以針對輸出連線獲得額外一層的安全性，請務必允許所有 Microsoft 365 或 Office 365 URL。</td>
</tr>
<tr class="even">
<td>設定分割通道 VPN</td>
<td><p>建議您為會略過虛擬私人網路 (VPN) 的 Teams 流量提供替代路徑，通常稱為<a href="/windows/security/identity-protection/vpn/vpn-routing">分割通道 VPN</a>。 分割通道表示 Microsoft 365 或 Office 365 的流量不會通過 VPN，而是直接進入 Microsoft 365 或 Office 365。 略過 VPN 會對 Teams 品質產生正面影響，並減少來自 VPN 裝置和組織網路的負載。 若要實作分割通道 VPN，請與 VPN 廠商合作。</p>
<p>我們建議略過 VPN 的其他原因：
<ul>
<li><p>VPN 通常不會設計或設定為支援即時媒體。</p></li> 
<li><p>某些 VPN 可能也不支援 UDP (這是 Teams 所需)。</p></li> 
<li><p>VPN 也會在已加密的媒體流量上引入額外的加密層。</p></li> 
<li><p>由於透過 VPN 裝置切換流量，與 Teams 的連線可能會沒有效率。</p></li></td>
</tr>
<tr class="odd">
<td>實作 QoS</td>
<td><a href="/microsoftteams/qos-in-teams">使用服務品質 (QoS)</a> 來設定封包優先順序。 這將改善 Teams 中的通話品質，並協助您監控和疑難排解通話品質。 QoS 應該在受管理網路的所有區段上實作。 即使在網路已佈建足夠頻寬時，在發生未預期的網路事件時，QoS 也可提供風險緩解。 使用 QoS 時，會優先處理語音流量，使得這些非預期的事件不會對品質造成負面影響。</td>
</tr>
<tr class="even">
<td>最佳化 WiFi</td>
<td><p>類似於 VPN，WiFi 網路不一定需要設計或設定為支援即時媒體。 規劃或最佳化 WiFi 網路以支援 Teams，是實現高品質部署的重要考慮事項。 考慮下列因素：</p>
<ul>
<li><p>實作 QoS 或 WiFi 多媒體 (WMM) 以確保透過 WiFi 網路的媒體流量有適當的優先順序。</p></li>
<li><p>規劃和最佳化 WiFi 頻帶與存取點放置方式。 根據存取點放置方式，2.4 GHz 範圍可能會提供足夠的體驗，但存取點往往會受到該範圍中運作的其他消費者裝置影響。 5 GHz 範圍因其密度範圍較適合即時媒體，但需要更多存取點以取得足夠的覆蓋範圍。 端點也需要支援該範圍並經過設定，才能據以運用這些頻帶。</p></li>
<li><p>如果您使用的是雙頻 WiFi 網路，請考慮實作頻帶操縱。 <em>頻帶操縱</em>是 WiFi 廠商所實作的技術，可影響雙頻用戶端以使用 5 GHz 範圍。</p></li>
<li><p>當相同頻道的存取點太接近時，可能會導致信號重疊且無意間的競爭，導致使用者體驗不佳。 確保頻道上相鄰的存取點沒有重疊。</p></li>
</ul>
<p>每個無線廠商都有其部署無線解決方案的建議。 請洽詢您的 WiFi 廠商以了解特定指引。</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>頻寬需求

無論您的網路狀況如何，Teams 的設計都可提供最佳的音訊、視訊和內容共用體驗。 也就是說，當頻寬不足時，Teams 會優先處理音訊品質，之後才是視訊品質。

在頻寬未受限的情況下，Teams 會最佳化媒體品質，包括高逼真度音訊、最高至 1080p 的視訊解析度，以及最高 30fps (每秒畫面數) 的視訊和內容。

下表說明 Teams 使用頻寬的方式。 Teams 在頻寬利用方面一向非常節約，可提供低於 1.5 Mbps 的 HD 視訊品質。 每個音訊/視訊通話或會議中的實際頻寬消耗，會根據幾個因素而有所不同，例如視訊版面配置、視訊解析度和每秒視訊畫面格數。 當有更多頻寬可用時，品質和使用狀況便會提高，以提供最佳體驗。

:::row:::
   :::column span="":::
      **形式**
   :::column-end:::
   :::column span="3":::
      **頻寬需求 （位元速率 KB/s 上/下）**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
   :::column-end:::
   :::column span="":::
      **最小值**
   :::column-end:::
   :::column span="":::
      **建議**
   :::column-end:::
   :::column span="":::
      **最佳效能**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **音訊**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        一對一
   :::column-end:::
   :::column span="":::
        10/10
   :::column-end:::
   :::column span="":::
        58/58
   :::column-end:::
   :::column span="":::
        76/76
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        會議
   :::column-end:::
   :::column span="":::
        10/10
   :::column-end:::
   :::column span="":::
        58/58
   :::column-end:::
   :::column span="":::
        76/76
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **視訊**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        一對一
   :::column-end:::
   :::column span="":::
        150/150
   :::column-end:::
   :::column span="":::
        1,500/1,500
   :::column-end:::
   :::column span="":::
        4,000/4,000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        會議
   :::column-end:::
   :::column span="":::
        150/200
   :::column-end:::
   :::column span="":::
        2,500/4,000
   :::column-end:::
   :::column span="":::
        4,000/4,000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **共用螢幕**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        一對一
   :::column-end:::
   :::column span="":::
        200/200
   :::column-end:::
   :::column span="":::
        1,500/1,500
   :::column-end:::
   :::column span="":::
        4,000/4,000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        會議
   :::column-end:::
   :::column span="":::
        250/250
   :::column-end:::
   :::column span="":::
        2,500/2,500
   :::column-end:::
   :::column span="":::
        4,000/4,000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **齊聚模式**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        一對一
   :::column-end:::
   :::column span="":::
        不適用
   :::column-end:::
   :::column span="":::
        N/A
   :::column-end:::
   :::column span="":::
        不適用
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        會議
   :::column-end:::
   :::column span="":::
        1,000/1,500
   :::column-end:::
   :::column span="":::
        1,500/2,500
   :::column-end:::
   :::column span="":::
        2,500/4,000
   :::column-end:::
:::row-end:::

**最低**、 **建議的**，以及 **最佳** 頻寬需求是根據每個端點的使用情況。 一般來說，每個使用者為一個端點，例如電腦或行動裝置。 不過，如果使用者 *同時* 在電腦 *與* 行動裝置上參與 Teams 會議，則兩個端點皆會與該使用者相關聯。

- 視訊通話的 **最低** 頻寬需求為最高 240p 解析度、共用螢幕內容畫面播放速率可調整 1.875 到 7.5fps，而齊聚模式/大型圖庫視訊最高 540p 解析度。  

- 視訊通話的 **建議** 頻寬需求為最高 1080p 解析度 <sup>\*</sup>、共用螢幕內容畫面播放速率可調整為 7.5 到 30fps，而齊聚模式/大型圖庫視訊最高 1080p 解析度 <sup>\*</sup>。  

- **「最佳效能** 指引」可達成較大型的會議出席者人數、高遺失環境以及較高動作內容逼真度的視訊，螢幕共用內容畫面播放速率可調整從 15 到 30fps。

<sup>\*</sup>預期最高品質 1080p ，但根據您的網路狀況，音訊解析度和品質會加以優化。  

## <a name="related-topics"></a>相關主題

[Microsoft 365 和 Office 365 網路連線原則](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[全球端點：商務用 Skype Online 和 Teams](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Teams 的 Proxy 伺服器](proxy-servers-for-skype-for-business-online.md)

[Teams 中的媒體：為什麼會議很簡單](https://aka.ms/teams-media)

[Teams 中的媒體：深入探討媒體流程](https://aka.ms/teams-media-flows)

[Teams 中的身分識別和驗證](identify-models-authentication.md)

[如何推出 Teams](./deploy-overview.md)

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)
