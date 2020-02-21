---
title: Lync Server 2013： 部署 Enterprise Voice
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
ms.openlocfilehash: 5a19016a095e38a0df70a561976c6b03d59fdfd1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="1882f-102">部署 Lync Server 2013 中的 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="1882f-102">Deploying Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1882f-103">_**主題上次修改日期：** 2012年-10-03_</span><span class="sxs-lookup"><span data-stu-id="1882f-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="1882f-104">Lync Server 2013、 Enterprise Voice 為 Lync Server 2013 基礎結構的一部分。</span><span class="sxs-lookup"><span data-stu-id="1882f-104">Lync Server 2013, Enterprise Voice is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="1882f-105">部署 Enterprise Voice 需要您：</span><span class="sxs-lookup"><span data-stu-id="1882f-105">Deploying Enterprise Voice requires that you:</span></span>

<div id="sectionSection0" class="section">

1.  <span data-ttu-id="1882f-106">請先檢閱[Planning for Lync Server 2013 中的企業語音](lync-server-2013-planning-for-enterprise-voice.md)] 區段中的規劃文件。</span><span class="sxs-lookup"><span data-stu-id="1882f-106">Review the [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) section of the Planning documentation.</span></span>

2.  <span data-ttu-id="1882f-107">完成功能與元件的計劃，使用此工作負載來部署。</span><span class="sxs-lookup"><span data-stu-id="1882f-107">Finalize plans for features and components to deploy with this workload.</span></span>

3.  <span data-ttu-id="1882f-108">執行規劃工具設計拓撲，以反映您的部署決策。</span><span class="sxs-lookup"><span data-stu-id="1882f-108">Run Planning Tool to design a topology that reflects your deployment decisions.</span></span>

