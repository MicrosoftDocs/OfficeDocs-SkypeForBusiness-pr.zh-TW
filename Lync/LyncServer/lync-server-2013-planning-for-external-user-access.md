---
title: Lync Server 2013： 規劃外部使用者存取
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
ms.openlocfilehash: 15b4a64c729268efcbdf2bb572c47122d4b41510
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="57d22-102">規劃 Lync Server 2013 中的外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="57d22-102">Planning for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57d22-103">_**上次修改主題：** 2013年-01-19_</span><span class="sxs-lookup"><span data-stu-id="57d22-103">_**Topic Last Modified:** 2013-01-19_</span></span>

<span data-ttu-id="57d22-104">在大多數的組織的通訊是關於服務和不在您的內部網路內的使用者。</span><span class="sxs-lookup"><span data-stu-id="57d22-104">Communications in most organizations involve services and users that are not inside your internal network.</span></span> <span data-ttu-id="57d22-105">這些服務和使用者包含暫時或永久異地，員工的客戶或合作夥伴組織，使用公用立即訊息 (IM) 服務和潛在客戶、 合作夥伴和您邀請匿名使用者的人員對會議的簡報。</span><span class="sxs-lookup"><span data-stu-id="57d22-105">These services and users include employees who are temporarily or permanently offsite, employees of customer or partner organizations, people who use public instant messaging (IM) services, and potential customers, partners and anonymous users whom you invite to meetings and presentations.</span></span> <span data-ttu-id="57d22-106">在此文件，這些人員統稱為*外部使用者*。</span><span class="sxs-lookup"><span data-stu-id="57d22-106">In this documentation, these people are collectively referred to as *external users*.</span></span>

<span data-ttu-id="57d22-107">使用 Microsoft Lync Server 2013 中，您組織中的使用者可以使用 IM 和目前狀態與外部使用者通訊和他們可以參與音訊/視訊 (A / V) 會議和 web 會議與離站員工和其他類型的外部使用者。</span><span class="sxs-lookup"><span data-stu-id="57d22-107">With Microsoft Lync Server 2013, users in your organization can use IM and presence to communicate with external users, and they can participate in audio/video (A/V) conferencing and web conferencing with your offsite employees and other types of external users.</span></span> <span data-ttu-id="57d22-108">您也可以支援從行動裝置，並透過 Enterprise Voice 的外部存取。</span><span class="sxs-lookup"><span data-stu-id="57d22-108">You can also support external access from mobile devices and over Enterprise Voice.</span></span> <span data-ttu-id="57d22-109">不屬於您組織的外部使用者可以參與 Lync Server 2013 會議，允許匿名出席者。</span><span class="sxs-lookup"><span data-stu-id="57d22-109">External users who are not members of your organization can participate in Lync Server 2013 meetings, allowing anonymous attendees.</span></span>

<span data-ttu-id="57d22-110">若要支援跨組織的防火牆的通訊，您可以部署 Lync Server 2013 Edge Server 在周邊網路 （也稱為 DMZ、 非軍事區和遮蔽式子網路）。</span><span class="sxs-lookup"><span data-stu-id="57d22-110">To support communications across your organization’s firewall, you deploy Lync Server 2013 Edge Server in your perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span> <span data-ttu-id="57d22-111">Edge Server 控制如何在防火牆外的使用者可以連線到您的內部 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="57d22-111">The Edge Server controls how users outside the firewall can connect to your internal Lync Server 2013 deployment.</span></span> <span data-ttu-id="57d22-112">它也會控制源自內防火牆的外部使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="57d22-112">It also controls communications with external users that originate within the firewall.</span></span>

<span data-ttu-id="57d22-113">根據您的需求，您可以部署一個或多個位置中的一或多個 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="57d22-113">Depending on your requirements, you can deploy one or more Edge Servers in one or more locations.</span></span> <span data-ttu-id="57d22-114">本節說明在 Lync Server 2013 中的外部使用者存取的案例，其中說明如何規劃您的 edge 和反向 proxy 拓撲。</span><span class="sxs-lookup"><span data-stu-id="57d22-114">This section describes scenarios for external user access in Lync Server 2013, and it explains how to plan your edge and reverse proxy topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="57d22-115">雖然您需要的 Edge Server，以支援企業語音與外部使用者存取，本節著重於支援 IM、 目前狀態、 A / V 會議、 同盟、 web 會議和 Lync Mobile。</span><span class="sxs-lookup"><span data-stu-id="57d22-115">Although you need an Edge Server to support Enterprise Voice and external user access, this section focuses on support for IM, presence, A/V conferencing, federation, web conferencing, and Lync Mobile.</span></span> <span data-ttu-id="57d22-116">如需支援的企業語音的詳細資訊，請參閱規劃文件中的<A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Lync Server 2013 中的企業語音</A>。</span><span class="sxs-lookup"><span data-stu-id="57d22-116">For details about support for Enterprise Voice, see <A href="lync-server-2013-planning-for-enterprise-voice.md">Planning for Enterprise Voice in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="57d22-117">本章節內容</span><span class="sxs-lookup"><span data-stu-id="57d22-117">In This Section</span></span>

  - [<span data-ttu-id="57d22-118">Lync Server 2013 中的變更會影響到 Edge Server 規劃</span><span class="sxs-lookup"><span data-stu-id="57d22-118">Changes in Lync Server 2013 that affect Edge Server planning</span></span>](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [<span data-ttu-id="57d22-119">Lync Server 2013 的外部使用者存取元件的系統需求</span><span class="sxs-lookup"><span data-stu-id="57d22-119">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [<span data-ttu-id="57d22-120">Lync Server 2013 中的外部使用者存取的概觀</span><span class="sxs-lookup"><span data-stu-id="57d22-120">Overview of external user access in Lync Server 2013</span></span>](lync-server-2013-overview-of-external-user-access.md)

  - [<span data-ttu-id="57d22-121">了解在 Lync Server 2013 中的自動探索</span><span class="sxs-lookup"><span data-stu-id="57d22-121">Understanding Autodiscover in Lync Server 2013</span></span>](lync-server-2013-understanding-autodiscover.md)

  - [<span data-ttu-id="57d22-122">Lync Server 2013 中選擇的拓撲</span><span class="sxs-lookup"><span data-stu-id="57d22-122">Choosing a topology in Lync Server 2013</span></span>](lync-server-2013-choosing-a-topology.md)

  - [<span data-ttu-id="57d22-123">Lync Server 2013 中的資料收集</span><span class="sxs-lookup"><span data-stu-id="57d22-123">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="57d22-124">決定針對 Lync Server 2013 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="57d22-124">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)

  - [<span data-ttu-id="57d22-125">決定外部 A / V 防火牆和連接埠需求 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57d22-125">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="57d22-126">Lync Server 2013 中的 Edge Server 憑證計劃</span><span class="sxs-lookup"><span data-stu-id="57d22-126">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)

  - [<span data-ttu-id="57d22-127">Lync Server 2013 中的外部使用者存取的案例</span><span class="sxs-lookup"><span data-stu-id="57d22-127">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

