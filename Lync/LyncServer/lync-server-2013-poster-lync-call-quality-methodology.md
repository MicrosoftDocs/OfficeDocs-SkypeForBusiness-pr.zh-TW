---
title: Lync Server 2013： 海報： Lync 通話品質方法
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
ms.openlocfilehash: 849e74fb4857dd7b3ab98b8a8efd9c3ce3781e35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-call-quality-methodology-in-lync-server-2013"></a>Lync Server 2013 中的 Lync 通話品質方法

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016年-06-24_

本文是隨附的[Lync 通話品質方法](http://go.microsoft.com/fwlink/?linkid=391841)海報，您可以從下載中心下載。

![海報中描述的 CQM 程序](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "海報中描述的 CQM 程序")

您可以使用此海報以了解 CQM、 通話品質方法 Lync 2013 和 2010，可協助您找出並消除問題影響通話品質和使用者經驗的 Lync 的實作，包括 enterprise voice 功能。 通話品質方法就是新的疑難排解更妥善地可以專注於改善 Lync 中的企業語音服務的服務管理架構。 在本文中，您可以深入了解 CQM、 幾種類型的伺服器與解決方案，監控，以及如何收集的遙測資料處理的項目。

如果您有關於如何使用 CQM 問題，您可以提交至 cqmfeedback@microsoft.com 問題。

海報說明下列領域：

  - Lync CQM 是什麼？

  - 優先順序： 執行趨勢查詢

  - PCD

  - Managed/Unmanaged

  - 伺服器廠隨身攜帶

  - 最後一個哩隨身攜帶

  - 結束點隨身攜帶

  - 服務管理

  - 棋盤遊戲規則

<span id="WhatIs"></span>

<div>

## <a name="what-is-lync-cqm"></a>Lync CQM 是什麼？

通話品質方法就是新的疑難排解更妥善地可以專注於改善 Lync 中的企業語音服務的服務管理架構。 當您使用 CQM 時，需要更輕鬆的方式就能保證通話品質及提升使用者滿意度，適用於企業語音服務。 [通話品質方法](http://go.microsoft.com/fwlink/p/?linkid=615208)會詳細說明 CQM。 這篇文章和海報是該內容的摘要。

CQM 細分系統疑難排解到三個路徑或 「 通道 」。 這些是： 伺服器廠隨身攜帶，它看來伺服器和、 結束點隨身攜帶，查看使用者裝置和媒體用來執行通話，以及上次哩隨身攜帶，地址整合的傳統交換的電話網路之間的連結。

每個途徑可分成數個區段相關的特定區域或主題，並在每個區段定義之所以資訊可接受的品質等級，不採取動作達成品質等級，與服務管理計畫就會處於維護的地方再移至下一個主題的品質等級。

海報會呈現為棋盤遊戲 Lync CQM 的三個播放，每個使用者都就會通過經歷下列其中一個通道。 卡隨附下載可用來模擬呼叫必須克服的品質障礙。 提示與建議相關的目標，以及如何達成這些隨附沿著的三個路徑，以及要先實際的應用程式中的哪些隨身攜帶的優先順序指導方針 （在 [遊戲時，所有三個通道中會處理平行）。

CQM 如何運作中更早版本的 Lync？ CQM's new for Lync 2013 中，但是大部分的它可適用於與 Lync 2010 搭配使用。 CQM 可能運作進行一定程度與 Microsoft Office Communicator，但這是未經測試，而且不受支援。

如果您有關於如何使用 CQM 問題，您可以提交至 cqmfeedback@microsoft.com 問題。

</div>

<span id="Trending"></span>

<div>

## <a name="prioritize-run-trending-queries"></a>優先順序： 執行趨勢查詢

CQM 的第一步是執行每個趨勢查詢的兩週，並再分析結果。 優先順序矯正措施的最大的資料流參與者、 最高不佳的資料流率，並受管理的區域 （您可以控制的項目）。如果 [音訊/視訊多點 Control Unit (AV MCU) 或中繼查詢顯示不佳的結果，請啟動紅色或伺服器廠隨身攜帶。如果有線或無線查詢顯示不佳的結果，請啟動藍色或最後一個哩隨身攜帶。如果 VPN 或外部查詢顯示不佳的結果，請啟動綠色或結束點隨身攜帶。

開始使用您選擇 [隨身攜帶之後，定義每個區域 (Assert)，可以使用，以符合該目標 (Achieve)，然後實作留在目標 （維持） 的程序的目標。 您也可以使用此海報以遊戲，若要了解 CQM 背後的原則。

</div>

<span id="PCD"></span>

<div>

## <a name="pcd"></a>PCD

PreCall 診斷工具 (PCD) 可協助您找出並診斷問題在周邊網路 （QoE 資料庫不會收集資訊 edge 或周邊網路），也要疑難排解中最後一個哩的連線。 為 Windows 8 新式應用程式或 Windows 桌面應用程式工具可供http://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88。

</div>

<span id="ManagedUn"></span>

<div>

## <a name="managedunmanaged"></a>Managed/Unmanaged

Lync Server 部署和網路基礎結構通常可分成 managed 和 unmanaged 空格。 受管理的空間可包含您整個內有線的網路和伺服器基礎結構。 未受管理的空間是無線基礎結構，以及外部網路基礎結構。

進行這樣的區分會增加資料的緣故，並可協助您組織的焦點上會有可測量影響使用者的語音和視訊品質的工作負載。 使用者可以品質不同期望如果來電會被放置在基礎結構上您擁有 （管理） 與基礎結構的 （未受管理） 的其他實體的控制下的部分。 這並不是說無線使用者由左到自己的裝置有極佳的 Lync Server 體驗。

改善的未受管理的空間中的語音品質必須要有高品質的受管理的空間中。 無線 (Wi-fi) 是否會被視為受管理或未受管理的空間是由您的組織。 是解決方案所，不同於兩個的空格，以達到狀況良好的環境的技術。

</div>

<span id="ServRd"></span>

<div>

## <a name="the-server-plant-road"></a>伺服器廠隨身攜帶

區段 1 伺服器廠隨身攜帶的地址中的 Lync 實作實際的伺服器。 收集有關伺服器本身及實作中的其角色 KHI 資料並分析結果。 如果巨集指令已獲得保證，更正發現的任何問題。 本主題的其他詳細資料會以[Lync Server 2013 中的機碼健康狀態指標](lync-server-2013-poster-key-health-indicators.md)時所附帶 KHI 海報的相關文件呈現。

下一個區段位址 AV MCU 伺服器和中繼伺服器之間的媒體資料流。 首先決定不佳的資料流閾值的目標。 不佳的資料流通常是 PacketLossRate \> .01 或 PacketLossRateMax \> .05。 另一個令人滿意的目標是 PoorStreamsRatio \< 2%。 接下來，使用詳細的查詢來找出與不佳的資料流的 AVMCU 和中繼伺服器配對、 調查不佳的資料流的原因、 查看不佳的資料流路徑中的網路設備、 修復不佳的資料流，並定義網路最佳或 「 金會員 」 設定設備。 若要維護您成就，實作程序和工具來管理組態漂移並報告新的問題領域。

接下來，檢查中繼伺服器與公用交換電話網路 (PSTN) 閘道間的媒體資料流。 首先決定不佳的資料流閾值的目標。 不佳的資料流通常是 PacketLossRate \> .01 或 PacketLossRateMax \> .05。 另一個令人滿意的目標是 PoorStreamsRatio \< 2%。 接下來，使用詳細的查詢來找出與不佳的資料流的中繼伺服器和閘道配對、 調查不佳的資料流的原因、 查看不佳的資料流路徑中的網路設備、 修復不佳的資料流，並定義網路最佳或 「 金會員 」 設定設備。 若要維護您成就，實作程序和工具來管理組態漂移並報告新的問題領域。

最後，檢查您 PSTN 閘道的狀況度量資訊。 識別顯示健康情況及定義對其目標的統計資料。 沒有特定的指引這裡提供最多可能閘道可用。 一旦建立目標，修復達成目標; 視程序中您可能會定義閘道 」 金會員 」 或最佳組態。 若要維護您成就，實作程序和工具來管理組態漂移並報告新的問題領域。 請注意韌體和軟體更新可能會改變您的組態，或將引導您要變更 「 黃金 」 設定的定義，因此方法與照護這些活動。

</div>

<span id="LastMi"></span>

<div>

## <a name="the-last-mile-road"></a>最後一個哩隨身攜帶

兩個方式用戶端連線至網路，有線預期提供最高品質，因此這必須是您最初的焦點的最後一個哩問題。 使用 CQM 有線的查詢 (LastMile\_0\_有線) 和它會提供不良的資料流比率資料。 我們建議在定義的目標 PoorStreamsRatio \< 5%的站台\>300 資料流)。 若要達到目標，修復排序從最壞打算最佳，並實作 QoS 的子網路。

有線連線品質最佳化之後，改善無線品質變得更容易因為無線基礎結構在有線核心頂端位於每個位置。 在具有有線品質良好的網站不佳無線資料流必須歸因於特定的無線元件。 CQM 無線查詢 (LastMile\_1\_無線) 的日期範圍上運作，且會傳回所有內部的無線資料流環境中的 Lync 用戶端至或來自會議伺服器或中繼伺服器。 我們建議在定義的目標 PoorStreamsRatio \< 5%的站台\>300 資料流)。 若要達到目標，修復排序從最壞打算最佳，並實作 QoS 的子網路。

</div>

<span id="EndPt"></span>

<div>

## <a name="the-end-points-road"></a>結束點隨身攜帶

從開始到結束點隨身攜帶耳機與其他裝置以產生可接受的品質搭配 Lync 時已知的相關事宜。 我們建議在目標 AvgSendListen MOS \> 3.6 的實作方式具有超過 100 個資料流。)識別問題的裝置來達成目標，以及修正或加以取代。

接下來，檢查裝置或電腦處理的使用者通話音訊。 建議的目標品質評量是 AudioMicGlitchRate \<= 1。 當您找出使用者系統的最佳系統組態，定義 「 最佳 」 的電腦組態，包括驅動程式版本。

現在檢查音訊資料流採取從 Lync 端點系統，這可能會造成音訊品質不佳的網路路徑。 如果音訊，透過 VPN 連線可能會看到延遲問題。 如果內部 Lync 用戶端無法建立另一個內部的 Lync 用戶端，雙方或對等通話直接媒體資料流，它將會回復為轉送透過 Lync Edge server，重新導向延遲問題，以及增加的潛在的路徑遺失及抖動。 我們建議您透過 VPN 定義 0%的媒體品質計量。 當您修復達到您設定的目標，找出問題子網路，並調查防火牆規則、 封包 shapers，以及其他相關網路設備組態。

傳輸控制通訊協定 (TCP) 或使用者資料包通訊協定 (UDP)，可以使用 IP 封包。 TCP 是最佳的資料流。 UDP 是無連線且更有效率的媒體因為 TCP 復原機制無法解決即時媒體中的遺失。 Lync 一律偏好 UDP，但如果無法建立 UDP 工作階段，就會還原成 TCP。 透過 TCP 的媒體工作階段會透過 UDP 展示差的品質。 建議 0%連線的品質定義 over TCP。 當您修復達到您設定的目標，找出問題子網路，並調查防火牆規則、 封包 shapers，以及其他相關網路設備組態。

</div>

<span id="ServMgt"></span>

<div>

## <a name="service-management"></a>服務管理

服務管理功能的結束狀態的 CQM，以及所有三個通道的目的地。 若要維護的通話品質的高層級，請監視這些區域：

1.  **使用者**-修復活動應使用者滿意度中會顯示可測量的增加。 您可以測量這問題票證或其他的意見反應機制。 您也可以發佈品質計量。

2.  **處理程序**-定義每日、 每週及每月處理程序 operationalize CQM。 監視節奏持續開始較高的頻率 （每日），您會修復時，並移至較低頻率 （每月） 為您穩定。

3.  [**工具**]-找出兩個量值的工具及修復。 您可能會發現很有用來自動化執行 CQM 查詢以支援您的程序。 修復可能需要額外的工具，以強制執行標準化的設定網路元素或疑難排解遺失不佳的資料流中的範例。

</div>

<span id="BoardGm"></span>

<div>

## <a name="board-game-rules"></a>棋盤遊戲規則

您可以使用此海報 CQM 實作參考或遊戲的身分來練習概念。 若要播放，您將需要一個六角死及所提供的卡片。 使用標準 Avery 5871 名片上要列印的卡片可下載的版本。

遊戲是 3 的玩家。 有三種路徑的玩家可用來達成所需的品質，並達到中心服務管理狀態： 伺服器廠、 結束點和最後一個哩。 每個路徑有停駐點沿著您 Assert 品質目標，達成目標，以及維護系統的層面的方式。 將卡放在指定的區域，與上述並再繪製 5 卡。 檢閱已繪製，並將其放在相關棋盤區段上的卡片。 每個玩家卡透過依其路徑移動逐步解說，要達成這些目標、 和維護的服務層級宣告品質目標。 所有的玩家達到中心服務管理狀態時，就會完成遊戲。 遊戲卡下載會提供更詳細的規則。

**Assert**品質目標，以檢閱適用於該目標和狀態參數能功能將而且不會選擇要接受。 我們建議的起始點，但您必須進行的最後呼叫。 例外狀況是 KHI 資料，其中應該使用 Microsoft 所建立的標準。 請參閱隨附 KHI 海報。

若要在遊戲**Achieve**使用取代 KHI 資料及系統查詢所提供的卡片。 如果您沒有不繪製指定的外觀與相關的卡片遊戲開頭，您可以繼續過去它。 如果沒有相關的卡片，回復死。 如果您復原在卡片上編號] 下，您都已成功。 如果您將位於或超過指定的數字，您必須從艙面繪製其他卡片。 如果卡片會指出兩個以上的玩家需要回復，它們必須全部回復成功。

要**維持**在遊戲，狀態出過吵雜有關該方面的 Lync 環境與服務管理計劃。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 網路指南](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[維護狀況良好的 Lync 伺服器 Foundation 主要的健康狀態指標：](http://go.microsoft.com/fwlink/?linkid=391838)  
[Lync 通話品質方法](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

