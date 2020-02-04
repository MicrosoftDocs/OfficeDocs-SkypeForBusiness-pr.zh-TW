---
title: 檢視 Microsoft SIP Processing Language (MSPL) 伺服器應用程式
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
ms.openlocfilehash: 63c1ce638e6bc9509c8faf46b39989b366f610a0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a><span data-ttu-id="e0a3d-102">在 Lync Server 2013 中檢視 Microsoft SIP Processing Language (MSPL) 伺服器應用程式</span><span class="sxs-lookup"><span data-stu-id="e0a3d-102">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0a3d-103">_**主題上次修改日期：** 2014-09-26_</span><span class="sxs-lookup"><span data-stu-id="e0a3d-103">_**Topic Last Modified:** 2014-09-26_</span></span>

<span data-ttu-id="e0a3d-104">Microsoft SIP 處理語言（MSPL）伺服器應用程式是一個只使用指令碼語言的腳本式應用程式，而不是 Microsoft Lync 2010 API。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-104">A Microsoft SIP Processing Language (MSPL) server application is a script-only application that uses a scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="e0a3d-105">MSPL 提供對篩選與 proxy 行為的更精細控制，以及將特定訊息分派給事務型 SIP 應用程式的功能。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-105">MSPL provides more granular control over filtering and proxy behaviors, in addition to a facility for dispatching specific messages to transaction-based SIP applications.</span></span> <span data-ttu-id="e0a3d-106">MSPL 專門用來篩選和路由 SIP 訊息。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-106">MSPL is used specifically for filtering and routing SIP messages.</span></span> <span data-ttu-id="e0a3d-107">MSPL 應用程式在與 UserServices 模組相同的進程中執行，而以 Lync 2010 API 為基礎的程式是在個別的進程中執行。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-107">MSPL applications run in the same process as the UserServices module, while a program that is based on the Lync 2010 API runs in a separate process.</span></span>

<span data-ttu-id="e0a3d-108">您可以使用 Lync Server [控制台] 的 [**拓撲**] 群組中的 [**伺服器應用程式**] 頁面，來查看在 Lync server 2013 環境中，在前端伺服器上執行的 MSPL 伺服器應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-108">You can use the **Server Application** page in the **Topology** group of Lync Server Control Panel to see a list of MSPL server applications that run on Front End Servers in your Lync Server 2013 environment.</span></span> <span data-ttu-id="e0a3d-109">清單會顯示每個池可用的腳本，以及它們是否已啟用或重要。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-109">The list shows the scripts that are available for each pool, as well as whether they are enabled or critical.</span></span> <span data-ttu-id="e0a3d-110">腳本會以其列出的循序執行。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-110">The scripts run in the order they are listed.</span></span>

