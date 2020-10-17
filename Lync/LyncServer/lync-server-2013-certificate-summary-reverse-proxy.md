---
title: Lync Server 2013：憑證摘要-反向 proxy
description: Lync Server 2013：憑證摘要-反向 proxy。
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
ms.openlocfilehash: 0cc250d6de2eb1a0b6c3ad3495c8df62942f9a81
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572299"
---
# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 的憑證摘要-反向 proxy

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-14_

反向 proxy 的憑證需求比 Edge Server 的憑證需求更簡單。 提供的流程圖提供必要的需求。 伴隨的表格提供一般的憑證主體名稱與主體別名，與我們在 Edge Server 討論中已複習的案例有關。 如需 Edge Server 案例的詳細資訊，請參閱 [Lync server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)。

**反向 Proxy 的憑證流程圖表**

![Edge Server 的憑證流程圖表](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Edge Server 的憑證流程圖表")

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
<th>主體名稱</th>
<th> (SAN) /Order 的主體替代名稱</th>
<th>註解</th>
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
<p> (選用) :*。 contoso.com</p></td>
<td><p>憑證必須由公用 CA 和伺服器 EKU 所發行。 服務包括通訊錄服務、通訊群組擴充的 Office Web Apps for 會議，以及 Lync IP 裝置發行規則。 主體替代名稱包括：</p>
<ul>
<li><p>前端伺服器或前端集區的外部 Web 服務 FQDN</p></li>
<li><p>Director 或 Director 集區的外部 Web 服務 FQDN</p></li>
<li><p>電話撥入式會議</p></li>
<li><p>線上會議發佈規則</p></li>
<li><p>適用于會議的 Office Web Apps</p></li>
<li><p>Lyncdiscover (自動探索) </p></li>
</ul>
<p>選用的萬用字元會取代「符合和撥入 SAN</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

