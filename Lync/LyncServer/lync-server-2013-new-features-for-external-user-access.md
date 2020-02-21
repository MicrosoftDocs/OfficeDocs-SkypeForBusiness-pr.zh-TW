---
title: 外部使用者存取的 Lync Server 2013： 新功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New features for external user access
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398794(v=OCS.15)
ms:contentKeyID: 48184884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 526daf4359cec022b71476dc4abaa67c52e8409a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-features-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="fa83e-102">Lync Server 2013 中的外部使用者存取的新功能</span><span class="sxs-lookup"><span data-stu-id="fa83e-102">New features for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa83e-103">_**主題上次修改日期：** 2012年-10-17_</span><span class="sxs-lookup"><span data-stu-id="fa83e-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="fa83e-104">Lync Server 2013 引進擴充功能與通訊的方法，為您的使用者的新功能。</span><span class="sxs-lookup"><span data-stu-id="fa83e-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="fa83e-105">此外，Lync Server 2013 引進變更至現有的服務，以更妥善地整合，並擴充可供貴組織的服務。</span><span class="sxs-lookup"><span data-stu-id="fa83e-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="fa83e-106">以下是可能會影響規劃的變更摘要。 與部署的 Lync Server 2013 Edge Server 服務。</span><span class="sxs-lookup"><span data-stu-id="fa83e-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

  - <span data-ttu-id="fa83e-107">**支援 IPv6 定址**   Lync Server 2013 支援 IPv6 定址的所有 Edge Server 服務。</span><span class="sxs-lookup"><span data-stu-id="fa83e-107">**Support for IPv6 addressing**   Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="fa83e-108">如果您已透過 Windows Server 中設定介面提供 IPv6 位址，您可以透過在拓撲產生器的 IP 位址設定 Edge Server 設定中使用 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="fa83e-108">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fa83e-109">Lync Server 2013 中的 IPv6 位址的使用取決於路由器和防火牆，貴組織部署，以及透過網際網路服務提供者支援的 IPv6 支援。</span><span class="sxs-lookup"><span data-stu-id="fa83e-109">Use of IPv6 addresses in Lync Server 2013 depends on support of IPv6 in routers and firewalls that your organization deploys, as well as support through your Internet service provider.</span></span>

    
    </div>

  - <span data-ttu-id="fa83e-110">**可延伸訊息和顯示狀態通訊協定 (XMPP)**   Lync Server 2013 引進 （在 Edge Server 上已部署） 完全整合的 XMPP proxy 及 XMPP 閘道部署在前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="fa83e-110">**Extensible Messaging and Presence Protocol (XMPP)**   Lync Server 2013 introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="fa83e-111">您可部署 XMPP 同盟作為選用元件。</span><span class="sxs-lookup"><span data-stu-id="fa83e-111">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="fa83e-112">新增及設定 XMPP proxy 及 XMPP 閘道將允許 Microsoft Lync 2013 使用者從 XMPP 為基礎的協力廠商的立即訊息 (IM) 和目前狀態新增連絡人。</span><span class="sxs-lookup"><span data-stu-id="fa83e-112">Adding and configuring the XMPP proxy and XMPP gateway will allow your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fa83e-113">目前，Lync Server 2013 中的 XMPP 服務僅提供立即訊息和 Lync 用戶端與 XMPP 型連絡人之間的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="fa83e-113">Currently, the XMPP services in Lync Server 2013 only provide instant messaging and presence between Lync clients and XMPP-based contacts.</span></span>

    
    </div>

  - <span data-ttu-id="fa83e-114">**行動用戶端行動性服務**   Lync Server 2013 中的行動服務客戶更新 Lync Server 2010 中引進，可讓行動電話上的 Microsoft Lync 行動用戶端和平板電腦裝置使用支援的 Apple iOS、 Android、 Windows Phone 或 Nokia 行動裝置，以執行這類活動傳送和接收立即訊息、 檢視連絡人，以及檢視目前狀態。</span><span class="sxs-lookup"><span data-stu-id="fa83e-114">**Mobility services for Mobile clients**   Introduced in a customer update for Lync Server 2010, Mobility services in Lync Server 2013 allow Microsoft Lync Mobile clients on mobile phones and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="fa83e-115">此外，行動裝置支援某些 Enterprise Voice 功能，例如按一下以加入會議，從公司撥號，單一數字到達，語音信箱和未接來電通知。</span><span class="sxs-lookup"><span data-stu-id="fa83e-115">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fa83e-116">行動性服務使用前端伺服器中部署的反向 Proxy 和發佈的服務。</span><span class="sxs-lookup"><span data-stu-id="fa83e-116">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="fa83e-117">Edge Server 不需要進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="fa83e-117">No changes are required to Edge Servers.</span></span>

    
    </div>

  - <span data-ttu-id="fa83e-118">**Director 是選用角色**   後未變更的 Lync Server 2013 拓撲中的 Director 伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="fa83e-118">**Directors are an optional role**   The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="fa83e-119">它仍主控 web 服務、 預先驗證傳入的使用者要求，並指示其主集區的外部使用者。</span><span class="sxs-lookup"><span data-stu-id="fa83e-119">It still hosts web services, pre-authenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="fa83e-120">變更為選用角色從建議角色 Director 不減損 Director 的值，但強調降低伺服器計數，並沒有其他硬體需求 （例如，硬體負載平衡器的 Director） 需求危害特色與功能。</span><span class="sxs-lookup"><span data-stu-id="fa83e-120">Changing the Director from a recommended role to an optional role does not diminish the value of the Director, but emphasizes reducing server count and other hardware requirements (for example, hardware load balancers for the Director) requirements without compromising features and functionality.</span></span> <span data-ttu-id="fa83e-121">因為前端伺服器可以做為不會影響所提供的服務與 Director 的相同工作，您可以選擇性地部署 Director，如果您選擇。</span><span class="sxs-lookup"><span data-stu-id="fa83e-121">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can optionally deploy Directors if you choose to.</span></span> <span data-ttu-id="fa83e-122">安全地可以排除 Director 與前端伺服器將會提供相同的服務，在其位置的信賴度。</span><span class="sxs-lookup"><span data-stu-id="fa83e-122">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in their place.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="fa83e-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fa83e-123">See Also</span></span>


[<span data-ttu-id="fa83e-124">規劃和設定 Lync Server 2013 中的 IPv6</span><span class="sxs-lookup"><span data-stu-id="fa83e-124">Planning for and configuring IPv6 in Lync Server 2013</span></span>](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[<span data-ttu-id="fa83e-125">規劃 Lync Server 2013 中的外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="fa83e-125">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="fa83e-126">可延伸訊息與顯示狀態通訊協定 (XMPP) 同盟 Lync Server 2013 中規劃</span><span class="sxs-lookup"><span data-stu-id="fa83e-126">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

