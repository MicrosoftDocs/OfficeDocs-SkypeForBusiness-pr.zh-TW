---
title: Lync Server 2013： Persistent Chat Server 的運作方式
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
ms.openlocfilehash: 4a88bdad2a73022468297d73dd10bff0d26a3fee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a><span data-ttu-id="1998d-102">在 Lync Server 2013 中，Persistent Chat Server 的運作方式</span><span class="sxs-lookup"><span data-stu-id="1998d-102">How Persistent Chat Server works in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1998d-103">_**主題上次修改日期：** 2012-11-21_</span><span class="sxs-lookup"><span data-stu-id="1998d-103">_**Topic Last Modified:** 2012-11-21_</span></span>

<span data-ttu-id="1998d-104">Lync Server 2013，Persistent Chat Server 可讓您加入一段時間內的多方、主題型交談。</span><span class="sxs-lookup"><span data-stu-id="1998d-104">Lync Server 2013, Persistent Chat Server enables you to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="1998d-105">Persistent Chat Server 可以協助貴組織執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="1998d-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="1998d-106">改進地理位置分散且跨部門之小組間的通訊</span><span class="sxs-lookup"><span data-stu-id="1998d-106">Improve communication between geographically dispersed and cross-functional teams</span></span>

  - <span data-ttu-id="1998d-107">擴大資訊傳達和參與範圍</span><span class="sxs-lookup"><span data-stu-id="1998d-107">Broaden information awareness and participation</span></span>

  - <span data-ttu-id="1998d-108">改進大組織的通訊</span><span class="sxs-lookup"><span data-stu-id="1998d-108">Improve communication with your extended organization</span></span>

  - <span data-ttu-id="1998d-109">緩和資訊超載的狀況</span><span class="sxs-lookup"><span data-stu-id="1998d-109">Reduce information overload</span></span>

  - <span data-ttu-id="1998d-110">改進資訊傳達方式</span><span class="sxs-lookup"><span data-stu-id="1998d-110">Improve information awareness</span></span>

  - <span data-ttu-id="1998d-111">加強重要知識和資訊的傳播</span><span class="sxs-lookup"><span data-stu-id="1998d-111">Increase dispersion of important knowledge and information</span></span>

<span data-ttu-id="1998d-112">您可以將 Persistent Chat Server 部署為具有 Lync Server 2013 的選用角色。</span><span class="sxs-lookup"><span data-stu-id="1998d-112">You can deploy Persistent Chat Server as an optional role with Lync Server 2013.</span></span> <span data-ttu-id="1998d-113">在專用集區上執行 persistent Chat services，且 Persistent Chat Server 集區取決於 Lync 伺服器集區，以將郵件路由傳送至該伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="1998d-113">Persistent Chat services run on a dedicated pool, and a Persistent Chat Server pool depends on a Lync Server pool to route messages to it.</span></span> <span data-ttu-id="1998d-114">用戶端將使用 eXtensible Chat Communication Over SIP (XCCOS)。</span><span class="sxs-lookup"><span data-stu-id="1998d-114">Clients use eXtensible Chat Communication Over SIP (XCCOS).</span></span> <span data-ttu-id="1998d-115">Lync Server 前端伺服器設定為將流量路由傳送至 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="1998d-115">The Lync Server Front End Servers are configured to route the traffic to a Persistent Chat Server pool.</span></span>

<div>

## <a name="high-level-architecture"></a><span data-ttu-id="1998d-116">高層架構</span><span class="sxs-lookup"><span data-stu-id="1998d-116">High-Level Architecture</span></span>

<span data-ttu-id="1998d-117">下列圖表提供 Persistent Chat Server 架構和服務的高層級。</span><span class="sxs-lookup"><span data-stu-id="1998d-117">The following diagrams provide high-level perspectives of the Persistent Chat Server architecture and services.</span></span>

<span data-ttu-id="1998d-118">**Persistent Chat Server 高層架構**</span><span class="sxs-lookup"><span data-stu-id="1998d-118">**Persistent Chat Server High-Level Architecture**</span></span>

<span data-ttu-id="1998d-119">![Persistent Chat Server 架構。](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Persistent Chat Server 架構。")</span><span class="sxs-lookup"><span data-stu-id="1998d-119">![Persistent Chat Server architecture.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Persistent Chat Server architecture.")</span></span>

