---
title: Lync Server 2013：新常設聊天室伺服器功能
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
ms.openlocfilehash: fe207d2469a36d880e9ed519ff1d47d942ed79aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a><span data-ttu-id="46f38-102">Lync Server 2013 中的新常設聊天室伺服器功能</span><span class="sxs-lookup"><span data-stu-id="46f38-102">New Persistent Chat Server features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46f38-103">_**主題上次修改日期：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="46f38-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="46f38-104">Lync Server 2013，持續聊天伺服器可讓您參與多方、依時間保留的、以主題為基礎的交談。</span><span class="sxs-lookup"><span data-stu-id="46f38-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="46f38-105">持續聊天伺服器可協助您的組織執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="46f38-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="46f38-106">改善地理位置分散且跨職能團隊之間的溝通</span><span class="sxs-lookup"><span data-stu-id="46f38-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="46f38-107">拓寬資訊意識及參與情況</span><span class="sxs-lookup"><span data-stu-id="46f38-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="46f38-108">改善與您的延伸組織的溝通</span><span class="sxs-lookup"><span data-stu-id="46f38-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="46f38-109">減少資訊超載</span><span class="sxs-lookup"><span data-stu-id="46f38-109">Reduce information overload</span></span>

  - <span data-ttu-id="46f38-110">改善資訊意識</span><span class="sxs-lookup"><span data-stu-id="46f38-110">Improve information awareness</span></span>

  - <span data-ttu-id="46f38-111">增加重要知識與資訊的散佈</span><span class="sxs-lookup"><span data-stu-id="46f38-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="46f38-112">Lync Server 2013，在 Microsoft Office 365 中無法使用持續聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="46f38-112">Lync Server 2013, Persistent Chat Server is not available in Microsoft Office 365.</span></span> <span data-ttu-id="46f38-113">目前，它只能供內部部署的 Lync 2013 客戶使用。</span><span class="sxs-lookup"><span data-stu-id="46f38-113">At this time, it is available only to on-premise Lync 2013 customers.</span></span>

<span data-ttu-id="46f38-114">在 Lync 2013 中，持續性聊天功能已整合至 Lync 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="46f38-114">In Lync 2013, Persistent Chat functionality is integrated into the Lync 2013 client.</span></span> <span data-ttu-id="46f38-115">因此，使用者可以在 Lync 2013 用戶端中存取立即訊息/目前狀態、音訊/視頻、會議和持續聊天。</span><span class="sxs-lookup"><span data-stu-id="46f38-115">As a result, users have access to Instant Messaging/Presence, Audio/Video, Conferencing, and Persistent Chat all in the Lync 2013 client.</span></span> <span data-ttu-id="46f38-116">如需 Lync 2013 用戶端的詳細資訊， <http://go.microsoft.com/fwlink/p/?linkid=270877>請參閱。</span><span class="sxs-lookup"><span data-stu-id="46f38-116">For more information about the Lync 2013 client, see <http://go.microsoft.com/fwlink/p/?linkid=270877>.</span></span>

<span data-ttu-id="46f38-117">本主題描述新版 Lync Server 2013、持續聊天伺服器與舊版（Microsoft Lync Server 2010、群組聊天）之間的功能變更，包括：</span><span class="sxs-lookup"><span data-stu-id="46f38-117">This topic describes feature changes between the new version of Lync Server 2013, Persistent Chat Server and the previous version (Microsoft Lync Server 2010, Group Chat), including:</span></span>

  - <span data-ttu-id="46f38-118">在 Lync Server [控制台] 中提供管理體驗，並消除群組聊天系統管理工具</span><span class="sxs-lookup"><span data-stu-id="46f38-118">Provide an administrative experience in Lync Server Control Panel, and eliminate the Group Chat Admin Tool</span></span>

  - <span data-ttu-id="46f38-119">透過去除群組聊天設定工具，將持續聊天伺服器的設定設定整合到拓撲建立器中</span><span class="sxs-lookup"><span data-stu-id="46f38-119">Integrate configuration settings for Persistent Chat Server into Topology Builder by eliminating the Group Chat Configuration tool</span></span>

  - <span data-ttu-id="46f38-120">輕鬆從舊版的持久性聊天伺服器進行遷移和升級</span><span class="sxs-lookup"><span data-stu-id="46f38-120">Ease migration and upgrade from previous versions of Persistent Chat Server</span></span>

  - <span data-ttu-id="46f38-121">提供高可用性與災害復原解決方案</span><span class="sxs-lookup"><span data-stu-id="46f38-121">Provide high availability and disaster recovery solutions</span></span>

