---
title: Lync Server 2013：回應群組的容量規劃
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72f3e49806dc573a4e17bc917834deba97a74ca2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a>Lync Server 2013 中的回應群組的容量規劃

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

<div id="sectionSection0" class="section">

下表說明您可以用來做為容量規劃需求基礎的 [回應群組] 使用者模型。

<div>


> [!NOTE]  
> 下表中的數位假設您針對所有回應群組音訊檔案使用 16 kHz、單聲道、16位波（.wav）檔案。 如果您使用其他檔案格式（例如，Windows Media Audio （.wma）），這些數位可能會有所不同。



</div>

<div>


> [!IMPORTANT]  
> 請記住，對於災難復原容量規劃，配對池的每個池都應該能夠處理兩個池中所有回應群組的工作量。



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
<th>衡量</th>
<th>每個企業版池（含8個前端伺服器）</th>
<th>每個標準版 server</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>每秒來電數</p></td>
<td><p>位</p></td>
<td><p>pplx-2</p></td>
</tr>
<tr class="even">
<td><p>連線到 IVR 或 MoH 的並行呼叫</p></td>
<td><p>480</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>並行匿名會話（無 IM）</p></td>
<td><p>224</p></td>
<td><p>28</p></td>
</tr>
<tr class="even">
<td><p>並行匿名會話（與 IM）</p></td>
<td><p>64</p></td>
<td><p>型</p></td>
</tr>
<tr class="odd">
<td><p>使用中的代理程式（正式與非正式）</p></td>
<td><p>1200</p></td>
<td><p>1200</p></td>
</tr>
<tr class="even">
<td><p>查尋群組的數目</p></td>
<td><p>400</p></td>
<td><p>400</p></td>
</tr>
<tr class="odd">
<td><p>IVR 群組數（使用語音辨識）</p></td>
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

