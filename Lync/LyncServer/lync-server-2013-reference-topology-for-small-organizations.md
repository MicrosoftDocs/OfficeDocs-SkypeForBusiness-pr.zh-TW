---
title: 適用于小型組織的 Lync Server 2013 參考拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e0171d9678d5d890cf4ecb81f6de25f9b558b05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a><span data-ttu-id="33009-102">小型組織中 Lync Server 2013 的參照拓撲</span><span class="sxs-lookup"><span data-stu-id="33009-102">Reference topology for Lync Server 2013 in small organizations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33009-103">_**主題上次修改日期：** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="33009-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="33009-104">小型組織的參考拓朴顯示如何只部署三台伺服器來執行 Lync Server，以部署強健、高可用性的解決方案。</span><span class="sxs-lookup"><span data-stu-id="33009-104">The reference topology for small organizations shows how you can deploy a robust, highly available solution by deploying only three servers running Lync Server.</span></span>

<span data-ttu-id="33009-105">**小型組織的參照拓撲**</span><span class="sxs-lookup"><span data-stu-id="33009-105">**Reference topology for small organizations**</span></span>

<span data-ttu-id="33009-106">![部署三個伺服器圖表的參考拓撲](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "部署三個伺服器圖表的參考拓撲")</span><span class="sxs-lookup"><span data-stu-id="33009-106">![Reference topology deploying three servers diagram](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Reference topology deploying three servers diagram")</span></span>

  - <span data-ttu-id="33009-107">**部署這個組織的一組標準版伺服器**   在其中央網站上有4000使用者。</span><span class="sxs-lookup"><span data-stu-id="33009-107">**Pair of Standard Edition Servers Deployed**    This organization has 4,000 users at their central site.</span></span> <span data-ttu-id="33009-108">組織已部署兩個標準版伺服器並成對搭配，以啟用高可用性和災害復原。</span><span class="sxs-lookup"><span data-stu-id="33009-108">The organization has deployed two Standard Edition servers and paired them together to enable high availability and disaster recovery.</span></span> <span data-ttu-id="33009-109">每個伺服器住房2000使用者，但所有使用者的相關資訊都會在兩個伺服器之間同步處理。</span><span class="sxs-lookup"><span data-stu-id="33009-109">Each server homes 2,000 users, but information about all users is synchronized between the two servers.</span></span> <span data-ttu-id="33009-110">如果其中一個是關閉的，系統管理員可以將這些使用者的服務容錯移轉到其他伺服器，並將使用者的中斷降至最低。</span><span class="sxs-lookup"><span data-stu-id="33009-110">If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users.</span></span> <span data-ttu-id="33009-111">如需有關 Lync Server 2013 中高可用性與災害復原功能的詳細資訊，請參閱[在 Lync server 2013 中規劃高可用性和災難](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)復原。</span><span class="sxs-lookup"><span data-stu-id="33009-111">For more information about high availability and disaster recovery features in Lync Server 2013, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="33009-112">**建議使用 Edge 伺服器部署。**   雖然內部 IM、目前狀態與會議不需要部署邊緣伺服器，但我們建議您即使小型部署也一樣。</span><span class="sxs-lookup"><span data-stu-id="33009-112">**Edge Server deployment is recommended.**   Although deploying an Edge Server is not required for internal IM, presence and conferencing, we recommend it even for small deployments.</span></span> <span data-ttu-id="33009-113">您可以部署 Edge 伺服器來將您的 Lync 伺服器投資最大化，為目前組織防火牆以外的使用者提供服務。</span><span class="sxs-lookup"><span data-stu-id="33009-113">You can maximize your Lync Server investment by deploying an Edge Server to provide service to users currently outside your organization’s firewalls.</span></span> <span data-ttu-id="33009-114">其優點包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="33009-114">The benefits include the following:</span></span>
    
      - <span data-ttu-id="33009-115">貴組織的使用者可以使用 Lync Server 的功能（如果他們在家中或在路上）。</span><span class="sxs-lookup"><span data-stu-id="33009-115">Your organization’s own users can use Lync Server functionality, if they are working from home or are out on the road.</span></span>
    
      - <span data-ttu-id="33009-116">您的使用者可以邀請外部使用者參與會議。</span><span class="sxs-lookup"><span data-stu-id="33009-116">Your users can invite outside users to participate in meetings.</span></span>
    
      - <span data-ttu-id="33009-117">如果您有合作夥伴、廠商或客戶組織，且使用 Lync Server，您可以建立與該組織的*聯盟關聯*。</span><span class="sxs-lookup"><span data-stu-id="33009-117">If you have a partner, vendor or customer organization that also uses Lync Server, you can form a *federated relationship* with that organization.</span></span> <span data-ttu-id="33009-118">接著，您的 Lync Server 部署會辨識來自該同盟組織的使用者，以更好的方式共同作業。</span><span class="sxs-lookup"><span data-stu-id="33009-118">Your Lync Server deployment would then recognize users from that federated organization, leading to better collaboration.</span></span>
    
      - <span data-ttu-id="33009-119">您的使用者可以與公用 IM 服務的使用者交換立即訊息，包括下列任一或所有專案： Windows Live、AOL、Yahoo\!和 Google 交談。</span><span class="sxs-lookup"><span data-stu-id="33009-119">Your users can exchange instant messages with users of public IM services, including any or all of the following: Windows Live, AOL, Yahoo\!, and Google Talk.</span></span> <span data-ttu-id="33009-120">您可能需要使用這些服務的公用 IM 連線的個別授權。</span><span class="sxs-lookup"><span data-stu-id="33009-120">A separate license might be required for public IM connectivity with these services.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P><span data-ttu-id="33009-121">從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。</span><span class="sxs-lookup"><span data-stu-id="33009-121">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="33009-122">擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟</span><span class="sxs-lookup"><span data-stu-id="33009-122">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="33009-123">信使，直到服務關閉日期為止。</span><span class="sxs-lookup"><span data-stu-id="33009-123">Messenger until the service shut down date.</span></span> <span data-ttu-id="33009-124">AOL 和 Yahoo！的存留期結束日期為2014年6月</span><span class="sxs-lookup"><span data-stu-id="33009-124">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="33009-125">已公佈。</span><span class="sxs-lookup"><span data-stu-id="33009-125">has been announced.</span></span> <span data-ttu-id="33009-126">如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</span><span class="sxs-lookup"><span data-stu-id="33009-126">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="33009-127">PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權</span><span class="sxs-lookup"><span data-stu-id="33009-127">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="33009-128">名單.</span><span class="sxs-lookup"><span data-stu-id="33009-128">Messenger.</span></span> <span data-ttu-id="33009-129">Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</span><span class="sxs-lookup"><span data-stu-id="33009-129">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="33009-130">Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。</span><span class="sxs-lookup"><span data-stu-id="33009-130">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="33009-131">與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="33009-131">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="33009-132">您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="33009-132">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

        
        </div>

  - <span data-ttu-id="33009-133">**分支網站的留存能力。**   這個組織正在執行 Lync Server 企業語音功能的試驗程式。</span><span class="sxs-lookup"><span data-stu-id="33009-133">**Branch site survivability.**   This organization is running a pilot program of the Enterprise Voice feature of Lync Server.</span></span> <span data-ttu-id="33009-134">有些使用者使用 Lync Server 作為其唯一的語音方案。</span><span class="sxs-lookup"><span data-stu-id="33009-134">Some users are using Lync Server as their sole voice solution.</span></span> <span data-ttu-id="33009-135">有些語音試驗使用者位於分支網站上。</span><span class="sxs-lookup"><span data-stu-id="33009-135">Some of these Voice pilot users are located at the branch site.</span></span> <span data-ttu-id="33009-136">分支網站沒有可靠的廣域網路（WAN）連結到中央網站，所以會在該處部署 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="33009-136">The branch site does not have a reliable wide area network (WAN) link to the central site, so a Survivable Branch Appliance is deployed there.</span></span> <span data-ttu-id="33009-137">在已部署的情況下，如果 WAN 連結關閉，分支網站上的使用者仍可撥打及接聽電話（在組織和 PSTN 通話中的呼叫）、擁有語音信箱功能，以及與雙方的立即訊息（IM）進行通訊。</span><span class="sxs-lookup"><span data-stu-id="33009-137">With this deployed, if the WAN link goes down, users at the branch site can still make and receive calls (both calls within the organization and PSTN calls), have voice mail functionality, and communicate with two-party instant messaging (IM).</span></span> <span data-ttu-id="33009-138">使用者也可以在 WAN 連結無法使用時進行驗證。</span><span class="sxs-lookup"><span data-stu-id="33009-138">Users can also be authenticated when the WAN link is unavailable as well.</span></span>

  - <span data-ttu-id="33009-139">**Exchange UM 部署。**</span><span class="sxs-lookup"><span data-stu-id="33009-139">**Exchange UM deployment.**</span></span> <span data-ttu-id="33009-140">這個參照拓撲包含 Exchange 整合通訊（UM）伺服器，該伺服器會執行 Microsoft Exchange Server，而不是 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="33009-140">This reference topology includes an Exchange Unified Messaging (UM) Server, which runs Microsoft Exchange Server, not Lync Server.</span></span>
    
    <span data-ttu-id="33009-141">如需有關 Exchange UM 的詳細資訊，請參閱規劃檔中的 lync server [2013 中的 Exchange 整合訊息整合規劃](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)（ [lync server 2013 中的託管 exchange](lync-server-2013-hosted-exchange-unified-messaging-integration.md)整合訊息整合）。</span><span class="sxs-lookup"><span data-stu-id="33009-141">For details about Exchange UM, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="33009-142">**Office Web Apps 伺服器。**</span><span class="sxs-lookup"><span data-stu-id="33009-142">**Office Web Apps Server.**</span></span> <span data-ttu-id="33009-143">我們建議您在使用 Web 會議的每一個組織中部署 Office Web Apps Server 或 Office Web Apps 伺服器群。</span><span class="sxs-lookup"><span data-stu-id="33009-143">We recommend deploying an Office Web Apps Server or Office Web Apps Server farm in every organization that uses web conferencing.</span></span> <span data-ttu-id="33009-144">Office Web Apps 伺服器可讓 PowerPoint 投影片呈現在網路會議中。</span><span class="sxs-lookup"><span data-stu-id="33009-144">Office Web Apps Server makes it possible for PowerPoint slides to be presented in web conferences.</span></span> <span data-ttu-id="33009-145">如需詳細資訊，請參閱設定[與 Office Web Apps server 和 Lync server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="33009-145">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

