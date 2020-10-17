---
title: Lync Server 2013：憑證摘要-公用立即訊息連線
description: Lync Server 2013：憑證摘要-公用立即訊息連線能力。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abf5a01bdeb03da158e221c623417a1b42cc82f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572329"
---
# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>Lync Server 2013 中的憑證摘要-公用立即訊息連線

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-19_

若要設定公用立即訊息連線的憑證，您應該先注意到其他 SIP 同盟類型或甚至是標準 Edge Server 憑證沒有任何不同之處，但北美線上 (AOL) 需要唯一的憑證設定。 除了一般的 server 增強金鑰使用方式外 (EKU) ，北美線上) Edge 集區的情況也需要憑證或憑證 (也包含用戶端 EKU。 用戶端 EKU 是憑證的新增，也是指派給 Edge Server 的外部公用憑證的一部分。

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
<td><p>憑證必須來自公用 CA，而且若要部署與 AOL 的公用 IM 連線，則必須具有伺服器 EKU 和用戶端 EKU。 此憑證會指派給下列專案的外部 Edge Server 介面：</p>
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

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