<span data-ttu-id="e0a3d-111">這些腳本包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="e0a3d-111">These scripts include the following:</span></span>

  - <span data-ttu-id="e0a3d-112">ClientVersionFilter 為管理員提供一種方式，以指定池支援的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-112">ClientVersionFilter provides the administrator with a way to specify the version of clients that are supported by a pool.</span></span> <span data-ttu-id="e0a3d-113">用戶端版本篩選會檢查用戶端版本，並可讓用戶端無法登入，或向使用者顯示一則訊息，指出他或她使用的用戶端不受支援。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-113">The client version filter checks the client version and can either prevent the client from logging on or present the user with a message that indicates he or she is using a client that is not supported.</span></span> <span data-ttu-id="e0a3d-114">您也可以設定 [用戶端版本] 篩選器，以向使用者顯示一則訊息，其中包含用戶端最新版下載版本的 URL。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-114">The client version filter can also be configured to display a message to the user that contains the URL of the latest downloadable version of the client.</span></span>

  - <span data-ttu-id="e0a3d-115">TranslationService 會根據管理員所定義的正常化規則，轉譯使用者以164個數字撥號的數位。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-115">TranslationService translates a number that a user dials to an E.164 number according to the normalization rules defined by the administrator.</span></span> <span data-ttu-id="e0a3d-116">如需詳細資訊，請參閱[Lync Server 2013 中的翻譯規則](lync-server-2013-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-116">For details, see [Translation rules in Lync Server 2013](lync-server-2013-translation-rules.md).</span></span>

  - <span data-ttu-id="e0a3d-117">IncomingFederation 會強制執行租使用者層級的同盟驗證與來自外部部署的傳入訊息。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-117">IncomingFederation enforces tenant-level federation validation for inter-tenant and incoming messages from external deployments.</span></span>

  - <span data-ttu-id="e0a3d-118">UserServices 是前端伺服器的 SIP 註冊機構、目前狀態和會議元件。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-118">UserServices is the SIP Registrar, presence, and conferencing component of a Front End Server.</span></span> <span data-ttu-id="e0a3d-119">它提供了在 SIP Proxy 之上建立的緊密整合 IM、目前狀態及會議功能。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-119">It provides closely integrated IM, presence, and conferencing features built on top of the SIP Proxy.</span></span>

  - <span data-ttu-id="e0a3d-120">InterClusterRouting 負責將呼叫路由到被叫方的主要註冊機構池。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-120">InterClusterRouting is responsible for routing calls to the callee’s primary Registrar pool.</span></span> <span data-ttu-id="e0a3d-121">如需詳細資訊，請參閱[Lync server 2013 的前端伺服器 VoIP 元件](lync-server-2013-front-end-server-voip-components.md)。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-121">For details, see [Front End Server VoIP components for Lync Server 2013](lync-server-2013-front-end-server-voip-components.md).</span></span>

  - <span data-ttu-id="e0a3d-122">IIMFilter （智慧 IM 篩選器）會封鎖包含可按一下之 Url 或試圖開機檔案傳輸的郵件。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-122">IIMFilter (Intelligent IM Filter) blocks messages that contain clickable URLs or that attempt to initiate file transfers.</span></span> <span data-ttu-id="e0a3d-123">IIMFilter 也會代表伺服器檢查用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-123">IIMFilter also checks the client version on behalf of the server.</span></span> <span data-ttu-id="e0a3d-124">IIMFilter 會影響使用 Lync Server 或 Communicator 啟動的檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-124">IIMFilter affects file transfers that are initiated by using either Lync Server or Communicator.</span></span> <span data-ttu-id="e0a3d-125">根據預設，在連結的第一個字元前面新增一個底線字元，即可停用可按一下的連結。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-125">By default, clickable links are disabled by adding an underscore character before the first character of the link.</span></span> <span data-ttu-id="e0a3d-126">系統管理員可以變更此行為，讓連結遭到封鎖，在這種情況下，包含可按一下之 Url 的郵件或試圖開機檔案傳輸的訊息，伺服器會封鎖其預定目的地。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-126">An administrator can change this behavior so that the link is blocked, in which case messages that contain clickable URLs or that attempt to initiate a file transfer are blocked by the server from reaching their intended destinations.</span></span> <span data-ttu-id="e0a3d-127">在執行 Lync Server 的所有伺服器上，除了 Proxy 伺服器與封存伺服器外，還會安裝 IIMFilter。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-127">IIMFilter is installed on all servers running Lync Server except Proxy Servers and Archiving Servers.</span></span>

  - <span data-ttu-id="e0a3d-128">UserPinService 是用來驗證電話撥入式會議的使用者個人識別碼（Pin）。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-128">UserPinService is used to verify user personal identification numbers (PINs) for dial-in conferencing.</span></span>

  - <span data-ttu-id="e0a3d-129">DefaultRouting 是運行 Lync Server 之伺服器的預設路由應用程式。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-129">DefaultRouting is the default routing application for servers running Lync Server.</span></span> <span data-ttu-id="e0a3d-130">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-130">It is enabled by default.</span></span> <span data-ttu-id="e0a3d-131">路由應用程式已安裝在所有標準版和企業版伺服器上。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-131">The routing application is installed on all Standard Edition and Enterprise Edition servers.</span></span>

  - <span data-ttu-id="e0a3d-132">ExumRouting 路由呼叫到 Exchange Server 整合通訊（UM）。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-132">ExumRouting routes calls to Exchange Server Unified Messaging (UM).</span></span> <span data-ttu-id="e0a3d-133">ExumRouting 會決定適當的 Exchange UM 伺服器，以便在有新的語音信箱訊息來存放時傳送通話。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-133">ExumRouting determines the appropriate Exchange UM server to route the call to when there is a new voice mail message to deposit.</span></span> <span data-ttu-id="e0a3d-134">ExumRouting 也會處理一些 Exchange UM 整合的其他方面，包括傳送到自動語音應答及訂閱者存取。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-134">ExumRouting also handles some other Exchange UM integration aspects, including routing to Auto Attendant and Subscriber Access.</span></span>

  - <span data-ttu-id="e0a3d-135">OutboundRouting 會根據撥打的號碼和使用者的撥號授權，決定將呼叫路由到電話號碼的閘道。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-135">OutboundRouting determines the gateway that routes a call to a phone number according to the dialed number and the user’s dialing authorization.</span></span> <span data-ttu-id="e0a3d-136">如果閘道無法處理通話，OutboundRouting 也會處理通話的重新路由。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-136">OutboundRouting also handles rerouting of calls if a gateway cannot process a call.</span></span>

  - <span data-ttu-id="e0a3d-137">QoEAgent 會透過 SIP 服務要求從端點接收經驗品質（QoE）資料，並將資料傳送到監視伺服器上的目的地佇列，或是使用 HTTP POST 傳送資料給協力廠商消費者。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-137">QoEAgent receives Quality of Experience (QoE) data reports from endpoints through SIP SERVICE requests, and sends the data to the destination queue on the Monitoring Server or to third-party consumers using HTTP POST.</span></span> <span data-ttu-id="e0a3d-138">如需詳細資訊，請參閱[在 Lync Server 2013 中部署監視](lync-server-2013-deploying-monitoring.md)。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-138">For details, see [Deploying monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).</span></span>

  - <span data-ttu-id="e0a3d-139">OutgoingFederation 會強制執行租使用者層級同盟驗證，以取得目標外部部署的訊息。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-139">OutgoingFederation enforces tenant-level federation validation for messages going to a targeted external deployment.</span></span>

  - <span data-ttu-id="e0a3d-140">AcpRouting [代理傳送給音訊會議提供者的邀請要求] 到音訊會議提供者閘道。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-140">AcpRouting proxies INVITE requests destined for the audio conferencing provider to the audio conferencing provider gateway.</span></span>

