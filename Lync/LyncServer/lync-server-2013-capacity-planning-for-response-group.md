---
title: Lync Server 2013：回應群組的容量規劃
description: Lync Server 2013：回應群組的容量規劃。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78c543f558f67deaaeb781b308aa5f68d39cd785
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544429"
---
# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a>在 Lync Server 2013 中規劃回應群組的容量

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

<div id="sectionSection0" class="section">

下表說明您可以用來作為容量規劃需求之基礎的回應群組使用者模型。

<div>


> [!NOTE]  
> 下表中的數位是假設您使用 16 kHz、mono、16位 ( 波形) 所有回應群組音訊檔案的檔案。 如果您使用其他檔案格式，例如 Windows Media Audio ( .wma) ，這些數位可能會有所不同。



</div>

<div>


> [!IMPORTANT]  
> 請記住，針對嚴重損壞修復容量規劃，配對集區的每個集區都應該可以處理兩個集區中所有回應群組的工作量。



</div>

### <a name="response-group-user-model"></a>回應群組使用者模型

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>計量</th>
<th>每個 Enterprise Edition 集區 (，含8部前端伺服器) </th>
<th>每個 Standard Edition server</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>每秒來電數</p></td>
<td><p>16 </p></td>
<td><p>第</p></td>
</tr>
<tr class="even">
<td><p>連線至 IVR 或 MoH 的並行通話</p></td>
<td><p>480</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p> (沒有 IM) 的併發匿名會話</p></td>
<td><p>224</p></td>
<td><p>日</p></td>
</tr>
<tr class="even">
<td><p>使用 IM)  (同時匿名會話</p></td>
<td><p>64</p></td>
<td><p>8 </p></td>
</tr>
<tr class="odd">
<td><p>主動代理 (正式和非正式) </p></td>
<td><p>1200</p></td>
<td><p>1200</p></td>
</tr>
<tr class="even">
<td><p>群組搜尋數目</p></td>
<td><p>400</p></td>
<td><p>400</p></td>
</tr>
<tr class="odd">
<td><p>IVR 群組 (使用語音辨識的數目) </p></td>
<td><p>200</p></td>
<td><p>200</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

