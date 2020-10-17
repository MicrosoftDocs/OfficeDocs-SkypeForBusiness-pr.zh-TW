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
ms.openlocfilehash: 4b2784c5cb04994004503010426ebc98763c0250
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531146"
---
# <a name="deploying-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="3ef13-102">在 Lync Server 2013 中部署企業語音</span><span class="sxs-lookup"><span data-stu-id="3ef13-102">Deploying Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ef13-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="3ef13-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="3ef13-104">Lync Server 2013，Enterprise Voice 是 Lync Server 2013 基礎結構的一部分。</span><span class="sxs-lookup"><span data-stu-id="3ef13-104">Lync Server 2013, Enterprise Voice is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="3ef13-105">部署 Enterprise Voice 時，需要您：</span><span class="sxs-lookup"><span data-stu-id="3ef13-105">Deploying Enterprise Voice requires that you:</span></span>

<div id="sectionSection0" class="section">

1.  <span data-ttu-id="3ef13-106">請參閱規劃檔中的《 [Lync Server 2013 規劃中的企業語音規劃](lync-server-2013-planning-for-enterprise-voice.md) 」一節。</span><span class="sxs-lookup"><span data-stu-id="3ef13-106">Review the [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) section of the Planning documentation.</span></span>

2.  <span data-ttu-id="3ef13-107">完成與此工作負載一起部署的功能與元件的計畫。</span><span class="sxs-lookup"><span data-stu-id="3ef13-107">Finalize plans for features and components to deploy with this workload.</span></span>

3.  <span data-ttu-id="3ef13-108">執行規劃工具來設計拓撲，以反映您的部署決策。</span><span class="sxs-lookup"><span data-stu-id="3ef13-108">Run Planning Tool to design a topology that reflects your deployment decisions.</span></span>

