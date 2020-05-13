---
title: Lync Server 2013：新的持久聊天伺服器功能
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
ms.openlocfilehash: 6203e6a7ee99f4b080fa93976a2a937e62fe9d3c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a><span data-ttu-id="53641-102">Lync Server 2013 中的新 Persistent Chat Server 功能</span><span class="sxs-lookup"><span data-stu-id="53641-102">New Persistent Chat Server features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53641-103">_**主題上次修改日期：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="53641-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="53641-104">Lync Server 2013，Persistent Chat Server 可讓您加入一段時間內的多方、主題型交談。</span><span class="sxs-lookup"><span data-stu-id="53641-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="53641-105">Persistent Chat Server 可以協助貴組織執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="53641-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="53641-106">改進地理位置分散且跨部門之小組間的通訊</span><span class="sxs-lookup"><span data-stu-id="53641-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="53641-107">擴大資訊傳達和參與範圍</span><span class="sxs-lookup"><span data-stu-id="53641-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="53641-108">改進大組織的通訊</span><span class="sxs-lookup"><span data-stu-id="53641-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="53641-109">緩和資訊超載的狀況</span><span class="sxs-lookup"><span data-stu-id="53641-109">Reduce information overload</span></span>

  - <span data-ttu-id="53641-110">改進資訊傳達方式</span><span class="sxs-lookup"><span data-stu-id="53641-110">Improve information awareness</span></span>

  - <span data-ttu-id="53641-111">加強重要知識和資訊的傳播</span><span class="sxs-lookup"><span data-stu-id="53641-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="53641-112">Lync Server 2013，在 Microsoft 365 或 Office 365 中無法使用 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="53641-112">Lync Server 2013, Persistent Chat Server is not available in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="53641-113">目前只有內部部署 Lync 2013 客戶可以使用此功能。</span><span class="sxs-lookup"><span data-stu-id="53641-113">At this time, it is available only to on-premise Lync 2013 customers.</span></span>

<span data-ttu-id="53641-114">在 Lync 2013 中，Persistent Chat 功能已整合至 Lync 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="53641-114">In Lync 2013, Persistent Chat functionality is integrated into the Lync 2013 client.</span></span> <span data-ttu-id="53641-115">因此，使用者可以在 Lync 2013 用戶端中存取立即訊息/目前狀態、Audio/Video、會議及持續聊天。</span><span class="sxs-lookup"><span data-stu-id="53641-115">As a result, users have access to Instant Messaging/Presence, Audio/Video, Conferencing, and Persistent Chat all in the Lync 2013 client.</span></span> <span data-ttu-id="53641-116">如需 Lync 2013 用戶端的詳細資訊，請參閱 <https://go.microsoft.com/fwlink/p/?linkid=270877> 。</span><span class="sxs-lookup"><span data-stu-id="53641-116">For more information about the Lync 2013 client, see <https://go.microsoft.com/fwlink/p/?linkid=270877>.</span></span>

<span data-ttu-id="53641-117">本主題說明新版本的 Lync Server 2013、Persistent Chat Server 和舊版（Microsoft Lync Server 2010、群組聊天）之間的功能變更，包括：</span><span class="sxs-lookup"><span data-stu-id="53641-117">This topic describes feature changes between the new version of Lync Server 2013, Persistent Chat Server and the previous version (Microsoft Lync Server 2010, Group Chat), including:</span></span>

  - <span data-ttu-id="53641-118">在 Lync Server 控制台中提供管理體驗，並消除群組聊天管理工具</span><span class="sxs-lookup"><span data-stu-id="53641-118">Provide an administrative experience in Lync Server Control Panel, and eliminate the Group Chat Admin Tool</span></span>

  - <span data-ttu-id="53641-119">透過消除群組聊天設定工具，將 Persistent Chat Server 的設定整合到拓撲產生器中</span><span class="sxs-lookup"><span data-stu-id="53641-119">Integrate configuration settings for Persistent Chat Server into Topology Builder by eliminating the Group Chat Configuration tool</span></span>

  - <span data-ttu-id="53641-120">輕鬆從舊版的持久聊天伺服器遷移和升級</span><span class="sxs-lookup"><span data-stu-id="53641-120">Ease migration and upgrade from previous versions of Persistent Chat Server</span></span>

  - <span data-ttu-id="53641-121">提供高可用性和嚴重損壞修復解決方案</span><span class="sxs-lookup"><span data-stu-id="53641-121">Provide high availability and disaster recovery solutions</span></span>