<span data-ttu-id="46f38-122">如需最新版本持久性聊天伺服器的其他詳細資料，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="46f38-122">For additional details about the latest version of Persistent Chat Server, see the following:</span></span>

  - <span data-ttu-id="46f38-123">持續性聊天<http://go.microsoft.com/fwlink/p/?linkid=270945>說明，提供持續聊天功能的詳細清單、運作方式，以及如何在執行持續聊天伺服器時使用它們。</span><span class="sxs-lookup"><span data-stu-id="46f38-123">The Persistent Chat Help at <http://go.microsoft.com/fwlink/p/?linkid=270945> which provides a detailed list of Persistent Chat features, how they work, and how to use them while running Persistent Chat Server.</span></span>

  - <span data-ttu-id="46f38-124">規劃檔中的[Lync server 2013 中的持續聊天伺服器規劃](lync-server-2013-planning-for-persistent-chat-server.md)，在[lync server 2013](lync-server-2013-deploying-persistent-chat-server.md)的 [部署] 檔中部署持續式聊天伺服器[，從 Lync Server 2010 升級，群組聊天或 Office 通訊伺服器 2007 R2 群組聊天至 Lync Server 2013、持續聊天伺服器](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)在作業檔中，以及在操作檔中[管理 lync server 2013 （持續聊天伺服器](managing-lync-server-2013-persistent-chat-server.md)），所有這些都提供有關設定的指示。持續聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="46f38-124">The [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation, [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) in the Migration documentation, and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) in the Operations documentation, all of which provide instructions for setting up Persistent Chat Server.</span></span>

  - <span data-ttu-id="46f38-125">永久聊天伺服器檔（Windows 安裝程式檔案）可讓使用者存取持續聊天伺服器的完整離線檔。</span><span class="sxs-lookup"><span data-stu-id="46f38-125">The Persistent Chat Server Documentation.msi file (Windows Installer file) lets users access comprehensive offline documentation about Persistent Chat Server.</span></span>

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a><span data-ttu-id="46f38-126">持久聊天伺服器的重要拓撲變更</span><span class="sxs-lookup"><span data-stu-id="46f38-126">Key Topology Changes for Persistent Chat Server</span></span>

<span data-ttu-id="46f38-127">持續聊天伺服器的下列高層次變更包括：</span><span class="sxs-lookup"><span data-stu-id="46f38-127">The following high-level changes for Persistent Chat Server include:</span></span>

<span data-ttu-id="46f38-128">持續聊天伺服器現在是一個伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="46f38-128">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="46f38-129">在 Microsoft Lync Server 2010 中，群組聊天伺服器是適用于 Microsoft Lync Server 2010 的協力廠商信任應用程式。</span><span class="sxs-lookup"><span data-stu-id="46f38-129">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="46f38-130">您可以使用拓撲結構建立器，將持續式聊天新增至您的 Lync Server 2013 拓撲。</span><span class="sxs-lookup"><span data-stu-id="46f38-130">Persistent Chat can be added to your Lync Server 2013 topology by using Topology Builder.</span></span> <span data-ttu-id="46f38-131">在 Lync Server 2013 中，持續聊天伺服器功能是使用三個新的伺服器角色來實現：</span><span class="sxs-lookup"><span data-stu-id="46f38-131">In Lync Server 2013, Persistent Chat Server functionality is implemented by using three new server roles:</span></span>

  - <span data-ttu-id="46f38-132">**PersistentChatService：** 這是持續聊天的前端角色。</span><span class="sxs-lookup"><span data-stu-id="46f38-132">**PersistentChatService:** This is the front end role for Persistent Chat.</span></span> <span data-ttu-id="46f38-133">在標準版部署中，Persistent 是由引導程式部署的標準版伺服器（例如任何其他 Lync 伺服器角色）來 collocated 持久聊天伺服器服務角色。</span><span class="sxs-lookup"><span data-stu-id="46f38-133">In Standard Edition deployments, Persistent Chat Server Service Role is collocated on the Standard Edition server deployed by Bootstrapper, like any other Lync Server role.</span></span> <span data-ttu-id="46f38-134">在企業版部署中，系統會在獨立電腦上以引導程式（例如任何其他 Lync 伺服器角色）來部署持久聊天服務角色。</span><span class="sxs-lookup"><span data-stu-id="46f38-134">In Enterprise Edition deployments, Persistent Chat Service Role is deployed on stand-alone computers by Bootstrapper, like any other Lync Server role.</span></span>

  - <span data-ttu-id="46f38-135">**PersistentChatStore：** 與持久聊天內容資料庫對應的後端伺服器，其中所有的聊天內容都儲存在其中。</span><span class="sxs-lookup"><span data-stu-id="46f38-135">**PersistentChatStore:** Back End Server that corresponds to the Persistent Chat content database, where all the chat content is stored.</span></span>

  - <span data-ttu-id="46f38-136">**PersistentChatComplianceStore：** 與持久聊天規範資料庫相對應的後端伺服器角色，所有符合性事件都會儲存在其中。</span><span class="sxs-lookup"><span data-stu-id="46f38-136">**PersistentChatComplianceStore:** Back End Server role that corresponds to the Persistent Chat Compliance database, where all compliance events are stored.</span></span>

