---
title: Lync Server 2013 伺服器角色
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398536(v=OCS.15)
ms:contentKeyID: 48184456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a413bde093c375a887f1ea39c435401b3ce1c4a6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510260"
---
# <a name="server-roles-in-lync-server-2013"></a><span data-ttu-id="60f39-102">Lync Server 2013 中的伺服器角色</span><span class="sxs-lookup"><span data-stu-id="60f39-102">Server roles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60f39-103">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="60f39-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="60f39-104">每一部執行 Lync Server 的伺服器都會執行一或多個 *伺服器角色*。</span><span class="sxs-lookup"><span data-stu-id="60f39-104">Each server running Lync Server runs one or more *server roles*.</span></span> <span data-ttu-id="60f39-105">伺服器角色是該伺服器所提供之 Lync Server 功能的定義集合。</span><span class="sxs-lookup"><span data-stu-id="60f39-105">A server role is a defined set of Lync Server functionalities provided by that server.</span></span> <span data-ttu-id="60f39-106">您不需要在您的網路中部署所有可用的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="60f39-106">You do not need to deploy all available server roles in your network.</span></span> <span data-ttu-id="60f39-107">只安裝包含您想要之功能的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="60f39-107">Install only the server roles that contain the functionality that you want.</span></span>

<span data-ttu-id="60f39-108">即使您不熟悉 Lync Server 中的伺服器角色，規劃工具也可以根據您所需的功能，針對您需要部署的伺服器，引導您使用最佳解決方案。</span><span class="sxs-lookup"><span data-stu-id="60f39-108">Even if you are not familiar with server roles in Lync Server, the Planning Tool can guide you to the best solution for the servers that you need to deploy, based on the features that you want.</span></span> <span data-ttu-id="60f39-109">本節提供伺服器角色及其提供的一般功能的簡短概述：</span><span class="sxs-lookup"><span data-stu-id="60f39-109">This section provides a brief overview of the server roles and the general features that they provide:</span></span>

  - <span data-ttu-id="60f39-110">Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="60f39-110">Standard Edition Server</span></span>

  - <span data-ttu-id="60f39-111">前端伺服器及後端伺服器</span><span class="sxs-lookup"><span data-stu-id="60f39-111">Front End Server and Back End Server</span></span>

  - <span data-ttu-id="60f39-112">Edge Server</span><span class="sxs-lookup"><span data-stu-id="60f39-112">Edge Server</span></span>

  - <span data-ttu-id="60f39-113">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="60f39-113">Mediation Server</span></span>

  - <span data-ttu-id="60f39-114">Director</span><span class="sxs-lookup"><span data-stu-id="60f39-114">Director</span></span>

  - <span data-ttu-id="60f39-115">Persistent Chat 前端伺服器</span><span class="sxs-lookup"><span data-stu-id="60f39-115">Persistent Chat Front End Server</span></span>

  - <span data-ttu-id="60f39-116">Persistent chat Store (Persistent Chat 後端伺服器) </span><span class="sxs-lookup"><span data-stu-id="60f39-116">Persistent Chat Store (Persistent Chat Back End Server)</span></span>

  - <span data-ttu-id="60f39-117">Persistent Chat 合規性存放區 (持續性聊天規範後端伺服器) </span><span class="sxs-lookup"><span data-stu-id="60f39-117">Persistent Chat Compliance Store (Persistent Chat Compliance Back End Server)</span></span>

<span data-ttu-id="60f39-118">針對大部分的伺服器角色，針對可擴充性和高可用性，您 *可以部署多* 部伺服器的集區，所有執行相同的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="60f39-118">For most server roles, for scalability and high availability you can deploy *pools* of multiple servers all running the same server role.</span></span> <span data-ttu-id="60f39-119">集區中的每部伺服器都必須執行一或多個相同的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="60f39-119">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="60f39-120">在 Lync Server 中大多數的集區類型，您必須部署負載平衡器，以在集區中的不同伺服器間散佈流量。</span><span class="sxs-lookup"><span data-stu-id="60f39-120">For most types of pools in Lync Server, you must deploy a load balancer to spread traffic between the various servers in the pool.</span></span> <span data-ttu-id="60f39-121">Lync Server 同時支援網域名稱系統 (DNS) 負載平衡與硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="60f39-121">Lync Server supports both Domain Name System (DNS) load balancing and hardware load balancers.</span></span>

