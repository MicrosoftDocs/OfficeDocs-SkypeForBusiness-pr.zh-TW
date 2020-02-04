---
title: Lync Server 2013：持久聊天伺服器的運作方式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Persistent Chat Server works
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49684643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 692f9a40bc2c0fd885fc251a4a792d480a69c57d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a><span data-ttu-id="81e30-102">在 Lync Server 2013 中，持久聊天伺服器的運作方式</span><span class="sxs-lookup"><span data-stu-id="81e30-102">How Persistent Chat Server works in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81e30-103">_**主題上次修改日期：** 2012-11-21_</span><span class="sxs-lookup"><span data-stu-id="81e30-103">_**Topic Last Modified:** 2012-11-21_</span></span>

<span data-ttu-id="81e30-104">Lync Server 2013，持續聊天伺服器可讓您參與多方、依時間保留的、以主題為基礎的交談。</span><span class="sxs-lookup"><span data-stu-id="81e30-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="81e30-105">持續聊天伺服器可協助您的組織執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="81e30-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="81e30-106">改善地理位置分散且跨職能團隊之間的溝通</span><span class="sxs-lookup"><span data-stu-id="81e30-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="81e30-107">拓寬資訊意識及參與情況</span><span class="sxs-lookup"><span data-stu-id="81e30-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="81e30-108">改善與您的延伸組織的溝通</span><span class="sxs-lookup"><span data-stu-id="81e30-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="81e30-109">減少資訊超載</span><span class="sxs-lookup"><span data-stu-id="81e30-109">Reduce information overload</span></span>

  - <span data-ttu-id="81e30-110">改善資訊意識</span><span class="sxs-lookup"><span data-stu-id="81e30-110">Improve information awareness</span></span>

  - <span data-ttu-id="81e30-111">增加重要知識與資訊的散佈</span><span class="sxs-lookup"><span data-stu-id="81e30-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="81e30-112">您可以使用 Lync Server 2013 來部署持久聊天伺服器作為選用角色。</span><span class="sxs-lookup"><span data-stu-id="81e30-112">You can deploy Persistent Chat Server as an optional role with Lync Server 2013.</span></span> <span data-ttu-id="81e30-113">持久性聊天服務在專用的池中執行，而持續聊天伺服器池則依賴 Lync 伺服器池來傳送郵件給它。</span><span class="sxs-lookup"><span data-stu-id="81e30-113">Persistent Chat services run on a dedicated pool, and a Persistent Chat Server pool depends on a Lync Server pool to route messages to it.</span></span> <span data-ttu-id="81e30-114">用戶端透過 SIP （XCCOS）使用可擴展聊天通訊。</span><span class="sxs-lookup"><span data-stu-id="81e30-114">Clients use eXtensible Chat Communication Over SIP (XCCOS).</span></span> <span data-ttu-id="81e30-115">Lync Server 前端伺服器已設定為將流量路由到持續聊天伺服器池。</span><span class="sxs-lookup"><span data-stu-id="81e30-115">The Lync Server Front End Servers are configured to route the traffic to a Persistent Chat Server pool.</span></span>

<div>

## <a name="high-level-architecture"></a><span data-ttu-id="81e30-116">高層次架構</span><span class="sxs-lookup"><span data-stu-id="81e30-116">High-Level Architecture</span></span>

<span data-ttu-id="81e30-117">下列圖表提供持續聊天伺服器架構與服務的高層觀點。</span><span class="sxs-lookup"><span data-stu-id="81e30-117">The following diagrams provide high-level perspectives of the Persistent Chat Server architecture and services.</span></span>

<span data-ttu-id="81e30-118">**持續聊天伺服器的高層次架構**</span><span class="sxs-lookup"><span data-stu-id="81e30-118">**Persistent Chat Server High-Level Architecture**</span></span>

<span data-ttu-id="81e30-119">![Persistent Chat Server 架構。](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Persistent Chat Server 架構。")</span><span class="sxs-lookup"><span data-stu-id="81e30-119">![Persistent Chat Server architecture.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Persistent Chat Server architecture.")</span></span>

<span data-ttu-id="81e30-120">**持續聊天伺服器高層級服務**</span><span class="sxs-lookup"><span data-stu-id="81e30-120">**Persistent Chat Server High-Level Services**</span></span>