<span data-ttu-id="46f38-137">這些持續聊天伺服器角色是選擇性的，而且只由想要全面持久聊天伺服器功能的客戶所安裝。</span><span class="sxs-lookup"><span data-stu-id="46f38-137">These Persistent Chat Server roles are optional, and are installed only by customers who want comprehensive Persistent Chat Server functionality.</span></span> <span data-ttu-id="46f38-138">只有在您選擇部署持續性聊天規範時，才需要**PersistentChatComplianceStore**角色。</span><span class="sxs-lookup"><span data-stu-id="46f38-138">The **PersistentChatComplianceStore** role is needed only if you choose to deploy Persistent Chat Compliance.</span></span>

<span data-ttu-id="46f38-139">**PersistentChatService**角色會執行兩個服務：</span><span class="sxs-lookup"><span data-stu-id="46f38-139">The **PersistentChatService** role runs two services:</span></span>

  - <span data-ttu-id="46f38-140">持續聊天服務</span><span class="sxs-lookup"><span data-stu-id="46f38-140">Persistent Chat service</span></span>

  - <span data-ttu-id="46f38-141">持續聊天相容性服務</span><span class="sxs-lookup"><span data-stu-id="46f38-141">Persistent Chat Compliance service</span></span>

<span data-ttu-id="46f38-142">在每個持續聊天伺服器上執行這些服務，即可在多伺服器持久性聊天伺服器池中提供這些服務的高可用性。</span><span class="sxs-lookup"><span data-stu-id="46f38-142">Having these services run on each Persistent Chat Server provides high availability for these services in a multiserver Persistent Chat Server pool.</span></span>

