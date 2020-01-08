---
title: Lync Server 2013：Edge 元件支援的伺服器組合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported server collocation for edge components
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425934(v=OCS.15)
ms:contentKeyID: 48183978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3ad78cc1060c64181a75acefa21e64809e0d7b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977015"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a>Lync Server 2013 中 Edge 元件支援的伺服器組合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

[存取邊緣] 服務、[Web 會議邊緣] 服務、A/V 邊緣服務與 XMPP Proxy 服務在邊緣伺服器上都是 collocated 的。 下列伺服器提供外部使用者存取所需的功能，而且必須部署為專用伺服器：

  - Edge 伺服器

  - 導演（選用）

  - 反向 proxy

<div>


> [!IMPORTANT]  
> 反向 proxy 不需要專門為 Lync Server 2013 提供服務。 例如，您可以提供服務來發佈 Lync Server Web 服務，並同時為另一個網站提供已發佈的網站，而不需要 Lync 伺服器。 如果您在周邊網路中已經有反向 proxy 伺服器支援其他服務，您可以將它用於 Lync Server 2013。



</div>

</div>

<span> </span>

</div>

</div>

</div>

