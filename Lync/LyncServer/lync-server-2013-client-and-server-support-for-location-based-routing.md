---
title: Lync Server 2013：位置基礎路由的用戶端和伺服器支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3791b359422c4b5bef463a612db6f0b74c07f096
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 中的位置基礎路由的用戶端和伺服器支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-06-18_

Lync Server 會強制執行以位置為基礎的路由。 Lync Server 可以識別使用者從公司網路中連線的網路網站。 由於遠端使用者位於公司網路之外，因此其位置被認為是未知的。

<div>

## <a name="lync-server-support"></a>Lync Server 支援

位置式路由要求 Lync Server 2013 CU1 是在指定拓撲中的所有前端池和標準版伺服器上部署。 如果未在拓撲中的特定 Lync 元件上安裝 Lync Server 2013 CU1，則無法完全強制執行以位置為基礎的路由限制。

下表列出針對位置路由支援的伺服器角色與版本組合。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>泳池版本</th>
<th>中繼伺服器版本</th>
<th>受</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 2013 年2月累計更新</p></td>
<td><p>Lync Server 2013 2013 年2月累計更新</p></td>
<td><p>是的</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 2013 年2月累計更新</p></td>
<td><p>Lync Server 2013</p></td>
<td><p>不</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 2013 年2月累計更新</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>不</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 2013 年2月累計更新</p></td>
<td><p>Office 通訊伺服器 2007 R2</p></td>
<td><p>不</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013</p></td>
<td><p>每</p></td>
<td><p>不</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010</p></td>
<td><p>每</p></td>
<td><p>不</p></td>
</tr>
<tr class="odd">
<td><p>Office 通訊伺服器 2007 R2</p></td>
<td><p>每</p></td>
<td><p>不</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a>Lync 用戶端支援

下表會識別以位置為基礎的路由支援的用戶端。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>用戶端類型</th>
<th>受</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>是的</p></td>
<td><p>包括 Lync 2013 2013 年2月累計更新</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>是的</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>不</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>是的</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync 助理</p></td>
<td><p>是的</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Windows 8 版 Lync</p></td>
<td><p>不</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Mobile 2013</p></td>
<td><p>不</p></td>
<td><p>如果使用者使用的是啟用位置路由的使用者，則必須針對 Lync Mobile 2013 用戶端停用 VoIP。</p></td>
</tr>
<tr class="even">
<td><p>Lync Mobile 2010</p></td>
<td><p>是的</p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> 若要針對 Lync Mobile 2013 用戶端停用 VoIP，請針對所有啟用位置路由的使用者，指派您已停用的設定、IP 音訊/影片的行動原則。 如需行動原則的詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">新 CsMobilityPolicy</A>。



</div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中規劃位置基礎路由](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

