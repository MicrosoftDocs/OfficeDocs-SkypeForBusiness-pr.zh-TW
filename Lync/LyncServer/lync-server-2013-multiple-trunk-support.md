---
title: Lync Server 2013：多個主幹支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2581ee5f67c6af1c5afd0622f7893ccc2486b51d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507040"
---
# <a name="multiple-trunk-support-in-lync-server-2013"></a><span data-ttu-id="55498-102">Lync Server 2013 中的多個主幹支援</span><span class="sxs-lookup"><span data-stu-id="55498-102">Multiple trunk support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55498-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="55498-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="55498-104">Lync Server 2013 功能支援閘道和轉送伺服器之間的多重關聯。</span><span class="sxs-lookup"><span data-stu-id="55498-104">Lync Server 2013 functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="55498-105">這些關聯是透過定義主幹（轉送伺服器集區和公用交換電話網路 (PSTN) 閘道、會話邊界控制器 (SBC) 或 IP-PBX）進行。</span><span class="sxs-lookup"><span data-stu-id="55498-105">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="55498-106">使用拓撲產生器，將閘道與轉送伺服器相關聯 (也就是說，主幹) 。</span><span class="sxs-lookup"><span data-stu-id="55498-106">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

  - <span data-ttu-id="55498-107">若要在 Lync Server 2013 中指派或移除主幹，您必須先在拓撲產生器中定義主幹。</span><span class="sxs-lookup"><span data-stu-id="55498-107">To assign or remove a trunk in Lync Server 2013, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="55498-108">主幹包含下列關聯：轉送伺服器的完整功能變數名稱 (FQDN) 、轉送伺服器接聽埠、閘道 FQDN 及閘道聆聽埠。</span><span class="sxs-lookup"><span data-stu-id="55498-108">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>

  - <span data-ttu-id="55498-109">若要設定多個主幹，您可以在同一個閘道和轉送伺服器之間建立多個關聯。</span><span class="sxs-lookup"><span data-stu-id="55498-109">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="55498-110">這為企業語音基礎結構提供額外的復原能力，尤其適用于私人分公司 exchange (PBX) interoperational 案例。</span><span class="sxs-lookup"><span data-stu-id="55498-110">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span>

<span data-ttu-id="55498-111">定義主幹時，它必須與路由相關聯。</span><span class="sxs-lookup"><span data-stu-id="55498-111">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="55498-112">若要將主幹關聯至路由，您可以在拓撲產生器中定義主幹的簡易名稱。</span><span class="sxs-lookup"><span data-stu-id="55498-112">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="55498-113">在 Lync Server 控制台中，這個簡易名稱是用來做為主幹名稱，主幹可以與路由相關聯。</span><span class="sxs-lookup"><span data-stu-id="55498-113">This simple name is used as the trunk name in the Lync Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="55498-114">簡易主幹名稱是 Lync Server 管理命令介面中使用的閘道名稱。</span><span class="sxs-lookup"><span data-stu-id="55498-114">The simple trunk name is used as the gateway name from the Lync Server Management Shell.</span></span>

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

<span data-ttu-id="55498-115">管理員必須選取與轉送伺服器相關聯的預設主幹。</span><span class="sxs-lookup"><span data-stu-id="55498-115">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="55498-116">在 [拓撲產生器] 中，以滑鼠右鍵按一下關聯的轉送伺服器，然後按一下 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="55498-116">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="55498-117">指定轉送伺服器的預設閘道。</span><span class="sxs-lookup"><span data-stu-id="55498-117">Specify the default gateway for the Mediation Server.</span></span>

<span data-ttu-id="55498-118">下圖說明為每個轉送伺服器和閘道定義的多個主幹。</span><span class="sxs-lookup"><span data-stu-id="55498-118">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span>

<span data-ttu-id="55498-119">**M-N 主幹路由**</span><span class="sxs-lookup"><span data-stu-id="55498-119">**M-N Trunk Routing**</span></span>

<span data-ttu-id="55498-120">![多重主幹指派。](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "多重主幹指派。")</span><span class="sxs-lookup"><span data-stu-id="55498-120">![Multiple trunk assignments.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Multiple trunk assignments.")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