<span data-ttu-id="e0a3d-141">在邊緣伺服器上執行的腳本包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="e0a3d-141">Scripts that run on Edge Servers include the following:</span></span>

  - <span data-ttu-id="e0a3d-142">IIMFilter</span><span class="sxs-lookup"><span data-stu-id="e0a3d-142">IIMFilter</span></span>

  - <span data-ttu-id="e0a3d-143">如果要求是目前伺服器的發件者，則 OptionsHandler 會回應 **[200 確定]** 的傳入選項要求。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-143">OptionsHandler responds to incoming OPTIONS requests with **200 OK** if the request is destined for the current server.</span></span> <span data-ttu-id="e0a3d-144">這用於拓撲驗證。</span><span class="sxs-lookup"><span data-stu-id="e0a3d-144">This is used for topology validation.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e0a3d-145">請參閱</span><span class="sxs-lookup"><span data-stu-id="e0a3d-145">See Also</span></span>


[<span data-ttu-id="e0a3d-146">在 Lync Server 2013 中啟用或停用 Microsoft SIP 處理語言（MSPL）伺服器應用程式</span><span class="sxs-lookup"><span data-stu-id="e0a3d-146">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[<span data-ttu-id="e0a3d-147">在 Lync Server 2013 中將 Microsoft SIP 處理語言（MSPL）應用程式標示為重要或不重要</span><span class="sxs-lookup"><span data-stu-id="e0a3d-147">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

