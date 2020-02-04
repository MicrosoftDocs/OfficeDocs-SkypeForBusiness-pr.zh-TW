---
title: Lync Server 2013：監視群組聊天
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa350924503f430ec0494cc5e1eb17f7878084a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a>在 Lync Server 2013 中監視群組聊天

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-08-04_

我們強烈建議您執行 Microsoft 下載中心提供的最新[累計伺服器更新安裝程式](http://support.microsoft.com/kb/968802)，以改善效能。

假設您執行的是最新累計更新，請使用下列壓力測試資料表，以瞭解您的群組聊天伺服器是否正在最佳健康情況下執行。

### <a name="test-environment-and-user-model"></a>測試環境與使用者模型

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>群組聊天區中的三個群組聊天伺服器，每個都有 8 GB 的記憶體和8個處理器。</p></td>
</tr>
<tr class="even">
<td><p>在企業版中，有兩個 Lync Server 2013 前端。</p></td>
</tr>
<tr class="odd">
<td><p>60000在三個群組聊天伺服器上併發使用者。</p></td>
</tr>
<tr class="even">
<td><p>由群組聊天池託管的25000頻道。</p></td>
</tr>
<tr class="odd">
<td><p>頻道大小：</p>
<ul>
<li><p>小型頻道大小：30</p></li>
<li><p>中等通道大小：150</p></li>
<li><p>大型通道大小：2500</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>頻道計數：</p>
<ul>
<li><p>數位小型頻道：24000</p></li>
<li><p>數位中型頻道800</p></li>
<li><p>將大型頻道編號24</p></li>
<li><p>通道總24824</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>邀請頻道：</p>
<ul>
<li><p>頻道的一半是邀請頻道</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>使用者加入的頻道數目：</p>
<ul>
<li><p>小：12</p></li>
<li><p>中：2</p></li>
<li><p>大型：1</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>聯接速率：</p>
<ul>
<li><p>每個伺服器共有10個總/秒、3.33/秒</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>登出頻率：</p>
<ul>
<li><p>每個伺服器共有10個總/秒、3.33/秒</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>聊天速度：</p>
<ul>
<li><p>每個伺服器總共20個總計/秒、6.66/秒</p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> 使用不同的硬體規格或使用者設定檔時，可能會有下列效能計數器數值。



</div>

### <a name="performance-counter-to-be-monitored"></a>要監視的效能計數器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>效能計數器</th>
<th>閾值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Process （ChannelService）-&gt;處理器時間百分比</p></td>
<td><p>Min：0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

