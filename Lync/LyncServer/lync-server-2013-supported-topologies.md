---
title: Lync Server 2013 支援的拓撲
description: Lync Server 2013 支援的拓撲。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39c19577fbda7e377e145abfd473d2cf8e6d4a1a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558019"
---
# <a name="supported-topologies-in-lync-server-2013"></a><span data-ttu-id="94fe7-103">Lync Server 2013 中支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="94fe7-103">Supported topologies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94fe7-104">_**主題上次修改日期：** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="94fe7-104">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="94fe7-105">Lync Server 2013 支援在組織內部部署網站，並整合內部部署與 Lync Online 部署（稱為「混合部署」）。</span><span class="sxs-lookup"><span data-stu-id="94fe7-105">Lync Server 2013 supports deployment of sites on premises in an organization and integration of on-premises deployments with Lync Online deployments, which is known as a hybrid deployment.</span></span> <span data-ttu-id="94fe7-106">在混合部署中，一些使用者會位於內部部署，而一些使用者會位於線上。</span><span class="sxs-lookup"><span data-stu-id="94fe7-106">In a hybrid deployment, some users are homed on-premises and some users are homed online.</span></span>

<span data-ttu-id="94fe7-107">若為內部部署，Lync Server 2013 可支援部署一或多個網站，以符合高可用性和位置需求。</span><span class="sxs-lookup"><span data-stu-id="94fe7-107">For on-premises deployments, Lync Server 2013 supports deployment of one or more sites that can be scaled to meet high availability and location requirements.</span></span> <span data-ttu-id="94fe7-108">您可以建構這些站台及其元件，以達到組織在存取與恢復能力方面的需求。</span><span class="sxs-lookup"><span data-stu-id="94fe7-108">You can structure these sites and their components to meet the access and resiliency requirements of your organization.</span></span>

