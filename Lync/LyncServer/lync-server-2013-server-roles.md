---
title: Lync Server 2013 伺服器角色
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35b8c5b052defcdc1d60ef9900c283f9f50b3809
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-roles-in-lync-server-2013"></a><span data-ttu-id="c752c-102">Lync Server 2013 中的伺服器角色</span><span class="sxs-lookup"><span data-stu-id="c752c-102">Server roles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c752c-103">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="c752c-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="c752c-104">運行 Lync Server 的每個伺服器都執行一或多個*伺服器角色*。</span><span class="sxs-lookup"><span data-stu-id="c752c-104">Each server running Lync Server runs one or more *server roles*.</span></span> <span data-ttu-id="c752c-105">伺服器角色是該伺服器所提供的一組 Lync 伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="c752c-105">A server role is a defined set of Lync Server functionalities provided by that server.</span></span> <span data-ttu-id="c752c-106">您不需要在您的網路中部署所有可用的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="c752c-106">You do not need to deploy all available server roles in your network.</span></span> <span data-ttu-id="c752c-107">只安裝包含所需功能的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="c752c-107">Install only the server roles that contain the functionality that you want.</span></span>

<span data-ttu-id="c752c-108">即使您不熟悉 Lync Server 中的伺服器角色，規劃工具也可以根據您所需的功能，為您提供所需部署之伺服器的最佳解決方案。</span><span class="sxs-lookup"><span data-stu-id="c752c-108">Even if you are not familiar with server roles in Lync Server, the Planning Tool can guide you to the best solution for the servers that you need to deploy, based on the features that you want.</span></span> <span data-ttu-id="c752c-109">本節簡要說明伺服器角色及其提供的一般功能：</span><span class="sxs-lookup"><span data-stu-id="c752c-109">This section provides a brief overview of the server roles and the general features that they provide:</span></span>

  - <span data-ttu-id="c752c-110">Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="c752c-110">Standard Edition Server</span></span>

  - <span data-ttu-id="c752c-111">前端伺服器和後端伺服器</span><span class="sxs-lookup"><span data-stu-id="c752c-111">Front End Server and Back End Server</span></span>

  - <span data-ttu-id="c752c-112">Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="c752c-112">Edge Server</span></span>

  - <span data-ttu-id="c752c-113">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="c752c-113">Mediation Server</span></span>

  - <span data-ttu-id="c752c-114">Director</span><span class="sxs-lookup"><span data-stu-id="c752c-114">Director</span></span>

  - <span data-ttu-id="c752c-115">持續聊天前端伺服器</span><span class="sxs-lookup"><span data-stu-id="c752c-115">Persistent Chat Front End Server</span></span>

  - <span data-ttu-id="c752c-116">持續聊天存放區（持續聊天后端伺服器）</span><span class="sxs-lookup"><span data-stu-id="c752c-116">Persistent Chat Store (Persistent Chat Back End Server)</span></span>

  - <span data-ttu-id="c752c-117">持續交談合規性存放區（持續式聊天規範後端伺服器）</span><span class="sxs-lookup"><span data-stu-id="c752c-117">Persistent Chat Compliance Store (Persistent Chat Compliance Back End Server)</span></span>

<span data-ttu-id="c752c-118">針對大部分的伺服器角色，如需可伸縮性和高可用性，您可以將多個伺服器的*pool*部署在執行相同的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="c752c-118">For most server roles, for scalability and high availability you can deploy *pools* of multiple servers all running the same server role.</span></span> <span data-ttu-id="c752c-119">池中的每個伺服器都必須執行相同的伺服器角色或角色。</span><span class="sxs-lookup"><span data-stu-id="c752c-119">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="c752c-120">針對 Lync Server 中的大部分類型的 pool，您必須部署負載平衡器，以便在池中的各個伺服器之間散佈流量。</span><span class="sxs-lookup"><span data-stu-id="c752c-120">For most types of pools in Lync Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="c752c-121">Lync Server 同時支援網域名稱系統（DNS）負載平衡與硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="c752c-121">Lync Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>

<div>

## <a name="standard-edition-server"></a><span data-ttu-id="c752c-122">Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="c752c-122">Standard Edition Server</span></span>