<span data-ttu-id="53641-122">如需最新版本 Persistent Chat Server 的其他詳細資訊，請參閱下列各項：</span><span class="sxs-lookup"><span data-stu-id="53641-122">For additional details about the latest version of Persistent Chat Server, see the following:</span></span>

  - <span data-ttu-id="53641-123">Persistent Chat <https://go.microsoft.com/fwlink/p/?linkid=270945> 說明，提供持續性聊天功能的詳細清單、運作方式，以及如何在執行 Persistent Chat Server 時使用這些功能。</span><span class="sxs-lookup"><span data-stu-id="53641-123">The Persistent Chat Help at <https://go.microsoft.com/fwlink/p/?linkid=270945> which provides a detailed list of Persistent Chat features, how they work, and how to use them while running Persistent Chat Server.</span></span>

  - <span data-ttu-id="53641-124">規劃檔中的「Lync Server 2013」中的 [[持久聊天伺服器規劃](lync-server-2013-planning-for-persistent-chat-server.md)]，在 [部署檔] 中[部署 [lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) ] 中的 [Persistent Chat server]，[遷移自 Lync server 2010，群組聊天或 Office 通訊伺服器 2007 R2 Group Chat To Lync Server 2013，persistent chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) in the The The Operations 檔，以及[管理 Lync Server 2013 （](managing-lync-server-2013-persistent-chat-server.md)該檔中的 persistent chat Server），其全部都提供設定 Persistent Chat server 的指示。</span><span class="sxs-lookup"><span data-stu-id="53641-124">The [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation, [Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) in the Migration documentation, and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) in the Operations documentation, all of which provide instructions for setting up Persistent Chat Server.</span></span>

  - <span data-ttu-id="53641-125">Persistent Chat Server 檔 .msi 檔案（Windows Installer 檔案）可讓使用者存取有關 Persistent Chat Server 的完整離線檔。</span><span class="sxs-lookup"><span data-stu-id="53641-125">The Persistent Chat Server Documentation.msi file (Windows Installer file) lets users access comprehensive offline documentation about Persistent Chat Server.</span></span>

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a><span data-ttu-id="53641-126">Persistent Chat Server 的重要拓撲變更</span><span class="sxs-lookup"><span data-stu-id="53641-126">Key Topology Changes for Persistent Chat Server</span></span>

<span data-ttu-id="53641-127">Persistent Chat Server 的下列高層級變更包括：</span><span class="sxs-lookup"><span data-stu-id="53641-127">The following high-level changes for Persistent Chat Server include:</span></span>

