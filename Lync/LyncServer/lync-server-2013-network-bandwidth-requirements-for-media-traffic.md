---
title: Lync Server 2013 媒體流量的網路頻寬需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network bandwidth requirements for media traffic
ms:assetid: 83e83b16-0f0e-4d87-901a-0faa4618cdc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688118(v=OCS.15)
ms:contentKeyID: 49733716
ms.date: 09/25/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 684f13a10c066e8902bed0024d7546017450ee9e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-bandwidth-requirements-for-media-traffic-in-lync-server-2013"></a>Lync Server 2013 中媒體流量的網路頻寬需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-09-24_

網路規劃的一個重要部分是，確保您的網路能夠處理 Lync Server 產生的媒體流量。 本節可協助您規劃該媒體流量。

<div>

## <a name="media-traffic-network-usage"></a>媒體流量網路使用量

媒體流量的頻寬使用可能會因為不同的變數數量（例如編解碼器使用量、解析度及活動層級）而計算的難度。 [頻寬使用量] 是所使用的編解碼器及資料流程活動（這兩者在不同情況之間有所不同）的功能。 下表列出 Lync Server 2013 案例中常用的音訊編解碼器。

### <a name="audio-codec-bandwidth"></a>音訊編解碼器頻寬

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>音訊編解碼器</th>
<th>案例</th>
<th>音訊負載高位元速率（KBPS）</th>
<th>僅限頻寬音訊負載和 IP 報頭（Kbps）</th>
<th>頻寬音訊負載、IP 標頭、UDP、RTP 與 SRTP （Kbps）</th>
<th>頻寬音訊負載、IP 標頭、UDP、RTP、SRTP 及轉寄錯誤修正（Kbps）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTAudio Wideband</p></td>
<td><p>對等</p></td>
<td><p>29.0</p></td>
<td><p>45.0</p></td>
<td><p>57.0</p></td>
<td><p>86.0</p></td>
</tr>
<tr class="even">
<td><p>RTAudio Narrowband</p></td>
<td><p>對等、PSTN</p></td>
<td><p>11.8</p></td>
<td><p>27.8</p></td>
<td><p>39.8</p></td>
<td><p>51.6</p></td>
</tr>
<tr class="odd">
<td><p>G. 722</p></td>
<td><p>會議</p></td>
<td><p>64.0</p></td>
<td><p>80.0</p></td>
<td><p>95.6</p></td>
<td><p>159.6</p></td>
</tr>
<tr class="even">
<td><p>G. 722 身歷聲</p></td>
<td><p>對等、會議</p></td>
<td><p>128.0</p></td>
<td><p>144.0</p></td>
<td><p>159.6</p></td>
<td><p>223.6</p></td>
</tr>
<tr class="odd">
<td><p>G. 711</p></td>
<td><p>PSTN、會議</p></td>
<td><p>64.0</p></td>
<td><p>80.0</p></td>
<td><p>92.0</p></td>
<td><p>156.0</p></td>
</tr>
<tr class="even">
<td><p>Siren</p></td>
<td><p>會議</p></td>
<td><p>16.0</p></td>
<td><p>32.0</p></td>
<td><p>47.6</p></td>
<td><p>63.6</p></td>
</tr>
</tbody>
</table>


上表中的頻寬數是以 20ms packetization 為基礎（每秒50個數據包），以及 Siren 和 G. 722 包含來自會議案例的額外安全即時傳輸通訊協定（SRTP）額外負荷，並假設資料流程的作用是100%。 當連結上有資料包遺失時，會動態使用轉寄錯誤修正（FEC），以協助維持音訊資料流程的品質。

722編解碼器的身歷聲版是由以 Lync 房間系統為基礎的系統所使用，它可啟用身歷聲麥克風捕獲，讓監聽器能夠更容易地區分會議室中的多個 talkers。

在影片中，預設的編解碼器是先進/MPEG-4 的第10部分高級視頻編碼標準，搭配其可伸縮的影片編碼延伸，以提供時態可伸縮性。 為了維持 Lync 2010 或 Office Communicator 2007 R2 用戶端之間的互通性，在 Lync 2013 與舊版用戶端之間，仍會使用 RTVideo 編解碼器進行對等通話。 Lync 2013 和舊版用戶端的會議會話中，Lync 2013 端點可能會使用兩個視頻編解碼器來編碼影片，並傳送 bitstream 到 Lync 2013 和 RTVideo bitstream 至 Lync 2010 或 Office Communicator 2007 R2 用戶端。