<span data-ttu-id="46f38-143">此外，若要支援在持續聊天室中的檔案上傳和下載，持續聊天伺服器會包含 web 服務。</span><span class="sxs-lookup"><span data-stu-id="46f38-143">Additionally, to support the file upload and download in Persistent Chat rooms, Persistent Chat Server includes a web service.</span></span> <span data-ttu-id="46f38-144">之前，此服務是在持久聊天伺服器、前端伺服器以及必要的網際網路資訊服務（IIS）上 collocated，以作為先決條件來安裝。</span><span class="sxs-lookup"><span data-stu-id="46f38-144">Previously, this service was collocated on the Persistent Chat Server, Front End Server and required Internet Information Services (IIS) to be installed as a prerequisite.</span></span> <span data-ttu-id="46f38-145">在 Lync Server 2013 永久聊天伺服器中，檔案上傳/下載 web 服務是與 Lync Server 2013 前端伺服器 collocated。</span><span class="sxs-lookup"><span data-stu-id="46f38-145">In Lync Server 2013 Persistent Chat Server, the File Upload/Download web service is collocated with the Lync Server 2013 Front End Server.</span></span> <span data-ttu-id="46f38-146">如果是副作用，網際網路資訊服務（IIS）已不再是持久聊天伺服器的先決條件。</span><span class="sxs-lookup"><span data-stu-id="46f38-146">As a side effect, Internet Information Services (IIS) is no longer a prerequisite for Persistent Chat Server.</span></span> <span data-ttu-id="46f38-147">檔案上傳/下載 web 服務在網際網路資訊服務（IIS）管理員中會被識別為**PersistentChat** 。</span><span class="sxs-lookup"><span data-stu-id="46f38-147">The File Upload/Download web service is identified as **PersistentChat** in the Internet Information Services (IIS) Manager.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="46f38-148">只有當前端伺服器是標準版&nbsp;前端伺服器時， <STRONG>PersistentChatService</STRONG>角色才能&nbsp;在與 Lync server 2013 前端伺服器相同的伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="46f38-148">The <STRONG>PersistentChatService</STRONG> role can run on the same server as a Lync Server 2013&nbsp;Front End Server only if that Front End Server is a Standard Edition&nbsp;Front End Server.</span></span> <span data-ttu-id="46f38-149"><STRONG>PersistentChatService</STRONG>角色無法獨立于 Lync server 2013&nbsp;前端伺服器執行。</span><span class="sxs-lookup"><span data-stu-id="46f38-149">The <STRONG>PersistentChatService</STRONG> role cannot run independently of a Lync Server 2013&nbsp;Front End Server.</span></span> <span data-ttu-id="46f38-150">它只能安裝在 Lync Server 2013 部署的內容中。</span><span class="sxs-lookup"><span data-stu-id="46f38-150">It can be installed only in the context of a Lync Server 2013 deployment.</span></span>



</div>

<span data-ttu-id="46f38-151">在永久聊天伺服器中，已消除查閱服務。</span><span class="sxs-lookup"><span data-stu-id="46f38-151">In Persistent Chat Server, Lookup service has been eliminated.</span></span> <span data-ttu-id="46f38-152">在 Lync Server 2010 中，[群組聊天] 會在每個群組聊天伺服器前端伺服器上執行查閱服務，並執行路由至其中一個頻道伺服器。</span><span class="sxs-lookup"><span data-stu-id="46f38-152">In Lync Server 2010, Group Chat, the Lookup service ran on every Group Chat Server Front End Server, and performed routing to one of the Channel Servers.</span></span> <span data-ttu-id="46f38-153">Lync Server 2013 依賴連絡人物件來傳送的方式，其中每個持續聊天伺服器池都是由 Lync Server 前端伺服器所使用的連絡人物件所代表，並將要求傳送到適當的持續聊天伺服器池，以及在池中執行持續聊天伺服器的其中一個電腦。</span><span class="sxs-lookup"><span data-stu-id="46f38-153">Lync Server 2013 relies on routing by using contact objects, where each Persistent Chat Server pool is represented by a contact object that is used by the Lync Server Front End Servers to identify and route requests to an appropriate Persistent Chat Server pool, and to one of the computers running Persistent Chat Server in the pool.</span></span>

