---
title: Lync Server 2013：來自舊版部署的支援用戶端
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported clients from previous deployments
ms:assetid: 69d427f8-57a5-4244-b2ed-f2eb7600285e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398499(v=OCS.15)
ms:contentKeyID: 48184390
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f404dad679eeffa91465f3f8547fbe86ce74b0c1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524130"
---
# <a name="supported-clients-from-previous-deployments-in-lync-server-2013"></a>Lync Server 2013 的先前部署支援的用戶端

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-12-14_

在共存案例中，Lync Server 2013 用戶端可以與舊版的 Lync Server 和 Office 通訊伺服器互動處理用戶端。 與舊版不同的是，Lync Server 2010 支援新的 Lync 2013 用戶端。 這可讓從 Lync Server 2010 升級的組織，將新的用戶端與 Lync Server 升級獨立。

<div>

## <a name="supported-server-and-client-combinations"></a>支援的伺服器和用戶端組合

下表顯示支援的用戶端版本和伺服器版本組合。 Lync Server 2013 支援兩個先前的用戶端版本，而 Lync Server 2010 支援新的 Lync 2013 用戶端。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>用戶端</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>支援</p></td>
<td><p>支援</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2013</p></td>
<td><p>支援</p></td>
<td><p>不支援</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>支援</p></td>
<td><p>支援</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendant</p></td>
<td><p>支援</p></td>
<td><p>支援</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 群組聊天</p></td>
<td><p>不適用</p></td>
<td><p>Supported1</p></td>
<td><p>不適用</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2010</p></td>
<td><p>不支援</p></td>
<td><p>支援</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendee</p></td>
<td><p>非 Supported2</p></td>
<td><p>支援</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable3</p></td>
<td><p>支援</p></td>
<td><p>支援</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Office Communications Server 2007 R2 Attendant</p></td>
<td><p>不支援</p></td>
<td><p>支援</p></td>
<td><p>支援</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007</p></td>
<td><p>不支援</p></td>
<td><p>支援</p></td>
<td><p>支援</p></td>
</tr>
<tr class="odd">
<td><p>Office Live Meeting 2007</p></td>
<td><p>不支援</p></td>
<td><p>支援</p></td>
<td><p>支援</p></td>
</tr>
</tbody>
</table>


1In Microsoft Lync Server 2010，群組聊天伺服器會提供群組聊天功能，這是 Lync Server 2010 的協力廠商信任應用程式。 Lync 2013 用戶端與 Lync Server 2010 （群組聊天）不相容。

2Lync Web App 2013 現在提供完整的會議體驗，包括電腦音訊和影片，且被視為 Lync 2010 出席者的取代。

Office Communicator 2007 R2 中的3The 目前狀態和 IM 功能與 Lync Server 2013 相容，但會議功能卻不相容。 從 Office 通訊伺服器 2007 R2 進行遷移時，Office Communicator 2007 R2 適用于目前狀態和 IM 互通性，但是使用者應使用 Lync Web App 2013 加入 Lync Server 的 [2013] 會議。

<div>


> [!NOTE]  
> 如需 Lync Server 2013 用戶端與舊版 Lync Server 和 Office 通訊伺服器之用戶端共存及互動的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-client-interoperability-in-lync-2013.md">用戶端互通性（lync 2013</A> ）。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