所需的頻寬取決於解析度、品質和畫面播放速率。 針對每個解決方法，有兩個有趣的位元速率：

  - **[最大有效負載位元速率**   ] 這是 Lync 2013 端點將針對此解析度所支援的最大畫面播放速率進行解析的位元速率。 這個值很有趣，因為它允許最高品質和畫面播放速率的影片。

  - **最小有效負載比**   對，Lync 2013 端點會切換到下一個較低解析度的位元速率。 為了保證特定的解析度，可用的影片有效載荷比對該解析度而言不得低於此最小位元速率。 這個值很有趣，因此您可以在最大比對無法使用或不切實際的情況下，瞭解可能的最小值。 對於某些使用者來說，此類低比對的影片可能會被視為無法接受的影片體驗，所以在考慮這些最低的影片負載位元速率時，請務必小心。 請注意，對於只有少量或不含使用者移動的影片畫面，實際比對的情況可能也會暫時下降低於最小位元速率。

Lync 2013 支援更多解析度。 這可讓您更好地調整不同網路頻寬和接收用戶端功能。 此外，Lync 2013 的預設長寬比已改為16:9。 網路攝像頭仍支援4:3 長寬比，不允許在16:9 長寬比中捕獲。

### <a name="video-resolution-bandwidth"></a>影片解析度頻寬

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>影片編碼解碼器</th>
<th>解析度和長寬比</th>
<th>最大視頻有效負載位元速率（Kbps）</th>
<th>最小視頻有效負載位元速率（Kbps）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>H-p</p></td>
<td><p>320x180 （16:9）</p>
<p>212x160 （4:3）</p></td>
<td><p>250</p></td>
<td><p>工資</p></td>
</tr>
<tr class="even">
<td><p>H-p/RTVideo</p></td>
<td><p>424x240 （16:9））</p>
<p>320x240 （4:3</p></td>
<td><p>350</p></td>
<td><p>100</p></td>
</tr>
<tr class="odd">
<td><p>H-p</p></td>
<td><p>480x270 （16:9）</p>
<p>424x320 （4:3）</p></td>
<td><p>450</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>H-p/RTVideo</p></td>
<td><p>640x360 （16:9）</p>
<p>640x480 （4:3）</p></td>
<td><p>800</p></td>
<td><p>300</p></td>
</tr>
<tr class="odd">
<td><p>H-p</p></td>
<td><p>848x480 （16:9）</p></td>
<td><p>1500</p></td>
<td><p>400</p></td>
</tr>
<tr class="even">
<td><p>H-p</p></td>
<td><p>960x540 （16:9）</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
<tr class="odd">
<td><p>H-p/RTVideo</p></td>
<td><p>1280x720 （16:9）</p></td>
<td><p>2500</p></td>
<td><p>700</p></td>
</tr>
<tr class="even">
<td><p>H-p</p></td>
<td><p>1920x1080 （16:9）</p></td>
<td><p>4000</p></td>
<td><p>1500</p></td>
</tr>
<tr class="odd">
<td><p>H-p/RTVideo</p></td>
<td><p>960x144 （20:3）</p></td>
<td><p>500</p></td>
<td><p>工資</p></td>
</tr>
<tr class="even">
<td><p>H-p</p></td>
<td><p>1280x192 （20:3）</p></td>
<td><p>1000</p></td>
<td><p>250</p></td>
</tr>
<tr class="odd">
<td><p>H-p</p></td>
<td><p>1920x288 （20:3）</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


[視頻 FEC] 包含在使用中的 [影片] 負載比對，因此不會有不同的值搭配影片 FEC，也不會顯示 FEC。

端點不會持續傳輸音訊或視頻包。 視情況而定，會根據不同的資料流程活動層級，指出傳送資料流程的頻率。 資料流程的活動取決於媒體和案例，不依賴于使用的編解碼器。 在對等案例中：

  - 端點只會在使用者朗讀時傳送音訊資料流程。

  - 這兩個參與者都會收到音訊資料流程。

  - 如果使用影片，兩個端點都會在整個通話期間傳送和接收影片串流。

  - 對於只有很少或無運動的影片場景，實際比對的影片可能會略過低，因為視頻編解碼器將會略過影片的編碼區域而不會變更。

