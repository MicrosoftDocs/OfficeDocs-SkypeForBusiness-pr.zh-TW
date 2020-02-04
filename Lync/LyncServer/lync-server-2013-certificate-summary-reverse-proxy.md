---
title: Lync Server 2013：憑證摘要 - 反向 Proxy
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42e52fa8522de53404fee3f3b5798f159361dbf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 中的憑證摘要 - 反向 Proxy

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-14_

反向 proxy 的憑證需求比邊緣伺服器更簡單。 提供的流程圖提供必要的需求。 隨附的表格針對我們在 Edge 伺服器討論中審查的案例，提供典型的憑證受領人名稱和消費者替換名稱。 如需有關 Edge 伺服器案例的詳細資訊，請參閱[Lync server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)。

**反向 Proxy 的憑證流程圖**

![Edge Server 的憑證流程圖](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Edge Server 的憑證流程圖")

### <a name="reverse-proxy-external-interface"></a>反向 Proxy：外部介面

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
<th>Subject 備用名稱（SAN）/Order</th>
<th>批註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>反向 Proxy</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>webext.contoso.com</p>
<p>webdirext.contoso.com</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>officewebapps01.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>（選擇性）:*. contoso.com</p></td>
<td><p>證書必須由公用 CA 以及伺服器 EKU 所頒發。 服務包括通訊錄服務、通訊群組擴充會議的 Office Web Apps，以及 Lync IP 裝置發佈規則。 消費者備用名稱包括：</p>
<ul>
<li><p>前端伺服器或頂層端池的外部 Web 服務 FQDN</p></li>
<li><p>主管或主管池的外部 Web 服務 FQDN</p></li>
<li><p>電話撥入式會議</p></li>
<li><p>線上會議發佈規則</p></li>
<li><p>適用于會議的 Office Web Apps</p></li>
<li><p>Lyncdiscover （自動探索）</p></li>
</ul>
<p>選用的萬用字元會取代 [開會] 和 [撥入] SAN</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