<span data-ttu-id="c752c-123">標準版伺服器專為小型組織設計，且適用于大型組織的試驗專案。</span><span class="sxs-lookup"><span data-stu-id="c752c-123">The Standard Edition server is designed for small organizations, and for pilot projects of large organizations.</span></span> <span data-ttu-id="c752c-124">它能讓 Lync Server 的許多功能（包括必要的資料庫）都能在單一伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="c752c-124">It enables many of the features of Lync Server, including the necessary databases, to run on a single server.</span></span> <span data-ttu-id="c752c-125">這可讓您以較低的成本進行 Lync Server 功能，但不會提供真正的高可用性方案。</span><span class="sxs-lookup"><span data-stu-id="c752c-125">This enables you to have Lync Server functionality for a lower cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="c752c-126">標準版伺服器可讓您使用立即訊息（IM）、目前狀態、會議和企業語音，所有都是在一部伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="c752c-126">Standard Edition server enables you to use instant messaging (IM), presence, conferencing, and Enterprise Voice, all running on one server.</span></span>

<span data-ttu-id="c752c-127">針對高可用性方案，請使用 Lync Server 企業版。</span><span class="sxs-lookup"><span data-stu-id="c752c-127">For a high-availability solution, use Lync Server Enterprise Edition.</span></span>

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="c752c-128">前端伺服器和後端伺服器</span><span class="sxs-lookup"><span data-stu-id="c752c-128">Front End Server and Back End Server</span></span>

<span data-ttu-id="c752c-129">在 Lync Server 企業版中，前端伺服器是核心伺服器角色，並執行許多基本的 Lync 伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="c752c-129">In Lync Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Lync Server functions.</span></span> <span data-ttu-id="c752c-130">前端伺服器（以及後端伺服器）是在任何 Lync Server 企業版部署中唯一需要的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="c752c-130">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Lync Server Enterprise Edition deployment.</span></span>

<span data-ttu-id="c752c-131">[*前端] 池*是一組前端伺服器（配置相同），共同作業為使用者群組提供服務。</span><span class="sxs-lookup"><span data-stu-id="c752c-131">A *Front End pool* is a set of Front End Servers, configured identically, that work together to provide services for a common group of users.</span></span> <span data-ttu-id="c752c-132">多台執行相同角色的伺服器池提供可伸縮性和容錯移轉功能。</span><span class="sxs-lookup"><span data-stu-id="c752c-132">A pool of multiple servers running the same role provides scalability and failover capability.</span></span>

