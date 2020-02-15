---
title: Lync Server 2013： 新的常設聊天室伺服器功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Persistent Chat Server features
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412965(v=OCS.15)
ms:contentKeyID: 48185341
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5257490dc63e1626c0cdb6dcf7e6ce1f17e75cd1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a><span data-ttu-id="c85e4-102">Lync Server 2013 中的新 Persistent Chat Server 功能</span><span class="sxs-lookup"><span data-stu-id="c85e4-102">New Persistent Chat Server features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c85e4-103">_**主題上次修改日期：** 2012年-10-29_</span><span class="sxs-lookup"><span data-stu-id="c85e4-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="c85e4-104">Lync Server 2013，Persistent Chat Server 可讓您參與多方、 主題型保留一段時間的交談。</span><span class="sxs-lookup"><span data-stu-id="c85e4-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="c85e4-105">Persistent Chat Server 可協助組織，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c85e4-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="c85e4-106">改進地理位置分散且跨部門之小組間的通訊</span><span class="sxs-lookup"><span data-stu-id="c85e4-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="c85e4-107">擴大資訊傳達和參與範圍</span><span class="sxs-lookup"><span data-stu-id="c85e4-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="c85e4-108">改進大組織的通訊</span><span class="sxs-lookup"><span data-stu-id="c85e4-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="c85e4-109">緩和資訊超載的狀況</span><span class="sxs-lookup"><span data-stu-id="c85e4-109">Reduce information overload</span></span>

  - <span data-ttu-id="c85e4-110">改進資訊傳達方式</span><span class="sxs-lookup"><span data-stu-id="c85e4-110">Improve information awareness</span></span>

  - <span data-ttu-id="c85e4-111">加強重要知識和資訊的傳播</span><span class="sxs-lookup"><span data-stu-id="c85e4-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="c85e4-112">無法在 Microsoft Office 365 中使用 Lync Server 2013，Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="c85e4-112">Lync Server 2013, Persistent Chat Server is not available in Microsoft Office 365.</span></span> <span data-ttu-id="c85e4-113">在這個階段中，它是只適用於內部部署 Lync 2013 客戶。</span><span class="sxs-lookup"><span data-stu-id="c85e4-113">At this time, it is available only to on-premise Lync 2013 customers.</span></span>

<span data-ttu-id="c85e4-114">在 Lync 2013 常設聊天室功能整合到 Lync 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="c85e4-114">In Lync 2013, Persistent Chat functionality is integrated into the Lync 2013 client.</span></span> <span data-ttu-id="c85e4-115">因此，使用者可以存取所有的 Lync 2013 用戶端 Instant Messaging/目前狀態、 音訊/視訊、 會議及常設聊天室。</span><span class="sxs-lookup"><span data-stu-id="c85e4-115">As a result, users have access to Instant Messaging/Presence, Audio/Video, Conferencing, and Persistent Chat all in the Lync 2013 client.</span></span> <span data-ttu-id="c85e4-116">如需有關 Lync 2013 用戶端的詳細資訊，請參閱<http://go.microsoft.com/fwlink/p/?linkid=270877>。</span><span class="sxs-lookup"><span data-stu-id="c85e4-116">For more information about the Lync 2013 client, see <http://go.microsoft.com/fwlink/p/?linkid=270877>.</span></span>

<span data-ttu-id="c85e4-117">本主題說明 Lync Server 2013，Persistent Chat Server 與先前的版本 （Microsoft Lync Server 2010，Group Chat） 的新版本之間的功能變更包括：</span><span class="sxs-lookup"><span data-stu-id="c85e4-117">This topic describes feature changes between the new version of Lync Server 2013, Persistent Chat Server and the previous version (Microsoft Lync Server 2010, Group Chat), including:</span></span>

  - <span data-ttu-id="c85e4-118">提供 Lync Server 控制台] 中的系統管理體驗，並排除 Group Chat Admin Tool</span><span class="sxs-lookup"><span data-stu-id="c85e4-118">Provide an administrative experience in Lync Server Control Panel, and eliminate the Group Chat Admin Tool</span></span>

  - <span data-ttu-id="c85e4-119">整合拓撲產生器中的 for Persistent Chat Server 的組態設定，藉由消除群組聊天設定工具</span><span class="sxs-lookup"><span data-stu-id="c85e4-119">Integrate configuration settings for Persistent Chat Server into Topology Builder by eliminating the Group Chat Configuration tool</span></span>

  - <span data-ttu-id="c85e4-120">輕鬆移轉及升級舊版 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="c85e4-120">Ease migration and upgrade from previous versions of Persistent Chat Server</span></span>

  - <span data-ttu-id="c85e4-121">提供高可用性和災害復原解決方案</span><span class="sxs-lookup"><span data-stu-id="c85e4-121">Provide high availability and disaster recovery solutions</span></span>

