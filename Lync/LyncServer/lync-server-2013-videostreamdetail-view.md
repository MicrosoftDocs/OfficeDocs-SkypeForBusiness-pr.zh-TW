---
title: Lync Server 2013： VideoStreamDetail view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStreamDetail view
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49733863
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfa754fbcc24377b07bab3b13473adb1c5e953ea
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a>Lync Server 2013 中的 [VideoStreamDetail] 視圖

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

[VideoStreamDetail] 視圖會儲存資料庫中每個影片資料流程的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。


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
<th>說明</th>
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
<td><p>MediaLineLabel</p></td>
<td><p>Tinyint</p></td>
<td><p>從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</p></td>
</tr>
<tr class="even">
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>媒體線中的唯一識別碼。</p></td>
</tr>
<tr class="odd">
<td><p>開始</p></td>
<td><p>datetime</p></td>
<td><p>會話的開始時間。</p></td>
</tr>
<tr class="even">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>會話的結束時間。</p></td>
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
<td><p>呼叫者的使用者代理程式類型。 如需詳細資訊，請參閱<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中</a>的 [UserAgent] 資料表。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>Nvarchar （64）</p></td>
<td><p>呼叫者的使用者代理類別。 如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 資料表（QoE）</a> 。</p></td>
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
<td><p>呼叫者終點的 CPU 核心數。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>Smallint</p></td>
<td><p>被呼叫者的端點的 CPU 核心數。</p></td>
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
<td><p>ConnectivityIce</p></td>
<td><p>Tinyint</p></td>
<td><p>媒體路徑（例如直接或中繼）的相關資訊。 如需詳細資訊，請參閱<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中</a>的 [MediaLine] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>針對呼叫者位數標誌中描述的互動式連線建立（ICE）程式的相關資訊。 如需詳細資訊，請參閱體驗品質監視伺服器通訊協定的規格。</p></td>
</tr>
<tr class="even">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>針對被呼叫者的 bits 標誌中所述的互動式連線建立（ICE）程式的相關資訊。 如需詳細資訊，請參閱體驗品質監視伺服器通訊協定的規格。</p></td>
</tr>
<tr class="odd">
<td><p>傳輸</p></td>
<td><p>int</p></td>
<td><p>傳輸類型：0是 UDP，1是 TCP。</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>來電者的 IP 位址。 這可能是 IPv4 或 IPv6 位址。</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>呼叫者使用的埠。</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>稍微</p></td>
<td><p>指出來電者是否在組織網路內。 1表示呼叫者是在商業網路內，0代表呼叫者在網路以外。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>被呼叫者的 IP 位址。 這可能是 IPv4 或 IPv6 位址。</p></td>
</tr>
<tr class="even">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>被呼叫者使用的埠。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeInside</p></td>
<td><p>稍微</p></td>
<td><p>指出來電者是否在組織網路內。1代表被叫方是在商業網路內，0代表被叫方在網路以外。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserSite</p></td>
<td><p>Nvarchar</p></td>
<td><p>來電者的網站名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRegion</p></td>
<td><p>Nvarchar</p></td>
<td><p>來電者網站之國家/地區的名稱。</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserSite</p></td>
<td><p>Nvarchar</p></td>
<td><p>被呼叫者的網站名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRegion</p></td>
<td><p>Nvarchar</p></td>
<td><p>被呼叫者網站之國家/地區的名稱。</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>呼叫者所使用之 A/V 邊緣服務的 IP 位址。 如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>呼叫者使用的 A/V 邊緣服務上的埠。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>被呼叫者所使用之 A/V 邊緣服務的 IP 位址金鑰。 如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>被呼叫者使用的 A/V 邊緣服務上的埠。</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDev</p></td>
<td><p>Varchar （256）</p></td>
<td><p>來電者的擷取裝置名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDev</p></td>
<td><p>Varchar （256）</p></td>
<td><p>來電者的轉譯裝置名稱。</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>Varchar （256）</p></td>
<td><p>來電者的捕獲裝置驅動程式名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDevDriver</p></td>
<td><p>Varchar （256）</p></td>
<td><p>來電者的轉譯裝置驅動程式名稱。</p></td>
</tr>
<tr class="even">
<td><p>CalleeCaptureDev</p></td>
<td><p>Varchar （256）</p></td>
<td><p>被呼叫者的擷取裝置名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDev</p></td>
<td><p>Varchar （256）</p></td>
<td><p>被呼叫者的轉譯裝置名稱。</p></td>
</tr>
<tr class="even">
<td><p>CalleCaptureDevDriver</p></td>
<td><p>Varchar （256）</p></td>
<td><p>被呼叫者的捕獲裝置驅動程式名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>Varchar （256）</p></td>
<td><p>被呼叫者的轉譯裝置驅動程式名稱。</p></td>
</tr>
<tr class="even">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>Tinyint</p></td>
<td><p>來電者的網路連線類型：0是 [有線]，1是 [無線]。</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>稍微</p></td>
<td><p>指出呼叫者是否已經由虛擬專用網路連接。 1是虛擬私人網路（VPN），0是非 VPN。</p></td>
</tr>
<tr class="even">
<td><p>CallerLinkSpeed</p></td>
<td><p>小數（18，）</p></td>
<td><p>呼叫者端點的網路連結速度，以 bps 表示。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>Tinyint</p></td>
<td><p>被呼叫者的網路連線類型：0是 [有線]，1是 [無線]。</p></td>
</tr>
<tr class="even">
<td><p>CalleeVPN</p></td>
<td><p>稍微</p></td>
<td><p>指出被呼叫者是否已經由虛擬私人網路絡進行連線。 1是虛擬私人網路（VPN），0是非 VPN。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeLinkSpeed</p></td>
<td><p>小數（18，0）</p></td>
<td><p>被呼叫者的端點的網路連結速度（bps）。</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>decimal （3，2）</p></td>
<td><p>Narrowband 音訊會話的會話 MOS （根據兩個音訊資料流程）。</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>在給定各種原則設定（TURN、API、SDP、原則伺服器等）的情況下，套用到指定傳送端資料流程的實際頻寬。 這不會與有效的頻寬混淆，因為頻寬估計可能會有較低的效率。 這實際上是最大頻寬：傳送資料流程可能會受到頻寬估計所施加的限制。</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>從即時控制通訊協定（RTCP）統計資料的平均網路抖動。</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>通話期間網路抖動的最大值。</p></td>
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
<td><p>PacketLossRate</p></td>
<td><p>十進位（5，4）</p></td>
<td><p>通話期間的平均資料包遺失率。</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRateMax</p></td>
<td><p>十進位（5，4）</p></td>
<td><p>通話期間觀察到的最大資料包遺失。</p></td>
</tr>
<tr class="even">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>影片串流的資料包計數（即時傳輸通訊協定、RTP）。</p></td>
</tr>
<tr class="odd">
<td><p>BandwidthEst</p></td>
<td><p>int</p></td>
<td><p>音訊資料流程的頻寬估計值。</p></td>
</tr>
<tr class="even">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>用於通話的音訊編解碼器，<a href="lync-server-2013-payloaddescription-table.md">在 Lync Server 2013 的 PayloadDescription 資料表中</a>參考。</p></td>
</tr>
<tr class="odd">
<td><p>VideoResolution</p></td>
<td><p>char （9）</p></td>
<td><p>以圖元為單位的影片解析度，以圖元為單位的寬度乘以圖元高度。 報告為字串。</p></td>
</tr>
<tr class="even">
<td><p>VideoBitRateAvg</p></td>
<td><p>int</p></td>
<td><p>影片串流的平均位元速率。</p></td>
</tr>
<tr class="odd">
<td><p>InboundVideoFrameRateAvg</p></td>
<td><p>十進位（9，4）</p></td>
<td><p>收到的視頻畫面播放速率。</p></td>
</tr>
<tr class="even">
<td><p>OutboundVideoFrameRateAvg</p></td>
<td><p>十進位（9，4）</p></td>
<td><p>已傳送的視頻畫面播放速率。</p></td>
</tr>
<tr class="odd">
<td><p>ViideoBitRateMax</p></td>
<td><p>int</p></td>
<td><p>影片會話期間的最大視頻位元速率。</p></td>
</tr>
<tr class="even">
<td><p>VideoPacketLossRate</p></td>
<td><p>十進位（9，4）</p></td>
<td><p>視頻資料包遺失的頻率。</p></td>
</tr>
<tr class="odd">
<td><p>VideoFrameLossRate</p></td>
<td><p>decimal （9.4）</p></td>
<td><p>遺失的視頻畫面總百分比。</p></td>
</tr>
<tr class="even">
<td><p>VideoFEC</p></td>
<td><p>稍微</p></td>
<td><p>不使用。</p></td>
</tr>
<tr class="odd">
<td><p>VideoAllocateBWAvg</p></td>
<td><p>int</p></td>
<td><p>為影片所分配的平均頻寬量。</p></td>
</tr>
<tr class="even">
<td><p>VideoLocalFrameLossPercentageAvg</p></td>
<td><p>decimal （9.4）</p></td>
<td><p>遺失的視頻畫面總百分比。</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>稍微</p></td>
<td><p>P 斷言身分識別資訊的資料流程方向。 1表示資料流程方向從來電者到被叫方;0表示資料流程方向是從被叫方到來電者。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

