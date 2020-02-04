---
title: Lync Server 2013：外部使用者存取概觀
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
ms.openlocfilehash: 1007dfb330aaa21dbac269f606102c51712c9bf7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-external-user-access-in-lync-server-2013"></a><span data-ttu-id="a479b-102">Lync Server 2013 中的外部使用者存取概觀</span><span class="sxs-lookup"><span data-stu-id="a479b-102">Overview of external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a479b-103">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="a479b-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="a479b-104">在本檔中，我們使用「*外部使用者*」來定義與您的 Lync Server 2013 和 lync 2013 使用者在防火牆外通訊的大型使用者類別。</span><span class="sxs-lookup"><span data-stu-id="a479b-104">In this documentation, we use the term *external user* to define a large category of users who communicate with your Lync Server 2013 and Lync 2013 users from outside the firewall.</span></span> <span data-ttu-id="a479b-105">您可以授權用來與內部使用者（也就是從防火牆內登入 Lync Server 的使用者）傳達 Lync Server 2013 的外部使用者可能包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="a479b-105">External users that you can authorize to communicate Lync Server 2013 with internal users (that is, users who sign in to Lync Server from inside the firewall) can include the following:</span></span>

  - <span data-ttu-id="a479b-106">\*\*\*\* 從防火牆外部登入 Lync Server 的組織使用者。   </span><span class="sxs-lookup"><span data-stu-id="a479b-106">**Remote users**   Users of your organization who sign in to Lync Server from outside the firewall.</span></span>

  - <span data-ttu-id="a479b-107">\*\*\*\*    將帳戶與信任的客戶或合作夥伴組織（例如 lync server 2010、lync server 2013 或 Office 通訊伺服器 2007 R2）共同擁有的同盟使用者。</span><span class="sxs-lookup"><span data-stu-id="a479b-107">**Federated users**   Users who have an account with a trusted customer or partner organization, such as Lync Server 2010, Lync Server 2013 or Office Communications Server 2007 R2.</span></span> <span data-ttu-id="a479b-108">同盟使用者也可以使用可擴展訊息和目前狀態通訊協定（XMPP），透過 Edge 伺服器上的 XMPP proxy 以及前端伺服器或池中的 XMPP 閘道，來成為已定義合作夥伴組織的成員。</span><span class="sxs-lookup"><span data-stu-id="a479b-108">Federated users can also be members of defined partner organizations using extensible messaging and presence protocol (XMPP) by way of the XMPP proxy on the Edge Server and XMPP gateway on the Front End Server or pool.</span></span> <span data-ttu-id="a479b-109">已定義信任關係（稱為同盟）不與 Active Directory 網域服務信任關係相關。</span><span class="sxs-lookup"><span data-stu-id="a479b-109">A defined trust relationship, called a federation, is not related to or dependent upon an Active Directory Domain Services trust relationship.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a479b-110">AOL 和 Yahoo！的存留期結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="a479b-110">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="a479b-111">已公佈。</span><span class="sxs-lookup"><span data-stu-id="a479b-111">has been announced.</span></span> <span data-ttu-id="a479b-112">如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</span><span class="sxs-lookup"><span data-stu-id="a479b-112">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="a479b-113">\*\*\*\*    您的使用者透過公用立即訊息聯機服務（Windows Live、Yahoo）建立的公用立即訊息連線使用者連絡人\!</span><span class="sxs-lookup"><span data-stu-id="a479b-113">**Public Instant Messaging Connectivity users**   Contacts that your users establish through public instant messaging connectivity services (Windows Live, Yahoo\!</span></span> <span data-ttu-id="a479b-114">和 AOL）。</span><span class="sxs-lookup"><span data-stu-id="a479b-114">and AOL).</span></span>

  - <span data-ttu-id="a479b-115">\*\*\*\*    您組織成員的行動使用者使用者是使用智慧手機或平板電腦來執行 Lync 行動用戶端，且能夠與其他使用者類別進行通訊。</span><span class="sxs-lookup"><span data-stu-id="a479b-115">**Mobile users**   Users that are members of your organization that use a smart phone or tablet running a Lync Mobile client sign in to your internal deployment and are able to communicate with the other classes of users.</span></span> <span data-ttu-id="a479b-116">行動使用者使用由反向 proxy 發佈的行動服務來存取內部部署。</span><span class="sxs-lookup"><span data-stu-id="a479b-116">The mobile user uses mobility services that are published through the reverse proxy to access the internal deployment.</span></span> <span data-ttu-id="a479b-117">如需 Lync Mobile 可用功能和功能的詳細資訊，請參閱的行動用戶端[http://go.microsoft.com/fwlink/p/?LinkID=234777](http://go.microsoft.com/fwlink/p/?linkid=234777)比較表。</span><span class="sxs-lookup"><span data-stu-id="a479b-117">For details on features and capabilities available to Lync Mobile , see the Mobile Client Comparison Tables at [http://go.microsoft.com/fwlink/p/?LinkID=234777](http://go.microsoft.com/fwlink/p/?linkid=234777).</span></span>

  - <span data-ttu-id="a479b-118">\*\*\*\*    在您組織的 Active Directory 網域服務或支援的聯盟網域中沒有使用者帳戶的匿名使用者使用者，但在內部部署會議中收到遠端參與邀請的使用者。</span><span class="sxs-lookup"><span data-stu-id="a479b-118">**Anonymous users**   Users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but who have received invitations to participate remotely in an on-premises conference.</span></span>

<span data-ttu-id="a479b-119">您的 edge 部署提供下列通訊類型的外部存取：</span><span class="sxs-lookup"><span data-stu-id="a479b-119">Your edge deployment provides external access for the following types of communication:</span></span>

  - <span data-ttu-id="a479b-120">**Im 和目前狀態**   授權的外部使用者可以參與 im 交談和會議，而且他們可以取得其他人目前狀態的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a479b-120">**IM and presence**   Authorized external users can participate in IM conversations and conferences, and they can get information about one another’s presence status.</span></span> <span data-ttu-id="a479b-121">公用 IM 服務提供者的使用者可以與組織中的個別 Lync Server 使用者進行 IM 交談，並存取目前狀態資訊，但他們無法使用 Lync Server 參與 IM 多方會議。</span><span class="sxs-lookup"><span data-stu-id="a479b-121">Users of public IM service providers can participate in IM conversations with individual Lync Server users in your organization and access presence information, but they cannot participate in IM multiparty conferences using Lync Server.</span></span> <span data-ttu-id="a479b-122">它是完全對等通訊。</span><span class="sxs-lookup"><span data-stu-id="a479b-122">It is strictly peer-to-peer communication.</span></span> <span data-ttu-id="a479b-123">公用 IM 服務提供者的使用者不支援檔案傳輸，而且對等通訊中的音訊/影片支援 Windows Messenger 2011 使用者，但不適用於公用 IM 服務提供者的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="a479b-123">File transfer is not supported for users of public IM service providers, and audio/video in peer-to-peer communications is supported for Windows Messenger 2011 users, but not other users of public IM service providers.</span></span>
    
    <span data-ttu-id="a479b-124">支援 SIP 與 XMPP 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="a479b-124">Both SIP and XMPP protocols are supported.</span></span> <span data-ttu-id="a479b-125">若要提供 XMPP 的服務，請參閱[在 Lync Server 2013 中規劃 SIP、XMPP 同盟及公用立即訊息](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)。</span><span class="sxs-lookup"><span data-stu-id="a479b-125">To provide services for XMPP, see [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="a479b-126">\*\*\*\*    已授權外部使用者的網路會議可參與您的 Lync Server 部署所託管的會議。</span><span class="sxs-lookup"><span data-stu-id="a479b-126">**Web conferencing**   Authorized external users can participate in conferences that are hosted on your Lync Server deployment.</span></span> <span data-ttu-id="a479b-127">您可以在遠端使用者、同盟使用者和匿名使用者參與網路會議，但公用 IM 使用者無法參與會議。</span><span class="sxs-lookup"><span data-stu-id="a479b-127">Remote users, federated users, and anonymous users can be enabled for participation in web conferencing, but public IM users cannot participate in conferences.</span></span> <span data-ttu-id="a479b-128">根據您選取的選項，網路會議的使用者可以參與桌面與應用程式共用，也可以充當會議召集人或簡報者。</span><span class="sxs-lookup"><span data-stu-id="a479b-128">Depending on the options that you select, web conferencing-enabled users can participate in desktop and application sharing and can act as meeting organizers or presenters.</span></span>

  - <span data-ttu-id="a479b-129">**A/V 會議**   授權的外部使用者可以參與 Lync Server 部署主機的音訊和視訊會議。</span><span class="sxs-lookup"><span data-stu-id="a479b-129">**A/V conferencing**   Authorized external users can participate in audio and video conferences that your Lync Server deployment hosts.</span></span> <span data-ttu-id="a479b-130">Windows Messenger 2011 使用者支援對等通訊中的音訊/視頻，但不適用於公用 IM 服務提供者的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="a479b-130">Audio/video in peer-to-peer communications is supported for Windows Messenger 2011 users, but not for other users of public IM service providers.</span></span>

<span data-ttu-id="a479b-131">若要控制通訊，您可以設定一或多個原則，以定義組織內部和外部的使用者彼此通訊的方式。</span><span class="sxs-lookup"><span data-stu-id="a479b-131">In order to control communications, you can configure one or more policies that define how users inside and outside your organization communicate with each other.</span></span> <span data-ttu-id="a479b-132">您也可以針對個別內部使用者或特定類型的外部使用者設定設定並套用原則，以控制與外部使用者的通訊。</span><span class="sxs-lookup"><span data-stu-id="a479b-132">You can also configure settings and apply policies for individual internal users or for specific types of external users to control communications with external users.</span></span>

<span data-ttu-id="a479b-133">Lync Server 2013 用來提供外部存取的角色：</span><span class="sxs-lookup"><span data-stu-id="a479b-133">Lync Server 2013 roles that are used to provide external access:</span></span>

<span data-ttu-id="a479b-134">**Edge 伺服器**   ： edge 伺服器是一種伺服器或伺服器池，可執行允許外部存取 IM 和目前狀態、會議、音訊/影片，以及其他媒體（例如，檔案傳輸）服務的服務。</span><span class="sxs-lookup"><span data-stu-id="a479b-134">**Edge Server**   The Edge Server is a server or a pool of servers that run the services that allow external access to IM and presence, conferencing, audio/video, and other media (for example, file transfer) services.</span></span> <span data-ttu-id="a479b-135">您也可以將 Edge 伺服器設定為與其他 Lync Server 或 Office 通訊伺服器 2007 R2 部署以及其他 XMPP 部署進行聯盟。</span><span class="sxs-lookup"><span data-stu-id="a479b-135">Optionally, you can configure the Edge Server to federate with other Lync Server or Office Communications Server 2007 R2 deployments, and other XMPP deployments.</span></span> <span data-ttu-id="a479b-136">您可以透過 Edge 伺服器啟用並設定選用的公用 IM 連線功能。</span><span class="sxs-lookup"><span data-stu-id="a479b-136">The optional public IM connectivity feature is enabled and configured through the Edge Server.</span></span>

<span data-ttu-id="a479b-137">**主管**   ：控制器是執行 Lync server 2013 主管角色的選用伺服器或伺服器池，該角色會預先驗證使用者要求，並將要求傳送給使用者的家用前端伺服器或頂層端池，但不會家用任何使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="a479b-137">**Director**   The Director is an optional server or server pool running the Lync Server 2013 Director role that pre-authenticates user requests and routes requests to the users’ home Front End Server or Front End pool, but does not home any user accounts.</span></span>

<span data-ttu-id="a479b-138">**反向**proxy 是特殊伺服器的一般期限，可發佈內部網路上可用的資源，並從已發佈的資源取得用戶端的資訊。   </span><span class="sxs-lookup"><span data-stu-id="a479b-138">**Reverse Proxy**   A reverse proxy is a general term for specialized servers that publish resources available on the internal network and retrieve information for clients from the published resource.</span></span> <span data-ttu-id="a479b-139">Lync Server 2013 使用反向 proxy 來發佈許多功能，例如會議會議、會議加入位置、通訊錄、通訊群組清單展開、下載會議內容、裝置更新、行動服務等等。</span><span class="sxs-lookup"><span data-stu-id="a479b-139">Lync Server 2013 uses the reverse proxy to publish a number of features, such as conferencing meetings, conference join locations, the address book, distribution list expansion, downloading meeting content, device updates, Mobility services, and more.</span></span> <span data-ttu-id="a479b-140">任何可符合發佈必要資源位置需求的反向 proxy 都可以使用。</span><span class="sxs-lookup"><span data-stu-id="a479b-140">Any reverse proxy that can meet the requirements for publishing the necessary resource locations can be used.</span></span> <span data-ttu-id="a479b-141">Microsoft Forefront 威脅管理閘道（TMG）2010是用來示範必要發佈規則的範例，但不需要 Forefront TMG 2010。</span><span class="sxs-lookup"><span data-stu-id="a479b-141">Microsoft Forefront Threat Management Gateway (TMG) 2010 is used as an example for the purposes of illustrating the publishing rules necessary, but Forefront TMG 2010 is not required.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a479b-142">Lync Server 2013 支援 IPv4 與 IPv6。</span><span class="sxs-lookup"><span data-stu-id="a479b-142">Lync Server 2013 supports both IPv4 and IPv6.</span></span> <span data-ttu-id="a479b-143">Windows Server&nbsp;2008&nbsp;r2、Windows Server 2012 和 Windows server 2012 R2 使用可同時使用 IPv4 與 IPv6 的雙堆疊。</span><span class="sxs-lookup"><span data-stu-id="a479b-143">Windows Server&nbsp;2008&nbsp;R2, Windows Server 2012, and Windows Server 2012 R2 use a dual stack that can use both IPv4 and IPv6 concurrently.</span></span> <span data-ttu-id="a479b-144">這很重要，因為部署從 IPv4 轉移到 IPv6 的過渡性質。</span><span class="sxs-lookup"><span data-stu-id="a479b-144">This is important because of the transitional nature of a deployment moving from IPv4 to IPv6.</span></span> <span data-ttu-id="a479b-145">在某些情況下，可能會支援 IPv4，在部署的其他區域中，您可以使用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="a479b-145">IPv4 can be supported in some areas, where in other areas of the deployment, IPv6 can be used.</span></span> <span data-ttu-id="a479b-146">這在網際網路和內部部署的考慮尤為重要。</span><span class="sxs-lookup"><span data-stu-id="a479b-146">This is especially important where the Internet and internal deployments are concerned.</span></span> <span data-ttu-id="a479b-147">外部用戶端必須透過反向 proxy 進行通訊，才能使用行動、會議、通訊錄下載及其他服務。</span><span class="sxs-lookup"><span data-stu-id="a479b-147">External clients must communicate through the reverse proxy to use services such as mobility, meetings, address book download, and others.</span></span> <span data-ttu-id="a479b-148">目前，Forefront 威脅管理閘道2010和 Internet 安全性和加速伺服器2006不支援 IPv6 定址，無論它們的版本為何都要部署。</span><span class="sxs-lookup"><span data-stu-id="a479b-148">Currently, Forefront Threat Management Gateway 2010 and Internet Security and Acceleration Server 2006 do not support IPv6 addressing, regardless of the operating system version that they are deployed on.</span></span> <span data-ttu-id="a479b-149">您必須規劃與與外部用戶端相關的 IPv6 和 IPv4 使用方式。</span><span class="sxs-lookup"><span data-stu-id="a479b-149">You must plan accordingly in relation to your use of IPv6 and IPv4 as they relate to external clients.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