<span data-ttu-id="94fe7-109">Lync Server 2013 內部部署是由下列專案所組成：</span><span class="sxs-lookup"><span data-stu-id="94fe7-109">A Lync Server 2013 on-premises deployment consists of the following:</span></span>

  - <span data-ttu-id="94fe7-p103">部署中至少要有一個中央站台 (也稱為資料中心)。每個中央站台都至少要有一個 Enterprise Edition 前端集區或一部 Standard Edition Server。這些項目包含：</span><span class="sxs-lookup"><span data-stu-id="94fe7-p103">Your deployment must include at least one central site (also known as a data center). Each central site must contain at least one Enterprise Edition Front End pool or one Standard Edition server. These consist of the following:</span></span>
    
      - <span data-ttu-id="94fe7-113">Enterprise Edition 前端集區，由一或多部前端伺服器 (通常至少兩部前端伺服器，以維持延展性) 與一部個別的後端伺服器所組成。</span><span class="sxs-lookup"><span data-stu-id="94fe7-113">Enterprise Edition Front End pool, which consists of one or more Front End Servers (typically, at least two Front End Servers for scalability) and a separate Back End Server.</span></span> <span data-ttu-id="94fe7-114">前端集區最多可包含十二部前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="94fe7-114">A Front End pool can contain a maximum of twelve Front End Servers.</span></span> <span data-ttu-id="94fe7-115">多部前端伺服器間必須使用負載平衡。</span><span class="sxs-lookup"><span data-stu-id="94fe7-115">Load balancing is required for multiple Front End Servers.</span></span> <span data-ttu-id="94fe7-116">針對 SIP 流量，建議您使用 DNS 負載平衡，但也支援硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="94fe7-116">For SIP traffic, we recommend DNS load balancing, but hardware load balancing is also supported.</span></span> <span data-ttu-id="94fe7-117">如果您對 SIP 流量使用 DNS 負載平衡，您仍需要適用於 HTTP 流量的硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="94fe7-117">If you use DNS load balancing for SIP traffic, you still need a hardware load balancer for HTTP traffic.</span></span> <span data-ttu-id="94fe7-118">建議資料庫的高可用性的 SQL Server 鏡像。</span><span class="sxs-lookup"><span data-stu-id="94fe7-118">We recommend SQL Server mirroring for high availability of databases.</span></span> <span data-ttu-id="94fe7-119">後端資料庫必須要有個別的執行個體，但您可以將封存資料庫、監控資料庫、常設聊天室資料庫，以及常設聊天室規範資料庫與其組合。</span><span class="sxs-lookup"><span data-stu-id="94fe7-119">The back-end database requires a separate instance, but you can collocate the archiving database, monitoring database, persistent chat database, and persistent chat compliance database with it.</span></span> <span data-ttu-id="94fe7-120">Lync Server 2013 支援對部署中的檔案共用使用共用叢集。</span><span class="sxs-lookup"><span data-stu-id="94fe7-120">Lync Server 2013 supports the use of a shared cluster for the file shares in your deployment.</span></span> <span data-ttu-id="94fe7-121">如需資料庫儲存需求的詳細資訊，請參閱 [Lync Server 2013 中的資料庫軟體支援](lync-server-2013-database-software-support.md)。</span><span class="sxs-lookup"><span data-stu-id="94fe7-121">For details about database storage requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="94fe7-122">如需檔案儲存需求的詳細資訊，請參閱 [Lync Server 2013 中的檔案儲存支援](lync-server-2013-file-storage-support.md)。</span><span class="sxs-lookup"><span data-stu-id="94fe7-122">For details about file storage requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="94fe7-123">如果您組合 Lync Server 資料庫，強烈建議評估可能影響可用性及效能的所有因素。</span><span class="sxs-lookup"><span data-stu-id="94fe7-123">If you collocate Lync Server databases, we highly recommend assessing all factors that might affect availability and performance.</span></span> <span data-ttu-id="94fe7-124">若要確認容錯移轉功能，建議您測試所有容錯移轉狀況。</span><span class="sxs-lookup"><span data-stu-id="94fe7-124">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>

        
        </div>
    
      - <span data-ttu-id="94fe7-125">Standard Edition Server，其中包含組合的 SQL Server Express 資料庫。</span><span class="sxs-lookup"><span data-stu-id="94fe7-125">Standard Edition server, which includes a collocated SQL Server Express database.</span></span>

  - <span data-ttu-id="94fe7-126">部署中也可以有一或多個與中央網站相關聯的分支網站。</span><span class="sxs-lookup"><span data-stu-id="94fe7-126">Your deployment can also have one or more branch sites associated with a central site.</span></span>

