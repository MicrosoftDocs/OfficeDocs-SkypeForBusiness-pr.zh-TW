---
title: Lync Server 2013：監控群組聊天
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
ms.openlocfilehash: cf44bbaa00412de24af21c493fd05b88bd6259af
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531930"
---
# <a name="monitoring-group-chat-in-lync-server-2013"></a>在 Lync Server 2013 中監控群組聊天

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-08-04_

強烈建議您在 Microsoft 下載中心上執行最新的 [累積伺服器更新安裝程式](https://support.microsoft.com/kb/968802) ，以改善效能。

假設您正在執行最新的累計更新，請使用下列壓力測試表格，以瞭解您的群組聊天伺服器是否在最佳狀況下執行。

### <a name="test-environment-and-user-model"></a>測試環境和使用者模型

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
<td><p>群組聊天集區中的三個群組聊天伺服器，每個都有 8 GB 的記憶體和8個處理器。</p></td>
</tr>
<tr class="even">
<td><p>Enterprise Edition 中的兩部 Lync Server 2013 前端。</p></td>
</tr>
<tr class="odd">
<td><p>60000三個群組聊天伺服器的並行使用者。</p></td>
</tr>
<tr class="even">
<td><p>由群組聊天集區主控的25000通道。</p></td>
</tr>
<tr class="odd">
<td><p>通道大小：</p>
<ul>
<li><p>小通道大小：30</p></li>
<li><p>中型通道大小：150</p></li>
<li><p>大通道大小：2500</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>通道計數：</p>
<ul>
<li><p>數位小型通道：24000</p></li>
<li><p>數位中型通道800</p></li>
<li><p>數位大通道24</p></li>
<li><p>通道總數24824</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>邀請通道：</p>
<ul>
<li><p>一半通道邀請通道</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>使用者加入的通道數目：</p>
<ul>
<li><p>Small：12</p></li>
<li><p>中：2</p></li>
<li><p>大：1</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>聯接率：</p>
<ul>
<li><p>每個伺服器每秒10個總計/秒、3.33/秒</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>登出率：</p>
<ul>
<li><p>每個伺服器每秒10個總計/秒、3.33/秒</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>交談速度：</p>
<ul>
<li><p>每個伺服器總共20個、每秒 6.66/秒</p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> 使用不同的硬體規格或使用者設定檔時，可能會發生下列效能計數器數目。



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
<th>閾 值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>處理 (ChannelService) &gt; 處理器時間</p></td>
<td><p>最小值：0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