<span data-ttu-id="c752c-133">前端伺服器包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="c752c-133">The Front End Server includes the following:</span></span>

  - <span data-ttu-id="c752c-134">使用者驗證與註冊</span><span class="sxs-lookup"><span data-stu-id="c752c-134">User authentication and registration</span></span>

  - <span data-ttu-id="c752c-135">目前狀態資訊與連絡人卡片交換</span><span class="sxs-lookup"><span data-stu-id="c752c-135">Presence information and contact card exchange</span></span>

  - <span data-ttu-id="c752c-136">通訊錄服務與通訊群組清單展開</span><span class="sxs-lookup"><span data-stu-id="c752c-136">Address book services and distribution list expansion</span></span>

  - <span data-ttu-id="c752c-137">IM 功能，包括多方 IM 會議</span><span class="sxs-lookup"><span data-stu-id="c752c-137">IM functionality, including multiparty IM conferences</span></span>

  - <span data-ttu-id="c752c-138">網路會議、PSTN 電話撥入式會議及 A/V 會議（如果已部署）</span><span class="sxs-lookup"><span data-stu-id="c752c-138">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed)</span></span>

  - <span data-ttu-id="c752c-139">針對 Lync Server 隨附的兩個應用程式（例如，會議助理與回應群組應用程式）和協力廠商應用程式的應用程式託管</span><span class="sxs-lookup"><span data-stu-id="c752c-139">Application hosting, for both applications included with Lync Server (for example, Conferencing Attendant and Response Group application), and third-party applications</span></span>

  - <span data-ttu-id="c752c-140">您也可以選擇監視，以收集通話詳細資料記錄（CDRs）的使用方式資訊，並呼叫錯誤記錄（Cer）。</span><span class="sxs-lookup"><span data-stu-id="c752c-140">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="c752c-141">此資訊提供有關透過企業語音通話和 A/V 會議來遍歷您網路之媒體質量（音訊與影片）的統計資料。</span><span class="sxs-lookup"><span data-stu-id="c752c-141">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>

  - <span data-ttu-id="c752c-142">網頁元件（例如網頁排程程式及加入啟動器）支援的 web 工作。</span><span class="sxs-lookup"><span data-stu-id="c752c-142">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>

  - <span data-ttu-id="c752c-143">您可以選擇性地封存 IM 通訊與會議內容，以符合合規性的原因。</span><span class="sxs-lookup"><span data-stu-id="c752c-143">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons.</span></span> <span data-ttu-id="c752c-144">如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的存檔規劃](lync-server-2013-planning-for-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="c752c-144">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>
    
    <span data-ttu-id="c752c-145">在 Lync Server 2010 和早期版本中，監視及封存是獨立的伺服器角色，而不是在前端伺服器上 collocated。</span><span class="sxs-lookup"><span data-stu-id="c752c-145">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>

  - <span data-ttu-id="c752c-146">您也可以選擇是否已啟用持續聊天、聊天室管理的持續聊天 Web 服務和檔案上傳/下載的持續聊天 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="c752c-146">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>

<span data-ttu-id="c752c-147">前端池也是使用者和會議資料的主要存儲區。</span><span class="sxs-lookup"><span data-stu-id="c752c-147">Front End Pools are also the primary store for user and conference data.</span></span> <span data-ttu-id="c752c-148">每個使用者的相關資訊會在池中的三個前端伺服器之間複製，並在後端伺服器上備份。</span><span class="sxs-lookup"><span data-stu-id="c752c-148">Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>

<span data-ttu-id="c752c-149">此外，部署中的一個前端池也會執行*中央管理伺服器*，該伺服器會將基本配置資料管理並部署到執行 Lync Server 的所有伺服器。</span><span class="sxs-lookup"><span data-stu-id="c752c-149">Additionally, one Front End pool in the deployment also runs the *Central Management Server*, which manages and deploys basic configuration data to all servers running Lync Server.</span></span> <span data-ttu-id="c752c-150">中央管理伺服器也提供 Lync Server 管理命令介面和檔案傳輸功能。</span><span class="sxs-lookup"><span data-stu-id="c752c-150">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>

<span data-ttu-id="c752c-151">後端伺服器是執行 Microsoft SQL Server 的資料庫伺服器，可為前端池提供資料庫服務。</span><span class="sxs-lookup"><span data-stu-id="c752c-151">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="c752c-152">後端伺服器可做為池使用者與會議資料的備份儲存，而且是其他資料庫（例如回應群組資料庫）的主要存儲區。</span><span class="sxs-lookup"><span data-stu-id="c752c-152">The Back End Servers serve as backup stores for the pool’s user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="c752c-153">您可以使用單一後端伺服器，但建議使用 SQL Server 鏡像的解決方案，以進行容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="c752c-153">You can have a single Back End Server, but a solution that uses SQL Server mirroring is recommended for failover.</span></span> <span data-ttu-id="c752c-154">後端伺服器不會執行任何 Lync Server 軟體。</span><span class="sxs-lookup"><span data-stu-id="c752c-154">Back End Servers do not run any Lync Server software.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c752c-155">我們不建議將 Lync Server 資料庫與其他資料庫 collocating。</span><span class="sxs-lookup"><span data-stu-id="c752c-155">We do not recommend collocating Lync Server databases with other databases.</span></span> <span data-ttu-id="c752c-156">如果您這麼做，可用性和效能可能會受到影響。</span><span class="sxs-lookup"><span data-stu-id="c752c-156">If you do so, availability and performance may be affected.</span></span>



</div>

<span data-ttu-id="c752c-157">儲存在後端伺服器資料庫中的資訊包含目前狀態資訊、使用者的連絡人清單、會議資料，包括所有目前會議狀態的永久性資料，以及會議排程資料。</span><span class="sxs-lookup"><span data-stu-id="c752c-157">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="c752c-158">Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="c752c-158">Edge Server</span></span>

<span data-ttu-id="c752c-159">Edge 伺服器可讓您的使用者與組織防火牆以外的使用者進行通訊及共同作業。</span><span class="sxs-lookup"><span data-stu-id="c752c-159">Edge Server enables your users to communicate and collaborate with users outside the organization’s firewalls.</span></span> <span data-ttu-id="c752c-160">這些外部使用者可以包含組織自己的使用者，這些使用者目前正在異地作業、同盟夥伴組織的使用者，以及受邀加入 Lync Server 部署之會議的外部使用者。</span><span class="sxs-lookup"><span data-stu-id="c752c-160">These external users can include the organization’s own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Lync Server deployment.</span></span> <span data-ttu-id="c752c-161">Edge 伺服器也可連線至公用 IM 聯機服務，包括 Windows Live、AOL、Yahoo\!和 Google 交談。</span><span class="sxs-lookup"><span data-stu-id="c752c-161">Edge Server also enables connectivity to public IM connectivity services, including Windows Live, AOL, Yahoo\!, and Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="c752c-162">從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。</span><span class="sxs-lookup"><span data-stu-id="c752c-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="c752c-163">擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="c752c-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="c752c-164">信使，直到服務關閉日期為止。</span><span class="sxs-lookup"><span data-stu-id="c752c-164">Messenger until the service shut down date.</span></span> <span data-ttu-id="c752c-165">AOL 和 Yahoo！的存留期結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="c752c-165">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="c752c-166">已公佈。</span><span class="sxs-lookup"><span data-stu-id="c752c-166">has been announced.</span></span> <span data-ttu-id="c752c-167">如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</span><span class="sxs-lookup"><span data-stu-id="c752c-167">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="c752c-168">PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="c752c-168">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="c752c-169">名單.</span><span class="sxs-lookup"><span data-stu-id="c752c-169">Messenger.</span></span> <span data-ttu-id="c752c-170">Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</span><span class="sxs-lookup"><span data-stu-id="c752c-170">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="c752c-171">Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。</span><span class="sxs-lookup"><span data-stu-id="c752c-171">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="c752c-172">與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="c752c-172">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="c752c-173">您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="c752c-173">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="c752c-174">部署 Edge 伺服器也會啟用行動裝置服務，支援行動裝置上的 Lync 功能。</span><span class="sxs-lookup"><span data-stu-id="c752c-174">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="c752c-175">使用者可以使用支援的 Apple iOS、Android、Windows Phone 或 Nokia 行動裝置來執行諸如傳送和接收立即訊息、查看連絡人及查看目前狀態等活動。</span><span class="sxs-lookup"><span data-stu-id="c752c-175">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="c752c-176">此外，行動裝置支援一些企業語音功能，例如按一下以加入會議、透過工作撥打電話、單一號碼達到、語音信箱及未接來電。</span><span class="sxs-lookup"><span data-stu-id="c752c-176">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="c752c-177">行動裝置功能也支援不支援在背景中執行之應用程式之行動裝置的*推播通知*。</span><span class="sxs-lookup"><span data-stu-id="c752c-177">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="c752c-178">推播通知是傳送給行動裝置的通知，在行動應用程式處於非使用中時，發生該事件。</span><span class="sxs-lookup"><span data-stu-id="c752c-178">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>

<span data-ttu-id="c752c-179">Edge 伺服器也包含完全整合的可擴展訊息和目前狀態通訊協定（XMPP） proxy，並包含在前端伺服器上的 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="c752c-179">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="c752c-180">您可以設定這些 XMPP 元件，讓您的 Lync Server 2013 使用者從 XMPP 的合作夥伴（例如 Google 交談）新增連絡人，以進行立即訊息和目前狀態。</span><span class="sxs-lookup"><span data-stu-id="c752c-180">You can configure these XMPP components to enable your Lync Server 2013 users to add contacts from XMPP-based partners (such as Google Talk) for instant messaging and presence.</span></span>

<span data-ttu-id="c752c-181">如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="c752c-181">For details, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="c752c-182">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="c752c-182">Mediation Server</span></span>

<span data-ttu-id="c752c-183">中繼伺服器是用來實現企業語音和電話撥入式會議的必要元件。</span><span class="sxs-lookup"><span data-stu-id="c752c-183">Mediation Server is a necessary component for implementing Enterprise Voice and dial-in conferencing.</span></span> <span data-ttu-id="c752c-184">轉送伺服器會轉譯信號，在某些設定中，您內部 Lync 伺服器基礎結構與公用交換式電話網絡（PSTN）閘道、IP PBX 或會話初始通訊協定（SIP）幹線之間的媒體。</span><span class="sxs-lookup"><span data-stu-id="c752c-184">Mediation Server translates signaling, and, in some configurations, media between your internal Lync Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="c752c-185">您可以在與前臺伺服器相同的伺服器上執行轉送服務伺服器 collocated，或將它分割成獨立的中繼伺服器池。</span><span class="sxs-lookup"><span data-stu-id="c752c-185">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="c752c-186">如需詳細資訊，請參閱規劃檔中的[Lync server 2013 中的 [轉送伺服器元件](lync-server-2013-mediation-server-component.md)]。</span><span class="sxs-lookup"><span data-stu-id="c752c-186">For details, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="c752c-187">Director</span><span class="sxs-lookup"><span data-stu-id="c752c-187">Director</span></span>

<span data-ttu-id="c752c-188">控制器可驗證 Lync Server 使用者要求，但不會提供使用者帳戶或提供目前狀態或會議服務。</span><span class="sxs-lookup"><span data-stu-id="c752c-188">Directors can authenticate Lync Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="c752c-189">在能讓外部使用者存取的部署中加強安全性時，控制器是最實用的。</span><span class="sxs-lookup"><span data-stu-id="c752c-189">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="c752c-190">Director 可以在將要求傳送到內部伺服器前進行驗證。</span><span class="sxs-lookup"><span data-stu-id="c752c-190">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="c752c-191">在拒絕服務攻擊的情況下，攻擊會以控制器為結束，而且不會到達前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="c752c-191">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span> <span data-ttu-id="c752c-192">如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的主管案例](lync-server-2013-scenarios-for-the-director.md)。</span><span class="sxs-lookup"><span data-stu-id="c752c-192">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-roles"></a><span data-ttu-id="c752c-193">持續聊天伺服器角色</span><span class="sxs-lookup"><span data-stu-id="c752c-193">Persistent Chat Server Roles</span></span>