<span data-ttu-id="94fe7-127">本節說明 Lync Server 2013 部署的網站和元件。</span><span class="sxs-lookup"><span data-stu-id="94fe7-127">This section describes the sites and components of a Lync Server 2013 deployment.</span></span> <span data-ttu-id="94fe7-128">如需 Lync Server 2013 網站、拓撲及元件規劃的詳細資訊，請參閱規劃檔中的 lync server 2013 和[Lync server 2013](lync-server-2013-reference-topologies.md)中[規劃 lync Server 及參考拓撲之前，必須先知道的拓撲基本知識](lync-server-2013-topology-basics-you-must-know-before-planning.md)。</span><span class="sxs-lookup"><span data-stu-id="94fe7-128">For details about Lync Server 2013 site, topology, and component planning, see [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) and [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="94fe7-129">如需與舊版元件整合相關的詳細資訊，請參閱 [Lync Server 2013 中支援的遷移路徑和共存案例](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md)。</span><span class="sxs-lookup"><span data-stu-id="94fe7-129">For details about integration of components of previous releases, see [Supported migration paths and coexistence scenarios in Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="94fe7-130">「前端」、「Edge」、「中繼」和「Director」伺服器角色都不支援延伸集區。</span><span class="sxs-lookup"><span data-stu-id="94fe7-130">Stretched pools are not supported for the Front End, Edge, Mediation, and Director server roles.</span></span>



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a><span data-ttu-id="94fe7-131">中央站台的拓撲與元件 (內部部署)</span><span class="sxs-lookup"><span data-stu-id="94fe7-131">Central Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="94fe7-132">雖然中央站台拓撲必須包含一個前端集區或一部 Standard Edition Server，但各個中央站台也可包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="94fe7-132">Although a central site topology must include one Front End pool or one Standard Edition server, each central site can also contain the following:</span></span>

  - <span data-ttu-id="94fe7-p107">多個前端集區，可位於相同或不同的網域。但是，前端集區中的所有前端伺服器與該集區的後端伺服器必須位於相同網域。</span><span class="sxs-lookup"><span data-stu-id="94fe7-p107">Multiple Front End pools, which can be in the same domain or different domains. However, all Front End Servers in a Front End pool, and the Back End Server for that pool, must be in the same domain.</span></span>

  - <span data-ttu-id="94fe7-135">多部 Standard Edition Server。</span><span class="sxs-lookup"><span data-stu-id="94fe7-135">Multiple Standard Edition servers.</span></span>

  - <span data-ttu-id="94fe7-136">Office Web Apps Server，可與 Lync Server 2013 中的 Office Web 應用程式搭配使用，以處理 Microsoft PowerPoint 簡報的共用及呈現。</span><span class="sxs-lookup"><span data-stu-id="94fe7-136">Office Web Apps Server, which is used with Office Web Applications in Lync Server 2013 to handle the sharing and rendering of Microsoft PowerPoint presentations.</span></span>

  - <span data-ttu-id="94fe7-137">Edge Server 或 Edge 集區在周邊網路中，如果您想要部署支援同盟協力廠商、公用 IM 連線、可延伸的訊息和顯示狀態通訊協定 (XMPP) 閘道、遠端使用者存取、匿名使用者加入會議或 Exchange 整合通訊 (UM) 。</span><span class="sxs-lookup"><span data-stu-id="94fe7-137">Edge Server or Edge pool in your perimeter network, if you want your deployment to support federated partners, public IM connectivity, an extensible messaging and presence protocol (XMPP) gateway, remote user access, participation of anonymous users in meetings, or Exchange Unified Messaging (UM).</span></span> <span data-ttu-id="94fe7-138">Edge Server 不可與任何其他伺服器角色組合。</span><span class="sxs-lookup"><span data-stu-id="94fe7-138">You cannot collocate any other server role with an Edge Server.</span></span> <span data-ttu-id="94fe7-139">建議在情況允許時使用 DNS 負載平衡，但也支援硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="94fe7-139">We recommend DNS load balancing, where appropriate, but hardware load balancing is also supported.</span></span> <span data-ttu-id="94fe7-140">內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。</span><span class="sxs-lookup"><span data-stu-id="94fe7-140">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="94fe7-141">您不能在一個 Edge 介面上使用 DNS 負載平衡，而在另一個 Edge 介面上使用硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="94fe7-141">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span> <span data-ttu-id="94fe7-142">如需負載平衡需求和支援的詳細資訊，請參閱部署檔中的規劃檔和[部署外部使用者2013存取](lync-server-2013-deploying-external-user-access.md)中的 [在 lync server [2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)]。</span><span class="sxs-lookup"><span data-stu-id="94fe7-142">For details about load balancing requirements and support, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="94fe7-143">轉送伺服器或集區，如果您想要在中央網站的前端集區中支援 Enterprise Voice 或電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="94fe7-143">Mediation Server or pool, if you want to support Enterprise Voice or dial-in conferencing in a Front End pool at the central site.</span></span> <span data-ttu-id="94fe7-144">根據您部署企業語音支援的方式，您可以在 (預設) 或部署獨立轉送伺服器或集區的前端集區中組合轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="94fe7-144">Depending on how you deploy Enterprise Voice support, you can collocate the Mediation Server in a Front End pool (the default) or deploy a stand-alone Mediation Server or pool.</span></span> <span data-ttu-id="94fe7-145">當適當) 從轉送伺服器集區的閘道對等發佈流量（包括 PSTN 閘道、IP-PBX 或 SIP 主幹會話邊界 (SBC) ）時，您可以使用 DNS、硬體或應用程式負載平衡 (。如需規劃適當轉送伺服器拓撲的詳細資訊，請參閱規劃檔中的 [Lync server 2013 中的轉送伺服器部署指導方針](lync-server-2013-deployment-guidelines-for-mediation-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="94fe7-145">You can use DNS, hardware, or application load balancing (when appropriate) to distribute traffic from a Mediation Server pool’s gateway peer, including a PSTN gateway, IP-PBX, or SIP trunk Session Border Control (SBC).For details about planning the appropriate Mediation Server topology, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="94fe7-146">Persistent Chat Server，如果您想要讓使用者能夠參與多方，以主題為基礎的交談會隨著時間而保留。</span><span class="sxs-lookup"><span data-stu-id="94fe7-146">Persistent Chat Server, if you want to users to be able to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="94fe7-147">若要提供更多的容量及增強的可靠性，您的拓撲可包含多部執行 Persistent Chat Server 的電腦。</span><span class="sxs-lookup"><span data-stu-id="94fe7-147">To provide more capacity and increased reliability, your topology can include multiple computers running Persistent Chat Server.</span></span> <span data-ttu-id="94fe7-148">您無法組合 Persistent Chat Server 與企業版集區中的其他伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="94fe7-148">You cannot collocate Persistent Chat Server with other server roles in an Enterprise pool.</span></span> <span data-ttu-id="94fe7-149">不過，您可以在 Standard Edition server 上組合 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="94fe7-149">However, you can collocate Persistent Chat Server on a Standard Edition server.</span></span> <span data-ttu-id="94fe7-150">常設聊天室需要一個資料庫，而且，如果您實作常設聊天室規範，則需要常設聊天室規範資料庫，但是資料庫可與封存資料庫或監控資料庫組合，或者在 Enterprise Edition 前端集區的後端伺服器上組合。</span><span class="sxs-lookup"><span data-stu-id="94fe7-150">Persistent chat requires a database and, if you implement persistent chat compliance, a persistent chat compliance database, but the databases can be collocated with the Archiving database, Monitoring database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="94fe7-151">如需規劃適當之持久聊天伺服器拓撲的詳細資訊，請參閱規劃檔中的在 [Lync server 2013 中規劃 Persistent Chat Server](lync-server-2013-planning-for-persistent-chat-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="94fe7-151">For details about planning the appropriate Persistent Chat Server topology, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="94fe7-152">監控 (如果您要在部署中支援音訊/視訊經驗品質 (QoE) 的資料收集以及企業語音與 A/V 會議的詳細通話記錄 (CDR))。</span><span class="sxs-lookup"><span data-stu-id="94fe7-152">Monitoring, if you want to support data collection for audio/video Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="94fe7-153">您也可以選擇安裝 Microsoft System Center Operations Manager (過去的 Microsoft Operations Manager) ，它會使用監控 CDR 和 QoE 資料來產生接近即時的警報，以顯示通話可靠性和媒體質量的健康情況。</span><span class="sxs-lookup"><span data-stu-id="94fe7-153">Optionally, you can install the Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which uses Monitoring CDR and QoE data to generate near real-time alerts that show the health of call reliability and media quality.</span></span> <span data-ttu-id="94fe7-154">在部署時，監控可與前端伺服器或 Standard Edition Server 組合。</span><span class="sxs-lookup"><span data-stu-id="94fe7-154">Monitoring, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="94fe7-155">監控必須要有資料庫，但此資料庫可與封存伺服器、常設聊天室資料庫、常設聊天室規範資料庫或 Enterprise Edition 前端集區的後端伺服器組合。</span><span class="sxs-lookup"><span data-stu-id="94fe7-155">Monitoring requires a database, but the database can be collocated with the Archiving database, persistent chat database, persistent chat compliance database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span>

  - <span data-ttu-id="94fe7-156">封存 (如果您基於規範而要在部署中封存 IM 通訊與會議內容)。</span><span class="sxs-lookup"><span data-stu-id="94fe7-156">Archiving, if you want to archive IM communications and meeting content (for compliance reasons) in your deployment.</span></span> <span data-ttu-id="94fe7-157">在部署時，封存可與前端伺服器或 Standard Edition Server 組合。</span><span class="sxs-lookup"><span data-stu-id="94fe7-157">Archiving, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="94fe7-158">封存儲存需要部署封存資料庫或與 Exchange 2013 儲存體整合。</span><span class="sxs-lookup"><span data-stu-id="94fe7-158">Archiving storage requires either deployment of an Archiving database or integration with Exchange 2013 storage.</span></span> <span data-ttu-id="94fe7-159">如果您同時使用這兩種模式，又稱為 *混合模式*，exchange 2013 儲存區是用來儲存位於 Exchange 2013 上之使用者的封存資料，而封存資料庫是用來封存部署中所有其他使用者的資料。</span><span class="sxs-lookup"><span data-stu-id="94fe7-159">If you use both, which is known as *mixed mode*, Exchange 2013 storage is used to store archive data for users who are homed on Exchange 2013, and the Archiving database is used to archive data for all other users in your deployment.</span></span> <span data-ttu-id="94fe7-160">如果您需要封存資料庫，該資料庫可以在監控資料庫、常設聊天室資料庫、常設聊天室規範資料庫或前端集區的後端伺服器上組合。</span><span class="sxs-lookup"><span data-stu-id="94fe7-160">If you require an Archiving database, the database can be collocated on the Monitoring database, persistent chat database, persistent chat compliance database, or on the Back End Server of a Front End pool.</span></span> <span data-ttu-id="94fe7-161">如需規劃適當封存拓撲的詳細資訊，請參閱規劃檔中的 [規劃在 Lync Server 2013 中的](lync-server-2013-planning-for-archiving.md) 封存。</span><span class="sxs-lookup"><span data-stu-id="94fe7-161">For details about planning the appropriate Archiving topology, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="94fe7-162">Director 或 Director 集區，如果您想要對使用者的主集區（可以是 Enterprise Edition 前端集區或 Standard Edition Server）進行恢復與重新導向，以進行 Lync Server 2013 使用者要求的恢復與重新導向。</span><span class="sxs-lookup"><span data-stu-id="94fe7-162">Director or Director pool, if you want to facilitate resiliency and redirection of Lync Server 2013 user requests to the user’s home pool, which can be either an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="94fe7-163">建議您在每個支援外部使用者存取的中央站台以及每個部署一或多個前端集區的中央站台上，部署 Director 或 Director 集區。</span><span class="sxs-lookup"><span data-stu-id="94fe7-163">We recommend that you deploy a Director or Director pool in each central site that supports external user access and in each central site in which you deploy one or more Front End pools.</span></span> <span data-ttu-id="94fe7-164">每個 Director 集區最多可包含十個 Director。</span><span class="sxs-lookup"><span data-stu-id="94fe7-164">Each Director pool can contain a maximum of ten Directors.</span></span> <span data-ttu-id="94fe7-165">Director 不可與任何其他伺服器角色組合。</span><span class="sxs-lookup"><span data-stu-id="94fe7-165">A Director cannot be collocated with any other server role.</span></span> <span data-ttu-id="94fe7-166">如需規劃適當 Director 拓撲的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的 Director 案例](lync-server-2013-scenarios-for-the-director.md) 。</span><span class="sxs-lookup"><span data-stu-id="94fe7-166">For details about planning the appropriate Director topology, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="94fe7-167">反向 proxy （不是 Lync Server 2013 元件），但是如果您想要支援同盟使用者的 web 內容共用或支援行動性流量，則需要。</span><span class="sxs-lookup"><span data-stu-id="94fe7-167">Reverse proxy, which is not a Lync Server 2013 component, but is required if you want to support sharing of web content for federated users or to support Mobility traffic.</span></span> <span data-ttu-id="94fe7-168">您無法使用任何 Lync Server 2013 伺服器角色組合反向 proxy 伺服器，但您可以在組織中對其他應用程式使用的現有反向 proxy 伺服器上設定支援，以執行 Lync Server 2013 部署的反向 proxy 支援。</span><span class="sxs-lookup"><span data-stu-id="94fe7-168">You cannot collocate a reverse proxy server with any Lync Server 2013 server role, but you can implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span> <span data-ttu-id="94fe7-169">如需反向 proxy 伺服器的詳細資訊，請參閱部署檔中的 [設定 Lync Server 2013 的反向 proxy 伺服器](lync-server-2013-setting-up-reverse-proxy-servers.md) 。</span><span class="sxs-lookup"><span data-stu-id="94fe7-169">For details about reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="94fe7-170">在 Lync Server 2013 中，A/V 的會議、監控和封存都是在前端伺服器上執行，而且不再是個別的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="94fe7-170">In Lync Server 2013, A/V Conferencing, Monitoring, and Archiving run on Front End Servers and are no longer separate server roles.</span></span>



</div>

<span data-ttu-id="94fe7-171">您在中央網站上部署的所有前端集區與 Standard Edition Server，將會共用您為中央網站所部署的下列各項：</span><span class="sxs-lookup"><span data-stu-id="94fe7-171">All Front End pools and Standard Edition servers that you deploy at a central site share any of the following that you deploy for the central site:</span></span>

  - <span data-ttu-id="94fe7-172">Director 或 Director 集區</span><span class="sxs-lookup"><span data-stu-id="94fe7-172">Director or Director pool</span></span>

  - <span data-ttu-id="94fe7-173">獨立式中繼伺服器或集區</span><span class="sxs-lookup"><span data-stu-id="94fe7-173">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="94fe7-174">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="94fe7-174">Office Web Apps Server</span></span>

  - <span data-ttu-id="94fe7-175">Edge Server 或 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="94fe7-175">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="94fe7-176">常設聊天室伺服器或集區</span><span class="sxs-lookup"><span data-stu-id="94fe7-176">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="94fe7-177">監視</span><span class="sxs-lookup"><span data-stu-id="94fe7-177">Monitoring</span></span>

  - <span data-ttu-id="94fe7-178">封存</span><span class="sxs-lookup"><span data-stu-id="94fe7-178">Archiving</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="94fe7-179">如果您想要支援 Exchange 2013 整合通訊的整合，但它不是 Lync Server 2013 網站的元件，則可以在您的 Lync Server 2013 部署中實施 Exchange UM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="94fe7-179">An Exchange UM Server can be implemented with your Lync Server 2013 deployment if you want to support integration of Exchange 2013 Unified Messaging, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="94fe7-180">多個中央網站也可共用您在某個中央網站上部署的下列任何項目：</span><span class="sxs-lookup"><span data-stu-id="94fe7-180">Multiple central sites can also share any of the following that you deploy in one central site:</span></span>

  - <span data-ttu-id="94fe7-181">獨立式中繼伺服器或集區</span><span class="sxs-lookup"><span data-stu-id="94fe7-181">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="94fe7-182">Edge Server 或 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="94fe7-182">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="94fe7-183">常設聊天室伺服器或集區</span><span class="sxs-lookup"><span data-stu-id="94fe7-183">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="94fe7-184">封存</span><span class="sxs-lookup"><span data-stu-id="94fe7-184">Archiving</span></span>

  - <span data-ttu-id="94fe7-185">監視</span><span class="sxs-lookup"><span data-stu-id="94fe7-185">Monitoring</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="94fe7-186">Exchange UM 伺服器可與您的 Lync Server 2013 部署搭配執行，並由多部中央網站共用，但它不是 Lync Server 2013 網站的元件。</span><span class="sxs-lookup"><span data-stu-id="94fe7-186">An Exchange UM Server can be implemented with your Lync Server 2013 deployment and shared by multiple central sites, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="94fe7-187">如需 Lync Server 2013 伺服器角色及功能的詳細資訊，請參閱規劃檔中的 [Lync server 2013 中的伺服器角色](lync-server-2013-server-roles.md) 。</span><span class="sxs-lookup"><span data-stu-id="94fe7-187">For details about Lync Server 2013 server roles and functionality, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md) in the Planning documentation.</span></span>

<span data-ttu-id="94fe7-188">如需 Lync Server 2013 Server 組合支援的摘要，請參閱 [Lync server 2013 中的支援伺服器組合](lync-server-2013-supported-server-collocation.md)。</span><span class="sxs-lookup"><span data-stu-id="94fe7-188">For a summary of Lync Server 2013 server collocation support, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<span data-ttu-id="94fe7-189">除了本節先前所涵蓋的伺服器角色和功能之外，Lync Server 2013 還有其他元件和選項，其中包括下列部分或所有專案：</span><span class="sxs-lookup"><span data-stu-id="94fe7-189">In addition to the server roles and functionality covered previously in this section, Lync Server 2013 has additional components and options, which can include some or all of the following:</span></span>

  - <span data-ttu-id="94fe7-190">防火牆</span><span class="sxs-lookup"><span data-stu-id="94fe7-190">Firewalls</span></span>

  - <span data-ttu-id="94fe7-191">PSTN 閘道 (如果部署企業語音)</span><span class="sxs-lookup"><span data-stu-id="94fe7-191">PSTN gateways (if deploying Enterprise Voice)</span></span>

  - <span data-ttu-id="94fe7-192">Exchange UM 伺服器</span><span class="sxs-lookup"><span data-stu-id="94fe7-192">Exchange UM Server</span></span>

  - <span data-ttu-id="94fe7-193">DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="94fe7-193">DNS load balancing</span></span>

  - <span data-ttu-id="94fe7-194">硬體負載平衡器</span><span class="sxs-lookup"><span data-stu-id="94fe7-194">Hardware load balancers</span></span>

  - <span data-ttu-id="94fe7-195">SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="94fe7-195">SQL Server databases</span></span>

  - <span data-ttu-id="94fe7-196">檔案共用</span><span class="sxs-lookup"><span data-stu-id="94fe7-196">File shares</span></span>

<span data-ttu-id="94fe7-197">如需所有 Lync Server 2013 功能、元件及選項的詳細資訊，請參閱規劃檔。</span><span class="sxs-lookup"><span data-stu-id="94fe7-197">For details about all of the Lync Server 2013 features, components, and options, see the Planning documentation.</span></span>

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a><span data-ttu-id="94fe7-198">分支站台的拓撲與元件 (內部部署)</span><span class="sxs-lookup"><span data-stu-id="94fe7-198">Branch Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="94fe7-p115">分支站台會與中央站台相關聯，而且分支站台中的每個 Survivable Branch Appliance 都會與相關聯之中央站台上的一個 Enterprise Edition 前端集區或一部 Standard Edition Server 相關聯。分支站台大部分的功能皆依存於中央站台，因此分支站台上的元件僅包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="94fe7-p115">A branch site is associated with a central site, and each Survivable Branch Appliance in a branch site is associated with an Enterprise Edition Front End pool or a Standard Edition server in the associated central site. Branch sites depend on the central site for most of their functionality, so components at a branch site contain only the following:</span></span>

  - <span data-ttu-id="94fe7-201">Survivable 分支裝置，將公用交換電話網路 (PSTN) 閘道與某些 Lync Server 功能結合在一起。</span><span class="sxs-lookup"><span data-stu-id="94fe7-201">A Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway with some Lync Server functionality.</span></span> <span data-ttu-id="94fe7-202">您可以使用 Survivable Branch 裝置上的註冊機構實例來組合轉送伺服器，也可以部署一部獨立的轉送伺服器或轉送伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="94fe7-202">A Mediation Server can be collocated with the instance of the Registrar on the Survivable Branch Appliance, and you can deploy a stand-alone Mediation Server or pool of Mediation Servers.</span></span>

  - <span data-ttu-id="94fe7-203">Survivable 分支伺服器，這是執行 Windows Server 且已安裝 Lync Server 2013 註冊機構和轉送伺服器軟體的伺服器。</span><span class="sxs-lookup"><span data-stu-id="94fe7-203">A Survivable Branch Server, which is a server running Windows Server that has Lync Server 2013 Registrar and Mediation Server software installed.</span></span>

  - <span data-ttu-id="94fe7-204">獨立式 PSTN 閘道 (不是 Survivable Branch Appliance 的一部分) 與獨立式中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="94fe7-204">A stand-alone PSTN gateway (not part of the Survivable Branch Appliance) and a stand-alone Mediation Server.</span></span>

<span data-ttu-id="94fe7-205">Survivable 分支伺服器的需求與任何 Lync Server 2013 伺服器角色的需求相同。</span><span class="sxs-lookup"><span data-stu-id="94fe7-205">The requirements for Survivable Branch Servers are the same as the requirements for any Lync Server 2013 server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