<span data-ttu-id="46f38-154">在 Lync Server 2013 中，有合規性服務修改：</span><span class="sxs-lookup"><span data-stu-id="46f38-154">In Lync Server 2013, there are Compliance service modifications:</span></span>

  - <span data-ttu-id="46f38-155">在 Lync Server 2010 中，合規性服務會獨立執行（非 collocated），且僅適用于單一伺服器。</span><span class="sxs-lookup"><span data-stu-id="46f38-155">In Lync Server 2010, the Compliance service ran stand-alone (non-collocated), and only on a single server.</span></span> <span data-ttu-id="46f38-156">合規性服務現在會在所有持續聊天伺服器前端伺服器上執行，並在持續性聊天服務上執行，因此可在多伺服器持久聊天伺服器池中提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="46f38-156">The Compliance service now runs on all the Persistent Chat Server Front End Servers, alongside the Persistent Chat service, and thereby provides high availability in a multiserver Persistent Chat Server pool.</span></span> <span data-ttu-id="46f38-157">您可以將單一合規性配接器設定為從合規性資料庫和其他其中一個系統（XML 檔案、Exchange 託管的歸檔等）提取資料。</span><span class="sxs-lookup"><span data-stu-id="46f38-157">A single compliance adapter can be configured to extract data from the compliance database and into one of the other systems (XML file, Exchange-hosted archives, and so on).</span></span> <span data-ttu-id="46f38-158">持續聊天伺服器包括 XML 配接器。</span><span class="sxs-lookup"><span data-stu-id="46f38-158">Persistent Chat Server includes an XML adapter.</span></span>

  - <span data-ttu-id="46f38-159">持續式聊天服務和每個持續聊天伺服器前端伺服器所共用的 [訊息佇列] （又稱為 MSMQ）佇列現在都是由兩個服務共用的私用佇列。</span><span class="sxs-lookup"><span data-stu-id="46f38-159">The Message Queuing (also known as MSMQ) queue that is shared by the Persistent Chat service and the Compliance service on each Persistent Chat Server Front End Server is now a private queue shared only by the two services.</span></span> <span data-ttu-id="46f38-160">所有合規性服務將寫入相同的規範後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="46f38-160">All compliance services write to the same Compliance Back End database.</span></span> <span data-ttu-id="46f38-161">它們也會從該資料庫讀取，目的是將資料傳送到其配接器的實例。</span><span class="sxs-lookup"><span data-stu-id="46f38-161">They also all read from that database, for the purpose of sending the data to their instance of the adapter.</span></span> <span data-ttu-id="46f38-162">相容性後端伺服器會以新的後端伺服器角色表示。</span><span class="sxs-lookup"><span data-stu-id="46f38-162">The Compliance Back End Server is represented as a new Back End Server role.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="46f38-163">就像在舊版中一樣，所有合規性資料只會處理一次。</span><span class="sxs-lookup"><span data-stu-id="46f38-163">As in previous versions, all compliance data is processed only once.</span></span> <span data-ttu-id="46f38-164">資料可能是由在各種 Lync Server 2013、持續聊天伺服器電腦上執行的規範服務所呼叫的任何配接器實例所處理。</span><span class="sxs-lookup"><span data-stu-id="46f38-164">The data may be processed by any of the adapter instances invoked by the compliance service running on the various Lync Server 2013, Persistent Chat Server computers.</span></span> <span data-ttu-id="46f38-165">在永久聊天伺服器中，任何一個配接器實例都可以處理資料。</span><span class="sxs-lookup"><span data-stu-id="46f38-165">In Persistent Chat Server, any one of the adapter instances could process the data.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="46f38-166">如需安裝訊息佇列的相關資訊，請參閱部署檔中的<A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Lync Server 2013 的安裝作業系統和必備軟體</A>。</span><span class="sxs-lookup"><span data-stu-id="46f38-166">For information about installing Message Queuing, see <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Install operating systems and prerequisite software on servers for Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="46f38-167">在 Lync Server 2013 中，在高可用性和災害復原中都有一些改良功能：</span><span class="sxs-lookup"><span data-stu-id="46f38-167">In Lync Server 2013, there are improvements in both high availability and disaster recovery:</span></span>

  - <span data-ttu-id="46f38-168">高可用性改良：您可以使用 SQL Server 鏡像，在資料中心（網站內）中，為持續性聊天伺服器內容資料庫和持續交談合規性資料庫提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="46f38-168">High availability improvements: SQL Server mirroring is used to provide high availability for the Persistent Chat Server content database and Persistent Chat compliance database within a data center (in-site).</span></span>

  - <span data-ttu-id="46f38-169">災難復原改良功能：持續性聊天伺服器支援延伸池架構，可讓單一持久聊天伺服器池延伸到兩個網站（也就是拓撲結構中的單一邏輯池），並以物理方式存放在池中的伺服器位於兩個網站上）。</span><span class="sxs-lookup"><span data-stu-id="46f38-169">Disaster recovery improvements: Persistent Chat Server supports a stretched pool architecture that enables a single Persistent Chat Server pool to be stretched across two sites (that is, a single logical pool in the topology, with servers in the pool physically located across two sites).</span></span> <span data-ttu-id="46f38-170">SQL Server 記錄傳送是用於跨網站災害復原。</span><span class="sxs-lookup"><span data-stu-id="46f38-170">SQL Server Log Shipping is used for cross-site disaster recovery.</span></span>

