---
title: Lync Server 2013：標牌： Lync 通話品質方法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Lync Call Quality Methodology'
ms:assetid: a069f4e5-4f80-4f0f-8657-2e07276b6b41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593600(v=OCS.15)
ms:contentKeyID: 61084874
ms.date: 06/24/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3647de7f803a8ec90d50236c5cf14c1a1cf8e0da
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513390"
---
# <a name="lync-call-quality-methodology-in-lync-server-2013"></a>Lync Server 2013 中的 lync 通話品質方法

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-06-24_

本文是 [Lync 通話品質方法](https://go.microsoft.com/fwlink/?linkid=391841) 海報的隨附，您可以從下載中心下載。

![描述 CQM 處理常式的海報](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "描述 CQM 處理常式的海報")

您可以使用此海報來瞭解 CQM，這是 Lync 2013 和2010的通話品質方法，可協助您找出並消除影響包含企業語音功能之 Lync 實施之通話品質和使用者經驗的問題。 通話品質方法是一種新的疑難排解和服務管理架構，可更好地致力於改進 Lync 中的 enterprise voice 服務。 在本文中，您可深入瞭解 CQM、所監控的伺服器和解決方案種類，以及如何處理收集的遙測資料。

如果您有關于如何使用 CQM 的問題，您可以將問題提交至 cqmfeedback@microsoft.com。

海報會說明下列方面：

  - 何謂 Lync CQM？

  - 優先順序：執行趨勢查詢

  - Pcd

  - Managed/非管理

  - 伺服器植物道路

  - 最後一個英里道路

  - 結束點道路

  - 服務管理

  - 董事會遊戲規則

<span id="WhatIs"></span>

<div>

## <a name="what-is-lync-cqm"></a>何謂 Lync CQM？

通話品質方法是一種新的疑難排解和服務管理架構，可更好地致力於改進 Lync 中的 enterprise voice 服務。 當您使用 CQM 時，需要較低的工作量，以確保企業語音服務的通話品質和使用者滿意度。 在 [通話品質方法](https://go.microsoft.com/fwlink/p/?linkid=615208)中，CQM 更充分地說明。 本文和海報是該內容的摘要。

CQM 會將系統疑難排解細分為三個路徑或 "道路"。 這些是：伺服器植物道路，它會看一下伺服器及它們之間的連結、端點道路，看起來就像是用來用來進行通話的使用者裝置和媒體，最後一次的道路是用來處理傳統切換電話網絡通話的整合。

每個道路都會分成數個與特定區域或主題相關的區段，而且每個片段定義都是針對可接受的品質等級，採取動作以達成該品質階層，並將服務管理計畫放在保持品質層級，再繼續進行下一個主題。

海報會顯示 Lync CQM 做為三位玩家的董事會遊戲，每個玩家都會透過道路。 下載所含的卡片是用來模擬障礙，以通話必須克服的品質。 這三個路徑會包含目標的相關提示和建議，以及如何在遊戲中的實際應用程式中優先處理的優先順序指導方針，這三個道路都是以平行) 進行處理的 (。

CQM 在舊版 Lync 中的運作方式？ CQM 是 Lync 2013 的新功能，但大部分可以搭配用來搭配 Lync 2010 使用。 CQM 可能會使用 Microsoft Office Communicator 的程度，但這已經過測試，且不受支援。

如果您有關于如何使用 CQM 的問題，您可以將問題提交至 cqmfeedback@microsoft.com。

</div>

<span id="Trending"></span>

<div>

## <a name="prioritize-run-trending-queries"></a>優先順序：執行趨勢查詢

CQM 的第一個步驟是執行每兩周的趨勢查詢，然後分析結果。 依最大的資料流程貢獻因素、最高不良的資料流程比率及受管理的區域，設定修正動作的優先順序， (您可以控制) 。如果 Audio/Video 的多重點控制項單位 (AV MCU) 或中繼查詢顯示結果不良，請從紅色或伺服器植物道路開始。如果有線或無線查詢顯示結果不良，請從藍色或最近的道路開始。如果 VPN 或外部查詢顯示結果不良，請從綠色或端點道路開始。

選擇開始的道路之後，請為每個區域 (Assert) 中定義目標，以符合該目標 (達成) ，然後執行程式以保持目標 (維護) 。 您也可以將此標牌當做遊戲使用，以瞭解 CQM 背後的原則。

</div>

<span id="PCD"></span>

<div>

## <a name="pcd"></a>Pcd

PreCall 診斷工具 (.PCD) 可協助您找出並診斷周邊網路中的問題 (QoE 資料庫不會收集 edge 或周邊網路) 上的資訊，同時也可疑難排解最後一個英里的連線。 這項工具既可以是 Windows 8 新式應用程式，也可以是 Windows 桌面應用程式 https://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88 。

</div>

<span id="ManagedUn"></span>

<div>

## <a name="managedunmanaged"></a>Managed/非管理

Lync Server 部署和網路基礎結構通常可分割為受管理和非管理的空間。 受管理的空間包含您整個內部有線網路和伺服器基礎結構。 非管理的空間為無線基礎結構和外部網路基礎結構。

進行此項區分可提高資料的清晰度，並可協助您的組織專注于對使用者的語音及視頻品質有實實在在影響的工作負載。 如果呼叫是放在您 (擁有 (非) managed) 某些其他實體以外的基礎結構上，則使用者的品質期望會不同。 這並不是說無線使用者留下其專屬裝置，使其具備絕佳的 Lync 伺服器體驗。

在未管理的空間中提升語音品質需要您在受管理的空間中具有高品質。 無線 (Wi-Fi) 是否視為受管理或未受管理的空間是由您的組織所決定。 實現狀況良好環境的技術在這兩個空白處是不同的解決方案。

</div>

<span id="ServRd"></span>

<div>

## <a name="the-server-plant-road"></a>伺服器植物道路

「伺服器植物道路的第1部定址 Lync 實施中的實際伺服器。 收集有關伺服器本身及其在實施中之角色的 KHI 資料，並分析結果。 如果有必要採取行動，請更正發現的任何問題。 有關此主題的詳細資訊，請在 KHI 海報隨附的 [Lync Server 2013 中的重要狀況](lync-server-2013-poster-key-health-indicators.md) 指標一文仲介紹。

下一段是 AV MCU 伺服器和轉送伺服器之間的媒體資料流程。 請先決定資料流程閥值不良的目標。 不良的資料流程通常是 PacketLossRate \> .01 或 PacketLossRateMax \> 。 另一個必要的目標是 PoorStreamsRatio \< 2%。 接下來，使用詳細的查詢來找出使用不良資料流程的 AVMCU 和轉送伺服器配對、調查不良資料流程的原因、查看不良資料流程路徑中的網路設備、修復不良資料流程，以及為網路裝置定義最優或「黃金」設定。 若要維護您的成就，請執行程式及工具，以管理設定偏移，並報告新的問題範圍。

接下來，檢查轉送伺服器和公用交換電話網路 (PSTN) 閘道之間的媒體資料流程。 請先決定資料流程閥值不良的目標。 不良的資料流程通常是 PacketLossRate \> .01 或 PacketLossRateMax \> 。 另一個必要的目標是 PoorStreamsRatio \< 2%。 接下來，使用詳細的查詢來尋找具有不良資料流程的轉送伺服器和閘道配對、調查不良資料流程的原因、查看不良資料流程路徑中的網路設備、修正不良的資料流程，以及為網路裝置定義最優或「黃金」設定。 若要維護您的成就，請執行程式及工具，以管理設定偏移，並報告新的問題範圍。

最後，檢查您的 PSTN 閘道的健康情況計量。 識別顯示狀況的統計資料，並針對這些統計資料定義目標。 這裡不提供任何特定指導，因為可使用許多可能的閘道。 建立目標之後，視需要進行修正以取得目標;在此程式中，您可能會定義閘道的「黃金」或最佳設定。 若要維護您的成就，請執行程式及工具，以管理設定偏移，並報告新的問題範圍。 請注意，固件和軟體更新可能會變更您的設定，或會使您變更「黃金」設定的定義，所以請謹慎使用這些活動。

</div>

<span id="LastMi"></span>

<div>

## <a name="the-last-mile-road"></a>最後一個英里道路

在用戶端連線到網路的兩種方式中，有線預期會提供最高的品質，而且必須是最後一個英里問題的初始焦點。 使用 CQM 有線查詢 (LastMile \_ 0 \_ 有線) 以及它所提供的不良資料流程比率資料。 建議您定義目標 PoorStreamsRatio \< 5% for sites with \> 300 資料流程) 。 若要取得您的目標，請將從最差排序的子網修正為最佳，並執行 QoS。

在您優化有線連線的品質後，增強無線品質會變得更容易，因為無線基礎結構位於每個位置的有線核心。 具有良好有線品質的網站中的無線資料流程不良，必須依特定無線元件而歸對。 CQM 無線查詢 (LastMile \_ 1 \_ 無線) 會在日期範圍內運作，並且會傳回您環境中所有內部的無線資料流程，從 Lync 用戶端到或從會議服務器或轉送伺服器。 建議您定義目標 PoorStreamsRatio \< 5% for sites with \> 300 資料流程) 。 若要取得您的目標，請將從最差排序的子網修正為最佳，並執行 QoS。

