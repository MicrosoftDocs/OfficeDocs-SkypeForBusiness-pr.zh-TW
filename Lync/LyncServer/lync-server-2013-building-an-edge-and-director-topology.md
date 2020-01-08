---
title: Lync Server 2013：建置 Edge 和 Director 拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Building an edge and Director topology
ms:assetid: 11e5759e-d69f-4c39-8994-f467c279c558
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398202(v=OCS.15)
ms:contentKeyID: 48183451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae45053e8d9c01cd484da8a052304712f04a06fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976111"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="building-an-edge-and-director-topology-in-lync-server-2013"></a><span data-ttu-id="1f7a8-102">在 Lync Server 2013 中建置 Edge 和 Director 拓撲</span><span class="sxs-lookup"><span data-stu-id="1f7a8-102">Building an edge and Director topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f7a8-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="1f7a8-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="1f7a8-104">建立拓撲包含下列規劃與部署工作：</span><span class="sxs-lookup"><span data-stu-id="1f7a8-104">Building the topology involves the following planning and deployment tasks:</span></span>

  - <span data-ttu-id="1f7a8-105">**規劃**   您需要為組織定義適當的拓撲，並找出部署所需的元件。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-105">**Planning**   You need to define an appropriate topology for your organization and identify the components required to deploy it.</span></span> <span data-ttu-id="1f7a8-106">這些是規劃流程中的標準步驟。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-106">These are standard steps in the planning process.</span></span> <span data-ttu-id="1f7a8-107">Lync Server 2013 提供的 Microsoft Lync Server 2013、規劃工具可讓您輕鬆開始規劃程式，以及包括在您的需求和方案完成後輕鬆進行變更的功能。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-107">The Microsoft Lync Server 2013, Planning Tool provided with Lync Server 2013 makes it easy to start the planning process, as well as including the ability to easily make changes as your requirements and plans are finalized.</span></span>

  - <span data-ttu-id="1f7a8-108">**部署**   您使用拓撲建立器定義的拓朴，對於部署任何 Lync server 2013 伺服器而言，都是必要的。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-108">**Deployment**   The topology that you define using Topology Builder is essential to the deployment of any Lync Server 2013 server.</span></span> <span data-ttu-id="1f7a8-109">如果您沒有在規劃工作中使用拓撲建立器來定義及發佈拓撲，您必須先完成它併發布拓撲，才能部署邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-109">If you do not finish defining and publishing your topology by using Topology Builder as part of your planning efforts, you must complete it and publish the topology before you deploy your Edge Servers.</span></span>

<span data-ttu-id="1f7a8-110">您必須先部署至少一個內部池，才能部署 Edge 伺服器元件，而且必須安裝 [拓撲建立器] 來部署內部池。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-110">You cannot deploy Edge Server components until you have deployed at least one internal pool, and you must install Topology Builder to deploy an internal pool.</span></span> <span data-ttu-id="1f7a8-111">本節不會涵蓋拓撲建立器的安裝，因為這是內部池安裝程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-111">This section does not cover installation of Topology Builder because that is part of the installation process for the internal pool.</span></span>

<span data-ttu-id="1f7a8-112">如需這些工具的詳細資訊，請參閱[Lync Server 2013 中的外部使用者存取部署檢查清單](lync-server-2013-deployment-checklist-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-112">For details about these tools, see [Deployment checklist for external user access in Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1f7a8-113">如果您先前使用拓撲建立器定義完整的拓撲（包括邊緣拓撲），您可以跳過在<A href="lync-server-2013-define-your-edge-topology.md">Lync server 2013 中定義您的 edge 拓朴</A>，並在此區段的<A href="lync-server-2013-publish-your-topology.md">lync Server 2013 工作中發佈您的拓撲</A>，但您必須完成<A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">匯出 Lync server 2013 拓撲，並將它複製到外部媒體以進行 edge 安裝</A>任務。</span><span class="sxs-lookup"><span data-stu-id="1f7a8-113">If you previously used Topology Builder to define a complete topology, including the edge topology, you do can skip the <A href="lync-server-2013-define-your-edge-topology.md">Define your edge topology in Lync Server 2013</A> and <A href="lync-server-2013-publish-your-topology.md">Publish your topology in Lync Server 2013</A> tasks in this section, but you do need to complete the <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A> task.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1f7a8-114">本節內容</span><span class="sxs-lookup"><span data-stu-id="1f7a8-114">In This Section</span></span>

  - [<span data-ttu-id="1f7a8-115">在 Lync Server 2013 中定義 Edge 拓撲</span><span class="sxs-lookup"><span data-stu-id="1f7a8-115">Define your edge topology in Lync Server 2013</span></span>](lync-server-2013-define-your-edge-topology.md)

  - [<span data-ttu-id="1f7a8-116">針對 Lync Server 2013 在拓撲中定義選用的 Director 拓撲</span><span class="sxs-lookup"><span data-stu-id="1f7a8-116">Define optional Director topologies in your topology for Lync Server 2013</span></span>](lync-server-2013-define-optional-director-topologies-in-your-topology.md)

  - [<span data-ttu-id="1f7a8-117">在 Lync Server 2013 中發行拓撲</span><span class="sxs-lookup"><span data-stu-id="1f7a8-117">Publish your topology in Lync Server 2013</span></span>](lync-server-2013-publish-your-topology.md)

  - [<span data-ttu-id="1f7a8-118">匯出 Lync Server 2013 拓撲並將拓撲複製到 Edge 安裝的外部媒體</span><span class="sxs-lookup"><span data-stu-id="1f7a8-118">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

