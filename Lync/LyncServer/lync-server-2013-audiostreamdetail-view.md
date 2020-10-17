---
title: Lync Server 2013： AudioStreamDetail view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStreamDetail view
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49733792
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a9abfbc214e72cf059250910ecec4ad3bcdba33
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515780"
---
# <a name="audiostreamdetail-view-in-lync-server-2013"></a>Lync Server 2013 中的 AudioStreamDetail 視圖

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

AudioStreamDetail View 儲存資料庫中每個音訊資料流程的資訊。 此視圖已引進于 Microsoft Lync Server 2013。


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
<th>詳細資料</th>
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
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>媒體行中的唯一識別碼。</p></td>
</tr>
<tr class="even">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>會話的開始時間。</p></td>
</tr>
<tr class="odd">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>工作階段結束時間。</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>位</p></td>
<td><p>對話方塊類別：0是 Lync Server 的轉送伺服器腿;1是轉送伺服器到 PSTN 閘道腿。</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>位</p></td>
<td><p>指示是否略過呼叫的旗標。</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>如果有的話，則表示即使旁路 IDs 相符也不會略過通話的原因。 只定義了一個值：</p>
<p>0x0001 –預設網路介面卡的未知旁路識別碼。</p></td>
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
<td><p>來電者使用者代理程式的類型。 如需詳細資訊，請參閱 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>Nvarchar (64) </p></td>
<td><p>來電者使用者代理程式的類別。 如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef 表格 (Lync Server 2013 中的 QoE) </a> 。</p></td>
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
<td><p>來電者端點中的 CPU 核心數目。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>Smallint</p></td>
<td><p>受話者端點中的 CPU 核心數目。</p></td>
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
<td><p>CorrelationKey</p></td>
<td></td>
<td><p>相關機碼。 從 <a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 的 SessionCorrelation 表格中</a>參照。</p></td>
</tr>
<tr class="odd">
<td><p>ConnectivityIce</p></td>
<td><p>Tinyint</p></td>
<td><p>媒體路徑的相關資訊，例如 direct 或中繼。 如需詳細資訊，請參閱 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>發話者位元旗標中描述之互動式連線建立 (ICE) 程序的相關資訊。如需詳細資訊，請參閱＜經驗品質監控伺服器通訊協定規格＞。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>受話者位元旗標中描述之互動式連線建立 (ICE) 程序的相關資訊。如需詳細資訊，請參閱＜經驗品質監控伺服器通訊協定規格＞。</p></td>
</tr>
<tr class="even">
<td><p>傳輸</p></td>
<td><p>Tinyint</p></td>
<td><p>傳輸類型：0是 UDP，1是 TCP。</p></td>
</tr>
<tr class="odd">
<td><p>CallerIPAddr</p></td>
<td><p>var (50) </p></td>
<td><p>來電者的 IP 位址。 這可以是 IPv4 或 IPv6 位址。</p></td>
</tr>
<tr class="even">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>發話者使用的連接埠。</p></td>
</tr>
<tr class="odd">
<td><p>CallerInside</p></td>
<td><p>位</p></td>
<td><p>會指出來電者是否在間隔網路內：1表示來電者位於商業網路內，0表示來電者位於網路外。</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50) </p></td>
<td><p>被呼叫者的 IP 位址。 這可以是 IPv4 或 IPv6 位址。</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>受話者使用的連接埠。</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>位</p></td>
<td><p>會指出受話者是否在間隔網路內：1表示受話者位於商業網路內，0表示受話者位於網路外。</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserSite</p></td>
<td><p>Nvarchar (128) </p></td>
<td><p>來電者網站的名稱。</p></td>
</tr>
<tr class="even">
<td><p>CallerRegion</p></td>
<td><p>Nvarchar (128) </p></td>
<td><p>來電者網站的國家/地區名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserSite</p></td>
<td><p>Nvarchar (128) </p></td>
<td><p>被呼叫者之網站的名稱。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRegion</p></td>
<td><p>Nvarchar (128) </p></td>
<td><p>被呼叫者網站的國家/地區名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50) </p></td>
<td><p>發話者使用之 A/V Edge Service 的 IP 位址。 如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>發話者在 A/V Edge Service 上使用的連接埠。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50) </p></td>
<td><p>被呼叫者所使用之 A/V Edge service 的 IP 位址金鑰。 如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>受話者在 A/V Edge Service 上使用的連接埠。</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDev</p></td>
<td><p>Varchar (256) </p></td>
<td><p>發話者的擷取裝置名稱。</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDev</p></td>
<td><p>Varchar (256) </p></td>
<td><p>發話者的轉換裝置名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>Varchar (256) </p></td>
<td><p>發話者的擷取裝置驅動程式名稱。</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDriver</p></td>
<td><p>Varchar (256) </p></td>
<td><p>發話者的轉換裝置驅動程式名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>Varchar (256) </p></td>
<td><p>受話者的擷取裝置名稱。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>Varchar (256) </p></td>
<td><p>受話者的轉換裝置名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDevDriver</p></td>
<td><p>Varchar (256) </p></td>
<td><p>受話者的擷取裝置驅動程式名稱。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>Varchar (256) </p></td>
<td><p>受話者的轉換裝置驅動程式名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>Tinyint</p></td>
<td><p>來電者的網路連線類型：0是有線的，1是無線。</p></td>
</tr>
<tr class="even">
<td><p>CallerVPN</p></td>
<td><p>位</p></td>
<td><p>會指出呼叫者是否是透過虛擬私人網路絡（1是虛擬私人網路） (VPN) ，0是非 VPN。</p></td>
</tr>
<tr class="odd">
<td><p>CallerLinkSpeed</p></td>
<td><p>十進位 (18，0) </p></td>
<td><p>呼叫者端點的網路連結速度（bps）。</p></td>
</tr>
<tr class="even">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>Tinyint</p></td>
<td><p>被呼叫者的網路連線類型：0是有線的，1是無線。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>位</p></td>
<td><p>會指出呼叫者是否是透過虛擬私人網路絡（1是虛擬私人網路） (VPN) ，0是非 VPN。</p></td>
</tr>
<tr class="even">
<td><p>CalleeLinkSpeed</p></td>
<td><p>十進位 (18，0) </p></td>
<td><p>被呼叫者端點的網路連結速度（bps）。</p></td>
</tr>
<tr class="odd">
<td><p>ConversationalMOS</p></td>
<td><p>十進位 (3，2) </p></td>
<td><p>音訊工作階段的窄頻交談方式 MOS (兩種音訊資料流皆為依據)。</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>針對指定之傳送端資料流程套用至指定之傳送端資料流程的實際頻寬，可 (轉換、API、SDP、原則伺服器等等) 。 這並不會混淆有效的頻寬，因為頻寬估算可能會有較低的有效頻寬。 這基本上是傳送資料流程可以採用限制頻寬估計所強加限制的最大頻寬</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>從即時控制通訊協定 (RTCP) 統計資料的平均網路抖動。</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>通話期間的最大網路抖動。</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRate</p></td>
<td><p>十進位 (5，4) </p></td>
<td><p>通話期間的平均封包遺失率。</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRateMax</p></td>
<td><p>十進位 (5，4) </p></td>
<td><p>通話期間觀察到的封包遺失上限。</p></td>
</tr>
<tr class="odd">
<td><p>BurstDensity</p></td>
<td><p>十進位 (9，4) </p></td>
<td><p>通話期間的猝量遺失期間的封包遺失平均密度。</p></td>
</tr>
<tr class="even">
<td><p>BurstDuration</p></td>
<td><p>int</p></td>
<td><p>通話期間的猝量遺失期間的封包遺失平均持續時間。</p></td>
</tr>
<tr class="odd">
<td><p>BurstGapDensity</p></td>
<td><p>十進位 (9，4) </p></td>
<td><p>封包遺失失敗之間的平均封包遺失密度。</p></td>
</tr>
<tr class="even">
<td><p>BurstGapDuration</p></td>
<td><p>int</p></td>
<td><p>封包遺失的平均持續時間。</p></td>
</tr>
<tr class="odd">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>音訊資料流程的封包計數。</p></td>
</tr>
<tr class="even">
<td><p>BandwidthEst</p></td>
<td><p>int</p></td>
<td><p>音訊資料流程的頻寬估計值。</p></td>
</tr>
<tr class="odd">
<td><p>DegradationAvg</p></td>
<td><p>十進位 (3，2) </p></td>
<td><p>整個通話的網路 MOS 降低。 範圍是0.0 到5.0。 此度量顯示由於抖動和封包遺失，網路 MOS 減少的數量。 可接受的品質應小於0.5。</p></td>
</tr>
<tr class="even">
<td><p>DegradationMax</p></td>
<td><p>十進位 (3，2) </p></td>
<td><p>通話期間的最大網路 MOS 降級。</p></td>
</tr>
<tr class="odd">
<td><p>DegradationJitterAvg</p></td>
<td><p>十進位 (3，2) </p></td>
<td><p>抖動導致的網路 MOS 降低。</p></td>
</tr>
<tr class="even">
<td><p>DegradationPacketLossAvg</p></td>
<td><p>十進位 (3，2) </p></td>
<td><p>封包遺失導致的網路 MOS 降低。</p></td>
</tr>
<tr class="odd">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>用於通話的音訊編解碼器，從 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 的 PayloadDescription 表格中</a>參照。</p></td>
</tr>
<tr class="even">
<td><p>AudioSampleRate</p></td>
<td><p>int</p></td>
<td><p>音訊資料流程的取樣速率。</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>來電者所傳送之音訊的後續類比增益控制音訊信號層級。 此度量單位的單位是 dBmo。 若要取得可接受的品質，至少要有 30 dBmo。 A/V 的會議服務器或 IP 電話不會報告此度量。</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>來電者接收之音訊的音訊信號層級。 此度量單位的單位是 dBmo。 若要取得可接受的品質，至少要有 30 dBmo。 A/V 的會議服務器或 IP 電話不會報告此度量。</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>來電者所傳送之音訊的後續類比增益控制音訊雜訊層級。 此度量單位的單位是 dBmo。 針對可接受的品質，它應小於 35 dBmo。 A/V 的會議服務器或 IP 電話不會報告此度量。</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>來電者接收之音訊的後續類比增益控制音訊雜訊層級。 此度量單位的單位是 dBmo。 針對可接受的品質，它應小於 35 dBmo。 A/V 的會議服務器或 IP 電話不會報告此度量。</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoReturn</p></td>
<td><p>int</p></td>
<td><p>呼叫來電者的回顯回復功能增強功能。 此度量單位的單位為 dB。 較低的值表示較少的回聲。 A/V 的會議服務器或 IP 電話不會報告此度量。</p></td>
</tr>
<tr class="even">
<td><p>CallerSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>呼叫者的喇叭轉譯每五分鐘的平均故障。 為了獲得良好的品質，應小於每五分鐘一次。 不會 A/V 會議伺服器、轉送伺服器或 IP 電話上報告。</p></td>
</tr>
<tr class="odd">
<td><p>CallerMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>來電者的擴音器 capture 每五分鐘的平均故障。 若為良好的品質，這應小於每五分鐘一次。 不會 A/V 會議伺服器、轉送伺服器或 IP 電話上報告。</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampDriftRateMic</p></td>
<td><p>十進位 (9，2) </p></td>
<td><p>來電者的麥克風裝置時鐘相對於 CPU 時鐘的相對頻率。</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampDriftRateSpk</p></td>
<td><p>十進位 (9，2) </p></td>
<td><p>來電者的揚聲器裝置時鐘相對於 CPU 時鐘的相對頻率。</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampErrorMicMs</p></td>
<td><p>十進位 (9，2) </p></td>
<td><p>通話的最後20秒內的平均麥克風捕獲資料流程時間戳記錯誤（毫秒）。</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampErrorSpkMs</p></td>
<td><p>十進位 (9，2) </p></td>
<td><p>呼叫者的最後20秒內，平均來電者的發言人轉譯資料流程時間戳記錯誤（毫秒）。</p></td>
</tr>
<tr class="even">
<td><p>CallerVsEntryCauses</p></td>
<td><p>Smallint</p></td>
<td><p>語音開關是一種具有低中斷能力的半雙工模式。 如需詳細資訊，請參閱 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoEventCauses</p></td>
<td><p>Tinyint</p></td>
<td><p>來電者的 echo 事件原因。 如需詳細資訊，請參閱 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p>CallerEchoPercentMicIn</p></td>
<td><p>十進位 (5，2) </p></td>
<td><p>在來電者的麥克風捕獲資料流程中偵測到迴響的時間百分比。 如果使用的是耳機，則值應該很低。</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoPercentSend</p></td>
<td><p>十進位 (5，2) </p></td>
<td><p>在來電者的傳送資料流程中偵測到迴響的時間百分比。 傳送資料流程中的高回音百分比會傳回回聲洩漏。</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>從來電者音訊的閘道，在轉送伺服器上接收信號等級;這只適用于轉送伺服器。 此度量單位為 dBoV。 為了獲得良好的品質，可接受的範圍應為-30 到-18 dBoV。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>從來電者的音訊的閘道處接收轉送伺服器上的信號等級。 這只適用于轉送伺服器。 此度量單位為 dBoV。 為了獲得良好的品質，可接受的範圍應小於-50 dBoV。</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>在套用至來電者音訊的轉送伺服器端 (AGC) 自動取得控制權。</p></td>
</tr>
<tr class="odd">
<td><p>CallerInitialSignalLevelRMS</p></td>
<td><p>float</p></td>
<td><p>對來電者傳入的信號的根平均方 (RMS) ，最多可達前30秒的呼叫。</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>代表被呼叫者所傳送之音訊的後續類比增益控制音訊信號等級。 此度量單位的單位是 dBmo。 若要取得可接受的品質，至少要有 30 dBmo。 A/V 的會議服務器或 IP 電話不會報告此度量。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>被呼叫者所接收之音訊的音訊信號層級。 此度量單位的單位是 dBmo。 若要取得可接受的品質，至少要有 30 dBmo。 A/V 的會議服務器或 IP 電話不會報告此度量。</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>受話者所傳送之音訊的後續類比增益控制音訊雜訊層級。 此度量單位的單位是 dBmo。 針對可接受的品質，它應小於 35 dBmo。 A/V 的會議服務器或 IP 電話不會報告此度量。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>受話者接收之音訊的後續類比增益控制音訊雜訊層級。 此度量單位的單位是 dBmo。 針對可接受的品質，它應小於 35 dBmo。 A/V 的會議服務器或 IP 電話不會報告此度量。</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoReturn</p></td>
<td><p>int</p></td>
<td><p>被呼叫者的回顯傳回遺失增強功能。 此度量單位的單位為 dB。 較低的值表示較少的回聲。 A/V 的會議服務器或 IP 電話不會報告此度量。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>被呼叫者的喇叭轉譯每五分鐘的平均故障。 為了獲得良好的品質，應小於每五分鐘一次。 不會 A/V 會議伺服器、轉送伺服器或 IP 電話上報告。</p></td>
</tr>
<tr class="even">
<td><p>CalleeMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>受話者麥克風捕獲每五分鐘的平均故障。 若為良好的品質，這應小於每五分鐘一次。 不會 A/V 會議伺服器、轉送伺服器或 IP 電話上報告。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampDriftRateMic</p></td>
<td><p>十進位 (9，2) </p></td>
<td><p>受話者的麥克風裝置時鐘相對於 CPU 時鐘的相對頻率。</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampDriftRateSpk</p></td>
<td><p>十進位 (9，2) </p></td>
<td><p>受話者的揚聲器裝置時鐘相對於 CPU 時鐘的相對頻率。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampErrorMicMs</p></td>
<td><p>十進位 (9，2) </p></td>
<td><p>通話的最後20秒內的平均麥克風捕獲資料流程時間戳記錯誤（毫秒）。</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampErrorSpkMs</p></td>
<td><p>十進位 (9，2) </p></td>
<td><p>通話的最後20秒內，被呼叫者的發言人轉譯資料流程時間戳記錯誤（毫秒）。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVsEntryCauses</p></td>
<td><p>Smallint</p></td>
<td><p>語音開關是一種具有低中斷能力的半雙工模式。 如需詳細資訊，請參閱 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoEventCauses</p></td>
<td><p>Tinyint</p></td>
<td><p>被呼叫者的 echo 事件原因。 如需詳細資訊，請參閱 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEchoPercentMicIn</p></td>
<td><p>十進位 (5，2) </p></td>
<td><p>被呼叫者的麥克風捕獲資料流程中偵測到迴響的時間百分比。 如果使用的是耳機，則值應該很低。</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoPercentSend</p></td>
<td><p>十進位 (5，2) </p></td>
<td><p>在被呼叫者的已傳送資料流程中偵測到迴響的時間百分比。 傳送資料流程中的高回音百分比會傳回回聲洩漏。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>從受話者的音訊的閘道從轉送伺服器接收信號層級;這只適用于轉送伺服器。 此度量單位為 dBoV。 為了獲得良好的品質，可接受的範圍應為 [-30 到-18] dBoV。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>從所呼叫者音訊的閘道，在轉送伺服器上收到的信號等級。 這只適用于轉送伺服器。 此度量單位為 dBoV。 為了獲得良好的品質，可接受的範圍應小於-50 dBoV。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>在套用至受話者音訊的轉送伺服器端 (AGC) 自動取得控制權。</p></td>
</tr>
<tr class="even">
<td><p>CalleeInitialSignalLevelRMS</p></td>
<td><p>float</p></td>
<td><p>從來電者傳入的信號的根平均平方 (RMS) ，最多可達前30秒的呼叫。</p></td>
</tr>
<tr class="odd">
<td><p>RatioConcealedSamplesAvg</p></td>
<td><p>十進位 (5，2) </p></td>
<td><p>音訊修復所產生之隱藏樣本與一般範例的平均比率。</p></td>
</tr>
<tr class="even">
<td><p>RatioStretchedSamplesAvg</p></td>
<td><p>十進位 (5，2) </p></td>
<td><p>音訊修復所產生之延伸樣本的平均比率為典型範例。</p></td>
</tr>
<tr class="odd">
<td><p>RatioCompressedSamplesAvg</p></td>
<td><p>十進位 (5，2) </p></td>
<td><p>音訊修復所產生之壓縮樣本與一般範例的平均比率。</p></td>
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
<td><p>OverallAvgNetworkMOS</p></td>
<td><p>十進位 (3，2) </p></td>
<td><p>通話的平均寬頻網路 MOS。 此度量取決於所用的封包遺失、抖動和編解碼器。 範圍是1.0 到5.0。</p></td>
</tr>
<tr class="odd">
<td><p>OverallMinNetworkMOS</p></td>
<td><p>十進位 (3，2) </p></td>
<td><p>通話的最小寬頻網路 MOS。</p></td>
</tr>
<tr class="even">
<td><p>SendListenMOS</p></td>
<td><p>十進位 (3，2) </p></td>
<td><p>已傳送之音訊的平均預測寬頻傾聽 MOS 分數，包括語音層級、雜訊層級和捕獲裝置特性。</p></td>
</tr>
<tr class="odd">
<td><p>SendListenMOSMin</p></td>
<td><p>十進位 (3，2) </p></td>
<td><p>通話的最小 SendListenMOS。</p></td>
</tr>
<tr class="even">
<td><p>RecvListenMOS</p></td>
<td><p>十進位 (3，2) </p></td>
<td><p>從網路接收之音訊的平均預測寬頻傾聽 MOS 分數，包括語音層級、雜訊層級、編解碼器、網路狀況和捕獲裝置特性。</p></td>
</tr>
<tr class="odd">
<td><p>RecvListenMOSMin</p></td>
<td><p>十進位 (3，2) </p></td>
<td><p>通話的最小 RecvListenMOS。</p></td>
</tr>
<tr class="even">
<td><p>AudioFECUsed</p></td>
<td><p>位</p></td>
<td><p>會指出是否使用音訊 FEC 進行通話。</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>位</p></td>
<td><p>表示 p 宣稱識別資訊的方向;1表示資料流程是從來電者流向被呼叫者;0表示資料流程方向從被叫方傳送給來電者。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

