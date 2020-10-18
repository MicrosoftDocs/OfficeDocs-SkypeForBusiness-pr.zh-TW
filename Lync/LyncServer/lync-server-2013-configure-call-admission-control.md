---
title: Lync Server 2013：設定通話許可控制
description: Lync Server 2013：設定通話許可控制。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c6da7e20f45e61f7364af3e8b749def05bd29fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575169"
---
# <a name="configure-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="421f5-103">在 Lync Server 2013 中設定通話許可控制</span><span class="sxs-lookup"><span data-stu-id="421f5-103">Configure call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="421f5-104">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="421f5-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="421f5-105">通話許可控制 (CAC) 是一種方案，可判斷即時會話是否可以根據可用的頻寬建立，以協助避免網路擁塞之使用者的音訊/視頻品質不良。</span><span class="sxs-lookup"><span data-stu-id="421f5-105">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="421f5-106">CAC 只會控制音訊和影片的即時流量，而且不會影響資料流量。</span><span class="sxs-lookup"><span data-stu-id="421f5-106">CAC controls real-time traffic only for audio and video, and does not affect data traffic.</span></span> <span data-ttu-id="421f5-107">當預設 WAN 路徑不具備必要的頻寬時，CAC 可能會透過網際網路路徑路由傳送通話。</span><span class="sxs-lookup"><span data-stu-id="421f5-107">CAC may route the call through an Internet path when the default WAN path does not have the required bandwidth.</span></span> <span data-ttu-id="421f5-108">如需詳細資訊，請參閱規劃檔中的 [規劃 Lync Server 2013 中的通話許可控制](lync-server-2013-planning-for-call-admission-control.md) 。</span><span class="sxs-lookup"><span data-stu-id="421f5-108">For details, see [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="421f5-109">本節提供一組範例程式，說明如何在網路中部署及管理 CAC。</span><span class="sxs-lookup"><span data-stu-id="421f5-109">This section provides a set of example procedures that illustrate how to deploy and manage CAC in your network.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="421f5-110">在您部署 CAC 之前，您必須收集商業網路拓撲的所有必要資訊，如範例所述：在規劃檔中 <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">收集 Lync Server 2013 的通話許可控制需求</A> 。</span><span class="sxs-lookup"><span data-stu-id="421f5-110">Before you deploy CAC, you must gather all of the required information for your enterprise network topology, as described in <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Example: Gathering your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="421f5-111">此外，請確定已安裝並啟動 CAC 元件，如在部署檔中的 <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">定義和設定前端集區或 Standard Edition 2013 server</A> 中所述。</span><span class="sxs-lookup"><span data-stu-id="421f5-111">Also be sure that CAC components have been installed and activated, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="421f5-112">本節中的所有 CAC 部署和管理範例都是使用 Lync Server 管理命令介面來執行。</span><span class="sxs-lookup"><span data-stu-id="421f5-112">All CAC deployment and management examples in this section are performed by using the Lync Server Management Shell.</span></span> <span data-ttu-id="421f5-113">或者，您也可以使用 Lync Server 控制台的 [ <STRONG>網路</STRONG> 設定] 區段來管理 CAC。</span><span class="sxs-lookup"><span data-stu-id="421f5-113">As an alternative, you can also use the <STRONG>Network Configuration</STRONG> section of Lync Server Control Panel to manage CAC.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="421f5-114">本章節內容</span><span class="sxs-lookup"><span data-stu-id="421f5-114">In This Section</span></span>

  - [<span data-ttu-id="421f5-115">在 Lync Server 2013 中設定 CAC 的網路地區</span><span class="sxs-lookup"><span data-stu-id="421f5-115">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)

  - [<span data-ttu-id="421f5-116">在 Lync Server 2013 中建立頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="421f5-116">Create bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [<span data-ttu-id="421f5-117">在 Lync Server 2013 中設定 CAC 的網路網站</span><span class="sxs-lookup"><span data-stu-id="421f5-117">Configure network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-sites-for-cac.md)

  - [<span data-ttu-id="421f5-118">在 Lync Server 2013 中將子網與 CAC 的網路網站產生關聯</span><span class="sxs-lookup"><span data-stu-id="421f5-118">Associate subnets with network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [<span data-ttu-id="421f5-119">在 Lync Server 2013 中建立網路地區連結</span><span class="sxs-lookup"><span data-stu-id="421f5-119">Create network region links in Lync Server 2013</span></span>](lync-server-2013-create-network-region-links.md)

  - [<span data-ttu-id="421f5-120">在 Lync Server 2013 中建立網路區間路由</span><span class="sxs-lookup"><span data-stu-id="421f5-120">Create network interregion routes in Lync Server 2013</span></span>](lync-server-2013;-create-network-interregion-routes.md)

  - [<span data-ttu-id="421f5-121">在 Lync Server 2013 中建立網路站間原則</span><span class="sxs-lookup"><span data-stu-id="421f5-121">Create network intersite policies in Lync Server 2013</span></span>](lync-server-2013-create-network-intersite-policies.md)

  - [<span data-ttu-id="421f5-122">在 Lync Server 2013 中啟用通話許可控制</span><span class="sxs-lookup"><span data-stu-id="421f5-122">Enable call admission control in Lync Server 2013</span></span>](lync-server-2013-enable-call-admission-control.md)

  - [<span data-ttu-id="421f5-123">Lync Server 2013 的通話許可控制部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="421f5-123">Call admission control deployment checklist for Lync Server 2013</span></span>](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

