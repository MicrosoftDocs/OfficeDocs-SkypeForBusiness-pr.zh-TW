---
title: Lync Server 2013：通話駐留的容量規劃
description: Lync Server 2013：通話駐留的容量規劃。
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
ms.openlocfilehash: 053a6dabad9d10540e84e9e4f43de09057c295f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544539"
---
# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a>Lync Server 2013 中通話駐留的容量規劃

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-13_

<div id="sectionSection0" class="section">

下表說明您可以用來作為容量規劃需求基礎的通話駐留使用者模型。

<div>


> [!IMPORTANT]  
> 請記住，針對嚴重損壞修復容量規劃，配對集區的每個集區都應該可以處理兩個集區中的通話駐留服務工作負載。



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
<th>計量</th>
<th>每個前端伺服器集區 (8 部前端伺服器) </th>
<th>每個 Standard Edition server</th>
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