<span data-ttu-id="1998d-120">**Persistent Chat Server 高層服務**</span><span class="sxs-lookup"><span data-stu-id="1998d-120">**Persistent Chat Server High-Level Services**</span></span>

<span data-ttu-id="1998d-121">![Persistent Chat Server 元件。](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Persistent Chat Server 元件。")</span><span class="sxs-lookup"><span data-stu-id="1998d-121">![Persistent Chat Server components.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Persistent Chat Server components.")</span></span>

<span data-ttu-id="1998d-122">在 Persistent Chat Server 前端伺服器上執行的兩項服務：</span><span class="sxs-lookup"><span data-stu-id="1998d-122">Two services run on the Persistent Chat Server Front End Servers:</span></span>

  - <span data-ttu-id="1998d-123">常設聊天室 (通道)</span><span class="sxs-lookup"><span data-stu-id="1998d-123">Persistent Chat (Channel)</span></span>

  - <span data-ttu-id="1998d-124">合規性</span><span class="sxs-lookup"><span data-stu-id="1998d-124">Compliance</span></span>

<div>

## <a name="persistent-chat-channel-service"></a><span data-ttu-id="1998d-125">常設聊天室 (通道) 服務</span><span class="sxs-lookup"><span data-stu-id="1998d-125">Persistent Chat (Channel) Service</span></span>

<span data-ttu-id="1998d-126">Persistent Chat (通道) 服務是負責 Persistent Chat Server 的核心服務。</span><span class="sxs-lookup"><span data-stu-id="1998d-126">The Persistent Chat (Channel) service is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="1998d-127">此服務提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="1998d-127">This service provides the following functions:</span></span>

  - <span data-ttu-id="1998d-128">接受傳入訊息</span><span class="sxs-lookup"><span data-stu-id="1998d-128">Accepts incoming messages</span></span>

  - <span data-ttu-id="1998d-129">在持續聊天室內註冊和列出線上參與者</span><span class="sxs-lookup"><span data-stu-id="1998d-129">Registers and lists online participants within a Persistent Chat room</span></span>

  - <span data-ttu-id="1998d-130">重新傳輸訊息給其他通道訂閱者</span><span class="sxs-lookup"><span data-stu-id="1998d-130">Retransmits messages to other channel subscribers</span></span>

  - <span data-ttu-id="1998d-131">實作通道管理、聊天室邀請、搜尋及新內容通知的邏輯</span><span class="sxs-lookup"><span data-stu-id="1998d-131">Implements logic for channel management, chat room invitation, search, and new content notifications</span></span>

<span data-ttu-id="1998d-132">Persistent Chat (通道) 服務會透過使用 Persistent 聊天存放區，儲存和存取聊天室內容及其他系統中繼資料 (授權規則等) 。</span><span class="sxs-lookup"><span data-stu-id="1998d-132">The Persistent Chat (Channel) service stores and accesses chat room content and other system metadata (authorization rules, and so on) by using the Persistent Chat Store.</span></span> <span data-ttu-id="1998d-133">此項服務會將上傳至聊天室的檔案儲存在 Persistent Chat File Store 中。</span><span class="sxs-lookup"><span data-stu-id="1998d-133">This service stores files that are uploaded into chat rooms in the Persistent Chat File Store.</span></span>

</div>

<div>

## <a name="compliance-service"></a><span data-ttu-id="1998d-134">規範服務</span><span class="sxs-lookup"><span data-stu-id="1998d-134">Compliance Service</span></span>

<span data-ttu-id="1998d-135">規範服務是 Persistent Chat Server 的選用元件，負責將聊天內容和事件封存到 Persistent Chat 規範存放區。</span><span class="sxs-lookup"><span data-stu-id="1998d-135">The Compliance service is an optional component of Persistent Chat Server and is responsible for archiving chat content and events to the Persistent Chat Compliance Store.</span></span> <span data-ttu-id="1998d-136">如果貴組織的法規要求封存持續聊天活動，您可以部署選用的持續性聊天規範服務。</span><span class="sxs-lookup"><span data-stu-id="1998d-136">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="1998d-137">規範服務是安裝在 Persistent Chat 集區中的每個 Persistent Chat Server 上。</span><span class="sxs-lookup"><span data-stu-id="1998d-137">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> <span data-ttu-id="1998d-138">設定後，Persistent Chat Server 相容性會記錄使用者活動，例如加入和離開聊天室，以及張貼和讀取郵件。</span><span class="sxs-lookup"><span data-stu-id="1998d-138">When configured, Persistent Chat Server compliance records user activity such as joining and leaving rooms, and posting and reading of messages.</span></span> <span data-ttu-id="1998d-139">規範服務會儲存需要在 Persistent Chat 相容性檔案存放區中封存的檔案。</span><span class="sxs-lookup"><span data-stu-id="1998d-139">The Compliance service stores files that need to be archived in the Persistent Chat Compliance File Store.</span></span>