<span data-ttu-id="81e30-121">![Persistent Chat Server 元件。](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Persistent Chat Server 元件。")</span><span class="sxs-lookup"><span data-stu-id="81e30-121">![Persistent Chat Server components.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Persistent Chat Server components.")</span></span>

<span data-ttu-id="81e30-122">在永久聊天伺服器前端伺服器上執行兩項服務：</span><span class="sxs-lookup"><span data-stu-id="81e30-122">Two services run on the Persistent Chat Server Front End Servers:</span></span>

  - <span data-ttu-id="81e30-123">持續聊天（頻道）</span><span class="sxs-lookup"><span data-stu-id="81e30-123">Persistent Chat (Channel)</span></span>

  - <span data-ttu-id="81e30-124">從屬</span><span class="sxs-lookup"><span data-stu-id="81e30-124">Compliance</span></span>

<div>

## <a name="persistent-chat-channel-service"></a><span data-ttu-id="81e30-125">持續聊天（通道）服務</span><span class="sxs-lookup"><span data-stu-id="81e30-125">Persistent Chat (Channel) Service</span></span>

<span data-ttu-id="81e30-126">持續聊天（通道）服務是負責持久聊天伺服器的核心服務。</span><span class="sxs-lookup"><span data-stu-id="81e30-126">The Persistent Chat (Channel) service is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="81e30-127">此服務提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="81e30-127">This service provides the following functions:</span></span>

  - <span data-ttu-id="81e30-128">接受接收的郵件</span><span class="sxs-lookup"><span data-stu-id="81e30-128">Accepts incoming messages</span></span>

  - <span data-ttu-id="81e30-129">在持續聊天室中註冊並列出線上參與者</span><span class="sxs-lookup"><span data-stu-id="81e30-129">Registers and lists online participants within a Persistent Chat room</span></span>

  - <span data-ttu-id="81e30-130">將郵件重新傳送至其他通道訂閱者</span><span class="sxs-lookup"><span data-stu-id="81e30-130">Retransmits messages to other channel subscribers</span></span>

  - <span data-ttu-id="81e30-131">針對通道管理、聊天室邀請、搜尋及新的內容通知實現邏輯</span><span class="sxs-lookup"><span data-stu-id="81e30-131">Implements logic for channel management, chat room invitation, search, and new content notifications</span></span>

<span data-ttu-id="81e30-132">永久聊天（通道）服務會使用 [永久聊天] 存放區，儲存及存取聊天室內容和其他系統中繼資料（授權規則等）。</span><span class="sxs-lookup"><span data-stu-id="81e30-132">The Persistent Chat (Channel) service stores and accesses chat room content and other system metadata (authorization rules, and so on) by using the Persistent Chat Store.</span></span> <span data-ttu-id="81e30-133">此服務會儲存已上傳到 [永久聊天] 檔案存放區中的聊天室的檔案。</span><span class="sxs-lookup"><span data-stu-id="81e30-133">This service stores files that are uploaded into chat rooms in the Persistent Chat File Store.</span></span>

</div>

<div>

## <a name="compliance-service"></a><span data-ttu-id="81e30-134">合規性服務</span><span class="sxs-lookup"><span data-stu-id="81e30-134">Compliance Service</span></span>

<span data-ttu-id="81e30-135">合規性服務是永久性聊天伺服器的選擇性元件，負責將聊天內容和事件封存到持續性聊天合規性存放區。</span><span class="sxs-lookup"><span data-stu-id="81e30-135">The Compliance service is an optional component of Persistent Chat Server and is responsible for archiving chat content and events to the Persistent Chat Compliance Store.</span></span> <span data-ttu-id="81e30-136">如果您的組織有需要永久聊天活動進行封存的規章，您可以部署選用的持續聊天合規性服務。</span><span class="sxs-lookup"><span data-stu-id="81e30-136">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="81e30-137">相容性服務已安裝在持續聊天池中的每個持續聊天伺服器上。</span><span class="sxs-lookup"><span data-stu-id="81e30-137">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> <span data-ttu-id="81e30-138">設定後，持久的聊天伺服器規範會記錄使用者活動，例如加入和離開聊天室，以及張貼及讀取訊息。</span><span class="sxs-lookup"><span data-stu-id="81e30-138">When configured, Persistent Chat Server compliance records user activity such as joining and leaving rooms, and posting and reading of messages.</span></span> <span data-ttu-id="81e30-139">合規性服務儲存需要封存在持續聊天相容性檔案存放區中的檔案。</span><span class="sxs-lookup"><span data-stu-id="81e30-139">The Compliance service stores files that need to be archived in the Persistent Chat Compliance File Store.</span></span>