4.  <span data-ttu-id="1882f-109">中所述[定義和設定 Lync Server 2013 中的拓撲](lync-server-2013-defining-and-configuring-the-topology.md)中部署文件，請在拓撲產生器] 中開啟拓撲設計。</span><span class="sxs-lookup"><span data-stu-id="1882f-109">Open the topology design in Topology Builder, as described in [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1882f-110">安裝拓撲產生器是內部集區的部署程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="1882f-110">Installation of Topology Builder is part of the deployment process for the internal pool.</span></span> <span data-ttu-id="1882f-111">如需詳細資訊，請參閱部署文件中的<A href="lync-server-2013-install-lync-server-administrative-tools.md">安裝 Lync Server 2013 系統管理工具</A>。</span><span class="sxs-lookup"><span data-stu-id="1882f-111">For details, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="1882f-112">此外，您必須已部署 Lync Server，Enterprise Edition，中央站台和對應至您選擇要部署的參考拓撲的分支網站。</span><span class="sxs-lookup"><span data-stu-id="1882f-112">Additionally, you must have already deployed Lync Server, Enterprise Edition at central sites and branch sites that correspond to the reference topology that you choose to deploy.</span></span> <span data-ttu-id="1882f-113">您無法部署企業語音元件，直到您已定義、 發行及安裝檔案來至少一個內部集區，您必須使用拓撲產生器來定義和發佈的內部集區。</span><span class="sxs-lookup"><span data-stu-id="1882f-113">You can’t deploy Enterprise Voice components until you have defined, published, and installed files for at least one internal pool, and you must use Topology Builder to define and publish an internal pool.</span></span>

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

<span data-ttu-id="1882f-114">若要檢視部署企業語音的伺服器角色的位置 （和其關係到另一個和其他 Lync Server 2013 伺服器角色） 的範例與參考拓撲，請參閱規劃文件中的[Lync Server 2013 中的參考拓撲](lync-server-2013-reference-topologies.md)。</span><span class="sxs-lookup"><span data-stu-id="1882f-114">To view reference topologies with examples of where Enterprise Voice server roles can be deployed (and their relationship to one another and other Lync Server 2013 server roles), see [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span>

<span data-ttu-id="1882f-115">若要檢視的參考拓撲顯示及說明範例通話許可控制部署，包括網路地區、 網站及網路子網路，請參閱[範例： 收集您的 Lync Server 2013 中的通話許可控制需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)中規劃文件。</span><span class="sxs-lookup"><span data-stu-id="1882f-115">To view a reference topology that illustrates and explains a sample call admission control deployment, including network regions, network sites, and subnets, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1882f-116">若要部署 Enterprise Voice 在中央網站，請繼續閱讀本章節中的主題。</span><span class="sxs-lookup"><span data-stu-id="1882f-116">To deploy Enterprise Voice at a central site, continue reading the topics in this section.</span></span> <span data-ttu-id="1882f-117">若要部署 Enterprise Voice 在分支網站，跳至<A href="lync-server-2013-deploying-branch-sites.md">Lync Server 2013 中部署分支網站</A>部署文件中。</span><span class="sxs-lookup"><span data-stu-id="1882f-117">To deploy Enterprise Voice at a branch site, skip to <A href="lync-server-2013-deploying-branch-sites.md">Deploying branch sites in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="1882f-118">本節包含部署程的序，在每部前端伺服器或 Standard Edition 伺服器上，此中繼伺服器已組合的建議，以及具有獨立的中繼伺服器集區的部署。</span><span class="sxs-lookup"><span data-stu-id="1882f-118">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="1882f-119">如果您使用拓撲產生器中定義並發行拓撲，配置中繼伺服器上每個前端伺服器或 Standard Edition 伺服器，因為部署精靈已自動安裝的檔案，您可以略過下列內容當您安裝適用於您的前端伺服器集區或 Standard Edition server 檔案的中繼伺服器：</span><span class="sxs-lookup"><span data-stu-id="1882f-119">You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>

  - [<span data-ttu-id="1882f-120">在 Lync Server 2013 中設定主幹</span><span class="sxs-lookup"><span data-stu-id="1882f-120">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

<span data-ttu-id="1882f-121">如果您使用拓撲產生器來定義和發佈中繼伺服器的獨立集區中，您可以使用下列內容：</span><span class="sxs-lookup"><span data-stu-id="1882f-121">If you used Topology Builder to define and publish a Mediation Server in a stand-alone pool, you can use the following content:</span></span>

  - <span data-ttu-id="1882f-122">確認您的拓撲符合軟體和環境先決條件，[針對 Lync Server 2013 Enterprise Voice 必要條件](lync-server-2013-enterprise-voice-prerequisites.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="1882f-122">Verify that your topology meets the software and environment prerequisites, as described in [Enterprise Voice prerequisites for Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1882f-123">本章節內容</span><span class="sxs-lookup"><span data-stu-id="1882f-123">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="1882f-124">Lync Server 2013 Enterprise Voice 先決條件</span><span class="sxs-lookup"><span data-stu-id="1882f-124">Enterprise Voice prerequisites for Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [<span data-ttu-id="1882f-125">部署中繼伺服器和 Lync Server 2013 中定義 peers</span><span class="sxs-lookup"><span data-stu-id="1882f-125">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [<span data-ttu-id="1882f-126">在 Lync Server 2013 中設定主幹</span><span class="sxs-lookup"><span data-stu-id="1882f-126">Configuring trunks in Lync Server 2013</span></span>](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [<span data-ttu-id="1882f-127">Lync Server 2013 中設定撥號對應表</span><span class="sxs-lookup"><span data-stu-id="1882f-127">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [<span data-ttu-id="1882f-128">在 Lync Server 2013 中設定語音原則、 PSTN 使用方式記錄和語音路由</span><span class="sxs-lookup"><span data-stu-id="1882f-128">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [<span data-ttu-id="1882f-129">匯出及匯入 Lync Server 2013 中的語音路由設定</span><span class="sxs-lookup"><span data-stu-id="1882f-129">Exporting and importing voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="1882f-130">測試 Lync Server 2013 中的語音路由</span><span class="sxs-lookup"><span data-stu-id="1882f-130">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [<span data-ttu-id="1882f-131">暫止的變更語音路由設定 Lync Server 2013 中發佈</span><span class="sxs-lookup"><span data-stu-id="1882f-131">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [<span data-ttu-id="1882f-132">部署內部部署 Exchange UM 以提供 Lync Server 2013 語音信箱</span><span class="sxs-lookup"><span data-stu-id="1882f-132">Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail</span></span>](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [<span data-ttu-id="1882f-133">提供 Lync Server 2013 使用者語音信箱上裝載的 Exchange UM</span><span class="sxs-lookup"><span data-stu-id="1882f-133">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [<span data-ttu-id="1882f-134">設定與 Exchange Online 內部部署 Lync Server 2013 整合</span><span class="sxs-lookup"><span data-stu-id="1882f-134">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [<span data-ttu-id="1882f-135">部署 Lync Server 2013 中的進階的 Enterprise Voice 功能</span><span class="sxs-lookup"><span data-stu-id="1882f-135">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [<span data-ttu-id="1882f-136">關於網路地區、 網站及 Lync Server 2013 中的子網路</span><span class="sxs-lookup"><span data-stu-id="1882f-136">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [<span data-ttu-id="1882f-137">建立或修改 Lync Server 2013 中的網路區域</span><span class="sxs-lookup"><span data-stu-id="1882f-137">Create or modify a network region in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [<span data-ttu-id="1882f-138">建立或修改 Lync Server 2013 中的網路網站</span><span class="sxs-lookup"><span data-stu-id="1882f-138">Create or modify a network site in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [<span data-ttu-id="1882f-139">關聯子網路與 Lync Server 2013 中的網路網站</span><span class="sxs-lookup"><span data-stu-id="1882f-139">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [<span data-ttu-id="1882f-140">在 Lync Server 2013 中設定通話許可控制</span><span class="sxs-lookup"><span data-stu-id="1882f-140">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)
    
      - [<span data-ttu-id="1882f-141">在 Lync Server 2013 中設定增強型的 9-1-1</span><span class="sxs-lookup"><span data-stu-id="1882f-141">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [<span data-ttu-id="1882f-142">在 Lync Server 2013 中設定媒體旁路</span><span class="sxs-lookup"><span data-stu-id="1882f-142">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [<span data-ttu-id="1882f-143">啟用使用者的 Lync Server 2013 中的 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="1882f-143">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1882f-144">另請參閱</span><span class="sxs-lookup"><span data-stu-id="1882f-144">See Also</span></span>


[<span data-ttu-id="1882f-145">部署 Lync Server 2013 中的分支網站</span><span class="sxs-lookup"><span data-stu-id="1882f-145">Deploying branch sites in Lync Server 2013</span></span>](lync-server-2013-deploying-branch-sites.md)  
[<span data-ttu-id="1882f-146">在 Lync Server 2013 中設定電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="1882f-146">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)  
[<span data-ttu-id="1882f-147">在 Lync Server 2013 中設定通話駐留</span><span class="sxs-lookup"><span data-stu-id="1882f-147">Configuring Call Park in Lync Server 2013</span></span>](lync-server-2013-configuring-call-park.md)  
[<span data-ttu-id="1882f-148">在 Lync Server 2013 中設定未指派號碼的宣告</span><span class="sxs-lookup"><span data-stu-id="1882f-148">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[<span data-ttu-id="1882f-149">部署 Lync Server 2013 中監視</span><span class="sxs-lookup"><span data-stu-id="1882f-149">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

