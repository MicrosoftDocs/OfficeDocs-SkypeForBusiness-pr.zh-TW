---
title: Lync Server 2013：部署中繼伺服器並定義對等項目
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
ms.openlocfilehash: b20f5e733dddd34971ca3a5070e99364785e147a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a><span data-ttu-id="830fb-102">在 Lync Server 2013 中部署中繼伺服器並定義對等項目</span><span class="sxs-lookup"><span data-stu-id="830fb-102">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="830fb-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="830fb-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="830fb-104">[企業語音工作]、[電話撥入式會議] 和 [高級企業語音應用程式] （回應群組應用程式、通話駐留應用程式、通話許可控制（CAC）等）都可在前端池中使用。</span><span class="sxs-lookup"><span data-stu-id="830fb-104">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="830fb-105">使用 Lync Server 2013，轉送伺服器的功能會內嵌在前端伺服器中。</span><span class="sxs-lookup"><span data-stu-id="830fb-105">With Lync Server 2013, the functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="830fb-106">不再需要個別獨立的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="830fb-106">A separate stand-alone Mediation Server is no longer necessary.</span></span> <span data-ttu-id="830fb-107">前端池可以直接與支援的閘道（公開交換式電話網絡（PSTN）閘道或 IP PBX）通訊，移除要作為仲介的中繼伺服器需求。</span><span class="sxs-lookup"><span data-stu-id="830fb-107">Front End pools can communicate directly with supported gateways (a public switched telephone network (PSTN) gateway or an IP-PBX), removing the need for a Mediation Server to serve as an intermediary.</span></span>

<span data-ttu-id="830fb-108">唯一的例外是如果您將 SIP 主幹設定為連線至網際網路電話服務提供者的會話框線控制器。</span><span class="sxs-lookup"><span data-stu-id="830fb-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="830fb-109">若要將企業語音結構連線至 SIP 中繼提供者，必須部署個別的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="830fb-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>

<span data-ttu-id="830fb-110">Lync Server （前端池或獨立中繼伺服器上的中繼伺服器元件）與閘道之間的連線，會定義為稱為*主幹*的邏輯關聯。</span><span class="sxs-lookup"><span data-stu-id="830fb-110">The connection between Lync Server (the Mediation Server component on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a *trunk*.</span></span> <span data-ttu-id="830fb-111">本節中的主題描述如何定義主幹，以及如果您連線到 SIP 主幹，如何部署獨立的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="830fb-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="830fb-112">本節內容</span><span class="sxs-lookup"><span data-stu-id="830fb-112">In This Section</span></span>

  - [<span data-ttu-id="830fb-113">在 Lync Server 2013 的拓撲產生器中定義中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="830fb-113">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [<span data-ttu-id="830fb-114">在 Lync Server 2013 的拓撲產生器中定義閘道</span><span class="sxs-lookup"><span data-stu-id="830fb-114">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [<span data-ttu-id="830fb-115">在 Lync Server 2013 中安裝轉送服務伺服器的檔案</span><span class="sxs-lookup"><span data-stu-id="830fb-115">Install the files for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-install-the-files-for-mediation-server.md)

  - [<span data-ttu-id="830fb-116">在 Lync Server 2013 的拓撲產生器中定義其他 trunks</span><span class="sxs-lookup"><span data-stu-id="830fb-116">Define additional trunks in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="830fb-117">相關各節</span><span class="sxs-lookup"><span data-stu-id="830fb-117">Related Sections</span></span>

[<span data-ttu-id="830fb-118">在 Lync Server 2013 中設定撥入會議</span><span class="sxs-lookup"><span data-stu-id="830fb-118">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

