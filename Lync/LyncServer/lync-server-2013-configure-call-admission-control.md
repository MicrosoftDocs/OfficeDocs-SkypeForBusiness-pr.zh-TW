---
title: Lync Server 2013： 設定通話許可控制
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
ms.openlocfilehash: e318ac448aa046f001022d40bc5680fd62d37378
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="c22e6-102">在 Lync Server 2013 中設定通話許可控制</span><span class="sxs-lookup"><span data-stu-id="c22e6-102">Configure call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c22e6-103">_**主題上次修改日期：** 2012年-09-21_</span><span class="sxs-lookup"><span data-stu-id="c22e6-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c22e6-104">通話許可控制 (CAC) 是解決方案，可以決定是否可以建立的即時工作階段為基礎，協助防範擁塞網路上的使用者的音訊/視訊品質不佳的可用頻寬。</span><span class="sxs-lookup"><span data-stu-id="c22e6-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="c22e6-105">CAC 控制僅適用於音訊與視訊、 即時流量，並不會影響資料流量。</span><span class="sxs-lookup"><span data-stu-id="c22e6-105">CAC controls real-time traffic only for audio and video, and does not affect data traffic.</span></span> <span data-ttu-id="c22e6-106">CAC 可能會將電話路由傳送到網際網路路徑時的預設 WAN 路徑沒有所需的頻寬。</span><span class="sxs-lookup"><span data-stu-id="c22e6-106">CAC may route the call through an Internet path when the default WAN path does not have the required bandwidth.</span></span> <span data-ttu-id="c22e6-107">如需詳細資訊，請參閱規劃文件中的[Planning for Lync Server 2013 中的通話許可控制](lync-server-2013-planning-for-call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="c22e6-107">For details, see [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="c22e6-108">本章節提供一組範例程序，說明如何部署及管理 CAC 網路中。</span><span class="sxs-lookup"><span data-stu-id="c22e6-108">This section provides a set of example procedures that illustrate how to deploy and manage CAC in your network.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c22e6-109">部署 CAC 之前，您必須先收集必要資訊的所有企業網路拓撲中, 所述<A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">範例： 收集您的 Lync Server 2013 中的通話許可控制需求</A>中規劃文件。</span><span class="sxs-lookup"><span data-stu-id="c22e6-109">Before you deploy CAC, you must gather all of the required information for your enterprise network topology, as described in <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Example: Gathering your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="c22e6-110">也請務必 CAC 的元件，已安裝並啟動中, 所述<A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">定義和設定 Lync Server 2013 中的前端集區或 Standard Edition server</A>部署文件中。</span><span class="sxs-lookup"><span data-stu-id="c22e6-110">Also be sure that CAC components have been installed and activated, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c22e6-111">所有本節中的 CAC 部署及管理範例是使用 Lync Server 管理命令介面來都執行。</span><span class="sxs-lookup"><span data-stu-id="c22e6-111">All CAC deployment and management examples in this section are performed by using the Lync Server Management Shell.</span></span> <span data-ttu-id="c22e6-112">或者，您也可以使用 Lync Server 控制台的 [<STRONG>網路設定</STRONG>] 區段來管理 CAC。</span><span class="sxs-lookup"><span data-stu-id="c22e6-112">As an alternative, you can also use the <STRONG>Network Configuration</STRONG> section of Lync Server Control Panel to manage CAC.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c22e6-113">本章節內容</span><span class="sxs-lookup"><span data-stu-id="c22e6-113">In This Section</span></span>

  - [<span data-ttu-id="c22e6-114">設定 Lync Server 2013 中的 CAC 網路地區</span><span class="sxs-lookup"><span data-stu-id="c22e6-114">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)

  - [<span data-ttu-id="c22e6-115">在 Lync Server 2013 中建立頻寬原則設定檔</span><span class="sxs-lookup"><span data-stu-id="c22e6-115">Create bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [<span data-ttu-id="c22e6-116">設定 Lync Server 2013 中的 CAC 的網路網站</span><span class="sxs-lookup"><span data-stu-id="c22e6-116">Configure network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-sites-for-cac.md)

  - [<span data-ttu-id="c22e6-117">將子網路與網站關聯的 Lync Server 2013 中的 CAC</span><span class="sxs-lookup"><span data-stu-id="c22e6-117">Associate subnets with network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [<span data-ttu-id="c22e6-118">在 Lync Server 2013 中建立網路地區連結</span><span class="sxs-lookup"><span data-stu-id="c22e6-118">Create network region links in Lync Server 2013</span></span>](lync-server-2013-create-network-region-links.md)

  - [<span data-ttu-id="c22e6-119">在 Lync Server 2013 中建立網路區間路由</span><span class="sxs-lookup"><span data-stu-id="c22e6-119">Create network interregion routes in Lync Server 2013</span></span>](lync-server-2013;-create-network-interregion-routes.md)

  - [<span data-ttu-id="c22e6-120">Lync Server 2013 中建立網站間原則</span><span class="sxs-lookup"><span data-stu-id="c22e6-120">Create network intersite policies in Lync Server 2013</span></span>](lync-server-2013-create-network-intersite-policies.md)

  - [<span data-ttu-id="c22e6-121">啟用 Lync Server 2013 中的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="c22e6-121">Enable call admission control in Lync Server 2013</span></span>](lync-server-2013-enable-call-admission-control.md)

  - [<span data-ttu-id="c22e6-122">Lync Server 2013 的通話許可控制部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="c22e6-122">Call admission control deployment checklist for Lync Server 2013</span></span>](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

