---
title: 規劃商務用 Skype Server 的會議拓撲
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 摘要：閱讀此主題以瞭解如何在商務用 Skype Server 中規劃會議拓撲。
ms.openlocfilehash: dc7c62d45a2ebd84f38cc67ce996ba0ac72aa794
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814093"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a><span data-ttu-id="49033-103">規劃商務用 Skype Server 的會議拓撲</span><span class="sxs-lookup"><span data-stu-id="49033-103">Plan your conferencing topology for Skype for Business Server</span></span>
 
<span data-ttu-id="49033-104">**摘要：** 閱讀此主題以瞭解如何在商務用 Skype Server 中規劃會議拓撲。</span><span class="sxs-lookup"><span data-stu-id="49033-104">**Summary:** Read this topic to learn about planning your conferencing topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="49033-105">本主題說明商務用 Skype Server 中的會議拓撲基礎：</span><span class="sxs-lookup"><span data-stu-id="49033-105">This topic describes topology basics for conferencing in Skype for Business Server:</span></span>
  
- <span data-ttu-id="49033-106">支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="49033-106">Supported topologies</span></span>
    
- <span data-ttu-id="49033-107">電話撥入式會議考慮</span><span class="sxs-lookup"><span data-stu-id="49033-107">Dial-in conferencing considerations</span></span>
    
- <span data-ttu-id="49033-108">Web 會議考慮</span><span class="sxs-lookup"><span data-stu-id="49033-108">Web conferencing considerations</span></span>
    
- <span data-ttu-id="49033-109">大型會議的需求</span><span class="sxs-lookup"><span data-stu-id="49033-109">Requirements for large meetings</span></span>
    
