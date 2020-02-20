---
title: Lync Server 2013： 部署中繼伺服器，並定義 peers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16a5611e8137aba2f465c6488201ba1b2936dd76
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a><span data-ttu-id="5572f-102">部署中繼伺服器和 Lync Server 2013 中定義 peers</span><span class="sxs-lookup"><span data-stu-id="5572f-102">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5572f-103">_**主題上次修改日期：** 2012年-09-21_</span><span class="sxs-lookup"><span data-stu-id="5572f-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="5572f-104">Enterprise Voice workload、 電話撥入式會議和進階的 Enterprise Voice 應用程式 （回應群組應用程式、 通話駐留應用程式、 通話許可控制 (CAC)、 等等），可在前端集區。</span><span class="sxs-lookup"><span data-stu-id="5572f-104">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="5572f-105">搭配 Lync Server 2013 中繼伺服器的功能是內建前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="5572f-105">With Lync Server 2013, the functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="5572f-106">不同獨立中繼伺服器不再是必要的。</span><span class="sxs-lookup"><span data-stu-id="5572f-106">A separate stand-alone Mediation Server is no longer necessary.</span></span> <span data-ttu-id="5572f-107">前端集區可以與彼此直接支援閘道 （公用交換電話網路 (PSTN) 閘道或 IP PBX）、 移除做為媒介中繼伺服器的需求。</span><span class="sxs-lookup"><span data-stu-id="5572f-107">Front End pools can communicate directly with supported gateways (a public switched telephone network (PSTN) gateway or an IP-PBX), removing the need for a Mediation Server to serve as an intermediary.</span></span>

<span data-ttu-id="5572f-108">唯一的例外是如果您設定 SIP 主幹連線工作階段邊界控制器至網際網路電話語音服務提供者。</span><span class="sxs-lookup"><span data-stu-id="5572f-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="5572f-109">若要連線至您的 SIP 主幹提供者的企業語音基礎結構，必須部署一部中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="5572f-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>

<span data-ttu-id="5572f-110">Lync 伺服器 （中繼伺服器元件上的前端集區或獨立中繼伺服器） 與閘道之間的連線會定義為呼叫*主幹*邏輯關聯。</span><span class="sxs-lookup"><span data-stu-id="5572f-110">The connection between Lync Server (the Mediation Server component on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a *trunk*.</span></span> <span data-ttu-id="5572f-111">本節主題說明如何定義主幹，以及如何部署獨立中繼伺服器中，如果您連線至 SIP 主幹。</span><span class="sxs-lookup"><span data-stu-id="5572f-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5572f-112">本章節內容</span><span class="sxs-lookup"><span data-stu-id="5572f-112">In This Section</span></span>

  - [<span data-ttu-id="5572f-113">在 Lync Server 2013 中的拓撲產生器中定義中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="5572f-113">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [<span data-ttu-id="5572f-114">在 Lync Server 2013 中的拓撲產生器中定義閘道</span><span class="sxs-lookup"><span data-stu-id="5572f-114">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [<span data-ttu-id="5572f-115">Lync Server 2013 中的中繼伺服器的安裝檔案</span><span class="sxs-lookup"><span data-stu-id="5572f-115">Install the files for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-install-the-files-for-mediation-server.md)

  - [<span data-ttu-id="5572f-116">在 Lync Server 2013 中的拓撲產生器中定義其他主幹</span><span class="sxs-lookup"><span data-stu-id="5572f-116">Define additional trunks in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="5572f-117">相關各節</span><span class="sxs-lookup"><span data-stu-id="5572f-117">Related Sections</span></span>

[<span data-ttu-id="5572f-118">在 Lync Server 2013 中設定電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="5572f-118">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

