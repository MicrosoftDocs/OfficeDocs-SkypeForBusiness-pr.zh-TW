---
title: Lync Server 2013：Edge 元件支援的伺服器組合
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
ms.openlocfilehash: bc12e442be98ba1fd962634460200ce749aca3d6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="f4206-102">Lync Server 2013 中 Edge 元件支援的伺服器組合</span><span class="sxs-lookup"><span data-stu-id="f4206-102">Supported server collocation for edge components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4206-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="f4206-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="f4206-104">[存取邊緣] 服務、[Web 會議邊緣] 服務、A/V 邊緣服務與 XMPP Proxy 服務在邊緣伺服器上都是 collocated 的。</span><span class="sxs-lookup"><span data-stu-id="f4206-104">The Access Edge service, Web Conferencing Edge service, A/V Edge service and XMPP Proxy service are collocated on the Edge Servers.</span></span> <span data-ttu-id="f4206-105">下列伺服器提供外部使用者存取所需的功能，而且必須部署為專用伺服器：</span><span class="sxs-lookup"><span data-stu-id="f4206-105">The following servers provide functions needed for external user access and must be deployed as dedicated servers:</span></span>

  - <span data-ttu-id="f4206-106">Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="f4206-106">Edge Server</span></span>

  - <span data-ttu-id="f4206-107">導演（選用）</span><span class="sxs-lookup"><span data-stu-id="f4206-107">Director (Optional)</span></span>

  - <span data-ttu-id="f4206-108">反向 proxy</span><span class="sxs-lookup"><span data-stu-id="f4206-108">Reverse proxy</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f4206-109">反向 proxy 不需要專門為 Lync Server 2013 提供服務。</span><span class="sxs-lookup"><span data-stu-id="f4206-109">The reverse proxy does not need to be dedicated to serving only Lync Server 2013.</span></span> <span data-ttu-id="f4206-110">例如，您可以提供服務來發佈 Lync Server Web 服務，並同時為另一個網站提供已發佈的網站，而不需要 Lync 伺服器。</span><span class="sxs-lookup"><span data-stu-id="f4206-110">For example, you can provide services to publish the Lync Server Web services, and concurrently provide a published Web site for another Web site that has no bearing on Lync Server at all.</span></span> <span data-ttu-id="f4206-111">如果您在周邊網路中已經有反向 proxy 伺服器支援其他服務，您可以將它用於 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="f4206-111">If you already have a reverse proxy server in the perimeter network to support other services, you can use it for Lync Server 2013.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