</div>

<div>

## <a name="persistent-chat-web-services"></a><span data-ttu-id="1998d-140">Persistent Chat Web 服務</span><span class="sxs-lookup"><span data-stu-id="1998d-140">Persistent Chat Web Services</span></span>

<span data-ttu-id="1998d-141">在 Lync Server 前端伺服器上，執行的兩個服務會依 Internet Information Services (IIS) 所執行，並以 web 元件的形式執行：</span><span class="sxs-lookup"><span data-stu-id="1998d-141">On the Lync Server Front End Servers, two services run that depend on Internet Information Services (IIS), and are implemented as web components:</span></span>

  - <span data-ttu-id="1998d-142">檔案**上傳/下載的持續性聊天 Web 服務**負責在聊天室中張貼及檢索檔案。</span><span class="sxs-lookup"><span data-stu-id="1998d-142">**Persistent Chat Web Services for File Upload/Download** Responsible for posting and retrieving files from chat rooms.</span></span>

  - <span data-ttu-id="1998d-143">**聊天室管理的持續性聊天 Web 服務**負責為使用者提供管理其聊天室的能力，以及建立新的聊天室。</span><span class="sxs-lookup"><span data-stu-id="1998d-143">**Persistent Chat Web Services for Chat Room Management** Responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a><span data-ttu-id="1998d-144">如何開始使用 Persistent Chat Server？</span><span class="sxs-lookup"><span data-stu-id="1998d-144">How Do I Start Using Persistent Chat Server?</span></span>

<span data-ttu-id="1998d-145">Persistent Chat Server 是 Lync Server 2013 基礎結構中的選用伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="1998d-145">Persistent Chat Server is an optional server role within the Lync Server 2013 infrastructure.</span></span> <span data-ttu-id="1998d-146">如果您安裝 Persistent Chat Server role，系統管理員已透過原則啟用的任何使用者，都可以搭配 Lync 2013 用戶端使用持續性聊天。</span><span class="sxs-lookup"><span data-stu-id="1998d-146">If you install the Persistent Chat Server role, any users who have been enabled through policy by an administrator can use Persistent Chat with the Lync 2013 client.</span></span>

