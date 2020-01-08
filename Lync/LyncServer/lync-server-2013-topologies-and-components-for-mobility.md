---
title: Lync Server 2013：行動性的拓撲和元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 537eda14f2587e06bd8a1112f2a6a44299b0b78e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a><span data-ttu-id="6c485-102">Lync Server 2013 中的行動性的拓撲和元件</span><span class="sxs-lookup"><span data-stu-id="6c485-102">Topologies and components for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c485-103">_**主題上次修改日期：** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="6c485-103">_**Topic Last Modified:** 2013-02-17_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="6c485-104">為了支援行動裝置上的 Lync mobile 應用程式，Lync Server 2013 提供三種服務： Lync Server 2013 Mcx 行動服務、Lync Server 2013 自動探索服務，以及 Lync Server 2013 推播通知服務。</span><span class="sxs-lookup"><span data-stu-id="6c485-104">To support Lync mobile applications on mobile devices, Lync Server 2013 provides three services: Lync Server 2013 Mcx Mobility Service, Lync Server 2013 Autodiscover Service, and Lync Server 2013 Push Notification Service.</span></span> <span data-ttu-id="6c485-105">Lync Server 2013 的累積更新：2月2013新增免費的、高級的 Lync 2013 行動用戶端服務-透過使用整合通訊網頁 API 或 UCWA 的行動支援。</span><span class="sxs-lookup"><span data-stu-id="6c485-105">The Cumulative Updates for Lync Server 2013: February 2013 adds a complimentary, but advanced, service for Lync 2013 Mobile clients—mobility support through the use of the Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="6c485-106">本節簡要說明這些元件，並識別支援行動性的 Lync Server 2013 拓撲。</span><span class="sxs-lookup"><span data-stu-id="6c485-106">This section briefly describes these components and identifies the Lync Server 2013 topologies that support mobility.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6c485-107">您也可以在混合式部署中使用行動服務。</span><span class="sxs-lookup"><span data-stu-id="6c485-107">Mobility services are also available in hybrid deployments.</span></span> <span data-ttu-id="6c485-108">如果您的使用者在線上，您就不需要部署支援行動性的服務。</span><span class="sxs-lookup"><span data-stu-id="6c485-108">You are not required to deploy services for supporting mobility if your users are homed online.</span></span> <span data-ttu-id="6c485-109">您必須定義自動探索服務的設定，才能讓行動使用者尋找其線上身分識別。</span><span class="sxs-lookup"><span data-stu-id="6c485-109">You do need to define a setting for the Autodiscover Service to enable mobile users to find their online identity.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6c485-110">如果您打算規劃任何外部使用者連線（例如，同盟、外部使用者存取或行動功能），您必須使用 Edge 伺服器搭配標準版 server 和前端伺服器或前端池。</span><span class="sxs-lookup"><span data-stu-id="6c485-110">If you are planning any external user connectivity (for example, federation, external user access, or mobility features), you must use Edge Servers with Standard Edition server and the Front End Server or Front End pool.</span></span> <span data-ttu-id="6c485-111">標準版伺服器和 [前端伺服器] 或 [前端] 池沒有必要的元件可讓外部使用者存取您的內部部署，或用於內部部署與外部使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="6c485-111">The Standard Edition server and the Front End Server or Front End pool do not have the necessary components to enable external users to access your internal deployment, or for the internal deployment to communicate with your external users.</span></span> <span data-ttu-id="6c485-112">針對所有案例，包括與內部使用者共同作業或溝通的外部使用者（包括行動性），您必須部署至少一個 Edge 伺服器和一個反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="6c485-112">For all scenarios that include external users collaborating or communicating with internal users, including mobility, you must deploy at least one Edge Server and one reverse proxy.</span></span><BR><span data-ttu-id="6c485-113"><EM>推播通知</EM>使用 Lync Online 服務的同盟類型，該類型會託管推播通知交換房屋（PNCH）。</span><span class="sxs-lookup"><span data-stu-id="6c485-113"><EM>Push notification</EM> uses a type of federation to the Lync Online services, which hosts the Push Notification Clearing House (PNCH).</span></span> <span data-ttu-id="6c485-114">推播通知指的是當行動裝置處於非使用中時，由應用程式推送給 Apple iPhone、iPad 和 Windows Phone 的音效通知、螢幕警示（文字）和徽章。</span><span class="sxs-lookup"><span data-stu-id="6c485-114">Push notification refers to the sound alerts, on-screen alerts (text), and badges that are pushed by applications to the Apple iPhone, iPad, and Windows Phone, when the mobile device is inactive.</span></span> <span data-ttu-id="6c485-115">PNCH 從 Lync Server 接收推播通知。</span><span class="sxs-lookup"><span data-stu-id="6c485-115">PNCH receives push notifications from Lync Server.</span></span> <span data-ttu-id="6c485-116">當 PNCH 收到訊息的通知時，PNCH 會根據訊息所針對的行動用戶端，透過 Apple 推播通知服務或 Lync Server 2013 推播通知服務，將通知轉寄給行動用戶端。</span><span class="sxs-lookup"><span data-stu-id="6c485-116">When PNCH receives a notification of a message, PNCH forwards a notification to mobile clients through either the Apple Push Notification Services or Lync Server 2013 Push Notification Service, based on the mobile client that the message is intended for.</span></span> <span data-ttu-id="6c485-117">PNCH 是這些行動用戶端所需的服務。</span><span class="sxs-lookup"><span data-stu-id="6c485-117">PNCH is a required service for these mobile clients.</span></span> <span data-ttu-id="6c485-118">若要與 Lync Online 聯盟，PNCH 會使用 Edge 伺服器與憑證來確保機密性與驗證、原則，以及正確設定的網域名稱系統（DNS）記錄。</span><span class="sxs-lookup"><span data-stu-id="6c485-118">To federate to Lync Online, PNCH uses Edge Servers and certificates to ensure confidentiality and authentication, policies, and correctly configured domain name system (DNS) records.</span></span> <span data-ttu-id="6c485-119">Nokia Symbian 及 Android 版 Lync Mobile 用戶端不使用 PNCH。</span><span class="sxs-lookup"><span data-stu-id="6c485-119">Nokia Symbian and Android-based Lync Mobile clients do not use PNCH.</span></span> <span data-ttu-id="6c485-120">如需規劃及部署邊緣伺服器的詳細資料，請參閱在 lync server <A href="lync-server-2013-planning-for-external-user-access.md">2013 中規劃外部使用者存取</A>，以及<A href="lync-server-2013-deploying-external-user-access.md">在 lync Server 2013 中部署外部使用者存取</A>。</span><span class="sxs-lookup"><span data-stu-id="6c485-120">For details about planning and deploying Edge Servers, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A> and <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="6c485-121">適用于 Apple 裝置的 Lync 2013 行動用戶端，其中包含 Lync Server 2013 的累積更新：年2月2013不再使用推播通知或推播通知內部（PNCH）。</span><span class="sxs-lookup"><span data-stu-id="6c485-121">The Lync 2013 Mobile clients for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer use push notification or the push notification clearing house (PNCH).</span></span> <span data-ttu-id="6c485-122">Windows Phone 上的 Lync 2013 行動用戶端仍在使用推播通知和（PNCH）。</span><span class="sxs-lookup"><span data-stu-id="6c485-122">Lync 2013 Mobile clients on Windows Phone still use push notification and the (PNCH).</span></span>