在會議案例中：

  - 端點只會在使用者朗讀時傳送音訊資料流程。

  - 所有參與者都會收到音訊資料流程。

  - 如果使用影片，所有參與者都可以接收最多五個接收影片資料流程與一個全景（例如，長寬比20:3）影片資料流程。 根據預設，五個接收影片資料流程是以使用中的演講者記錄為基礎，但使用者也可以手動選取他們要接收影片串流的參與者。

  - 每個開啟使用者傳送影片串流的參與者都會傳送一或多個影片串流。 Lync 2013 新增最多五個視頻資料流程的功能，以優化所有接收用戶端的視頻品質。 所傳送的實際影片資料流程數是由寄件者根據 CPU 功能、可用的上行頻寬，以及接收請求特定影片資料流程的用戶端數來決定。 最常見的情況是，當舊版用戶端加入會議時，會傳送一個 .H 和一個 RTVideo 影片資料流程。 另一個常見的案例是傳送多個 .H 視頻資料流程（例如，有不同的視頻解析度），以適應不同的接收器要求。

除了即時傳輸通訊協定（RTP）流量的音訊和視頻媒體所需頻寬之外，即時傳輸控制通訊協定（RTCP）還需要頻寬。 RTCP 是用來報告 RTP 資料流程的統計資料和帶外控制。 針對規劃，請使用下表中的頻寬數來 RTCP 流量。 這些值代表用於 RTCP 的最大頻寬，以及音訊與影片資料流程之間的不同，因為控制資料的差異

### <a name="rtcp-bandwidth"></a>RTCP 頻寬

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>媒體</th>
<th>RTCP 最大頻寬（Kbps）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音訊</p></td>
<td><p>500</p></td>
</tr>
<tr class="even">
<td><p>影片（僅限 .H 或 RTVideo 傳送/接收）</p></td>
<td><p>第</p></td>
</tr>
<tr class="odd">
<td><p>影片（要傳送/接收的 RTVideo 和）</p></td>
<td><p>工資</p></td>
</tr>
</tbody>
</table>


針對容量規劃而言，以下兩個頻寬是重要的：

  - **最大頻寬（不含 FEC**   資料流程將會使用的最大頻寬），包括資料流程的一般活動以及案例中使用的一般編解碼器（不 FEC）。這是資料流程達到100% 活動且沒有資料包遺失觸發使用 FEC 的頻寬。這對計算必須指派多少頻寬以允許在特定情況下使用編解碼器是很有趣的。 

  - **最大頻寬為 FEC**   資料流程所使用的最大頻寬，包括資料流程的一般活動，以及 FEC 中使用之典型的編解碼器。 這是資料流程達到100% 活動時的頻寬，且有資料包遺失觸發使用 FEC 來改善品質。 這對計算必須指派多少頻寬以允許在特定案例中使用編解碼器，並允許使用 FEC 在資料包遺失情況下保持品質。 

下表也會列出額外的頻寬值（**一般頻寬**）。 這是資料流程佔用的平均頻寬，包括資料流程的一般活動，以及案例中使用的典型編解碼器。 這個頻寬可用來 approximating 媒體流量在任何指定時間佔用多少頻寬，但不應該用來進行容量規劃，因為當活動等級高於平均時，個別通話就會超過這個值。 下表中的一般視頻串流頻寬是依據測量的客戶資料所觀察到的不同視頻解析度。 例如，在點對點工作階段中，大部分的使用者都會使用預設的 [視頻轉譯] 視窗，而某些百分比的使用者可能會增加或最大化 Lync 應用程式，以允許較高的視頻解析度。

下清單格針對各種案例提供這三種頻寬值。