<span data-ttu-id="c85e4-122">如其他需 Persistent Chat Server 的最新版本的詳細資訊，請參閱下列各項：</span><span class="sxs-lookup"><span data-stu-id="c85e4-122">For additional details about the latest version of Persistent Chat Server, see the following:</span></span>

  - <span data-ttu-id="c85e4-123">常設聊天室協助在<http://go.microsoft.com/fwlink/p/?linkid=270945>功能，它們的運作方式，以及如何使用它們時執行 Persistent Chat Server 提供常設聊天室的詳細的清單。</span><span class="sxs-lookup"><span data-stu-id="c85e4-123">The Persistent Chat Help at <http://go.microsoft.com/fwlink/p/?linkid=270945> which provides a detailed list of Persistent Chat features, how they work, and how to use them while running Persistent Chat Server.</span></span>

  - <span data-ttu-id="c85e4-124">[Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)中規劃文件、 部署文件中的[Deploying Persistent Chat Server 在 Lync Server 2013 中](lync-server-2013-deploying-persistent-chat-server.md)，[從 Lync Server 2010，Group Chat 或 Office Communications Server 2007 R2 Group Chat to Lync Server 2013，Persistent Chat Server 移轉](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)中移轉文件中，並[管理 Lync Server 2013，Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md)的作業文件中所有的指示設定常設聊天室伺服器。</span><span class="sxs-lookup"><span data-stu-id="c85e4-124">The [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation, [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) in the Migration documentation, and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) in the Operations documentation, all of which provide instructions for setting up Persistent Chat Server.</span></span>

  - <span data-ttu-id="c85e4-125">常設聊天室伺服器 Documentation.msi 檔 （Windows Installer 檔案） 可讓使用者存取完整離線文件相關 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="c85e4-125">The Persistent Chat Server Documentation.msi file (Windows Installer file) lets users access comprehensive offline documentation about Persistent Chat Server.</span></span>

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a><span data-ttu-id="c85e4-126">常設聊天室伺服器的主要拓撲變更</span><span class="sxs-lookup"><span data-stu-id="c85e4-126">Key Topology Changes for Persistent Chat Server</span></span>

<span data-ttu-id="c85e4-127">Persistent Chat Server 高層級的下列變更包括：</span><span class="sxs-lookup"><span data-stu-id="c85e4-127">The following high-level changes for Persistent Chat Server include:</span></span>

