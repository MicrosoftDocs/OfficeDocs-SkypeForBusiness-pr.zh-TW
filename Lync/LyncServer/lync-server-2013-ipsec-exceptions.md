---
title: Lync Server 2013 IPsec 例外狀況
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IPsec exceptions
ms:assetid: 241f1eca-6f2f-44de-90b1-2cb659cbe27c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425719(v=OCS.15)
ms:contentKeyID: 48183627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ee06e4b7f3cabc606a612cd0f332aed47b46823
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514150"
---
# <a name="ipsec-exceptions-in-lync-server-2013"></a>Lync Server 2013 中的 IPsec 例外狀況

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-27_

對於已經部署 Internet Protocol Security (IPsec，請參閱 IETF RFC 4301-4309) 的企業網路而言，用於傳送音訊、視訊與全景視訊的連接埠範圍，必須停用 IPSec。為了避免在媒體連接埠分配期間，因為 IPSec 交涉而導致出現延遲現象，建議您這麼做。

下表說明建議採用的 IPSec 例外設定。

### <a name="recommended-ipsec-exceptions"></a>建議的 IPsec 例外

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>規則名稱</th>
<th>來源 IP</th>
<th>目的地 IP</th>
<th>Protocol (通訊協定)</th>
<th>來源連接埠</th>
<th>目的地連接埠</th>
<th>驗證需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A/V Edge Server (輸入的內部流量)</p></td>
<td><p>任何</p></td>
<td><p>A/V Edge Server (內部流量)</p></td>
<td><p>UDP 和 TCP</p></td>
<td><p>任何</p></td>
<td><p>任何</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="even">
<td><p>A/V Edge Server (輸入的外部流量)</p></td>
<td><p>任何</p></td>
<td><p>A/V Edge Server (外部流量)</p></td>
<td><p>UDP 和 TCP</p></td>
<td><p>任何</p></td>
<td><p>任何</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="odd">
<td><p>A/V Edge Server (輸出的內部流量)</p></td>
<td><p>A/V Edge Server (內部流量)</p></td>
<td><p>任何</p></td>
<td><p>UDP &amp; TCP</p></td>
<td><p>任何</p></td>
<td><p>任何</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="even">
<td><p>A/V Edge Server (輸出的外部流量)</p></td>
<td><p>A/V Edge Server (外部流量)</p></td>
<td><p>任何</p></td>
<td><p>UDP 和 TCP</p></td>
<td><p>任何</p></td>
<td><p>任何</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="odd">
<td><p>中繼伺服器 (輸入流量)</p></td>
<td><p>任何</p></td>
<td><p>調解</p>
<p>伺服器 (s) </p></td>
<td><p>UDP 和 TCP</p></td>
<td><p>任何</p></td>
<td><p>任何</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="even">
<td><p>中繼伺服器 (輸出流量)</p></td>
<td><p>調解</p>
<p>伺服器 (s) </p></td>
<td><p>任何</p></td>
<td><p>UDP 和 TCP</p></td>
<td><p>任何</p></td>
<td><p>任何</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="odd">
<td><p>會議服務員 (輸入流量)</p></td>
<td><p>任何</p></td>
<td><p>執行會議服務員的前端伺服器</p></td>
<td><p>UDP 和 TCP</p></td>
<td><p>任何</p></td>
<td><p>任何</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="even">
<td><p>會議服務員 (輸出流量)</p></td>
<td><p>執行會議服務員的前端伺服器</p></td>
<td><p>任何</p></td>
<td><p>UDP 和 TCP</p></td>
<td><p>任何</p></td>
<td><p>任何</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="odd">
<td><p>A/V 會議 (輸入流量)</p></td>
<td><p>任何</p></td>
<td><p>前端伺服器</p></td>
<td><p>UDP 和 TCP</p></td>
<td><p>任何</p></td>
<td><p>任何</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="even">
<td><p>A/V 會議 (輸出流量)</p></td>
<td><p>前端伺服器</p></td>
<td><p>任何</p></td>
<td><p>UDP 和 TCP</p></td>
<td><p>任何</p></td>
<td><p>任何</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="odd">
<td><p>Exchange (輸入流量)</p></td>
<td><p>任何</p></td>
<td><p>Exchange Unified Messaging</p></td>
<td><p>UDP 和 TCP</p></td>
<td><p>任何</p></td>
<td><p>任何</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="even">
<td><p>應用程式共用伺服器輸入</p></td>
<td><p>任何</p></td>
<td><p>應用程式共用伺服器</p></td>
<td><p>TCP</p></td>
<td><p>任何</p></td>
<td><p>任何</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="odd">
<td><p>應用程式共用伺服器輸出</p></td>
<td><p>應用程式共用伺服器</p></td>
<td><p>任何</p></td>
<td><p>TCP</p></td>
<td><p>任何</p></td>
<td><p>任何</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="even">
<td><p>Exchange (輸出流量)</p></td>
<td><p>Exchange Unified Messaging</p></td>
<td><p>任何</p></td>
<td><p>UDP 和 TCP</p></td>
<td><p>任何</p></td>
<td><p>任何</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="odd">
<td><p>用戶端</p></td>
<td><p>任何</p></td>
<td><p>任何</p></td>
<td><p>Udp</p></td>
<td><p>指定的媒體連接埠範圍</p></td>
<td><p>任何</p></td>
<td><p>不要驗證</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

