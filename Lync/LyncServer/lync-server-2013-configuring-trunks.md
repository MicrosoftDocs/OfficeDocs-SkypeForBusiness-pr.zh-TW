---
title: Lync Server 2013：設定主幹
description: Lync Server 2013：設定主幹。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07d9503cd38419a7145796a6edf8484a14cdeb53
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544149"
---
# <a name="configuring-trunks-in-lync-server-2013"></a><span data-ttu-id="b67b0-103">在 Lync Server 2013 中設定主幹</span><span class="sxs-lookup"><span data-stu-id="b67b0-103">Configuring trunks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b67b0-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b67b0-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b67b0-105">在企業語音部署中，您可以設定轉送伺服器與一或多個下列對等間的主幹，為組織中的 Enterprise Voice 用戶端和裝置提供公用交換電話網路 (PSTN) 連線能力：</span><span class="sxs-lookup"><span data-stu-id="b67b0-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

  - <span data-ttu-id="b67b0-106">網際網路電話語音服務提供者 (ITSP) 的 SIP 主幹連線</span><span class="sxs-lookup"><span data-stu-id="b67b0-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="b67b0-107">PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="b67b0-107">PSTN gateway</span></span>

  - <span data-ttu-id="b67b0-108">專用交換機 (Private branch exchange，PBX)</span><span class="sxs-lookup"><span data-stu-id="b67b0-108">Private branch exchange (PBX)</span></span>

<span data-ttu-id="b67b0-109">如需詳細資訊，請參閱規劃檔中的 [規劃 Lync Server 2013 中的 PSTN 連線能力](lync-server-2013-planning-for-pstn-connectivity.md) 。</span><span class="sxs-lookup"><span data-stu-id="b67b0-109">For details, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) in the Planning documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b67b0-110">在您開始進行主幹設定之前，請確認已建立拓撲，而且中繼伺服器及其對等已設定好，並彼此產生關聯。</span><span class="sxs-lookup"><span data-stu-id="b67b0-110">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="b67b0-111">如需詳細資訊，請參閱部署檔中的在 <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Lync Server 2013 中定義拓撲</A> 產生器中的閘道。</span><span class="sxs-lookup"><span data-stu-id="b67b0-111">For details, see <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b67b0-112">作為主幹設定的一部分，您可以啟用 Lync Server 2013 媒體旁路功能，讓媒體略過轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="b67b0-112">As a part of trunk configuration, you can enable the Lync Server 2013 media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="b67b0-113">不論是否啟用媒體旁路功能，都可以設定主幹，但強烈建議您啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="b67b0-113">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="b67b0-114">如需詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-planning-for-media-bypass.md">規劃 Lync Server 2013 中的媒體旁路</A> 。</span><span class="sxs-lookup"><span data-stu-id="b67b0-114">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b67b0-115">本章節內容</span><span class="sxs-lookup"><span data-stu-id="b67b0-115">In This Section</span></span>

  - [<span data-ttu-id="b67b0-116">Lync Server 2013 中的多個主幹支援</span><span class="sxs-lookup"><span data-stu-id="b67b0-116">Multiple trunk support in Lync Server 2013</span></span>](lync-server-2013-multiple-trunk-support.md)

  - [<span data-ttu-id="b67b0-117">Lync Server 2013 中的主幹間路由</span><span class="sxs-lookup"><span data-stu-id="b67b0-117">Inter-trunk routing in Lync Server 2013</span></span>](lync-server-2013-inter-trunk-routing.md)

  - [<span data-ttu-id="b67b0-118">在 Lync Server 2013 中查看主幹設定資訊</span><span class="sxs-lookup"><span data-stu-id="b67b0-118">View trunk configuration information in Lync Server 2013</span></span>](lync-server-2013-view-trunk-configuration-information.md)

  - [<span data-ttu-id="b67b0-119">在 Lync Server 2013 中設定含媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="b67b0-119">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="b67b0-120">在 Lync Server 2013 中設定無媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="b67b0-120">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [<span data-ttu-id="b67b0-121">在 Lync Server 2013 中建立主幹設定的新集合</span><span class="sxs-lookup"><span data-stu-id="b67b0-121">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [<span data-ttu-id="b67b0-122">在 Lync Server 2013 中刪除現有的 SIP 主幹設定的集合</span><span class="sxs-lookup"><span data-stu-id="b67b0-122">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="b67b0-123">在 Lync Server 2013 中修改 SIP 主幹設定設定</span><span class="sxs-lookup"><span data-stu-id="b67b0-123">Modify SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="b67b0-124">在 Lync Server 2013 中測試 SIP 主幹設定設定</span><span class="sxs-lookup"><span data-stu-id="b67b0-124">Test SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="b67b0-125">在 Lync Server 2013 中查看個別 SIP 主幹的相關資訊</span><span class="sxs-lookup"><span data-stu-id="b67b0-125">View information about individual SIP trunks in Lync Server 2013</span></span>](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b67b0-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b67b0-126">See Also</span></span>


[<span data-ttu-id="b67b0-127">在 Lync Server 2013 中的拓撲產生器中定義閘道</span><span class="sxs-lookup"><span data-stu-id="b67b0-127">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[<span data-ttu-id="b67b0-128">在 Lync Server 2013 中規劃 PSTN 連線能力</span><span class="sxs-lookup"><span data-stu-id="b67b0-128">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
[<span data-ttu-id="b67b0-129">在 Lync Server 2013 中規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="b67b0-129">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