<span data-ttu-id="46f38-171">如需高可用性和災難復原的詳細資訊，請參閱在部署檔中[針對 Lync server 2013 的高可用性和災難復原設定持久聊天伺服器](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="46f38-171">For more information about high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a><span data-ttu-id="46f38-172">持久聊天伺服器的主要管理與管理變更</span><span class="sxs-lookup"><span data-stu-id="46f38-172">Key Administration and Management Changes for Persistent Chat Server</span></span>

<span data-ttu-id="46f38-173">Lync Server 2013 可讓您更輕鬆地管理和管理持久聊天伺服器，只要提供：</span><span class="sxs-lookup"><span data-stu-id="46f38-173">Lync Server 2013 has made it easier to administer and manage Persistent Chat Server by providing:</span></span>

  - <span data-ttu-id="46f38-174">整合管理和管理。</span><span class="sxs-lookup"><span data-stu-id="46f38-174">Unified administration and management.</span></span> <span data-ttu-id="46f38-175">Lync Server 2013 可讓您更輕鬆地使用 Lync 系統管理員熟悉的工具來管理和管理持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="46f38-175">Lync Server 2013 makes it easier to manage and administer Persistent Chat Server by using tools that are already familiar to Lync administrators.</span></span> <span data-ttu-id="46f38-176">持續聊天伺服器包含與 Lync Server 控制台整合的系統管理使用者介面體驗，可解決舊版群組聊天伺服器使用者介面的效能問題。</span><span class="sxs-lookup"><span data-stu-id="46f38-176">Persistent Chat Server includes an administrative user interface experience that is integrated with the Lync Server Control Panel, which addresses performance issues with the previous versions of the Group Chat Server user interface.</span></span> <span data-ttu-id="46f38-177">此外，持續聊天伺服器還包含一組 Windows PowerShell Cmdlet，可用於管理及管理持久聊天伺服器類別、持續聊天伺服器機房（包括刪除聊天室及清除過時的內容）和增益集。</span><span class="sxs-lookup"><span data-stu-id="46f38-177">Also, Persistent Chat Server includes a collection of Windows PowerShell cmdlets to administer and manage Persistent Chat Server categories, Persistent Chat Server rooms (including deleting rooms and purging obsolete content), and add-ins.</span></span>

  - <span data-ttu-id="46f38-178">簡化的管理模型。</span><span class="sxs-lookup"><span data-stu-id="46f38-178">Simplified administration model.</span></span> <span data-ttu-id="46f38-179">Lync Server 2013 通過解決下列重要客戶需求，來變更並簡化持續聊天伺服器模型：</span><span class="sxs-lookup"><span data-stu-id="46f38-179">Lync Server 2013 has changed and simplified the Persistent Chat Server model by addressing the following key customer requirements:</span></span>
    
      - <span data-ttu-id="46f38-180">移除範圍與類別的複雜嵌套層次結構。</span><span class="sxs-lookup"><span data-stu-id="46f38-180">Remove the complex nested hierarchies of scopes and categories.</span></span>
    
      - <span data-ttu-id="46f38-181">支援以定義拒絕清單以及目前 MindAlign 客戶的允許清單（範圍），這些客戶正在規劃遷移至持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="46f38-181">Support to define deny lists as well as allowed lists (scopes) for current MindAlign customers who are planning to migrate to Persistent Chat Server.</span></span>

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a><span data-ttu-id="46f38-182">先前群組聊天伺服器版本中的使用者角色有何不同？</span><span class="sxs-lookup"><span data-stu-id="46f38-182">What’s Different about User Roles from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="46f38-183">Lync Server 2010，群組聊天擁有使用者系統管理員角色、聊天室管理員角色，以及可管理增益集的 Lync Server 管理員角色。持續聊天伺服器只提供永久性聊天管理員角色（類似其他 Lync）伺服器角色的存取控制（RBAC）角色）。</span><span class="sxs-lookup"><span data-stu-id="46f38-183">Lync Server 2010, Group Chat had a user administrator role, a chat room administrator role and a Lync Server administrator role that could manage add-ins. Persistent Chat Server simply provides a Persistent Chat Administrator role (which is similar to other Lync Server role-based access control (RBAC) roles).</span></span> <span data-ttu-id="46f38-184">任何擁有此 RBAC 角色成員的人都可以管理聊天室、增益集及類別（因此，您可以取得這些類別的使用者存取），以及設定持久聊天伺服器池。</span><span class="sxs-lookup"><span data-stu-id="46f38-184">Anyone who is a member of this RBAC role can manage chat rooms, add-ins, and categories (and therefore gain user access for these categories), and configuration of the Persistent Chat Server pool.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a><span data-ttu-id="46f38-185">從先前的群組聊天伺服器版本，聊天室類別有何不同？</span><span class="sxs-lookup"><span data-stu-id="46f38-185">What’s Different about Chat Room Categories from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="46f38-186">聊天室類別無法再嵌套，且無法再修改根類別。</span><span class="sxs-lookup"><span data-stu-id="46f38-186">Chat room categories can no longer be nested, and the root category can no longer be modified.</span></span> <span data-ttu-id="46f38-187">AllowedMembers/DeniedMembers 包含在舊版群組聊天伺服器版本中使用的範圍（除了不支援指定拒絕清單之外）。</span><span class="sxs-lookup"><span data-stu-id="46f38-187">AllowedMembers/DeniedMembers comprise what a scope used to be in legacy Group Chat Server versions (except that it didn’t support specifying a Denied list).</span></span> <span data-ttu-id="46f38-188">因為沒有嵌套類別，所以不能再重寫範圍。</span><span class="sxs-lookup"><span data-stu-id="46f38-188">Scopes can no longer be overridden, because there are no nested categories.</span></span> <span data-ttu-id="46f38-189">Lync Server 2013 中的持續聊天系統管理員可以建立和管理聊天室類別。</span><span class="sxs-lookup"><span data-stu-id="46f38-189">A Persistent Chat Administrator in Lync Server 2013 can create and manage chat room categories.</span></span> <span data-ttu-id="46f38-190">在建立及管理聊天室類別的過程中，持續性聊天管理員可以設定擁有權的主體（Active Directory 群組/容器/使用者），這些使用者有權存取屬於特定類別之聊天室的成員/提供者。</span><span class="sxs-lookup"><span data-stu-id="46f38-190">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="46f38-191">持續聊天管理員也可以在類別中新增 DeniedMembers，並將它們變成 [允許] 清單的明確排除。</span><span class="sxs-lookup"><span data-stu-id="46f38-191">A Persistent Chat Administrator can also add DeniedMembers to a category, and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="46f38-192">DeniedMembers 會覆寫 AllowedMembers 中的內容。</span><span class="sxs-lookup"><span data-stu-id="46f38-192">DeniedMembers override what’s in AllowedMembers.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a><span data-ttu-id="46f38-193">聊天室屬性與舊版群組聊天伺服器版本有何不同？</span><span class="sxs-lookup"><span data-stu-id="46f38-193">What’s Different about Chat Room Properties from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="46f38-194">Lync Server 2013 （持久聊天伺服器）中存在開啟聊天室的新概念。</span><span class="sxs-lookup"><span data-stu-id="46f38-194">A new concept of open chat rooms exists in Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="46f38-195">所有允許的成員都可以加入聊天室，而不需要獨佔成員資格。</span><span class="sxs-lookup"><span data-stu-id="46f38-195">All allowed members can join the chat room, without exclusive membership.</span></span>

<span data-ttu-id="46f38-196">已消除舊版持久性聊天伺服器中所包含的下列聊天室屬性：</span><span class="sxs-lookup"><span data-stu-id="46f38-196">The following chat room properties that were included in previous versions of Persistent Chat Server have been eliminated:</span></span>

  - <span data-ttu-id="46f38-197">主題：聊天室現在只有描述。</span><span class="sxs-lookup"><span data-stu-id="46f38-197">Topic: A Room now only has a Description.</span></span>

  - <span data-ttu-id="46f38-198">[建立新成員清單]：在永久聊天伺服器中，所有聊天室都是以空的成員資格開始（並且可以最大化到允許成員 equaling 的成員資格）。</span><span class="sxs-lookup"><span data-stu-id="46f38-198">Create New Member list: In Persistent Chat Server, all chat rooms start with empty membership (and can maximize to a membership equaling the Allowed Members).</span></span>

  - <span data-ttu-id="46f38-199">檔案上傳：您可以用來設定每個聊天室的設定，以控制是否允許檔案上傳/下載。</span><span class="sxs-lookup"><span data-stu-id="46f38-199">File Upload: Used to be a setting per chat room to control whether file upload/downloads were allowed.</span></span> <span data-ttu-id="46f38-200">現在，這只會設定類別等級，並套用至該類別中的所有聊天室。</span><span class="sxs-lookup"><span data-stu-id="46f38-200">This is now set only the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="46f38-201">聊天記錄：用來設定每個聊天室的設定，以控制是否已啟用聊天記錄，但現在只會在類別層級設定，並套用到該類別中的所有聊天室。</span><span class="sxs-lookup"><span data-stu-id="46f38-201">Chat History: Used to be a setting per chat room to control if Chat History was enabled, but is now set only at the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="46f38-202">邀請：會議室永遠會繼承類別的 [邀請] 設定;或者，您可以在聊天室中關閉該檔案。</span><span class="sxs-lookup"><span data-stu-id="46f38-202">Invites: A room always inherits the Invites setting for the category; or it can be turned off on the room.</span></span> <span data-ttu-id="46f38-203">如果該類別先前已設定為 [邀請]，會議室就無法開啟邀請。</span><span class="sxs-lookup"><span data-stu-id="46f38-203">A room cannot turn on Invites if the category was previously set to Invites off.</span></span>

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a><span data-ttu-id="46f38-204">舊版群組聊天伺服器版本中的原則有何不同？</span><span class="sxs-lookup"><span data-stu-id="46f38-204">What’s Different about Policies from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="46f38-205">持續聊天伺服器已啟用新的 Lync 原則，且持續聊天、每個使用者/池/網站/全域設定。</span><span class="sxs-lookup"><span data-stu-id="46f38-205">Persistent Chat Server has a new Lync policy enabled with Persistent Chat, per user/pool/site/global settings.</span></span> <span data-ttu-id="46f38-206">在 Lync 2013 用戶端中，只有透過策略來啟用持續聊天（直接或透過 [池/網站/全域設定]）的使用者，才能使用持續式聊天環境。</span><span class="sxs-lookup"><span data-stu-id="46f38-206">In the Lync 2013 client, the Persistent Chat environment is available only for users who are enabled by policy for Persistent Chat (either directly or through the pool/site/global setting).</span></span>

<span data-ttu-id="46f38-207">舊版的群組聊天伺服器沒有任何整合到 Lync 伺服器原則的原則。</span><span class="sxs-lookup"><span data-stu-id="46f38-207">Previous versions of Group Chat Server did not have any policies integrated into the Lync Server policies.</span></span> <span data-ttu-id="46f38-208">在每位使用者和每個類別/房間基礎上，使用 [**可以上傳**檔案的每個使用者] 功能，您就可以讓使用者成為使用者系統管理員、聊天室管理員，或設定使用者上傳檔案的能力。</span><span class="sxs-lookup"><span data-stu-id="46f38-208">On a per user and per category/room basis, by using the **Can Upload Files** per user feature, you could make the user a User administrator, a chat room administrator, or configure the user’s ability to upload files.</span></span> <span data-ttu-id="46f38-209">持續聊天伺服器檔案**上傳**功能只針對每個類別。</span><span class="sxs-lookup"><span data-stu-id="46f38-209">The Persistent Chat Server **File Upload** feature is just per category.</span></span>

</div>

<div>

## <a name="logging"></a><span data-ttu-id="46f38-210">記錄</span><span class="sxs-lookup"><span data-stu-id="46f38-210">Logging</span></span>

<span data-ttu-id="46f38-211">持續聊天伺服器與 System Center Operations Manager 的記錄功能已整合至 Lync Server 2013 追蹤記錄。</span><span class="sxs-lookup"><span data-stu-id="46f38-211">Logging for Persistent Chat Server and System Center Operations Manager is integrated into the Lync Server 2013 trace logging.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="46f38-212">請參閱</span><span class="sxs-lookup"><span data-stu-id="46f38-212">See Also</span></span>


[<span data-ttu-id="46f38-213">在 Lync Server 2013 中規劃常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="46f38-213">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

