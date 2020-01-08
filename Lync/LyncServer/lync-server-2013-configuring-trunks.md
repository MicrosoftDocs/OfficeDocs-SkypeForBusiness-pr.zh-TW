---
title: Lync Server 2013：設定主幹
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d40a290f75ae48b73a4695e04ea2934b0c4d695
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a><span data-ttu-id="12236-102">在 Lync Server 2013 中設定主幹</span><span class="sxs-lookup"><span data-stu-id="12236-102">Configuring trunks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12236-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="12236-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="12236-104">在企業語音部署中，您可以設定在中繼伺服器與一或多個下列對等之間的幹線，為貴組織中的企業語音用戶端和裝置提供公用交換電話網絡（PSTN）連線：</span><span class="sxs-lookup"><span data-stu-id="12236-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

  - <span data-ttu-id="12236-105">網際網路電話服務提供者（ITSP）的 SIP 中繼連線</span><span class="sxs-lookup"><span data-stu-id="12236-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>

  - <span data-ttu-id="12236-106">PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="12236-106">PSTN gateway</span></span>

  - <span data-ttu-id="12236-107">私人分支 exchange （PBX）</span><span class="sxs-lookup"><span data-stu-id="12236-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="12236-108">如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 規劃 PSTN](lync-server-2013-planning-for-pstn-connectivity.md)連線。</span><span class="sxs-lookup"><span data-stu-id="12236-108">For details, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) in the Planning documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="12236-109">開始中繼設定前，請確認已建立拓撲，且已設定並與其他中繼伺服器及其對等專案相關聯。</span><span class="sxs-lookup"><span data-stu-id="12236-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="12236-110">如需詳細資訊，請參閱部署檔中的<A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Lync Server 2013 [拓撲</A>建立器] 中的 [定義閘道]。</span><span class="sxs-lookup"><span data-stu-id="12236-110">For details, see <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Define a gateway in Topology Builder in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="12236-111">您可以在主幹設定中啟用 Lync Server 2013 媒體旁路功能，這可讓媒體略過中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="12236-111">As a part of trunk configuration, you can enable the Lync Server 2013 media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="12236-112">Trunks 可以使用或不啟用媒體旁路進行設定，但我們強烈建議您啟用它。</span><span class="sxs-lookup"><span data-stu-id="12236-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="12236-113">如需詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-planning-for-media-bypass.md">Lync Server 2013 中的媒體旁路規劃</A>。</span><span class="sxs-lookup"><span data-stu-id="12236-113">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="12236-114">本節內容</span><span class="sxs-lookup"><span data-stu-id="12236-114">In This Section</span></span>

  - [<span data-ttu-id="12236-115">Lync Server 2013 中有多個中繼支援</span><span class="sxs-lookup"><span data-stu-id="12236-115">Multiple trunk support in Lync Server 2013</span></span>](lync-server-2013-multiple-trunk-support.md)

  - [<span data-ttu-id="12236-116">Lync Server 2013 中的中繼間路由</span><span class="sxs-lookup"><span data-stu-id="12236-116">Inter-trunk routing in Lync Server 2013</span></span>](lync-server-2013-inter-trunk-routing.md)

  - [<span data-ttu-id="12236-117">在 Lync Server 2013 中查看幹線設定資訊</span><span class="sxs-lookup"><span data-stu-id="12236-117">View trunk configuration information in Lync Server 2013</span></span>](lync-server-2013-view-trunk-configuration-information.md)

  - <span data-ttu-id="12236-118">[在 Lync Server 2013 中使用 [旁路媒體] 設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="12236-118">[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)</span></span>

  - [<span data-ttu-id="12236-119">在 Lync Server 2013 中設定沒有媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="12236-119">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [<span data-ttu-id="12236-120">在 Lync Server 2013 中建立中繼設定的新集合</span><span class="sxs-lookup"><span data-stu-id="12236-120">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [<span data-ttu-id="12236-121">刪除 Lync Server 2013 中現有的 SIP 幹線配置設定集合</span><span class="sxs-lookup"><span data-stu-id="12236-121">Delete an existing collection of SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="12236-122">在 Lync Server 2013 中修改 SIP 幹線配置設定</span><span class="sxs-lookup"><span data-stu-id="12236-122">Modify SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="12236-123">在 Lync Server 2013 中測試 SIP 幹線配置設定</span><span class="sxs-lookup"><span data-stu-id="12236-123">Test SIP trunk configuration settings in Lync Server 2013</span></span>](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [<span data-ttu-id="12236-124">在 Lync Server 2013 中查看個別 SIP trunks 的相關資訊</span><span class="sxs-lookup"><span data-stu-id="12236-124">View information about individual SIP trunks in Lync Server 2013</span></span>](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="12236-125">請參閱</span><span class="sxs-lookup"><span data-stu-id="12236-125">See Also</span></span>


[<span data-ttu-id="12236-126">在 Lync Server 2013 的拓撲產生器中定義閘道</span><span class="sxs-lookup"><span data-stu-id="12236-126">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[<span data-ttu-id="12236-127">在 Lync Server 2013 規劃 PSTN 連線能力</span><span class="sxs-lookup"><span data-stu-id="12236-127">Planning for PSTN connectivity in Lync Server 2013</span></span>](lync-server-2013-planning-for-pstn-connectivity.md)  
[<span data-ttu-id="12236-128">在 Lync Server 2013 中規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="12236-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