4.  <span data-ttu-id="3ef13-109">開啟拓撲產生器中的拓撲設計，如在部署檔中的 [定義及設定 Lync Server 2013 中的拓撲](lync-server-2013-defining-and-configuring-the-topology.md) 所述。</span><span class="sxs-lookup"><span data-stu-id="3ef13-109">Open the topology design in Topology Builder, as described in [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3ef13-110">安裝拓撲產生器是內部集區之部署程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="3ef13-110">Installation of Topology Builder is part of the deployment process for the internal pool.</span></span> <span data-ttu-id="3ef13-111">如需詳細資訊，請參閱部署檔中的 <A href="lync-server-2013-install-lync-server-administrative-tools.md">安裝 Lync Server 2013 系統管理工具</A> 。</span><span class="sxs-lookup"><span data-stu-id="3ef13-111">For details, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="3ef13-112">此外，您還必須已在中央網站和分支網站上部署 Lync Server Enterprise Edition，並對應至您選擇要部署的參考拓撲。</span><span class="sxs-lookup"><span data-stu-id="3ef13-112">Additionally, you must have already deployed Lync Server, Enterprise Edition at central sites and branch sites that correspond to the reference topology that you choose to deploy.</span></span> <span data-ttu-id="3ef13-113">您必須先定義、發佈和安裝至少一個內部集區的檔案，然後再使用拓撲產生器來定義及發行內部集區，才能部署 Enterprise Voice 元件。</span><span class="sxs-lookup"><span data-stu-id="3ef13-113">You can’t deploy Enterprise Voice components until you have defined, published, and installed files for at least one internal pool, and you must use Topology Builder to define and publish an internal pool.</span></span>

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

<span data-ttu-id="3ef13-114">若要查看參考拓撲，其可部署 Enterprise Voice server role 的範例，以及其與其他 (和其他 Lync Server 2013 伺服器) 角色的關聯性，請參閱規劃檔中的 [Lync server 2013 中的參考拓撲](lync-server-2013-reference-topologies.md) 。</span><span class="sxs-lookup"><span data-stu-id="3ef13-114">To view reference topologies with examples of where Enterprise Voice server roles can be deployed (and their relationship to one another and other Lync Server 2013 server roles), see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span>

<span data-ttu-id="3ef13-115">若要查看說明及說明範例通話許可控制部署（包括網路地區、網路網站及子網）的參考拓撲，請參閱規劃檔中的 [範例：在 Lync Server 2013 中收集通話許可控制需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 。</span><span class="sxs-lookup"><span data-stu-id="3ef13-115">To view a reference topology that illustrates and explains a sample call admission control deployment, including network regions, network sites, and subnets, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3ef13-116">若要在中央網站部署企業語音，請繼續閱讀本節中的主題。</span><span class="sxs-lookup"><span data-stu-id="3ef13-116">To deploy Enterprise Voice at a central site, continue reading the topics in this section.</span></span> <span data-ttu-id="3ef13-117">若要在分支網站部署企業語音，請跳過部署檔中的 <A href="lync-server-2013-deploying-branch-sites.md">Lync Server 2013 中的部署分支網站</A> 。</span><span class="sxs-lookup"><span data-stu-id="3ef13-117">To deploy Enterprise Voice at a branch site, skip to <A href="lync-server-2013-deploying-branch-sites.md">Deploying branch sites in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="3ef13-118">本節包含在每一部前端伺服器或 Standard Edition server 上組合轉送伺服器的部署程式，如建議，也適用于具備獨立轉送伺服器集區的部署。</span><span class="sxs-lookup"><span data-stu-id="3ef13-118">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="3ef13-119">如果您使用拓撲產生器來定義及發行每一部前端伺服器或 Standard Edition server 上的轉送伺服器的拓撲，您可以略過下列內容，因為當您為前端伺服器集區或 Standard Edition server 安裝檔時，部署嚮導已自動安裝轉送伺服器的檔案：</span><span class="sxs-lookup"><span data-stu-id="3ef13-119">You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>

  - [<span data-ttu-id="3ef13-120">在 Lync Server 2013 中設定主幹</span><span class="sxs-lookup"><span data-stu-id="3ef13-120">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

<span data-ttu-id="3ef13-121">如果您使用拓撲產生器來定義及發行獨立集區中的轉送伺服器，您可以使用下列內容：</span><span class="sxs-lookup"><span data-stu-id="3ef13-121">If you used Topology Builder to define and publish a Mediation Server in a stand-alone pool, you can use the following content:</span></span>

  - <span data-ttu-id="3ef13-122">請確認您的拓撲符合軟體和環境必要條件（如 [Lync Server 2013 的 Enterprise Voice 必要條件](lync-server-2013-enterprise-voice-prerequisites.md)所述）。</span><span class="sxs-lookup"><span data-stu-id="3ef13-122">Verify that your topology meets the software and environment prerequisites, as described in [Enterprise Voice prerequisites for Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3ef13-123">本章節內容</span><span class="sxs-lookup"><span data-stu-id="3ef13-123">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="3ef13-124">Lync Server 2013 的 Enterprise Voice 必要條件</span><span class="sxs-lookup"><span data-stu-id="3ef13-124">Enterprise Voice prerequisites for Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [<span data-ttu-id="3ef13-125">在 Lync Server 2013 中部署轉送伺服器及定義對等專案</span><span class="sxs-lookup"><span data-stu-id="3ef13-125">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [<span data-ttu-id="3ef13-126">在 Lync Server 2013 中設定主幹</span><span class="sxs-lookup"><span data-stu-id="3ef13-126">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [<span data-ttu-id="3ef13-127">在 Lync Server 2013 中設定撥號對應表</span><span class="sxs-lookup"><span data-stu-id="3ef13-127">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [<span data-ttu-id="3ef13-128">在 Lync Server 2013 中設定語音原則、PSTN 使用方式記錄和語音路由</span><span class="sxs-lookup"><span data-stu-id="3ef13-128">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [<span data-ttu-id="3ef13-129">在 Lync Server 2013 中匯出及匯入語音路由設定</span><span class="sxs-lookup"><span data-stu-id="3ef13-129">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="3ef13-130">在 Lync Server 2013 中測試語音路由</span><span class="sxs-lookup"><span data-stu-id="3ef13-130">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [<span data-ttu-id="3ef13-131">在 Lync Server 2013 中將擱置的變更發佈至語音路由設定</span><span class="sxs-lookup"><span data-stu-id="3ef13-131">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="3ef13-132">部署內部部署 Exchange UM 以提供 Lync Server 2013 語音信箱</span><span class="sxs-lookup"><span data-stu-id="3ef13-132">Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail</span></span>](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [<span data-ttu-id="3ef13-133">在主控 Exchange UM 上提供 Lync Server 2013 使用者語音信箱</span><span class="sxs-lookup"><span data-stu-id="3ef13-133">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [<span data-ttu-id="3ef13-134">設定內部部署 Lync Server 2013 與 Exchange Online 整合</span><span class="sxs-lookup"><span data-stu-id="3ef13-134">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [<span data-ttu-id="3ef13-135">在 Lync Server 2013 中部署高級 Enterprise Voice 功能</span><span class="sxs-lookup"><span data-stu-id="3ef13-135">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [<span data-ttu-id="3ef13-136">關於 Lync Server 2013 中的網路地區、網站和子網</span><span class="sxs-lookup"><span data-stu-id="3ef13-136">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [<span data-ttu-id="3ef13-137">在 Lync Server 2013 中建立或修改網路地區</span><span class="sxs-lookup"><span data-stu-id="3ef13-137">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [<span data-ttu-id="3ef13-138">在 Lync Server 2013 中建立或修改網路網站</span><span class="sxs-lookup"><span data-stu-id="3ef13-138">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [<span data-ttu-id="3ef13-139">在 Lync Server 2013 中建立子網與網路網站的關聯</span><span class="sxs-lookup"><span data-stu-id="3ef13-139">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [<span data-ttu-id="3ef13-140">在 Lync Server 2013 中設定通話許可控制</span><span class="sxs-lookup"><span data-stu-id="3ef13-140">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)
    
      - [<span data-ttu-id="3ef13-141">在 Lync Server 2013 中設定增強型9-1-1</span><span class="sxs-lookup"><span data-stu-id="3ef13-141">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [<span data-ttu-id="3ef13-142">在 Lync Server 2013 中設定媒體旁路</span><span class="sxs-lookup"><span data-stu-id="3ef13-142">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [<span data-ttu-id="3ef13-143">在 Lync Server 2013 中啟用使用者的 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="3ef13-143">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3ef13-144">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3ef13-144">See Also</span></span>


[<span data-ttu-id="3ef13-145">在 Lync Server 2013 中部署分支網站</span><span class="sxs-lookup"><span data-stu-id="3ef13-145">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)  
[<span data-ttu-id="3ef13-146">在 Lync Server 2013 中設定電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="3ef13-146">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)  
[<span data-ttu-id="3ef13-147">在 Lync Server 2013 中設定通話駐留</span><span class="sxs-lookup"><span data-stu-id="3ef13-147">Configuring Call Park in Lync Server 2013</span></span>](lync-server-2013-configuring-call-park.md)  
[<span data-ttu-id="3ef13-148">在 Lync Server 2013 中設定未指派號碼的宣告</span><span class="sxs-lookup"><span data-stu-id="3ef13-148">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[<span data-ttu-id="3ef13-149">在 Lync Server 2013 中部署監控</span><span class="sxs-lookup"><span data-stu-id="3ef13-149">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

