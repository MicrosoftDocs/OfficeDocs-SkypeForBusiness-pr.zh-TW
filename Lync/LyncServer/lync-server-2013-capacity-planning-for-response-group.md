---
title: Lync Server 2013： 容量規劃回應群組
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
ms.openlocfilehash: 4e5724978347b50db2790e4d5798aace8489acbb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a>容量規劃的 Lync Server 2013 中的回應群組

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-29_

<div id="sectionSection0" class="section">

下表說明您可以使用容量規劃需求為基礎的回應群組使用者模型。

<div>


> [!NOTE]  
> 下表中的數字假設，您使用 16 kHz 單音的 16 位元 Wave (.wav) 檔案的所有回應群組音訊檔案。 如果您使用其他檔案格式，例如 Windows Media Audio (.wma) 數字可能會有所不同。



</div>

<div>


> [!IMPORTANT]  
> 請記住，災害復原容量規劃，配對集區的每個集區應該能夠處理兩個集區中的所有回應群組的工作負載。



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
<th>評量</th>
<th>每個 Enterprise Edition 集區 （使用 8 前端伺服器）</th>
<th>每個 Standard Edition 伺服器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>每秒來電</p></td>
<td><p>16 </p></td>
<td><p>2 </p></td>
</tr>
<tr class="even">
<td><p>連線至 IVR 或 MoH 的並行通話</p></td>
<td><p>480</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>並行匿名工作階段數 （不含 IM)</p></td>
<td><p>224</p></td>
<td><p>28</p></td>
</tr>
<tr class="even">
<td><p>並行匿名工作階段數 （包含 IM)</p></td>
<td><p>64</p></td>
<td><p>8 </p></td>
</tr>
<tr class="odd">
<td><p>作用中的代理程式 （正式和非正式）</p></td>
<td><p>1200</p></td>
<td><p>1200</p></td>
</tr>
<tr class="even">
<td><p>群組搜尋數目</p></td>
<td><p>400</p></td>
<td><p>400</p></td>
</tr>
<tr class="odd">
<td><p>（使用語音辨識） IVR 群組數</p></td>
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

