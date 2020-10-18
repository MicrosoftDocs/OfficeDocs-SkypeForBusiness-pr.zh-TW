---
title: 查看 Microsoft SIP 處理語言 (MSPL) 伺服器應用程式
description: View (MSPL) 伺服器應用程式的 Microsoft SIP 處理語言。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d844acf542546a668c4fc086a07cd6a7bb4a8f5a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577069"
---
# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a><span data-ttu-id="b9ee6-103">在 Lync Server 2013 中查看 Microsoft SIP 處理語言 (MSPL) 伺服器應用程式</span><span class="sxs-lookup"><span data-stu-id="b9ee6-103">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9ee6-104">_**主題上次修改日期：** 2014-09-26_</span><span class="sxs-lookup"><span data-stu-id="b9ee6-104">_**Topic Last Modified:** 2014-09-26_</span></span>

<span data-ttu-id="b9ee6-105">Microsoft SIP 處理語言 (MSPL) server 應用程式是一種僅限腳本的應用程式，其使用指令碼語言，而不是 Microsoft Lync 2010 API。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-105">A Microsoft SIP Processing Language (MSPL) server application is a script-only application that uses a scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="b9ee6-106">MSPL 針對篩選和 proxy 行為提供更細微的控制，除了用於將特定郵件傳送至交易型 SIP 應用程式的工具之外。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-106">MSPL provides more granular control over filtering and proxy behaviors, in addition to a facility for dispatching specific messages to transaction-based SIP applications.</span></span> <span data-ttu-id="b9ee6-107">MSPL 特別用於篩選和路由 SIP 郵件。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-107">MSPL is used specifically for filtering and routing SIP messages.</span></span> <span data-ttu-id="b9ee6-108">MSPL 應用程式會在與 UserServices 模組相同的進程中執行，而以 Lync 2010 API 為基礎的程式則會在個別的進程中執行。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-108">MSPL applications run in the same process as the UserServices module, while a program that is based on the Lync 2010 API runs in a separate process.</span></span>

<span data-ttu-id="b9ee6-109">您可以使用 Lync Server 控制台的**拓撲**群組中的 [**伺服器應用程式**] 頁面，查看您的 lync Server 2013 環境中前端伺服器上執行的 MSPL 伺服器應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-109">You can use the **Server Application** page in the **Topology** group of Lync Server Control Panel to see a list of MSPL server applications that run on Front End Servers in your Lync Server 2013 environment.</span></span> <span data-ttu-id="b9ee6-110">清單會顯示每個集區可用的腳本，以及這些腳本是否已啟用或很重要。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-110">The list shows the scripts that are available for each pool, as well as whether they are enabled or critical.</span></span> <span data-ttu-id="b9ee6-111">腳本會依照列出的循序執行。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-111">The scripts run in the order they are listed.</span></span>

