---
title: Lync Server 2013： VideoStreamDetail view
description: Lync Server 2013： VideoStreamDetail view。
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
ms.openlocfilehash: a3f420c292627d15fd0d54f2eba01c565a49a72d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567969"
---
# <a name="videostreamdetail-view-in-lync-server-2013"></a>Lync Server 2013 中的 VideoStreamDetail 視圖

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

VideoStreamDetail View 儲存資料庫中每個影片資料流程的資訊。 此視圖已引進于 Microsoft Lync Server 2013。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>欄</th>
<th>資料類型</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SessionTime</p></td>
<td><p>datetime</p></td>
<td><p>從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</p></td>
</tr>
<tr class="odd">
<td><p>MediaLineLabel</p></td>
<td><p>Tinyint</p></td>
<td><p>從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</p></td>
</tr>
<tr class="even">
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>媒體行中的唯一識別碼。</p></td>
</tr>
<tr class="odd">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>會話的開始時間。</p></td>
</tr>
<tr class="even">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>工作階段結束時間。</p></td>
</tr>
<tr class="odd">
<td><p>CallPriority</p></td>
<td><p>int</p></td>
<td><p>通話的優先順序。</p></td>
</tr>
<tr class="even">
<td><p>CallerPool</p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>發話者集區 FQDN。</p></td>
</tr>
<tr class="odd">
<td><p>CalleePool</p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>受話者集區 FQDN。</p></td>
</tr>
<tr class="even">
<td><p>Caller</p></td>
<td><p>Nvarchar (450) </p></td>
<td><p>來電者的 URI。</p></td>
</tr>
<tr class="odd">
<td><p>方</p></td>
<td><p>Nvarchar (450) </p></td>
<td><p>被呼叫者的 URI。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgent</p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>發話者的使用者代理程式字串。</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentType</p></td>
<td><p>Smallint</p></td>
<td><p>發話者的使用者代理程式類型。 如需詳細資訊，請參閱 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>Nvarchar (64) </p></td>
<td><p>發話者的使用者代理程式類別。 如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef 表格 (Lync Server 2013 中的 QoE) </a> 。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgent</p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>受話者的使用者代理程式字串。</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentType</p></td>
<td><p>Smallint</p></td>
<td><p>被呼叫者之使用者代理程式的類型。 如需詳細資訊，請參閱 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>Nvarchar (64) </p></td>
<td><p>被呼叫者之使用者代理程式的類別。 如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) 中的 Lync Server 2013</a> 。</p></td>
</tr>
<tr class="even">
<td><p>CallerEndpoint</p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>發話者的端點名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEndpoint</p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>被呼叫者的端點名稱。</p></td>
</tr>
<tr class="even">
<td><p>CallerOS</p></td>
<td><p>Nvarchar (128) </p></td>
<td><p>呼叫者端點的作業系統 (OS) 。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeOS</p></td>
<td><p>Nvarchar (128) </p></td>
<td><p>受話者端點的作業系統 (OS) 。</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUName</p></td>
<td><p>Nvarchar (128) </p></td>
<td><p>來電者端點的 CPU 名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUName</p></td>
<td><p>Nvarchar (128) </p></td>
<td><p>受話者端點的 CPU 名稱。</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUNumberOfCores</p></td>
<td><p>Smallint</p></td>
<td><p>來電者端點的 CPU 核心數目。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>Smallint</p></td>
<td><p>受話者端點的 CPU 核心數目。</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>來電者端點的 CPU 處理器速度。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>受話者端點的 CPU 處理器速度。</p></td>
</tr>
<tr class="even">
<td><p>CallerVirtualizationFlag</p></td>
<td><p>Tinyint</p></td>
<td><p>會指出來電者的系統是否在虛擬化環境中執行。 如需詳細資訊，請參閱 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的端點表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVirtualizationFlag</p></td>
<td><p>Tinyint</p></td>
<td><p>會指出受話者的系統是否正在虛擬環境中執行。 如需詳細資訊，請參閱 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的端點表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p>ConnectivityIce</p></td>
<td><p>Tinyint</p></td>
<td><p>媒體路徑的相關資訊，例如 direct 或中繼。 如需詳細資訊，請參閱 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>發話者位元旗標中描述之互動式連線建立 (ICE) 程序的相關資訊。如需詳細資訊，請參閱＜經驗品質監控伺服器通訊協定規格＞。</p></td>
</tr>
<tr class="even">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>受話者位元旗標中描述之互動式連線建立 (ICE) 程序的相關資訊。如需詳細資訊，請參閱＜經驗品質監控伺服器通訊協定規格＞。</p></td>
</tr>
<tr class="odd">
<td><p>傳輸</p></td>
<td><p>int</p></td>
<td><p>傳輸類型：0是 UDP，1是 TCP。</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var (50) </p></td>
<td><p>來電者的 IP 位址。 這可以是 IPv4 或 IPv6 位址。</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>發話者使用的連接埠。</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>位</p></td>
<td><p>會指出來電者是否在組織網路內。 1表示來電者位於商業網路內，0表示來電者位於網路外。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50) </p></td>
<td><p>被呼叫者的 IP 位址。 這可以是 IPv4 或 IPv6 位址。</p></td>
</tr>
<tr class="even">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>受話者使用的連接埠。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeInside</p></td>
<td><p>位</p></td>
<td><p>會指出來電者是否在組織網路內。1表示受話者位於商業網路內，0表示受話者位於網路外。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserSite</p></td>
<td><p>Nvarchar (128) </p></td>
<td><p>來電者網站的名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRegion</p></td>
<td><p>Nvarchar (128) </p></td>
<td><p>來電者網站的國家/地區名稱。</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserSite</p></td>
<td><p>Nvarchar (128) </p></td>
<td><p>被呼叫者之網站的名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRegion</p></td>
<td><p>Nvarchar (128) </p></td>
<td><p>被呼叫者網站的國家/地區名稱。</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50) </p></td>
<td><p>發話者使用之 A/V Edge Service 的 IP 位址。 如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>呼叫者所使用 A/V Edge service 上的埠。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50) </p></td>
<td><p>被呼叫者所使用之 A/V Edge service 的 IP 位址金鑰。 如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>被呼叫者所使用 A/V Edge service 上的埠。</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDev</p></td>
<td><p>Varchar (256) </p></td>
<td><p>發話者的擷取裝置名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDev</p></td>
<td><p>Varchar (256) </p></td>
<td><p>發話者的轉換裝置名稱。</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>Varchar (256) </p></td>
<td><p>發話者的擷取裝置驅動程式名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDevDriver</p></td>
<td><p>Varchar (256) </p></td>
<td><p>發話者的轉換裝置驅動程式名稱。</p></td>
</tr>
<tr class="even">
<td><p>CalleeCaptureDev</p></td>
<td><p>Varchar (256) </p></td>
<td><p>受話者的擷取裝置名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDev</p></td>
<td><p>Varchar (256) </p></td>
<td><p>受話者的轉換裝置名稱。</p></td>
</tr>
<tr class="even">
<td><p>CalleCaptureDevDriver</p></td>
<td><p>Varchar (256) </p></td>
<td><p>受話者的擷取裝置驅動程式名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>Varchar (256) </p></td>
<td><p>受話者的轉換裝置驅動程式名稱。</p></td>
</tr>
<tr class="even">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>Tinyint</p></td>
<td><p>來電者的網路連線類型：0是有線的，1是無線。</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>位</p></td>
<td><p>會指出呼叫者是否透過虛擬專用網路連接。 1 是虛擬私人網路 (VPN)，0 是非 VPN。</p></td>
</tr>
<tr class="even">
<td><p>CallerLinkSpeed</p></td>
<td><p>十進位 (18，) </p></td>
<td><p>呼叫者端點的網路連結速度（bps）。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>Tinyint</p></td>
<td><p>被呼叫者的網路連線類型：0是有線的，1是無線。</p></td>
</tr>
<tr class="even">
<td><p>CalleeVPN</p></td>
<td><p>位</p></td>
<td><p>會指出是否已透過虛擬專用網路連接被呼叫者。 1 是虛擬私人網路 (VPN)，0 是非 VPN。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeLinkSpeed</p></td>
<td><p>十進位 (18，0) </p></td>
<td><p>受話者端點的網路連結速度 (以 bps) 為單位）。</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>十進位 (3，2) </p></td>
<td><p>音訊工作階段的窄頻交談方式 MOS (兩種音訊資料流皆為依據)。</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>針對指定之傳送端資料流程套用至指定之傳送端資料流程的實際頻寬，可 (轉換、API、SDP、原則伺服器等等) 。 這並不會混淆有效的頻寬，因為頻寬估算可能會有較低的有效頻寬。 基本上，除了頻寬預估值規定的限制以外，這是傳送端資料流所能取得的最大頻寬。</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>從即時控制通訊協定 (RTCP) 統計資料的平均網路抖動。</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>通話期間的最大網路抖動。</p></td>
</tr>
<tr class="even">
<td><p>往返</p></td>
<td><p>int</p></td>
<td><p>從 RTCP 統計資料來回的時間。</p></td>
</tr>
<tr class="odd">
<td><p>RoundTripMax</p></td>
<td><p>int</p></td>
<td><p>音訊資料流程的最大來回時間。</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRate</p></td>
<td><p>十進位 (5，4) </p></td>
<td><p>通話期間的平均封包遺失率。</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRateMax</p></td>
<td><p>十進位 (5，4) </p></td>
<td><p>通話期間觀察到的封包遺失上限。</p></td>
</tr>
<tr class="even">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>影片的封包計數 (即時傳輸通訊協定，RTP) 。</p></td>
</tr>
<tr class="odd">
<td><p>BandwidthEst</p></td>
<td><p>int</p></td>
<td><p>音訊資料流程的頻寬估計值。</p></td>
</tr>
<tr class="even">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>用於通話的音訊編解碼器，從 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 的 PayloadDescription 表格中</a>參照。</p></td>
</tr>
<tr class="odd">
<td><p>VideoResolution</p></td>
<td><p>char (9) </p></td>
<td><p>影片解析度（圖元寬度乘以圖元高度）。 報告為字串。</p></td>
</tr>
<tr class="even">
<td><p>VideoBitRateAvg</p></td>
<td><p>int</p></td>
<td><p>視頻資料流程的平均位元速率。</p></td>
</tr>
<tr class="odd">
<td><p>InboundVideoFrameRateAvg</p></td>
<td><p>十進位 (9，4) </p></td>
<td><p>收到的影片的畫面速率。</p></td>
</tr>
<tr class="even">
<td><p>OutboundVideoFrameRateAvg</p></td>
<td><p>十進位 (9，4) </p></td>
<td><p>傳送影片的畫面速率。</p></td>
</tr>
<tr class="odd">
<td><p>ViideoBitRateMax</p></td>
<td><p>int</p></td>
<td><p>影片中的最大視頻位元速率。</p></td>
</tr>
<tr class="even">
<td><p>VideoPacketLossRate</p></td>
<td><p>十進位 (9，4) </p></td>
<td><p>視頻封包遺失的速率。</p></td>
</tr>
<tr class="odd">
<td><p>VideoFrameLossRate</p></td>
<td><p>十進位 (9.4) </p></td>
<td><p>丟失之總影片框的百分比。</p></td>
</tr>
<tr class="even">
<td><p>VideoFEC</p></td>
<td><p>位</p></td>
<td><p>不會使用。</p></td>
</tr>
<tr class="odd">
<td><p>VideoAllocateBWAvg</p></td>
<td><p>int</p></td>
<td><p>為影片所分配的平均頻寬量。</p></td>
</tr>
<tr class="even">
<td><p>VideoLocalFrameLossPercentageAvg</p></td>
<td><p>十進位 (9.4) </p></td>
<td><p>已遺失之總影片框的百分比。</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>位</p></td>
<td><p>P-宣稱身分識別資訊的資料流程方向。 1表示資料流程是從來電者流向被呼叫者;0表示資料流程方向從被叫方傳送給來電者。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

