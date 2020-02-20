---
title: 從舊版部署 Lync Server 2013： 支援的用戶端
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
ms.openlocfilehash: 7cef56a80ed02afd5942c117e08bb058e178aebe
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-clients-from-previous-deployments-in-lync-server-2013"></a>從 Lync Server 2013 中的舊部署支援的用戶端

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-12-14_

在共存案例中，Lync Server 2013 用戶端可以從舊版 Lync Server 和 Office Communications Server 的用戶端與互動。 不同於先前的版本，Lync Server 2010 支援新的 Lync 2013 用戶端。 這可讓組織人員從 Lync Server 2010 推出新用戶端的 Lync Server 升級獨立升級。

<div>

## <a name="supported-server-and-client-combinations"></a>支援的伺服器和用戶端組合

下表顯示支援的用戶端版本和伺服器版本組合。 Lync Server 2013 支援兩個舊版用戶端，和 Lync Server 2010 支援新的 Lync 2013 用戶端。


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
<td><p>Lync 2010 群組交談</p></td>
<td><p>不適用</p></td>
<td><p>支援 1</p></td>
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
<td><p>不支援 2</p></td>
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


1 in Microsoft Lync Server 2010，已隨附於 Group Chat 伺服器、 協力廠商信任的應用程式適用於 Lync Server 2010 群組聊天功能。 Lync 2013 用戶端不與 Lync Server 2010，Group Chat 相容。

2Lync Web App 2013https 現在提供的完整會議中體驗，包括電腦音訊及視訊，並會被視為 Lync 2010 Attendee 取代。

3The 目前狀態和 Office Communicator 2007 R2 中的 IM 功能相容搭配 Lync Server 2013，但不是會議功能。 在移轉期間從 Office Communications Server 2007 R2，Office Communicator 2007 R2 適合用來顯示狀態及 IM 互通性，但使用者應該使用 Lync Web App 2013https 加入 Lync Server 2013 會議。

<div>


> [!NOTE]  
> 如需 Lync Server 2013 用戶端並存和更早版本的 Lync Server 和 Office Communications Server 的用戶端進行互動的能力的詳細資訊，請參閱規劃文件中的<A href="lync-server-2013-client-interoperability-in-lync-2013.md">Lync 2013 中的用戶端互通性</A>。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

