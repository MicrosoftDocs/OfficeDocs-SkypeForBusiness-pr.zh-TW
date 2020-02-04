---
title: Lync Server 2013 支援的拓撲
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
ms.openlocfilehash: 0f200cde348d1fbdc931daa25abef28aec804a1b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-topologies-in-lync-server-2013"></a><span data-ttu-id="9ebab-102">Lync Server 2013 中支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="9ebab-102">Supported topologies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ebab-103">_**主題上次修改日期：** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="9ebab-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="9ebab-104">Lync Server 2013 支援部署組織內部部署的網站，並與 Lync Online 部署（稱為混合式部署）整合內部部署部署。</span><span class="sxs-lookup"><span data-stu-id="9ebab-104">Lync Server 2013 supports deployment of sites on premises in an organization and integration of on-premises deployments with Lync Online deployments, which is known as a hybrid deployment.</span></span> <span data-ttu-id="9ebab-105">在混合式部署中，有些使用者是駐留在內部部署的，而某些使用者則是在線上。</span><span class="sxs-lookup"><span data-stu-id="9ebab-105">In a hybrid deployment, some users are homed on-premises and some users are homed online.</span></span>

<span data-ttu-id="9ebab-106">針對內部部署的部署，Lync Server 2013 支援部署一或多個可調整以滿足高可用性和位置需求的網站。</span><span class="sxs-lookup"><span data-stu-id="9ebab-106">For on-premises deployments, Lync Server 2013 supports deployment of one or more sites that can be scaled to meet high availability and location requirements.</span></span> <span data-ttu-id="9ebab-107">您可以建立這些網站及其元件的結構，以符合貴組織的存取和復原需求。</span><span class="sxs-lookup"><span data-stu-id="9ebab-107">You can structure these sites and their components to meet the access and resiliency requirements of your organization.</span></span>

<span data-ttu-id="9ebab-108">Lync Server 2013 內部部署部署包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="9ebab-108">A Lync Server 2013 on-premises deployment consists of the following:</span></span>

  - <span data-ttu-id="9ebab-109">您的部署必須包含至少一個中央網站（也稱為「資料中心」）。</span><span class="sxs-lookup"><span data-stu-id="9ebab-109">Your deployment must include at least one central site (also known as a data center).</span></span> <span data-ttu-id="9ebab-110">每個中央網站都必須包含至少一個企業版的前端池或一個標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="9ebab-110">Each central site must contain at least one Enterprise Edition Front End pool or one Standard Edition server.</span></span> <span data-ttu-id="9ebab-111">這些內容包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="9ebab-111">These consist of the following:</span></span>
    
      - <span data-ttu-id="9ebab-112">[企業版頂層端] 池，包含一或多個前端伺服器（通常是至少兩個可伸縮性的前端伺服器）和獨立的後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="9ebab-112">Enterprise Edition Front End pool, which consists of one or more Front End Servers (typically, at least two Front End Servers for scalability) and a separate Back End Server.</span></span> <span data-ttu-id="9ebab-113">前端池最多可以包含十二個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="9ebab-113">A Front End pool can contain a maximum of twelve Front End Servers.</span></span> <span data-ttu-id="9ebab-114">多個前端伺服器需要負載平衡。</span><span class="sxs-lookup"><span data-stu-id="9ebab-114">Load balancing is required for multiple Front End Servers.</span></span> <span data-ttu-id="9ebab-115">針對 SIP 流量，我們建議 DNS 負載平衡，但也支援硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="9ebab-115">For SIP traffic, we recommend DNS load balancing, but hardware load balancing is also supported.</span></span> <span data-ttu-id="9ebab-116">如果您使用 [DNS 負載平衡] 進行 SIP 流量，您仍需要用於 HTTP 流量的硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="9ebab-116">If you use DNS load balancing for SIP traffic, you still need a hardware load balancer for HTTP traffic.</span></span> <span data-ttu-id="9ebab-117">我們建議 SQL Server 鏡像提供高可用性的資料庫。</span><span class="sxs-lookup"><span data-stu-id="9ebab-117">We recommend SQL Server mirroring for high availability of databases.</span></span> <span data-ttu-id="9ebab-118">後端資料庫需要個別的實例，但您可以 collocate 封存資料庫、監視資料庫、持久聊天資料庫，以及與它持久的聊天合規性資料庫。</span><span class="sxs-lookup"><span data-stu-id="9ebab-118">The back-end database requires a separate instance, but you can collocate the archiving database, monitoring database, persistent chat database, and persistent chat compliance database with it.</span></span> <span data-ttu-id="9ebab-119">Lync Server 2013 支援在您部署中的檔案共用中使用共用的群集。</span><span class="sxs-lookup"><span data-stu-id="9ebab-119">Lync Server 2013 supports the use of a shared cluster for the file shares in your deployment.</span></span> <span data-ttu-id="9ebab-120">如需資料庫儲存空間需求的詳細資料，請參閱[Lync Server 2013 中的資料庫軟體支援](lync-server-2013-database-software-support.md)。</span><span class="sxs-lookup"><span data-stu-id="9ebab-120">For details about database storage requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="9ebab-121">如需檔案儲存空間需求的詳細資料，請參閱[Lync Server 2013 中的檔案儲存支援](lync-server-2013-file-storage-support.md)。</span><span class="sxs-lookup"><span data-stu-id="9ebab-121">For details about file storage requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md).</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="9ebab-122">如果您 collocate Lync Server 資料庫，我們強烈建議您評估可能會影響可用性和效能的所有因素。</span><span class="sxs-lookup"><span data-stu-id="9ebab-122">If you collocate Lync Server databases, we highly recommend assessing all factors that might affect availability and performance.</span></span> <span data-ttu-id="9ebab-123">若要確認容錯移轉功能，建議測試所有容錯移轉案例。</span><span class="sxs-lookup"><span data-stu-id="9ebab-123">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>

        
        </div>
    
      - <span data-ttu-id="9ebab-124">標準版伺服器，包括 collocated SQL Server Express 資料庫。</span><span class="sxs-lookup"><span data-stu-id="9ebab-124">Standard Edition server, which includes a collocated SQL Server Express database.</span></span>

  - <span data-ttu-id="9ebab-125">您的部署也可以有一個或多個與中央網站相關聯的分支網站。</span><span class="sxs-lookup"><span data-stu-id="9ebab-125">Your deployment can also have one or more branch sites associated with a central site.</span></span>

