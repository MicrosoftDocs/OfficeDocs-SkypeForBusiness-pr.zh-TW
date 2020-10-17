---
title: Lync Server 2013：建立 edge 和 Director 拓撲
description: Lync Server 2013：建立 edge 和 Director 拓撲。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Building an edge and Director topology
ms:assetid: 11e5759e-d69f-4c39-8994-f467c279c558
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398202(v=OCS.15)
ms:contentKeyID: 48183451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcb2d422136cf0a421c68ebc2adba50f03c5cc85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569269"
---
# <a name="building-an-edge-and-director-topology-in-lync-server-2013"></a><span data-ttu-id="1e33b-103">在 Lync Server 2013 中建立 edge 和 Director 拓撲</span><span class="sxs-lookup"><span data-stu-id="1e33b-103">Building an edge and Director topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e33b-104">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="1e33b-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="1e33b-105">建置拓撲牽涉到下列規劃與部署工作：</span><span class="sxs-lookup"><span data-stu-id="1e33b-105">Building the topology involves the following planning and deployment tasks:</span></span>

  - <span data-ttu-id="1e33b-106">**規劃**    您必須定義組織的適當拓撲，並識別部署所需的元件。</span><span class="sxs-lookup"><span data-stu-id="1e33b-106">**Planning**   You need to define an appropriate topology for your organization and identify the components required to deploy it.</span></span> <span data-ttu-id="1e33b-107">以下是規劃程序中的標準步驟。</span><span class="sxs-lookup"><span data-stu-id="1e33b-107">These are standard steps in the planning process.</span></span> <span data-ttu-id="1e33b-108">Lync Server 2013 提供的 Microsoft Lync Server 2013，規劃工具可讓您輕鬆開始規劃程式，也就是在您的需求與計畫完成後，也能輕鬆地進行變更。</span><span class="sxs-lookup"><span data-stu-id="1e33b-108">The Microsoft Lync Server 2013, Planning Tool provided with Lync Server 2013 makes it easy to start the planning process, as well as including the ability to easily make changes as your requirements and plans are finalized.</span></span>

  - <span data-ttu-id="1e33b-109">**部署**    您使用拓撲產生器定義的拓撲，對部署任何 Lync Server 2013 伺服器而言是必要的。</span><span class="sxs-lookup"><span data-stu-id="1e33b-109">**Deployment**   The topology that you define using Topology Builder is essential to the deployment of any Lync Server 2013 server.</span></span> <span data-ttu-id="1e33b-110">如果您在規劃工作時未使用拓撲產生器來完成定義及發行拓撲，您必須先完成該拓撲，然後再發佈拓撲，再部署 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="1e33b-110">If you do not finish defining and publishing your topology by using Topology Builder as part of your planning efforts, you must complete it and publish the topology before you deploy your Edge Servers.</span></span>

<span data-ttu-id="1e33b-111">您必須先部署至少一個內部集區，才能部署 Edge Server 元件，而且必須安裝拓撲產生器才能部署內部集區。</span><span class="sxs-lookup"><span data-stu-id="1e33b-111">You cannot deploy Edge Server components until you have deployed at least one internal pool, and you must install Topology Builder to deploy an internal pool.</span></span> <span data-ttu-id="1e33b-112">本節不涵蓋拓撲產生器的安裝，因為這是內部集區之安裝程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="1e33b-112">This section does not cover installation of Topology Builder because that is part of the installation process for the internal pool.</span></span>

<span data-ttu-id="1e33b-113">如需這些工具的詳細資訊，請參閱 [Lync Server 2013 中的外部使用者存取的部署檢查清單](lync-server-2013-deployment-checklist-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="1e33b-113">For details about these tools, see [Deployment checklist for external user access in Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1e33b-114">如果您先前使用拓撲產生器來定義完整的拓撲，包括 edge 拓撲，您可以在 [ <A href="lync-server-2013-define-your-edge-topology.md">Lync server 2013] 中略過 [定義您的 edge 拓撲</A> ]，並在此區段的 [ <A href="lync-server-2013-publish-your-topology.md">lync server 2013] 工作中發佈拓撲</A> ，但是您必須完成 [ <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">匯出 Lync server 2013 拓撲]，然後將其複製到 [外部媒體] 以進行 edge 安裝</A> 任務。</span><span class="sxs-lookup"><span data-stu-id="1e33b-114">If you previously used Topology Builder to define a complete topology, including the edge topology, you do can skip the <A href="lync-server-2013-define-your-edge-topology.md">Define your edge topology in Lync Server 2013</A> and <A href="lync-server-2013-publish-your-topology.md">Publish your topology in Lync Server 2013</A> tasks in this section, but you do need to complete the <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A> task.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1e33b-115">本章節內容</span><span class="sxs-lookup"><span data-stu-id="1e33b-115">In This Section</span></span>

  - [<span data-ttu-id="1e33b-116">在 Lync Server 2013 中定義您的 edge 拓撲</span><span class="sxs-lookup"><span data-stu-id="1e33b-116">Define your edge topology in Lync Server 2013</span></span>](lync-server-2013-define-your-edge-topology.md)

  - [<span data-ttu-id="1e33b-117">在您的拓撲中為 Lync Server 2013 定義選用的 Director 拓撲</span><span class="sxs-lookup"><span data-stu-id="1e33b-117">Define optional Director topologies in your topology for Lync Server 2013</span></span>](lync-server-2013-define-optional-director-topologies-in-your-topology.md)

  - [<span data-ttu-id="1e33b-118">在 Lync Server 2013 中發行您的拓撲</span><span class="sxs-lookup"><span data-stu-id="1e33b-118">Publish your topology in Lync Server 2013</span></span>](lync-server-2013-publish-your-topology.md)

  - [<span data-ttu-id="1e33b-119">匯出 Lync Server 2013 拓撲，並將其複製到 edge 安裝的外部媒體</span><span class="sxs-lookup"><span data-stu-id="1e33b-119">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

