---
title: Lync Server 2013：行動性的拓撲和元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ccce5823e997cafc5e8c8e7555df18bc67d1fe6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a><span data-ttu-id="ea121-102">Lync Server 2013 中行動性的拓撲和元件</span><span class="sxs-lookup"><span data-stu-id="ea121-102">Topologies and components for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea121-103">_**主題上次修改日期：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="ea121-103">_**Topic Last Modified:** 2013-02-17_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="ea121-104">為了支援行動裝置上的 Lync 行動應用程式，Lync Server 2013 提供三種服務： Lync Server 2013 Mcx 行動服務、Lync Server 2013 自動探索服務，以及 Lync Server 2013 推播通知服務。</span><span class="sxs-lookup"><span data-stu-id="ea121-104">To support Lync mobile applications on mobile devices, Lync Server 2013 provides three services: Lync Server 2013 Mcx Mobility Service, Lync Server 2013 Autodiscover Service, and Lync Server 2013 Push Notification Service.</span></span> <span data-ttu-id="ea121-105">Lync Server 2013 的累計更新：2月2013新增「Lync 2013 行動用戶端」（透過使用整合通訊網頁 API 或 UCWA）的免費服務。</span><span class="sxs-lookup"><span data-stu-id="ea121-105">The Cumulative Updates for Lync Server 2013: February 2013 adds a complimentary, but advanced, service for Lync 2013 Mobile clients—mobility support through the use of the Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="ea121-106">本節簡短說明這些元件，並識別支援行動性的 Lync Server 2013 拓撲。</span><span class="sxs-lookup"><span data-stu-id="ea121-106">This section briefly describes these components and identifies the Lync Server 2013 topologies that support mobility.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ea121-107">在混合式部署中也提供行動服務。</span><span class="sxs-lookup"><span data-stu-id="ea121-107">Mobility services are also available in hybrid deployments.</span></span> <span data-ttu-id="ea121-108">若您的使用者在線上，您就不需要部署支援行動性的服務。</span><span class="sxs-lookup"><span data-stu-id="ea121-108">You are not required to deploy services for supporting mobility if your users are homed online.</span></span> <span data-ttu-id="ea121-109">您必須定義自動探索服務的設定，讓行動使用者能夠尋找其線上身分識別。</span><span class="sxs-lookup"><span data-stu-id="ea121-109">You do need to define a setting for the Autodiscover Service to enable mobile users to find their online identity.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ea121-110">若要規劃任何外部使用者連線 (例如，同盟、外部使用者存取或行動功能) ，您必須使用具有 Standard Edition server 和前端伺服器或前端集區的 Edge server。</span><span class="sxs-lookup"><span data-stu-id="ea121-110">If you are planning any external user connectivity (for example, federation, external user access, or mobility features), you must use Edge Servers with Standard Edition server and the Front End Server or Front End pool.</span></span> <span data-ttu-id="ea121-111">Standard Edition server 和前端伺服器或前端集區沒有必要的元件可讓外部使用者存取您的內部部署，或內部部署與外部使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="ea121-111">The Standard Edition server and the Front End Server or Front End pool do not have the necessary components to enable external users to access your internal deployment, or for the internal deployment to communicate with your external users.</span></span> <span data-ttu-id="ea121-112">針對包含與內部使用者共同作業或通訊之外部使用者的所有案例（包括行動性），您必須至少部署一個 Edge Server 與一個反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="ea121-112">For all scenarios that include external users collaborating or communicating with internal users, including mobility, you must deploy at least one Edge Server and one reverse proxy.</span></span><BR><span data-ttu-id="ea121-113"><EM>推播通知</EM>使用 Lync Online 服務的同盟類型，它會主控推播通知的 (PNCH) 。</span><span class="sxs-lookup"><span data-stu-id="ea121-113"><EM>Push notification</EM> uses a type of federation to the Lync Online services, which hosts the Push Notification Clearing House (PNCH).</span></span> <span data-ttu-id="ea121-114">推播通知指的是在行動裝置非使用中時，會由應用程式推入 Apple iPhone、iPad 和 Windows Phone 之聲音警示、螢幕上警示 (文字) 和徽章。</span><span class="sxs-lookup"><span data-stu-id="ea121-114">Push notification refers to the sound alerts, on-screen alerts (text), and badges that are pushed by applications to the Apple iPhone, iPad, and Windows Phone, when the mobile device is inactive.</span></span> <span data-ttu-id="ea121-115">PNCH 接收來自 Lync Server 的推播通知。</span><span class="sxs-lookup"><span data-stu-id="ea121-115">PNCH receives push notifications from Lync Server.</span></span> <span data-ttu-id="ea121-116">當 PNCH 收到郵件的通知時，PNCH 會根據郵件適用的行動用戶端，將通知傳送給行動用戶端（透過 Apple Push Notification Services 或 Lync Server 2013 推播通知服務）。</span><span class="sxs-lookup"><span data-stu-id="ea121-116">When PNCH receives a notification of a message, PNCH forwards a notification to mobile clients through either the Apple Push Notification Services or Lync Server 2013 Push Notification Service, based on the mobile client that the message is intended for.</span></span> <span data-ttu-id="ea121-117">PNCH 是這些行動用戶端所需的服務。</span><span class="sxs-lookup"><span data-stu-id="ea121-117">PNCH is a required service for these mobile clients.</span></span> <span data-ttu-id="ea121-118">為了同盟至 Lync Online，PNCH 會使用 Edge Server 和憑證，以確保機密性和驗證、原則，以及正確設定的網域名稱系統 (DNS) 記錄。</span><span class="sxs-lookup"><span data-stu-id="ea121-118">To federate to Lync Online, PNCH uses Edge Servers and certificates to ensure confidentiality and authentication, policies, and correctly configured domain name system (DNS) records.</span></span> <span data-ttu-id="ea121-119">Nokia Symbian 和 Android 型 Lync Mobile 用戶端不使用 PNCH。</span><span class="sxs-lookup"><span data-stu-id="ea121-119">Nokia Symbian and Android-based Lync Mobile clients do not use PNCH.</span></span> <span data-ttu-id="ea121-120">如需規劃及部署 Edge server 的詳細資訊，請參閱在 lync server <A href="lync-server-2013-planning-for-external-user-access.md">2013 中規劃外部使用者存取</A>和<A href="lync-server-2013-deploying-external-user-access.md">部署 lync server 2013 中的外部使用者存取</A>。</span><span class="sxs-lookup"><span data-stu-id="ea121-120">For details about planning and deploying Edge Servers, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A> and <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="ea121-121">2013 Lync Server 的 Lync Server 行動用戶端（適用于 Lync Server 2013 的累計更新引進）：2月2013不再使用推播通知或推播通知 PNCH () 。</span><span class="sxs-lookup"><span data-stu-id="ea121-121">The Lync 2013 Mobile clients for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer use push notification or the push notification clearing house (PNCH).</span></span> <span data-ttu-id="ea121-122">在 Windows Phone 上的 Lync 2013 行動用戶端仍會使用推播通知和 (PNCH) 。</span><span class="sxs-lookup"><span data-stu-id="ea121-122">Lync 2013 Mobile clients on Windows Phone still use push notification and the (PNCH).</span></span>



