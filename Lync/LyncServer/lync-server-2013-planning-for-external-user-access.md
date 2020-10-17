---
title: Lync Server 2013：規劃外部使用者存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3068cae2545c0d3f1df3f04935914d21d032ffc2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522180"
---
# <a name="planning-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="7908d-102">在 Lync Server 2013 中規劃外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="7908d-102">Planning for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7908d-103">_**主題上次修改日期：** 2013-01-19_</span><span class="sxs-lookup"><span data-stu-id="7908d-103">_**Topic Last Modified:** 2013-01-19_</span></span>

<span data-ttu-id="7908d-104">大多陣列織中的通訊都包括並非內部網路內部的服務和使用者。</span><span class="sxs-lookup"><span data-stu-id="7908d-104">Communications in most organizations involve services and users that are not inside your internal network.</span></span> <span data-ttu-id="7908d-105">這些服務和使用者包括暫時或永久異地的員工、客戶或夥伴組織的員工、使用公用立即訊息 (IM) 服務的人員，以及您邀請參加會議及簡報的潛在客戶、合作夥伴和匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="7908d-105">These services and users include employees who are temporarily or permanently offsite, employees of customer or partner organizations, people who use public instant messaging (IM) services, and potential customers, partners and anonymous users whom you invite to meetings and presentations.</span></span> <span data-ttu-id="7908d-106">在本檔中，這些人員統稱為 *外部使用者*。</span><span class="sxs-lookup"><span data-stu-id="7908d-106">In this documentation, these people are collectively referred to as *external users*.</span></span>

<span data-ttu-id="7908d-107">使用 Microsoft Lync Server 2013，您組織中的使用者可以使用 IM 和目前狀態與外部使用者通訊，也可以加入音訊/視頻 (A/V) 會議和 web 會議與您的非現場員工和其他類型的外部使用者。</span><span class="sxs-lookup"><span data-stu-id="7908d-107">With Microsoft Lync Server 2013, users in your organization can use IM and presence to communicate with external users, and they can participate in audio/video (A/V) conferencing and web conferencing with your offsite employees and other types of external users.</span></span> <span data-ttu-id="7908d-108">您也可以從行動裝置和 Enterprise Voice，支援外部存取。</span><span class="sxs-lookup"><span data-stu-id="7908d-108">You can also support external access from mobile devices and over Enterprise Voice.</span></span> <span data-ttu-id="7908d-109">非組織成員的外部使用者可以參與 Lync Server 2013 會議，允許匿名出席者。</span><span class="sxs-lookup"><span data-stu-id="7908d-109">External users who are not members of your organization can participate in Lync Server 2013 meetings, allowing anonymous attendees.</span></span>

<span data-ttu-id="7908d-110">為了支援整個組織防火牆的通訊，您可以在周邊網路中部署 Lync Server 2013 Edge Server (也稱為 DMZ、網路隔離區域及遮罩式子網) 。</span><span class="sxs-lookup"><span data-stu-id="7908d-110">To support communications across your organization’s firewall, you deploy Lync Server 2013 Edge Server in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="7908d-111">Edge Server 會控制防火牆外的使用者如何連線至您的內部 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="7908d-111">The Edge Server controls how users outside the firewall can connect to your internal Lync Server 2013 deployment.</span></span> <span data-ttu-id="7908d-112">它也會控制與來源防火牆內之外部使用者的通訊。</span><span class="sxs-lookup"><span data-stu-id="7908d-112">It also controls communications with external users that originate within the firewall.</span></span>

<span data-ttu-id="7908d-113">視您的需求而定，您可以在一個或多個位置部署一或多個 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="7908d-113">Depending on your requirements, you can deploy one or more Edge Servers in one or more locations.</span></span> <span data-ttu-id="7908d-114">本節說明 Lync Server 2013 中外部使用者存取的案例，並說明如何規劃 edge 和反向 proxy 拓撲。</span><span class="sxs-lookup"><span data-stu-id="7908d-114">This section describes scenarios for external user access in Lync Server 2013, and it explains how to plan your edge and reverse proxy topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7908d-115">雖然您需要 Edge Server 才能支援 Enterprise Voice 和外部使用者存取，但本節著重于支援 IM、顯示狀態、A/V 會議、同盟、web 會議和 Lync Mobile。</span><span class="sxs-lookup"><span data-stu-id="7908d-115">Although you need an Edge Server to support Enterprise Voice and external user access, this section focuses on support for IM, presence, A/V conferencing, federation, web conferencing, and Lync Mobile.</span></span> <span data-ttu-id="7908d-116">如需有關 Enterprise Voice 支援的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-planning-for-enterprise-voice.md">規劃 Lync Server 2013 中的 Enterprise Voice</A> 。</span><span class="sxs-lookup"><span data-stu-id="7908d-116">For details about support for Enterprise Voice, see <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7908d-117">本章節內容</span><span class="sxs-lookup"><span data-stu-id="7908d-117">In This Section</span></span>

  - [<span data-ttu-id="7908d-118">Lync Server 2013 中影響 Edge Server 規劃的變更</span><span class="sxs-lookup"><span data-stu-id="7908d-118">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [<span data-ttu-id="7908d-119">Lync Server 2013 之外部使用者存取元件的系統需求</span><span class="sxs-lookup"><span data-stu-id="7908d-119">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="7908d-120">Lync Server 2013 中的外部使用者存取的概覽</span><span class="sxs-lookup"><span data-stu-id="7908d-120">Overview of external user access in Lync Server 2013</span></span>](lync-server-2013-overview-of-external-user-access.md)

  - [<span data-ttu-id="7908d-121">瞭解 Lync Server 2013 中的自動探索</span><span class="sxs-lookup"><span data-stu-id="7908d-121">Understanding Autodiscover in Lync Server 2013</span></span>](lync-server-2013-understanding-autodiscover.md)

  - [<span data-ttu-id="7908d-122">在 Lync Server 2013 中選擇拓撲</span><span class="sxs-lookup"><span data-stu-id="7908d-122">Choosing a topology in Lync Server 2013</span></span>](lync-server-2013-choosing-a-topology.md)

  - [<span data-ttu-id="7908d-123">Lync Server 2013 中的資料收集</span><span class="sxs-lookup"><span data-stu-id="7908d-123">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="7908d-124">決定 Lync Server 2013 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="7908d-124">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="7908d-125">決定 Lync Server 2013 的外部 A/V 防火牆和埠需求</span><span class="sxs-lookup"><span data-stu-id="7908d-125">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="7908d-126">在 Lync Server 2013 中規劃 Edge Server 憑證</span><span class="sxs-lookup"><span data-stu-id="7908d-126">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)

  - [<span data-ttu-id="7908d-127">Lync Server 2013 中的外部使用者存取案例</span><span class="sxs-lookup"><span data-stu-id="7908d-127">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