<span data-ttu-id="b9ee6-112">這些指令碼包括下列項目：</span><span class="sxs-lookup"><span data-stu-id="b9ee6-112">These scripts include the following:</span></span>

  - <span data-ttu-id="b9ee6-113">ClientVersionFilter 為系統管理員提供一種方法，用以指定集區支援的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-113">ClientVersionFilter provides the administrator with a way to specify the version of clients that are supported by a pool.</span></span> <span data-ttu-id="b9ee6-114">用戶端版本篩選器會檢查用戶端版本，並可防止用戶端登入或向使用者顯示訊息，指出其使用的是不支援的用戶端。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-114">The client version filter checks the client version and can either prevent the client from logging on or present the user with a message that indicates he or she is using a client that is not supported.</span></span> <span data-ttu-id="b9ee6-115">用戶端版本篩選也可以設定為向使用者顯示一則訊息，該使用者包含最新可下載版本用戶端的 URL。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-115">The client version filter can also be configured to display a message to the user that contains the URL of the latest downloadable version of the client.</span></span>

  - <span data-ttu-id="b9ee6-116">TranslationService 會轉譯使用者根據系統管理員所定義的正規化規則，撥打 e.164 號碼的數位。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-116">TranslationService translates a number that a user dials to an E.164 number according to the normalization rules defined by the administrator.</span></span> <span data-ttu-id="b9ee6-117">如需詳細資訊，請參閱 [Lync Server 2013 中的轉譯規則](lync-server-2013-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-117">For details, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md).</span></span>

  - <span data-ttu-id="b9ee6-118">IncomingFederation 會針對租使用者和來自外部部署的內送郵件，強制執行租使用者層級的同盟驗證。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-118">IncomingFederation enforces tenant-level federation validation for inter-tenant and incoming messages from external deployments.</span></span>

  - <span data-ttu-id="b9ee6-119">UserServices 是前端伺服器的 SIP 註冊、目前狀態及會議元件。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-119">UserServices is the SIP Registrar, presence, and conferencing component of a Front End Server.</span></span> <span data-ttu-id="b9ee6-120">它提供了緊密整合的 IM、目前狀態及會議功能（建立于 SIP Proxy 之上）。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-120">It provides closely integrated IM, presence, and conferencing features built on top of the SIP Proxy.</span></span>

  - <span data-ttu-id="b9ee6-121">InterClusterRouting 負責將通話路由傳送至被呼叫者的主要註冊集區。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-121">InterClusterRouting is responsible for routing calls to the callee’s primary Registrar pool.</span></span> <span data-ttu-id="b9ee6-122">如需詳細資訊，請參閱 [Lync server 2013 的前端伺服器 VoIP 元件](lync-server-2013-front-end-server-voip-components.md)。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-122">For details, see [Front End Server VoIP components for Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span></span>

  - <span data-ttu-id="b9ee6-123">IIMFilter (智慧 IM 篩選) 會封鎖包含可按一下 URLs 或嘗試初始化檔案傳輸的郵件。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-123">IIMFilter (Intelligent IM Filter) blocks messages that contain clickable URLs or that attempt to initiate file transfers.</span></span> <span data-ttu-id="b9ee6-124">IIMFilter 也會代表伺服器檢查用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-124">IIMFilter also checks the client version on behalf of the server.</span></span> <span data-ttu-id="b9ee6-125">IIMFilter 會影響使用 Lync Server 或 Communicator 所初始化的檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-125">IIMFilter affects file transfers that are initiated by using either Lync Server or Communicator.</span></span> <span data-ttu-id="b9ee6-126">根據預設，會在連結的第一個字元之前新增底線字元，以停用可按一下的連結。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-126">By default, clickable links are disabled by adding an underscore character before the first character of the link.</span></span> <span data-ttu-id="b9ee6-127">管理員可以變更此行為，讓連結遭到封鎖，在這種情況下，包含可按一下的 URLs 或嘗試初始化檔案傳輸的郵件會遭到伺服器封鎖，無法到達其預定目的地。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-127">An administrator can change this behavior so that the link is blocked, in which case messages that contain clickable URLs or that attempt to initiate a file transfer are blocked by the server from reaching their intended destinations.</span></span> <span data-ttu-id="b9ee6-128">IIMFilter 已安裝在所有執行 Lync Server 的伺服器上，但 Proxy 伺服器和封存伺服器除外。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-128">IIMFilter is installed on all servers running Lync Server except Proxy Servers and Archiving Servers.</span></span>

  - <span data-ttu-id="b9ee6-129">UserPinService 用於驗證使用者個人識別碼 (Pin 碼) 的電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-129">UserPinService is used to verify user personal identification numbers (PINs) for dial-in conferencing.</span></span>

  - <span data-ttu-id="b9ee6-130">DefaultRouting 是執行 Lync Server 之伺服器的預設路由應用程式。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-130">DefaultRouting is the default routing application for servers running Lync Server.</span></span> <span data-ttu-id="b9ee6-131">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-131">It is enabled by default.</span></span> <span data-ttu-id="b9ee6-132">路由應用程式安裝在所有的 Standard Edition 和 Enterprise Edition server 上。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-132">The routing application is installed on all Standard Edition and Enterprise Edition servers.</span></span>

  - <span data-ttu-id="b9ee6-133">ExumRouting 將通話路由傳送至 Exchange Server 整合通訊 (UM) 。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-133">ExumRouting routes calls to Exchange Server Unified Messaging (UM).</span></span> <span data-ttu-id="b9ee6-134">ExumRouting 會決定當有新的語音信箱訊息要放入時，適當的 Exchange UM 伺服器將通話路由傳送至此。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-134">ExumRouting determines the appropriate Exchange UM server to route the call to when there is a new voice mail message to deposit.</span></span> <span data-ttu-id="b9ee6-135">ExumRouting 也會處理其他一些 Exchange UM 整合的層面，包括路由傳送至自動語音應答和使用者存取。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-135">ExumRouting also handles some other Exchange UM integration aspects, including routing to Auto Attendant and Subscriber Access.</span></span>

  - <span data-ttu-id="b9ee6-136">OutboundRouting 會根據撥打的號碼和使用者的撥號授權，決定將通話路由傳送至電話號碼的閘道。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-136">OutboundRouting determines the gateway that routes a call to a phone number according to the dialed number and the user’s dialing authorization.</span></span> <span data-ttu-id="b9ee6-137">如果閘道無法處理呼叫，OutboundRouting 也會處理呼叫的重新路由。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-137">OutboundRouting also handles rerouting of calls if a gateway cannot process a call.</span></span>

  - <span data-ttu-id="b9ee6-138">QoEAgent 會收到經驗品質 (QoE 透過 SIP 服務要求從端點) 資料包表，並將資料傳送至監控伺服器上的目的地佇列，或是使用 HTTP POST 將資料傳送至協力廠商消費者。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-138">QoEAgent receives Quality of Experience (QoE) data reports from endpoints through SIP SERVICE requests, and sends the data to the destination queue on the Monitoring Server or to third-party consumers using HTTP POST.</span></span> <span data-ttu-id="b9ee6-139">如需詳細資訊，請參閱 [在 Lync Server 2013 中部署監控](lync-server-2013-deploying-monitoring.md)。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-139">For details, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

  - <span data-ttu-id="b9ee6-140">OutgoingFederation 會對傳送至目標外部部署的郵件強制執行租使用者層級同盟驗證。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-140">OutgoingFederation enforces tenant-level federation validation for messages going to a targeted external deployment.</span></span>

  - <span data-ttu-id="b9ee6-141">AcpRouting proxy 邀請要求的音訊會議提供者到音訊會議提供者閘道的要求。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-141">AcpRouting proxies INVITE requests destined for the audio conferencing provider to the audio conferencing provider gateway.</span></span>

<span data-ttu-id="b9ee6-142">在 Edge Server 上執行的腳本包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="b9ee6-142">Scripts that run on Edge Servers include the following:</span></span>

  - <span data-ttu-id="b9ee6-143">IIMFilter</span><span class="sxs-lookup"><span data-stu-id="b9ee6-143">IIMFilter</span></span>

  - <span data-ttu-id="b9ee6-144">OptionsHandler 會回應含 200 OK 的傳入選項要求。如果要求是目前伺服器的目的地，則為 **[確定]** 。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-144">OptionsHandler responds to incoming OPTIONS requests with **200 OK** if the request is destined for the current server.</span></span> <span data-ttu-id="b9ee6-145">這用於拓撲驗證。</span><span class="sxs-lookup"><span data-stu-id="b9ee6-145">This is used for topology validation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b9ee6-146">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b9ee6-146">See Also</span></span>


[<span data-ttu-id="b9ee6-147">在 Lync Server 2013 中啟用或停用 Microsoft SIP 處理語言 (MSPL) 伺服器應用程式</span><span class="sxs-lookup"><span data-stu-id="b9ee6-147">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[<span data-ttu-id="b9ee6-148">在 Lync Server 2013 中將 Microsoft SIP 處理語言 (MSPL) 應用程式標示為關鍵或非關鍵</span><span class="sxs-lookup"><span data-stu-id="b9ee6-148">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