</div>

<div>

## <a name="mobility-components"></a><span data-ttu-id="6c485-123">行動元件</span><span class="sxs-lookup"><span data-stu-id="6c485-123">Mobility Components</span></span>

<span data-ttu-id="6c485-124">支援行動性的服務如下所示：</span><span class="sxs-lookup"><span data-stu-id="6c485-124">The services that support mobility are as follows:</span></span>

  - <span data-ttu-id="6c485-125">**Lync server 2013 整合通訊 Web API （UCWA）**   可在 Lync Server 2013 中提供即時通訊與行動裝置和 Web 用戶端的服務。</span><span class="sxs-lookup"><span data-stu-id="6c485-125">**Lync Server 2013 Unified Communications Web API (UCWA)**   Provides services for real-time communications with mobile and web clients in Lync Server 2013.</span></span> <span data-ttu-id="6c485-126">當您部署 Lync Server 2013 的累積更新時：2月2013到前端伺服器和控制器，安裝會在內部和外部 web 服務（Ucwa）中建立一個虛擬目錄。</span><span class="sxs-lookup"><span data-stu-id="6c485-126">When you deploy the Cumulative Updates for Lync Server 2013: February 2013 to the Front End Server and Director, the installation creates a virtual directory in the internal and external web services (Ucwa).</span></span> <span data-ttu-id="6c485-127">屬於 Ucwa 虛擬目錄的網頁元件接受來自 UCWA 的用戶端的呼叫。</span><span class="sxs-lookup"><span data-stu-id="6c485-127">A web component that is part of the Ucwa virtual directory accepts calls from UCWA-enabled clients.</span></span> <span data-ttu-id="6c485-128">用戶端應用程式會在 REST 介面進行通訊，以取得目前狀態、連絡人、立即訊息、VoIP、視訊會議及共同作業。</span><span class="sxs-lookup"><span data-stu-id="6c485-128">The client apps communicate over a REST interface for presence, contacts, instant messaging, VoIP, video conferencing, and collaboration.</span></span> <span data-ttu-id="6c485-129">UCWA 使用 P-取得的通道來傳送事件，例如撥入通話、內送立即訊息，或是傳送給用戶端應用程式的訊息。</span><span class="sxs-lookup"><span data-stu-id="6c485-129">UCWA uses a P-GET based channel to send events, such as an incoming call, incoming instant message, or a message to the client app.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6c485-130">[ <EM>REST</EM> ] 或 [representational 狀態傳輸] 是一種軟體結構樣式，適用于廣泛採用許多形式的分散式系統，且很適合一般的 Web 服務需求。</span><span class="sxs-lookup"><span data-stu-id="6c485-130"><EM>REST</EM> or representational state transfer, is a software architectural style for distributed systems that has been widely adopted in many forms and is well suited to the requirements of Web services in general.</span></span>

    
    </div>

  - <span data-ttu-id="6c485-131">**Lync Server 2013 行動服務（Mcx）**   此服務支援在行動裝置上進行 Lync 功能，例如立即訊息（IM）、目前狀態和連絡人。</span><span class="sxs-lookup"><span data-stu-id="6c485-131">**Lync Server 2013 Mobility Service (Mcx)**   This service supports Lync functionality, such as instant messaging (IM), presence, and contacts, on mobile devices.</span></span> <span data-ttu-id="6c485-132">行動服務是在每個要支援行動裝置上的 Lync 功能的每個池中，都安裝在每個前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="6c485-132">The Mobility Service is installed on every Front End Server in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="6c485-133">當您安裝 Lync Server 2013 時，會在內部網站和前端伺服器上的外部網站下建立新的虛擬目錄（Mcx）。</span><span class="sxs-lookup"><span data-stu-id="6c485-133">When you install Lync Server 2013, a new virtual directory (Mcx) is created under both the internal website and the external website on your Front End Servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6c485-134">Lync server 2013 使用 Lync Server 2013 的累積更新：2月2013支援 Lync Server 2010 的累積更新中所引入的行動服務：2011年11月的，以及 UCWA 網頁元件。</span><span class="sxs-lookup"><span data-stu-id="6c485-134">Lync Server 2013 with the Cumulative Updates for Lync Server 2013: February 2013 supports both the Mobility service introduced in the Cumulative Update for Lync Server 2010: November 2011, commonly known as Mcx, and the UCWA web component.</span></span> <span data-ttu-id="6c485-135">這兩種行動服務的組合提供在 Lync Server 2013 上使用 Lync 2010 行動裝置和 Lync 2013 行動用戶端的使用者互通性與使用。</span><span class="sxs-lookup"><span data-stu-id="6c485-135">The combination of these two mobility services provides interoperability and use by users with Lync 2010 Mobile and Lync 2013 Mobile clients on Lync Server 2013.</span></span>

    
    </div>

  - <span data-ttu-id="6c485-136">**Lync server 2013 自動探索服務**   ：此服務會識別使用者的位置，並讓行動裝置和其他 lync 用戶端找出資源，例如 Lync Server 2013 Web 服務的內部和外部 url，以及 Mcx 或 UCWA 的 URL （無論網路位置為何）。</span><span class="sxs-lookup"><span data-stu-id="6c485-136">**Lync Server 2013 Autodiscover Service**   This service identifies the location of the user and enables mobile devices and other Lync clients to locate resources—such as the internal and external URLs for Lync Server 2013 Web Services, and the URL for the Mcx or UCWA—regardless of network location.</span></span> <span data-ttu-id="6c485-137">自動搜尋使用硬式編碼主機名稱（lyncdiscoverinternal 網路中的使用者，lyncdiscover 網路外部使用者）和使用者的 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="6c485-137">Automatic discovery uses hardcoded host names (lyncdiscoverinternal for users inside the network; lyncdiscover for users outside the network) and the SIP domain of the user.</span></span> <span data-ttu-id="6c485-138">它支援使用 HTTP 或 HTTPS 的用戶端連線。</span><span class="sxs-lookup"><span data-stu-id="6c485-138">It supports client connections that use either HTTP or HTTPS.</span></span>
    
    <span data-ttu-id="6c485-139">自動探索服務會安裝在每個前端伺服器上，以及每個要支援行動裝置上的 Lync 功能的每個池中的每個控制器上。</span><span class="sxs-lookup"><span data-stu-id="6c485-139">The Autodiscover Service is installed on every Front End Server and on every Director in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="6c485-140">當您安裝自動探索服務時，會在內部網站和外部網站（在前端伺服器與控制器）底下建立新的虛擬目錄（自動探索）。</span><span class="sxs-lookup"><span data-stu-id="6c485-140">When you install the Autodiscover Service, a new virtual directory (Autodiscover) is created under both the internal website and the external website, on both Front End Servers and Directors.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6c485-141">[自動探索服務] 會在這裡列出，因為它在提供行動用戶端服務時會一直是一個重要的元件。</span><span class="sxs-lookup"><span data-stu-id="6c485-141">The Autodiscover Service is listed here because it remains a critical component when providing mobile client services.</span></span> <span data-ttu-id="6c485-142">已展開 Lync Server 2013 中的自動探索角色，以便為所有用戶端提供服務。</span><span class="sxs-lookup"><span data-stu-id="6c485-142">The role of Autodiscover in Lync Server 2013 has been expanded to provide services for all clients.</span></span> <span data-ttu-id="6c485-143">如需規劃自動探索服務的詳細資料，請參閱<A href="lync-server-2013-planning-for-autodiscover.md">在 Lync Server 2013 中規劃自動</A>探索。</span><span class="sxs-lookup"><span data-stu-id="6c485-143">For details about planning for the Autodiscover Service, see <A href="lync-server-2013-planning-for-autodiscover.md">Planning for Autodiscover in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="6c485-144">**推播通知服務**   ：此服務是位於 Lync Online 資料中心的雲端服務。</span><span class="sxs-lookup"><span data-stu-id="6c485-144">**Push Notification Service**   This service is a cloud-based service that is located in the Lync Online data center.</span></span> <span data-ttu-id="6c485-145">當支援的 Apple iOS 裝置或 Windows Phone 上的 Lync 行動裝置應用程式在非使用中時，它無法回應新的事件，例如新的立即訊息（IM）邀請、未接的立即訊息、未接來電或語音信箱，因為這些裝置不支援在背景中執行的行動應用程式。</span><span class="sxs-lookup"><span data-stu-id="6c485-145">When the Lync mobile application on a supported Apple iOS device or Windows Phone is inactive, it cannot respond to new events, such as a new instant messaging (IM) invitation, a missed instant message, a missed call, or voice mail, because these devices do not support mobile applications running in the background.</span></span> <span data-ttu-id="6c485-146">在這些情況下，會將新事件（稱為推播*通知*）通知傳送到行動裝置。</span><span class="sxs-lookup"><span data-stu-id="6c485-146">In these cases, a notification of the new event—called a *push notification*—is sent to the mobile device.</span></span> <span data-ttu-id="6c485-147">行動服務會傳送通知給雲端型推播通知服務，然後將通知傳送至 Apple 推播通知服務（APNS）（針對支援的 Apple iOS 裝置）或 Microsoft 推播通知服務（MPNS）。）（適用于 Windows Phone），然後將它傳送到行動裝置。</span><span class="sxs-lookup"><span data-stu-id="6c485-147">The Mobility Service sends the notification to the cloud-based Push Notification Service, which then sends the notification either to the Apple Push Notification Service (APNS) (for supported Apple iOS devices) or to the Microsoft Push Notification Service (MPNS) (for Windows Phone), which then sends it on to the mobile device.</span></span> <span data-ttu-id="6c485-148">然後，使用者就可以在行動裝置上回應通知，以啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="6c485-148">The user can then respond to the notification on the mobile device to activate the application.</span></span>
    
    <span data-ttu-id="6c485-149">Apple 和 Windows Phone 裝置上的 Lync 2010 Mobile 使用推播通知。</span><span class="sxs-lookup"><span data-stu-id="6c485-149">The Lync 2010 Mobile on Apple and Windows Phone devices use push notifications.</span></span> <span data-ttu-id="6c485-150">適用于 Apple 裝置的 Lync 2013 行動用戶端，其中包含 Lync Server 2013 的累積更新：年2月2013不再使用推播通知或推播清除房屋（PNCH）。</span><span class="sxs-lookup"><span data-stu-id="6c485-150">The Lync 2013 Mobile client for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer uses push notification or the push notification clearing house (PNCH).</span></span>