</div>

<div>

## <a name="mobility-components"></a><span data-ttu-id="ea121-123">行動元件</span><span class="sxs-lookup"><span data-stu-id="ea121-123">Mobility Components</span></span>

<span data-ttu-id="ea121-124">支援行動性的服務如下：</span><span class="sxs-lookup"><span data-stu-id="ea121-124">The services that support mobility are as follows:</span></span>

  - <span data-ttu-id="ea121-125">\*\*Lync Server 2013 整合通訊網頁 API (UCWA) \*\*    提供 Lync Server 2013 中即時通訊與行動裝置和 web 用戶端之間的服務。</span><span class="sxs-lookup"><span data-stu-id="ea121-125">**Lync Server 2013 Unified Communications Web API (UCWA)**   Provides services for real-time communications with mobile and web clients in Lync Server 2013.</span></span> <span data-ttu-id="ea121-126">當您將 Lync Server 2013 2013 的累計更新部署至前端伺服器及 Director 時，安裝會在內部和外部 web 服務 (Ucwa) 中建立虛擬目錄。</span><span class="sxs-lookup"><span data-stu-id="ea121-126">When you deploy the Cumulative Updates for Lync Server 2013: February 2013 to the Front End Server and Director, the installation creates a virtual directory in the internal and external web services (Ucwa).</span></span> <span data-ttu-id="ea121-127">屬於 Ucwa 虛擬目錄的網頁元件接受來自啟用 UCWA 之用戶端的呼叫。</span><span class="sxs-lookup"><span data-stu-id="ea121-127">A web component that is part of the Ucwa virtual directory accepts calls from UCWA-enabled clients.</span></span> <span data-ttu-id="ea121-128">用戶端應用程式會透過 REST 介面進行通訊，以進行目前狀態、連絡人、立即訊息、VoIP、視訊會議及共同作業。</span><span class="sxs-lookup"><span data-stu-id="ea121-128">The client apps communicate over a REST interface for presence, contacts, instant messaging, VoIP, video conferencing, and collaboration.</span></span> <span data-ttu-id="ea121-129">UCWA 使用 P-GET 通道，將事件（例如來電、內送立即訊息或郵件）傳送至用戶端應用程式。</span><span class="sxs-lookup"><span data-stu-id="ea121-129">UCWA uses a P-GET based channel to send events, such as an incoming call, incoming instant message, or a message to the client app.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ea121-130"><EM>REST</EM>或代表性狀態轉移是一種軟體架構樣式，適用于已廣泛採用多種表單的分散式系統，而且一般都很適合 Web 服務的需求。</span><span class="sxs-lookup"><span data-stu-id="ea121-130"><EM>REST</EM> or representational state transfer, is a software architectural style for distributed systems that has been widely adopted in many forms and is well suited to the requirements of Web services in general.</span></span>

    
    </div>

  - <span data-ttu-id="ea121-131">\*\*Lync Server 2013 行動性服務 (Mcx) \*\*    此服務支援在行動裝置上進行 Lync 功能，例如立即訊息 (IM) 、目前狀態和連絡人。</span><span class="sxs-lookup"><span data-stu-id="ea121-131">**Lync Server 2013 Mobility Service (Mcx)**   This service supports Lync functionality, such as instant messaging (IM), presence, and contacts, on mobile devices.</span></span> <span data-ttu-id="ea121-132">行動服務安裝在每個集區中的每一部前端伺服器上，以支援行動裝置上的 Lync 功能。</span><span class="sxs-lookup"><span data-stu-id="ea121-132">The Mobility Service is installed on every Front End Server in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="ea121-133">當您安裝 Lync Server 2013 時，會在內部網站和前端伺服器上的外部網站上建立新的虛擬目錄 (Mcx) 。</span><span class="sxs-lookup"><span data-stu-id="ea121-133">When you install Lync Server 2013, a new virtual directory (Mcx) is created under both the internal website and the external website on your Front End Servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ea121-134">Lync Server 2013 （含 Lync Server 2013 的累計更新）：二月份2013同時支援 Lync Server 2010： 11 2011 月的累計更新所引進的行動服務，也就是 Mcx 和 UCWA 網頁元件。</span><span class="sxs-lookup"><span data-stu-id="ea121-134">Lync Server 2013 with the Cumulative Updates for Lync Server 2013: February 2013 supports both the Mobility service introduced in the Cumulative Update for Lync Server 2010: November 2011, commonly known as Mcx, and the UCWA web component.</span></span> <span data-ttu-id="ea121-135">這兩種行動裝置的組合可提供 Lync Server 2013 上的 Lync 2010 行動裝置和 Lync 2013 行動用戶端的互通性和使用方式。</span><span class="sxs-lookup"><span data-stu-id="ea121-135">The combination of these two mobility services provides interoperability and use by users with Lync 2010 Mobile and Lync 2013 Mobile clients on Lync Server 2013.</span></span>

    
    </div>

  - <span data-ttu-id="ea121-136">**Lync Server 2013 自動探索服務**    這項服務會識別使用者的位置，並可讓行動裝置和其他 Lync 用戶端尋找資源，例如 Lync Server 2013 Web 服務的內部和外部 URLs，以及 Mcx 或 UCWA 的 URL （不論網路位置為何）。</span><span class="sxs-lookup"><span data-stu-id="ea121-136">**Lync Server 2013 Autodiscover Service**   This service identifies the location of the user and enables mobile devices and other Lync clients to locate resources—such as the internal and external URLs for Lync Server 2013 Web Services, and the URL for the Mcx or UCWA—regardless of network location.</span></span> <span data-ttu-id="ea121-137">自動探索針對網路內部使用者 (lyncdiscoverinternal，使用硬式編碼主機名稱。lyncdiscover 在網路外的使用者) 和使用者的 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="ea121-137">Automatic discovery uses hardcoded host names (lyncdiscoverinternal for users inside the network; lyncdiscover for users outside the network) and the SIP domain of the user.</span></span> <span data-ttu-id="ea121-138">它支援使用 HTTP 或 HTTPS 的用戶端連線。</span><span class="sxs-lookup"><span data-stu-id="ea121-138">It supports client connections that use either HTTP or HTTPS.</span></span>
    
    <span data-ttu-id="ea121-139">自動探索服務會安裝在每個前端伺服器及每個集區中的每個 Director 上，以支援行動裝置上的 Lync 功能。</span><span class="sxs-lookup"><span data-stu-id="ea121-139">The Autodiscover Service is installed on every Front End Server and on every Director in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="ea121-140">當您安裝自動探索服務時，會在內部網站和外部網站（兩部前端伺服器及 Director）下建立新的虛擬目錄 (自動探索) 。</span><span class="sxs-lookup"><span data-stu-id="ea121-140">When you install the Autodiscover Service, a new virtual directory (Autodiscover) is created under both the internal website and the external website, on both Front End Servers and Directors.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ea121-141">自動探索服務是在提供行動用戶端服務時維持重要元件，所以會列在這裡。</span><span class="sxs-lookup"><span data-stu-id="ea121-141">The Autodiscover Service is listed here because it remains a critical component when providing mobile client services.</span></span> <span data-ttu-id="ea121-142">Lync Server 2013 中的自動探索角色已經過擴充，可提供所有用戶端的服務。</span><span class="sxs-lookup"><span data-stu-id="ea121-142">The role of Autodiscover in Lync Server 2013 has been expanded to provide services for all clients.</span></span> <span data-ttu-id="ea121-143">如需規劃自動探索服務的詳細資訊，請參閱<A href="lync-server-2013-planning-for-autodiscover.md">在 Lync Server 2013 中規劃自動</A>探索。</span><span class="sxs-lookup"><span data-stu-id="ea121-143">For details about planning for the Autodiscover Service, see <A href="lync-server-2013-planning-for-autodiscover.md">Planning for Autodiscover in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="ea121-144">**推播通知服務**    此項服務是位於 Lync Online 資料中心的雲端式服務。</span><span class="sxs-lookup"><span data-stu-id="ea121-144">**Push Notification Service**   This service is a cloud-based service that is located in the Lync Online data center.</span></span> <span data-ttu-id="ea121-145">當支援的 Apple iOS 裝置或 Windows Phone 上的 Lync 行動應用程式處於非使用中狀態時，它無法回應新的事件，例如新的立即訊息 (IM) 邀請、錯過的立即訊息、未接來電或語音信箱，因為這些裝置不支援在後臺執行的行動應用程式。</span><span class="sxs-lookup"><span data-stu-id="ea121-145">When the Lync mobile application on a supported Apple iOS device or Windows Phone is inactive, it cannot respond to new events, such as a new instant messaging (IM) invitation, a missed instant message, a missed call, or voice mail, because these devices do not support mobile applications running in the background.</span></span> <span data-ttu-id="ea121-146">在這些情況下，會將新事件（稱為推播*通知*）的通知傳送至行動裝置。</span><span class="sxs-lookup"><span data-stu-id="ea121-146">In these cases, a notification of the new event—called a *push notification*—is sent to the mobile device.</span></span> <span data-ttu-id="ea121-147">行動服務會將通知傳送至雲端式推播通知服務，然後將通知傳送至 Apple Push Notification Service (APNS)  (以取得支援的 Apple iOS 裝置) 或 Microsoft 推播通知服務 (MPNS)  (，然後再將其傳送至行動裝置。</span><span class="sxs-lookup"><span data-stu-id="ea121-147">The Mobility Service sends the notification to the cloud-based Push Notification Service, which then sends the notification either to the Apple Push Notification Service (APNS) (for supported Apple iOS devices) or to the Microsoft Push Notification Service (MPNS) (for Windows Phone), which then sends it on to the mobile device.</span></span> <span data-ttu-id="ea121-148">然後，使用者可以在行動裝置上回應通知，以啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="ea121-148">The user can then respond to the notification on the mobile device to activate the application.</span></span>
    
    <span data-ttu-id="ea121-149">Apple 和 Windows Phone 裝置上的 Lync 2010 Mobile 使用推播通知。</span><span class="sxs-lookup"><span data-stu-id="ea121-149">The Lync 2010 Mobile on Apple and Windows Phone devices use push notifications.</span></span> <span data-ttu-id="ea121-150">2013 Lync Server 的 Lync Server 行動用戶端（適用于 Lync Server 2013 的累計更新引進）：2月2013不再使用推播通知或推播通知 PNCH () 。</span><span class="sxs-lookup"><span data-stu-id="ea121-150">The Lync 2013 Mobile client for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer uses push notification or the push notification clearing house (PNCH).</span></span>

