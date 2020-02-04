---
title: Lync Server 2013：建立回應群組代理群組
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group agent groups
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520969(v=OCS.15)
ms:contentKeyID: 48183688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e2a8a41b67818cf1f2aec9ec8daaa46eeff783a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-response-group-agent-groups-lync-server-2013"></a>在 Lync Server 2013 中建立回應群組代理群組

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-12_

當您建立 [代理群組] 時，請選取指派給群組的 agent，並指定其他群組設定，例如路由方法，以及代理程式是否可以登入和登出群組。

必須登入和登出群組的代理程式（與登入或登出 Lync Server 不同）稱為*正式代理程式*。 正式的代理程式必須先登入群組，才能接收路由到群組的呼叫。 此功能對從群組接聽通話的工程師很有用。 正式的代理程式可在 Lync 2013 中按一下功能表項目來登入和登出其群組，以開啟 Windows Internet Explorer Internet 瀏覽器，並顯示網頁主控台。

未登入或登出群組的工程師稱為*非正式代理*程式。 非正式的代理程式會在登入 Lync Server 時自動登入該群組，且無法登出群組。

<div>


> [!NOTE]  
> 只有內部部署使用者可以使用代理程式。 如果代理程式是從內部部署移至線上，回應群組呼叫將不會路由至該代理程式。



</div>

<div>

## <a name="in-this-section"></a>本節內容

[在 Lync Server 2013 中建立或修改代理群組](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

