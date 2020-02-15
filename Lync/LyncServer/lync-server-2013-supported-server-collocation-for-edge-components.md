---
title: Lync Server 2013： 支援 edge 元件的伺服器共同配置
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
ms.openlocfilehash: e52d1c630bba8c93193c2e309d4d3299f45a6388
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="b5c50-102">適用於 Lync Server 2013 中的 edge 元件支援的伺服器共同配置</span><span class="sxs-lookup"><span data-stu-id="b5c50-102">Supported server collocation for edge components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5c50-103">_**主題上次修改日期：** 2012年-09-08_</span><span class="sxs-lookup"><span data-stu-id="b5c50-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="b5c50-104">Access Edge 服務、 Web Conferencing Edge service 為 A / V Edge service 和 XMPP Proxy 服務組合在 Edge Server 上。</span><span class="sxs-lookup"><span data-stu-id="b5c50-104">The Access Edge service, Web Conferencing Edge service, A/V Edge service and XMPP Proxy service are collocated on the Edge Servers.</span></span> <span data-ttu-id="b5c50-105">下列伺服器提供外部使用者存取所需的各項功能，而且必須部署在專用伺服器：</span><span class="sxs-lookup"><span data-stu-id="b5c50-105">The following servers provide functions needed for external user access and must be deployed as dedicated servers:</span></span>

  - <span data-ttu-id="b5c50-106">Edge Server</span><span class="sxs-lookup"><span data-stu-id="b5c50-106">Edge Server</span></span>

  - <span data-ttu-id="b5c50-107">Director (選擇性)</span><span class="sxs-lookup"><span data-stu-id="b5c50-107">Director (Optional)</span></span>

  - <span data-ttu-id="b5c50-108">反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="b5c50-108">Reverse proxy</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b5c50-109">反向 proxy 不需要是專門提供 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="b5c50-109">The reverse proxy does not need to be dedicated to serving only Lync Server 2013.</span></span> <span data-ttu-id="b5c50-110">例如，您可以提供服務給發佈 Lync 伺服器 Web 服務，並同時提供另一個網站，具有不具有 Lync 伺服器上所有已發佈的網站。</span><span class="sxs-lookup"><span data-stu-id="b5c50-110">For example, you can provide services to publish the Lync Server Web services, and concurrently provide a published Web site for another Web site that has no bearing on Lync Server at all.</span></span> <span data-ttu-id="b5c50-111">如果您已在周邊網路，以支援其他服務中的反向 proxy 伺服器，您可以將它用於 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="b5c50-111">If you already have a reverse proxy server in the perimeter network to support other services, you can use it for Lync Server 2013.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

