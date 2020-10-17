---
title: Lync Server 2013： edge 元件支援的伺服器組合
description: Lync Server 2013： edge 元件支援的伺服器組合。
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
ms.openlocfilehash: 7bf253e5210e077ca62b3d00f7f130d54d8392a5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556359"
---
# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="68c40-103">Lync Server 2013 中的 edge 元件支援的伺服器組合</span><span class="sxs-lookup"><span data-stu-id="68c40-103">Supported server collocation for edge components in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68c40-104">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="68c40-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="68c40-105">在 Edge Server 上組合 Access Edge service、Web 會議 Edge service、A/V Edge service 和 XMPP Proxy 服務。</span><span class="sxs-lookup"><span data-stu-id="68c40-105">The Access Edge service, Web Conferencing Edge service, A/V Edge service and XMPP Proxy service are collocated on the Edge Servers.</span></span> <span data-ttu-id="68c40-106">下列伺服器提供外部使用者存取所需的各項功能，而且必須部署在專用伺服器：</span><span class="sxs-lookup"><span data-stu-id="68c40-106">The following servers provide functions needed for external user access and must be deployed as dedicated servers:</span></span>

  - <span data-ttu-id="68c40-107">Edge Server</span><span class="sxs-lookup"><span data-stu-id="68c40-107">Edge Server</span></span>

  - <span data-ttu-id="68c40-108">Director (選擇性)</span><span class="sxs-lookup"><span data-stu-id="68c40-108">Director (Optional)</span></span>

  - <span data-ttu-id="68c40-109">反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="68c40-109">Reverse proxy</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="68c40-110">反向 proxy 不需要專門服務于 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="68c40-110">The reverse proxy does not need to be dedicated to serving only Lync Server 2013.</span></span> <span data-ttu-id="68c40-111">例如，您可以提供服務來發佈 Lync Server Web 服務，並同時為另一個網站提供已發佈的網站，該網站與 Lync Server 根本沒有任何關係。</span><span class="sxs-lookup"><span data-stu-id="68c40-111">For example, you can provide services to publish the Lync Server Web services, and concurrently provide a published Web site for another Web site that has no bearing on Lync Server at all.</span></span> <span data-ttu-id="68c40-112">如果您在周邊網路中已有反向 proxy 伺服器以支援其他服務，您可以將其用於 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="68c40-112">If you already have a reverse proxy server in the perimeter network to support other services, you can use it for Lync Server 2013.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

