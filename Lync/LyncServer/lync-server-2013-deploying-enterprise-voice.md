---
title: Lync Server 2013：部署企業語音
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf57d55899d556ddfde633c975ae9f0516e48e14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="874e3-102">在 Lync Server 2013 中部署企業版語音</span><span class="sxs-lookup"><span data-stu-id="874e3-102">Deploying Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="874e3-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="874e3-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="874e3-104">Lync Server 2013，企業語音是 Lync Server 2013 基礎結構的一部分。</span><span class="sxs-lookup"><span data-stu-id="874e3-104">Lync Server 2013, Enterprise Voice is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="874e3-105">部署企業語音要求您：</span><span class="sxs-lookup"><span data-stu-id="874e3-105">Deploying Enterprise Voice requires that you:</span></span>

<div id="sectionSection0" class="section">

1.  <span data-ttu-id="874e3-106">請在規劃檔的 [ [Lync Server 2013] 區段中，查看企業語音規劃](lync-server-2013-planning-for-enterprise-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="874e3-106">Review the [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) section of the Planning documentation.</span></span>

2.  <span data-ttu-id="874e3-107">使用此工作負載來完成要部署之功能和元件的方案。</span><span class="sxs-lookup"><span data-stu-id="874e3-107">Finalize plans for features and components to deploy with this workload.</span></span>

3.  <span data-ttu-id="874e3-108">執行規劃工具以設計反映您部署決定的拓撲。</span><span class="sxs-lookup"><span data-stu-id="874e3-108">Run Planning Tool to design a topology that reflects your deployment decisions.</span></span>

4.  <span data-ttu-id="874e3-109">如在 [部署檔] 中的 [ [Lync Server 2013] 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)，請在 [拓撲建立器] 中開啟拓撲設計。</span><span class="sxs-lookup"><span data-stu-id="874e3-109">Open the topology design in Topology Builder, as described in [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="874e3-110">[拓撲建立器] 的安裝是內部池之部署程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="874e3-110">Installation of Topology Builder is part of the deployment process for the internal pool.</span></span> <span data-ttu-id="874e3-111">如需詳細資訊，請參閱在部署檔中<A href="lync-server-2013-install-lync-server-administrative-tools.md">安裝 Lync Server 2013 系統管理工具</A>。</span><span class="sxs-lookup"><span data-stu-id="874e3-111">For details, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="874e3-112">此外，您還必須已在中央網站和分支網站上部署 Lync Server、企業版，且對應到您選擇要部署的參考拓撲。</span><span class="sxs-lookup"><span data-stu-id="874e3-112">Additionally, you must have already deployed Lync Server, Enterprise Edition at central sites and branch sites that correspond to the reference topology that you choose to deploy.</span></span> <span data-ttu-id="874e3-113">您必須先定義、發佈及安裝至少一個內部池的檔案，才能部署企業語音元件，而且您必須使用拓撲建立器來定義及發佈內部池。</span><span class="sxs-lookup"><span data-stu-id="874e3-113">You can’t deploy Enterprise Voice components until you have defined, published, and installed files for at least one internal pool, and you must use Topology Builder to define and publish an internal pool.</span></span>

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

<span data-ttu-id="874e3-114">若要查看含企業語音伺服器角色（以及它們與其他 Lync Server 2013 伺服器角色）的範例，請參閱規劃檔中的[Lync server 2013 中的參考拓撲](lync-server-2013-reference-topologies.md)。</span><span class="sxs-lookup"><span data-stu-id="874e3-114">To view reference topologies with examples of where Enterprise Voice server roles can be deployed (and their relationship to one another and other Lync Server 2013 server roles), see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span>

<span data-ttu-id="874e3-115">若要查看說明並說明範例呼叫許可控制部署（包括網路區域、網路網站和子網）的參照拓朴，請參閱在規劃檔中的[Lync Server 2013 中收集您對通話許可控制的需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="874e3-115">To view a reference topology that illustrates and explains a sample call admission control deployment, including network regions, network sites, and subnets, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> <span data-ttu-id="874e3-116">若要在中央網站部署企業語音，請繼續閱讀本節中的主題。</span><span class="sxs-lookup"><span data-stu-id="874e3-116">To deploy Enterprise Voice at a central site, continue reading the topics in this section.</span></span> <span data-ttu-id="874e3-117">若要在分支網站上部署企業語音，請跳過部署檔中的<A href="lync-server-2013-deploying-branch-sites.md">Lync Server 2013 中的 [部署分支網站</A>]。</span><span class="sxs-lookup"><span data-stu-id="874e3-117">To deploy Enterprise Voice at a branch site, skip to <A href="lync-server-2013-deploying-branch-sites.md">Deploying branch sites in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="874e3-118">本節包含適用于部署的程式，其中，在每個前端伺服器或標準版伺服器上 collocated 的中繼伺服器（如有建議），以及使用獨立的中繼伺服器池的部署。</span><span class="sxs-lookup"><span data-stu-id="874e3-118">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="874e3-119">如果您使用拓撲建立器定義併發布在每個前端伺服器或標準版伺服器上 collocates 轉送伺服器的拓撲，就可以略過下列內容，因為部署嚮導已自動安裝檔案供當您為前端伺服器池或標準版伺服器安裝檔案時，會進行中繼伺服器：</span><span class="sxs-lookup"><span data-stu-id="874e3-119">You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>

  - [<span data-ttu-id="874e3-120">在 Lync Server 2013 中設定主幹</span><span class="sxs-lookup"><span data-stu-id="874e3-120">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

<span data-ttu-id="874e3-121">如果您使用拓撲建立器在獨立的池中定義併發布轉送伺服器，您可以使用下列內容：</span><span class="sxs-lookup"><span data-stu-id="874e3-121">If you used Topology Builder to define and publish a Mediation Server in a stand-alone pool, you can use the following content:</span></span>

  - <span data-ttu-id="874e3-122">請確認您的拓撲符合軟體與環境的先決條件，如[Lync Server 2013 的企業語音先決條件](lync-server-2013-enterprise-voice-prerequisites.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="874e3-122">Verify that your topology meets the software and environment prerequisites, as described in [Enterprise Voice prerequisites for Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="874e3-123">本節內容</span><span class="sxs-lookup"><span data-stu-id="874e3-123">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="874e3-124">Lync Server 2013 的企業語音先決條件</span><span class="sxs-lookup"><span data-stu-id="874e3-124">Enterprise Voice prerequisites for Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [<span data-ttu-id="874e3-125">在 Lync Server 2013 中部署中繼伺服器並定義對等項目</span><span class="sxs-lookup"><span data-stu-id="874e3-125">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [<span data-ttu-id="874e3-126">在 Lync Server 2013 中設定主幹</span><span class="sxs-lookup"><span data-stu-id="874e3-126">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [<span data-ttu-id="874e3-127">在 Lync Server 2013 中設定撥號對應表</span><span class="sxs-lookup"><span data-stu-id="874e3-127">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [<span data-ttu-id="874e3-128">在 Lync Server 2013 中設定語音原則、PSTN 使用方式記錄及語音路由</span><span class="sxs-lookup"><span data-stu-id="874e3-128">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [<span data-ttu-id="874e3-129">在 Lync Server 2013 中匯出和匯入語音路由組態</span><span class="sxs-lookup"><span data-stu-id="874e3-129">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="874e3-130">在 Lync Server 2013 中測試語音路由</span><span class="sxs-lookup"><span data-stu-id="874e3-130">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [<span data-ttu-id="874e3-131">在 Lync Server 2013 中發佈語音路由設定的擱置變更</span><span class="sxs-lookup"><span data-stu-id="874e3-131">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="874e3-132">部署內部部署的 Exchange UM，以提供 Lync Server 2013 語音信箱</span><span class="sxs-lookup"><span data-stu-id="874e3-132">Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail</span></span>](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [<span data-ttu-id="874e3-133">在主控 Exchange UM 上提供 Lync Server 2013 使用者語音信箱</span><span class="sxs-lookup"><span data-stu-id="874e3-133">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [<span data-ttu-id="874e3-134">配置與 Exchange Online 的內部部署 Lync Server 2013 整合</span><span class="sxs-lookup"><span data-stu-id="874e3-134">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [<span data-ttu-id="874e3-135">在 Lync Server 2013 中部署高級企業語音功能</span><span class="sxs-lookup"><span data-stu-id="874e3-135">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [<span data-ttu-id="874e3-136">關於 Lync Server 2013 中的網路區域、網站和子網路</span><span class="sxs-lookup"><span data-stu-id="874e3-136">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [<span data-ttu-id="874e3-137">在 Lync Server 2013 中建立或修改網路區域</span><span class="sxs-lookup"><span data-stu-id="874e3-137">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [<span data-ttu-id="874e3-138">在 Lync Server 2013 中建立或修改網站</span><span class="sxs-lookup"><span data-stu-id="874e3-138">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [<span data-ttu-id="874e3-139">在 Lync Server 2013 中建立子網路與網路站台的關聯</span><span class="sxs-lookup"><span data-stu-id="874e3-139">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [<span data-ttu-id="874e3-140">在 Lync Server 2013 中設定通話許可控制</span><span class="sxs-lookup"><span data-stu-id="874e3-140">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)
    
      - [<span data-ttu-id="874e3-141">在 Lync Server 2013 中設定增強型 9-1-1</span><span class="sxs-lookup"><span data-stu-id="874e3-141">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [<span data-ttu-id="874e3-142">在 Lync Server 2013 中設定媒體旁路</span><span class="sxs-lookup"><span data-stu-id="874e3-142">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [<span data-ttu-id="874e3-143">在 Lync Server 2013 中啟用企業語音的使用者</span><span class="sxs-lookup"><span data-stu-id="874e3-143">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="874e3-144">請參閱</span><span class="sxs-lookup"><span data-stu-id="874e3-144">See Also</span></span>


[<span data-ttu-id="874e3-145">在 Lync Server 2013 中部署分支網站</span><span class="sxs-lookup"><span data-stu-id="874e3-145">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)  
[<span data-ttu-id="874e3-146">在 Lync Server 2013 中設定撥入會議</span><span class="sxs-lookup"><span data-stu-id="874e3-146">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)  
[<span data-ttu-id="874e3-147">在 Lync Server 2013 中設定通話駐留</span><span class="sxs-lookup"><span data-stu-id="874e3-147">Configuring Call Park in Lync Server 2013</span></span>](lync-server-2013-configuring-call-park.md)  
[<span data-ttu-id="874e3-148">在 Lync Server 2013 中設定未指派號碼的宣告</span><span class="sxs-lookup"><span data-stu-id="874e3-148">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[<span data-ttu-id="874e3-149">在 Lync Server 2013 中部署監視</span><span class="sxs-lookup"><span data-stu-id="874e3-149">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

