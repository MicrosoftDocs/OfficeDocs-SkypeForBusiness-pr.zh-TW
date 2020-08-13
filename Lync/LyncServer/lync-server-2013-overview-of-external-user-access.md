---
title: Lync Server 2013：外部使用者存取的概覽
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of external user access
ms:assetid: 97aded6c-5fa3-4225-95a6-9ad094d61654
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398775(v=OCS.15)
ms:contentKeyID: 48184934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdf596a16fbed1cab1b622b373febb0f173344cb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-external-user-access-in-lync-server-2013"></a><span data-ttu-id="6857c-102">Lync Server 2013 中的外部使用者存取的概覽</span><span class="sxs-lookup"><span data-stu-id="6857c-102">Overview of external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6857c-103">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="6857c-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="6857c-104">在本檔中，我們使用「 *外部使用者* 」來定義與您的 Lync Server 2013 和 lync 2013 使用者從防火牆外通訊的大型使用者類別。</span><span class="sxs-lookup"><span data-stu-id="6857c-104">In this documentation, we use the term *external user* to define a large category of users who communicate with your Lync Server 2013 and Lync 2013 users from outside the firewall.</span></span> <span data-ttu-id="6857c-105">您可以授權以與內部使用者通訊 Lync Server 2013 的外部使用者 (也就是說，從) 防火牆內登入 Lync Server 的使用者可以包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="6857c-105">External users that you can authorize to communicate Lync Server 2013 with internal users (that is, users who sign in to Lync Server from inside the firewall) can include the following:</span></span>

  - <span data-ttu-id="6857c-106">**遠端使用者**    從防火牆外登入 Lync Server 之組織的使用者。</span><span class="sxs-lookup"><span data-stu-id="6857c-106">**Remote users**   Users of your organization who sign in to Lync Server from outside the firewall.</span></span>

  - <span data-ttu-id="6857c-107">同盟**使用者**    具有信任之客戶或夥伴組織之帳戶的使用者，例如 Lync Server 2010、Lync Server 2013 或 Office 通訊伺服器 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="6857c-107">**Federated users**   Users who have an account with a trusted customer or partner organization, such as Lync Server 2010, Lync Server 2013 or Office Communications Server 2007 R2.</span></span> <span data-ttu-id="6857c-108">同盟使用者也可以是使用可延伸訊息和顯示狀態通訊協定 (XMPP) 透過前端伺服器或集區上的 Edge Server 和 XMPP 閘道上的 XMPP proxy 的方式來定義之夥伴組織的成員。</span><span class="sxs-lookup"><span data-stu-id="6857c-108">Federated users can also be members of defined partner organizations using extensible messaging and presence protocol (XMPP) by way of the XMPP proxy on the Edge Server and XMPP gateway on the Front End Server or pool.</span></span> <span data-ttu-id="6857c-109">已定義的信任關係（稱為「同盟」）與 Active Directory 網域服務信任關聯或相互依存。</span><span class="sxs-lookup"><span data-stu-id="6857c-109">A defined trust relationship, called a federation, is not related to or dependent upon an Active Directory Domain Services trust relationship.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6857c-110">AOL 和 Yahoo！的循環結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="6857c-110">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="6857c-111">已宣告。</span><span class="sxs-lookup"><span data-stu-id="6857c-111">has been announced.</span></span> <span data-ttu-id="6857c-112">如需詳細資訊，請參閱 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</span><span class="sxs-lookup"><span data-stu-id="6857c-112">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="6857c-113">**公用立即訊息連線使用者**    您的使用者透過公用立即訊息聯機服務建立的連絡人 (Windows Live、Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="6857c-113">**Public Instant Messaging Connectivity users**   Contacts that your users establish through public instant messaging connectivity services (Windows Live, Yahoo\!</span></span> <span data-ttu-id="6857c-114">和 AOL) 。</span><span class="sxs-lookup"><span data-stu-id="6857c-114">and AOL).</span></span>

  - <span data-ttu-id="6857c-115">行動**使用者**    使用智慧型電話或 tablet 執行 Lync 行動用戶端之組織成員的使用者，會登入您的內部部署，而且可以與其他類別的使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="6857c-115">**Mobile users**   Users that are members of your organization that use a smart phone or tablet running a Lync Mobile client sign in to your internal deployment and are able to communicate with the other classes of users.</span></span> <span data-ttu-id="6857c-116">行動使用者使用透過反向 proxy 發佈的行動服務來存取內部部署。</span><span class="sxs-lookup"><span data-stu-id="6857c-116">The mobile user uses mobility services that are published through the reverse proxy to access the internal deployment.</span></span> <span data-ttu-id="6857c-117">如需 Lync Mobile 可用功能的詳細資訊，請參閱中的行動用戶端比較表 [https://go.microsoft.com/fwlink/p/?LinkID=234777](https://go.microsoft.com/fwlink/p/?linkid=234777) 。</span><span class="sxs-lookup"><span data-stu-id="6857c-117">For details on features and capabilities available to Lync Mobile , see the Mobile Client Comparison Tables at [https://go.microsoft.com/fwlink/p/?LinkID=234777](https://go.microsoft.com/fwlink/p/?linkid=234777).</span></span>

  - <span data-ttu-id="6857c-118">**匿名使用者**    在您組織的 Active Directory 網域服務或支援的同盟網域中沒有使用者帳戶的使用者，但已接收到在內部部署會議中遠端加入邀請的使用者。</span><span class="sxs-lookup"><span data-stu-id="6857c-118">**Anonymous users**   Users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but who have received invitations to participate remotely in an on-premises conference.</span></span>

<span data-ttu-id="6857c-119">您的 edge 部署提供下列通訊類型的外部存取：</span><span class="sxs-lookup"><span data-stu-id="6857c-119">Your edge deployment provides external access for the following types of communication:</span></span>

  - <span data-ttu-id="6857c-120">**IM 和目前狀態**    授權的外部使用者可以參與 IM 交談和會議，也可以取得彼此的狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="6857c-120">**IM and presence**   Authorized external users can participate in IM conversations and conferences, and they can get information about one another’s presence status.</span></span> <span data-ttu-id="6857c-121">公用 IM 服務提供者的使用者可以與組織中的個別 Lync Server 使用者參與 IM 交談，存取顯示狀態資訊，但不能使用 Lync Server 參與 IM 多方會議。</span><span class="sxs-lookup"><span data-stu-id="6857c-121">Users of public IM service providers can participate in IM conversations with individual Lync Server users in your organization and access presence information, but they cannot participate in IM multiparty conferences using Lync Server.</span></span> <span data-ttu-id="6857c-122">完全對等通訊。</span><span class="sxs-lookup"><span data-stu-id="6857c-122">It is strictly peer-to-peer communication.</span></span> <span data-ttu-id="6857c-123">公用 IM 服務提供者的使用者不支援檔案傳輸，而且對等通訊中的音訊/影片支援 Windows Messenger 2011 使用者，但不適用於公用 IM 服務提供者的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="6857c-123">File transfer is not supported for users of public IM service providers, and audio/video in peer-to-peer communications is supported for Windows Messenger 2011 users, but not other users of public IM service providers.</span></span>
    
    <span data-ttu-id="6857c-124">支援 SIP 和 XMPP 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="6857c-124">Both SIP and XMPP protocols are supported.</span></span> <span data-ttu-id="6857c-125">若要提供服務以供 XMPP，請參閱 [在 Lync Server 2013 中規劃 SIP、XMPP 同盟及公用立即訊息](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)。</span><span class="sxs-lookup"><span data-stu-id="6857c-125">To provide services for XMPP, see [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="6857c-126">**Web 會議**    授權的外部使用者可以加入您的 Lync Server 部署上的會議。</span><span class="sxs-lookup"><span data-stu-id="6857c-126">**Web conferencing**   Authorized external users can participate in conferences that are hosted on your Lync Server deployment.</span></span> <span data-ttu-id="6857c-127">遠端使用者、同盟使用者和匿名使用者可以啟用網路會議，但公用 IM 使用者無法參與會議。</span><span class="sxs-lookup"><span data-stu-id="6857c-127">Remote users, federated users, and anonymous users can be enabled for participation in web conferencing, but public IM users cannot participate in conferences.</span></span> <span data-ttu-id="6857c-128">視您選取的選項而定，啟用 web 會議的使用者可以參與桌面和應用程式共用，也可以充當會議召集人或簡報者。</span><span class="sxs-lookup"><span data-stu-id="6857c-128">Depending on the options that you select, web conferencing-enabled users can participate in desktop and application sharing and can act as meeting organizers or presenters.</span></span>

  - <span data-ttu-id="6857c-129">**會議 A/V**    已授權的外部使用者可以參與您的 Lync Server 部署主控的音訊和影片會議。</span><span class="sxs-lookup"><span data-stu-id="6857c-129">**A/V conferencing**   Authorized external users can participate in audio and video conferences that your Lync Server deployment hosts.</span></span> <span data-ttu-id="6857c-130">對等通訊中的音訊/影片支援 Windows Messenger 2011 使用者，但不適用於公用 IM 服務提供者的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="6857c-130">Audio/video in peer-to-peer communications is supported for Windows Messenger 2011 users, but not for other users of public IM service providers.</span></span>

<span data-ttu-id="6857c-131">若要控制通訊，您可以設定一或多個原則，以定義組織內部和外部使用者之間的通訊方式。</span><span class="sxs-lookup"><span data-stu-id="6857c-131">In order to control communications, you can configure one or more policies that define how users inside and outside your organization communicate with each other.</span></span> <span data-ttu-id="6857c-132">您也可以為個別內部使用者或特定類型的外部使用者設定設定並套用原則，以控制與外部使用者的通訊。</span><span class="sxs-lookup"><span data-stu-id="6857c-132">You can also configure settings and apply policies for individual internal users or for specific types of external users to control communications with external users.</span></span>

<span data-ttu-id="6857c-133">Lync Server 2013 用來提供外部存取的角色：</span><span class="sxs-lookup"><span data-stu-id="6857c-133">Lync Server 2013 roles that are used to provide external access:</span></span>

<span data-ttu-id="6857c-134">**Edge Server**    Edge Server 是伺服器或伺服器集區，可執行服務，以允許外部存取 IM 及目前狀態、會議、音訊/影片及其他媒體 (例如，檔案傳輸) 服務。</span><span class="sxs-lookup"><span data-stu-id="6857c-134">**Edge Server**   The Edge Server is a server or a pool of servers that run the services that allow external access to IM and presence, conferencing, audio/video, and other media (for example, file transfer) services.</span></span> <span data-ttu-id="6857c-135">您也可以將 Edge Server 設定為與其他 Lync Server 或 Office 通訊伺服器 2007 R2 部署及其他 XMPP 部署的同盟。</span><span class="sxs-lookup"><span data-stu-id="6857c-135">Optionally, you can configure the Edge Server to federate with other Lync Server or Office Communications Server 2007 R2 deployments, and other XMPP deployments.</span></span> <span data-ttu-id="6857c-136">透過 Edge Server 啟用並設定選用的公用 IM 連線功能。</span><span class="sxs-lookup"><span data-stu-id="6857c-136">The optional public IM connectivity feature is enabled and configured through the Edge Server.</span></span>

<span data-ttu-id="6857c-137">**Director**    Director 是執行 Lync Server 2013 Director 角色的選用伺服器或伺服器集區，可對使用者的首頁前端伺服器或前端集區執行預先驗證使用者要求和路由要求，但不會家用任何使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="6857c-137">**Director**   The Director is an optional server or server pool running the Lync Server 2013 Director role that pre-authenticates user requests and routes requests to the users’ home Front End Server or Front End pool, but does not home any user accounts.</span></span>

<span data-ttu-id="6857c-138">**反向 Proxy**    反向 proxy 是特殊伺服器的一般術語，可用來發佈內部網路上的資源，並從已發佈的資源中取得用戶端的資訊。</span><span class="sxs-lookup"><span data-stu-id="6857c-138">**Reverse Proxy**   A reverse proxy is a general term for specialized servers that publish resources available on the internal network and retrieve information for clients from the published resource.</span></span> <span data-ttu-id="6857c-139">Lync Server 2013 使用反向 proxy 來發佈許多功能，例如會議會議、會議加入位置、通訊錄、通訊群組清單展開、下載會議內容、裝置更新、行動服務等等。</span><span class="sxs-lookup"><span data-stu-id="6857c-139">Lync Server 2013 uses the reverse proxy to publish a number of features, such as conferencing meetings, conference join locations, the address book, distribution list expansion, downloading meeting content, device updates, Mobility services, and more.</span></span> <span data-ttu-id="6857c-140">可以使用任何可符合發佈必要資源位置之需求的反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="6857c-140">Any reverse proxy that can meet the requirements for publishing the necessary resource locations can be used.</span></span> <span data-ttu-id="6857c-141">Microsoft Forefront 威脅管理閘道 (TMG) 2010 是一個範例，用來示範必要的發行規則，但不需要 Forefront TMG 2010。</span><span class="sxs-lookup"><span data-stu-id="6857c-141">Microsoft Forefront Threat Management Gateway (TMG) 2010 is used as an example for the purposes of illustrating the publishing rules necessary, but Forefront TMG 2010 is not required.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6857c-142">Lync Server 2013 同時支援 IPv4 和 IPv6。</span><span class="sxs-lookup"><span data-stu-id="6857c-142">Lync Server 2013 supports both IPv4 and IPv6.</span></span> <span data-ttu-id="6857c-143">Windows Server &nbsp; 2008 &nbsp; R2、windows server 2012 及 Windows Server 2012 R2 使用雙重堆疊，可以同時使用 IPv4 和 IPv6。</span><span class="sxs-lookup"><span data-stu-id="6857c-143">Windows Server&nbsp;2008&nbsp;R2, Windows Server 2012, and Windows Server 2012 R2 use a dual stack that can use both IPv4 and IPv6 concurrently.</span></span> <span data-ttu-id="6857c-144">這一點很重要，因為部署的過渡性質從 IPv4 移至 IPv6。</span><span class="sxs-lookup"><span data-stu-id="6857c-144">This is important because of the transitional nature of a deployment moving from IPv4 to IPv6.</span></span> <span data-ttu-id="6857c-145">在某些情況下可以支援 IPv4，在某些情況下，您可以在部署的其他區域中使用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="6857c-145">IPv4 can be supported in some areas, where in other areas of the deployment, IPv6 can be used.</span></span> <span data-ttu-id="6857c-146">這對網際網路和內部部署的考慮尤為重要。</span><span class="sxs-lookup"><span data-stu-id="6857c-146">This is especially important where the Internet and internal deployments are concerned.</span></span> <span data-ttu-id="6857c-147">外部用戶端必須透過反向 proxy 進行通訊，才能使用行動、會議、通訊錄下載等服務。</span><span class="sxs-lookup"><span data-stu-id="6857c-147">External clients must communicate through the reverse proxy to use services such as mobility, meetings, address book download, and others.</span></span> <span data-ttu-id="6857c-148">目前，Forefront 威脅管理閘道2010和 Internet Security 和加速度 Server 2006 不支援 IPv6 定址，不論其部署所在的作業系統版本為何。</span><span class="sxs-lookup"><span data-stu-id="6857c-148">Currently, Forefront Threat Management Gateway 2010 and Internet Security and Acceleration Server 2006 do not support IPv6 addressing, regardless of the operating system version that they are deployed on.</span></span> <span data-ttu-id="6857c-149">您必須相對於使用 IPv6 和 IPv4 （與外部用戶端有關）進行對應計畫。</span><span class="sxs-lookup"><span data-stu-id="6857c-149">You must plan accordingly in relation to your use of IPv6 and IPv4 as they relate to external clients.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

