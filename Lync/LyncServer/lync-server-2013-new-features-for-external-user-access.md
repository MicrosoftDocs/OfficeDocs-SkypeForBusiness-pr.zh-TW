---
title: Lync Server 2013：外部使用者存取的新功能
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
ms.openlocfilehash: 43df9901b7bac37bb812eeb00c54537151496eb7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534310"
---
# <a name="new-features-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="fafc4-102">Lync Server 2013 中外部使用者存取的新功能</span><span class="sxs-lookup"><span data-stu-id="fafc4-102">New features for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fafc4-103">_**主題上次修改日期：** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="fafc4-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="fafc4-104">Lync Server 2013 引進新功能，可擴充使用者的功能和通訊方法。</span><span class="sxs-lookup"><span data-stu-id="fafc4-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="fafc4-105">另外，Lync Server 2013 也會引入現有服務的變更，以更好地整合及擴充組織可使用的服務。</span><span class="sxs-lookup"><span data-stu-id="fafc4-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="fafc4-106">下列摘要會影響您規劃和部署 Lync Server 2013 Edge Server 服務的變更。</span><span class="sxs-lookup"><span data-stu-id="fafc4-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

  - <span data-ttu-id="fafc4-107">**支援 IPv6 定址**    Lync Server 2013 支援所有 Edge Server 服務的 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="fafc4-107">**Support for IPv6 addressing**   Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="fafc4-108">如果您已在 Windows Server 中透過設定提供介面的 IPv6 位址，您可以透過 [拓撲產生器] 中的 IP 位址設定，使用 Edge Server 設定中的 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="fafc4-108">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fafc4-109">在 Lync Server 2013 中使用 IPv6 位址，取決於您的組織部署的路由器和防火牆中的 IPv6 支援，以及透過網際網路服務提供者的支援。</span><span class="sxs-lookup"><span data-stu-id="fafc4-109">Use of IPv6 addresses in Lync Server 2013 depends on support of IPv6 in routers and firewalls that your organization deploys, as well as support through your Internet service provider.</span></span>

    
    </div>

  - <span data-ttu-id="fafc4-110">可延伸\*\*的訊息和顯示狀態通訊協定 (XMPP) \*\*    Lync Server 2013 引進在 Edge server 上部署的完整整合式 XMPP proxy () 以及在前端伺服器上部署的 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="fafc4-110">**Extensible Messaging and Presence Protocol (XMPP)**   Lync Server 2013 introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway deployed on your Front End Servers.</span></span> <span data-ttu-id="fafc4-111">您可部署 XMPP 同盟作為選用元件。</span><span class="sxs-lookup"><span data-stu-id="fafc4-111">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="fafc4-112">新增及設定 XMPP proxy 和 XMPP 閘道，可讓您的 Microsoft Lync 2013 使用者新增來自 XMPP 的合作夥伴的連絡人，以進行立即訊息 (IM) 及顯示狀態。</span><span class="sxs-lookup"><span data-stu-id="fafc4-112">Adding and configuring the XMPP proxy and XMPP gateway will allow your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fafc4-113">目前，Lync Server 2013 中的 XMPP 服務只會在 Lync 用戶端和以 XMPP 為基礎的連絡人之間提供立即訊息和目前狀態。</span><span class="sxs-lookup"><span data-stu-id="fafc4-113">Currently, the XMPP services in Lync Server 2013 only provide instant messaging and presence between Lync clients and XMPP-based contacts.</span></span>

    
    </div>

  - <span data-ttu-id="fafc4-114">**行動用戶端**     的行動服務在 Lync Server 2010 的客戶更新中引進，Lync Server 2013 中的行動服務可讓 Microsoft Lync Mobile 用戶端在行動電話和平板電腦裝置上使用支援的 Apple iOS、Android、Windows Phone 或 Nokia 行動裝置執行這類活動，例如傳送和接收立即訊息、查看連絡人及查看顯示狀態。</span><span class="sxs-lookup"><span data-stu-id="fafc4-114">**Mobility services for Mobile clients**   Introduced in a customer update for Lync Server 2010, Mobility services in Lync Server 2013 allow Microsoft Lync Mobile clients on mobile phones and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform such activities as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="fafc4-115">此外，行動裝置也支援某些企業語音功能，例如按一下以加入會議、呼叫透過工作、單一號碼到達、語音信箱及未接來電通知。</span><span class="sxs-lookup"><span data-stu-id="fafc4-115">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fafc4-116">行動性服務使用前端伺服器中部署的反向 Proxy 和發佈的服務。</span><span class="sxs-lookup"><span data-stu-id="fafc4-116">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="fafc4-117">Edge Server 不需要進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="fafc4-117">No changes are required to Edge Servers.</span></span>

    
    </div>

  - <span data-ttu-id="fafc4-118">**Director 是選用的角色**    Lync Server 2013 拓撲中 Director 伺服器的角色尚未變更。</span><span class="sxs-lookup"><span data-stu-id="fafc4-118">**Directors are an optional role**   The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="fafc4-119">它仍然會主控 web 服務、對傳入的使用者要求進行驗證，並將外部使用者導向其主集區。</span><span class="sxs-lookup"><span data-stu-id="fafc4-119">It still hosts web services, pre-authenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="fafc4-120">將 Director 從建議的角色變更為選用的角色，並不會降低 Director 的價值，但是會強調伺服器計數和其他硬體需求 (例如，Director) 需求的硬體負載平衡器，而不會損除功能和功能。</span><span class="sxs-lookup"><span data-stu-id="fafc4-120">Changing the Director from a recommended role to an optional role does not diminish the value of the Director, but emphasizes reducing server count and other hardware requirements (for example, hardware load balancers for the Director) requirements without compromising features and functionality.</span></span> <span data-ttu-id="fafc4-121">因為前端伺服器可以做與 Director 不會影響之服務的相同工作，所以您可以選擇部署 Director （如果選擇）。</span><span class="sxs-lookup"><span data-stu-id="fafc4-121">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can optionally deploy Directors if you choose to.</span></span> <span data-ttu-id="fafc4-122">您可以放心地排除 Director，前端伺服器將會在其位置提供相同的服務。</span><span class="sxs-lookup"><span data-stu-id="fafc4-122">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in their place.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="fafc4-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fafc4-123">See Also</span></span>


[<span data-ttu-id="fafc4-124">在 Lync Server 2013 中規劃及設定 IPv6</span><span class="sxs-lookup"><span data-stu-id="fafc4-124">Planning for and configuring IPv6 in Lync Server 2013</span></span>](lync-server-2013-planning-for-and-configuring-ipv6.md)  


[<span data-ttu-id="fafc4-125">在 Lync Server 2013 中規劃外部使用者存取</span><span class="sxs-lookup"><span data-stu-id="fafc4-125">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="fafc4-126">在 Lync Server 2013 中規劃可擴展郵件和顯示狀態通訊協定 (XMPP) 同盟</span><span class="sxs-lookup"><span data-stu-id="fafc4-126">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

