---
title: Lync Server 2013：憑證摘要 - 調整式合併 Edge (使用 NAT 透過私人 IP 位址進行 DNS 負載平衡)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: 41677dbd-3d07-498a-8591-df255b606647
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425921(v=OCS.15)
ms:contentKeyID: 48183959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 547e8f98cad0f985feda95758d4bfa826b0f731e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975496"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Lync Server 2013 中的憑證摘要 - 調整式合併 Edge (使用 NAT 透過私人 IP 位址進行 DNS 負載平衡)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

Microsoft Lync Server 2013 使用憑證來相互驗證其他伺服器，並加密從伺服器到伺服器和伺服器的資料到用戶端。 證書需要符合與伺服器相關聯的網域名稱系統（DNS）記錄的名稱，以及憑證上的主旨名稱（SAN）與 subject 替換名稱（SAN）。 若要成功對應伺服器、DNS 記錄和憑證專案，您必須仔細規劃您想要的伺服器在 DNS 中註冊的完整功能變數名稱，以及憑證上的 SN 與 SAN 專案。

從公用憑證授權單位（CA）要求指派給 Edge 伺服器外部介面的憑證。 在下列文章中，已說明為整合通訊提供憑證成功的公用 Ca 如下所示： [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395)要求憑證時，您可以使用 Lync Server 部署嚮導所產生的憑證申請，或由公用 CA 提供的程式手動建立要求。 指派憑證時，會將憑證指派給存取邊緣服務介面、網路會議邊緣服務介面，以及音訊/視頻驗證服務。 音訊/視頻驗證服務不應與 A/V 邊緣服務混淆，因為它不會使用憑證來加密音訊與視頻資料流程。 內部邊緣伺服器介面可以使用來自內部（到您的組織） CA 或來自公用 CA 的憑證的憑證。 內部介面憑證只使用 SN，而且不需要或使用 SAN 專案。

<div>


> [!NOTE]  
> 下表顯示 [subject 替換名稱] 清單中的第二個 SIP 專案（sip.fabrikam.com），供您參考。 針對貴組織中的每個 SIP 網域，您必須在證書受領人備用名稱清單中新增一個對應的 FQDN。



</div>

<div>

## <a name="scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat"></a>使用 NAT 調整合並邊緣、使用私人 IP 位址進行 DNS 負載平衡


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>元件</th>
<th>消費者名稱（SN）</th>
<th>Subject 替代名稱（SAN）/Order</th>
<th>批註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>已縮放的合併邊緣（外部邊緣）</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>證書必須來自公用 CA，且必須擁有伺服器 EKU 及用戶端 EKU，才能部署與 AOL 的公用 IM 連線。 此外，對於縮放的邊緣伺服器，證書私密金鑰必須是可匯出的，以及已複製到每個 Edge 伺服器的憑證和私密金鑰。 已將憑證指派給外部邊緣介面，以進行下列作業：</p>
<ul>
<li><p>存取邊緣</p></li>
<li><p>會議邊緣</p></li>
<li><p>A/V 邊緣</p></li>
</ul>
<p>請注意，San 會根據您在拓撲建立器中的定義，自動新增到憑證中。 您可以視需要為其他 SIP 網域以及其他所需支援的專案新增 SAN 專案。 Subject 名稱是在 SAN 中複製，而且必須存在，才能正常運作。</p></td>
</tr>
<tr class="even">
<td><p>已縮放的合併邊緣（內部邊緣）</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>不需要 SAN</p></td>
<td><p>證書可以由公用或私人 CA 頒發，且必須包含伺服器 EKU。 已將證書指派給內部邊緣介面。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a>證書摘要–公用立即訊息連線


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>元件</th>
<th>消費者名稱</th>
<th>Subject 替代名稱（SAN）/Order</th>
<th>批註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部/存取邊緣</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>證書必須來自公用 CA，且必須擁有伺服器 EKU 及用戶端 EKU，才能部署與 AOL 的公用 IM 連線。 已將憑證指派給外部邊緣介面，以進行下列作業：</p>
<ul>
<li><p>存取邊緣</p></li>
<li><p>會議邊緣</p></li>
<li><p>A/V 邊緣</p></li>
</ul>
<p>請注意，San 會根據您在拓撲建立器中的定義，自動新增到憑證中。 您可以視需要為其他 SIP 網域以及其他所需支援的專案新增 SAN 專案。 Subject 名稱是在 SAN 中複製，而且必須存在，才能正常運作。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>可擴展訊息和目前狀態通訊協定的憑證摘要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>元件</th>
<th>消費者名稱</th>
<th>Subject 替代名稱（SAN）/Order</th>
<th>批註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>指派給 Edge 伺服器或 Edge 池的存取邊緣服務</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>xmpp.contoso.com</p>
<p><strong>*. contoso.com</strong></p></td>
<td><p>前三個 SAN 專案是完整邊緣伺服器的一般 SAN 專案。 Contoso.com 是在根網域層級與 XMPP 夥伴聯盟所需的專案。 此專案可讓 XMPP 的所有網域使用尾碼 *. contoso.com。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

