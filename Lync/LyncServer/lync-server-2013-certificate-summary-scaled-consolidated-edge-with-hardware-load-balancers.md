---
title: 憑證摘要-調整式合併邊緣搭配硬體負載平衡器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 894a9f3e-7cba-4915-8fdf-e52f2f25126f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398692(v=OCS.15)
ms:contentKeyID: 48184729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c522b72683bd07f92aa0442f8373458f43a7f62
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>憑證摘要-調整式合併邊緣搭配硬體負載平衡器在 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-22_

Microsoft Lync Server 2013 使用相互驗證其他伺服器，以及加密資料從伺服器對伺服器的憑證和用戶端的伺服器。 憑證必須進行伺服器關聯網域名稱系統 (DNS) 記錄與憑證上的主體名稱 (SN) 和主體替代名稱 (SAN) 的名稱比對。 若要成功對應伺服器、DNS 記錄和憑證項目，您必須依據 DNS 中的註冊以及憑證上的 SN 和 SAN 項目，仔細規劃所要的伺服器完整名稱。

指派給 Edge Server 外部介面的憑證要求從公用憑證授權單位 (CA)。 有示範中提供的憑證，如下列文章中所列的整合通訊的目的，成功的公用 Ca: [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395)。 當要求憑證，您可以使用 Lync Server 部署精靈] 所產生的憑證要求，或以手動方式或公用 CA 所提供的程序來建立要求。 指派憑證時，會將憑證指派到 Access Edge 服務介面、 Web Conferencing Edge service 介面和音訊/視訊驗證服務。 音訊/視訊驗證服務不應混淆與 A / V Edge service，不會使用憑證來加密音訊和視訊資料流。 （您組織內部） ca 的憑證或公用 ca 的憑證，可以使用內部 Edge Server 介面。 內部介面憑證僅可使用 SN，且不需要也不會使用 SAN 項目。

<div>


> [!NOTE]
> 下表在主體替代名稱清單中顯示第二個 SIP 項目 (sip.fabrikam.com) 供您參考。針對組織中的每個 SIP 網域，您需要憑證主體替代名稱清單中列出的對應 FQDN。



</div>

<div>

## <a name="certificates-required-for-scaled-consolidated-edge-with-hardware-load-balancers"></a>使用硬體負載平衡器調整式合併 Edge 所需的憑證


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
<th>主體名稱</th>
<th>主體替代名稱 (SAN)/順序</th>
<th>註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>單一合併式 Edge Server (外部 Edge)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>若要部署與 AOL 的公用 IM 連線，憑證必須來自公用 CA，且必須具有伺服器 EKU 和用戶端 EKU。 此外，調整式 Edge server，憑證的私密金鑰必須可匯出並複製到每個 Edge server 憑證的私密金鑰與憑證指派給的外部 Edge 介面：</p>
<ul>
<li><p>Access Edge Service</p></li>
<li><p>Web Conferencing Edge service</p></li>
<li><p>A/V Edge service</p></li>
</ul>
<p>請注意，系統會根據您在拓撲產生器中的定義，將 SAN 自動新增至憑證。您可以視需要為其他 SIP 網域新增 SAN 項目，或新增其他必須支援的項目。SAN 中的主體名稱會複寫，且必須存在才能正常運作。</p></td>
</tr>
<tr class="even">
<td><p>單一合併式 Edge Server (內部 Edge)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>不需要 SAN</p></td>
<td><p>憑證可由公用或私人 CA 來核發，且必須包含伺服器 EKU。 將憑證指派至 Edge Server 的內部介面。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a>憑證摘要 - 公用立即訊息連線


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
<th>主體名稱</th>
<th>主體替代名稱 (SAN)/順序</th>
<th>註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 /access Edge service</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>若要部署與 AOL 的公用 IM 連線，憑證必須來自公用 CA，且必須具有伺服器 EKU 和用戶端 EKU。系統會針對下列項目將憑證指派給外部 Edge 介面：</p>
<ul>
<li><p>Access Edge Service</p></li>
<li><p>Web Conferencing Edge service</p></li>
<li><p>A/V Edge service</p></li>
</ul>
<p>請注意，系統會根據您在拓撲產生器中的定義，將 SAN 自動新增至憑證。您可以視需要為其他 SIP 網域新增 SAN 項目，或新增其他必須支援的項目。SAN 中的主體名稱會複寫，且必須存在才能正常運作。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>可延伸訊息和顯示狀態通訊協定的憑證摘要


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
<th>主體名稱</th>
<th>主體替代名稱 (SAN)/順序</th>
<th>註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>指派給 Access Edge service 之 Edge Server 或 Edge 集區</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>xmpp.contoso.com</p>
<p><strong>*。 contoso.com</strong></p></td>
<td><p>前三個 SAN 項目是完整的 Edge server 的一般 SAN 項目。 contoso.com 是在根網域層級與 XMPP 協力廠商同盟的必要項目。 此項目可允許所有包含尾碼 *.contoso.com 之網域使用 XMPP。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

