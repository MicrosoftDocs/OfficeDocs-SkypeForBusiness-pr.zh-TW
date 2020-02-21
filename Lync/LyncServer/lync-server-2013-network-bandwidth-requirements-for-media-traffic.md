---
title: 媒體流量的 Lync Server 2013 網路頻寬需求
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
ms.openlocfilehash: a89517fb83fa5cd0c7defd62b47f7ddf9b29a303
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="network-bandwidth-requirements-for-media-traffic-in-lync-server-2013"></a>Lync Server 2013 中的媒體流量網路頻寬需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015年-09-24_

網路規劃中一個重要的部份是確保網路能夠處理 Lync Server 所產生的媒體流量。本節將協助您規劃這類媒體流量。

<div>

## <a name="media-traffic-network-usage"></a>媒體流量網路使用方式

由於不同變數 (例如轉碼器使用率、解析度和活動層級) 的數目，計算媒體流量頻寬使用率將是一項挑戰。 頻寬使用率是使用的轉碼器和資料流活動的函數，這兩者會根據案例的不同而有所差異。 下表列出 Lync Server 2013 案例中普遍使用的音訊轉碼器。

### <a name="audio-codec-bandwidth"></a>音訊轉碼器頻寬

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
<th>音訊轉碼器</th>
<th>案例</th>
<th>音訊承載位元速率 (KBPS)</th>
<th>僅頻寬音訊承載和 IP 標頭 (Kbps)</th>
<th>頻寬音訊承載、IP 標頭、UDP、RTP 和 SRTP (Kbps)</th>
<th>頻寬音訊承載、IP 標頭、UDP、RTP、SRTP 和正向錯誤更正 (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTAudio 寬頻</p></td>
<td><p>端對端</p></td>
<td><p>29.0</p></td>
<td><p>45.0</p></td>
<td><p>57.0</p></td>
<td><p>86.0</p></td>
</tr>
<tr class="even">
<td><p>RTAudio 窄頻</p></td>
<td><p>對等，PSTN</p></td>
<td><p>11.8</p></td>
<td><p>27.8</p></td>
<td><p>39.8</p></td>
<td><p>51.6</p></td>
</tr>
<tr class="odd">
<td><p>G.722</p></td>
<td><p>會議</p></td>
<td><p>64.0</p></td>
<td><p>80.0</p></td>
<td><p>95.6</p></td>
<td><p>159.6</p></td>
</tr>
<tr class="even">
<td><p>G.722 立體聲</p></td>
<td><p>對等，會議</p></td>
<td><p>128.0</p></td>
<td><p>144.0</p></td>
<td><p>159.6</p></td>
<td><p>223.6</p></td>
</tr>
<tr class="odd">
<td><p>G.711</p></td>
<td><p>PSTN 會議</p></td>
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


上表中的頻寬數字以 20ms 封包 (每秒 50 個封包) 為依據，對於 Siren 和 G.722 包括會議案例中的安全即時傳輸通訊協定 (SRTP) 額外負荷，因此假定資料流處於 100% 活動狀態。連結上發生封包遺失時將動態使用正向錯誤更正 (FEC)，以協助維護音訊資料流的品質。

系統根據 Lync 會議室系統，可讓立體聲麥克風擷取，以便更妥善地辨別會議室中的多位說話者包括代表接聽程式使用 G.722 轉碼器的立體聲版本。

對於視訊，預設轉碼器是 H.264/MPEG-4 Part 10 Advanced Video Coding 標準版 (加裝暫時擴充的可調整視訊編碼擴充)。 若要維護的互通性與 Lync 2010 或 Office Communicator 2007 R2 的用戶端，或 RTVideo 轉碼器仍然適用於 Lync 2013 與舊版用戶端之間的對等通話。 兼具會議工作階段，Lync 2013 和 Lync 2013 的舊版用戶端端點可能編碼使用這兩個視訊轉碼器的視訊，並將 H.264 bitstream 傳送給 Lync 2013 和 Lync 2010 或 Office Communicator 2007 R2 的用戶端或 RTVideo bitstream。

所需頻寬依解析度、品質和播放速率而定。 對於每個解析度，有兩個特別的位元速率：

  - **最大的承載位元速率**   這是 Lync 2013 端點將用來支援此解決方案的最大畫面速率解析度的位元速率。 此值特別的原因在於它允許最高品質和播放速率視訊。

  - **最小的承載位元速率**   這是位元速率下其 Lync 2013 端點會切換至下一個較低的解析度。 為了確保達到一定的解析度，可用的視訊承載位元速率不可低於該解析度的位元速率下限。 此值很特別，您可以從而了解最大位元速率不可用或不可行的情況下可能的最小值。 對於某些使用者，如此的低位元速率視訊可能會被視為無法接受的視訊體驗，因此請謹慎使用這些位元速率。 請注意，對於使用者很少或沒有動作的視訊場景，實際的位元速率可能暫時低於位元速率下限。

Lync 2013 支援許多更多解決方法。 這能夠讓您更加調整為不同的網路頻寬和接收用戶端功能。 除了 Lync 2013 的預設外觀比例已變更為 16:9。 對於無法以 16:9 外觀比例擷取的網路攝影機，仍然支援 4:3 外觀比例。

### <a name="video-resolution-bandwidth"></a>視訊解析度頻寬

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>視訊轉碼器</th>
<th>解析度和外觀比例</th>
<th>最大視訊承載位元速率 (Kbps)</th>
<th>最小視訊承載位元速率 (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>320 x 180 (16:9)</p>
<p>212 x 160 (4:3)</p></td>
<td><p>250</p></td>
<td><p>15 </p></td>
</tr>
<tr class="even">
<td><p>H.264/RTVideo</p></td>
<td><p>424 x 240 (16:9))</p>
<p>320x240 (4:3</p></td>
<td><p>350</p></td>
<td><p>100</p></td>
</tr>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>480 x 270 度 (16:9)</p>
<p>424 x 320 (4:3)</p></td>
<td><p>450</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>H.264/RTVideo</p></td>
<td><p>640 x 360 (16:9)</p>
<p>640 x 480 (4:3)</p></td>
<td><p>800</p></td>
<td><p>300</p></td>
</tr>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>848 x 480 (16:9)</p></td>
<td><p>1500</p></td>
<td><p>400</p></td>
</tr>
<tr class="even">
<td><p>H.264</p></td>
<td><p>高 960 x 540 (16:9)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
<tr class="odd">
<td><p>H.264/RTVideo</p></td>
<td><p>1280 x 720 (16:9)</p></td>
<td><p>2500</p></td>
<td><p>700</p></td>
</tr>
<tr class="even">
<td><p>H.264</p></td>
<td><p>1920 x 1080 (16:9)</p></td>
<td><p>4000</p></td>
<td><p>1500</p></td>
</tr>
<tr class="odd">
<td><p>H.264/RTVideo</p></td>
<td><p>960x144 (20:3)</p></td>
<td><p>500</p></td>
<td><p>15 </p></td>
</tr>
<tr class="even">
<td><p>H.264</p></td>
<td><p>1280 x 192 (20:3)</p></td>
<td><p>1000</p></td>
<td><p>250</p></td>
</tr>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>1920x288 (20:3)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


使用視訊 FEC 時，它包括在視訊承載位元速率中，因此有還是沒有視訊 FEC，都沒有單獨的值。

端點不會持續對音訊或視訊封包進行資料流處理。依據不同的案例，有不同層級的資料流活動來指示為資料流傳送封包的頻率。資料流的活動依媒體和案例而定，而不是取決於使用的轉碼器。在對等案例中：

  - 端點只在使用者說話時傳送音訊資料流。

  - 這兩個參與者都會接收音訊資料流。

  - 如果使用視訊，這兩個端點會在整個通話期間傳送和接收視訊資料流。

  - 對於很少或沒有動作的視訊場景，實際的位元速率可能暫時變得相當低，因為視訊轉碼器將略過視訊的編碼區域而不變更。

在會議案例中：

  - 端點只在使用者說話時傳送音訊資料流。

  - 所有參與者都會接收音訊資料流。

  - 如果使用視訊，所有參與者都能夠接收多達五個接收視訊資料流和一個全景 (例如，外觀比例 20:3) 視訊資料流。根據預設，五個接收視訊資料流以目前發言者記錄為依據，但是使用者也可手動選取要接收視訊資料流的參與者。

  - 各個開啟使用者傳送視訊資料流的參與者都將傳送一個或多個視訊資料流。 Lync 2013 新增視訊品質最佳化的所有接收的用戶端傳送多達五個視訊資料流的功能。 傳送的視訊資料流實際數目由傳送者依據 CPU 能力、可用上行連結頻寬和要求特定視訊串流的接收用戶端數目所決定。 最常見的情況是，舊版用戶端加入會議時，傳送一個 H.264 和一個 RTVideo 視訊資料流。 另一個常見的情況是，傳送多個 H.264 視訊資料流 (例如，不同視訊解析度的視訊資料流)，以配合不同的接收方要求。

除了音訊和視訊媒體的即時傳輸通訊協定 (RTP) 流量所需的頻寬，即時傳輸控制通訊協定 (RTCP) 也需要頻寬。RTCP 用於報告統計資料和頻外控制 RTP 資料流。為了規畫，將下表中的頻寬數字用於 RTCP 流量。這些值表示用於 RTCP 的最大頻寬及音訊和視訊資料流的不同 (由於控制資料的不同)

### <a name="rtcp-bandwidth"></a>RTCP 頻寬

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>媒體業</th>
<th>RTCP 最大頻寬 (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音訊</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>視訊 (僅傳送/接收 H.264 或 RTVideo)</p></td>
<td><p>10 </p></td>
</tr>
<tr class="odd">
<td><p>視訊 (傳送/接收 H.264 或 RTVideo)</p></td>
<td><p>15 </p></td>
</tr>
</tbody>
</table>


為了進行容量規劃，需要以下兩種頻寬：

  - **沒有 FEC 的最大頻寬**   會耗用資料流，包括沒有 FEC 的案例中的資料流及使用的一般轉碼器的一般活動的最大頻寬這是頻寬時，資料流處於 100%活動和沒有觸發使用 FEC 沒有封包遺失這是特別用於運算必須配置多少頻寬允許以供特定案例的轉碼器。 

  - **使用 FEC 的最大頻寬**   耗用資料流，包括資料流，使用 FEC 的案例中使用的一般轉碼器的一般活動的最大頻寬 這是頻寬時，資料流處於 100%活動和沒有觸發使用 FEC 改善品質的封包遺失。 這是特別用於運算必須配置多少頻寬允許以用於特定案例中，並允許 FEC 保留品質封包遺失的情況下使用的轉碼器。 

下表還列出其他頻寬值**一般頻寬**。 這是資料流使用的平均頻寬，包括資料流的一般活動和案例中使用的一般轉碼器。 此頻寬可用於近似運算媒體流量在任何指定時間使用多少頻寬，而不可用於容量規劃，因為活動層級高於平均值時個別通話將超過此值。 下表所列的一般視訊資料流以所測量的客戶資料中得到的不同視訊解析度為依據。 例如，在大部分的使用者會使用預設的端對端工作階段中影片轉譯視窗而部分的使用者百分比會增加或最大化 Lync 應用程式，以允許較高的視訊解析度。

下表提供了各種案例的三種頻寬值。

### <a name="audiovideo-capacity-planning-for-peer-to-peer-sessions"></a>對等工作階段的音訊/視訊容量規劃

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
<th>媒體業</th>
<th>轉碼器</th>
<th>一般資料流頻寬 (Kbps)</th>
<th>沒有 FEC 的最大資料流頻寬</th>
<th>具有 FEC 的最大資料流頻寬</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音訊</p></td>
<td><p>RTAudio 寬頻</p></td>
<td><p>39.8</p></td>
<td><p>62</p></td>
<td><p>91</p></td>
</tr>
<tr class="even">
<td><p>音訊</p></td>
<td><p>RTAudio 窄頻</p></td>
<td><p>29.3</p></td>
<td><p>44.8</p></td>
<td><p>56.6</p></td>
</tr>
<tr class="odd">
<td><p>呼叫 Lync 2013 端點時的主要視訊</p></td>
<td><p>H.264</p></td>
<td><p>460</p></td>
<td><p>4010 (對於 1920x1080 的最大解析度)</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="even">
<td><p>呼叫 Lync 2010 或 Office Communicator 2007 R2 端點時的主要視訊</p></td>
<td><p>或 RTVideo</p></td>
<td><p>460</p></td>
<td><p>2510 (對於 1280x720 的最大解析度)</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>呼叫 Lync 2013 端點時的全景視訊</p></td>
<td><p>H.264</p></td>
<td><p>190</p></td>
<td><p>2010 (對於 1920x288 的最大解析度)</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="even">
<td><p>呼叫 Lync 2010 或 Office Communicator 2007 R2 端點時的全景視訊</p></td>
<td><p>或 RTVideo</p></td>
<td><p>190</p></td>
<td><p>510 (對於 960x144 的最大解析度)</p></td>
<td><p>無</p></td>
</tr>
</tbody>
</table>


### <a name="audiovideo-capacity-planning-for-conferences"></a>會議的音訊/視訊容量規劃

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
<th>媒體業</th>
<th>一般轉碼器</th>
<th>一般資料流頻寬 (Kbps)</th>
<th>沒有 FEC 的最大資料流頻寬</th>
<th>具有 FEC 的最大資料流頻寬</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音訊</p></td>
<td><p>G.722</p></td>
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
<td><p>主要視訊接收</p></td>
<td><p>H.264 及/或 RTVideo</p></td>
<td><p>260</p></td>
<td><p>8015</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="even">
<td><p>主要視訊傳送</p></td>
<td><p>H.264 及/或 RTVideo</p></td>
<td><p>270</p></td>
<td><p>8015</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="odd">
<td><p>全景視訊接收</p></td>
<td><p>H.264 及/或 RTVideo</p></td>
<td><p>190</p></td>
<td><p>2010 (對於 1920x288 的最大解析度)</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="even">
<td><p>全景視訊傳送</p></td>
<td><p>H.264 及/或 RTVideo</p></td>
<td><p>190</p></td>
<td><p>2515 (對於使用多個解析度/轉碼器傳送位元資料流)</p></td>
<td><p>無</p></td>
</tr>
</tbody>
</table>


對於主要視訊，一般和最大資料流頻寬分別是所有接收視訊資料流的彙總頻寬和所有傳送視訊資料流的彙總頻寬。即使對於多個視訊資料流，一般視訊頻寬也小於對等工作階段的頻寬，因為許多視訊會議使用內容共用，使得視訊頻寬縮小，而導致視訊解析度降低。對於這兩個傳送和接收資料流，例如兩個連入 1920x1080p 視訊資料流，支援的最大彙總視訊承載頻寬為 8000 Kbps。

全景視訊的一般資料流頻寬是以僅傳輸 960x144 全景視訊的目前可用裝置為依據。一旦 1920x288 全景視訊的裝置可供使用，一般資料流頻寬便可望增加。

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
<th>媒體業</th>
<th>一般轉碼器</th>
<th>一般資料流頻寬 (Kbps)</th>
<th>沒有 FEC 的最大資料流頻寬</th>
<th>具有 FEC 的最大資料流頻寬</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音訊</p></td>
<td><p>G.711 （這包括 PSTN 參與者在會議中）</p></td>
<td><p>64.8</p></td>
<td><p>97</p></td>
<td><p>161</p></td>
</tr>
<tr class="even">
<td><p>音訊</p></td>
<td><p>RTAudio 窄頻</p></td>
<td><p>30.9</p></td>
<td><p>44.8</p></td>
<td><p>56.6</p></td>
</tr>
</tbody>
</table>


這些表中的網路頻寬數字僅表示單向流量，包括每個資料流的 5 Kbps RTCP 流量負荷。對於視訊，最大視訊位元速率用於運算最大資料流。

</div>

</div>

<span> </span>

</div>

</div>

</div>

