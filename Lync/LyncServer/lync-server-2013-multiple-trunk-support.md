---
title: Lync Server 2013：支援多個主幹
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
ms.openlocfilehash: 9d13ca1a28fd28a6d280ddf3a18e57e09376e668
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="multiple-trunk-support-in-lync-server-2013"></a><span data-ttu-id="48ede-102">Lync Server 2013 中有多個中繼支援</span><span class="sxs-lookup"><span data-stu-id="48ede-102">Multiple trunk support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48ede-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="48ede-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="48ede-104">Lync Server 2013 功能支援閘道與中繼伺服器之間的多個關聯性。</span><span class="sxs-lookup"><span data-stu-id="48ede-104">Lync Server 2013 functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="48ede-105">這些關聯是透過定義幹線來建立的，這是中繼伺服器池與公用交換式電話網絡（PSTN）閘道、會話邊界控制器（SBC）或 IP PBX 之間的邏輯關聯。</span><span class="sxs-lookup"><span data-stu-id="48ede-105">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="48ede-106">使用 [拓撲建立器]，將閘道與中繼伺服器（也就是 trunks）建立關聯。</span><span class="sxs-lookup"><span data-stu-id="48ede-106">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

  - <span data-ttu-id="48ede-107">若要在 Lync Server 2013 中指派或移除主幹，您必須先在拓撲建立器中定義主幹。</span><span class="sxs-lookup"><span data-stu-id="48ede-107">To assign or remove a trunk in Lync Server 2013, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="48ede-108">主幹包含下列關聯：中繼伺服器的完整功能變數名稱（FQDN）、中繼伺服器偵聽埠、閘道 FQDN，以及閘道偵聽埠。</span><span class="sxs-lookup"><span data-stu-id="48ede-108">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>

  - <span data-ttu-id="48ede-109">若要設定多個 trunks，您可以在同一個閘道與中繼伺服器之間建立多個關聯性。</span><span class="sxs-lookup"><span data-stu-id="48ede-109">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="48ede-110">這可為企業語音結構提供額外的復原能力，這在私人分支 exchange （PBX） interoperational 案例中特別有用。</span><span class="sxs-lookup"><span data-stu-id="48ede-110">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span>

<span data-ttu-id="48ede-111">定義主幹時，必須與路由建立關聯。</span><span class="sxs-lookup"><span data-stu-id="48ede-111">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="48ede-112">若要將主幹與路線建立關聯，您可以在 [拓撲建立器] 中定義主幹的簡單名稱。</span><span class="sxs-lookup"><span data-stu-id="48ede-112">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="48ede-113">這個簡單的名稱是在 Lync Server [控制台] 中用來做為幹線名稱，其中 trunks 可以與路由建立關聯。</span><span class="sxs-lookup"><span data-stu-id="48ede-113">This simple name is used as the trunk name in the Lync Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="48ede-114">簡單的主幹名稱是從 Lync Server 管理命令介面的閘道名稱使用。</span><span class="sxs-lookup"><span data-stu-id="48ede-114">The simple trunk name is used as the gateway name from the Lync Server Management Shell.</span></span>

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

<span data-ttu-id="48ede-115">系統管理員必須選取與中繼伺服器相關聯的預設主幹。</span><span class="sxs-lookup"><span data-stu-id="48ede-115">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="48ede-116">從拓撲建立器，以滑鼠右鍵按一下關聯的中繼伺服器，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="48ede-116">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="48ede-117">指定中繼伺服器的預設閘道。</span><span class="sxs-lookup"><span data-stu-id="48ede-117">Specify the default gateway for the Mediation Server.</span></span>

<span data-ttu-id="48ede-118">下圖說明針對每個中繼伺服器和閘道定義的多個 trunks。</span><span class="sxs-lookup"><span data-stu-id="48ede-118">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span>

<span data-ttu-id="48ede-119">**M-N 幹線路由**</span><span class="sxs-lookup"><span data-stu-id="48ede-119">**M-N Trunk Routing**</span></span>

<span data-ttu-id="48ede-120">![多重主幹指派。](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "多重主幹指派。")</span><span class="sxs-lookup"><span data-stu-id="48ede-120">![Multiple trunk assignments.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Multiple trunk assignments.")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