<span data-ttu-id="53641-128">Persistent Chat Server 現在是一個伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="53641-128">Persistent Chat Server is now a server role.</span></span> <span data-ttu-id="53641-129">在 Microsoft Lync Server 2010 中，Group Chat Server 是協力廠商信任的 Microsoft Lync Server 2010 應用程式。</span><span class="sxs-lookup"><span data-stu-id="53641-129">In Microsoft Lync Server 2010, Group Chat Server was a third-party trusted application for Microsoft Lync Server 2010.</span></span> <span data-ttu-id="53641-130">您可以使用拓撲產生器，將 Persistent 聊天新增至您的 Lync Server 2013 拓撲。</span><span class="sxs-lookup"><span data-stu-id="53641-130">Persistent Chat can be added to your Lync Server 2013 topology by using Topology Builder.</span></span> <span data-ttu-id="53641-131">在 Lync Server 2013 中，Persistent Chat Server 功能是使用三個新的伺服器角色來執行：</span><span class="sxs-lookup"><span data-stu-id="53641-131">In Lync Server 2013, Persistent Chat Server functionality is implemented by using three new server roles:</span></span>

  - <span data-ttu-id="53641-132">**PersistentChatService：** 這是持續聊天的前端角色。</span><span class="sxs-lookup"><span data-stu-id="53641-132">**PersistentChatService:** This is the front end role for Persistent Chat.</span></span> <span data-ttu-id="53641-133">在 Standard Edition 部署中，在引導程式部署的 Standard Edition 伺服器上組合 Persistent Chat Server 服務角色，如同任何其他 Lync Server 角色。</span><span class="sxs-lookup"><span data-stu-id="53641-133">In Standard Edition deployments, Persistent Chat Server Service Role is collocated on the Standard Edition server deployed by Bootstrapper, like any other Lync Server role.</span></span> <span data-ttu-id="53641-134">在 Enterprise Edition 部署中，Persistent 和任何其他 Lync Server 角色一樣，可在獨立電腦上部署 Persistent Chat Service 角色。</span><span class="sxs-lookup"><span data-stu-id="53641-134">In Enterprise Edition deployments, Persistent Chat Service Role is deployed on stand-alone computers by Bootstrapper, like any other Lync Server role.</span></span>

  - <span data-ttu-id="53641-135">**PersistentChatStore：** 對應至 Persistent Chat 內容資料庫的後端伺服器，所有的聊天室內容都儲存在此伺服器上。</span><span class="sxs-lookup"><span data-stu-id="53641-135">**PersistentChatStore:** Back End Server that corresponds to the Persistent Chat content database, where all the chat content is stored.</span></span>

  - <span data-ttu-id="53641-136">**PersistentChatComplianceStore：** 對應至 Persistent Chat 規範資料庫的後端伺服器角色，所有的相容性事件都儲存在該資料庫中。</span><span class="sxs-lookup"><span data-stu-id="53641-136">**PersistentChatComplianceStore:** Back End Server role that corresponds to the Persistent Chat Compliance database, where all compliance events are stored.</span></span>

<span data-ttu-id="53641-137">這些 Persistent Chat Server role 是選用的，而且只有在需要完整的持久聊天伺服器功能的客戶才能安裝。</span><span class="sxs-lookup"><span data-stu-id="53641-137">These Persistent Chat Server roles are optional, and are installed only by customers who want comprehensive Persistent Chat Server functionality.</span></span> <span data-ttu-id="53641-138">只有當您選擇部署持續性聊天相容性時，才需要**PersistentChatComplianceStore**角色。</span><span class="sxs-lookup"><span data-stu-id="53641-138">The **PersistentChatComplianceStore** role is needed only if you choose to deploy Persistent Chat Compliance.</span></span>

<span data-ttu-id="53641-139">**PersistentChatService**角色會執行兩項服務：</span><span class="sxs-lookup"><span data-stu-id="53641-139">The **PersistentChatService** role runs two services:</span></span>

  - <span data-ttu-id="53641-140">Persistent Chat service</span><span class="sxs-lookup"><span data-stu-id="53641-140">Persistent Chat service</span></span>

  - <span data-ttu-id="53641-141">Persistent Chat 合規性服務</span><span class="sxs-lookup"><span data-stu-id="53641-141">Persistent Chat Compliance service</span></span>

<span data-ttu-id="53641-142">在每個 Persistent Chat Server 上執行這些服務，可在多伺服器 Persistent Chat Server 集區中為這些服務提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="53641-142">Having these services run on each Persistent Chat Server provides high availability for these services in a multiserver Persistent Chat Server pool.</span></span>