<span data-ttu-id="c85e4-128">Persistent Chat Server 現在是一個伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="c85e4-128">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="c85e4-129">在 [Microsoft Lync Server 2010，Group Chat 伺服器已 Microsoft Lync Server 2010 的協力廠商信任應用程式。</span><span class="sxs-lookup"><span data-stu-id="c85e4-129">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="c85e4-130">使用拓撲產生器時，可加入常設聊天室 Lync Server 2013 拓撲。</span><span class="sxs-lookup"><span data-stu-id="c85e4-130">Persistent Chat can be added to your Lync Server 2013 topology by using Topology Builder.</span></span> <span data-ttu-id="c85e4-131">在 Lync Server 2013，Persistent Chat Server 功能被實作使用三個新的伺服器角色：</span><span class="sxs-lookup"><span data-stu-id="c85e4-131">In Lync Server 2013, Persistent Chat Server functionality is implemented by using three new server roles:</span></span>

  - <span data-ttu-id="c85e4-132">**PersistentChatService:** 這是針對常設聊天室前端角色。</span><span class="sxs-lookup"><span data-stu-id="c85e4-132">**PersistentChatService:** This is the front end role for Persistent Chat.</span></span> <span data-ttu-id="c85e4-133">在 Standard Edition 部署中，常設聊天室伺服器服務角色組合在像任何其他的 Lync Server 角色部署的器，Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="c85e4-133">In Standard Edition deployments, Persistent Chat Server Service Role is collocated on the Standard Edition server deployed by Bootstrapper, like any other Lync Server role.</span></span> <span data-ttu-id="c85e4-134">在 Enterprise Edition 部署中，常設聊天室服務角色被部署在獨立電腦上啟動載入器，像任何其他 Lync 伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="c85e4-134">In Enterprise Edition deployments, Persistent Chat Service Role is deployed on stand-alone computers by Bootstrapper, like any other Lync Server role.</span></span>

  - <span data-ttu-id="c85e4-135">**PersistentChatStore:** 後端伺服器對應至常設聊天室內容資料庫，儲存所有聊天室的內容。</span><span class="sxs-lookup"><span data-stu-id="c85e4-135">**PersistentChatStore:** Back End Server that corresponds to the Persistent Chat content database, where all the chat content is stored.</span></span>

  - <span data-ttu-id="c85e4-136">**PersistentChatComplianceStore:** 備份端伺服器角色會對應至常設聊天室規範資料庫，儲存所有的規範事件。</span><span class="sxs-lookup"><span data-stu-id="c85e4-136">**PersistentChatComplianceStore:** Back End Server role that corresponds to the Persistent Chat Compliance database, where all compliance events are stored.</span></span>

<span data-ttu-id="c85e4-137">這些 Persistent Chat Server 角色是選擇性的並且會安裝只能由客戶需要完整 Persistent Chat Server 功能。</span><span class="sxs-lookup"><span data-stu-id="c85e4-137">These Persistent Chat Server roles are optional, and are installed only by customers who want comprehensive Persistent Chat Server functionality.</span></span> <span data-ttu-id="c85e4-138">只有當您選擇部署常設聊天室規範需要**PersistentChatComplianceStore**角色。</span><span class="sxs-lookup"><span data-stu-id="c85e4-138">The **PersistentChatComplianceStore** role is needed only if you choose to deploy Persistent Chat Compliance.</span></span>

<span data-ttu-id="c85e4-139">**PersistentChatService**角色執行兩項服務：</span><span class="sxs-lookup"><span data-stu-id="c85e4-139">The **PersistentChatService** role runs two services:</span></span>

  - <span data-ttu-id="c85e4-140">常設聊天服務</span><span class="sxs-lookup"><span data-stu-id="c85e4-140">Persistent Chat service</span></span>

  - <span data-ttu-id="c85e4-141">常設聊天室規範服務</span><span class="sxs-lookup"><span data-stu-id="c85e4-141">Persistent Chat Compliance service</span></span>

<span data-ttu-id="c85e4-142">在每個 Persistent Chat Server 上執行這些服務能提供這些服務的多重伺服器 Persistent Chat Server 集區中的高可用性。</span><span class="sxs-lookup"><span data-stu-id="c85e4-142">Having these services run on each Persistent Chat Server provides high availability for these services in a multiserver Persistent Chat Server pool.</span></span>

<span data-ttu-id="c85e4-143">此外，若要支援的檔案上傳和下載中的常設聊天室，Persistent Chat Server 包括 web 服務。</span><span class="sxs-lookup"><span data-stu-id="c85e4-143">Additionally, to support the file upload and download in Persistent Chat rooms, Persistent Chat Server includes a web service.</span></span> <span data-ttu-id="c85e4-144">過去，此服務已組合 Persistent Chat Server、 前端伺服器與需要網際網路資訊服務 (IIS)，若要安裝的必要條件。</span><span class="sxs-lookup"><span data-stu-id="c85e4-144">Previously, this service was collocated on the Persistent Chat Server, Front End Server and required Internet Information Services (IIS) to be installed as a prerequisite.</span></span> <span data-ttu-id="c85e4-145">在 [Lync Server 2013 常設聊天室伺服器、 檔案上傳/下載 web 服務會與 Lync Server 2013 前端伺服器配置在一起。</span><span class="sxs-lookup"><span data-stu-id="c85e4-145">In Lync Server 2013 Persistent Chat Server, the File Upload/Download web service is collocated with the Lync Server 2013 Front End Server.</span></span> <span data-ttu-id="c85e4-146">副作用，網際網路資訊服務 (IIS) 不再是 Persistent Chat Server 的必要條件。</span><span class="sxs-lookup"><span data-stu-id="c85e4-146">As a side effect, Internet Information Services (IIS) is no longer a prerequisite for Persistent Chat Server.</span></span> <span data-ttu-id="c85e4-147">檔案上傳/下載 web 服務會被識別為**Atl-persistentchat**在網際網路資訊服務 (IIS) 管理員] 中。</span><span class="sxs-lookup"><span data-stu-id="c85e4-147">The File Upload/Download web service is identified as **PersistentChat** in the Internet Information Services (IIS) Manager.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c85e4-148"><STRONG>PersistentChatService</STRONG>角色可以執行 Lync Server 2013 相同伺服器上的&nbsp;前端伺服器只有在該前端伺服器為 Standard Edition&nbsp;前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="c85e4-148">The <STRONG>PersistentChatService</STRONG> role can run on the same server as a Lync Server 2013&nbsp;Front End Server only if that Front End Server is a Standard Edition&nbsp;Front End Server.</span></span> <span data-ttu-id="c85e4-149"><STRONG>PersistentChatService</STRONG>角色不能執行 Lync Server 2013 獨立&nbsp;前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="c85e4-149">The <STRONG>PersistentChatService</STRONG> role cannot run independently of a Lync Server 2013&nbsp;Front End Server.</span></span> <span data-ttu-id="c85e4-150">它可以安裝 Lync Server 2013 部署的內容中。</span><span class="sxs-lookup"><span data-stu-id="c85e4-150">It can be installed only in the context of a Lync Server 2013 deployment.</span></span>



</div>

<span data-ttu-id="c85e4-151">在 [常設聊天室伺服器排除查閱服務。</span><span class="sxs-lookup"><span data-stu-id="c85e4-151">In Persistent Chat Server, Lookup service has been eliminated.</span></span> <span data-ttu-id="c85e4-152">在 Lync Server 2010，Group Chat，查閱服務在每個群組聊天伺服器前端伺服器上執行，並執行下列其中一個通道伺服器的路由。</span><span class="sxs-lookup"><span data-stu-id="c85e4-152">In Lync Server 2010, Group Chat, the Lookup service ran on every Group Chat Server Front End Server, and performed routing to one of the Channel Servers.</span></span> <span data-ttu-id="c85e4-153">Lync Server 2013 依賴路由使用連絡人物件，其中每個 Persistent Chat Server 集區由以找出並路由傳送要求至適當的 Persistent Chat Server 集區，以及由 Lync Server 前端伺服器的連絡人物件其中一個執行 Persistent Chat Server 集區中的電腦。</span><span class="sxs-lookup"><span data-stu-id="c85e4-153">Lync Server 2013 relies on routing by using contact objects, where each Persistent Chat Server pool is represented by a contact object that is used by the Lync Server Front End Servers to identify and route requests to an appropriate Persistent Chat Server pool, and to one of the computers running Persistent Chat Server in the pool.</span></span>

<span data-ttu-id="c85e4-154">在 Lync Server 2013 中，有規範服務修改：</span><span class="sxs-lookup"><span data-stu-id="c85e4-154">In Lync Server 2013, there are Compliance service modifications:</span></span>

  - <span data-ttu-id="c85e4-155">Lync Server 2010 的規範服務執行獨立 （非-組合在一起），並只在單一伺服器上。</span><span class="sxs-lookup"><span data-stu-id="c85e4-155">In Lync Server 2010, the Compliance service ran stand-alone (non-collocated), and only on a single server.</span></span> <span data-ttu-id="c85e4-156">規範服務現在會執行所有常設聊天室伺服器前端伺服器，以及常設聊天室服務，並藉此提供的多重伺服器 Persistent Chat Server 集區中的高可用性。</span><span class="sxs-lookup"><span data-stu-id="c85e4-156">The Compliance service now runs on all the Persistent Chat Server Front End Servers, alongside the Persistent Chat service, and thereby provides high availability in a multiserver Persistent Chat Server pool.</span></span> <span data-ttu-id="c85e4-157">單一規範配接器可以設定成從規範資料庫，其中一個其他系統 （XML 檔案、 Exchange 託管封存，依此類推） 擷取資料。</span><span class="sxs-lookup"><span data-stu-id="c85e4-157">A single compliance adapter can be configured to extract data from the compliance database and into one of the other systems (XML file, Exchange-hosted archives, and so on).</span></span> <span data-ttu-id="c85e4-158">Persistent Chat Server 包含 XML 介面卡。</span><span class="sxs-lookup"><span data-stu-id="c85e4-158">Persistent Chat Server includes an XML adapter.</span></span>

  - <span data-ttu-id="c85e4-159">訊息佇列 (又稱為 MSMQ) 佇列所共用的常設聊天室服務和每個 Persistent Chat Server 前端伺服器上的規範服務現在是僅供這兩項服務共用的私用佇列。</span><span class="sxs-lookup"><span data-stu-id="c85e4-159">The Message Queuing (also known as MSMQ) queue that is shared by the Persistent Chat service and the Compliance service on each Persistent Chat Server Front End Server is now a private queue shared only by the two services.</span></span> <span data-ttu-id="c85e4-160">所有的規範服務寫入至相同的規範後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="c85e4-160">All compliance services write to the same Compliance Back End database.</span></span> <span data-ttu-id="c85e4-161">他們也所有從該資料庫讀取，目的將資料傳送到其執行個體的介面卡。</span><span class="sxs-lookup"><span data-stu-id="c85e4-161">They also all read from that database, for the purpose of sending the data to their instance of the adapter.</span></span> <span data-ttu-id="c85e4-162">規範後端伺服器是以表示做為新的後端伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="c85e4-162">The Compliance Back End Server is represented as a new Back End Server role.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c85e4-163">如同舊版中，所有規範資料都處理一次。</span><span class="sxs-lookup"><span data-stu-id="c85e4-163">As in previous versions, all compliance data is processed only once.</span></span> <span data-ttu-id="c85e4-164">資料可能會由叫用在各種不同的 Lync Server 2013，Persistent Chat Server 電腦所執行的規範服務的配接器執行任何的個體處理。</span><span class="sxs-lookup"><span data-stu-id="c85e4-164">The data may be processed by any of the adapter instances invoked by the compliance service running on the various Lync Server 2013, Persistent Chat Server computers.</span></span> <span data-ttu-id="c85e4-165">Persistent Chat Server，在其中一個配接器執行個體無法處理資料。</span><span class="sxs-lookup"><span data-stu-id="c85e4-165">In Persistent Chat Server, any one of the adapter instances could process the data.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c85e4-166">安裝訊息佇列的相關資訊，請參閱部署文件中<A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">安裝作業系統和 Lync Server 2013 的伺服器上的必要軟體</A>。</span><span class="sxs-lookup"><span data-stu-id="c85e4-166">For information about installing Message Queuing, see <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Install operating systems and prerequisite software on servers for Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="c85e4-167">在 Lync Server 2013 中，有高可用性和災害復原中的改良功能：</span><span class="sxs-lookup"><span data-stu-id="c85e4-167">In Lync Server 2013, there are improvements in both high availability and disaster recovery:</span></span>

  - <span data-ttu-id="c85e4-168">高可用性改進： SQL Server 鏡像時用於 Persistent Chat Server 內容資料庫與常設聊天室規範資料庫 （網站） 的資料中心內提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="c85e4-168">High availability improvements: SQL Server mirroring is used to provide high availability for the Persistent Chat Server content database and Persistent Chat compliance database within a data center (in-site).</span></span>

  - <span data-ttu-id="c85e4-169">嚴重損壞復原增強功能： Persistent Chat Server 支援延伸集區架構，可讓要跨兩個站台伸展直到佔滿單一 Persistent Chat Server 集區 （也就是單一邏輯集區在拓撲中，集區中的伺服器與實體跨兩個站台位於）。</span><span class="sxs-lookup"><span data-stu-id="c85e4-169">Disaster recovery improvements: Persistent Chat Server supports a stretched pool architecture that enables a single Persistent Chat Server pool to be stretched across two sites (that is, a single logical pool in the topology, with servers in the pool physically located across two sites).</span></span> <span data-ttu-id="c85e4-170">SQL Server 記錄傳送用於跨網站做為災害復原。</span><span class="sxs-lookup"><span data-stu-id="c85e4-170">SQL Server Log Shipping is used for cross-site disaster recovery.</span></span>

<span data-ttu-id="c85e4-171">如需高可用性和災害復原的詳細資訊，請參閱部署文件中的[Configuring Persistent Chat Server 的高可用性和 Lync Server 2013 中的災害復原](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="c85e4-171">For more information about high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a><span data-ttu-id="c85e4-172">金鑰管理和管理變更的常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="c85e4-172">Key Administration and Management Changes for Persistent Chat Server</span></span>

<span data-ttu-id="c85e4-173">Lync Server 2013 已進行更輕鬆地管理及管理 Persistent Chat Server 提供：</span><span class="sxs-lookup"><span data-stu-id="c85e4-173">Lync Server 2013 has made it easier to administer and manage Persistent Chat Server by providing:</span></span>

  - <span data-ttu-id="c85e4-174">整合的系統管理與管理。</span><span class="sxs-lookup"><span data-stu-id="c85e4-174">Unified administration and management.</span></span> <span data-ttu-id="c85e4-175">Lync Server 2013 讓您更容易管理，並使用早已熟悉 Lync 系統管理員的工具來管理 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="c85e4-175">Lync Server 2013 makes it easier to manage and administer Persistent Chat Server by using tools that are already familiar to Lync administrators.</span></span> <span data-ttu-id="c85e4-176">Persistent Chat Server 包含整合與 Lync Server Control Panel，地址與舊版群組聊天伺服器的使用者介面的效能問題的系統管理使用者介面體驗。</span><span class="sxs-lookup"><span data-stu-id="c85e4-176">Persistent Chat Server includes an administrative user interface experience that is integrated with the Lync Server Control Panel, which addresses performance issues with the previous versions of the Group Chat Server user interface.</span></span> <span data-ttu-id="c85e4-177">此外，Persistent Chat Server 包含 Windows PowerShell cmdlet 來管理與管理 Persistent Chat Server 類別、 （包括刪除聊天室和清除過時的內容），Persistent Chat Server 聊天室及增益集的集合。</span><span class="sxs-lookup"><span data-stu-id="c85e4-177">Also, Persistent Chat Server includes a collection of Windows PowerShell cmdlets to administer and manage Persistent Chat Server categories, Persistent Chat Server rooms (including deleting rooms and purging obsolete content), and add-ins.</span></span>

  - <span data-ttu-id="c85e4-178">簡化的管理模型。</span><span class="sxs-lookup"><span data-stu-id="c85e4-178">Simplified administration model.</span></span> <span data-ttu-id="c85e4-179">Lync Server 2013 已變更，並簡化 Persistent Chat Server 模型來解決下列重要客戶的需求：</span><span class="sxs-lookup"><span data-stu-id="c85e4-179">Lync Server 2013 has changed and simplified the Persistent Chat Server model by addressing the following key customer requirements:</span></span>
    
      - <span data-ttu-id="c85e4-180">移除複雜的巢狀的階層的範圍和分類。</span><span class="sxs-lookup"><span data-stu-id="c85e4-180">Remove the complex nested hierarchies of scopes and categories.</span></span>
    
      - <span data-ttu-id="c85e4-181">若要定義支援拒絕目前 MindAlign 客戶規劃移轉至 Persistent Chat Server 清單，以及允許的清單 （範圍）。</span><span class="sxs-lookup"><span data-stu-id="c85e4-181">Support to define deny lists as well as allowed lists (scopes) for current MindAlign customers who are planning to migrate to Persistent Chat Server.</span></span>

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a><span data-ttu-id="c85e4-182">從群組聊天伺服器舊版不同之處使用者角色是什麼？</span><span class="sxs-lookup"><span data-stu-id="c85e4-182">What’s Different about User Roles from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="c85e4-183">Lync Server 2010，Group Chat 是使用者系統管理員角色、 聊天室系統管理員角色和 Lync Server 系統管理員角色可以管理新增寫 Persistent Chat Server 只會提供 （也就是類似其他 Lync 常設聊天室系統管理員角色伺服器角色型存取控制 (RBAC) 角色）。</span><span class="sxs-lookup"><span data-stu-id="c85e4-183">Lync Server 2010, Group Chat had a user administrator role, a chat room administrator role and a Lync Server administrator role that could manage add-ins. Persistent Chat Server simply provides a Persistent Chat Administrator role (which is similar to other Lync Server role-based access control (RBAC) roles).</span></span> <span data-ttu-id="c85e4-184">任何人都屬於此 RBAC 角色的成員可以管理聊天室、 增益集和類別 （並因此取得這些類別的使用者存取），與 Persistent Chat Server 集區的設定。</span><span class="sxs-lookup"><span data-stu-id="c85e4-184">Anyone who is a member of this RBAC role can manage chat rooms, add-ins, and categories (and therefore gain user access for these categories), and configuration of the Persistent Chat Server pool.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a><span data-ttu-id="c85e4-185">從群組聊天伺服器舊版不同之處聊天室類別是什麼？</span><span class="sxs-lookup"><span data-stu-id="c85e4-185">What’s Different about Chat Room Categories from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="c85e4-186">聊天室類別可以不再巢狀，而不再修改根類別。</span><span class="sxs-lookup"><span data-stu-id="c85e4-186">Chat room categories can no longer be nested, and the root category can no longer be modified.</span></span> <span data-ttu-id="c85e4-187">AllowedMembers/DeniedMembers 構成 （不同之處在於它不支援指定拒絕清單） 是在舊版的 Group Chat 伺服器版本中使用的範圍。</span><span class="sxs-lookup"><span data-stu-id="c85e4-187">AllowedMembers/DeniedMembers comprise what a scope used to be in legacy Group Chat Server versions (except that it didn’t support specifying a Denied list).</span></span> <span data-ttu-id="c85e4-188">範圍可能不再是覆寫，因為有無巢狀的類別。</span><span class="sxs-lookup"><span data-stu-id="c85e4-188">Scopes can no longer be overridden, because there are no nested categories.</span></span> <span data-ttu-id="c85e4-189">在 Lync Server 2013 常設聊天室系統管理員可以建立及管理聊天室類別。</span><span class="sxs-lookup"><span data-stu-id="c85e4-189">A Persistent Chat Administrator in Lync Server 2013 can create and manage chat room categories.</span></span> <span data-ttu-id="c85e4-190">建立及管理聊天室類別的一部分，常設聊天室管理員可以設定必須是成員/建立者的特定類別的聊天室存取的主體 （Active Directory 群組/容器/使用者）。</span><span class="sxs-lookup"><span data-stu-id="c85e4-190">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="c85e4-191">A Persistent Chat Administrator 某個類別，也可以新增 DeniedMembers 和這些變得明確排除項目，以允許的清單。</span><span class="sxs-lookup"><span data-stu-id="c85e4-191">A Persistent Chat Administrator can also add DeniedMembers to a category, and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="c85e4-192">DeniedMembers 覆寫 AllowedMembers 的功能。</span><span class="sxs-lookup"><span data-stu-id="c85e4-192">DeniedMembers override what’s in AllowedMembers.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a><span data-ttu-id="c85e4-193">從群組聊天伺服器舊版不同之處聊天室屬性是什麼？</span><span class="sxs-lookup"><span data-stu-id="c85e4-193">What’s Different about Chat Room Properties from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="c85e4-194">Lync Server 2013，Persistent Chat Server 中有開啟的聊天室的新概念。</span><span class="sxs-lookup"><span data-stu-id="c85e4-194">A new concept of open chat rooms exists in Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="c85e4-195">所有允許的成員可加入聊天室時亦可，沒有獨佔成員資格。</span><span class="sxs-lookup"><span data-stu-id="c85e4-195">All allowed members can join the chat room, without exclusive membership.</span></span>

<span data-ttu-id="c85e4-196">已消除舊版 Persistent Chat Server 中所含的下列聊天室屬性：</span><span class="sxs-lookup"><span data-stu-id="c85e4-196">The following chat room properties that were included in previous versions of Persistent Chat Server have been eliminated:</span></span>

  - <span data-ttu-id="c85e4-197">主題內容： 會議室現在只有描述。</span><span class="sxs-lookup"><span data-stu-id="c85e4-197">Topic: A Room now only has a Description.</span></span>

  - <span data-ttu-id="c85e4-198">建立新成員清單： 中 Persistent Chat Server，所有聊天室開頭為空的成員資格 （和成員資格等於允許的成員可以最大化）。</span><span class="sxs-lookup"><span data-stu-id="c85e4-198">Create New Member list: In Persistent Chat Server, all chat rooms start with empty membership (and can maximize to a membership equaling the Allowed Members).</span></span>

  - <span data-ttu-id="c85e4-199">檔案上傳： 用來為每個控制項的聊天室的設定是否允許檔案上傳/下載。</span><span class="sxs-lookup"><span data-stu-id="c85e4-199">File Upload: Used to be a setting per chat room to control whether file upload/downloads were allowed.</span></span> <span data-ttu-id="c85e4-200">這現在已設定類別層級，並套用至該類別中的所有會議室。</span><span class="sxs-lookup"><span data-stu-id="c85e4-200">This is now set only the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="c85e4-201">聊天歷程記錄： 用來如果聊天歷程記錄已啟用，但現在已設定只在類別層級，並將套用至該類別中的所有聊天室是每個控制項的聊天室的設定。</span><span class="sxs-lookup"><span data-stu-id="c85e4-201">Chat History: Used to be a setting per chat room to control if Chat History was enabled, but is now set only at the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="c85e4-202">邀請： 會議室一律會繼承邀請類別; 設定或者，它可以關閉在會議室。</span><span class="sxs-lookup"><span data-stu-id="c85e4-202">Invites: A room always inherits the Invites setting for the category; or it can be turned off on the room.</span></span> <span data-ttu-id="c85e4-203">如果類別先前已設定為邀請 Invite 無法開啟會議室。</span><span class="sxs-lookup"><span data-stu-id="c85e4-203">A room cannot turn on Invites if the category was previously set to Invites off.</span></span>

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a><span data-ttu-id="c85e4-204">從群組聊天伺服器舊版不同之處原則是什麼？</span><span class="sxs-lookup"><span data-stu-id="c85e4-204">What’s Different about Policies from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="c85e4-205">Persistent Chat Server 有新的 Lync 原則啟用常設聊天室]，每個使用者/集區/網站/全域設定。</span><span class="sxs-lookup"><span data-stu-id="c85e4-205">Persistent Chat Server has a new Lync policy enabled with Persistent Chat, per user/pool/site/global settings.</span></span> <span data-ttu-id="c85e4-206">在 Lync 2013 用戶端的常設聊天室的環境是僅供由原則啟用常設聊天室的使用者 （直接或透過集區/網站/通用設定）。</span><span class="sxs-lookup"><span data-stu-id="c85e4-206">In the Lync 2013 client, the Persistent Chat environment is available only for users who are enabled by policy for Persistent Chat (either directly or through the pool/site/global setting).</span></span>

<span data-ttu-id="c85e4-207">舊版 Group Chat 伺服器並沒有任何已整合到 Lync Server 原則的原則。</span><span class="sxs-lookup"><span data-stu-id="c85e4-207">Previous versions of Group Chat Server did not have any policies integrated into the Lync Server policies.</span></span> <span data-ttu-id="c85e4-208">在每次使用者與每個類別/會議室為基礎，使用每個使用者功能，**可以上傳檔案**您無法讓使用者的使用者系統管理員，聊天室管理員，或設定使用者能夠將檔案上傳。</span><span class="sxs-lookup"><span data-stu-id="c85e4-208">On a per user and per category/room basis, by using the **Can Upload Files** per user feature, you could make the user a User administrator, a chat room administrator, or configure the user’s ability to upload files.</span></span> <span data-ttu-id="c85e4-209">Persistent Chat Server**檔案上傳**功能就只是每個類別。</span><span class="sxs-lookup"><span data-stu-id="c85e4-209">The Persistent Chat Server **File Upload** feature is just per category.</span></span>

</div>

<div>

## <a name="logging"></a><span data-ttu-id="c85e4-210">記錄</span><span class="sxs-lookup"><span data-stu-id="c85e4-210">Logging</span></span>

<span data-ttu-id="c85e4-211">Persistent Chat Server 及 System Center Operations Manager 的記錄已整合至 Lync Server 2013 追蹤記錄。</span><span class="sxs-lookup"><span data-stu-id="c85e4-211">Logging for Persistent Chat Server and System Center Operations Manager is integrated into the Lync Server 2013 trace logging.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c85e4-212">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c85e4-212">See Also</span></span>


[<span data-ttu-id="c85e4-213">規劃 Lync Server 2013 中的常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="c85e4-213">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

