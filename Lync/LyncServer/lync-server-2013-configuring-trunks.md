---
title: Lync Server 2013： 設定主幹
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
ms.openlocfilehash: 09151bf1e5fab592f8051878bcd8218690583309
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a><span data-ttu-id="62aea-102">在 Lync Server 2013 中設定主幹</span><span class="sxs-lookup"><span data-stu-id="62aea-102">Configuring trunks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62aea-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="62aea-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="62aea-104">Enterprise Voice 部署的一部分，您可以設定中繼伺服器與一或多個下列同儕 Enterprise Voice 用戶端和組織中的裝置提供公用交換的電話網路 (PSTN) 連線能力之間的主幹：</span><span class="sxs-lookup"><span data-stu-id="62aea-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

  - <span data-ttu-id="62aea-105">網際網路電話語音服務提供者 (ITSP) 的 SIP 主幹連線</span><span class="sxs-lookup"><span data-stu-id="62aea-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="62aea-106">PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="62aea-106">PSTN gateway</span></span>

  - <span data-ttu-id="62aea-107">專用交換機 (Private branch exchange，PBX)</span><span class="sxs-lookup"><span data-stu-id="62aea-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="62aea-108">如需詳細資訊，請參閱規劃文件中的[Planning for Lync Server 2013 中的 PSTN 連線能力](lync-server-2013-planning-for-pstn-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="62aea-108">For details, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) in the Planning documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="62aea-109">在您開始進行主幹設定之前，請確認已建立拓撲，而且中繼伺服器及其對等已設定好，並彼此產生關聯。</span><span class="sxs-lookup"><span data-stu-id="62aea-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="62aea-110">如需詳細資訊，請參閱部署文件中的<A href="lync-server-2013-define-a-gateway-in-topology-builder.md">定義在 Lync Server 2013 中的拓撲產生器的閘道</A>。</span><span class="sxs-lookup"><span data-stu-id="62aea-110">For details, see <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="62aea-111">主幹組態的一部分，您可以啟用 Lync Server 2013 媒體旁路功能，可讓媒體略過中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="62aea-111">As a part of trunk configuration, you can enable the Lync Server 2013 media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="62aea-112">不論是否啟用媒體旁路功能，都可以設定主幹，但強烈建議您啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="62aea-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="62aea-113">如需詳細資訊，請參閱<A href="lync-server-2013-planning-for-media-bypass.md">Planning for 媒體旁路 Lync Server 2013 中規劃文件。</A></span><span class="sxs-lookup"><span data-stu-id="62aea-113">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="62aea-114">本章節內容</span><span class="sxs-lookup"><span data-stu-id="62aea-114">In This Section</span></span>

  - [<span data-ttu-id="62aea-115">Lync Server 2013 中的多個主幹支援</span><span class="sxs-lookup"><span data-stu-id="62aea-115">Multiple trunk support in Lync Server 2013</span></span>](lync-server-2013-multiple-trunk-support.md)

  - [<span data-ttu-id="62aea-116">Lync Server 2013 中的主幹間路由</span><span class="sxs-lookup"><span data-stu-id="62aea-116">Inter-trunk routing in Lync Server 2013</span></span>](lync-server-2013-inter-trunk-routing.md)

  - [<span data-ttu-id="62aea-117">Lync Server 2013 中檢視主幹組態資訊</span><span class="sxs-lookup"><span data-stu-id="62aea-117">View trunk configuration information in Lync Server 2013</span></span>](lync-server-2013-view-trunk-configuration-information.md)

  - [<span data-ttu-id="62aea-118">設定與 Lync Server 2013 中的媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="62aea-118">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [<span data-ttu-id="62aea-119">沒有媒體旁路 Lync Server 2013 中設定主幹</span><span class="sxs-lookup"><span data-stu-id="62aea-119">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [<span data-ttu-id="62aea-120">在 Lync Server 2013 中建立新的主幹集合組態設定</span><span class="sxs-lookup"><span data-stu-id="62aea-120">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [<span data-ttu-id="62aea-121">刪除現有的 Lync Server 2013 中的 SIP 主幹組態設定集合</span><span class="sxs-lookup"><span data-stu-id="62aea-121">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="62aea-122">修改 Lync Server 2013 中的 SIP 主幹組態設定</span><span class="sxs-lookup"><span data-stu-id="62aea-122">Modify SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="62aea-123">在 Lync Server 2013 中測試 SIP 主幹組態設定</span><span class="sxs-lookup"><span data-stu-id="62aea-123">Test SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="62aea-124">檢視 Lync Server 2013 中的個別 SIP 主幹的相關資訊</span><span class="sxs-lookup"><span data-stu-id="62aea-124">View information about individual SIP trunks in Lync Server 2013</span></span>](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="62aea-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="62aea-125">See Also</span></span>


[<span data-ttu-id="62aea-126">在 Lync Server 2013 中的拓撲產生器中定義閘道</span><span class="sxs-lookup"><span data-stu-id="62aea-126">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[<span data-ttu-id="62aea-127">規劃 Lync Server 2013 中的 PSTN 連線</span><span class="sxs-lookup"><span data-stu-id="62aea-127">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
[<span data-ttu-id="62aea-128">規劃 Lync Server 2013 中的媒體旁路</span><span class="sxs-lookup"><span data-stu-id="62aea-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