<span data-ttu-id="c752c-194">持續聊天可讓使用者參與多方、在一段時間內保持的、以主題為基礎的交談。</span><span class="sxs-lookup"><span data-stu-id="c752c-194">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="c752c-195">持續聊天前端伺服器會執行持續聊天服務。</span><span class="sxs-lookup"><span data-stu-id="c752c-195">The Persistent Chat Front End Server runs the persistent chat service.</span></span> <span data-ttu-id="c752c-196">持續式聊天后端伺服器會儲存聊天記錄資料，以及類別和聊天室的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c752c-196">The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms.</span></span> <span data-ttu-id="c752c-197">選用的持續性聊天規範後端伺服器可以儲存聊天內容和相容性事件，以符合合規性的目的。</span><span class="sxs-lookup"><span data-stu-id="c752c-197">The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>

<span data-ttu-id="c752c-198">運行 Lync Server 標準版的伺服器也可以在同一個伺服器上執行持續聊天 collocated。</span><span class="sxs-lookup"><span data-stu-id="c752c-198">Servers running Lync Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="c752c-199">您無法 collocate 與企業版前端伺服器的永久聊天前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="c752c-199">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>

<span data-ttu-id="c752c-200">如需詳細資訊，請參閱[在 Lync server 2013 中規劃持久聊天伺服器](lync-server-2013-planning-for-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="c752c-200">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c752c-201">請參閱</span><span class="sxs-lookup"><span data-stu-id="c752c-201">See Also</span></span>


[<span data-ttu-id="c752c-202">Lync Server 2013 中的中繼伺服器元件</span><span class="sxs-lookup"><span data-stu-id="c752c-202">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  


[<span data-ttu-id="c752c-203">在 Lync Server 2013 中規劃封存</span><span class="sxs-lookup"><span data-stu-id="c752c-203">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
[<span data-ttu-id="c752c-204">在 Lync Server 2013 中規劃外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="c752c-204">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="c752c-205">Lync Server 2013 中的 Director 案例</span><span class="sxs-lookup"><span data-stu-id="c752c-205">Scenarios for the Director in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-the-director.md)  
[<span data-ttu-id="c752c-206">在 Lync Server 2013 中規劃常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="c752c-206">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

