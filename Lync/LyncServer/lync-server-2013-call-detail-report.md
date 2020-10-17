---
title: Lync Server 2013：詳細通話報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Detail Report
ms:assetid: 38862e35-3fec-41b9-a035-0b301942d446
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558637(v=OCS.15)
ms:contentKeyID: 48183843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ef309873ef51e06903123dfb5a1b6ecf68b4ea8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502750"
---
# <a name="call-detail-report-in-lync-server-2013"></a>Lync Server 2013 中的詳細通話報告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-05_

[通話詳細資料包告] 提供個別通話的詳細資訊，請參閱報告包括所有的經驗品質統計資料，以及 Lync Server 收集的統計資料，劃分成報表區段，例如：

  - 通話資訊

  - 呼叫者裝置和訊號計量

  - 被呼叫者裝置和訊號計量

  - 呼叫者用戶端事件

  - 被呼叫者用戶端事件

  - 音訊資料流 (呼叫者至被呼叫者)

  - 視訊資料流 (呼叫者至被呼叫者)

  - 音訊資料流 (被呼叫者至呼叫者)

  - 視訊資料流 (被呼叫者至呼叫者)

請注意，在指定報告上所見的類別及計量取決於兩個因素：工作階段類型，以及工作階段中所使用的端點類型。例如，純音訊通話不會報告視訊資料流計量，這是因為該通話沒有視訊資料流。同樣地，報告可能會只列出呼叫者統計資料，而沒有被呼叫者統計資料。這通常是因為被呼叫者並非使用 SIP 相容的裝置。端點會負責在通話結束時報告統計資料；不過行動電話 (對 SIP 或 SIP 統計資料一無所悉) 就無法報告該類資訊。如果您與某人通話，而他們使用行動電話接聽，則通話結束時將無法從該行動電話取得報告。

當您想確認指定通話為何發生媒體品質問題的確切原因時，[通話詳細資料報告] 最派得上用場。

<div>

## <a name="accessing-the-call-detail-report"></a>存取通話詳細資料報告

您可從下列報告中存取 [通話詳細資料報告]：

  - [在 [Lync Server 2013] 中的位置報告](lync-server-2013-location-report.md)，按一下 [通話量] 或 [低通話百分比] 計量 () 

  - [Lync Server 2013 (中的媒體質量摘要報告](lync-server-2013-media-quality-summary-report.md)：按一下 [通話量] 或 [通話百分比] 度量值) 

  - [Lync server 2013 (中的媒體質量比較報告](lync-server-2013-media-quality-comparison-report.md)，方法是按一下 [ [lync server 2013] 中的 [通話清單報告](lync-server-2013-call-list-report.md)]，然後按一下 [詳細資料] 度量) 。

  - [在 Lync Server 2013 (中](lync-server-2013-server-performance-report.md)，按一下 [通話量] 或 [通話不良百分比] 度量，以執行伺服器效能報告) 

  - [Lync Server 2013 (中的通話清單報告](lync-server-2013-call-list-report.md)，請按一下詳細資料度量) 

從 [通話詳細資料包告] 中，按一下下列其中一個計量，即可 [在 Lync Server 2013 中存取裝置報告](lync-server-2013-device-report.md) ：

  - 擷取裝置

  - 轉換裝置

按一下 [A/V Edge Server] 計量也可存取 [伺服器媒體品質趨勢報告]。

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a>發揮通話詳細資料報告的最大效用

[通話詳細資料報告] 通常涵蓋超過 250 個不同的計量，包括麥克風時間戳記漂移、低 SNR 時間及近端回音時間等項目。如果不記得這些計量實際上測量什麼，可嘗試將滑鼠移至計量標籤上，通常會顯示工具提示來說明該計量。

如果找不到某個計量，可在搜尋方塊中輸入部分計量標籤，然後按一下 [搜尋]。例如，如果找不到 [低 Low SNR 時間] 計量，可在搜尋方塊中輸入 SNR，然後按一下 [搜尋]。

請注意，報告只追蹤通話的相關資訊。 不會記錄通話本身。

</div>

<div>

## <a name="filters"></a>篩選

無。您無法篩選詳細通話報告。

</div>

<div>

## <a name="metrics"></a>指標

下表列出每個通話的詳細通話報告。