<span data-ttu-id="9ebab-126">本節說明 Lync Server 2013 部署的網站和元件。</span><span class="sxs-lookup"><span data-stu-id="9ebab-126">This section describes the sites and components of a Lync Server 2013 deployment.</span></span> <span data-ttu-id="9ebab-127">如需有關 Lync Server 2013 網站、拓撲和元件規劃的詳細資料，請參閱規劃 Lync server 2013 以及[Lync server 2013](lync-server-2013-reference-topologies.md)中的 [規劃] 檔中的參考拓撲[前，您必須瞭解的拓撲結構基礎](lync-server-2013-topology-basics-you-must-know-before-planning.md)。</span><span class="sxs-lookup"><span data-stu-id="9ebab-127">For details about Lync Server 2013 site, topology, and component planning, see [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md) and [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md) in the Planning documentation.</span></span> <span data-ttu-id="9ebab-128">如需整合舊版元件的詳細資訊，請參閱[Lync Server 2013 中支援的遷移路徑和共存案例](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md)。</span><span class="sxs-lookup"><span data-stu-id="9ebab-128">For details about integration of components of previous releases, see [Supported migration paths and coexistence scenarios in Lync Server 2013](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9ebab-129">前端、邊緣、轉送和控制器伺服器角色不支援延伸池。</span><span class="sxs-lookup"><span data-stu-id="9ebab-129">Stretched pools are not supported for the Front End, Edge, Mediation, and Director server roles.</span></span>



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a><span data-ttu-id="9ebab-130">中央網站拓撲與元件（內部部署）</span><span class="sxs-lookup"><span data-stu-id="9ebab-130">Central Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="9ebab-131">雖然中心網站拓朴必須包含一個前端池或一個標準版伺服器，但每個中央網站也可以包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="9ebab-131">Although a central site topology must include one Front End pool or one Standard Edition server, each central site can also contain the following:</span></span>

  - <span data-ttu-id="9ebab-132">多個前端池，可能位於同一個網域或不同的網域。</span><span class="sxs-lookup"><span data-stu-id="9ebab-132">Multiple Front End pools, which can be in the same domain or different domains.</span></span> <span data-ttu-id="9ebab-133">不過，前端池中的所有前端伺服器，以及該池的後端伺服器，都必須位於同一個網域中。</span><span class="sxs-lookup"><span data-stu-id="9ebab-133">However, all Front End Servers in a Front End pool, and the Back End Server for that pool, must be in the same domain.</span></span>

  - <span data-ttu-id="9ebab-134">多個標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="9ebab-134">Multiple Standard Edition servers.</span></span>

  - <span data-ttu-id="9ebab-135">在 Lync Server 2013 中與 Office Web 應用程式搭配使用的 office Web Apps Server，用來處理 Microsoft PowerPoint 簡報的共用和轉譯。</span><span class="sxs-lookup"><span data-stu-id="9ebab-135">Office Web Apps Server, which is used with Office Web Applications in Lync Server 2013 to handle the sharing and rendering of Microsoft PowerPoint presentations.</span></span>

  - <span data-ttu-id="9ebab-136">在周邊網路中的 edge 伺服器或邊緣池，如果您想讓您的部署支援同盟夥伴、公用 IM 連線、可擴展的訊息和目前狀態通訊協定（XMPP）閘道、遠端使用者存取權、參與會議中的匿名使用者，或 Exchange 整合訊息（UM）。</span><span class="sxs-lookup"><span data-stu-id="9ebab-136">Edge Server or Edge pool in your perimeter network, if you want your deployment to support federated partners, public IM connectivity, an extensible messaging and presence protocol (XMPP) gateway, remote user access, participation of anonymous users in meetings, or Exchange Unified Messaging (UM).</span></span> <span data-ttu-id="9ebab-137">您無法 collocate 任何其他伺服器角色與 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="9ebab-137">You cannot collocate any other server role with an Edge Server.</span></span> <span data-ttu-id="9ebab-138">我們建議在適當的地方進行 DNS 負載平衡，但也支援硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="9ebab-138">We recommend DNS load balancing, where appropriate, but hardware load balancing is also supported.</span></span> <span data-ttu-id="9ebab-139">內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。</span><span class="sxs-lookup"><span data-stu-id="9ebab-139">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="9ebab-140">您不能在一個 Edge 介面上使用 DNS 負載平衡，而在另一個 Edge 介面上使用硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="9ebab-140">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span> <span data-ttu-id="9ebab-141">如需負載平衡需求與支援的詳細資訊，請參閱在 lync server 2013 規劃中的[外部使用者存取](lync-server-2013-planning-for-external-user-access.md)在部署檔中的 [規劃檔] 和 [[部署在 lync server 2013 中的外部使用者存取](lync-server-2013-deploying-external-user-access.md)]。</span><span class="sxs-lookup"><span data-stu-id="9ebab-141">For details about load balancing requirements and support, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation and [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="9ebab-142">中繼伺服器或池：如果您想要在中央網站的前端池中支援企業語音或電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="9ebab-142">Mediation Server or pool, if you want to support Enterprise Voice or dial-in conferencing in a Front End pool at the central site.</span></span> <span data-ttu-id="9ebab-143">根據您部署企業語音支援的方式，您可以 collocate 前端池中的中繼伺服器（預設）或部署獨立的中繼伺服器或池。</span><span class="sxs-lookup"><span data-stu-id="9ebab-143">Depending on how you deploy Enterprise Voice support, you can collocate the Mediation Server in a Front End pool (the default) or deploy a stand-alone Mediation Server or pool.</span></span> <span data-ttu-id="9ebab-144">您可以使用 DNS、硬體或應用程式負載平衡（在適當時）從中繼伺服器池的閘道對等發佈流量，包括 PSTN 閘道、IP PBX 或 SIP 中繼會話框線控制（SBC）。如需規劃適當的中繼伺服器拓朴的詳細資料，請參閱規劃檔中的[Lync server 2013 中的中繼伺服器部署指導方針](lync-server-2013-deployment-guidelines-for-mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="9ebab-144">You can use DNS, hardware, or application load balancing (when appropriate) to distribute traffic from a Mediation Server pool’s gateway peer, including a PSTN gateway, IP-PBX, or SIP trunk Session Border Control (SBC).For details about planning the appropriate Mediation Server topology, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="9ebab-145">持續聊天伺服器：如果您想要讓使用者能夠參與多方，則會隨時間保留的、以主題為基礎的交談。</span><span class="sxs-lookup"><span data-stu-id="9ebab-145">Persistent Chat Server, if you want to users to be able to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="9ebab-146">若要提供更多容量並增加可靠性，您的拓撲可以包含多部電腦執行持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="9ebab-146">To provide more capacity and increased reliability, your topology can include multiple computers running Persistent Chat Server.</span></span> <span data-ttu-id="9ebab-147">您無法在企業版池中 collocate 持久聊天伺服器與其他伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="9ebab-147">You cannot collocate Persistent Chat Server with other server roles in an Enterprise pool.</span></span> <span data-ttu-id="9ebab-148">不過，您可以在標準版伺服器上 collocate 持續聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="9ebab-148">However, you can collocate Persistent Chat Server on a Standard Edition server.</span></span> <span data-ttu-id="9ebab-149">持續聊天需要資料庫，而且如果您實現持久的聊天合規性資料庫，但資料庫可以與存檔資料庫、監視資料庫，或在企業版的後端伺服器上 collocated[前端] 池。</span><span class="sxs-lookup"><span data-stu-id="9ebab-149">Persistent chat requires a database and, if you implement persistent chat compliance, a persistent chat compliance database, but the databases can be collocated with the Archiving database, Monitoring database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="9ebab-150">如需規劃適當持久聊天伺服器拓撲的詳細資料，請參閱規劃檔中的[Lync server 2013 中的持續聊天伺服器規劃](lync-server-2013-planning-for-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="9ebab-150">For details about planning the appropriate Persistent Chat Server topology, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="9ebab-151">監控（如果您想要支援音訊/視頻體驗品質（QoE）的資料收集，以及在您的部署中呼叫企業語音和 A/V 會議的詳細資料錄製（CDR）。</span><span class="sxs-lookup"><span data-stu-id="9ebab-151">Monitoring, if you want to support data collection for audio/video Quality of Experience (QoE) and call detail recording (CDR) for Enterprise Voice and A/V conferences in your deployment.</span></span> <span data-ttu-id="9ebab-152">您也可以選擇安裝 Microsoft System Center Operations Manager （舊稱 Microsoft 作業管理員），它使用監視 CDR 及 QoE 資料來產生近乎即時的通知，顯示通話可靠性和媒體質量的狀況。</span><span class="sxs-lookup"><span data-stu-id="9ebab-152">Optionally, you can install the Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which uses Monitoring CDR and QoE data to generate near real-time alerts that show the health of call reliability and media quality.</span></span> <span data-ttu-id="9ebab-153">在前端伺服器或標準版伺服器上 collocated [已部署] 時，監視。</span><span class="sxs-lookup"><span data-stu-id="9ebab-153">Monitoring, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="9ebab-154">[監視] 需要資料庫，但資料庫可以與 [封存資料庫]、[持續聊天資料庫]、[持續聊天規範] 資料庫，或在企業版的 [前端] 池的後端伺服器上 collocated。</span><span class="sxs-lookup"><span data-stu-id="9ebab-154">Monitoring requires a database, but the database can be collocated with the Archiving database, persistent chat database, persistent chat compliance database, or on the Back End Server of an Enterprise Edition Front End pool.</span></span>

  - <span data-ttu-id="9ebab-155">如果您想要在您的部署中封存 IM 通訊及會議內容（出於合規性原因），請封存。</span><span class="sxs-lookup"><span data-stu-id="9ebab-155">Archiving, if you want to archive IM communications and meeting content (for compliance reasons) in your deployment.</span></span> <span data-ttu-id="9ebab-156">當您在前端伺服器或標準版伺服器上進行 collocated 部署時，會進行歸檔。</span><span class="sxs-lookup"><span data-stu-id="9ebab-156">Archiving, when deployed, is collocated on Front End Servers or a Standard Edition server.</span></span> <span data-ttu-id="9ebab-157">封存儲存空間需要部署封存資料庫或與 Exchange 2013 儲存區整合。</span><span class="sxs-lookup"><span data-stu-id="9ebab-157">Archiving storage requires either deployment of an Archiving database or integration with Exchange 2013 storage.</span></span> <span data-ttu-id="9ebab-158">如果您同時使用兩者（稱為*混合模式*），則 exchange 2013 儲存空間用來儲存託管于 Exchange 2013 的使用者的封存資料，而封存資料庫則用於封存您部署中所有其他使用者的資料。</span><span class="sxs-lookup"><span data-stu-id="9ebab-158">If you use both, which is known as *mixed mode*, Exchange 2013 storage is used to store archive data for users who are homed on Exchange 2013, and the Archiving database is used to archive data for all other users in your deployment.</span></span> <span data-ttu-id="9ebab-159">如果您需要封存資料庫，您可以在監視資料庫、持續聊天資料庫、持續聊天規範資料庫，或頂層端池中的後端伺服器上 collocated 資料庫。</span><span class="sxs-lookup"><span data-stu-id="9ebab-159">If you require an Archiving database, the database can be collocated on the Monitoring database, persistent chat database, persistent chat compliance database, or on the Back End Server of a Front End pool.</span></span> <span data-ttu-id="9ebab-160">如需規劃適當的存檔拓撲的詳細資料，請參閱規劃檔中的[Lync Server 2013 中的存檔規劃](lync-server-2013-planning-for-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="9ebab-160">For details about planning the appropriate Archiving topology, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="9ebab-161">主管或主管擁有者，如果您想要協助將 Lync Server 2013 使用者要求的復原和重新導向到使用者的主文件，這可以是企業版前端池或標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="9ebab-161">Director or Director pool, if you want to facilitate resiliency and redirection of Lync Server 2013 user requests to the user’s home pool, which can be either an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="9ebab-162">我們建議您在支援外部使用者存取的每個中央網站，以及您部署一個或多個前端池的每個中心網站中，部署一個主管或主管池。</span><span class="sxs-lookup"><span data-stu-id="9ebab-162">We recommend that you deploy a Director or Director pool in each central site that supports external user access and in each central site in which you deploy one or more Front End pools.</span></span> <span data-ttu-id="9ebab-163">每個控制器池最多可以包含10個控制器。</span><span class="sxs-lookup"><span data-stu-id="9ebab-163">Each Director pool can contain a maximum of ten Directors.</span></span> <span data-ttu-id="9ebab-164">控制器無法與任何其他伺服器角色 collocated。</span><span class="sxs-lookup"><span data-stu-id="9ebab-164">A Director cannot be collocated with any other server role.</span></span> <span data-ttu-id="9ebab-165">如需規劃適當控制器拓撲的詳細資料，請參閱規劃檔中的[Lync Server 2013 中的主管案例](lync-server-2013-scenarios-for-the-director.md)。</span><span class="sxs-lookup"><span data-stu-id="9ebab-165">For details about planning the appropriate Director topology, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="9ebab-166">反向 proxy （不是 Lync Server 2013 元件），但如果您想要支援與同盟使用者共用網頁內容，或支援行動性流量，則需要。</span><span class="sxs-lookup"><span data-stu-id="9ebab-166">Reverse proxy, which is not a Lync Server 2013 component, but is required if you want to support sharing of web content for federated users or to support Mobility traffic.</span></span> <span data-ttu-id="9ebab-167">您無法使用任何 Lync Server 2013 伺服器角色來 collocate 反向 proxy 伺服器，但您可以在組織中針對其他人設定支援，以對 Lync Server 2013 部署執行反向 proxy 支援。程式.</span><span class="sxs-lookup"><span data-stu-id="9ebab-167">You cannot collocate a reverse proxy server with any Lync Server 2013 server role, but you can implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span> <span data-ttu-id="9ebab-168">如需反向 proxy 伺服器的詳細資料，請參閱部署檔中的[Lync Server 2013 設定反向 proxy 伺服器](lync-server-2013-setting-up-reverse-proxy-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="9ebab-168">For details about reverse proxy servers, see [Setting up reverse proxy servers for Lync Server 2013](lync-server-2013-setting-up-reverse-proxy-servers.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9ebab-169">在 Lync Server 2013 中，A/V 會議、監視及封存都是在前端伺服器上執行，不會再個別伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="9ebab-169">In Lync Server 2013, A/V Conferencing, Monitoring, and Archiving run on Front End Servers and are no longer separate server roles.</span></span>



</div>

<span data-ttu-id="9ebab-170">您在中央網站上部署的所有前端池和標準版伺服器共用您針對中心網站部署的下列任何一項：</span><span class="sxs-lookup"><span data-stu-id="9ebab-170">All Front End pools and Standard Edition servers that you deploy at a central site share any of the following that you deploy for the central site:</span></span>

  - <span data-ttu-id="9ebab-171">主管或主管池</span><span class="sxs-lookup"><span data-stu-id="9ebab-171">Director or Director pool</span></span>

  - <span data-ttu-id="9ebab-172">獨立的中繼伺服器或池</span><span class="sxs-lookup"><span data-stu-id="9ebab-172">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="9ebab-173">Office Web Apps 伺服器</span><span class="sxs-lookup"><span data-stu-id="9ebab-173">Office Web Apps Server</span></span>

  - <span data-ttu-id="9ebab-174">Edge 伺服器或 Edge 池</span><span class="sxs-lookup"><span data-stu-id="9ebab-174">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="9ebab-175">持續聊天伺服器或池</span><span class="sxs-lookup"><span data-stu-id="9ebab-175">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="9ebab-176">監視</span><span class="sxs-lookup"><span data-stu-id="9ebab-176">Monitoring</span></span>

  - <span data-ttu-id="9ebab-177">封存</span><span class="sxs-lookup"><span data-stu-id="9ebab-177">Archiving</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9ebab-178">如果您想要支援 Exchange 2013 整合通訊，但不是 Lync Server 2013 網站的元件，則可以使用 Lync Server 2013 部署來實施 Exchange UM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="9ebab-178">An Exchange UM Server can be implemented with your Lync Server 2013 deployment if you want to support integration of Exchange 2013 Unified Messaging, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="9ebab-179">多個中心網站也可以共用您在一個中央網站中部署的下列任何一項：</span><span class="sxs-lookup"><span data-stu-id="9ebab-179">Multiple central sites can also share any of the following that you deploy in one central site:</span></span>

  - <span data-ttu-id="9ebab-180">獨立的中繼伺服器或池</span><span class="sxs-lookup"><span data-stu-id="9ebab-180">Stand-alone Mediation Server or pool</span></span>

  - <span data-ttu-id="9ebab-181">Edge 伺服器或 Edge 池</span><span class="sxs-lookup"><span data-stu-id="9ebab-181">Edge Server or Edge pool</span></span>

  - <span data-ttu-id="9ebab-182">持續聊天伺服器或池</span><span class="sxs-lookup"><span data-stu-id="9ebab-182">Persistent Chat Server or pool</span></span>

  - <span data-ttu-id="9ebab-183">封存</span><span class="sxs-lookup"><span data-stu-id="9ebab-183">Archiving</span></span>

  - <span data-ttu-id="9ebab-184">監視</span><span class="sxs-lookup"><span data-stu-id="9ebab-184">Monitoring</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9ebab-185">Exchange UM 伺服器可以在您的 Lync Server 2013 部署中執行，並由多個中央網站共用，但它不是 Lync Server 2013 網站的元件。</span><span class="sxs-lookup"><span data-stu-id="9ebab-185">An Exchange UM Server can be implemented with your Lync Server 2013 deployment and shared by multiple central sites, but it is not a component of the Lync Server 2013 site.</span></span>



</div>

<span data-ttu-id="9ebab-186">如需 Lync Server 2013 伺服器角色和功能的詳細資訊，請參閱規劃檔中的[Lync server 2013 中的伺服器角色](lync-server-2013-server-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="9ebab-186">For details about Lync Server 2013 server roles and functionality, see [Server roles in Lync Server 2013](lync-server-2013-server-roles.md) in the Planning documentation.</span></span>

<span data-ttu-id="9ebab-187">如需 Lync Server 2013 server collocation 支援摘要，請參閱[Lync server 2013 中的支援的伺服器 collocation](lync-server-2013-supported-server-collocation.md)。</span><span class="sxs-lookup"><span data-stu-id="9ebab-187">For a summary of Lync Server 2013 server collocation support, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<span data-ttu-id="9ebab-188">除了本節前面所述的伺服器角色和功能之外，Lync Server 2013 還有其他元件和選項，其中包括下列部分或全部選項：</span><span class="sxs-lookup"><span data-stu-id="9ebab-188">In addition to the server roles and functionality covered previously in this section, Lync Server 2013 has additional components and options, which can include some or all of the following:</span></span>

  - <span data-ttu-id="9ebab-189">道</span><span class="sxs-lookup"><span data-stu-id="9ebab-189">Firewalls</span></span>

  - <span data-ttu-id="9ebab-190">PSTN 閘道（如果部署企業版語音）</span><span class="sxs-lookup"><span data-stu-id="9ebab-190">PSTN gateways (if deploying Enterprise Voice)</span></span>

  - <span data-ttu-id="9ebab-191">Exchange UM 伺服器</span><span class="sxs-lookup"><span data-stu-id="9ebab-191">Exchange UM Server</span></span>

  - <span data-ttu-id="9ebab-192">DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="9ebab-192">DNS load balancing</span></span>

  - <span data-ttu-id="9ebab-193">硬體負載平衡器</span><span class="sxs-lookup"><span data-stu-id="9ebab-193">Hardware load balancers</span></span>

  - <span data-ttu-id="9ebab-194">SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="9ebab-194">SQL Server databases</span></span>

  - <span data-ttu-id="9ebab-195">檔案共用</span><span class="sxs-lookup"><span data-stu-id="9ebab-195">File shares</span></span>

<span data-ttu-id="9ebab-196">如需所有 Lync Server 2013 功能、元件及選項的詳細資料，請參閱規劃檔。</span><span class="sxs-lookup"><span data-stu-id="9ebab-196">For details about all of the Lync Server 2013 features, components, and options, see the Planning documentation.</span></span>

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a><span data-ttu-id="9ebab-197">分支網站拓撲與元件（內部部署）</span><span class="sxs-lookup"><span data-stu-id="9ebab-197">Branch Site Topologies and Components (On-Premises)</span></span>

<span data-ttu-id="9ebab-198">分支網站與中央網站相關聯，且分支網站中的每個 Survivable 分支裝置都與相關聯的中央網站中的企業版前端池或標準版伺服器相關聯。</span><span class="sxs-lookup"><span data-stu-id="9ebab-198">A branch site is associated with a central site, and each Survivable Branch Appliance in a branch site is associated with an Enterprise Edition Front End pool or a Standard Edition server in the associated central site.</span></span> <span data-ttu-id="9ebab-199">分支網站在中心網站上的功能大部分，所以分支網站上的元件只包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="9ebab-199">Branch sites depend on the central site for most of their functionality, so components at a branch site contain only the following:</span></span>

  - <span data-ttu-id="9ebab-200">Survivable 分支裝置，將公用的交換電話網絡（PSTN）閘道與一些 Lync Server 功能結合在一起。</span><span class="sxs-lookup"><span data-stu-id="9ebab-200">A Survivable Branch Appliance, which combines a public switched telephone network (PSTN) gateway with some Lync Server functionality.</span></span> <span data-ttu-id="9ebab-201">您可以在 Survivable 分支裝置上，將中繼伺服器與註冊機構的實例 collocated，而且您可以部署獨立的中繼伺服器或轉送伺服器池。</span><span class="sxs-lookup"><span data-stu-id="9ebab-201">A Mediation Server can be collocated with the instance of the Registrar on the Survivable Branch Appliance, and you can deploy a stand-alone Mediation Server or pool of Mediation Servers.</span></span>

  - <span data-ttu-id="9ebab-202">Survivable 分支伺服器，這是執行 Windows Server 且已安裝 Lync Server 2013 註冊機構和中繼伺服器軟體的伺服器。</span><span class="sxs-lookup"><span data-stu-id="9ebab-202">A Survivable Branch Server, which is a server running Windows Server that has Lync Server 2013 Registrar and Mediation Server software installed.</span></span>

  - <span data-ttu-id="9ebab-203">獨立的 PSTN 閘道（不是 Survivable 分支裝置的一部分）和獨立的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="9ebab-203">A stand-alone PSTN gateway (not part of the Survivable Branch Appliance) and a stand-alone Mediation Server.</span></span>

<span data-ttu-id="9ebab-204">Survivable 分支伺服器的需求與任何 Lync Server 2013 伺服器角色的需求相同。</span><span class="sxs-lookup"><span data-stu-id="9ebab-204">The requirements for Survivable Branch Servers are the same as the requirements for any Lync Server 2013 server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

