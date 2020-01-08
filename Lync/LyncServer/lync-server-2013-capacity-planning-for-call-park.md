---
title: Lync Server 2013：通話駐留的容量規劃
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fe55e09c67e62676202def9e3def3454d7cbd33
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a>Lync Server 2013 中通話駐留的容量規劃

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-13_

<div id="sectionSection0" class="section">

下表說明您可以用來做為容量規劃需求基礎的通話駐留使用者模型。

<div>


> [!IMPORTANT]  
> 請記住，對於災難復原容量規劃，配對池的每個池都應該能夠處理兩個池中的通話駐留服務的工作負荷。



</div>

### <a name="call-park-user-model"></a>通話駐留使用者模型

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>衡量</th>
<th>每個前臺端池（含8個前端伺服器）</th>
<th>每個標準版 server</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>公園工資率</p></td>
<td><p>每分鐘8筆</p></td>
<td><p>每分鐘1</p></td>
</tr>
<tr class="even">
<td><p>檢索暫停的通話頻率</p></td>
<td><p>每分鐘8筆</p></td>
<td><p>每分鐘1</p></td>
</tr>
<tr class="odd">
<td><p>平均公園持續時間</p></td>
<td><p>60秒</p></td>
<td><p>60秒</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