<div>

## <a name="standard-edition-server"></a><span data-ttu-id="60f39-122">Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="60f39-122">Standard Edition Server</span></span>

<span data-ttu-id="60f39-123">Standard Edition server 是針對小型組織設計，也適用于大型組織的試驗專案。</span><span class="sxs-lookup"><span data-stu-id="60f39-123">The Standard Edition server is designed for small organizations, and for pilot projects of large organizations.</span></span> <span data-ttu-id="60f39-124">它可讓 Lync Server 的許多功能（包括必要的資料庫）在單一伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="60f39-124">It enables many of the features of Lync Server, including the necessary databases, to run on a single server.</span></span> <span data-ttu-id="60f39-125">這可讓您以較低的成本進行 Lync Server 功能，但不會提供真正的高可用性解決方案。</span><span class="sxs-lookup"><span data-stu-id="60f39-125">This enables you to have Lync Server functionality for a lower cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="60f39-126">Standard Edition server 可讓您使用立即訊息 (IM) 、目前狀態、會議及 Enterprise Voice，都是在一部伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="60f39-126">Standard Edition server enables you to use instant messaging (IM), presence, conferencing, and Enterprise Voice, all running on one server.</span></span>

<span data-ttu-id="60f39-127">如需高可用性解決方案，請使用 Lync Server Enterprise Edition。</span><span class="sxs-lookup"><span data-stu-id="60f39-127">For a high-availability solution, use Lync Server Enterprise Edition.</span></span>

</div>

<div>

## <a name="front-end-server-and-back-end-server"></a><span data-ttu-id="60f39-128">前端伺服器及後端伺服器</span><span class="sxs-lookup"><span data-stu-id="60f39-128">Front End Server and Back End Server</span></span>

<span data-ttu-id="60f39-129">在 Lync Server Enterprise Edition 中，前端伺服器是核心伺服器角色，而且會執行許多基本的 Lync Server 功能。</span><span class="sxs-lookup"><span data-stu-id="60f39-129">In Lync Server Enterprise Edition, the Front End Server is the core server role, and runs many basic Lync Server functions.</span></span> <span data-ttu-id="60f39-130">在任何 Lync Server Enterprise Edition 部署中，前端伺服器及後端伺服器都是唯一需要的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="60f39-130">The Front End Server, along with the Back End Servers, are the only server roles required to be in any Lync Server Enterprise Edition deployment.</span></span>

<span data-ttu-id="60f39-131">*前端集*區是一組前端伺服器（已正確設定），可共同運作，以提供通用使用者群組的服務。</span><span class="sxs-lookup"><span data-stu-id="60f39-131">A *Front End pool* is a set of Front End Servers, configured identically, that work together to provide services for a common group of users.</span></span> <span data-ttu-id="60f39-132">執行相同角色的多部伺服器集區提供可擴充性和容錯移轉功能。</span><span class="sxs-lookup"><span data-stu-id="60f39-132">A pool of multiple servers running the same role provides scalability and failover capability.</span></span>