<span data-ttu-id="ea121-151">下圖說明推播通知服務如何在使用 UCWA 和 Lync 2013 行動用戶端的 Lync Server 2013 拓撲中容納。</span><span class="sxs-lookup"><span data-stu-id="ea121-151">The following diagram illustrates how the Push Notification Service fits within a Lync Server 2013 topology that uses UCWA and Lync 2013 Mobile clients.</span></span>

<span data-ttu-id="ea121-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span><span class="sxs-lookup"><span data-stu-id="ea121-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span></span>

<span data-ttu-id="ea121-153">在 Lync Server 2010 的累計更新中引進：11月2011，Mcx service 會為 Lync 2010 行動用戶端提供服務。</span><span class="sxs-lookup"><span data-stu-id="ea121-153">Introduced in Cumulative Update for Lync Server 2010: November 2011, the Mcx service provides services to Lync 2010 Mobile clients.</span></span> <span data-ttu-id="ea121-154">下圖說明使用 Mcx 和 Lync 2010 行動用戶端套用至拓撲時的推播通知服務。</span><span class="sxs-lookup"><span data-stu-id="ea121-154">The following diagram illustrates the Push Notification Service as it applies to a topology using Mcx and Lync 2010 Mobile clients.</span></span>

<span data-ttu-id="ea121-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span><span class="sxs-lookup"><span data-stu-id="ea121-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="ea121-156">支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="ea121-156">Supported Topologies</span></span>

