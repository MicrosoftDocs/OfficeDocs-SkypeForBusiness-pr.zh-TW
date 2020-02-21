---
title: Lync Server 2013： 直接 SIP 連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP connections
ms:assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398151(v=OCS.15)
ms:contentKeyID: 48183357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49bfb60eebc6ef8fd271e43f747a4516b2e359d3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="direct-sip-connections-in-lync-server-2013"></a><span data-ttu-id="20338-102">Lync Server 2013 中的直接 SIP 連線</span><span class="sxs-lookup"><span data-stu-id="20338-102">Direct SIP connections in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20338-103">_**主題上次修改日期：** 2012年-08-13_</span><span class="sxs-lookup"><span data-stu-id="20338-103">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="20338-104">您可以使用*直接 SIP 連線*至 Lync 伺服器連線至下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="20338-104">You can use *direct SIP connections* to connect Lync Server to either of the following:</span></span>

  - <span data-ttu-id="20338-105">IP-PBX （如需詳細資訊，請參閱[Lync Server 2013 中的直接 SIP 部署選項](lync-server-2013-direct-sip-deployment-options.md)）。</span><span class="sxs-lookup"><span data-stu-id="20338-105">An IP-PBX (for details, see [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md)).</span></span>

  - <span data-ttu-id="20338-106">PSTN 閘道 （如需詳細資訊，請參閱[Lync Server 2013 中的 PSTN 閘道部署選項](lync-server-2013-pstn-gateway-deployment-options.md)）。</span><span class="sxs-lookup"><span data-stu-id="20338-106">A PSTN gateway (for details, see [PSTN gateway deployment options in Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)).</span></span>

<span data-ttu-id="20338-107">若要實作直接 SIP 連線，基本上遵循您用於實作 SIP 主幹的相同部署步驟。</span><span class="sxs-lookup"><span data-stu-id="20338-107">To implement a direct SIP connection, you follow essentially the same deployment steps as you would to implement a SIP trunk.</span></span> <span data-ttu-id="20338-108">在這兩種情況下，您可以實作連線所使用的中繼伺服器的外部介面。</span><span class="sxs-lookup"><span data-stu-id="20338-108">In both cases, you implement the connection by using the external interface of a Mediation Server.</span></span> <span data-ttu-id="20338-109">唯一的差異在於您將 SIP 主幹連線至外部實體 (如 ITSP 閘道)，而將直接 SIP 連線連接至區域網路中的內部實體 (如 IP-PBX 或公用交換電話網路 (PSTN) 閘道)。</span><span class="sxs-lookup"><span data-stu-id="20338-109">The only difference is that you connect SIP trunks to an external entity, such as an ITSP gateway, and you connect direct SIP connections to an internal entity within your local network, such as an IP-PBX or a public switched telephone network (PSTN) gateway.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="20338-110">本節內容</span><span class="sxs-lookup"><span data-stu-id="20338-110">In This Section</span></span>

  - [<span data-ttu-id="20338-111">Lync Server 2013 中的直接 SIP 部署選項</span><span class="sxs-lookup"><span data-stu-id="20338-111">Direct SIP deployment options in Lync Server 2013</span></span>](lync-server-2013-direct-sip-deployment-options.md)

  - [<span data-ttu-id="20338-112">Lync Server 2013 中的 PSTN 閘道部署選項</span><span class="sxs-lookup"><span data-stu-id="20338-112">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