<span data-ttu-id="60f39-133">前端伺服器包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="60f39-133">The Front End Server includes the following:</span></span>

  - <span data-ttu-id="60f39-134">使用者驗證和註冊</span><span class="sxs-lookup"><span data-stu-id="60f39-134">User authentication and registration</span></span>

  - <span data-ttu-id="60f39-135">目前狀態資訊和連絡人卡片交換</span><span class="sxs-lookup"><span data-stu-id="60f39-135">Presence information and contact card exchange</span></span>

  - <span data-ttu-id="60f39-136">通訊錄服務和通訊群組清單擴充</span><span class="sxs-lookup"><span data-stu-id="60f39-136">Address book services and distribution list expansion</span></span>

  - <span data-ttu-id="60f39-137">IM 功能（包括多方 IM 會議）</span><span class="sxs-lookup"><span data-stu-id="60f39-137">IM functionality, including multiparty IM conferences</span></span>

  - <span data-ttu-id="60f39-138">網路會議、PSTN 電話撥入式會議和 A/V 會議 (（若已部署）) </span><span class="sxs-lookup"><span data-stu-id="60f39-138">Web conferencing, PSTN Dial-in conferencing and A/V conferencing (if deployed)</span></span>

  - <span data-ttu-id="60f39-139">應用程式裝載，針對 Lync Server 所包含的兩個應用程式 (例如會議助理和回應群組應用程式) ，以及協力廠商應用程式</span><span class="sxs-lookup"><span data-stu-id="60f39-139">Application hosting, for both applications included with Lync Server (for example, Conferencing Attendant and Response Group application), and third-party applications</span></span>

  - <span data-ttu-id="60f39-140">（選用）監控，以 [通話詳細資料記錄] 的形式收集使用資訊 (Cdr) 並呼叫錯誤記錄 (Cer) 。</span><span class="sxs-lookup"><span data-stu-id="60f39-140">Optionally, Monitoring, to collect usage information in the form of call detail records (CDRs) and call error records (CERs).</span></span> <span data-ttu-id="60f39-141">此資訊提供有關媒體質量 (音訊和影片) 針對企業語音通話和 A/V 會議進行網路的統計資料。</span><span class="sxs-lookup"><span data-stu-id="60f39-141">This information provides metrics about the quality of the media (audio and video) traversing your network for both Enterprise Voice calls and A/V conferences.</span></span>

  - <span data-ttu-id="60f39-142">網頁元件至支援的 web 工作，例如 web 排程器及加入啟動器。</span><span class="sxs-lookup"><span data-stu-id="60f39-142">Web components to supported web-based tasks such as web scheduler and join launcher.</span></span>

  - <span data-ttu-id="60f39-143">（選用）封存 IM 通訊和會議內容，以符合合規性的原因。</span><span class="sxs-lookup"><span data-stu-id="60f39-143">Optionally, Archiving, to archive IM communications and meeting content for compliance reasons.</span></span> <span data-ttu-id="60f39-144">如需詳細資訊，請參閱規劃檔中的 [規劃 Lync Server 2013 中的](lync-server-2013-planning-for-archiving.md) 封存。</span><span class="sxs-lookup"><span data-stu-id="60f39-144">For details, see [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in the Planning documentation.</span></span>
    
    <span data-ttu-id="60f39-145">在 Lync Server 2010 和舊版中，監控和封存是不同的伺服器角色，不會組合在前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="60f39-145">In Lync Server 2010 and prior versions, Monitoring and Archiving were separate server roles, not collocated on Front End Server.</span></span>

  - <span data-ttu-id="60f39-146">（選用）啟用持續性聊天時，會持續聊天網頁服務用於聊天室管理，並可進行檔案上傳/下載的持續性聊天 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="60f39-146">Optionally, if Persistent chat is enabled, Persistent Chat Web Services for Chat Room Management and Persistent Chat Web Services for File Upload/Download.</span></span>

<span data-ttu-id="60f39-147">前端集區也是使用者和會議資料的主要儲存區。</span><span class="sxs-lookup"><span data-stu-id="60f39-147">Front End Pools are also the primary store for user and conference data.</span></span> <span data-ttu-id="60f39-148">每個使用者的資訊都會在集區中的三部前端伺服器之間進行複製，並在後端伺服器上備份。</span><span class="sxs-lookup"><span data-stu-id="60f39-148">Information about each user is replicated among three Front End Servers in the pool, and backed up on the Back End Servers.</span></span>

<span data-ttu-id="60f39-149">此外，部署中的一個前端集區也會執行 *中央管理伺服器*，此伺服器會管理及部署所有執行 Lync Server 的伺服器的基本設定資料。</span><span class="sxs-lookup"><span data-stu-id="60f39-149">Additionally, one Front End pool in the deployment also runs the *Central Management Server*, which manages and deploys basic configuration data to all servers running Lync Server.</span></span> <span data-ttu-id="60f39-150">中央管理伺服器也提供 Lync Server 管理命令介面和檔案傳輸功能。</span><span class="sxs-lookup"><span data-stu-id="60f39-150">The Central Management Server also provides Lync Server Management Shell and file transfer capabilities.</span></span>

<span data-ttu-id="60f39-151">後端伺服器是執行 Microsoft SQL Server 的資料庫伺服器，提供前端集區的資料庫服務。</span><span class="sxs-lookup"><span data-stu-id="60f39-151">The Back End Servers are database servers running Microsoft SQL Server that provide the database services for the Front End pool.</span></span> <span data-ttu-id="60f39-152">後端伺服器充當集區使用者和會議資料的備份存放區，也是其他資料庫（如回應群組資料庫）的主要儲存區。</span><span class="sxs-lookup"><span data-stu-id="60f39-152">The Back End Servers serve as backup stores for the pool’s user and conference data, and are the primary stores for other databases such as the Response Group database.</span></span> <span data-ttu-id="60f39-153">您可以擁有單一後端伺服器，但建議使用 SQL Server 鏡像的解決方案進行容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="60f39-153">You can have a single Back End Server, but a solution that uses SQL Server mirroring is recommended for failover.</span></span> <span data-ttu-id="60f39-154">後端伺服器不會執行任何 Lync Server 軟體。</span><span class="sxs-lookup"><span data-stu-id="60f39-154">Back End Servers do not run any Lync Server software.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="60f39-155">我們不建議使用其他資料庫組合 Lync Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="60f39-155">We do not recommend collocating Lync Server databases with other databases.</span></span> <span data-ttu-id="60f39-156">如果您這麼做，可用性和效能可能會受到影響。</span><span class="sxs-lookup"><span data-stu-id="60f39-156">If you do so, availability and performance may be affected.</span></span>



</div>

<span data-ttu-id="60f39-157">儲存在後端伺服器資料庫中的資訊包括目前狀態資訊、使用者的連絡人清單、會議資料（包括所有目前會議狀態的持續性資料）和會議排程資料。</span><span class="sxs-lookup"><span data-stu-id="60f39-157">Information stored in the Back End Server databases includes presence information, users' Contacts lists, conferencing data, including persistent data about the state of all current conferences, and conference scheduling data.</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="60f39-158">Edge Server</span><span class="sxs-lookup"><span data-stu-id="60f39-158">Edge Server</span></span>

<span data-ttu-id="60f39-159">Edge Server 可讓您的使用者與組織防火牆外的使用者進行通訊及共同作業。</span><span class="sxs-lookup"><span data-stu-id="60f39-159">Edge Server enables your users to communicate and collaborate with users outside the organization’s firewalls.</span></span> <span data-ttu-id="60f39-160">這些外部使用者可以包含組織的使用者，這些使用者目前在異地工作、同盟夥伴組織的使用者，以及已被邀請加入 Lync Server 部署之會議的外部使用者。</span><span class="sxs-lookup"><span data-stu-id="60f39-160">These external users can include the organization’s own users who are currently working offsite, users from federated partner organizations, and outside users who have been invited to join conferences hosted on your Lync Server deployment.</span></span> <span data-ttu-id="60f39-161">Edge Server 也可連線到公用 IM 聯機服務，包括 Windows Live、AOL、Yahoo \! 和 Google 交談。</span><span class="sxs-lookup"><span data-stu-id="60f39-161">Edge Server also enables connectivity to public IM connectivity services, including Windows Live, AOL, Yahoo\!, and Google Talk.</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="60f39-162">從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 ( 「PIC USL」 ) 不再提供購買新的或更新的協定。</span><span class="sxs-lookup"><span data-stu-id="60f39-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="60f39-163">具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="60f39-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="60f39-164">信使直到服務關閉日期。</span><span class="sxs-lookup"><span data-stu-id="60f39-164">Messenger until the service shut down date.</span></span> <span data-ttu-id="60f39-165">AOL 和 Yahoo！的循環結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="60f39-165">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="60f39-166">已宣告。</span><span class="sxs-lookup"><span data-stu-id="60f39-166">has been announced.</span></span> <span data-ttu-id="60f39-167">如需詳細資訊，請參閱 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</span><span class="sxs-lookup"><span data-stu-id="60f39-167">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="60f39-168">PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的個別使用者每個月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="60f39-168">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="60f39-169">信使。</span><span class="sxs-lookup"><span data-stu-id="60f39-169">Messenger.</span></span> <span data-ttu-id="60f39-170">Microsoft 提供此服務的能力已因 Yahoo！中的支援而產生，其所向下纏繞的底層合約。</span><span class="sxs-lookup"><span data-stu-id="60f39-170">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="60f39-171">Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。</span><span class="sxs-lookup"><span data-stu-id="60f39-171">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="60f39-172">與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="60f39-172">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="60f39-173">隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</span><span class="sxs-lookup"><span data-stu-id="60f39-173">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="60f39-174">部署 Edge Server 也會啟用行動裝置，其支援行動裝置上的 Lync 功能。</span><span class="sxs-lookup"><span data-stu-id="60f39-174">Deploying Edge Server also enables mobility services, which supports Lync functionality on mobile devices.</span></span> <span data-ttu-id="60f39-175">使用者可以使用支援的 Apple iOS、Android、Windows Phone 或 Nokia 行動裝置執行活動，例如傳送和接收立即訊息、查看連絡人及查看顯示狀態。</span><span class="sxs-lookup"><span data-stu-id="60f39-175">Users can use supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="60f39-176">此外，行動裝置還可支援某些 Enterprise Voice 功能，例如按一下加入會議、從公司撥號、單一號碼搜尋、語音信箱及未接來電。</span><span class="sxs-lookup"><span data-stu-id="60f39-176">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="60f39-177">行動功能也可以為不支援在背景執行應用程式的行動裝置，支援「推播通知」\*\*。</span><span class="sxs-lookup"><span data-stu-id="60f39-177">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="60f39-178">推播通知是針對在行動應用程式為非使用中狀態時所發生的事件，傳送給行動裝置的通知。</span><span class="sxs-lookup"><span data-stu-id="60f39-178">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span>

<span data-ttu-id="60f39-179">Edge Server 也包含完整整合的可延伸訊息和顯示狀態通訊協定 (XMPP) proxy，包含在前端伺服器上的 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="60f39-179">Edge Servers also include a fully-integrated Extensible Messaging and Presence Protocol (XMPP) proxy, with an XMPP gateway included on Front End Servers.</span></span> <span data-ttu-id="60f39-180">您可以設定這些 XMPP 元件，讓您的 Lync Server 2013 使用者新增來自以 XMPP 為基礎的合作夥伴的連絡人 (例如 Google 交談) 以進行立即訊息與顯示狀態。</span><span class="sxs-lookup"><span data-stu-id="60f39-180">You can configure these XMPP components to enable your Lync Server 2013 users to add contacts from XMPP-based partners (such as Google Talk) for instant messaging and presence.</span></span>

<span data-ttu-id="60f39-181">如需詳細資訊，請參閱規劃檔中的 [規劃 Lync Server 2013 中的外部使用者存取](lync-server-2013-planning-for-external-user-access.md) 。</span><span class="sxs-lookup"><span data-stu-id="60f39-181">For details, see [Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="60f39-182">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="60f39-182">Mediation Server</span></span>

<span data-ttu-id="60f39-183">轉送伺服器是用來執行企業語音和電話撥入式會議的必要元件。</span><span class="sxs-lookup"><span data-stu-id="60f39-183">Mediation Server is a necessary component for implementing Enterprise Voice and dial-in conferencing.</span></span> <span data-ttu-id="60f39-184">轉送伺服器轉譯信號，在某些設定中，您內部 Lync 伺服器基礎結構和公用交換電話網路之間的媒體會 (PSTN) 閘道、IP-PBX 或會話初始通訊協定 (SIP) 主幹。</span><span class="sxs-lookup"><span data-stu-id="60f39-184">Mediation Server translates signaling, and, in some configurations, media between your internal Lync Server infrastructure and a public switched telephone network (PSTN) gateway, IP-PBX, or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="60f39-185">您可以在前端伺服器所在的伺服器上執行轉送伺服器組合，或將其分割成獨立的轉送伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="60f39-185">You can run Mediation Server collocated on the same server as Front End Server, or separated into a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="60f39-186">如需詳細資訊，請參閱規劃檔中的 [Lync server 2013](lync-server-2013-mediation-server-component.md) 中的轉送伺服器元件。</span><span class="sxs-lookup"><span data-stu-id="60f39-186">For details, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="60f39-187">Director</span><span class="sxs-lookup"><span data-stu-id="60f39-187">Director</span></span>

<span data-ttu-id="60f39-188">Director 可驗證 Lync Server 使用者要求，但不會家用使用者帳戶，也不會提供目前狀態或會議服務。</span><span class="sxs-lookup"><span data-stu-id="60f39-188">Directors can authenticate Lync Server user requests, but they do not home user accounts or provide presence or conferencing services.</span></span> <span data-ttu-id="60f39-189">Director 在啟用外部使用者存取的部署中增強安全性是非常有用的。</span><span class="sxs-lookup"><span data-stu-id="60f39-189">Directors are most useful to enhance security in deployments that enable external user access.</span></span> <span data-ttu-id="60f39-190">Director 可以在將要求傳送至內部伺服器之前先驗證要求。</span><span class="sxs-lookup"><span data-stu-id="60f39-190">The Director can authenticate requests before sending them on to internal servers.</span></span> <span data-ttu-id="60f39-191">在拒絕服務攻擊的情況下，攻擊會以 Director 結尾，而且不會到達前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="60f39-191">In the case of a denial-of-service attack, the attack ends with the Director and does not reach the Front End servers.</span></span> <span data-ttu-id="60f39-192">如需詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的 Director 案例](lync-server-2013-scenarios-for-the-director.md) 。</span><span class="sxs-lookup"><span data-stu-id="60f39-192">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-roles"></a><span data-ttu-id="60f39-193">Persistent Chat Server Role</span><span class="sxs-lookup"><span data-stu-id="60f39-193">Persistent Chat Server Roles</span></span>

<span data-ttu-id="60f39-194">Persistent chat 可讓使用者加入一段時間內的多方、主題型交談。</span><span class="sxs-lookup"><span data-stu-id="60f39-194">Persistent chat enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="60f39-195">Persistent Chat 前端伺服器會執行 persistent chat service。</span><span class="sxs-lookup"><span data-stu-id="60f39-195">The Persistent Chat Front End Server runs the persistent chat service.</span></span> <span data-ttu-id="60f39-196">Persistent Chat 後端伺服器會儲存聊天記錄資料，以及類別和聊天室的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="60f39-196">The Persistent Chat Back End Server stores the chat history data, and information about categories and chat rooms.</span></span> <span data-ttu-id="60f39-197">選用的持續性聊天規範後端伺服器可以儲存聊天內容和符合性事件，以符合規範的目的。</span><span class="sxs-lookup"><span data-stu-id="60f39-197">The optional Persistent Chat Compliance Back End Server can store the chat content and compliance events for the purpose of compliance.</span></span>

<span data-ttu-id="60f39-198">執行 Lync Server Standard Edition 的伺服器也可以在同一部伺服器上執行 Persistent chat 組合。</span><span class="sxs-lookup"><span data-stu-id="60f39-198">Servers running Lync Server Standard Edition can also run Persistent chat collocated on the same server.</span></span> <span data-ttu-id="60f39-199">您無法以 Enterprise Edition 前端伺服器組合持久聊天前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="60f39-199">You cannot collocate the Persistent Chat Front End Server with Enterprise Edition Front End Server.</span></span>

<span data-ttu-id="60f39-200">如需詳細資訊，請參閱 [在 Lync server 2013 中規劃 Persistent Chat Server](lync-server-2013-planning-for-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="60f39-200">For details, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="60f39-201">另請參閱</span><span class="sxs-lookup"><span data-stu-id="60f39-201">See Also</span></span>


[<span data-ttu-id="60f39-202">Lync Server 2013 中的轉送伺服器元件</span><span class="sxs-lookup"><span data-stu-id="60f39-202">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  


[<span data-ttu-id="60f39-203">在 Lync Server 2013 中規劃封存</span><span class="sxs-lookup"><span data-stu-id="60f39-203">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
[<span data-ttu-id="60f39-204">在 Lync Server 2013 中規劃外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="60f39-204">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="60f39-205">Lync Server 2013 中的 Director 案例</span><span class="sxs-lookup"><span data-stu-id="60f39-205">Scenarios for the Director in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-the-director.md)  
[<span data-ttu-id="60f39-206">在 Lync Server 2013 中規劃 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="60f39-206">Planning for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