<span data-ttu-id="53641-143">此外，若要支援在 Persistent 聊天室中的檔案上傳與下載，Persistent Chat Server 會包含 web 服務。</span><span class="sxs-lookup"><span data-stu-id="53641-143">Additionally, to support the file upload and download in Persistent Chat rooms, Persistent Chat Server includes a web service.</span></span> <span data-ttu-id="53641-144">先前，此服務是在 Persistent Chat Server、前端伺服器及必要的網際網路資訊服務（IIS）上組合，以作為必要條件進行安裝。</span><span class="sxs-lookup"><span data-stu-id="53641-144">Previously, this service was collocated on the Persistent Chat Server, Front End Server and required Internet Information Services (IIS) to be installed as a prerequisite.</span></span> <span data-ttu-id="53641-145">在 Lync Server 2013 Persistent Chat Server 中，檔案上傳/下載 web 服務是以 Lync Server 2013 前端伺服器組合。</span><span class="sxs-lookup"><span data-stu-id="53641-145">In Lync Server 2013 Persistent Chat Server, the File Upload/Download web service is collocated with the Lync Server 2013 Front End Server.</span></span> <span data-ttu-id="53641-146">在副作用中，Internet Information Services （IIS）已不再是 Persistent Chat Server 的必要條件。</span><span class="sxs-lookup"><span data-stu-id="53641-146">As a side effect, Internet Information Services (IIS) is no longer a prerequisite for Persistent Chat Server.</span></span> <span data-ttu-id="53641-147">檔案上傳/下載 web 服務會在網際網路資訊服務（IIS）管理員中識別為**PersistentChat** 。</span><span class="sxs-lookup"><span data-stu-id="53641-147">The File Upload/Download web service is identified as **PersistentChat** in the Internet Information Services (IIS) Manager.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="53641-148"><STRONG>PersistentChatService</STRONG> &nbsp; 只有當前端伺服器為 Standard Edition 前端伺服器時，PersistentChatService 角色才能與 Lync Server 2013 前端伺服器在同一部伺服器上執行 &nbsp; 。</span><span class="sxs-lookup"><span data-stu-id="53641-148">The <STRONG>PersistentChatService</STRONG> role can run on the same server as a Lync Server 2013&nbsp;Front End Server only if that Front End Server is a Standard Edition&nbsp;Front End Server.</span></span> <span data-ttu-id="53641-149"><STRONG>PersistentChatService</STRONG> role 無法獨立于 Lync server 2013 &nbsp; 前端伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="53641-149">The <STRONG>PersistentChatService</STRONG> role cannot run independently of a Lync Server 2013&nbsp;Front End Server.</span></span> <span data-ttu-id="53641-150">它只能安裝在 Lync Server 2013 部署的內容中。</span><span class="sxs-lookup"><span data-stu-id="53641-150">It can be installed only in the context of a Lync Server 2013 deployment.</span></span>



</div>

<span data-ttu-id="53641-151">在 Persistent Chat Server 中，查閱服務已經消除。</span><span class="sxs-lookup"><span data-stu-id="53641-151">In Persistent Chat Server, Lookup service has been eliminated.</span></span> <span data-ttu-id="53641-152">在 [Lync Server 2010] 中，Group Chat，查閱服務于每個群組聊天伺服器前端伺服器上執行，並已執行路由傳送至其中一個通道伺服器。</span><span class="sxs-lookup"><span data-stu-id="53641-152">In Lync Server 2010, Group Chat, the Lookup service ran on every Group Chat Server Front End Server, and performed routing to one of the Channel Servers.</span></span> <span data-ttu-id="53641-153">Lync Server 2013 依賴使用 contact 物件進行路由傳送，其中每個 Persistent Chat Server 集區都是由 Lync Server 前端伺服器所使用，用來識別及傳送適當 Persistent Chat Server 集區的要求，以及集區中執行 Persistent Chat Server 的電腦之一所代表。</span><span class="sxs-lookup"><span data-stu-id="53641-153">Lync Server 2013 relies on routing by using contact objects, where each Persistent Chat Server pool is represented by a contact object that is used by the Lync Server Front End Servers to identify and route requests to an appropriate Persistent Chat Server pool, and to one of the computers running Persistent Chat Server in the pool.</span></span>

