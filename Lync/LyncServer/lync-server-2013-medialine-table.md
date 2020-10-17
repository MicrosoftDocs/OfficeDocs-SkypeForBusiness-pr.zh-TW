---
title: Lync Server 2013： MediaLine 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03f967b50c2fa9eae4f2599ce96dc9c592a57006
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516140"
---
# <a name="medialine-table-in-lync-server-2013"></a>Lync Server 2013 中的 MediaLine 表格

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-21_

每筆記錄代表一個媒體行。  (一個音訊會話通常會包含一個音訊媒體線。 一個音訊和影片 (A/V) 會話通常會包含一個音訊媒體線和一個影片媒體線，但如果使用會議裝置或使用畫廊 View，則會話可能會包含兩個影片媒體線。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>欄</strong></th>
<th><strong>資料類型</strong></th>
<th><strong>索引鍵/索引</strong></th>
<th><strong>詳細資料</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主要</p></td>
<td><p>從 <a href="lync-server-2013-session-table.md">Lync Server 2013 中的會話表</a>參考。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主要</p></td>
<td><p>從 <a href="lync-server-2013-session-table.md">Lync Server 2013 中的會話表</a>參考。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>Tinyint</p></td>
<td><p>主要</p></td>
<td><p>0為主要音訊、1為主要影片，2是全景影片，3是應用程式/桌面共用。 此標籤在單一會話中必須是唯一的。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectivityIce</strong></p></td>
<td><p>Tinyint</p></td>
<td><p> </p></td>
<td><p>此欄存在，但未用於 Microsoft Lync Server 2013。 CallerConnectivityICE 和 CalleeConnectivityICE 欄中已捕獲用於媒體線之連線的相關資訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>有關互動式連線建立 (冰) 程式的資訊，請參閱 bits 旗中所述的處理常式。 如需詳細資訊，請參閱可供下載的 <em>經驗品質監控伺服器通訊協定規格</em>。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>與 CallerIceWarningFlags 相同，但在被呼叫者的一端。 如需詳細資訊，請參閱可供下載的 <em>經驗品質監控伺服器通訊協定規格</em>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>安全性</strong></p></td>
<td><p>Tinyint</p></td>
<td><p> </p></td>
<td><p>使用中的安全性設定檔。 0 是無 (NONE)，1 是 SRTP，2 是 V1。</p></td>
</tr>
<tr class="even">
<td><p><strong>傳輸</strong></p></td>
<td><p>Tinyint</p></td>
<td><p> </p></td>
<td><p>0 是 UDP，1 是 TCP。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>來電者的 IP 位址。 如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>發話者使用的連接埠。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerSubnet</strong></p></td>
<td><p>int</p></td>
<td><p> 外國</p></td>
<td><p>來電者的子網。 如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerInside</strong></p></td>
<td><p>位</p></td>
<td><p> </p></td>
<td><p>1表示來電者位於商業網路內，0表示來電者位於網路外。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>來電者的 mac 位址（從 <a href="lync-server-2013-macaddress-table.md">Lync Server 2013 的 MacAddress 表格中</a>參照）。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>呼叫者使用之 Lync Server A/V Edge service 的 IP 位址。 如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>呼叫者在 A/V Edge service 上使用的埠。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>呼叫者使用的捕獲裝置。 從 <a href="lync-server-2013-device-table.md">Lync Server 2013 的裝置資料表中</a>參照。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>由來電者使用的呈現裝置。 從 <a href="lync-server-2013-device-table.md">Lync Server 2013 的裝置資料表中</a>參照。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>呼叫者的捕獲裝置的驅動程式，從 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 的 DeviceDriver 表格中</a>參照。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>呼叫者的轉譯裝置的驅動程式，從 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 的 DeviceDriver 表格中</a>參照。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerNetworkConnectionType</strong></p></td>
<td><p>Tinyint</p></td>
<td><p>Foreign</p></td>
<td><p>會指出來電者連線到網路的方式。 <a href="lync-server-2013-networkconnectiondetail-table.md">在 Lync Server 2013 中從 NetworkConnectionDetail 表格</a>取得的值。 一般值為0表示 WiFi 連線的有線連接 ' 1;在乙太網路連線時使用3。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerBssid</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>使用無線時的來電者 BSSID。 <a href="lync-server-2013-macaddress-table.md">在 Lync Server 2013 中從 MacAddress 表</a>參考。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerVPN</strong></p></td>
<td><p>位</p></td>
<td></td>
<td><p>來電者的連結。 1 是虛擬私人網路 (VPN)，0 是非 VPN。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerLinkSpeed</strong></p></td>
<td><p>十進位 (18，0) </p></td>
<td></td>
<td><p>來電者端點的網路連結速度（bps）。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>通話接收器的 IP 位址。 如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePort</strong></p></td>
<td><p>位</p></td>
<td></td>
<td><p>呼叫接收器使用的埠。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeSubnet</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>被呼叫者的子網。 如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeInside</strong></p></td>
<td><p>位</p></td>
<td><p> </p></td>
<td><p>1表示呼叫接收器位於商業網路內，0表示通話接收器位於網路外。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>被呼叫者的 Mac 位址。 從 <a href="lync-server-2013-macaddress-table.md">Lync Server 2013 的 MacAddress 表格中</a>參照。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>呼叫接收器所使用之 A/V Edge service 的 IP 位址。 如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>呼叫接收器在 A/V Edge Service 上使用的埠。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>外國</p></td>
<td><p>用於呼叫接收器的捕獲裝置。 從 <a href="lync-server-2013-device-table.md">Lync Server 2013 的裝置資料表中</a>參照。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>會呈現呼叫接收器所使用的裝置。 從 <a href="lync-server-2013-device-table.md">Lync Server 2013 的裝置資料表中</a>參照。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>呼叫接收器的捕獲裝置的驅動程式。 <a href="lync-server-2013-devicedriver-table.md">在 Lync Server 2013 中從 DeviceDriver 表</a>參考。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDevDriver</strong></p></td>
<td><p>Varchar (256) </p></td>
<td><p>Foreign</p></td>
<td><p>呼叫接收器的呈現裝置的驅動程式。 <a href="lync-server-2013-devicedriver-table.md">在 Lync Server 2013 中從 DeviceDriver 表</a>參考。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeNetworkConnectionType</strong></p></td>
<td><p>Tinyint</p></td>
<td><p>Foreign</p></td>
<td><p>會指出被呼叫者連線到網路的方式。 <a href="lync-server-2013-networkconnectiondetail-table.md">在 Lync Server 2013 中從 NetworkConnectionDetail 表格</a>取得的值。 一般值為0表示 WiFi 連線的有線連接 ' 1;在乙太網路連線時使用3。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeBssid</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>使用無線時，被呼叫者的 BSSID。 <a href="lync-server-2013-macaddress-table.md">在 Lync Server 2013 中從 MacAddress 表</a>參考。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeVPN</strong></p></td>
<td><p>位</p></td>
<td><p> </p></td>
<td><p>通話接收器的連結;1是虛擬私人網路 (VPN) ，0是非 VPN。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeLinkSpeed</strong></p></td>
<td><p>十進位 (18，0) </p></td>
<td><p> </p></td>
<td><p>通話接收器端點的網路連結速度（bps）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConversationalMOS</strong></p></td>
<td><p>十進位 (3，2) </p></td>
<td><p> </p></td>
<td><p>音訊工作階段的窄頻交談方式 MOS (兩種音訊資料流皆為依據)。</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimit</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>這是套用至指定之傳送端資料流程的實際頻寬，指定各種原則設定 (轉換、API、SDP、原則伺服器等等) 。 這並不會混淆有效的頻寬，因為頻寬估算可能會有較低的有效頻寬。 基本上，除了頻寬預估值規定的限制以外，這是傳送端資料流所能取得的最大頻寬。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>Smallint</p></td>
<td></td>
<td><p>這是所採用的頻寬容量來源。 它說明頻寬限制來自 ( "Policy Server"、"輪流伺服器"、"模態" 等) 。 從 <a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013 的 AppliedBandwidthSource 表格中</a>參照。</p></td>
</tr>
<tr class="even">
<td><p><strong>Caller</strong></p></td>
<td><p>位</p></td>
<td><p> </p></td>
<td><p>會指出是否已收到來自來電者的計量值;1為 [是]，null 值為 [否]。</p></td>
</tr>
<tr class="odd">
<td><p><strong>方</strong></p></td>
<td><p>位</p></td>
<td><p> </p></td>
<td><p>會指出是否已收到來自呼叫接收器的計量值;1為 [是]，null 值為 [否]。</p></td>
</tr>
<tr class="even">
<td><p><strong>MidCallReport</strong></p></td>
<td><p>位</p></td>
<td></td>
<td><p>會指出報表是針對會話的一部分，還是完整的會話。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>位</p></td>
<td></td>
<td><p>會指出呼叫是否分類為 (1) 或良好通話 (0) 的通話是否不良。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerConnectivityICE</strong></p></td>
<td><p>tinyInt</p></td>
<td></td>
<td><p>指出發話者是否使用 ICE 通訊協定 (網際網路連線建立) 連線至網路。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeConnectivityICE</strong></p></td>
<td><p>Tinyint</p></td>
<td></td>
<td><p>指出發話者是否使用 ICE 通訊協定 (網際網路連線建立) 連線至網路。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>撥打電話之使用者的反身 IP 位址。 在使用 NAT (網路位址轉譯) 的組織中，反身 IP 位址是 proxy 伺服器的 IP 位址。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>撥打通話之使用者所使用之 WiFi 驅動程式的裝置描述。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>撥打通話之使用者所使用 WiFi 驅動程式的版本號碼。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>接收通話之使用者的反身 IP 位址。 在使用 NAT (網路位址轉譯) 的組織中，反身 IP 位址是 proxy 伺服器的 IP 位址。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>接收通話之使用者所使用之 WiFi 驅動程式的裝置描述。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>接收通話之使用者所使用 WiFi 驅動程式的版本號碼。</p>
<p>此欄是在 Microsoft Lync Server 2013 中引進。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

