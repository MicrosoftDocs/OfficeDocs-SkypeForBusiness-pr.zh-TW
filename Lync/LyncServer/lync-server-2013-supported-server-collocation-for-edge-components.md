---
title: Lync Server 2013： edge 元件支援的伺服器組合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server collocation for edge components
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425934(v=OCS.15)
ms:contentKeyID: 48183978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71c8e30cfd4257982781e446a61c18518b570e06
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524000"
---
# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a>Lync Server 2013 中的 edge 元件支援的伺服器組合

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

在 Edge Server 上組合 Access Edge service、Web 會議 Edge service、A/V Edge service 和 XMPP Proxy 服務。 下列伺服器提供外部使用者存取所需的各項功能，而且必須部署在專用伺服器：

  - Edge Server

  - Director (選擇性)

  - 反向 Proxy

<div>


> [!IMPORTANT]  
> 反向 proxy 不需要專門服務于 Lync Server 2013。 例如，您可以提供服務來發佈 Lync Server Web 服務，並同時為另一個網站提供已發佈的網站，該網站與 Lync Server 根本沒有任何關係。 如果您在周邊網路中已有反向 proxy 伺服器以支援其他服務，您可以將其用於 Lync Server 2013。



</div>

</div>

<span> </span>

</div>

</div>

</div>