<span data-ttu-id="53641-154">在 Lync Server 2013 中，存在合規性服務修改：</span><span class="sxs-lookup"><span data-stu-id="53641-154">In Lync Server 2013, there are Compliance service modifications:</span></span>

  - <span data-ttu-id="53641-155">在 Lync Server 2010 中，規範服務會獨立執行（非組合），而且只能在單一伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="53641-155">In Lync Server 2010, the Compliance service ran stand-alone (non-collocated), and only on a single server.</span></span> <span data-ttu-id="53641-156">規範服務現在會在所有 Persistent Chat Server 前端伺服器（和 Persistent Chat service）上執行，因此可在多伺服器持久聊天伺服器集區中提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="53641-156">The Compliance service now runs on all the Persistent Chat Server Front End Servers, alongside the Persistent Chat service, and thereby provides high availability in a multiserver Persistent Chat Server pool.</span></span> <span data-ttu-id="53641-157">您可以設定單一規範介面卡，以從規範資料庫提取資料，以及將資料提取至其他其中一個系統（XML 檔案、Exchange 主控的封存等等）。</span><span class="sxs-lookup"><span data-stu-id="53641-157">A single compliance adapter can be configured to extract data from the compliance database and into one of the other systems (XML file, Exchange-hosted archives, and so on).</span></span> <span data-ttu-id="53641-158">Persistent Chat Server 包含 XML 介面卡。</span><span class="sxs-lookup"><span data-stu-id="53641-158">Persistent Chat Server includes an XML adapter.</span></span>

  - <span data-ttu-id="53641-159">在每個 Persistent Chat Server 前端伺服器上，由 Persistent Chat service 和合規性服務共用的郵件佇列（也稱為 MSMQ）佇列現在只是兩個服務共用私用佇列。</span><span class="sxs-lookup"><span data-stu-id="53641-159">The Message Queuing (also known as MSMQ) queue that is shared by the Persistent Chat service and the Compliance service on each Persistent Chat Server Front End Server is now a private queue shared only by the two services.</span></span> <span data-ttu-id="53641-160">所有規範服務都會寫入相同的合規性後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="53641-160">All compliance services write to the same Compliance Back End database.</span></span> <span data-ttu-id="53641-161">它們也會從該資料庫讀取資料，目的是為了將資料傳送至其配接器的實例。</span><span class="sxs-lookup"><span data-stu-id="53641-161">They also all read from that database, for the purpose of sending the data to their instance of the adapter.</span></span> <span data-ttu-id="53641-162">規範後端伺服器以新的後端伺服器角色表示。</span><span class="sxs-lookup"><span data-stu-id="53641-162">The Compliance Back End Server is represented as a new Back End Server role.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="53641-163">就像先前的版本一樣，所有規範資料都只處理一次。</span><span class="sxs-lookup"><span data-stu-id="53641-163">As in previous versions, all compliance data is processed only once.</span></span> <span data-ttu-id="53641-164">在不同的 Lync Server 2013，Persistent Chat Server 電腦上執行的規範服務所呼叫的任何配接器實例，都可以處理資料。</span><span class="sxs-lookup"><span data-stu-id="53641-164">The data may be processed by any of the adapter instances invoked by the compliance service running on the various Lync Server 2013, Persistent Chat Server computers.</span></span> <span data-ttu-id="53641-165">在 Persistent Chat Server 中，任何一種配接器實例都可以處理資料。</span><span class="sxs-lookup"><span data-stu-id="53641-165">In Persistent Chat Server, any one of the adapter instances could process the data.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="53641-166">如需安裝訊息佇列的相關資訊，請參閱部署檔中的在<A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Lync Server 2013 伺服器上安裝作業系統和必要條件軟體</A>。</span><span class="sxs-lookup"><span data-stu-id="53641-166">For information about installing Message Queuing, see <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Install operating systems and prerequisite software on servers for Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="53641-167">在 Lync Server 2013 中，高可用性和嚴重損壞修復都有增強功能：</span><span class="sxs-lookup"><span data-stu-id="53641-167">In Lync Server 2013, there are improvements in both high availability and disaster recovery:</span></span>

  - <span data-ttu-id="53641-168">高可用性增強功能： SQL Server 鏡像是用來提供高可用性的持久聊天伺服器內容資料庫和資料中心內的持久聊天規範資料庫（網站內）。</span><span class="sxs-lookup"><span data-stu-id="53641-168">High availability improvements: SQL Server mirroring is used to provide high availability for the Persistent Chat Server content database and Persistent Chat compliance database within a data center (in-site).</span></span>

  - <span data-ttu-id="53641-169">嚴重損壞修復功能： Persistent Chat Server 支援延伸集區架構，可讓單一持久聊天伺服器集區跨兩個網站（也就是拓撲中的單一邏輯集區）進行延伸，而且集區中的伺服器實際位於兩個網站上。</span><span class="sxs-lookup"><span data-stu-id="53641-169">Disaster recovery improvements: Persistent Chat Server supports a stretched pool architecture that enables a single Persistent Chat Server pool to be stretched across two sites (that is, a single logical pool in the topology, with servers in the pool physically located across two sites).</span></span> <span data-ttu-id="53641-170">SQL Server 記錄傳送可用於跨網站的嚴重損壞修復。</span><span class="sxs-lookup"><span data-stu-id="53641-170">SQL Server Log Shipping is used for cross-site disaster recovery.</span></span>