### <a name="audiovideo-capacity-planning-for-peer-to-peer-sessions"></a>點對點工作階段的音訊/視頻容量規劃

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>媒體</th>
<th>編碼</th>
<th>典型的資料流程頻寬（Kbps）</th>
<th>不含 FEC 的最大串流頻寬</th>
<th>含 FEC 的最大串流頻寬</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音訊</p></td>
<td><p>RTAudio Wideband</p></td>
<td><p>39.8</p></td>
<td><p>62</p></td>
<td><p>91</p></td>
</tr>
<tr class="even">
<td><p>音訊</p></td>
<td><p>RTAudio Narrowband</p></td>
<td><p>29.3</p></td>
<td><p>44.8</p></td>
<td><p>56.6</p></td>
</tr>
<tr class="odd">
<td><p>呼叫 Lync 2013 端點時的主要影片</p></td>
<td><p>H-p</p></td>
<td><p>460</p></td>
<td><p>4010（適用于1920x1080 的最大解析度）</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="even">
<td><p>呼叫 Lync 2010 或 Office Communicator 2007 R2 端點時的主要影片</p></td>
<td><p>RTVideo</p></td>
<td><p>460</p></td>
<td><p>2510（適用于1280x720 的最大解析度）</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>呼叫 Lync 2013 端點時的全景影片</p></td>
<td><p>H-p</p></td>
<td><p>190</p></td>
<td><p>2010（適用于1920x288 的最大解析度）</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="even">
<td><p>呼叫 Lync 2010 或 Office Communicator 2007 R2 端點時的全景影片</p></td>
<td><p>RTVideo</p></td>
<td><p>190</p></td>
<td><p>510（適用于960x144 的最大解析度）</p></td>
<td><p>不適用</p></td>
</tr>
</tbody>
</table>


### <a name="audiovideo-capacity-planning-for-conferences"></a>會議的音訊/視頻容量規劃

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>媒體</th>
<th>典型的編解碼器</th>
<th>典型的資料流程頻寬（Kbps）</th>
<th>不含 FEC 的最大串流頻寬</th>
<th>含 FEC 的最大串流頻寬</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音訊</p></td>
<td><p>G. 722</p></td>
<td><p>46.1</p></td>
<td><p>100.6</p></td>
<td><p>164.6</p></td>
</tr>
<tr class="even">
<td><p>音訊</p></td>
<td><p>Siren</p></td>
<td><p>25.5</p></td>
<td><p>52.6</p></td>
<td><p>68.6</p></td>
</tr>
<tr class="odd">
<td><p>主要視頻接收</p></td>
<td><p>H-p 和/或 RTVideo</p></td>
<td><p>260</p></td>
<td><p>8015</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="even">
<td><p>傳送主要影片</p></td>
<td><p>H-p 和/或 RTVideo</p></td>
<td><p>270</p></td>
<td><p>8015</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>全景視頻接收</p></td>
<td><p>H-p 和/或 RTVideo</p></td>
<td><p>190</p></td>
<td><p>2010（適用于1920x288 的最大解析度）</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="even">
<td><p>[全景視頻傳送]</p></td>
<td><p>H-p 和/或 RTVideo</p></td>
<td><p>190</p></td>
<td><p>2515（使用多個解析度/編解碼器傳送 bitstreams</p></td>
<td><p>不適用</p></td>
</tr>
</tbody>
</table>


在主要影片中，典型和最大串流頻寬是在所有接收的視頻資料流程中，以及所有傳送視頻資料流程的匯總頻寬。 即使有多個視頻資料流程，一般的影片頻寬也小於對等案例中，因為許多視訊會議都使用內容共用來產生較小的影片視窗，因而較小的視頻解析度。 受支援的匯總影片負載頻寬上限為 8000 Kbps，即傳送和接收資料流程（例如，如果有兩個傳入1920x1080p 影片串流）。

全景影片的典型資料流程頻寬是以目前可用的裝置為基礎，僅可進行960x144 全景影片。 一旦有1920x288 全景影片的裝置可供使用，一般的資料流程頻寬預計會增加。

### <a name="audio-capacity-planning-for-pstn"></a>PSTN 的音訊容量規劃

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>媒體</th>
<th>典型的編解碼器</th>
<th>典型的資料流程頻寬（Kbps）</th>
<th>不含 FEC 的最大串流頻寬</th>
<th>含 FEC 的最大串流頻寬</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音訊</p></td>
<td><p>G. 711 （在會議中包含 PSTN 參與者）</p></td>
<td><p>64.8</p></td>
<td><p>97</p></td>
<td><p>161</p></td>
</tr>
<tr class="even">
<td><p>音訊</p></td>
<td><p>RTAudio Narrowband</p></td>
<td><p>30.9</p></td>
<td><p>44.8</p></td>
<td><p>56.6</p></td>
</tr>
</tbody>
</table>


這些資料表中的網路頻寬數只代表單向流量，且針對每個資料流程的 RTCP 流量負荷，加上 5 Kbps。 對於影片而言，會使用最大的視頻位元速率來計算最大的資料流程。

</div>

</div>

<span> </span>

</div>

</div>

</div>

