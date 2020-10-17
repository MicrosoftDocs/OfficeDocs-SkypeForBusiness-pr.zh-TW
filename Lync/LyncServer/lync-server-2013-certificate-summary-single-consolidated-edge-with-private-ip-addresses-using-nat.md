---
title: Lync Server 2013：憑證摘要-單一合併 edge （使用 NAT 透過私人 IP 位址）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 6de6680e-5f47-48e6-8e06-4994d710ea6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398519(v=OCS.15)
ms:contentKeyID: 48184433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e41a2734feed26a929ed35fef3ec2c1dd320d9ac
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507900"
---
# <a name="certificate-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Lync Server 2013 中的憑證摘要-單一合併 edge （使用 NAT 透過私人 IP 位址）

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

Microsoft Lync Server 2013 使用憑證對其他伺服器進行相互驗證，以及將從伺服器到伺服器及伺服器的資料加密至用戶端。 憑證必須進行伺服器關聯網域名稱系統 (DNS) 記錄與憑證上的主體名稱 (SN) 和主體替代名稱 (SAN) 的名稱比對。 若要成功對應伺服器、DNS 記錄和憑證項目，您必須依據 DNS 中的註冊以及憑證上的 SN 和 SAN 項目，仔細規劃所要的伺服器完整名稱。

指派給 Edge Server 外部介面的憑證是從公用憑證授權單位單位 (CA) 所要求。 下列文章所列的公用 Ca 在提供憑證以實現整合通訊的目的時已成功示範： [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395) 。 要求憑證時，您可以使用 Lync Server 部署嚮導所產生的憑證要求，或是使用 Lync Server 管理命令介面 Cmdlet 或公用 CA 所提供的程式手動建立要求。 如需有關憑證管理的 Lync Server 管理命令介面 Cmdlet 的詳細資訊，請參閱 [憑證和驗證 Cmdlet In Lync server 2013](https://docs.microsoft.com/powershell/module/skype/) 在指派憑證時，會將憑證指派給 Access Edge service 介面、Web 會議 Edge service 介面及 Audio/Video 驗證服務。 Audio/Video 驗證服務不應該與 A/V Edge service 混淆，它不會使用憑證來加密音訊和影片資料流程。 內部 Edge Server 介面可使用來自內部 (的憑證) CA 或公用 CA 的憑證。 內部介面憑證僅可使用 SN，且不需要也不會使用 SAN 項目。

<div>


> [!NOTE]  
> 下表在主體替代名稱清單中顯示第二個 SIP 項目 (sip.fabrikam.com) 供您參考。針對組織中的每個 SIP 網域，您需要新增憑證主體替代名稱清單中列出的對應 FQDN。



</div>

<div>

## <a name="certificates-required-for-single-consolidated-edge-with-private-ip-addresses-using-nat"></a>具有使用 NAT 的私人 IP 位址之單一合併式 Edge 所需的憑證


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
<th>主體名稱 (SN)</th>
<th>主體替代名稱 (SAN)/順序</th>
<th>註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>單一合併式 Edge (外部 Edge)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>若要部署與 AOL 的公用 IM 連線，憑證必須來自公用 CA，且必須具有伺服器 EKU 和用戶端 EKU。系統會針對下列項目將憑證指派給外部 Edge 介面：</p>
<ul>
<li><p>Access Edge</p></li>
<li><p>Conferencing Edge</p></li>
<li><p>A/V Edge</p></li>
</ul>
<p>請注意，系統會根據您在拓撲產生器中的定義，將 SAN 自動新增至憑證。您可以視需要為其他 SIP 網域新增 SAN 項目，或新增其他必須支援的項目。SAN 中的主體名稱會複寫，且必須存在才能正常運作。</p></td>
</tr>
<tr class="even">
<td><p>單一合併式 Edge (內部 Edge)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>不需要 SAN</p></td>
<td><p>憑證可由公用或私人 CA 來核發，且必須包含伺服器 EKU。系統會將憑證指派給內部 Edge 介面。</p></td>
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
<td><p>外部/Access Edge</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>若要部署與 AOL 的公用 IM 連線，憑證必須來自公用 CA，且必須具有伺服器 EKU 和用戶端 EKU。系統會針對下列項目將憑證指派給外部 Edge 介面：</p>
<ul>
<li><p>Access Edge</p></li>
<li><p>Conferencing Edge</p></li>
<li><p>A/V Edge</p></li>
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
<td><p>指派給 Edge Server 或 Edge 集區的 Access Edge service</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>xmpp.contoso.com</p>
<p><strong>contoso.com</strong></p></td>
<td><p>前三個 SAN 專案是完整 Edge Server 的一般 SAN 專案。 contoso.com 是在根網域層級與 XMPP 協力廠商同盟的必要項目。 此項目可允許所有包含尾碼 *.contoso.com 之網域使用 XMPP。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