</div>

<div>

## <a name="persistent-chat-web-services"></a><span data-ttu-id="81e30-140">持續聊天 Web 服務</span><span class="sxs-lookup"><span data-stu-id="81e30-140">Persistent Chat Web Services</span></span>

<span data-ttu-id="81e30-141">在 Lync Server 前端伺服器上，執行兩個依存于網際網路資訊服務（IIS）的服務，並以網頁元件的形式實現：</span><span class="sxs-lookup"><span data-stu-id="81e30-141">On the Lync Server Front End Servers, two services run that depend on Internet Information Services (IIS), and are implemented as web components:</span></span>

  - <span data-ttu-id="81e30-142">檔案**上傳/下載的持續聊天 Web 服務**負責從聊天室張貼及檢索檔案。</span><span class="sxs-lookup"><span data-stu-id="81e30-142">**Persistent Chat Web Services for File Upload/Download** Responsible for posting and retrieving files from chat rooms.</span></span>

  - <span data-ttu-id="81e30-143">**聊天室管理的持續聊天 Web 服務**負責為使用者提供管理其聊天室的功能，並建立新的聊天室。</span><span class="sxs-lookup"><span data-stu-id="81e30-143">**Persistent Chat Web Services for Chat Room Management** Responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a><span data-ttu-id="81e30-144">我要如何開始使用持續聊天伺服器？</span><span class="sxs-lookup"><span data-stu-id="81e30-144">How Do I Start Using Persistent Chat Server?</span></span>

<span data-ttu-id="81e30-145">Persistent 聊天伺服器是 Lync Server 2013 基礎結構中的選擇性伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="81e30-145">Persistent Chat Server is an optional server role within the Lync Server 2013 infrastructure.</span></span> <span data-ttu-id="81e30-146">如果您安裝持久聊天伺服器角色，由系統管理員提供的任何已透過策略啟用的使用者都可以使用與 Lync 2013 用戶端的持續交談。</span><span class="sxs-lookup"><span data-stu-id="81e30-146">If you install the Persistent Chat Server role, any users who have been enabled through policy by an administrator can use Persistent Chat with the Lync 2013 client.</span></span>