</div>

<span id="EndPt"></span>

<div>

## <a name="the-end-points-road"></a>結束點道路

在與 Lync 搭配使用時，會以耳機和其他設備所知道的點，來開始查詢。 我們建議使用目標 AvgSendListen MOS \> 3.6，以實現具有超過100資料流程的執行。 ) 會識別有問題的裝置，並修正或取代，以實現目標。

接下來，檢查裝置或電腦處理音訊的使用者通話。 建議的目標品質度量為 AudioMicGlitchRate \< = 1。 當您識別使用者系統的最佳系統設定時，請定義包含驅動程式版本的「黃金」 PC 設定。

現在，檢查音訊資料流程從 Lync 端點系統取得的網路路徑，這可能會導致音訊品質不良。 如果音訊透過 VPN 連線，您可能會看到延遲問題。 若內部 Lync 用戶端無法建立直接媒體資料流程給兩方或對等通話的另一個內部 Lync 用戶端，它會回復至透過 Lync Edge server 轉送的路徑，進而導致遺失和抖動的可能性變得更高。 我們建議您透過 VPN 定義品質衡量值為0% 的媒體。 當您進行修正以達到您設定的目標時，請找出問題的子網，並調查防火牆規則、資料包 shapers，以及其他相關的網路設備設定。