<span data-ttu-id="53641-171">如需高可用性和嚴重損壞修復的詳細資訊，請參閱部署檔中的在[Lync server 2013 中設定 Persistent Chat Server，以取得高可用性和嚴重損壞修復](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="53641-171">For more information about high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a><span data-ttu-id="53641-172">Persistent Chat Server 的主要管理和管理變更</span><span class="sxs-lookup"><span data-stu-id="53641-172">Key Administration and Management Changes for Persistent Chat Server</span></span>

<span data-ttu-id="53641-173">Lync Server 2013 提供下列功能，讓您更容易管理及管理 Persistent Chat Server：</span><span class="sxs-lookup"><span data-stu-id="53641-173">Lync Server 2013 has made it easier to administer and manage Persistent Chat Server by providing:</span></span>

  - <span data-ttu-id="53641-174">統一的管理與管理。</span><span class="sxs-lookup"><span data-stu-id="53641-174">Unified administration and management.</span></span> <span data-ttu-id="53641-175">Lync Server 2013 利用 Lync 系統管理員所熟悉的工具，讓您更容易管理及管理 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="53641-175">Lync Server 2013 makes it easier to manage and administer Persistent Chat Server by using tools that are already familiar to Lync administrators.</span></span> <span data-ttu-id="53641-176">Persistent Chat Server 包含與 Lync Server 控制台整合的管理使用者介面體驗，其可解決舊版的群組聊天伺服器使用者介面的效能問題。</span><span class="sxs-lookup"><span data-stu-id="53641-176">Persistent Chat Server includes an administrative user interface experience that is integrated with the Lync Server Control Panel, which addresses performance issues with the previous versions of the Group Chat Server user interface.</span></span> <span data-ttu-id="53641-177">此外，Persistent Chat Server 包含 Windows PowerShell Cmdlet 的集合，用來管理和管理 Persistent Chat Server 類別、Persistent Chat Server 聊天室（包括刪除聊天室，以及清除已過時的內容）和增益集。</span><span class="sxs-lookup"><span data-stu-id="53641-177">Also, Persistent Chat Server includes a collection of Windows PowerShell cmdlets to administer and manage Persistent Chat Server categories, Persistent Chat Server rooms (including deleting rooms and purging obsolete content), and add-ins.</span></span>

  - <span data-ttu-id="53641-178">簡化的管理模型。</span><span class="sxs-lookup"><span data-stu-id="53641-178">Simplified administration model.</span></span> <span data-ttu-id="53641-179">Lync Server 2013 已透過解決下列主要客戶需求，以變更和簡化了 Persistent Chat Server 模型：</span><span class="sxs-lookup"><span data-stu-id="53641-179">Lync Server 2013 has changed and simplified the Persistent Chat Server model by addressing the following key customer requirements:</span></span>
    
      - <span data-ttu-id="53641-180">移除範圍和類別的複雜嵌套階層。</span><span class="sxs-lookup"><span data-stu-id="53641-180">Remove the complex nested hierarchies of scopes and categories.</span></span>
    
      - <span data-ttu-id="53641-181">支援定義拒絕清單及目前 MindAlign 客戶的允許清單（範圍），以遷移至 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="53641-181">Support to define deny lists as well as allowed lists (scopes) for current MindAlign customers who are planning to migrate to Persistent Chat Server.</span></span>

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a><span data-ttu-id="53641-182">來自舊版群組聊天伺服器版本的使用者角色有何不同？</span><span class="sxs-lookup"><span data-stu-id="53641-182">What’s Different about User Roles from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="53641-183">Lync Server 2010，群組聊天具有使用者系統管理員角色、聊天室系統管理員角色，以及可管理增益集的 Lync Server 系統管理員角色。 Persistent Chat Server 只會提供持續性聊天系統管理員角色（類似其他 Lync Server 角色型存取控制（RBAC）角色）。</span><span class="sxs-lookup"><span data-stu-id="53641-183">Lync Server 2010, Group Chat had a user administrator role, a chat room administrator role and a Lync Server administrator role that could manage add-ins. Persistent Chat Server simply provides a Persistent Chat Administrator role (which is similar to other Lync Server role-based access control (RBAC) roles).</span></span> <span data-ttu-id="53641-184">任何屬於此 RBAC 角色成員的人員，都可以管理聊天室、增益集和類別（因而取得這些類別的使用者存取），以及設定 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="53641-184">Anyone who is a member of this RBAC role can manage chat rooms, add-ins, and categories (and therefore gain user access for these categories), and configuration of the Persistent Chat Server pool.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a><span data-ttu-id="53641-185">來自舊版群組聊天伺服器版本的聊天室類別有何不同？</span><span class="sxs-lookup"><span data-stu-id="53641-185">What’s Different about Chat Room Categories from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="53641-186">聊天室類別可能不再是嵌套的，而且無法再修改根類別。</span><span class="sxs-lookup"><span data-stu-id="53641-186">Chat room categories can no longer be nested, and the root category can no longer be modified.</span></span> <span data-ttu-id="53641-187">AllowedMembers/DeniedMembers 所包含的範圍是用於舊版 Group Chat Server 版本（但不支援指定拒絕清單）。</span><span class="sxs-lookup"><span data-stu-id="53641-187">AllowedMembers/DeniedMembers comprise what a scope used to be in legacy Group Chat Server versions (except that it didn’t support specifying a Denied list).</span></span> <span data-ttu-id="53641-188">因為沒有嵌套的類別，所以範圍可能不再被覆寫。</span><span class="sxs-lookup"><span data-stu-id="53641-188">Scopes can no longer be overridden, because there are no nested categories.</span></span> <span data-ttu-id="53641-189">Lync Server 2013 中的 Persistent Chat 系統管理員可以建立及管理聊天室類別。</span><span class="sxs-lookup"><span data-stu-id="53641-189">A Persistent Chat Administrator in Lync Server 2013 can create and manage chat room categories.</span></span> <span data-ttu-id="53641-190">在建立及管理聊天室類別的過程中，Persistent Chat 管理員可以設定主體（Active Directory 群組/容器/使用者），該主體可存取屬於特定類別之聊天室的成員/建立者。</span><span class="sxs-lookup"><span data-stu-id="53641-190">As part of creating and managing chat room categories, a Persistent Chat Administrator can configure principals (Active Directory groups/containers/users) that have access to be members/creators of chat rooms of a particular category.</span></span> <span data-ttu-id="53641-191">Persistent Chat 系統管理員也可以新增 DeniedMembers 至類別，而這些專案會變成對允許清單的明確排除。</span><span class="sxs-lookup"><span data-stu-id="53641-191">A Persistent Chat Administrator can also add DeniedMembers to a category, and these become explicit exclusions to the allowed list.</span></span> <span data-ttu-id="53641-192">DeniedMembers 覆寫 AllowedMembers 中的內容。</span><span class="sxs-lookup"><span data-stu-id="53641-192">DeniedMembers override what’s in AllowedMembers.</span></span>

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a><span data-ttu-id="53641-193">舊群組聊天伺服器版本的聊天室內容有何不同？</span><span class="sxs-lookup"><span data-stu-id="53641-193">What’s Different about Chat Room Properties from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="53641-194">Lync Server 2013，Persistent Chat Server 中已存在開放式聊天室的新概念。</span><span class="sxs-lookup"><span data-stu-id="53641-194">A new concept of open chat rooms exists in Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="53641-195">所有允許的成員都可以加入聊天室，不需要獨佔成員資格。</span><span class="sxs-lookup"><span data-stu-id="53641-195">All allowed members can join the chat room, without exclusive membership.</span></span>

<span data-ttu-id="53641-196">已消除舊版 Persistent Chat Server 中包含的下列聊天室屬性：</span><span class="sxs-lookup"><span data-stu-id="53641-196">The following chat room properties that were included in previous versions of Persistent Chat Server have been eliminated:</span></span>

  - <span data-ttu-id="53641-197">主題：聊天室現在只有描述。</span><span class="sxs-lookup"><span data-stu-id="53641-197">Topic: A Room now only has a Description.</span></span>

  - <span data-ttu-id="53641-198">建立新的成員清單：在 Persistent Chat Server 中，所有聊天室都是以空成員資格開始（而且可以最大化至允許的成員的成員資格 equaling）。</span><span class="sxs-lookup"><span data-stu-id="53641-198">Create New Member list: In Persistent Chat Server, all chat rooms start with empty membership (and can maximize to a membership equaling the Allowed Members).</span></span>

  - <span data-ttu-id="53641-199">檔案上傳：用於設定每個聊天室的設定，以控制是否允許檔案上傳/下載。</span><span class="sxs-lookup"><span data-stu-id="53641-199">File Upload: Used to be a setting per chat room to control whether file upload/downloads were allowed.</span></span> <span data-ttu-id="53641-200">這現在只會設定類別層級，並套用至該類別中的所有聊天室。</span><span class="sxs-lookup"><span data-stu-id="53641-200">This is now set only the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="53641-201">聊天記錄：用來控制聊天記錄是否已啟用，但現在只會在類別層級設定，並套用至該類別中的所有聊天室。</span><span class="sxs-lookup"><span data-stu-id="53641-201">Chat History: Used to be a setting per chat room to control if Chat History was enabled, but is now set only at the category level and applies to all rooms in that category.</span></span>

  - <span data-ttu-id="53641-202">邀請：會議室永遠繼承類別的 [邀請] 設定。您也可以在會議室上關閉此功能。</span><span class="sxs-lookup"><span data-stu-id="53641-202">Invites: A room always inherits the Invites setting for the category; or it can be turned off on the room.</span></span> <span data-ttu-id="53641-203">若類別以前已設為 [邀請]，會議室便無法開啟邀請。</span><span class="sxs-lookup"><span data-stu-id="53641-203">A room cannot turn on Invites if the category was previously set to Invites off.</span></span>

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a><span data-ttu-id="53641-204">舊群組聊天伺服器版本的原則有何不同？</span><span class="sxs-lookup"><span data-stu-id="53641-204">What’s Different about Policies from Previous Group Chat Server Versions?</span></span>

<span data-ttu-id="53641-205">Persistent Chat Server 啟用新的 Lync 原則，具有持續聊天、每個使用者/集區/網站/全域設定。</span><span class="sxs-lookup"><span data-stu-id="53641-205">Persistent Chat Server has a new Lync policy enabled with Persistent Chat, per user/pool/site/global settings.</span></span> <span data-ttu-id="53641-206">在 Lync 2013 用戶端中，Persistent 聊天環境只適用于透過持久聊天（直接或透過集區/網站/全域設定）的原則所啟用的使用者。</span><span class="sxs-lookup"><span data-stu-id="53641-206">In the Lync 2013 client, the Persistent Chat environment is available only for users who are enabled by policy for Persistent Chat (either directly or through the pool/site/global setting).</span></span>

<span data-ttu-id="53641-207">舊版的群組聊天伺服器沒有任何整合在 Lync Server 原則中的原則。</span><span class="sxs-lookup"><span data-stu-id="53641-207">Previous versions of Group Chat Server did not have any policies integrated into the Lync Server policies.</span></span> <span data-ttu-id="53641-208">在每個使用者及每個類別/房間基礎上，使用 [**可上傳**每位使用者的檔案] 功能，您可以讓使用者成為使用者管理員、聊天室管理員或設定使用者上傳檔案的能力。</span><span class="sxs-lookup"><span data-stu-id="53641-208">On a per user and per category/room basis, by using the **Can Upload Files** per user feature, you could make the user a User administrator, a chat room administrator, or configure the user’s ability to upload files.</span></span> <span data-ttu-id="53641-209">Persistent Chat Server **File 上傳**功能僅限每個類別。</span><span class="sxs-lookup"><span data-stu-id="53641-209">The Persistent Chat Server **File Upload** feature is just per category.</span></span>

</div>

<div>

## <a name="logging"></a><span data-ttu-id="53641-210">記錄</span><span class="sxs-lookup"><span data-stu-id="53641-210">Logging</span></span>

<span data-ttu-id="53641-211">Persistent Chat Server 和 System Center Operations Manager 記錄已整合至 Lync Server 2013 追蹤記錄。</span><span class="sxs-lookup"><span data-stu-id="53641-211">Logging for Persistent Chat Server and System Center Operations Manager is integrated into the Lync Server 2013 trace logging.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="53641-212">另請參閱</span><span class="sxs-lookup"><span data-stu-id="53641-212">See Also</span></span>


[<span data-ttu-id="53641-213">在 Lync Server 2013 中規劃 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="53641-213">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
