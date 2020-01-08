---
title: Lync Server 2013：憑證摘要-公用立即訊息連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31988207403ef1ccb5ea366da6e1ec6b3d448b4e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>證書摘要-Lync Server 2013 中的公用立即訊息連線

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-19_

若要設定公用立即訊息連線的憑證，您應該先注意到其他 SIP 同盟類型或甚至是標準邊緣伺服器憑證沒有什麼不同，只是北美 Online （AOL）需要唯一證書配置。 除了一般的伺服器增強型金鑰用法（EKU）之外，美洲線上還需要證書或憑證（在邊緣池而言），也包含用戶端 EKU。 用戶端 EKU 是憑證的補充，而且是指派給 Edge 伺服器的外部公用憑證的一部分。

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
<td><p>證書必須來自公用 CA，而且如果要部署與 AOL 的公用 IM 連線，則必須擁有伺服器 EKU 和用戶端 EKU。 已將證書指派給外部邊緣伺服器介面，以進行下列作業：</p>
<ul>
<li><p>存取邊緣服務</p></li>
<li><p>網路會議 Edge 服務</p></li>
<li><p>A/V 邊緣服務</p></li>
</ul>
<p>請注意，San 會根據您在拓撲建立器中的定義，自動新增到憑證中。 您可以視需要為其他 SIP 網域以及其他所需支援的專案新增 SAN 專案。 Subject 名稱是在 SAN 中複製，而且必須存在，才能正常運作。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

