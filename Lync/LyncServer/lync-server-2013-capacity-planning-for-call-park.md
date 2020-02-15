---
title: Lync Server 2013： 容量規劃通話駐留
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1192ef9b5b30c722a4f62973cf4992da3ca7300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a>容量規劃的 Lync Server 2013 中的通話駐留

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-13_

<div id="sectionSection0" class="section">

下表說明您可以使用容量規劃需求為基礎的通話駐留使用者模型。

<div>


> [!IMPORTANT]  
> 請記住，災害復原容量規劃，配對集區的每個集區應該能夠處理兩個集區中的通話駐留服務的工作負載。



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
<th>評量</th>
<th>每個前端集區 （使用 8 前端伺服器）</th>
<th>每個 Standard Edition 伺服器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>駐留率</p></td>
<td><p>每分鐘 8 個</p></td>
<td><p>每分鐘 1 個</p></td>
</tr>
<tr class="even">
<td><p>擷取駐留通話率</p></td>
<td><p>每分鐘 8 個</p></td>
<td><p>每分鐘 1 個</p></td>
</tr>
<tr class="odd">
<td><p>平均駐留持續時間</p></td>
<td><p>60 秒</p></td>
<td><p>60 秒</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

