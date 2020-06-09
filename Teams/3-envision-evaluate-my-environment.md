---
title: 針對雲端語音工作負載評估您的環境
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 使用角色和網路分析來評估貴組織的就緒性，開啟正確的 TCP 和 UDP 埠，然後執行任何網路修正。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 698d63f0d53119569f6b212fa7db7a16c827f571
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610055"
---
# <a name="evaluate-my-environment"></a>評估我的環境

本文概述針對使用雲端語音服務來正確評估目前環境的需求。 您可以評估您的環境，找出會影響整體雲端語音部署的風險與需求。 透過預先識別這些專案，您可以調整您的規劃來促進成功。

## <a name="introduction-to-evaluating-your-environment"></a>評估您的環境簡介 

為了達到您的目標金鑰結果（OKRs），您先前已進行重要的服務決策。 下一步是執行環保探索，以評估與您 IT 和電話結構、網路及作業相關的所有方面，以確認貴組織已準備好要實施方案。

環境探索必須包含網路就緒評估，以確保您的網路可支援使用通話方案服務來實現音訊會議或電話系統。

您可以在環境評估與採納準備情況評估中識別技術風險，並針對每個已識別的風險開發緩解方案。
您應該將此資訊納入風險登記簿中。

<!--ENDOFSECTION-->

## <a name="current-environment"></a>目前環境

在您的環境探索中，包括與使用者計算有關的所有相關事項，例如電腦和行動裝置的準備情況評估，以支援音訊會議和電話系統規劃商務使用案例（從硬體需求到軟體需求）。

