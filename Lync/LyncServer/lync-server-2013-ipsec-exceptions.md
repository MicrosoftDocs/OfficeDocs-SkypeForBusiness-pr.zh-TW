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
ms.openlocfilehash: 37d5becaab996d6fe4889086d3a68a45ffc1f6d7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ipsec-exceptions-in-lync-server-2013"></a>Lync Server 2013 中的 IPsec 例外狀況

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-27_

針對網際網路通訊協定安全性（IPsec）（請參閱已部署的 IETF RFC 4301-4309）商業網路，必須停用用於傳送音訊、影片和全景影片的埠範圍。 建議因需要避免由於 IPsec 協商而分配媒體埠的任何延遲。

下表說明建議的 IPsec 例外狀況設定。

### <a name="recommended-ipsec-exceptions"></a>建議的 IPsec 例外狀況

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
<th>通訊協定</th>
<th>來源埠</th>
<th>目的地埠</th>
<th>驗證需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A/V 邊緣伺服器內部入站</p></td>
<td><p>每</p></td>
<td><p>A/V 邊緣伺服器內部</p></td>
<td><p>UDP 與 TCP</p></td>
<td><p>每</p></td>
<td><p>每</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="even">
<td><p>A/V 邊緣伺服器外部輸入</p></td>
<td><p>每</p></td>
<td><p>A/V 邊緣伺服器外部</p></td>
<td><p>UDP 與 TCP</p></td>
<td><p>每</p></td>
<td><p>每</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="odd">
<td><p>A/V 邊緣伺服器內部出站</p></td>
<td><p>A/V 邊緣伺服器內部</p></td>
<td><p>每</p></td>
<td><p>UDP &amp; TCP</p></td>
<td><p>每</p></td>
<td><p>每</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="even">
<td><p>A/V 邊緣伺服器外部輸出</p></td>
<td><p>A/V 邊緣伺服器外部</p></td>
<td><p>每</p></td>
<td><p>UDP 與 TCP</p></td>
<td><p>每</p></td>
<td><p>每</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="odd">
<td><p>中繼伺服器入站</p></td>
<td><p>每</p></td>
<td><p>仲介</p>
<p>伺服器（s）</p></td>
<td><p>UDP 與 TCP</p></td>
<td><p>每</p></td>
<td><p>每</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="even">
<td><p>轉送伺服器出站</p></td>
<td><p>仲介</p>
<p>伺服器（s）</p></td>
<td><p>每</p></td>
<td><p>UDP 與 TCP</p></td>
<td><p>每</p></td>
<td><p>每</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="odd">
<td><p>會議助理入站</p></td>
<td><p>每</p></td>
<td><p>運行會議助理的前端伺服器</p></td>
<td><p>UDP 與 TCP</p></td>
<td><p>每</p></td>
<td><p>每</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="even">
<td><p>會議助理出站</p></td>
<td><p>運行會議助理的前端伺服器</p></td>
<td><p>每</p></td>
<td><p>UDP 與 TCP</p></td>
<td><p>每</p></td>
<td><p>每</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="odd">
<td><p>A/V 會議入站</p></td>
<td><p>每</p></td>
<td><p>前端伺服器</p></td>
<td><p>UDP 與 TCP</p></td>
<td><p>每</p></td>
<td><p>每</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="even">
<td><p>A/V 會議輸出</p></td>
<td><p>前端伺服器</p></td>
<td><p>每</p></td>
<td><p>UDP 與 TCP</p></td>
<td><p>每</p></td>
<td><p>每</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="odd">
<td><p>Exchange 入站</p></td>
<td><p>每</p></td>
<td><p>Exchange 整合通訊</p></td>
<td><p>UDP 與 TCP</p></td>
<td><p>每</p></td>
<td><p>每</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="even">
<td><p>應用程式共用伺服器入站</p></td>
<td><p>每</p></td>
<td><p>應用程式共用伺服器</p></td>
<td><p>TCP-OUT</p></td>
<td><p>每</p></td>
<td><p>每</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="odd">
<td><p>應用程式共用伺服器出站</p></td>
<td><p>應用程式共用伺服器</p></td>
<td><p>每</p></td>
<td><p>TCP-OUT</p></td>
<td><p>每</p></td>
<td><p>每</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="even">
<td><p>Exchange 輸出</p></td>
<td><p>Exchange 整合通訊</p></td>
<td><p>每</p></td>
<td><p>UDP 與 TCP</p></td>
<td><p>每</p></td>
<td><p>每</p></td>
<td><p>不要驗證</p></td>
</tr>
<tr class="odd">
<td><p>台</p></td>
<td><p>每</p></td>
<td><p>每</p></td>
<td><p>UDP-IN</p></td>
<td><p>指定的媒體埠範圍</p></td>
<td><p>每</p></td>
<td><p>不要驗證</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

