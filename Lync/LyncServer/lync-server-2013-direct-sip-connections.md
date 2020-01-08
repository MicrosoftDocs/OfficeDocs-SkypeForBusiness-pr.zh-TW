---
title: Lync Server 2013：直接 SIP 連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Direct SIP connections
ms:assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398151(v=OCS.15)
ms:contentKeyID: 48183357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1decdfd4c755ea1788d088a4b539d8c555987f02
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-connections-in-lync-server-2013"></a><span data-ttu-id="1ab05-102">Lync Server 2013 中的直接 SIP 連線</span><span class="sxs-lookup"><span data-stu-id="1ab05-102">Direct SIP connections in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ab05-103">_**主題上次修改日期：** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="1ab05-103">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="1ab05-104">您可以使用*直接 SIP*連線，將 Lync Server 連線至下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="1ab05-104">You can use *direct SIP connections* to connect Lync Server to either of the following:</span></span>

  - <span data-ttu-id="1ab05-105">IP-PBX （如需詳細資訊，請參閱[Lync Server 2013 中的直接 SIP 部署選項](lync-server-2013-direct-sip-deployment-options.md)）。</span><span class="sxs-lookup"><span data-stu-id="1ab05-105">An IP-PBX (for details, see [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md)).</span></span>

  - <span data-ttu-id="1ab05-106">PSTN 閘道（如需詳細資訊，請參閱[Lync Server 2013 中的 PSTN 閘道部署選項](lync-server-2013-pstn-gateway-deployment-options.md)）。</span><span class="sxs-lookup"><span data-stu-id="1ab05-106">A PSTN gateway (for details, see [PSTN gateway deployment options in Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)).</span></span>

<span data-ttu-id="1ab05-107">若要實現直接 SIP 連線，您必須遵循與實施 SIP 幹線相同的部署步驟。</span><span class="sxs-lookup"><span data-stu-id="1ab05-107">To implement a direct SIP connection, you follow essentially the same deployment steps as you would to implement a SIP trunk.</span></span> <span data-ttu-id="1ab05-108">在這兩種情況下，您可以使用中繼伺服器的外部介面來實現連線。</span><span class="sxs-lookup"><span data-stu-id="1ab05-108">In both cases, you implement the connection by using the external interface of a Mediation Server.</span></span> <span data-ttu-id="1ab05-109">唯一的差異是，您可以將 SIP trunks 連線至外部實體（例如 ITSP 閘道），並將直接 SIP 連線連接到本機網路中的內部實體，例如 IP PBX 或公用交換電話網絡（PSTN）閘道。</span><span class="sxs-lookup"><span data-stu-id="1ab05-109">The only difference is that you connect SIP trunks to an external entity, such as an ITSP gateway, and you connect direct SIP connections to an internal entity within your local network, such as an IP-PBX or a public switched telephone network (PSTN) gateway.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1ab05-110">本節內容</span><span class="sxs-lookup"><span data-stu-id="1ab05-110">In This Section</span></span>

  - [<span data-ttu-id="1ab05-111">Lync Server 2013 中的 SIP 直接部署選項</span><span class="sxs-lookup"><span data-stu-id="1ab05-111">Direct SIP deployment options in Lync Server 2013</span></span>](lync-server-2013-direct-sip-deployment-options.md)

  - [<span data-ttu-id="1ab05-112">Lync Server 2013 中的 PSTN 閘道部署選項</span><span class="sxs-lookup"><span data-stu-id="1ab05-112">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