<span data-ttu-id="ea121-157">對 Lync Server 2013 套用累計更新：二月份2013新增 UCWA 網頁元件，以支援下列拓撲中的 Lync 2013 行動用戶端功能：</span><span class="sxs-lookup"><span data-stu-id="ea121-157">Applying the Cumulative Updates for Lync Server 2013: February 2013 adds the UCWA web components to support mobility for Lync 2013 Mobile client features in the following topologies:</span></span>

  - <span data-ttu-id="ea121-158">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="ea121-158">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="ea121-159">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="ea121-159">Lync Server 2013 Enterprise Edition</span></span>

<span data-ttu-id="ea121-160">Edge Server 可以是 Lync Server 2010 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="ea121-160">The Edge Server can be a Lync Server 2010 Edge Server.</span></span>

<span data-ttu-id="ea121-161">不含 Lync Server 2013 累計更新的 Lync Server 2013 部署：2月2013將使用 Mcx 行動性服務，而且只能為 Lync 2010 Mobile 提供服務。</span><span class="sxs-lookup"><span data-stu-id="ea121-161">A Lync Server 2013 deployment without the Cumulative Updates for Lync Server 2013: February 2013 will use the Mcx Mobility Service and can provide services only for Lync 2010 Mobile.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ea121-162">在使用具有兩個網路介面的轉送伺服器角色組合的前端伺服器上支援行動服務，但您必須採取適當的步驟來設定介面。</span><span class="sxs-lookup"><span data-stu-id="ea121-162">The Mobility Service is supported on Front End Servers that is collocated with the Mediation Server role with two network interfaces, but you must take appropriate steps to configure the interfaces.</span></span> <span data-ttu-id="ea121-163">您必須將 IP 位址指派給將會以轉送伺服器通訊的特定介面，以及會以前端伺服器進行通訊的網路介面 IP。</span><span class="sxs-lookup"><span data-stu-id="ea121-163">You must assign the IP addresses to the specific interface that will communicate as the Mediation Server, and the network interface IP that will communicate as the Front End Server.</span></span> <span data-ttu-id="ea121-164">您可以在拓撲產生器中，為每個服務選取正確的 IP 位址，而不是使用預設值<STRONG>使用所有設定的 ip 位址</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="ea121-164">You can do this in Topology Builder by selecting the correct IP address for each service, instead of using the default <STRONG>Use all configured IP addresses</STRONG>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ea121-165">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ea121-165">See Also</span></span>


[<span data-ttu-id="ea121-166">在 Lync Server 2013 中規劃外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="ea121-166">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="ea121-167">在 Lync Server 2013 中部署外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="ea121-167">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)  
[<span data-ttu-id="ea121-168">在 Lync Server 2013 中規劃自動探索</span><span class="sxs-lookup"><span data-stu-id="ea121-168">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

