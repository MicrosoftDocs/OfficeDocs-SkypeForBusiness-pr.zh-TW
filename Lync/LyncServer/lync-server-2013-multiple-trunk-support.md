---
title: Lync Server 2013： 多個主幹支援
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
ms.openlocfilehash: 4a2f8e9bea40532486d75e76887e35b496df8631
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="multiple-trunk-support-in-lync-server-2013"></a><span data-ttu-id="d5c5d-102">Lync Server 2013 中的多個主幹支援</span><span class="sxs-lookup"><span data-stu-id="d5c5d-102">Multiple trunk support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5c5d-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="d5c5d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d5c5d-104">Lync Server 2013 功能可支援多個閘道與中繼伺服器之間的關聯。</span><span class="sxs-lookup"><span data-stu-id="d5c5d-104">Lync Server 2013 functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="d5c5d-105">這些關聯中所定義的主幹，也就是邏輯關聯的中繼伺服器集區與公用交換的電話網路 (PSTN) 閘道、 工作階段邊界控制器 (SBC) 或 IP PBX 之間進行。</span><span class="sxs-lookup"><span data-stu-id="d5c5d-105">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="d5c5d-106">使用拓撲產生器來使閘道與中繼伺服器 （也就是主幹） 產生關聯。</span><span class="sxs-lookup"><span data-stu-id="d5c5d-106">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

  - <span data-ttu-id="d5c5d-107">若要指派或移除 Lync Server 2013 中的主幹，您必須先在拓撲產生器中定義主幹。</span><span class="sxs-lookup"><span data-stu-id="d5c5d-107">To assign or remove a trunk in Lync Server 2013, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="d5c5d-108">主幹所組成的下列關聯： 中繼伺服器的完整網域名稱 (FQDN)，中繼伺服器的聆聽連接埠、 閘道的 FQDN、 閘道聆聽連接埠。</span><span class="sxs-lookup"><span data-stu-id="d5c5d-108">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>

  - <span data-ttu-id="d5c5d-109">若要設定多個主幹，您可以建立多個相同的閘道與中繼伺服器之間的關聯。</span><span class="sxs-lookup"><span data-stu-id="d5c5d-109">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="d5c5d-110">這可提供其他企業語音基礎結構，也就是在專用交換機 (pbx) interoperational 案例特別有用。</span><span class="sxs-lookup"><span data-stu-id="d5c5d-110">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span>

<span data-ttu-id="d5c5d-111">定義主幹時，它必須與路由相關聯。</span><span class="sxs-lookup"><span data-stu-id="d5c5d-111">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="d5c5d-112">若要建立關聯的主幹路由，請您可以定義主幹的簡單名稱在拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="d5c5d-112">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="d5c5d-113">Lync Server Control Panel，其中主幹可以與路由相關聯的主幹名稱使用這個簡單的名稱。</span><span class="sxs-lookup"><span data-stu-id="d5c5d-113">This simple name is used as the trunk name in the Lync Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="d5c5d-114">簡單的主幹名稱會當做 Lync Server 管理命令介面的閘道名稱。</span><span class="sxs-lookup"><span data-stu-id="d5c5d-114">The simple trunk name is used as the gateway name from the Lync Server Management Shell.</span></span>

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

<span data-ttu-id="d5c5d-115">系統管理員必須先選取預設主幹相關聯的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="d5c5d-115">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="d5c5d-116">從 [拓撲產生器相關聯的中繼伺服器，以滑鼠右鍵按一下，然後按一下 [**內容**。</span><span class="sxs-lookup"><span data-stu-id="d5c5d-116">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="d5c5d-117">指定中繼伺服器的預設閘道。</span><span class="sxs-lookup"><span data-stu-id="d5c5d-117">Specify the default gateway for the Mediation Server.</span></span>

<span data-ttu-id="d5c5d-118">下圖說明針對每個中繼伺服器和閘道定義的多個主幹。</span><span class="sxs-lookup"><span data-stu-id="d5c5d-118">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span>

<span data-ttu-id="d5c5d-119">**M-N 主幹路由**</span><span class="sxs-lookup"><span data-stu-id="d5c5d-119">**M-N Trunk Routing**</span></span>

<span data-ttu-id="d5c5d-120">![多個主幹工作分派。](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "多個主幹工作分派。")</span><span class="sxs-lookup"><span data-stu-id="d5c5d-120">![Multiple trunk assignments.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Multiple trunk assignments.")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

