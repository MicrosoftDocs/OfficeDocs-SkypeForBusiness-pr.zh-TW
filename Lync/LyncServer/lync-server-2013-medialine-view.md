---
title: Lync Server 2013： MediaLine view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d930f3beeeddb5c5582f41c44f1c68ff7f21f18d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a>Lync Server 2013 中的 [MediaLine] 視圖

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

[MediaLine] 視圖會儲存資料庫中每個媒體線的相關資訊。 一個音訊會話通常包含一個音訊媒體線。 一個音訊與影片（A/V）會話通常包含一個音訊媒體線和一個影片媒體線;不過，如果使用會議裝置或使用圖庫視圖，該會話可能會包含兩個視頻媒體線。 此視圖已在 Microsoft Lync Server 2013 中推出。


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
<td><p>ConferenceDateTime</p></td>
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
<td><p>安全性</p></td>
<td><p>Tinyint</p></td>
<td><p>安全設定檔正在使用中。 0為 [無]，1為 SRTP，2為 V1。</p></td>
</tr>
<tr class="odd">
<td><p>傳輸</p></td>
<td><p>Tinyint</p></td>
<td><p>傳輸類型。 0是 UDP，1是 TCP。</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>來電者的 IP 位址。 這可以是 IPv4 或 IPv6 位址。</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>呼叫者使用的埠。</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>稍微</p></td>
<td><p>指出來電者是否在組織網路內。 1表示呼叫者是在商業網路內。 0代表呼叫者在網路以外。</p></td>
</tr>
<tr class="odd">
<td><p>CallerMacAddress</p></td>
<td><p>Varchar （256）</p></td>
<td><p>呼叫者使用之網路介面的 MAC 位址。</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>呼叫者所使用之 A/V 邊緣服務的 IP 位址。 如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>呼叫者使用的 A/V 邊緣服務上使用的埠。</p></td>
</tr>
<tr class="even">
<td><p>CallerReflexiveIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>由 A/V 邊緣服務報告的呼叫者 IP 位址。 此位址可能會與 CallerIPAddr （例如，如果用戶端位於 NAT 之後）不同。</p></td>
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
<td><p>CallerRenderDevDriver</p></td>
<td><p>Varchar （256）</p></td>
<td><p>來電者的轉譯裝置驅動程式名稱。</p></td>
</tr>
<tr class="odd">
<td><p>CallerWifiDriverDeviceDesc</p></td>
<td><p>Varchar （256</p></td>
<td><p>呼叫者的 Wifi 驅動程式描述。</p></td>
</tr>
<tr class="even">
<td><p>CallerWifiDriverVersion</p></td>
<td><p>Varchar （256）</p></td>
<td><p>呼叫者的 Wifi 驅動程式版本。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>Varchar （256）</p></td>
<td><p>呼叫者網路連線的詳細資料。 如需詳細資訊，請參閱<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中</a>的 [NetworkConnectionDetail] 資料表。</p></td>
</tr>
<tr class="even">
<td><p>CallerBssid</p></td>
<td><p>Varchar （256）</p></td>
<td><p>呼叫者 WiFi 連線所使用的基本服務組識別元。</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>稍微</p></td>
<td><p>指出呼叫者是否已經由虛擬專用網路連接。 1是虛擬私人網路（VPN），0是非 VPN。</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>被呼叫者的 IP 位址。 這可以是 IPv4 或 IPv6 位址。</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>被呼叫者使用的埠。</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>稍微</p></td>
<td><p>指出被呼叫者是否在商業網路內。 1代表被呼叫者是在商業網路內，0代表被呼叫者在網路以外。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeMacAddress</p></td>
<td><p>Varchar （256）</p></td>
<td><p>被呼叫者使用的網路介面 MAC 位址。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>被呼叫者所使用之 A/V 邊緣服務的 IP 位址。 如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>在被呼叫者所使用的 A/V 邊緣服務上使用的埠。</p></td>
</tr>
<tr class="even">
<td><p>CalleeReflexiveIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>被呼叫者的 IP 位址，由 A/V 邊緣服務所報告。 此位址可能會與 CalleeIPAddr （例如，如果用戶端位於 NAT 之後）不同。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>var （50）</p></td>
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
<td><p>CalleeWifiDriverDeviceDesc</p></td>
<td><p>Varchar （256）</p></td>
<td><p>被呼叫者的 Wifi 驅動程式描述。</p></td>
</tr>
<tr class="even">
<td><p>CalleeWifiDriverVersion</p></td>
<td><p>Varchar （256</p></td>
<td><p>被呼叫者的 Wifi 驅動程式版本。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>Varchar （256）</p></td>
<td><p>被呼叫者網路連線的詳細資料。 如需詳細資訊，請參閱<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中</a>的 [NetworkConnectionDetail] 資料表。</p></td>
</tr>
<tr class="even">
<td><p>CalleeBssid</p></td>
<td><p>Varchar （256）</p></td>
<td><p>被呼叫者的 WiFi 連線所使用的基本服務組識別元。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>稍微</p></td>
<td><p>指出被呼叫者是否已經由虛擬私人網路絡進行連線。 1是虛擬私人網路（VPN），0是非 VPN。</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>decimal （3，2）</p></td>
<td><p>Narrowband 音訊會話的會話 MOS （根據兩個音訊資料流程）。</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>這是在給定各種原則設定（TURN、API、SDP、原則伺服器等）的情況下，套用到指定傳送端資料流程的實際頻寬。 您應該不要將它與有效的頻寬混淆，因為頻寬估計可能會有較低的效率。 這實際上是最大頻寬：傳送資料流程可能會受到頻寬估計所施加的限制。</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthSource</p></td>
<td><p>Varchar （256）</p></td>
<td><p>強加頻寬上限的來源。 它描述頻寬限制的來源（例如，「原則伺服器」、「轉換伺服器」或「模態」）。</p></td>
</tr>
<tr class="odd">
<td><p>呼叫</p></td>
<td><p>稍微</p></td>
<td><p>指出來自來電者的統計資料是否已收到;1為 [是]，0為 [否]。</p></td>
</tr>
<tr class="even">
<td><p>方</p></td>
<td><p>稍微</p></td>
<td><p>指出是否已收到來自呼叫接收器的指標;1為 [是]，0為 [否]。</p></td>
</tr>
<tr class="odd">
<td><p>MidCallReport</p></td>
<td><p>稍微</p></td>
<td><p>指出報告是用於通話的一部分還是完全通話。</p></td>
</tr>
<tr class="even">
<td><p>ClassifiedPoorCall</p></td>
<td><p>稍微</p></td>
<td><p>指出通話是分類為不佳通話（1），或作為良好通話（0）。</p></td>
</tr>
<tr class="odd">
<td><p>CallerConnectivityICE</p></td>
<td><p>Tinyint</p></td>
<td><p>指示呼叫者是否使用 ICE 通訊協定（網際網路連線建立）連線至網路。</p></td>
</tr>
<tr class="even">
<td><p>CalleeConnectivityICE</p></td>
<td><p>Tinyint</p></td>
<td><p>指示使用者是否使用 ICE 通訊協定（網際網路連線建立）與網路連線。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

