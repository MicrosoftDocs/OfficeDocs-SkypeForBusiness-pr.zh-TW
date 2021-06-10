---
title: 評估您的雲端語音工作負載環境
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 使用角色和網路分析來評估貴組織的整備狀態、開啟正確的 TCP 和 UDP 埠、執行任何網路補救。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6b65e6f2f6db4f5e824e55368d0a7a097eb39ad9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094771"
---
# <a name="evaluate-my-environment"></a>評估我的環境

本文提供正確評估您目前使用雲端語音服務之環境的需求概觀。 您可以評估您的環境，找出會影響整體雲端語音部署的風險和需求。 您可以事先識別這些專案，以調整您的規劃以推動成功。

## <a name="introduction-to-evaluating-your-environment"></a>評估環境簡介

若要在 OKRs (達成) ，您先前會做出重要的服務決策。 下一個步驟是執行環境探索，評估與 IT 和電話基礎結構、網路和營運相關的所有層面，以確認貴組織已準備好執行解決方案。

環境探索必須包含網路就緒性評定，以確保您的網路能夠支援音訊會議或電話系統方案服務的執行。

您將技術風險識別為環境評估與採用準備評估的一部分，並針對每個已識別的風險制定緩解計畫。
您應該在風險註冊簿中加入這項資訊。

<!--ENDOFSECTION-->

## <a name="current-environment"></a>目前環境

在環境探索中，包含與使用者計算相關的所有事項，例如電腦和行動裝置就緒狀況評估，以支援音訊會議，以及 電話系統 電話方案商務使用案例 ，從硬體需求到軟體需求。

環境探索也可以發現您是否需要將電話號碼[移轉至 Microsoft。](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)
瞭解這可協助貴組織調整其專案計劃，並準備數位移植的必要資訊。 您可以使用環境探索[來Microsoft Teams，](environmental-discovery-for-microsoft-teams-rollout.md)以執行環境探索。

<table>
<tr><td>標題</td><td>描述</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>決策點</td><td><ul><li>神秘負責完成環境評定嗎？</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul><li>記錄環境評定的結果。</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="adoption-and-change-management-assessment-capabilities"></a>採用及變更管理評定功能

部署可讓使用者輕鬆取得新技術，但只有在使用者真正採用解決方案做為自己的解決方案之後，才能取得商務成果。 若要協助確保持續採用新解決方案，您必須將精力集中在使用者準備狀態和變更管理上。 若要獲得最佳結果，請進行使用者準備規劃，做為技術準備活動的平行作業，並納入下列活動：

-   **組織和使用者剖析：** 除了使用案例和人員分析之外，組織對變更的不信度分析

-   **準備狀態和資源準備：** 建立具有目標且廣範圍的認知、訓練和支援資源，包括焦點價值訊息，以加速使用者購買

請使用下列考慮來評估貴組織的準備程度，以解決使用者變更管理。

<table>
<tr><td>標題</td><td>描述</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>決策點</td><td><ul><li>您之前是否成功採用軟體或服務？</li><li>您可以追蹤使用方式的使用方式嗎？</li><li>您擁有資源來設計和管理初始和持續採用活動， (認知、訓練 &mdash; &mdash; 和支援) ？</li><li>您是否有專屬的使用者採用/變更管理團隊，或可以投資這些資源以確保業務成果？</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul><li>如果您對上述所有專案都回答是，請找出正確的使用者變更管理專案關係人， &quot; &quot; 並開始規劃您的使用者準備狀態。</li><li>如果您對上述部分或所有專案回答否，請考慮使用外部資源以協助推動貴組織的變更管理和採用 &quot; &quot; 相關活動。</li></ol></td></tr>
</table>


<!--ENDOFSECTION-->

## <a name="network-readiness"></a>網路就緒

Teams音訊和視 (編解碼器) 編解碼器，可以適應大部分網路條件，因此在大部分網路條件下執行效果更佳。 為了確保最佳且一致的績效，您應為您的網路做好準備，Teams。