<span data-ttu-id="1998d-147">如需如何部署 Persistent Chat Server 及如何讓使用者透過原則使用功能的詳細資訊，請參閱[在 Lync server 2013 中部署 Persistent Chat Server](lync-server-2013-deploying-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="1998d-147">For details about how to deploy Persistent Chat Server and enable users to leverage the capabilities by policy, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>

<span data-ttu-id="1998d-148">如需如何設定持久聊天伺服器部署設定的詳細資訊，請參閱[部署 Persistent Chat server In Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md)和[管理 Lync Server 2013，Persistent chat server](managing-lync-server-2013-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="1998d-148">For details about how to configure settings on your Persistent Chat Server deployment, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="1998d-149">如需如何依據原則啟用使用者以在 Lync 2013 用戶端上利用持續性聊天功能的詳細資訊，請參閱[部署 Persistent Chat server In Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md)和[管理 Lync Server 2013，Persistent chat server](managing-lync-server-2013-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="1998d-149">For details about how to enable users by policy such that they can leverage Persistent Chat functionality in Lync 2013 client, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) and [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).</span></span>

<span data-ttu-id="1998d-150">如果您已部署持續性聊天相容性，請參閱[管理 Lync server 2013 和 Persistent Chat server](managing-lync-server-2013-persistent-chat-server.md) ，以取得如何設定規范設定的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="1998d-150">If you deployed Persistent Chat compliance, see [Managing Lync Server 2013, Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) for details about how to configure settings for compliance.</span></span>

</div>

<div>

## <a name="persistent-chat-call-flows"></a><span data-ttu-id="1998d-151">Persistent 聊天通話流程</span><span class="sxs-lookup"><span data-stu-id="1998d-151">Persistent Chat Call Flows</span></span>

<span data-ttu-id="1998d-152">Persistent Chat 用戶端會使用 XCCOS 與 Persistent Chat service 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="1998d-152">The Persistent Chat client communicates with the Persistent Chat service by using XCCOS.</span></span> <span data-ttu-id="1998d-153">下列順序描述登入程序、一般聊天室訂閱以及訊息張貼的情況。</span><span class="sxs-lookup"><span data-stu-id="1998d-153">The following sequences describe the sign-in process and a typical room subscription and message post scenario.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="1998d-154">登入</span><span class="sxs-lookup"><span data-stu-id="1998d-154">Sign-in</span></span>

<span data-ttu-id="1998d-155">下列通話流程圖表和步驟說明登入程式。</span><span class="sxs-lookup"><span data-stu-id="1998d-155">The following call flow diagram and steps describe the sign-in process.</span></span>

<span data-ttu-id="1998d-156">**Persistent Chat 用戶端登入通話流程**</span><span class="sxs-lookup"><span data-stu-id="1998d-156">**Persistent Chat Client Sign-in Call Flow**</span></span>

<span data-ttu-id="1998d-157">![Persistent Chat Server 呼叫流程圖表。](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Persistent Chat Server 呼叫流程圖表。")</span><span class="sxs-lookup"><span data-stu-id="1998d-157">![Persistent Chat Server call flow diagram.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Persistent Chat Server call flow diagram.")</span></span>

1.  <span data-ttu-id="1998d-158">Persistent Chat 用戶端會先傳送 SIP 訂閱，以從伺服器中取得帶內布建檔。</span><span class="sxs-lookup"><span data-stu-id="1998d-158">The Persistent Chat client first sends a SIP SUBSCRIBE to retrieve the in-band provisioning document from the server.</span></span> <span data-ttu-id="1998d-159">這份檔會指出為使用者啟用或停用持續性聊天，以及 Persistent Chat Server 集區的 SIP URIs 清單。</span><span class="sxs-lookup"><span data-stu-id="1998d-159">This document indicates if Persistent Chat is enabled or disabled for the user and the list of SIP URIs for the Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="1998d-160">Persistent Chat 用戶端會將 SIP 邀請郵件傳送至在上一個步驟中取得之 Persistent Chat Server 的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="1998d-160">The Persistent Chat client sends a SIP INVITE message to the SIP URI of the Persistent Chat Server that it obtained in the previous step.</span></span> <span data-ttu-id="1998d-161">邀請順序後面接著是 200 OK 和 ACK，而且 Persistent Chat 用戶端現在已開啟具有 Persistent Chat Server 端點的 SIP 會話。</span><span class="sxs-lookup"><span data-stu-id="1998d-161">The INVITE sequence is followed by 200 OK and ACK, and the Persistent Chat client has now opened a SIP session with a Persistent Chat Server endpoint.</span></span> <span data-ttu-id="1998d-162">因此，Persistent Chat 用戶端會傳送 SIP 資訊郵件（包含聊天訊息或命令要求伺服器以採取動作），以與 Persistent 聊天伺服器進行通訊。</span><span class="sxs-lookup"><span data-stu-id="1998d-162">Consequently, the Persistent Chat client communicates with Persistent Chat Server by sending SIP INFO messages that contain either chat messages or commands requesting the server to take an action.</span></span> <span data-ttu-id="1998d-163">所有這些訊息都會以 200 OK 或「503 服務無法使用」(亦即在伺服器負載過重的情況下) 進行認可。</span><span class="sxs-lookup"><span data-stu-id="1998d-163">All of these messages are acknowledged with either 200 OK or 503 Service Unavailable (that is, in the event of heavy server load).</span></span> <span data-ttu-id="1998d-164">如果用戶端收到 503 回應，會重試訊息。</span><span class="sxs-lookup"><span data-stu-id="1998d-164">If the client receives a 503 response, it will retry the message.</span></span> <span data-ttu-id="1998d-165"> (本範例不包含503回應。 ) 如果伺服器接受郵件或命令，並傳送200，則該範例會以個別 SIP 資訊郵件的形式來提供對用戶端的回應。</span><span class="sxs-lookup"><span data-stu-id="1998d-165">(This example does not include a 503 response.) If the server accepts the message or command and sends 200 OK, it provides a response to the client in the form of a separate SIP INFO message.</span></span> <span data-ttu-id="1998d-166">該回應會包含對原始命令的參考。</span><span class="sxs-lookup"><span data-stu-id="1998d-166">This response includes a reference to the originating command.</span></span>

3.  <span data-ttu-id="1998d-167">Persistent Chat client 會傳送包含 XCCOS **getserverinfo**命令的 SIP 資訊訊息。</span><span class="sxs-lookup"><span data-stu-id="1998d-167">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getserverinfo** command.</span></span> <span data-ttu-id="1998d-168">Persistent Chat Server 會使用包含 Persistent Chat service 設定相關資訊的新 SIP 資訊郵件進行回復。</span><span class="sxs-lookup"><span data-stu-id="1998d-168">Persistent Chat Server replies with a new SIP INFO message that contains information about the Persistent Chat service configuration.</span></span>

4.  <span data-ttu-id="1998d-169">Persistent Chat client 會傳送包含 XCCOS **getassociations**命令的 SIP 資訊訊息。</span><span class="sxs-lookup"><span data-stu-id="1998d-169">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **getassociations** command.</span></span> <span data-ttu-id="1998d-170">Persistent Chat Server 會以新的 SIP 資訊訊息（包含使用者所屬聊天室的清單）進行回復。</span><span class="sxs-lookup"><span data-stu-id="1998d-170">Persistent Chat Server replies with a new SIP INFO message that contains the list of rooms of which the user is a member.</span></span> <span data-ttu-id="1998d-171">Persistent Chat 用戶端會重複執行此命令，以取得使用者為主管的聊天室清單。</span><span class="sxs-lookup"><span data-stu-id="1998d-171">The Persistent Chat client repeats the command to retrieve the list of rooms of which the user is a manager.</span></span>

5.  <span data-ttu-id="1998d-172">Persistent Chat 用戶端會從「目前狀態」檔取得關注的會議室清單，其中每個後續的會議室都會以 "roomSetting" 類別來表示。</span><span class="sxs-lookup"><span data-stu-id="1998d-172">The Persistent Chat client gets the list of followed rooms from the "presence" document, where each followed room is represented by a "roomSetting" category.</span></span> <span data-ttu-id="1998d-173">所有追蹤聊天室會聯結包含 XCCOS **bjoin** 命令的單一 SIP INFO 訊息，命令中又包含聊天室 URI 的清單。</span><span class="sxs-lookup"><span data-stu-id="1998d-173">All followed rooms are joined by a single SIP INFO message that contains the XCCOS **bjoin** command that contains the list of room URIs.</span></span> <span data-ttu-id="1998d-174">因為追蹤聊天室的清單保存在伺服器上，在任何電腦上的任何用戶端對於指定的使用者 URI 都有同樣的追蹤聊天室清單。</span><span class="sxs-lookup"><span data-stu-id="1998d-174">Because the list of followed rooms is kept on the server, any client on any computer has the same list of followed rooms for the specified user URI.</span></span> <span data-ttu-id="1998d-175">如果使用者在本機電腦登錄中) 啟用此選項，則持續聊天用戶端也會保留已開啟的 (會議室清單，然後在登入時，傳送包含每個開啟聊天室之 XCCOS **join**命令的 SIP 資訊訊息，以加入這些會議室。</span><span class="sxs-lookup"><span data-stu-id="1998d-175">The Persistent Chat client also keeps the list of opened rooms (if this option is enabled by the user) in the local computer registry, and joins each of these rooms at sign-in by sending a SIP INFO message that contains the XCCOS **join** command for each opened room.</span></span> <span data-ttu-id="1998d-176">因為此清單保留在登錄中，所以在不同電腦上執行的兩個 Persistent 聊天用戶端上可能會有不同的狀態。</span><span class="sxs-lookup"><span data-stu-id="1998d-176">Because this list is kept in the registry, it can be different on two Persistent Chat clients running on different computers.</span></span>

6.  <span data-ttu-id="1998d-177">在每個加入的會議室中，Persistent Chat 用戶端會傳送包含 XCCOS **bccoNtext**命令的 SIP 資訊訊息。</span><span class="sxs-lookup"><span data-stu-id="1998d-177">For each room joined, the Persistent Chat client sends a SIP INFO message that contains the XCCOS **bccontext** command.</span></span> <span data-ttu-id="1998d-178">Persistent Chat Server 會以新的 SIP 資訊訊息回復，該訊息包含會議室中的最近聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="1998d-178">Persistent Chat Server replies with a new SIP INFO message that contains the most recent chat message in the room.</span></span>

7.  <span data-ttu-id="1998d-179">Persistent Chat client 會傳送包含 XCCOS **getinv** (的 SIP 資訊郵件，也就是取得「邀請) 」命令，以要求用戶端尚未看到任何新的會議室邀請。</span><span class="sxs-lookup"><span data-stu-id="1998d-179">The Persistent Chat client sends a SIP INFO message that contains a XCCOS **getinv** (that is, get invitation) command to request any new room invitations that the client has not yet seen.</span></span> <span data-ttu-id="1998d-180">在個別的 SIP 資訊訊息中，Persistent Chat Server 會傳回這些聊天室的清單。</span><span class="sxs-lookup"><span data-stu-id="1998d-180">In a separate SIP INFO message, Persistent Chat Server returns a list of those rooms.</span></span>

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a><span data-ttu-id="1998d-181">訂閱聊天室及張貼訊息</span><span class="sxs-lookup"><span data-stu-id="1998d-181">Subscribe to a Room and Post a Message</span></span>

<span data-ttu-id="1998d-182">下列通話流程圖表和步驟說明一般會議室訂閱和郵件發表後的情況。</span><span class="sxs-lookup"><span data-stu-id="1998d-182">The following call flow diagram and steps describe a typical room subscription and message post scenario.</span></span>

<span data-ttu-id="1998d-183">**Persistent Chat Client 聊天室訂閱和郵件張貼通話流程**</span><span class="sxs-lookup"><span data-stu-id="1998d-183">**Persistent Chat Client Room Subscription and Message Posting Call Flow**</span></span>

<span data-ttu-id="1998d-184">![會議室訂閱和郵件發表後案例。](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "會議室訂閱和郵件發表後案例。")</span><span class="sxs-lookup"><span data-stu-id="1998d-184">![Room subscription and message post scenario.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Room subscription and message post scenario.")</span></span>

1.  <span data-ttu-id="1998d-185">在 [Persistent Chat] 用戶端中，User1 按一下 [**加入聊天室**]，按一下 [**搜尋**]，然後輸入某些搜尋準則。</span><span class="sxs-lookup"><span data-stu-id="1998d-185">From the Persistent Chat client, User1 clicks **Join a Chat Room**, clicks **Search**, and then enters some search criteria.</span></span> <span data-ttu-id="1998d-186">Persistent Chat client 會傳送包含 XCCOS)  (**chansrch**的 SIP 資訊郵件，以及搜尋準則。</span><span class="sxs-lookup"><span data-stu-id="1998d-186">The Persistent Chat client sends a SIP INFO message that contains the XCCOS **chansrch** (room search) command, along with the search criteria.</span></span> <span data-ttu-id="1998d-187">Persistent Chat Server 會查詢後端資料庫，並在新的 SIP 資訊訊息中回復，其中包含符合搜尋準則的可用會議室清單。</span><span class="sxs-lookup"><span data-stu-id="1998d-187">Persistent Chat Server queries the back-end database and replies in a new SIP INFO message that contains a list of available rooms that meet the search criteria.</span></span>

2.  <span data-ttu-id="1998d-188">使用者 1 選取要加入的聊天室，然後按一下 **[追蹤此聊天室]**。</span><span class="sxs-lookup"><span data-stu-id="1998d-188">User1 selects the chat room that he or she wants to join, and then clicks **Follow this room**.</span></span> <span data-ttu-id="1998d-189">Persistent Chat client 會傳送 Persistent Chat Server 包含 XCCOS **join**命令的 SIP 資訊訊息，以及使用者選取之聊天室的會議室識別碼。</span><span class="sxs-lookup"><span data-stu-id="1998d-189">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **join** command and the room ID of the chat room that the user selected.</span></span> <span data-ttu-id="1998d-190">Persistent Chat Server 會回復包含布建資料的 SIP 資訊訊息。</span><span class="sxs-lookup"><span data-stu-id="1998d-190">Persistent Chat Server replies with a SIP INFO message that contains the provisioning data.</span></span>

3.  <span data-ttu-id="1998d-191">Persistent Chat client 會傳送 Persistent Chat Server 包含 XCCOS **bccoNtext** (backchat coNtext) 命令的 SIP 資訊訊息。</span><span class="sxs-lookup"><span data-stu-id="1998d-191">The Persistent Chat client sends Persistent Chat Server a SIP INFO message that contains the XCCOS **bccontext** (backchat context) command.</span></span> <span data-ttu-id="1998d-192">Persistent Chat Server 會檢索聊天記錄，並將它以個別 SIP 資訊訊息傳回給 Persistent Chat 用戶端。</span><span class="sxs-lookup"><span data-stu-id="1998d-192">Persistent Chat Server retrieves the chat history, and returns it to the Persistent Chat client in a separate SIP INFO message.</span></span> <span data-ttu-id="1998d-193">此時，使用者進入聊天室，準備就緒參與。</span><span class="sxs-lookup"><span data-stu-id="1998d-193">At this point, the user enters the chat room and is ready to participate.</span></span>

4.  <span data-ttu-id="1998d-194">使用者 1 輸入新訊息，然後按一下 **[傳送]**。</span><span class="sxs-lookup"><span data-stu-id="1998d-194">User1 enters a new message, and then clicks **Send**.</span></span> <span data-ttu-id="1998d-195">Persistent Chat 用戶端會將郵件傳送至 SIP INFO XCCOS **grpchat**命令中的聊天室。</span><span class="sxs-lookup"><span data-stu-id="1998d-195">The Persistent Chat client posts the message to the chat room in a SIP INFO XCCOS **grpchat** command.</span></span> <span data-ttu-id="1998d-196">Persistent Chat Server 會在 Persistent Chat 後端資料庫中儲存這封新郵件的複本。</span><span class="sxs-lookup"><span data-stu-id="1998d-196">Persistent Chat Server stores a copy of this new message in the Persistent Chat back-end database.</span></span>

5.  <span data-ttu-id="1998d-197">Persistent Chat Server 會傳送個別的 SIP 資訊 XCCOS **grpchat**郵件複本給使用者，他已經輸入聊天室。</span><span class="sxs-lookup"><span data-stu-id="1998d-197">Persistent Chat Server sends a separate copy of the SIP INFO XCCOS **grpchat** message to User2, who has already entered the chat room.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a><span data-ttu-id="1998d-198">Persistent Chat 相容性通話流程</span><span class="sxs-lookup"><span data-stu-id="1998d-198">Persistent Chat Compliance Call Flows</span></span>

<span data-ttu-id="1998d-199">Persistent Chat Server 會使用訊息佇列 (又稱為 MSMQ) ，另一種是規範資料庫 (mgccomp) 來處理規範資料。</span><span class="sxs-lookup"><span data-stu-id="1998d-199">Persistent Chat Server uses Message Queuing (also known as MSMQ) and an additional compliance database (mgccomp) to process compliance data.</span></span> <span data-ttu-id="1998d-200">下列事件順序描述如何處理訊息張貼事件，用以作為如何處理規範事件的範例。</span><span class="sxs-lookup"><span data-stu-id="1998d-200">As an example of how compliance events are processed, the following sequence of events describes how a message post event is processed.</span></span>

1.  <span data-ttu-id="1998d-201">使用者在聊天室張貼訊息。</span><span class="sxs-lookup"><span data-stu-id="1998d-201">A user posts a message to a room.</span></span>

2.  <span data-ttu-id="1998d-202">Persistent Chat Server 會將相關資訊放入私人訊息佇列佇列中的事件。</span><span class="sxs-lookup"><span data-stu-id="1998d-202">Persistent Chat Server places information pertaining to the event in a private Message Queuing queue.</span></span>

3.  <span data-ttu-id="1998d-203">Persistent Chat 規範伺服器會從佇列中讀取此事件，並將它放入 mgccomp 資料庫，以備日後處理。</span><span class="sxs-lookup"><span data-stu-id="1998d-203">Persistent Chat Compliance server reads this event from the queue, and places it into the mgccomp database for processing later.</span></span>

4.  <span data-ttu-id="1998d-204">Persistent Chat 規範伺服器會定期處理資料庫中的一組事件，並將其傳送至 Persistent Chat 合規性介面卡以進行處理。</span><span class="sxs-lookup"><span data-stu-id="1998d-204">Periodically, the Persistent Chat Compliance server processes a set of events in the database, and sends them to the Persistent Chat Compliance adapter for processing.</span></span>

5.  <span data-ttu-id="1998d-205">如果介面卡成功處理資料，Persistent Chat server 會刪除 mgccomp 資料庫中的事件。</span><span class="sxs-lookup"><span data-stu-id="1998d-205">If the adapter successfully processes the data, Persistent Chat Compliance server deletes the events from the mgccomp database.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

