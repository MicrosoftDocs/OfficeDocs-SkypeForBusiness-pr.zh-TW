---
title: Lync Server 2013：MediaLine 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4828f67614115eb4d6f46ab0a0a7c315e02d1924
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a>Lync Server 2013 中的 MediaLine 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-21_

每個記錄代表一個媒體線。 （一個音訊會話通常包含一個音訊媒體線。 一個音訊與影片（A/V）會話通常包含一個音訊媒體線和一個視頻媒體線，但如果是使用會議裝置或使用了圖庫視圖，該會話可能包含兩個視頻媒體線。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>左欄</strong></th>
<th><strong>資料類型</strong></th>
<th><strong>索引鍵/索引</strong></th>
<th><strong>詳細資料</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>首選</p></td>
<td><p><a href="lync-server-2013-session-table.md">在 Lync Server 2013 的 [會話] 資料表中</a>參照。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>首選</p></td>
<td><p><a href="lync-server-2013-session-table.md">在 Lync Server 2013 的 [會話] 資料表中</a>參照。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>Tinyint</p></td>
<td><p>首選</p></td>
<td><p>0為主要音訊，1為主要影片，2為全景影片，3為應用程式/桌面共用。 這個標籤在單一會話中必須是唯一的。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectivityIce</strong></p></td>
<td><p>Tinyint</p></td>
<td><p> </p></td>
<td><p>此欄存在，但在 Microsoft Lync Server 2013 中未使用。 在 CallerConnectivityICE 和 CalleeConnectivityICE 欄中，會捕獲針對媒體線使用之連線性的相關資訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>有關在 bits 標誌中描述的互動式連接建立（ICE）程式的相關資訊。 如需詳細資訊，請參閱<em>體驗監視伺服器通訊協定規格的品質</em>（可供下載）。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>與 CallerIceWarningFlags 相同，但在被呼叫方端的那一側。 如需詳細資訊，請參閱<em>體驗監視伺服器通訊協定規格的品質</em>（可供下載）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>安全性</strong></p></td>
<td><p>Tinyint</p></td>
<td><p> </p></td>
<td><p>使用中的安全性設定檔。 0為 [無]，1為 SRTP，2為 V1。</p></td>
</tr>
<tr class="even">
<td><p><strong>傳輸</strong></p></td>
<td><p>Tinyint</p></td>
<td><p> </p></td>
<td><p>0是 UDP，1是 TCP。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>來電者的 IP 位址。 如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>呼叫者使用的埠。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerSubnet</strong></p></td>
<td><p>int</p></td>
<td><p> 外</p></td>
<td><p>來電者的子網。 如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerInside</strong></p></td>
<td><p>稍微</p></td>
<td><p> </p></td>
<td><p>1表示呼叫者是在商業網路內，0代表呼叫者在網路以外。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>來電者的 mac 位址，從<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 的 MacAddress 資料表中</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫者使用的 Lync Server A/V 邊緣服務 IP 位址。 如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>呼叫者在 A/V 邊緣服務上使用的埠。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫者使用的擷取裝置。 從<a href="lync-server-2013-device-table.md">Lync Server 2013 的裝置資料表中</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>由呼叫者使用的轉譯裝置。 從<a href="lync-server-2013-device-table.md">Lync Server 2013 的裝置資料表中</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫者的捕獲裝置驅動程式（從<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 的 DeviceDriver 資料表中</a>引用）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫者轉譯裝置的驅動程式，從<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 的 DeviceDriver 資料表中</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerNetworkConnectionType</strong></p></td>
<td><p>Tinyint</p></td>
<td><p>外</p></td>
<td><p>指出呼叫者連線到網路的方式。 值是從<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 的 NetworkConnectionDetail 資料表中</a>取得。 對於 WiFi 連線，一般的值為0（適用于有線連接，1）;如果是乙太網路連線，則為3。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerBssid</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫者的 BSSID （如果使用無線）。 從<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 的 MacAddress 資料表中</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerVPN</strong></p></td>
<td><p>稍微</p></td>
<td></td>
<td><p>來電者的連結。 1是虛擬私人網路（VPN），0是非 VPN。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerLinkSpeed</strong></p></td>
<td><p>小數（18，0）</p></td>
<td></td>
<td><p>呼叫者終點的網路連結速度（以 bps 為來）。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫接收器的 IP 位址。 如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePort</strong></p></td>
<td><p>稍微</p></td>
<td></td>
<td><p>呼叫接收器使用的埠。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeSubnet</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>被呼叫者的子網。 如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeInside</strong></p></td>
<td><p>稍微</p></td>
<td><p> </p></td>
<td><p>1代表呼叫接收器在商業網路內，0代表呼叫接收器在網路以外。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>被呼叫者的 Mac 位址。 從<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 的 MacAddress 資料表中</a>參考。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫接收器所使用之 A/V 邊緣服務的 IP 位址。 如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>由呼叫接收器在 A/V 邊緣服務上使用的埠。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>捕獲呼叫接收器使用的裝置。 從<a href="lync-server-2013-device-table.md">Lync Server 2013 的裝置資料表中</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫接收器所使用的轉譯裝置。 從<a href="lync-server-2013-device-table.md">Lync Server 2013 的裝置資料表中</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫接收器的擷取裝置的驅動程式。 從<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 的 DeviceDriver 資料表中</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDevDriver</strong></p></td>
<td><p>Varchar （256）</p></td>
<td><p>外</p></td>
<td><p>呼叫接收器的轉譯裝置的驅動程式。 從<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 的 DeviceDriver 資料表中</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeNetworkConnectionType</strong></p></td>
<td><p>Tinyint</p></td>
<td><p>外</p></td>
<td><p>表示被呼叫者連線到網路的方式。 值是從<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 的 NetworkConnectionDetail 資料表中</a>取得。 對於 WiFi 連線，一般的值為0（適用于有線連接，1）;如果是乙太網路連線，則為3。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeBssid</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>被呼叫者的 BSSID （如果使用無線）。 從<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 的 MacAddress 資料表中</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeVPN</strong></p></td>
<td><p>稍微</p></td>
<td><p> </p></td>
<td><p>呼叫接收器的連結;1是虛擬私人網路（VPN），0是非 VPN。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeLinkSpeed</strong></p></td>
<td><p>小數（18，0）</p></td>
<td><p> </p></td>
<td><p>呼叫接收器終點的網路連結速度，以 bps 為限。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConversationalMOS</strong></p></td>
<td><p>decimal （3，2）</p></td>
<td><p> </p></td>
<td><p>Narrowband 音訊會話的會話 MOS （根據兩個音訊資料流程）。</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimit</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>這是在給定各種原則設定（TURN、API、SDP、原則伺服器等）的情況下，套用到指定傳送端資料流程的實際頻寬。 這不會與有效的頻寬混淆，因為頻寬估計可能會有較低的效率。 這實際上是最大頻寬：傳送資料流程可能會受到頻寬估計所施加的限制。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>Smallint</p></td>
<td></td>
<td><p>這是強加頻寬上限的來源。 它描述頻寬限制的來源： [原則伺服器]、[轉換伺服器]、[模態] 等等。 從<a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013 的 AppliedBandwidthSource 資料表中</a>參考。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫</strong></p></td>
<td><p>稍微</p></td>
<td><p> </p></td>
<td><p>指出來自來電者的統計資料是否已收到;1為 [是]，null 值為 [否]。</p></td>
</tr>
<tr class="odd">
<td><p><strong>方</strong></p></td>
<td><p>稍微</p></td>
<td><p> </p></td>
<td><p>指出是否已收到來自呼叫接收器的指標;1為 [是]，null 值為 [否]。</p></td>
</tr>
<tr class="even">
<td><p><strong>MidCallReport</strong></p></td>
<td><p>稍微</p></td>
<td></td>
<td><p>指出報告是針對會話的一部分或完整的會話。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>稍微</p></td>
<td></td>
<td><p>指出通話是分類為不佳通話（值為1）或良好通話（0）。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerConnectivityICE</strong></p></td>
<td><p>tinyInt</p></td>
<td></td>
<td><p>指示呼叫者是否使用 ICE 通訊協定（網際網路連線建立）連線至網路。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeConnectivityICE</strong></p></td>
<td><p>Tinyint</p></td>
<td></td>
<td><p>指示呼叫者是否使用 ICE 通訊協定（網際網路連線建立）連線至網路。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>撥打電話之使用者的反身 IP 位址。 在使用 NAT （網路位址轉譯）的組織中，反身 IP 位址是 proxy 伺服器的 IP 位址。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>撥打電話之使用者所採用的 WiFi 驅動程式的裝置描述。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>撥打電話之使用者所採用的 WiFi 驅動程式版本號碼。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>接收通話之使用者的反身 IP 位址。 在使用 NAT （網路位址轉譯）的組織中，反身 IP 位址是 proxy 伺服器的 IP 位址。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>接收通話之使用者所使用之 WiFi 驅動程式的裝置描述。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>接收通話之使用者所使用的 WiFi 驅動程式版本號碼。</p>
<p>此欄是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