<span data-ttu-id="49033-110">如需硬體和軟體需求的詳細資訊，請參閱 [商務用 Skype Server 中會議的硬體和軟體需求](hardware-and-software-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="49033-110">For more information about hardware and software requirements, see [Hardware and software requirements for conferencing in Skype for Business Server](hardware-and-software-requirements.md).</span></span>
  
## <a name="supported-topologies"></a><span data-ttu-id="49033-111">支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="49033-111">Supported topologies</span></span>

<span data-ttu-id="49033-112">在商務用 Skype Server 中，執行會議服務的伺服器一定會組合前端伺服器或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="49033-112">In Skype for Business Server, the server running conferencing services is always collocated with the Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="49033-113">當您部署商務用 Skype Server 時，系統會自動部署 IM 會議功能。</span><span class="sxs-lookup"><span data-stu-id="49033-113">When you deploy Skype for Business Server, IM conferencing capabilities are automatically deployed.</span></span> <span data-ttu-id="49033-114">您可以使用拓撲產生器，指定是否要部署 web、音訊和影片 (A/V) 和電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="49033-114">You can specify whether to deploy web, audio and video (A/V), and dial-in conferencing by using the Topology Builder.</span></span> <span data-ttu-id="49033-115">您也可以使用拓撲產生器，將會議新增至現有的部署。</span><span class="sxs-lookup"><span data-stu-id="49033-115">You can also use Topology Builder to add conferencing to an existing deployment.</span></span> <span data-ttu-id="49033-116">如需拓撲基礎和組合案例的詳細資訊，請參閱 [適用于商務用 Skype Server 的拓撲基礎](../../plan-your-deployment/topology-basics/topology-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="49033-116">For details about topology basics and collocation scenarios, see [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md).</span></span>
  
<span data-ttu-id="49033-117">您可以在下列拓撲和設定中部署會議：</span><span class="sxs-lookup"><span data-stu-id="49033-117">You can deploy conferencing in the following topologies and configurations:</span></span>
  
- <span data-ttu-id="49033-118">商務用 Skype Server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="49033-118">Skype for Business Server Standard Edition</span></span>
    
- <span data-ttu-id="49033-119">商務用 Skype Server Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="49033-119">Skype for Business Server Enterprise Edition</span></span>
    
- <span data-ttu-id="49033-120">有或沒有 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="49033-120">With or without Enterprise Voice</span></span>
    
## <a name="dial-in-conferencing-considerations"></a><span data-ttu-id="49033-121">電話撥入式會議考慮</span><span class="sxs-lookup"><span data-stu-id="49033-121">Dial-in conferencing considerations</span></span>

<span data-ttu-id="49033-122">若要部署電話撥入式會議，您必須考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="49033-122">If you are deploying dial-in conferencing, you must consider the following:</span></span>
  
- <span data-ttu-id="49033-123">電話撥入式會議需要轉送伺服器才能在商務用 Skype Server 與 PSTN 閘道之間的某些設定) 中，轉譯 (和媒體，以及在轉送伺服器和 PSTN 閘道之間轉譯信號和媒體的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="49033-123">Dial-in conferencing requires a Mediation Server to translate signaling (and media in some configurations) between Skype for Business Server and the PSTN gateway, and a PSTN gateway to translate signaling and media between the Mediation Server and the PSTN gateway.</span></span>
    
   <span data-ttu-id="49033-124">在設定電話撥入式會議之前，您必須先部署 Enterprise Voice 或轉送伺服器，並至少部署下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="49033-124">Before you can configure dial-in conferencing, you need to deploy either Enterprise Voice or a Mediation Server and at least one of the following:</span></span>
    
  - <span data-ttu-id="49033-125">PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="49033-125">PSTN gateway</span></span>
    
  - <span data-ttu-id="49033-126">IP-PBX</span><span class="sxs-lookup"><span data-stu-id="49033-126">IP-PBX</span></span>
    
  - <span data-ttu-id="49033-127">透過設定 SIP 主幹) 所連接的網際網路電話語音服務提供者 (SBC)  (的會話邊界控制器</span><span class="sxs-lookup"><span data-stu-id="49033-127">Session Border Controller (SBC) (for an Internet telephony service provider to which you connect by configuring a SIP trunk)</span></span>
    
- <span data-ttu-id="49033-128">您可以在中央網站部署應用程式服務、會議應答應用程式和會議宣告應用程式，但不能在分支網站中。</span><span class="sxs-lookup"><span data-stu-id="49033-128">You can deploy the Application service, Conferencing Attendant application, and Conferencing Announcement application in a central site, but not in a branch site.</span></span>
    
- <span data-ttu-id="49033-129">您必須在每個部署商務用 Skype Server 會議的集區中部署電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="49033-129">You must deploy dial-in conferencing in every pool where you deploy Skype for Business Server conferencing.</span></span> <span data-ttu-id="49033-130">您不需要在每個集區中指派存取號碼，但是您必須在每個集區中部署電話撥入式會議功能。</span><span class="sxs-lookup"><span data-stu-id="49033-130">You do not need to assign access numbers in every pool, but you must deploy the dial-in conferencing feature in every pool.</span></span> <span data-ttu-id="49033-131">當使用者呼叫一個集區中的存取號碼，以在不同的集區加入商務用 Skype Server 會議時，此需求即支援記錄的名稱功能。</span><span class="sxs-lookup"><span data-stu-id="49033-131">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Skype for Business Server conference in a different pool.</span></span> 
    
<span data-ttu-id="49033-132">如需詳細資訊，請參閱 [在商務用 Skype Server 中規劃撥入式會議](dial-in-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="49033-132">For more information, see [Plan for dial-in conferencing in Skype for Business Server](dial-in-conferencing.md).</span></span>
  
## <a name="web-conferencing-considerations"></a><span data-ttu-id="49033-133">Web 會議考慮</span><span class="sxs-lookup"><span data-stu-id="49033-133">Web conferencing considerations</span></span>

<span data-ttu-id="49033-134">Web 會議需要下列專案：</span><span class="sxs-lookup"><span data-stu-id="49033-134">Web conferencing requires the following:</span></span> 
  
- <span data-ttu-id="49033-135">存取檔案存放區，以用來儲存 Web 會議內容。</span><span class="sxs-lookup"><span data-stu-id="49033-135">Access to the file store, which is used for storing web conferencing content.</span></span>
    
- <span data-ttu-id="49033-136">與 Office Web Apps Server/Office Online Server 整合，這是在會議期間共用 PowerPoint 檔案所需的。</span><span class="sxs-lookup"><span data-stu-id="49033-136">Integration with Office Web Apps Server/Office Online Server, which is necessary in order to share PowerPoint files during a conference.</span></span>
    
> [!NOTE]
> <span data-ttu-id="49033-137">Office Web Apps Server 的最新小小小，稱為 Office Online Server，它是由商務用 Skype Server 所支援。</span><span class="sxs-lookup"><span data-stu-id="49033-137">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Skype for Business Server.</span></span> <span data-ttu-id="49033-138">如需詳細資訊，請參閱 [Office Online Server 檔](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="49033-138">For more detail, refer to the [Office Online Server documentation](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx).</span></span> 
  
<span data-ttu-id="49033-139">商務用 Skype 伺服器提供下列方式來設定 Office Web Apps Server/Office Online Server。</span><span class="sxs-lookup"><span data-stu-id="49033-139">Skype for Business Server provides the following ways to configure Office Web Apps Server/Office Online Server.</span></span> <span data-ttu-id="49033-140">視您的需求而定，您可以：</span><span class="sxs-lookup"><span data-stu-id="49033-140">Depending on your needs you can:</span></span>
  
- <span data-ttu-id="49033-141">**安裝商務用 Skype Server 和 Office Web Apps Server/Office Online 伺服器內部部署（位於組織防火牆之後和相同網路區域）。**</span><span class="sxs-lookup"><span data-stu-id="49033-141">**Install both Skype for Business Server and Office Web Apps Server/Office Online Server on-premises behind your organization's firewall, and in the same network zone.**</span></span> <span data-ttu-id="49033-142">透過此拓撲，將會透過您的反向 proxy 伺服器提供外部的 Office Web Apps Server/Office Online 伺服器的存取權。</span><span class="sxs-lookup"><span data-stu-id="49033-142">With this topology, external access to Office Web Apps Server/Office Online Server will be provided through your reverse proxy server.</span></span> <span data-ttu-id="49033-143">理想狀況下，您應該在與商務用 Skype 伺服器相同的網路區域中安裝 Office Web Apps Server/Office Online Server。</span><span class="sxs-lookup"><span data-stu-id="49033-143">Ideally, you should install Office Web Apps Server/Office Online Server in the same network zone as Skype for Business Server.</span></span>
    
    <span data-ttu-id="49033-144">外部商務用 Skype 用戶端可以使用反向 proxy 伺服器（該伺服器會接受來自網際網路的要求，並將它們轉寄給內部網路），連線至商務用 Skype Server 和 Office Web Apps Server/Office Online Server。</span><span class="sxs-lookup"><span data-stu-id="49033-144">External Skype for Business clients can connect to Skype for Business Server and to Office Web Apps Server/Office Online Server by using a reverse proxy server, which is a server that takes requests from the Internet and forwards them to the internal network.</span></span> <span data-ttu-id="49033-145"> (內部用戶端不需要使用反向 proxy 伺服器，因為他們可以直接連線到 Office Web Apps Server/Office Online Server。如果您想要使用專用的 Office Web Apps Server/Office Online Server 伺服器陣列（僅供商務用 Skype Server 使用），則 ) 此拓撲最適合運作。</span><span class="sxs-lookup"><span data-stu-id="49033-145">(Internal clients do not need to use the reverse proxy server because they can connect to Office Web Apps Server/Office Online Server directly.) This topology works best if you want to use a dedicated Office Web Apps Server/Office Online Server farm that is only used by Skype for Business Server.</span></span>
    
- <span data-ttu-id="49033-146">**使用外部部署的 Office Web Apps Server/Office Online 伺服器。**</span><span class="sxs-lookup"><span data-stu-id="49033-146">**Use an externally deployed Office Web Apps Server/Office Online Server.**</span></span> <span data-ttu-id="49033-147">在此拓撲中，商務用 Skype 伺服器會部署在內部部署，並使用在商務用 Skype Server 網路區域以外部署的 Office Web Apps Server/Office Online 伺服器。</span><span class="sxs-lookup"><span data-stu-id="49033-147">In this topology, Skype for Business Server is deployed on-premises, and uses an Office Web Apps Server/Office Online Server that is deployed outside of the Skype for Business Server network zone.</span></span> <span data-ttu-id="49033-148">如果 Office Web Apps Server/Office Online 伺服器在公司中的多個應用程式之間共用，而且部署在需要商務用 Skype 伺服器的網路中，以使用 Office Web Apps Server/Office Online Server 的外部介面，則可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="49033-148">This may happen when Office Web Apps Server/Office Online Server is shared across multiple applications in the corporation and is deployed in a network requiring Skype for Business Server to use the external interface of Office Web Apps Server/Office Online Server and vice versa.</span></span>
    
    <span data-ttu-id="49033-149">您不需要安裝反向 proxy 伺服器;相反地，所有來自 Office Web Apps Server/Office Online 伺服器的要求，都是透過您的 Edge Server 路由傳送。</span><span class="sxs-lookup"><span data-stu-id="49033-149">You do not need to install a reverse proxy server; instead, all the requests from the Office Web Apps Server/Office Online Server to Skype for Business Server are routed through your Edge Server.</span></span> <span data-ttu-id="49033-150">您的內部和外部商務用 Skype 用戶端都使用外部 URL 連線到 Office Web Apps Server/Office Online Server。</span><span class="sxs-lookup"><span data-stu-id="49033-150">Both your internal and your external Skype for Business clients connect to Office Web Apps Server/Office Online Server using the external URL.</span></span>
    
    <span data-ttu-id="49033-151">如果 Office Web Apps Server/Office Online Server 部署在您的內部防火牆外，請選取 [ **Office Web Apps server] 部署在拓撲產生** 器中的外部網路 (，也就是周邊/網際網路) 。</span><span class="sxs-lookup"><span data-stu-id="49033-151">If the Office Web Apps Server/Office Online Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network** (that is, perimeter/Internet) in Topology Builder.</span></span>
    
<span data-ttu-id="49033-152">如需詳細資訊，請參閱 [設定商務用 Skype server 中的 Office Web Apps server 整合](../../deploy/deploy-conferencing/office-web-app-server.md)。</span><span class="sxs-lookup"><span data-stu-id="49033-152">For more information, see [Configure integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).</span></span> 
  
<span data-ttu-id="49033-153">不論您選取的拓撲為何，開啟正確的防火牆埠都很重要。</span><span class="sxs-lookup"><span data-stu-id="49033-153">Regardless of the topology you select, it is critical that the correct firewall ports be opened.</span></span> <span data-ttu-id="49033-154">您必須確定，Office Web Apps Server/Office Online Server、負載平衡器或商務用 Skype Server 上的防火牆沒有封鎖 DNS 名稱、IP 位址和埠。</span><span class="sxs-lookup"><span data-stu-id="49033-154">You must make sure that DNS names, IP addresses, and ports are not blocked by firewalls on the Office Web Apps Server/Office Online Server, the load balancer, or Skype for Business Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="49033-155">提供外部存取 Office Web Apps Server/Office Online 伺服器的另一個選項是在周邊網路中部署伺服器。</span><span class="sxs-lookup"><span data-stu-id="49033-155">Another option for providing external access to Office Web Apps Server/Office Online Server is to deploy the server in the perimeter network.</span></span> <span data-ttu-id="49033-156">如果您選擇執行這項操作，請記住，Office Web Apps Server/Office Online Server 安裝程式需要伺服器電腦成為 Active Directory 網域的成員。</span><span class="sxs-lookup"><span data-stu-id="49033-156">If you elect to do this, keep in mind that Office Web Apps Server/Office Online Server setup requires the server computer to be a member of your Active Directory domain.</span></span> <span data-ttu-id="49033-157">除非您的網路原則允許周邊網路中的電腦成為 Active Directory 網域成員，否則建議您不要在周邊網路中安裝 Office Web Apps Server/Office Online Server。</span><span class="sxs-lookup"><span data-stu-id="49033-157">Unless your network policy allows computers in the perimeter network to be Active Directory domain members, it is recommended that you do not install Office Web Apps Server/Office Online Server in the perimeter network.</span></span> <span data-ttu-id="49033-158">相反地，您應該在內部網路上安裝 Office Web Apps Server/Office Online Server，並透過反向 proxy 伺服器提供外部使用者存取。</span><span class="sxs-lookup"><span data-stu-id="49033-158">Instead, you should install Office Web Apps Server/Office Online Server in the internal network and provide external user access through your reverse proxy server.</span></span> 
  
## <a name="topology-requirements-for-large-meetings"></a><span data-ttu-id="49033-159">大型會議的拓撲需求</span><span class="sxs-lookup"><span data-stu-id="49033-159">Topology requirements for large meetings</span></span>

<span data-ttu-id="49033-160">單一大型會議需要至少一部前端伺服器和一部後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="49033-160">A single large meeting requires at least one Front End Server and one Back End Server.</span></span> <span data-ttu-id="49033-161">不過，為了提供高可用性，我們建議使用兩部前端伺服器集區和鏡像後端伺服器，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="49033-161">However, to provide high availability, we recommend a two Front End Server pool with mirrored Back End Servers as shown in the following diagram:</span></span>
  
<span data-ttu-id="49033-162">**大型會議拓撲**</span><span class="sxs-lookup"><span data-stu-id="49033-162">**Large meeting topology**</span></span>

![大型會議拓撲](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
<span data-ttu-id="49033-164">主控大型會議的使用者必須擁有位於前端集區中的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="49033-164">The user who hosts the large meetings must have their user account homed in Front End pool.</span></span> <span data-ttu-id="49033-165">不過，我們不建議您在此集區中主控其他使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="49033-165">However, we do not recommend that you host other user accounts in this pool.</span></span> <span data-ttu-id="49033-166">而只是用於大型會議。</span><span class="sxs-lookup"><span data-stu-id="49033-166">Instead, use it only for the large meetings.</span></span> <span data-ttu-id="49033-167">最佳作法是在此集區中建立特殊的使用者帳戶，僅供主控大型會議使用。</span><span class="sxs-lookup"><span data-stu-id="49033-167">The best practice is to create a special user account in this pool to be used only to host large meetings.</span></span> <span data-ttu-id="49033-168">因為大型會議設定已經針對效能進行優化，所以以一般使用者的身分使用它時，可能會發生問題，例如，當涉及 PSTN 端點時，無法將 P2P 會話提升為會議。</span><span class="sxs-lookup"><span data-stu-id="49033-168">Since the large meeting setting is optimized for performance, using it as a normal user could have problems such as the inability to promote a P2P session to a meeting when a PSTN endpoint is involved.</span></span>
  
<span data-ttu-id="49033-169">若要管理恰好兩部前端伺服器的集區，需要一些特殊的考慮。</span><span class="sxs-lookup"><span data-stu-id="49033-169">Managing a pool with exactly two Front End Servers requires some special considerations.</span></span> <span data-ttu-id="49033-170">如需詳細資訊，請參閱適用于商務用 Skype server [2015 的拓撲基礎](../../plan-your-deployment/topology-basics/topology-basics.md) 和 [商務用 skype Server 2015 的參考拓撲](../../plan-your-deployment/topology-basics/reference-topologies.md)。</span><span class="sxs-lookup"><span data-stu-id="49033-170">For more information, see [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) and [Reference topologies for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md).</span></span>
  
<span data-ttu-id="49033-171">此外，如果您想要選擇性地為大型會議所用的集區提供嚴重損壞修復備份和容錯移轉，您可以將它與不同資料中心的專用集區配對。</span><span class="sxs-lookup"><span data-stu-id="49033-171">Additionally, if you want to optionally provide disaster recovery backup and failover for the pool used for large meetings, you can pair it with a similarly set up dedicated pool in a different data center.</span></span> <span data-ttu-id="49033-172">如需詳細資訊，請參閱 [在商務用 Skype Server 中規劃高可用性和嚴重損壞修復](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="49033-172">For details, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
<span data-ttu-id="49033-173">拓撲的其他注意事項包括：</span><span class="sxs-lookup"><span data-stu-id="49033-173">Additional notes about the topology include:</span></span>
  
- <span data-ttu-id="49033-174">需要有檔案共用，才能儲存會議內容，以及在部署及啟用封存伺服器時儲存封存檔。</span><span class="sxs-lookup"><span data-stu-id="49033-174">A file share is required for storing meeting content and, if Archiving Server is deployed and enabled, for storing the archiving files.</span></span> <span data-ttu-id="49033-175">檔案共用可以專用於集區，也可以是部署集區之網站上其他集區所使用的相同檔案共用。</span><span class="sxs-lookup"><span data-stu-id="49033-175">The file share can be dedicated to the pool or can be the same file share used by another pool at the site in which the pool is deployed.</span></span> <span data-ttu-id="49033-176">如需設定檔案共用的詳細資訊，請參閱 [在商務用 Skype Server 2015 中建立檔案共用](../../deploy/install/create-a-file-share.md)。</span><span class="sxs-lookup"><span data-stu-id="49033-176">For details about configuring the file share, see [Create a file share in Skype for Business Server 2015](../../deploy/install/create-a-file-share.md).</span></span>
    
- <span data-ttu-id="49033-177">若要在大型會議中啟用 PowerPoint 簡報功能，必須使用 Office Web Apps Server/Office Online 伺服器。</span><span class="sxs-lookup"><span data-stu-id="49033-177">An Office Web Apps Server/Office Online Server is required for enabling the PowerPoint presentation functionality in large meetings.</span></span> <span data-ttu-id="49033-178">您可以將 Office Web Apps Server/Office Online 伺服器專用於大型會議集區，也可以是部署專用集區之網站上其他集區所使用的 Office Web Apps Server/Office Online 伺服器。</span><span class="sxs-lookup"><span data-stu-id="49033-178">The Office Web Apps Server/Office Online Server can be dedicated to the large meeting pool or, it can be the same Office Web Apps Server/Office Online Server used by other pools at the site in which the dedicated pool is deployed.</span></span> <span data-ttu-id="49033-179">如需詳細資訊，請參閱 [設定商務用 Skype server 中的 Office Web Apps server 整合](../../deploy/deploy-conferencing/office-web-app-server.md)。</span><span class="sxs-lookup"><span data-stu-id="49033-179">For more information, see [Configure integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).</span></span> 
    
- <span data-ttu-id="49033-180">前端伺服器的負載平衡需要對 HTTP 流量 (例如「會議內容下載) 」的硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="49033-180">Load balancing of the Front End Servers requires hardware load balancing for the HTTP traffic (such as meeting content download).</span></span> <span data-ttu-id="49033-181">建議使用 DNS 負載平衡進行 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="49033-181">DNS load balancing is recommended for SIP traffic.</span></span> <span data-ttu-id="49033-182">如需詳細資訊，請參閱 [商務用 Skype 的負載平衡需求](../../plan-your-deployment/network-requirements/load-balancing.md)。</span><span class="sxs-lookup"><span data-stu-id="49033-182">For details see [Load balancing requirements for Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md).</span></span> 
    
- <span data-ttu-id="49033-183">如果您想要針對專用的大型會議集區使用監控伺服器，我們建議使用監控伺服器及其在商務用 Skype Server 部署中的所有前端伺服器集區共用的資料庫。</span><span class="sxs-lookup"><span data-stu-id="49033-183">If you want to use Monitoring Server for the dedicated large-meeting pool, we recommend using the Monitoring Server and its database that are shared across all of the Front End Server pools in your Skype for Business Server deployment.</span></span> <span data-ttu-id="49033-184">如需詳細資訊，請參閱 [Plan for monitoring In 商務用 Skype Server](../../plan-your-deployment/monitoring.md)。</span><span class="sxs-lookup"><span data-stu-id="49033-184">For more information, see [Plan for monitoring in Skype for Business Server](../../plan-your-deployment/monitoring.md).</span></span>
    