<span data-ttu-id="6c485-151">下圖說明推播通知服務在使用 UCWA 和 Lync 2013 行動用戶端的 Lync Server 2013 拓撲中的相符程度。</span><span class="sxs-lookup"><span data-stu-id="6c485-151">The following diagram illustrates how the Push Notification Service fits within a Lync Server 2013 topology that uses UCWA and Lync 2013 Mobile clients.</span></span>

<span data-ttu-id="6c485-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span><span class="sxs-lookup"><span data-stu-id="6c485-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span></span>

<span data-ttu-id="6c485-153">在 Lync Server 2010 的累加更新中引入2011： Mcx 服務提供給 Lync 2010 行動用戶端的服務。</span><span class="sxs-lookup"><span data-stu-id="6c485-153">Introduced in Cumulative Update for Lync Server 2010: November 2011, the Mcx service provides services to Lync 2010 Mobile clients.</span></span> <span data-ttu-id="6c485-154">下圖說明使用 Mcx 和 Lync 2010 行動用戶端的拓撲結構時，推播通知服務。</span><span class="sxs-lookup"><span data-stu-id="6c485-154">The following diagram illustrates the Push Notification Service as it applies to a topology using Mcx and Lync 2010 Mobile clients.</span></span>

<span data-ttu-id="6c485-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span><span class="sxs-lookup"><span data-stu-id="6c485-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="6c485-156">支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="6c485-156">Supported Topologies</span></span>