<span data-ttu-id="81e30-147">如需有關如何部署持續聊天伺服器並讓使用者能夠利用策略的詳細資料，請參閱[在 Lync server 2013 中部署持久聊天伺服器](lync-server-2013-deploying-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="81e30-147">For details about how to deploy Persistent Chat Server and enable users to leverage the capabilities by policy, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>

<span data-ttu-id="81e30-148">如需如何在持續聊天伺服器部署上設定設定的詳細資料，請參閱[在 Lync server 2013 中部署持久聊天伺服器](lync-server-2013-deploying-persistent-chat-server.md)，以及[管理 lync Server 2013、持續聊天伺服器](managing-lync-server-2013-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="81e30-148">For details about how to configure settings on your Persistent Chat Server deployment, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="81e30-149">如需如何根據原則啟用使用者以使用 Lync 2013 用戶端中的持續聊天功能的詳細資料，請參閱[在 Lync server 2013 中部署持續聊天伺服器](lync-server-2013-deploying-persistent-chat-server.md)以及[管理 lync Server 2013、持續聊天伺服器](managing-lync-server-2013-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="81e30-149">For details about how to enable users by policy such that they can leverage Persistent Chat functionality in Lync 2013 client, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="81e30-150">如果您已部署持久的聊天合規性，請參閱[管理 Lync server 2013、持續聊天伺服器，](managing-lync-server-2013-persistent-chat-server.md)以取得如何設定合規性設定的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="81e30-150">If you deployed Persistent Chat compliance, see [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) for details about how to configure settings for compliance.</span></span>

</div>

<div>

## <a name="persistent-chat-call-flows"></a><span data-ttu-id="81e30-151">持續聊天通話流程</span><span class="sxs-lookup"><span data-stu-id="81e30-151">Persistent Chat Call Flows</span></span>

<span data-ttu-id="81e30-152">持續聊天用戶端會使用 XCCOS 與持續聊天服務進行通訊。</span><span class="sxs-lookup"><span data-stu-id="81e30-152">The Persistent Chat client communicates with the Persistent Chat service by using XCCOS.</span></span> <span data-ttu-id="81e30-153">下列順序描述登入程式，以及典型的聊天室訂閱和訊息發佈情況。</span><span class="sxs-lookup"><span data-stu-id="81e30-153">The following sequences describe the sign-in process and a typical room subscription and message post scenario.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="81e30-154">登入</span><span class="sxs-lookup"><span data-stu-id="81e30-154">Sign-in</span></span>

<span data-ttu-id="81e30-155">下列通話流程圖和步驟說明登入程式。</span><span class="sxs-lookup"><span data-stu-id="81e30-155">The following call flow diagram and steps describe the sign-in process.</span></span>

<span data-ttu-id="81e30-156">**持續聊天用戶端登入通話流程**</span><span class="sxs-lookup"><span data-stu-id="81e30-156">**Persistent Chat Client Sign-in Call Flow**</span></span>

<span data-ttu-id="81e30-157">![Persistent Chat Server 通話流程圖。](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Persistent Chat Server 通話流程圖。")</span><span class="sxs-lookup"><span data-stu-id="81e30-157">![Persistent Chat Server call flow diagram.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Persistent Chat Server call flow diagram.")</span></span>

1.  <span data-ttu-id="81e30-158">持續性聊天用戶端會先傳送 SIP 訂閱，以從伺服器取得帶外的提供檔。</span><span class="sxs-lookup"><span data-stu-id="81e30-158">The Persistent Chat client first sends a SIP SUBSCRIBE to retrieve the in-band provisioning document from the server.</span></span> <span data-ttu-id="81e30-159">這份檔會指出使用者是否已啟用或停用持續聊天，以及持續聊天伺服器池中的 SIP Uri 清單。</span><span class="sxs-lookup"><span data-stu-id="81e30-159">This document indicates if Persistent Chat is enabled or disabled for the user and the list of SIP URIs for the Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="81e30-160">持續聊天用戶端會將 SIP 邀請訊息傳送到在上一個步驟中取得的持續聊天伺服器的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="81e30-160">The Persistent Chat client sends a SIP INVITE message to the SIP URI of the Persistent Chat Server that it obtained in the previous step.</span></span> <span data-ttu-id="81e30-161">邀請順序後面接著200的 [確定] 和 [ACK]，持續聊天用戶端現在已開啟與持續聊天伺服器端點的 SIP 會話。</span><span class="sxs-lookup"><span data-stu-id="81e30-161">The INVITE sequence is followed by 200 OK and ACK, and the Persistent Chat client has now opened a SIP session with a Persistent Chat Server endpoint.</span></span> <span data-ttu-id="81e30-162">因此，持續聊天用戶端會傳送 SIP 資訊訊息，其中包含聊天訊息或命令要求伺服器採取動作的命令，來與持久聊天伺服器進行通訊。</span><span class="sxs-lookup"><span data-stu-id="81e30-162">Consequently, the Persistent Chat client communicates with Persistent Chat Server by sending SIP INFO messages that contain either chat messages or commands requesting the server to take an action.</span></span> <span data-ttu-id="81e30-163">所有這些訊息都是透過 200 OK 或503服務無法使用（也就是伺服器負載繁重的事件）來確認。</span><span class="sxs-lookup"><span data-stu-id="81e30-163">All of these messages are acknowledged with either 200 OK or 503 Service Unavailable (that is, in the event of heavy server load).</span></span> <span data-ttu-id="81e30-164">如果用戶端收到503回應，將會重試訊息。</span><span class="sxs-lookup"><span data-stu-id="81e30-164">If the client receives a 503 response, it will retry the message.</span></span> <span data-ttu-id="81e30-165">（這個範例不包含503回應）。如果伺服器接受該訊息或命令，並傳送 200 [確定]，就會以個別 SIP 資訊訊息的形式提供對用戶端的回應。</span><span class="sxs-lookup"><span data-stu-id="81e30-165">(This example does not include a 503 response.) If the server accepts the message or command and sends 200 OK, it provides a response to the client in the form of a separate SIP INFO message.</span></span> <span data-ttu-id="81e30-166">此回應包括對原始命令的參照。</span><span class="sxs-lookup"><span data-stu-id="81e30-166">This response includes a reference to the originating command.</span></span>

3.  <span data-ttu-id="81e30-167">持續聊天用戶端會傳送包含 XCCOS **getserverinfo**命令的 SIP 資訊訊息。</span><span class="sxs-lookup"><span data-stu-id="81e30-167">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getserverinfo** command.</span></span> <span data-ttu-id="81e30-168">持續聊天伺服器會以新的 SIP 資訊訊息回復，其中包含持續聊天服務設定的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="81e30-168">Persistent Chat Server replies with a new SIP INFO message that contains information about the Persistent Chat service configuration.</span></span>

4.  <span data-ttu-id="81e30-169">持續聊天用戶端會傳送包含 XCCOS **getassociations**命令的 SIP 資訊訊息。</span><span class="sxs-lookup"><span data-stu-id="81e30-169">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getassociations** command.</span></span> <span data-ttu-id="81e30-170">持續聊天伺服器會以新的 SIP 資訊訊息回復，其中包含使用者所屬的聊天室清單。</span><span class="sxs-lookup"><span data-stu-id="81e30-170">Persistent Chat Server replies with a new SIP INFO message that contains the list of rooms of which the user is a member.</span></span> <span data-ttu-id="81e30-171">持續性聊天用戶端會重複命令，以取得使用者為管理員的聊天室清單。</span><span class="sxs-lookup"><span data-stu-id="81e30-171">The Persistent Chat client repeats the command to retrieve the list of rooms of which the user is a manager.</span></span>

5.  <span data-ttu-id="81e30-172">持續聊天用戶端會從「目前狀態」檔中取得已追蹤的聊天室清單，其中每個聊天室都是以「roomSetting」類別表示。</span><span class="sxs-lookup"><span data-stu-id="81e30-172">The Persistent Chat client gets the list of followed rooms from the "presence" document, where each followed room is represented by a "roomSetting" category.</span></span> <span data-ttu-id="81e30-173">所有追蹤的聊天室都是由單一 SIP 資訊訊息所聯接，其中包含包含聊天室 Uri 清單的 XCCOS **bjoin**命令。</span><span class="sxs-lookup"><span data-stu-id="81e30-173">All followed rooms are joined by a single SIP INFO message that contains the XCCOS **bjoin** command that contains the list of room URIs.</span></span> <span data-ttu-id="81e30-174">因為已追蹤的聊天室清單會保留在伺服器上，所以任何電腦上的任何用戶端都有與指定使用者 URI 相同的已追蹤會議室清單。</span><span class="sxs-lookup"><span data-stu-id="81e30-174">Because the list of followed rooms is kept on the server, any client on any computer has the same list of followed rooms for the specified user URI.</span></span> <span data-ttu-id="81e30-175">持續聊天用戶端也會在本機電腦登錄中保留開啟的會議室（如果使用者已啟用此選項）清單，並在登入時，傳送包含每個開啟的聊天室的 XCCOS **join**命令的 SIP 資訊訊息，以加入該會議室。</span><span class="sxs-lookup"><span data-stu-id="81e30-175">The Persistent Chat client also keeps the list of opened rooms (if this option is enabled by the user) in the local computer registry, and joins each of these rooms at sign-in by sending a SIP INFO message that contains the XCCOS **join** command for each opened room.</span></span> <span data-ttu-id="81e30-176">由於此清單會保留在登錄中，因此在不同電腦上執行的兩個持續聊天用戶端可能會有不同的變化。</span><span class="sxs-lookup"><span data-stu-id="81e30-176">Because this list is kept in the registry, it can be different on two Persistent Chat clients running on different computers.</span></span>

6.  <span data-ttu-id="81e30-177">針對每個加入的聊天室，持續性聊天用戶端會傳送包含 XCCOS **bccoNtext**命令的 SIP 資訊訊息。</span><span class="sxs-lookup"><span data-stu-id="81e30-177">For each room joined, the Persistent Chat client sends a SIP INFO message that contains the XCCOS **bccontext** command.</span></span> <span data-ttu-id="81e30-178">持續聊天伺服器會以新的 SIP 資訊訊息回復，其中包含聊天室中最近的聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="81e30-178">Persistent Chat Server replies with a new SIP INFO message that contains the most recent chat message in the room.</span></span>

7.  <span data-ttu-id="81e30-179">持續性聊天用戶端會傳送一個 SIP 資訊訊息，其中包含 XCCOS **getinv** （也就是 [取得邀請]）命令，以要求用戶端尚未看到任何新的聊天室邀請。</span><span class="sxs-lookup"><span data-stu-id="81e30-179">The Persistent Chat client sends a SIP INFO message that contains a XCCOS **getinv** (that is, get invitation) command to request any new room invitations that the client has not yet seen.</span></span> <span data-ttu-id="81e30-180">在個別的 SIP 資訊訊息中，持續聊天伺服器會傳回這些聊天室的清單。</span><span class="sxs-lookup"><span data-stu-id="81e30-180">In a separate SIP INFO message, Persistent Chat Server returns a list of those rooms.</span></span>

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a><span data-ttu-id="81e30-181">訂閱聊天室並張貼訊息</span><span class="sxs-lookup"><span data-stu-id="81e30-181">Subscribe to a Room and Post a Message</span></span>

<span data-ttu-id="81e30-182">下列通話流程圖和步驟描述典型的房間訂閱和訊息文章案例。</span><span class="sxs-lookup"><span data-stu-id="81e30-182">The following call flow diagram and steps describe a typical room subscription and message post scenario.</span></span>

<span data-ttu-id="81e30-183">**持續聊天用戶端房間訂閱和郵件張貼通話流程**</span><span class="sxs-lookup"><span data-stu-id="81e30-183">**Persistent Chat Client Room Subscription and Message Posting Call Flow**</span></span>

<span data-ttu-id="81e30-184">![聊天室訂閱及訊息張貼的情況。](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "聊天室訂閱及訊息張貼的情況。")</span><span class="sxs-lookup"><span data-stu-id="81e30-184">![Room subscription and message post scenario.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Room subscription and message post scenario.")</span></span>

1.  <span data-ttu-id="81e30-185">從持久性聊天用戶端，User1 按一下 [**加入聊天室**]，按一下 [**搜尋**]，然後輸入一些搜尋準則。</span><span class="sxs-lookup"><span data-stu-id="81e30-185">From the Persistent Chat client, User1 clicks **Join a Chat Room**, clicks **Search**, and then enters some search criteria.</span></span> <span data-ttu-id="81e30-186">持續聊天用戶端會傳送包含 XCCOS **chansrch** （聊天室搜尋）命令的 SIP 資訊訊息，以及搜尋準則。</span><span class="sxs-lookup"><span data-stu-id="81e30-186">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **chansrch** (room search) command, along with the search criteria.</span></span> <span data-ttu-id="81e30-187">持續聊天伺服器會查詢後端資料庫，並在新的 SIP 資訊訊息中包含符合搜尋準則之可用聊天室清單的回復。</span><span class="sxs-lookup"><span data-stu-id="81e30-187">Persistent Chat Server queries the back-end database and replies in a new SIP INFO message that contains a list of available rooms that meet the search criteria.</span></span>

2.  <span data-ttu-id="81e30-188">[User1] 會選取他或她想要加入的聊天室，然後按一下 [**追蹤此聊天室**]。</span><span class="sxs-lookup"><span data-stu-id="81e30-188">User1 selects the chat room that he or she wants to join, and then clicks **Follow this room**.</span></span> <span data-ttu-id="81e30-189">持續聊天用戶端會傳送持續聊天伺服器的 SIP 資訊訊息，其中包含 XCCOS **join**命令，以及使用者選取的聊天室的聊天室識別碼。</span><span class="sxs-lookup"><span data-stu-id="81e30-189">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **join** command and the room ID of the chat room that the user selected.</span></span> <span data-ttu-id="81e30-190">持續聊天伺服器會以包含預配資料之 SIP 資訊訊息回復。</span><span class="sxs-lookup"><span data-stu-id="81e30-190">Persistent Chat Server replies with a SIP INFO message that contains the provisioning data.</span></span>

3.  <span data-ttu-id="81e30-191">持續聊天用戶端會傳送持久聊天伺服器，其中包含 XCCOS **bccoNtext** （backchat 內容）命令的 SIP 資訊訊息。</span><span class="sxs-lookup"><span data-stu-id="81e30-191">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **bccontext** (backchat context) command.</span></span> <span data-ttu-id="81e30-192">持續聊天伺服器會檢索聊天記錄，並將其傳回獨立 SIP 資訊訊息中的持續聊天用戶端。</span><span class="sxs-lookup"><span data-stu-id="81e30-192">Persistent Chat Server retrieves the chat history, and returns it to the Persistent Chat client in a separate SIP INFO message.</span></span> <span data-ttu-id="81e30-193">此時，使用者會進入聊天室並準備參與。</span><span class="sxs-lookup"><span data-stu-id="81e30-193">At this point, the user enters the chat room and is ready to participate.</span></span>

4.  <span data-ttu-id="81e30-194">[User1] 會輸入新郵件，然後按一下 [**傳送**]。</span><span class="sxs-lookup"><span data-stu-id="81e30-194">User1 enters a new message, and then clicks **Send**.</span></span> <span data-ttu-id="81e30-195">持續聊天用戶端會將訊息張貼到 SIP 資訊 XCCOS **grpchat**命令中的聊天室。</span><span class="sxs-lookup"><span data-stu-id="81e30-195">The Persistent Chat client posts the message to the chat room in a SIP INFO XCCOS **grpchat** command.</span></span> <span data-ttu-id="81e30-196">持續聊天伺服器會將此新郵件的複本儲存在持久的聊天后端資料庫中。</span><span class="sxs-lookup"><span data-stu-id="81e30-196">Persistent Chat Server stores a copy of this new message in the Persistent Chat back-end database.</span></span>

5.  <span data-ttu-id="81e30-197">持續聊天伺服器會將 SIP**資訊 XCCOS 的**個別複本傳送給使用者，他們已進入聊天室。</span><span class="sxs-lookup"><span data-stu-id="81e30-197">Persistent Chat Server sends a separate copy of the SIP INFO XCCOS **grpchat** message to User2, who has already entered the chat room.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a><span data-ttu-id="81e30-198">持續交談合規性通話流程</span><span class="sxs-lookup"><span data-stu-id="81e30-198">Persistent Chat Compliance Call Flows</span></span>

<span data-ttu-id="81e30-199">Persistent 聊天伺服器使用訊息佇列（也稱為 MSMQ）和額外的規範資料庫（mgccomp）來處理合規性資料。</span><span class="sxs-lookup"><span data-stu-id="81e30-199">Persistent Chat Server uses Message Queuing (also known as MSMQ) and an additional compliance database (mgccomp) to process compliance data.</span></span> <span data-ttu-id="81e30-200">如需處理合規性事件的方式範例，下列事件順序說明如何處理訊息張貼事件。</span><span class="sxs-lookup"><span data-stu-id="81e30-200">As an example of how compliance events are processed, the following sequence of events describes how a message post event is processed.</span></span>

1.  <span data-ttu-id="81e30-201">使用者將訊息張貼到聊天室。</span><span class="sxs-lookup"><span data-stu-id="81e30-201">A user posts a message to a room.</span></span>

2.  <span data-ttu-id="81e30-202">持續聊天伺服器會將與事件相關的資訊放在私人訊息佇列佇列中。</span><span class="sxs-lookup"><span data-stu-id="81e30-202">Persistent Chat Server places information pertaining to the event in a private Message Queuing queue.</span></span>

3.  <span data-ttu-id="81e30-203">Persistent 聊天合規性伺服器會從佇列中讀取這個事件，並將它放在 mgccomp 資料庫中供日後進行處理。</span><span class="sxs-lookup"><span data-stu-id="81e30-203">Persistent Chat Compliance server reads this event from the queue, and places it into the mgccomp database for processing later.</span></span>

4.  <span data-ttu-id="81e30-204">持續性聊天規範伺服器會定期處理資料庫中的一組事件，並將其傳送至持久聊天合規性配接器以進行處理。</span><span class="sxs-lookup"><span data-stu-id="81e30-204">Periodically, the Persistent Chat Compliance server processes a set of events in the database, and sends them to the Persistent Chat Compliance adapter for processing.</span></span>

5.  <span data-ttu-id="81e30-205">如果配接器成功處理資料，持久的聊天合規性伺服器會從 mgccomp 資料庫中刪除事件。</span><span class="sxs-lookup"><span data-stu-id="81e30-205">If the adapter successfully processes the data, Persistent Chat Compliance server deletes the events from the mgccomp database.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