IP 封包可以使用傳輸控制通訊協定 (TCP) 或使用者資料包協定 (UDP) 。 TCP 是資料流程的最佳功能。 UDP 是不需連線的，更有效率的媒體，因為 TCP 復原機制無法處理即時媒體的遺失。 Lync 一定會喜歡 UDP，但如果無法建立 UDP 會話，則會還原為 TCP。 透過 TCP 的媒體會話會顯示出品質不如透過 UDP 的情況。 我們建議您透過 TCP 的高品質定義來定義0% 連線。 當您進行修正以達到您設定的目標時，請找出問題的子網，並調查防火牆規則、資料包 shapers，以及其他相關的網路設備設定。

</div>

<span id="ServMgt"></span>

<div>

## <a name="service-management"></a>服務管理

服務管理是 CQM 的結束狀態，及所有三個道路的目的地。 若要維持高水準的通話品質，請監視以下區域：

1.  **使用者** -修復活動應顯示使用者滿意度的可衡量增加。 您可以依問題票證或其他意見反應機制來衡量這種情況。 您也可以發佈品質度量。

2.  **Process** -定義 operationalize CQM 每日、每週及每月的處理常式。 在您對 (每日) 進行補救時，監控 rhythm 會在較高的頻率開始， (每月) 以穩定狀態移至較低頻率。

3.  **工具** -識別用來測量和修正的工具。 您可能會發現自動化執行 CQM 查詢以支援您的程式是很有用的。 修復可能需要其他工具，以強制執行網元上的標準化設定或疑難排解不良資料流程中的遺失。

</div>

<span id="BoardGm"></span>

<div>

## <a name="board-game-rules"></a>董事會遊戲規則

您可以使用此標牌做為參考 CQM 的執行，也可以做為遊戲以練習概念。 若要播放，您需要 1 6 邊片及隨附的卡。 可在標準 Avery 5871 名片上列印的卡片可下載版本。

遊戲適用于3玩家。 玩家可使用三種路徑來達到所需的品質，並達到中心服務管理狀態：伺服器植物、端點及最後英里。 每個路徑會沿著您用來斷言品質目標的方式、達到目標，以及維護系統的一個方面而停止。 將卡片放在上述區域，然後再繪製5張牌。 回顧您已繪製的卡片，並將其放在相關的董事會區段。 每一部玩家會逐步移動名片上的各卡片，以判斷品質目標，達到這些目標，以及維護服務等級。 當所有玩家都達到中央服務管理狀態時，遊戲即完成。 隨遊戲卡下載提供更詳細的規則。

若要 **斷言** 品質目標，請複查適用于該目標的參數，並將您不會選擇接受的內容放在適當的狀態。 我們建議的起始點，但是您必須進行最後的呼叫。 例外狀況是 KHI 資料，其中應使用 Microsoft 所建立的標準。 請參閱隨附的 KHI 海報。

若要在遊戲中 **取得** ，請使用提供的卡片取代 KHI 資料和系統查詢。 如果遊戲開始時您未繪製與指定的方位相關的卡片，您可以繼續過去。 如果有相關的卡片，請翻轉骰子。 如果您是以卡片上所指出的數位來擲出，表明您已成功。 如果您在指定的數位上進行擲出或移過，您必須從卡片組中畫出另一個卡片。 如果此卡片指出兩個以上的玩家必須滾出，必須全部順利滾。

若要在遊戲中 **維護** ，請進一步瞭解 Lync 環境的相關服務管理計畫。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 網路指南](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[主要健康情況指示器：維護狀況良好的 Lync 伺服器的基礎](https://go.microsoft.com/fwlink/?linkid=391838)  
[Lync 通話品質方法](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