<span data-ttu-id="6c485-157">套用 Lync Server 2013 的累積更新：2013年2月新增 UCWA 網頁元件，以支援 Lync 2013 行動用戶端功能在下列拓撲中的行動：</span><span class="sxs-lookup"><span data-stu-id="6c485-157">Applying the Cumulative Updates for Lync Server 2013: February 2013 adds the UCWA web components to support mobility for Lync 2013 Mobile client features in the following topologies:</span></span>

  - <span data-ttu-id="6c485-158">Lync Server 2013 標準版</span><span class="sxs-lookup"><span data-stu-id="6c485-158">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="6c485-159">Lync Server 2013 企業版</span><span class="sxs-lookup"><span data-stu-id="6c485-159">Lync Server 2013 Enterprise Edition</span></span>

<span data-ttu-id="6c485-160">Edge 伺服器可以是 Lync Server 2010 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="6c485-160">The Edge Server can be a Lync Server 2010 Edge Server.</span></span>

<span data-ttu-id="6c485-161">不含 Lync Server 2013 累計更新的 Lync Server 2013 部署：2月2013將使用 Mcx 行動服務，且只能為 Lync 2010 Mobile 提供服務。</span><span class="sxs-lookup"><span data-stu-id="6c485-161">A Lync Server 2013 deployment without the Cumulative Updates for Lync Server 2013: February 2013 will use the Mcx Mobility Service and can provide services only for Lync 2010 Mobile.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6c485-162">Collocated 前端伺服器支援行動服務，而該伺服器擁有兩個網路介面的中繼伺服器角色，但您必須採取適當的步驟來設定介面。</span><span class="sxs-lookup"><span data-stu-id="6c485-162">The Mobility Service is supported on Front End Servers that is collocated with the Mediation Server role with two network interfaces, but you must take appropriate steps to configure the interfaces.</span></span> <span data-ttu-id="6c485-163">您必須將 IP 位址指派給將作為中繼伺服器通訊的特定介面，以及將通訊為前端伺服器的網路介面 IP。</span><span class="sxs-lookup"><span data-stu-id="6c485-163">You must assign the IP addresses to the specific interface that will communicate as the Mediation Server, and the network interface IP that will communicate as the Front End Server.</span></span> <span data-ttu-id="6c485-164">您可以在拓撲建立器中，為每個服務選取正確的 IP 位址，而不是使用預設的 [<STRONG>使用所有已設定的 ip 位址</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="6c485-164">You can do this in Topology Builder by selecting the correct IP address for each service, instead of using the default <STRONG>Use all configured IP addresses</STRONG>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6c485-165">請參閱</span><span class="sxs-lookup"><span data-stu-id="6c485-165">See Also</span></span>


[<span data-ttu-id="6c485-166">在 Lync Server 2013 中規劃外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="6c485-166">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="6c485-167">在 Lync Server 2013 中部署外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="6c485-167">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)  
[<span data-ttu-id="6c485-168">規劃 Lync Server 2013 中的自動探索</span><span class="sxs-lookup"><span data-stu-id="6c485-168">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