### <a name="call-detail-report-metrics"></a>詳細通話報告計量

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>姓名</th>
<th>可以排序這個項目嗎？</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>  呼叫者 PAI</strong></p></td>
<td><p>否</p></td>
<td><p>撥打通話之使用者的 P-Asserted-Identity。P-Asserted-Identity 可用來傳達信任網路中之使用者經驗證的身分識別。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫者 URI</strong></p></td>
<td><p>否</p></td>
<td><p>撥打通話之使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>呼叫者者端點</strong></p></td>
<td><p>否</p></td>
<td><p>用來撥打通話的裝置。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫者使用者代理程式</strong></p></td>
<td><p>否</p></td>
<td><p>撥打通話之裝置上所使用的軟體。</p></td>
</tr>
<tr class="odd">
<td><p><strong>通話開始</strong></p></td>
<td><p>否</p></td>
<td><p>啟動通話的日期與時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>中繼伺服器旁路通話</strong></p></td>
<td><p>否</p></td>
<td><p>指出通話是連接至 PSTN 語音閘道或完整 IP-PBX，而未通過中繼伺服器。</p></td>
</tr>
<tr class="odd">
<td><p><strong>呼叫者 OS</strong></p></td>
<td><p>否</p></td>
<td><p>呼叫者電腦的作業系統。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫者 CPU</strong></p></td>
<td><p>否</p></td>
<td><p>安裝在啟動通話之使用者電腦上的 CPU。</p></td>
</tr>
<tr class="odd">
<td><p><strong>呼叫者 CPU 核心編號</strong></p></td>
<td><p>否</p></td>
<td><p>啟動通話者所使用電腦的處理器編號。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫者 CPU 速度</strong></p></td>
<td><p>否</p></td>
<td><p>啟動通話者所使用電腦的 CPU 時脈速度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>呼叫者 CPU 模擬</strong></p></td>
<td><p>否</p></td>
<td><p>啟動通話者所使用電腦上的虛擬化 (若有的話)。</p></td>
</tr>
<tr class="even">
<td><p><strong>被呼叫者 PAI</strong></p></td>
<td><p>否</p></td>
<td><p>受邀加入通話之使用者的 P-Asserted-Identity。P-Asserted-Identity 可用來傳達信任網路中之使用者經驗證的身分識別。</p></td>
</tr>
<tr class="odd">
<td><p><strong>被呼叫者 URI</strong></p></td>
<td><p>否</p></td>
<td><p>被呼叫使用者的 SIP 位址。</p></td>
</tr>
<tr class="even">
<td><p><strong>被呼叫者端點</strong></p></td>
<td><p>否</p></td>
<td><p>用來接收通話的裝置。</p></td>
</tr>
<tr class="odd">
<td><p><strong>被呼叫者使用者代理程式</strong></p></td>
<td><p>否</p></td>
<td><p>接收通話之裝置上所使用的軟體。</p></td>
</tr>
<tr class="even">
<td><p><strong>Duration</strong></p></td>
<td><p>否</p></td>
<td><p>通話時間長度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>媒體旁路警告旗標</strong></p></td>
<td><p>否</p></td>
<td><p>略過中繼伺服器時發出的警告。</p></td>
</tr>
<tr class="even">
<td><p><strong>被呼叫者 OS</strong></p></td>
<td><p>否</p></td>
<td><p>被呼叫使用者的電腦作業系統。</p></td>
</tr>
<tr class="odd">
<td><p><strong>被呼叫者 CPU</strong></p></td>
<td><p>否</p></td>
<td><p>安裝在被呼叫使用者電腦上的 CPU。</p></td>
</tr>
<tr class="even">
<td><p><strong>被呼叫者核心編號</strong></p></td>
<td><p>否</p></td>
<td><p>被呼叫者所使用電腦中的處理器編號。</p></td>
</tr>
<tr class="odd">
<td><p><strong>被呼叫者 CPU 速度</strong></p></td>
<td><p>否</p></td>
<td><p>被呼叫者所使用電腦中的 CPU 時脈速度。</p></td>
</tr>
<tr class="even">
<td><p><strong>被呼叫者 CPU 虛擬</strong></p></td>
<td><p>否</p></td>
<td><p>被呼叫者所使用電腦上的虛擬化 (若有的話)。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