![描述品質三個要素的圖表](media/evaluate-my-environment-image1.png "描述品質的三個元件，以及服務管理如何與這三個元件重迭的圖表。將焦點放在網路上。")

## <a name="key-takeaways"></a>金鑰外賣

以下為本指南的主要說明。 您必須：

-   從用戶端開啟 TCP 埠 80 和 443 外Teams。

-   從將使用此埠的用戶端開啟 UDP 埠 3478 到 3481 外Teams。

-   確保您有足夠的頻寬來部署Teams。

-   執行 [網路評定工具](https://www.microsoft.com/download/details.aspx?id=53885) ，並確保您同時符合邊緣區段和用戶端區段的 [媒體](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) 品質和網路連接能力描述的需求。

## <a name="why-should-you-prepare-your-network"></a>為什麼要準備您的網路？

在我們查看要採取的步驟之前，瞭解哪些因素會影響使用者Teams進而影響使用者的滿意度和滿意度。
三個主要的風險區域可能會影響使用者對網路品質的感知：

-   可用的頻寬不足

-   防火牆和 Proxy 封鎖程式

-   網路障礙，例如抖動和封包遺失

下列步驟可協助判斷您的部署是否可能受上述任何一項因素影響，並有助於朝解決方向移動。
若無法準備您的網路，可能會導致使用者不滿意，以及代價昂貴的臨時修正程式。 您可以為網路及組織進行Teams，大幅提升成功的機會。

<!--ENDOFSECTION-->

## <a name="bandwidth-planning"></a>頻寬規劃

網路就緒的第一個步驟是確保您的網路有足夠的頻寬，Teams提供給使用者的方式。 規劃足夠的頻寬是相當簡單的工作，也是一項低障礙的開始，可確保使用者擁有高品質的Teams體驗。

### <a name="local-internet-egress"></a>當地網際網路出口

許多網路是專為使用中樞和分支拓撲所設計。 在這個拓撲中，網際網路流量通常會先將 WAN 傳輸至中央資料中心，再 (網際網路) 出口。 通常，這麼做是為了集中網路安全性裝置，以降低整體成本。

在 WAN 上回拖流量會增加延遲，並會對品質和使用者體驗造成負面影響。 由於Microsoft Teams在 Microsoft 的大型全域網路上執行，因此使用者附近通常會有網路對等位置。 使用者最有可能從靠近其位置的當地網際網路點出口，並儘快進入我們的語音優化網路，以取得更佳的績效。 針對某些工作負載，DNS 要求會用來將流量傳送至最近的前端伺服器。 在這種情況下，使用本地出口點時，必須搭配本地 DNS 解析度。

優化 Microsoft 全域網路的網路路徑將會改善績效，並最終為使用者提供最佳體驗。 如要取得詳細資訊，請參閱部落格文章在 Office 365 中取得[最佳Office 365。](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)

### <a name="vpn"></a>Vpn

VPN 為許多組織提供寶貴的服務。 很抱歉，它們通常未設計或配置為支援即時媒體。 某些 VPN 可能也不支援 UDP。 VPN 也會在已加密的媒體流量上引入額外的加密層。 此外，由於透過 VPN 裝置Teams釘住流量，可能無法有效率地與 Teams 服務建立連接。
此外，它們不一定是從容量角度設計，以配合預期的負載，Teams需求。

建議提供一個替代路徑，以針對流量Teams VPN。 這通常稱為 *分割線 VPN。* 分割轉場表示Microsoft 365或Office 365的流量不會穿過 VPN，但會直接Microsoft 365或Office 365。 這項變更會對品質產生正面影響，但也提供降低 VPN 裝置與組織網路負載的次要優點。

若要執行分割管道，請詢問 VPN 廠商的組組詳細資料。

### <a name="wi-fi"></a>Wi-Fi

與 VPN 一Wi-Fi，網路不一定設計或已配置為支援即時媒體。 規劃或優化支援Wi-Fi網路Teams是高品質部署的一項重要考慮。

有幾個因素可針對優化網路Wi-Fi作用：

-   在 WMM 中Wi-Fi QoS 或 (多媒體) ，以確保媒體流量比整個網路Wi-Fi優先順序。

-   規劃及優化Wi-Fi和存取點位置。 2.4 GHz 範圍可能會根據訪問點位置提供適當的體驗，但訪問點通常會受到該範圍內運作的其他消費者裝置影響。 5 GHz 範圍較適合即時媒體，因為媒體範圍密集，但需要更多存取點才能獲得足夠的覆蓋。 端點也需要支援該範圍並經過設定，才能據以運用這些頻帶。

-   如果部署雙Wi-Fi網路，請考慮執行帶式轉向。 帶式轉向是一項由Wi-Fi廠商所執行的技術，可影響雙頻用戶端使用 5 GHz 範圍。

-   當同一個通道的存取點太接近時，可能會導致訊號重迭和意外競爭，給使用者造成不良體驗。 確保頻道上相鄰的存取點沒有重疊。

每個無線廠商都有其部署無線解決方案的建議。 我們建議您向廠商尋求特定指引。

<!--ENDOFSECTION-->

## <a name="firewall-and-proxy-requirements"></a>防火牆和 Proxy 需求

Microsoft Teams連線到 Microsoft Online Services，並需要網際網路連線。 若要Teams，您必須從用戶端到網際網路開啟 TCP 埠 80 和 443，以及從用戶端到網際網路的 UDP 埠 3478 到 3481。 TCP 埠可用來連線至 Web 內容，例如 SharePoint Online、Exchange Online，以及 Teams 聊天服務。
外掛程式和連接器也會在這些 TCP 埠上連接。 這四個 UDP 埠用於音訊和視像等媒體，以確保它們能夠正確流動。

開啟這些埠對於可靠的部署Teams不可或缺。 封鎖這些埠不受支援，且會影響媒體質量。

如果您的組織要求您指定應開啟這些埠的確切 IP 位址範圍和網域，您可以限制這些埠的目標 IP 範圍和網域。 有關確切的埠、通訊協定和 IP 範圍清單，請參閱MICROSOFT 365或Office 365 URL 和[IP 位址範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams)。
如果您選擇限制目標 IP 位址範圍和網域，您必須確保埠和範圍清單保持在最新狀態，因為它們可能會變更。 您可以訂閱此 [RSS 提](https://go.microsoft.com/fwlink/p/?linkid=236301) 要，以在變更發生時進行更新。 此外，也可以定期執行網路[商務用 Skype，來測試是否開啟](https://www.microsoft.com/download/details.aspx?id=53885)所有埠。 您可以在下一節中進一步瞭解此工具的功能。

如果部署 Proxy 伺服器，建議您針對所有服務忽略 proxy 伺服器Teams伺服器。 雖然使用 Proxy 可能可以，但由於媒體強制使用 TCP 而非 UDP，因此品質很可能會降低。 有關 Proxy 伺服器和旁路詳細資訊，請參閱MICROSOFT 365或Office 365 URL 和[IP 位址範圍](./office-365-urls-ip-address-ranges.md)。

<!--ENDOFSECTION-->

## <a name="test-the-network"></a>測試網路

完成規劃與網路準備之後 ，包括升級頻寬和在防火牆中開啟埠，您應該測試網路的表現。 此測試的結果會更清楚地說明音訊會議或通話方案電話系統所需的網路優化或補救。

您可以下載[網路商務用 Skype工具](https://www.microsoft.com/download/details.aspx?id=53885)，以測試您的網路是否已準備好Teams。 此工具提供雙重功能：它可以測試是否已開啟所有正確的埠，也可以測試網路受損。

下載並安裝工具之後，您可以在 C：Microsoft 程式檔案商務用 Skype \\ \\ 網路評定工具找到它。 該目錄中包含如何使用工具的詳細指南 ，Usage.docx指南。

### <a name="test-for-opened-ports"></a>測試開啟的埠

開啟命令提示視窗，然後輸入 cd C 流覽至網路評定工具目錄：Microsoft 程式檔案商務用 Skype **\\ \\ 網路評定工具**。 在命令提示符中，輸入 **/connectivitychecknetworkassessmenttool.exe開啟的埠測試**

執行檢查之後，工具會顯示「驗證已成功完成」訊息，或是在封鎖的埠上報告。
它也會產生名為 Connectivity_results.txt 的檔案，其中包含工具的輸出，並儲存在 %userprofile% appdata 本地商務用 Microsoft Skype 網路評定工具 \\ \\ \\ \\ 目錄中。

我們建議您定期執行連接檢查，以確保埠已開啟且運作正常。

### <a name="test-for-network-impairments"></a>測試網路障礙

若要提高使用者滿意度，您應該限制網路上任何障礙。
最常見的網路障礙是延遲 (延遲) 封包遺失和抖動：

-   **延遲：** 這是從 A 點到網路 B 點取得 IP 封包所花的時間。 此網路傳播延遲基本上與兩點之間的實際距離和光速有關，包括介於兩者之間的各種路由器所增加的額外負荷。
    延遲是以單向或往返時間來測量。

-   **封包** 遺失：這通常定義為在給定時段內遺失的封包百分比。 封包遺失會直接影響音訊品質，從小型、個別遺失的封包幾乎不會影響到背對背的突發遺失，導致音訊完全中斷。

-   **封包間到達的抖動，或只是抖動：** 這是連續封包之間延遲的平均變化。 大部分的新式 VoIP 軟體 ，商務用 Skype，都可以透過緩衝來適應某些層級的抖動。 只有當抖動超過緩衝時，參與者才能注意到抖動的影響。

這些障礙的最大值會以 [媒體質量和](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)網路連接能力描述。
針對這些障礙進行測試時，我們會區分兩個不同的區段：

-   邊緣 *區段* 是路由器所生活的區段。 這是您每個位置連接網際網路的最接近的邏輯網路區段。 在大多數情況下，這是路由器的連接點，或可能是周邊網路 (也稱為 *DMZ、* 非軍事區和已篩選的子網) 。   此區段與網際網路之間不應發生其他影響路由器外裝置的流量。

-   用戶端 *區段* 是用戶端所在的邏輯網路區段。

您應該使用網路評定工具來測試這兩個區段。 若要測試區段，請流覽至目錄，networkassessmenttool.exe提示 **符** 輸入資料。 結果會寫入名為 Results.tsv 的檔案，您可以將結果與 [每個區段](/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) 的需求進行比較。

請注意，這兩個區段必須符合高品質部署的需求。 我們建議您直接執行工具多次一小時，以取得網路良好表現的指示。

<!--ENDOFSECTION-->

## <a name="network-remediation"></a>網路修復

如果頻寬規劃、埠測試或網路需求測試的結果顯示，您目前的網路需要修復才能部署Teams，您可以用多種方式達成此目的：

-   如果頻寬不足，請升級連接，讓Microsoft 365或Office 365流量不受阻礙。

-   針對封鎖的埠，變更防火牆規則，然後重新測試埠。

-   針對網路障礙，請一直執行根本原因分析。

QoS (服務品質) 優先處理和分隔流量，以與障礙進行較量。 有些組織選擇部署 QoS 以克服頻寬問題或限制流量流量。 這無法改善品質，並會導致新的問題。 當網路受損超過需求時，應一直執行根本原因分析。 QoS 可以是解決方案。
詳細資訊，請參閱在 Microsoft Teams 中[Microsoft Teams。](./qos-in-teams.md)

>[!NOTE]
>由於升級、擴充或其他商務需求，許多網路會隨著時間而演進。 在服務管理規劃中，請確保您擁有維護這些區域的操作程式。


<table>
<tr><td>標題</td><td>描述</td></tr>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>決策點</td><td><ul><li>神秘負責完成所有網路區段和組織位置的適當網路評定？</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul><li>您可以執行詳細的網路評估，協助確保您的網路已準備就緒，Microsoft Teams部署。</li><li>根據每個網路區段的評估結果執行網路補救。</li></ol></td></tr>
</table>

<!--ENDOFSECTION-->