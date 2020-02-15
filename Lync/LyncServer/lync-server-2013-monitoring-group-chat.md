---
title: Lync Server 2013： 監控群組聊天
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
ms.openlocfilehash: cb82eedd9d9578aeb4120136c1896267cde35392
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a>Lync Server 2013 中的監視群組聊天

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-08-04_

我們強烈建議的效能改進 Microsoft 下載中心上執行提供最新[累計伺服器更新安裝程式](http://support.microsoft.com/kb/968802)。

假設您正在執行最新累計更新，使用下列計量壓力測試表了解是否您群組聊天伺服器正在執行在最佳的狀況。

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
<td><p>三部群組聊天伺服器的 Group Chat 集區、 每個需要 8 GB 記憶體和 8 處理器。</p></td>
</tr>
<tr class="even">
<td><p>兩個 Lync Server 2013 Enterprise Edition 中結束前方。</p></td>
</tr>
<tr class="odd">
<td><p>跨三個群組聊天伺服器的 60000 位並行使用者。</p></td>
</tr>
<tr class="even">
<td><p>群組聊天集區所主控的 25000 通道。</p></td>
</tr>
<tr class="odd">
<td><p>通道大小：</p>
<ul>
<li><p>小型通道大小： 30</p></li>
<li><p>中型通道大小： 150</p></li>
<li><p>大型通道大小： 2500年</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>通道計數：</p>
<ul>
<li><p>數字小通道： 24000</p></li>
<li><p>數字中型通道 800</p></li>
<li><p>數字大型通道 24</p></li>
<li><p>總通道 24,824</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>邀請通道：</p>
<ul>
<li><p>一半的通道已邀請通道</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>使用者加入的通道數目：</p>
<ul>
<li><p>小型： 12</p></li>
<li><p>中型： 2</p></li>
<li><p>大型： 1</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>加入速率：</p>
<ul>
<li><p>10 總計/秒，每部伺服器的 3.33/秒</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>登出率：</p>
<ul>
<li><p>10 總計/秒，每部伺服器的 3.33/秒</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>聊天速率：</p>
<ul>
<li><p>20 總計/秒，6.66] / 秒每個伺服器</p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> 使用不同的硬體規格或使用者設定檔時，可能會有所不同下列效能計數器數字。



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
<th>臨界值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Process(ChannelService)-&gt;%處理器時間</p></td>
<td><p>最小值： 0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

