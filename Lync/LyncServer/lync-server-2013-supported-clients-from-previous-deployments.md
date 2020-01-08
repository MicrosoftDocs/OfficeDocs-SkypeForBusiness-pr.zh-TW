---
title: Lync Server 2013：舊部署支援的用戶端
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported clients from previous deployments
ms:assetid: 69d427f8-57a5-4244-b2ed-f2eb7600285e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398499(v=OCS.15)
ms:contentKeyID: 48184390
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b5cbecf45a9ea5203b3e459a895b2bddb0cfe55
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-clients-from-previous-deployments-in-lync-server-2013"></a>Lync Server 2013 中舊部署支援的用戶端

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-12-14_

在共存案例中，Lync Server 2013 用戶端可以與舊版 Lync Server 和 Office 通訊伺服器的用戶端互動。 與舊版版本不同，Lync Server 2010 支援新的 Lync 2013 用戶端。 這可讓從 Lync Server 2010 升級的組織在獨立于 Lync Server 升級的情況下，推出新的用戶端。

<div>

## <a name="supported-server-and-client-combinations"></a>支援的伺服器和用戶端組合

下表顯示用戶端版本和伺服器版本支援的組合。 Lync Server 2013 支援兩個舊版的用戶端版本，而 Lync Server 2010 支援新的 Lync 2013 用戶端。


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
<th>Office 通訊伺服器 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>受</p></td>
<td><p>受</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2013</p></td>
<td><p>受</p></td>
<td><p>不支援</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>受</p></td>
<td><p>受</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 助理</p></td>
<td><p>受</p></td>
<td><p>受</p></td>
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
<td><p>受</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 出席者</p></td>
<td><p>無法 Supported2</p></td>
<td><p>受</p></td>
<td><p>不支援</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable3</p></td>
<td><p>受</p></td>
<td><p>受</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Office 通訊伺服器 2007 R2 助理</p></td>
<td><p>不支援</p></td>
<td><p>受</p></td>
<td><p>受</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007</p></td>
<td><p>不支援</p></td>
<td><p>受</p></td>
<td><p>受</p></td>
</tr>
<tr class="odd">
<td><p>Office Live Meeting 2007</p></td>
<td><p>不支援</p></td>
<td><p>受</p></td>
<td><p>受</p></td>
</tr>
</tbody>
</table>


1In Microsoft Lync Server 2010，您可以在群組聊天伺服器（即 Lync Server 2010 的協力廠商信任應用程式）中使用群組聊天功能。 Lync 2013 用戶端與 Lync Server 2010 （群組聊天）不相容。

2Lync Web App 2013 現在提供完整的會議體驗，包括電腦音訊和影片，並被視為 Lync 2010 出席者的取代。

Office Communicator 2007 R2 中的3The 目前狀態與 IM 功能與 Lync Server 2013 相容，但會議功能不相容。 從 Office 通訊伺服器 2007 R2 遷移期間，Office Communicator 2007 R2 適用于目前狀態與 IM 互通性，但使用者應該使用 Lync Web App 2013 來加入 Lync Server 2013 會議。

<div>


> [!NOTE]  
> 如需有關 Lync Server 2013 用戶端與舊版 Lync Server 與 Office 通訊伺服器的共存及互動能力的詳細資料，請參閱規劃檔中的<A href="lync-server-2013-client-interoperability-in-lync-2013.md">lync 2013 中的用戶端互通性</A>。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