環境探索也可以揭示您是否需要將[電話號碼傳送給 Microsoft](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。
瞭解這將會協助您的組織調整其專案計劃，並準備數位移植所需的資訊。 您可以使用[Microsoft 團隊推出的環境探索](environmental-discovery-for-microsoft-teams-rollout.md)來執行環境探索。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>決策點</td><td><ul><li>誰負責完成環境評估？</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul><li>記錄環境評估的結果。</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="adoption-and-change-management-assessment-capabilities"></a>採納與變更管理評估功能 

部署在使用者的使用中提供了新的技術，但商務結果只會在使用者真正採用該方案本身之後才會實現。 為了協助確保持續採用新的解決方案，您必須將精力集中在使用者就緒性與變更管理上。 若要取得最佳結果，請執行使用者準備規劃，做為您的技術準備活動的並行工作流，並納入下列活動：

-   **組織與使用者的分析：** 除了使用案例與角色分析之外，還能分析組織 receptiveness 變更

-   **準備就緒與資源準備：** 建立具有針對性和廣泛認識、訓練及支援資源的功能，包括焦點價值訊息，以加速使用者購買

使用下列考慮來評估貴組織的準備工作，以解決使用者變更管理問題。

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>決策點</td><td><ul><li>您是否曾在使用者採用軟體或服務之前取得成功？</li><li>您可以追蹤使用 uptake 嗎？</li><li>您是否擁有設計及管理初始 &mdash; 和持續進行的 &mdash; 採納活動（認識、訓練及支援）的資源？</li><li>您是否擁有專用的使用者採用/變更管理小組，或是您是否可以投資這些資源以確保商業結果？</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul><li>如果您 &quot; 對上述所有專案回答 [是] &quot; ，請找出適當的使用者變更管理專案關係人，並開始進行您的使用者準備規劃。</li><li>如果您回答「 &quot; 不 &quot; 是」的部分或全部，請考慮使用外部資源來協助您的組織進行變更管理與採納相關活動。</li></ol></td></tr>
</table>


<!--ENDOFSECTION-->

## <a name="network-readiness"></a>網路就緒

團隊使用可適應的音訊和視頻技術（編解碼器），因此在大多數網路條件下都能更好地執行。 為確保最佳且一致的效能，您應該為小組準備好您的網路。

![描述三個品質元件的圖表](media/evaluate-my-environment-image1.png "描述三個品質元件的圖表，以及服務管理如何與所有三個元件重迭。焦點放在網路上。")

## <a name="key-takeaways"></a>主要優點

這些是本指南的主要優點。 您必須：

-   開啟從將使用團隊之用戶端傳出的 TCP 埠80和443。

-   從將使用團隊的用戶端向外開啟 UDP 埠3478到3481。

-   確定您有足夠的頻寬可用於部署團隊。

-   執行 [[網路評](https://www.microsoft.com/download/details.aspx?id=53885)量] 工具，並確保符合從邊緣區段和用戶端區段的[媒體質量和網路連線效能](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)中所述的需求。

## <a name="why-should-you-prepare-your-network"></a>為什麼應該準備網路？

在我們開始查看要採取的步驟之前，請務必瞭解可能會影響團隊效能的專案，進而讓使用者的幸福與滿意。
三個主要的風險區域會影響使用者如何感覺網路品質：

-   沒有足夠的頻寬

-   防火牆與 proxy 攔截程式

-   網路障礙，例如抖動和資料包遺失

下面所述的步驟可協助您判斷您的部署是否可能受到這些因素的影響，並將協助您移至解決方法。
無法準備您的網路，可能會導致不滿意的使用者，以及大量、較高的臨時修正程式。 透過為小組準備您的網路和您的組織，您就能極大地增加成功的機率。

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>頻寬規劃

網路準備就緒的第一個步驟是確保您的網路有足夠的頻寬可供形式小組提供給使用者使用。 規劃足夠的頻寬是相當簡單的工作，而且是一個非常低的障礙開始，以確保您的使用者具備高品質的團隊體驗。

### <a name="local-internet-egress"></a>本機網際網路出口

許多網路都是用來使用中樞與輪輻拓朴的設計。 在此拓朴中，網際網路流量通常會在 WAN （egresses）到網際網路前，先將 WAN 移到中央資料中心。 通常，這是為了將網路安全裝置集中化以減少總成本的目的。

跨 WAN 的 hauling 流量會增加延遲，並對品質和使用者體驗造成負面影響。 因為 Microsoft 團隊是在 Microsoft 大型全域網路上執行，所以通常會有網路對等位置靠近使用者。 使用者最有可能獲得較佳的效能，只要從當地的網際網路點 egressing 到他們的位置，並儘快將它移到我們的語音優化網路上。 針對某些工作負荷，DNS 要求是用來傳送流量到最接近的前端伺服器。 在這種情況下，請務必注意，當您使用本機的出局點時，它會與本機 DNS 解析搭配使用。

將網路路徑優化至 Microsoft 的全域網路可改善效能，並最終為使用者提供最佳的體驗。 如需詳細資訊，請參閱在[Office 365 中取得最佳連線和效能](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)的博客文章。

### <a name="vpn"></a>點對點

Vpn 為許多組織提供重要的服務。 遺憾的是，它們通常不是專為支援即時媒體而設計或設定。 某些 Vpn 可能也不支援 UDP。 Vpn 也會在已加密的媒體流量上方引入額外的加密層級。 此外，由於將流量釘選到 VPN 裝置，因此小組服務的連線可能無法有效。
此外，它們不一定是從容量角度設計來容納小組將需要的預期負載。

建議您提供一個替代路徑來避開團隊交通的 VPN。 這通常稱為*分割隧道 VPN*。 分割隧道意味著 Microsoft 365 或 Office 365 的流量不會穿過 VPN，但會直接移至 Microsoft 365 或 Office 365。 這項變更會對品質產生正面的影響，但也會提供減少 VPN 裝置與組織網路負載的次要優點。

若要實現分割隧道，請諮詢您的 VPN 供應商以取得設定詳細資料。

### <a name="wi-fi"></a>Wi-fi

就像 VPN，Wi-fi 網路不一定設計或設定為支援即時媒體。 規劃或優化 Wi-fi 網路以支援小組是高品質部署的重要考慮。

在優化 Wi-fi 網路時，有幾個因素會進入播放：

-   實施 QoS 或 Wi-fi 多媒體（WMM），以確保媒體流量在 Wi-fi 網路上得到相應的優先順序。

-   規劃及優化 Wi-fi 區段和存取點位置。 2.4 GHz 範圍可能會根據存取點位置提供適當的體驗，但存取點通常會受到在該範圍中運作的其他消費者裝置的影響。 5 GHz 的範圍更適合即時媒體，因為它們的密集範圍，但需要更多存取點才能取得足夠的覆蓋範圍。 端點也需要支援該範圍，並將其設定為可據此加以設定以利用這些區段。

-   如果已部署雙頻帶 Wi-fi 網路，請考慮實施頻帶指導委員會。 [樂隊控制] 是由 Wi-fi 廠家提供的技術，可影響雙頻帶用戶端使用 5 GHz 範圍。

-   當同一個頻道的存取點太靠近時，可能會導致信號重迭，並無意間爭奪，進而導致使用者無法正常發揮問題。 確定彼此連續的存取點位於沒有交疊的頻道上。

每個無線廠商都有自己的部署其無線解決方案的建議。 我們建議您向您的廠商諮詢特定的指導方針。

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>防火牆與 proxy 需求

Microsoft 團隊會連線到 Microsoft Online 服務，並需要網際網路連線才能取得此問題。 若要讓團隊正常運作，您必須從用戶端開啟 TCP 埠80和443，以及從用戶端到網際網路的 UDP 埠3478到3481。 TCP 埠是用來連線到網路內容（例如 SharePoint Online、Exchange Online 和團隊聊天服務）。
外掛程式和連接器也會連線到這些 TCP 埠。 在音訊和影片等媒體使用四個 UDP 埠，以確保它們正常流動。

開啟這些埠對於可靠的小組部署而言是必要的。 封鎖這些埠是不受支援的，而且會影響媒體質量。

如果您的組織要求您指定要開啟這些埠的確切 IP 位址範圍和網域，您可以限制這些埠的目標 IP 範圍和網域。 如需確切的埠、通訊協定和 IP 範圍清單，請參閱[Microsoft 365 或 Office 365 url 與 ip 位址範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)。
如果您選擇限制目標 IP 位址範圍和網域，您必須確保將埠清單和範圍保持在最新狀態，因為它們可能會變更。 您可以訂閱[此 RSS](https://go.microsoft.com/fwlink/p/?linkid=236301)摘要，以便在變更發生時進行更新。 您也可以定期執行[商務用 Skype 網路評估工具](https://www.microsoft.com/download/details.aspx?id=53885)來測試所有埠是否已開啟，這也是一種很好的做法。 您可以在下一節中找到更多關於此工具功能的資訊。

在要部署的 proxy 伺服器事件中，建議您略過所有團隊服務的 proxy 伺服器。 雖然您可以使用 proxy，但很可能是因為媒體不得不使用 TCP，而不是 UDP，所以品質會降低。 如需 proxy 伺服器及回避的詳細資訊，請參閱[Microsoft 365 或 Office 365 url 與 IP 位址範圍](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)。

<!--ENDOFSECTION-->

## <a name="test-the-network"></a>測試網路

完成規劃和網路準備之後（包括升級防火牆中的 [升級頻寬] 和 [開啟埠]），您應該測試網路的效能。 這個測試的結果會讓您更清楚地瞭解任何網路優化，或您的音訊會議或電話系統是否有通話方案實現所需的修正。

您可以下載[商務用 Skype 網路評估工具](https://www.microsoft.com/download/details.aspx?id=53885)，以測試您的網路是否已準備好供團隊進行。 此工具提供雙重功能：可以測試是否所有正確的埠都已開啟，而且可以測試網路是否有障礙。

下載並安裝該工具之後，您可以在 C： \\ Program Files \\ Microsoft 商務用 Skype Network 評估工具中找到該工具。 該目錄中包含如何使用此工具的詳細指南（例如，用法 .docx）。

### <a name="test-for-opened-ports"></a>測試已開啟的埠

若要開啟命令提示字元視窗並流覽至網路評量工具目錄，請輸入**Cd C： \\ Program Files \\ Microsoft 商務用 Skype Network 評估工具**。 在命令提示字元中，輸入 networkassessmenttool 以開始測試已開啟的埠 **/connectivitycheck**

執行檢查之後，該工具會顯示「驗證已成功完成」的訊息，或報告已封鎖的埠。
它也會產生名為 Connectivity_results .txt 的檔案，其中包含該工具的輸出，並將其儲存在% userprofile% \\ appdata \\ 本機 \\ microsoft 商務用 skype 網路評估工具 \\ 目錄中。

我們建議您定期執行連接檢查，以確保埠已開啟且正常運作。

### <a name="test-for-network-impairments"></a>測試網路是否有障礙

若要提高使用者滿意度，您應該限制在網路上有任何障礙。
最常見的網路障礙是延遲（延遲）、資料包遺失和抖動：

-   **延遲：** 這是取得 IP 資料包從點 A 到網路上的點 B 所需的時間。 此網路傳播延遲實質上會與兩個點之間的實際距離和光線速度之間的距離產生關聯，包括不同的路由器所佔用的額外負荷。
    延遲是以單向或往返時間的方式來測量。

-   **資料包遺失**：這通常是定義為在指定的時間視窗中遺失的資料包百分比。 資料包遺失會直接影響音訊品質-從較小、個別的遺失式資料包，幾乎不會影響到完全剪下音訊的背對後爆發損失。

-   **資料包間的抖動，或簡單地抖動：** 這是連續資料包之間延遲的平均變更。 大多數現代 VoIP 軟體（包括商務用 Skype）都可以透過緩衝來適應某些層級的抖動。 只有抖動超過了參與者會注意到抖動效果的緩衝，才會出現這種情況。

在[媒體質量和網路連線效能](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)中，會說明這些障礙的最大值。
測試這些障礙時，我們會區分兩個不同的區段：

-   [*邊緣] 區段*是您的路由器所在的區段。 這是您在每個位置都連接至網際網路的最接近邏輯網路區段。 在大多數情況下，這是路由器的連接點，或可能是周邊網路（也稱為*DMZ*、*隔離區域*及*遮罩子網*）。 除了路由器以外的裝置之外，不會發生任何其他影響裝置與網際網路之間的通信量。

-   *用戶端區段*是您的用戶端所在的邏輯網路區段。

您應該使用 [網路評量] 工具測試這兩個區段。 若要測試區段，請流覽至該目錄，然後在命令提示字元中輸入**networkassessmenttool。** 結果會寫入名為 tsv 的檔案名，您可以將其與每個區段的[需求](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)進行比較。

請注意，這兩個區段必須符合高品質部署的需求。 我們建議您多次執行該工具，以讓您的網路效能得到良好的指示。

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>網路修正

如果頻寬規劃、埠測試或網路需求測試的結果顯示您目前的網路需要修正，才能部署小組，您可以透過下列幾種方式來完成此動作：

-   如果沒有足夠的頻寬，請升級連線，讓 Microsoft 365 或 Office 365 的流量能夠流過 unhindered。

-   針對封鎖的埠，請變更防火牆規則並重新測試埠。

-   針對網路障礙，請務必執行根本原因分析。

您可以將服務品質（QoS）劃分優先順序並分隔流量，以讓障礙不足。 有些組織會選擇部署 QoS 來克服頻寬問題，或限制流量流動的通信量。 這不會改善品質，也會導致新問題。 當網路障礙超過需求時，請務必執行根本原因分析。 QoS 可以是解決方案。
如需詳細資訊，請參閱[Microsoft 團隊中的服務品質](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams)。

>[!NOTE]
>許多網路由於升級、擴充或其他業務需求而逐漸隨著時間發展。 請確定您有適當的運作程式，以維護這些區域做為服務管理規劃的一部分。


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>決策點</td><td><ul><li>誰負責在所有網路區段和組織位置完成正確的網路評估？</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul><li>您可以執行詳細的網路評量，以協助確保您的網路可供您的 Microsoft 團隊部署使用。</li><li>根據每個網路區段評估的結果來執行網路修正。</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->
