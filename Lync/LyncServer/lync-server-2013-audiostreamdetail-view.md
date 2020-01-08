---
title: Lync Server 2013： AudioStreamDetail view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioStreamDetail view
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49733792
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10992007c76321f8ed3b436b9786cbef840173ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a>Lync Server 2013 中的 [AudioStreamDetail] 視圖

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

[AudioStreamDetail] 視圖會儲存資料庫中每個音訊資料流程的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>左欄</th>
<th>資料類型</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SessionTime</p></td>
<td><p>datetime</p></td>
<td><p>從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</p></td>
</tr>
<tr class="odd">
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>媒體線中的唯一識別碼。</p></td>
</tr>
<tr class="even">
<td><p>開始</p></td>
<td><p>datetime</p></td>
<td><p>會話的開始時間。</p></td>
</tr>
<tr class="odd">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>會話的結束時間。</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>稍微</p></td>
<td><p>對話方塊類別：0是 Lync 伺服器以進行轉送伺服器腿;1是通向 PSTN 閘道腿的中繼伺服器。</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>稍微</p></td>
<td><p>該旗標指出通話是否被略過。</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>如果有的話，則指示即使繞過旁路 Id，也不會避開通話。 只定義一個值：</p>
<p>0x0001 –預設網路介面卡的旁路旁路 ID。</p></td>
</tr>
<tr class="odd">
<td><p>CallPriority</p></td>
<td><p>int</p></td>
<td><p>通話的優先順序。</p></td>
</tr>
<tr class="even">
<td><p>CallerPool</p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>呼叫者池 FQDN。</p></td>
</tr>
<tr class="odd">
<td><p>CalleePool</p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>被呼叫方池 FQDN。</p></td>
</tr>
<tr class="even">
<td><p>呼叫</p></td>
<td><p>Nvarchar （450）</p></td>
<td><p>來電者的 URI。</p></td>
</tr>
<tr class="odd">
<td><p>方</p></td>
<td><p>Nvarchar （450）</p></td>
<td><p>被呼叫者的 URI。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgent</p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>來電者的使用者代理程式字串。</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentType</p></td>
<td><p>Smallint</p></td>
<td><p>來電者的使用者代理程式類型。 如需詳細資訊，請參閱<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中</a>的 [UserAgent] 資料表。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>Nvarchar （64）</p></td>
<td><p>呼叫者使用者代理程式的類別。 如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 資料表（QoE）</a> 。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgent</p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>被呼叫者的使用者代理程式字串。</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentType</p></td>
<td><p>Smallint</p></td>
<td><p>被呼叫者的使用者代理程式類型。 如需詳細資訊，請參閱<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中</a>的 [UserAgent] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>Nvarchar （64）</p></td>
<td><p>被呼叫者的使用者代理程式類別。 如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 資料表（QoE）</a> 。</p></td>
</tr>
<tr class="even">
<td><p>CallerEndpoint</p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>來電者的端點名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEndpoint</p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>被呼叫者的端點名稱。</p></td>
</tr>
<tr class="even">
<td><p>CallerOS</p></td>
<td><p>Nvarchar</p></td>
<td><p>呼叫者終點的作業系統（OS）。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeOS</p></td>
<td><p>Nvarchar</p></td>
<td><p>被呼叫者的端點的作業系統（OS）。</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUName</p></td>
<td><p>Nvarchar</p></td>
<td><p>呼叫者終點的 CPU 名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUName</p></td>
<td><p>Nvarchar</p></td>
<td><p>被呼叫者的端點的 CPU 名稱。</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUNumberOfCores</p></td>
<td><p>Smallint</p></td>
<td><p>呼叫者終點中的 CPU 核心數。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>Smallint</p></td>
<td><p>被呼叫者的端點中的 CPU 核心數。</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>呼叫者終點的 CPU 處理器速度。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>被呼叫者的端點的 CPU 處理器速度。</p></td>
</tr>
<tr class="even">
<td><p>CallerVirtualizationFlag</p></td>
<td><p>Tinyint</p></td>
<td><p>指出呼叫者的系統在虛擬化環境中是否正在執行。 如需詳細資訊，請參閱<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的端點資料表</a>。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVirtualizationFlag</p></td>
<td><p>Tinyint</p></td>
<td><p>指出被呼叫者的系統是否正在虛擬化環境中執行。 如需詳細資訊，請參閱<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的端點資料表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CorrelationKey</p></td>
<td></td>
<td><p>[關聯金鑰]。 從<a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 的 SessionCorrelation 資料表中</a>參考。</p></td>
</tr>
<tr class="odd">
<td><p>ConnectivityIce</p></td>
<td><p>Tinyint</p></td>
<td><p>媒體路徑（例如直接或中繼）的相關資訊。 如需詳細資訊，請參閱<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中</a>的 [MediaLine] 資料表。</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>針對呼叫者位數標誌中描述的互動式連線建立（ICE）程式的相關資訊。 如需詳細資訊，請參閱體驗品質監視伺服器通訊協定的規格。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>針對被呼叫者的 bits 標誌中所述的互動式連線建立（ICE）程式的相關資訊。 如需詳細資訊，請參閱體驗品質監視伺服器通訊協定的規格。</p></td>
</tr>
<tr class="even">
<td><p>傳輸</p></td>
<td><p>Tinyint</p></td>
<td><p>傳輸類型：0是 UDP，1是 TCP。</p></td>
</tr>
<tr class="odd">
<td><p>CallerIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>來電者的 IP 位址。 這可能是 IPv4 或 IPv6 位址。</p></td>
</tr>
<tr class="even">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>呼叫者使用的埠。</p></td>
</tr>
<tr class="odd">
<td><p>CallerInside</p></td>
<td><p>稍微</p></td>
<td><p>指出來電者是否在間隔網路內：1表示呼叫者是在商業網路內，0代表來電者在網路以外。</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>被呼叫者的 IP 位址。 這可能是 IPv4 或 IPv6 位址。</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>被呼叫者使用的埠。</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>稍微</p></td>
<td><p>指出被呼叫者是否在間隔網路內：1代表被呼叫者是在商業網路內，0代表被呼叫者在網路以外。</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserSite</p></td>
<td><p>Nvarchar</p></td>
<td><p>來電者的網站名稱。</p></td>
</tr>
<tr class="even">
<td><p>CallerRegion</p></td>
<td><p>Nvarchar</p></td>
<td><p>來電者網站之國家/地區的名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserSite</p></td>
<td><p>Nvarchar</p></td>
<td><p>被呼叫者的網站名稱。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRegion</p></td>
<td><p>Nvarchar</p></td>
<td><p>被呼叫者網站之國家/地區的名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>呼叫者所使用之 A/V 邊緣服務的 IP 位址。 如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>呼叫者使用的 A/V 邊緣服務上使用的埠。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>被呼叫者所使用之 A/V 邊緣服務的 IP 位址金鑰。 如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>在被呼叫者所使用的 A/V 邊緣服務上使用的埠。</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDev</p></td>
<td><p>Varchar （256）</p></td>
<td><p>來電者的擷取裝置名稱。</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDev</p></td>
<td><p>Varchar （256）</p></td>
<td><p>來電者的轉譯裝置名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>Varchar （256）</p></td>
<td><p>來電者的捕獲裝置驅動程式名稱。</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDriver</p></td>
<td><p>Varchar （256）</p></td>
<td><p>來電者的轉譯裝置驅動程式名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>Varchar （256）</p></td>
<td><p>被呼叫者的擷取裝置名稱。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>Varchar （256）</p></td>
<td><p>被呼叫者的轉譯裝置名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDevDriver</p></td>
<td><p>Varchar （256）</p></td>
<td><p>被呼叫者的捕獲裝置驅動程式名稱。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>Varchar （256）</p></td>
<td><p>被呼叫者的轉譯裝置驅動程式名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>Tinyint</p></td>
<td><p>來電者的網路連線類型：0是 [有線]，1是 [無線]。</p></td>
</tr>
<tr class="even">
<td><p>CallerVPN</p></td>
<td><p>稍微</p></td>
<td><p>指出呼叫者是否已經由虛擬專用網路連接：1是虛擬私人網路（VPN），0是非 VPN。</p></td>
</tr>
<tr class="odd">
<td><p>CallerLinkSpeed</p></td>
<td><p>小數（18，0）</p></td>
<td><p>呼叫者端點的網路連結速度，以 bps 表示。</p></td>
</tr>
<tr class="even">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>Tinyint</p></td>
<td><p>被呼叫者的網路連線類型：0是 [有線]，1是 [無線]。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>稍微</p></td>
<td><p>指出呼叫者是否已經由虛擬專用網路連接：1是虛擬私人網路（VPN），0是非 VPN。</p></td>
</tr>
<tr class="even">
<td><p>CalleeLinkSpeed</p></td>
<td><p>小數（18，0）</p></td>
<td><p>被呼叫者的端點的網路連結速度，以 bps 表示。</p></td>
</tr>
<tr class="odd">
<td><p>ConversationalMOS</p></td>
<td><p>decimal （3，2）</p></td>
<td><p>Narrowband 音訊會話的會話 MOS （根據兩個音訊資料流程）。</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>在給定各種原則設定（TURN、API、SDP、原則伺服器等）的情況下，套用到指定傳送端資料流程的實際頻寬。 這不會與有效的頻寬混淆，因為頻寬估計可能會有較低的效率。 這實際上是最大頻寬：傳送資料流程可能會受到頻寬估計所強加的限制</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>從即時控制通訊協定（RTCP）統計資料的平均網路抖動。</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>通話期間網路抖動的最大值。</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRate</p></td>
<td><p>十進位（5，4）</p></td>
<td><p>通話期間的平均資料包遺失率。</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRateMax</p></td>
<td><p>十進位（5，4）</p></td>
<td><p>通話期間觀察到的最大資料包遺失。</p></td>
</tr>
<tr class="odd">
<td><p>BurstDensity</p></td>
<td><p>十進位（9，4）</p></td>
<td><p>通話期間猝發損失期間的平均資料包遺失密度。</p></td>
</tr>
<tr class="even">
<td><p>BurstDuration</p></td>
<td><p>int</p></td>
<td><p>通話期間猝發損失期間的平均資料包遺失時間。</p></td>
</tr>
<tr class="odd">
<td><p>BurstGapDensity</p></td>
<td><p>十進位（9，4）</p></td>
<td><p>在突發資料包遺失之間的間隔期間的平均資料包遺失密度。</p></td>
</tr>
<tr class="even">
<td><p>BurstGapDuration</p></td>
<td><p>int</p></td>
<td><p>猝發資料包遺失之間的平均持續時間。</p></td>
</tr>
<tr class="odd">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>音訊資料流程的 [資料包計數]。</p></td>
</tr>
<tr class="even">
<td><p>BandwidthEst</p></td>
<td><p>int</p></td>
<td><p>音訊資料流程的頻寬估計值。</p></td>
</tr>
<tr class="odd">
<td><p>DegradationAvg</p></td>
<td><p>decimal （3，2）</p></td>
<td><p>整個通話的網路 MOS 下降。 範圍是0.0 到5.0。 這個指標顯示由於抖動和資料包遺失而減少網路 MOS 的數量。 針對可接受的品質，它應該小於0.5。</p></td>
</tr>
<tr class="even">
<td><p>DegradationMax</p></td>
<td><p>decimal （3，2）</p></td>
<td><p>通話期間網路 MOS 的最大下降。</p></td>
</tr>
<tr class="odd">
<td><p>DegradationJitterAvg</p></td>
<td><p>decimal （3，2）</p></td>
<td><p>抖動造成的網路 MOS 下降。</p></td>
</tr>
<tr class="even">
<td><p>DegradationPacketLossAvg</p></td>
<td><p>decimal （3，2）</p></td>
<td><p>因數據包遺失而造成的網路 MOS 下降。</p></td>
</tr>
<tr class="odd">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>在<a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 的 PayloadDescription 資料表中</a>參考的音訊編解碼器。</p></td>
</tr>
<tr class="even">
<td><p>AudioSampleRate</p></td>
<td><p>int</p></td>
<td><p>音訊資料流程的採樣速率。</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>撥號後的類比增益控制呼叫者傳送之音訊的音訊信號等級。 這個指標的單位是 dBmo。 若要取得可接受的品質，至少要有 30 dBmo。 A/V 會議伺服器或 IP 電話不會報告此統計值。</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>來電者收到之音訊的音訊信號等級。 這個指標的單位是 dBmo。 若要取得可接受的品質，至少要有 30 dBmo。 A/V 會議伺服器或 IP 電話不會報告此統計值。</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>撥號後的類比增益控制來電者傳送之音訊的音訊雜訊層級。 這個指標的單位是 dBmo。 針對可接受的品質，它應該小於 35 dBmo。 A/V 會議伺服器或 IP 電話不會報告此統計值。</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>撥號後的類比增益控制來電者收到之音訊的音訊雜訊層級。 這個指標的單位是 dBmo。 針對可接受的品質，它應該小於 35 dBmo。 A/V 會議伺服器或 IP 電話不會報告此統計值。</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoReturn</p></td>
<td><p>int</p></td>
<td><p>來電者的迴響回報損失增強功能。 這個指標的單位是 dB。 較低的值代表較少的回音。 A/V 會議伺服器或 IP 電話不會報告此統計值。</p></td>
</tr>
<tr class="even">
<td><p>CallerSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>呼叫者的喇叭前轉譯每五分鐘的平均問題。 若要獲得較高的品質，此頻率應該小於每五分鐘。 無法由 A/V 會議伺服器、中繼伺服器或 IP 電話來報告。</p></td>
</tr>
<tr class="odd">
<td><p>CallerMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>呼叫者麥克風捕獲每五分鐘的平均問題。 若要獲得良好的品質，這應該少於每五分鐘一次。 無法由 A/V 會議伺服器、中繼伺服器或 IP 電話來報告。</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampDriftRateMic</p></td>
<td><p>decimal （9，2）</p></td>
<td><p>本機號碼相對於 CPU 時鐘的麥克風裝置時鐘偏移速度。</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampDriftRateSpk</p></td>
<td><p>decimal （9，2）</p></td>
<td><p>來電者與 CPU 時鐘相關的喇叭裝置時鐘偏移率。</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampErrorMicMs</p></td>
<td><p>decimal （9，2）</p></td>
<td><p>在呼叫的最後20秒內，麥克風捕獲串流的時間戳記錯誤（以毫秒為單位）。</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampErrorSpkMs</p></td>
<td><p>decimal （9，2）</p></td>
<td><p>呼叫者最近20秒內，來電者的喇叭轉譯資料流程時間戳記錯誤的平均值。</p></td>
</tr>
<tr class="even">
<td><p>CallerVsEntryCauses</p></td>
<td><p>Smallint</p></td>
<td><p>Voice 開關是一種半雙工模式，可減少中斷能力。 如需詳細資訊，請參閱<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中</a>的 [MediaLine] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoEventCauses</p></td>
<td><p>Tinyint</p></td>
<td><p>呼叫者回顯事件的原因。 如需詳細資訊，請參閱<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中</a>的 [MediaLine] 資料表。</p></td>
</tr>
<tr class="even">
<td><p>CallerEchoPercentMicIn</p></td>
<td><p>decimal （5，2）</p></td>
<td><p>在呼叫者麥克風捕獲串流中檢測到迴響的時間百分比。 如果使用耳機，該值應該較低。</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoPercentSend</p></td>
<td><p>decimal （5，2）</p></td>
<td><p>在來電者的傳送資料流程中檢測到迴響的時間百分比。 傳送資料流程中的高迴響百分比表示回應洩漏。</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>從呼叫者音訊的閘道在中繼伺服器上接收到的信號等級;這只適用于中繼伺服器。 這個度量單位是 dBoV。 若要獲得良好的品質，可接受的範圍應該是-30 到-18 的 dBoV。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>從呼叫者音訊的閘道在中繼伺服器上接收到的信號等級。 這只適用于中繼伺服器。 這個度量單位是 dBoV。 若要獲得良好的品質，可接受的範圍應該小於-50 dBoV。</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>將中繼伺服器端的自動增益控制（AGC）套用至呼叫者的音訊。</p></td>
</tr>
<tr class="odd">
<td><p>CallerInitialSignalLevelRMS</p></td>
<td><p>浮</p></td>
<td><p>呼叫的撥入信號的根平均數（RMS），最多為來電者的前30秒。</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>代表被呼叫者傳送之音訊的類比後增益控制音訊信號等級。 這個指標的單位是 dBmo。 若要取得可接受的品質，至少要有 30 dBmo。 A/V 會議伺服器或 IP 電話不會報告此統計值。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>被呼叫者接收之音訊的音訊信號等級。 這個指標的單位是 dBmo。 若要取得可接受的品質，至少要有 30 dBmo。 A/V 會議伺服器或 IP 電話不會報告此統計值。</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>防類比增益控制被呼叫者傳送之音訊的音訊雜訊層級。 這個指標的單位是 dBmo。 針對可接受的品質，它應該小於 35 dBmo。 A/V 會議伺服器或 IP 電話不會報告此統計值。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>已被呼叫者接收之音訊的反類比增益控制音訊雜訊層級。 這個指標的單位是 dBmo。 針對可接受的品質，它應該小於 35 dBmo。 A/V 會議伺服器或 IP 電話不會報告此統計值。</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoReturn</p></td>
<td><p>int</p></td>
<td><p>被呼叫者的迴響傳回損失增強功能。 這個指標的單位是 dB。 較低的值代表較少的回音。 A/V 會議伺服器或 IP 電話不會報告此統計值。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>被呼叫者的喇叭前轉譯每五分鐘的平均故障。 若要獲得較高的品質，此頻率應該小於每五分鐘。 無法由 A/V 會議伺服器、中繼伺服器或 IP 電話來報告。</p></td>
</tr>
<tr class="even">
<td><p>CalleeMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>被呼叫者麥克風捕獲每五分鐘的平均問題。 若要獲得良好的品質，這應該少於每五分鐘一次。 無法由 A/V 會議伺服器、中繼伺服器或 IP 電話來報告。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampDriftRateMic</p></td>
<td><p>decimal （9，2）</p></td>
<td><p>被呼叫者的麥克風裝置時鐘偏移率，相對於 CPU 時鐘。</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampDriftRateSpk</p></td>
<td><p>decimal （9，2）</p></td>
<td><p>被呼叫者的喇叭裝置時鐘偏移率，相對於 CPU 時鐘。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampErrorMicMs</p></td>
<td><p>decimal （9，2）</p></td>
<td><p>在呼叫的最後20秒內，麥克風捕獲串流的時間戳記錯誤（以毫秒為單位）。</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampErrorSpkMs</p></td>
<td><p>decimal （9，2）</p></td>
<td><p>呼叫者最近20秒內，被呼叫者的喇叭轉譯資料流程時間戳記錯誤的平均值。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVsEntryCauses</p></td>
<td><p>Smallint</p></td>
<td><p>Voice 開關是一種半雙工模式，可減少中斷能力。 如需詳細資訊，請參閱<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中</a>的 [MediaLine] 資料表。</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoEventCauses</p></td>
<td><p>Tinyint</p></td>
<td><p>被呼叫者的 echo 事件原因。 如需詳細資訊，請參閱<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中</a>的 [MediaLine] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEchoPercentMicIn</p></td>
<td><p>decimal （5，2）</p></td>
<td><p>在被呼叫者的麥克風捕獲資料流程中檢測到迴響的時間百分比。 如果使用耳機，該值應該較低。</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoPercentSend</p></td>
<td><p>decimal （5，2）</p></td>
<td><p>在被呼叫者的傳送資料流程中檢測到迴響的時間百分比。 傳送資料流程中的高迴響百分比表示回應洩漏。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>從被呼叫者音訊的閘道在中繼伺服器上接收到的信號等級;這只適用于中繼伺服器。 這個度量單位是 dBoV。 若要獲得良好的品質，可接受的範圍應該是 [-30 至-18] dBoV。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>從被呼叫者音訊的閘道，在中繼伺服器上接收到的信號等級。 這只適用于中繼伺服器。 這個度量單位是 dBoV。 若要獲得良好的品質，可接受的範圍應該小於-50 dBoV。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>將中繼伺服器端的自動增益控制（AGC）套用到被呼叫者的音訊。</p></td>
</tr>
<tr class="even">
<td><p>CalleeInitialSignalLevelRMS</p></td>
<td><p>浮</p></td>
<td><p>呼叫的撥入信號的根平均數（RMS），最多為撥打電話的前30秒。</p></td>
</tr>
<tr class="odd">
<td><p>RatioConcealedSamplesAvg</p></td>
<td><p>decimal （5，2）</p></td>
<td><p>從音訊康復產生的隱藏樣本到典型範例的平均比率。</p></td>
</tr>
<tr class="even">
<td><p>RatioStretchedSamplesAvg</p></td>
<td><p>decimal （5，2）</p></td>
<td><p>從音訊康復產生的延伸樣本數與典型範例的平均比率。</p></td>
</tr>
<tr class="odd">
<td><p>RatioCompressedSamplesAvg</p></td>
<td><p>decimal （5，2）</p></td>
<td><p>從音訊修復到典型範例所產生之壓縮樣本的平均比率。</p></td>
</tr>
<tr class="even">
<td><p>環路</p></td>
<td><p>int</p></td>
<td><p>從 RTCP 統計資料中往返的時間。</p></td>
</tr>
<tr class="odd">
<td><p>RoundTripMax</p></td>
<td><p>int</p></td>
<td><p>音訊資料流程的最大往返行程時間。</p></td>
</tr>
<tr class="even">
<td><p>OverallAvgNetworkMOS</p></td>
<td><p>decimal （3，2）</p></td>
<td><p>通話的平均 wideband 網路 MOS。 這個指標取決於所使用的資料包遺失、抖動和編解碼器。 範圍是1.0 到5.0。</p></td>
</tr>
<tr class="odd">
<td><p>OverallMinNetworkMOS</p></td>
<td><p>decimal （3，2）</p></td>
<td><p>通話的最小 wideband 網路 MOS。</p></td>
</tr>
<tr class="even">
<td><p>SendListenMOS</p></td>
<td><p>decimal （3，2）</p></td>
<td><p>已傳送音訊的平均預計 wideband，包括語音等級、雜訊等級及捕捉裝置特徵。</p></td>
</tr>
<tr class="odd">
<td><p>SendListenMOSMin</p></td>
<td><p>decimal （3，2）</p></td>
<td><p>通話的最小 SendListenMOS。</p></td>
</tr>
<tr class="even">
<td><p>RecvListenMOS</p></td>
<td><p>decimal （3，2）</p></td>
<td><p>平均預計 wideband 從網路接收之音訊的 MOS 分數，包括語音電平、雜訊層級、編解碼器、網路條件及捕獲裝置特徵。</p></td>
</tr>
<tr class="odd">
<td><p>RecvListenMOSMin</p></td>
<td><p>decimal （3，2）</p></td>
<td><p>通話的最小 RecvListenMOS。</p></td>
</tr>
<tr class="even">
<td><p>AudioFECUsed</p></td>
<td><p>稍微</p></td>
<td><p>指出是否已使用音訊 FEC 進行通話。</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>稍微</p></td>
<td><p>表示 p 斷言識別資訊的方向。1表示資料流程方向從來電者到被叫方;0表示資料流程方向是從被叫方到來電者。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

