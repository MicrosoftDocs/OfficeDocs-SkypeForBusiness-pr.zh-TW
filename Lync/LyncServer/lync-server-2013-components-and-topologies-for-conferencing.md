---
title: Lync Server 2013 會議元件與拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cfdb6ae250e3ccb97f044892daa8ac11e7c1b99b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502580"
---
# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="69c18-102">Lync Server 2013 中的會議元件與拓撲</span><span class="sxs-lookup"><span data-stu-id="69c18-102">Components and topologies for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69c18-103">_**主題上次修改日期：** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="69c18-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="69c18-104">當您在拓撲產生器中選取會議時，會將會議部署為前端伺服器或 Standard Edition Server 的一部分。</span><span class="sxs-lookup"><span data-stu-id="69c18-104">When you select conferencing in Topology Builder, conferencing is deployed as part of the Front End Server or Standard Edition server.</span></span> <span data-ttu-id="69c18-105">電話撥入式會議和 PowerPoint 共用需要其他元件和設定。</span><span class="sxs-lookup"><span data-stu-id="69c18-105">Dial-in conferencing and PowerPoint sharing requires additional components and configuration.</span></span> <span data-ttu-id="69c18-106">下列各節說明 web 會議、A/V 會議和電話撥入式會議所支援的元件和拓撲。</span><span class="sxs-lookup"><span data-stu-id="69c18-106">The following sections describe the supported components and topologies for web conferencing, A/V conferencing, and dial-in conferencing.</span></span>

<div>

## <a name="supported-components"></a><span data-ttu-id="69c18-107">支援的元件</span><span class="sxs-lookup"><span data-stu-id="69c18-107">Supported Components</span></span>

<span data-ttu-id="69c18-108">只有組織的前端伺服器或 Standard Edition 伺服器，才需要 [元件 web 會議和 A/V 會議]。</span><span class="sxs-lookup"><span data-stu-id="69c18-108">The only components web conferencing and A/V conferencing require are your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="69c18-109">如需前端伺服器和 Standard Edition server 的硬體和軟體需求清單，請參閱 Lync Server 2013 中 [支援的 Lync server 2013](lync-server-2013-supported-hardware.md) 和 [伺服器軟體和基礎結構支援](lync-server-2013-server-software-and-infrastructure-support.md)硬體。</span><span class="sxs-lookup"><span data-stu-id="69c18-109">For a list of hardware and software requirements for the Front End Servers and Standard Edition servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

<span data-ttu-id="69c18-110">Lync Server 2013 使用 Office Web Apps 與 Office Web apps Server 來處理 PowerPoint 簡報的共用及呈現。</span><span class="sxs-lookup"><span data-stu-id="69c18-110">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="69c18-111">如需安裝及設定 Office Web Apps Server 的詳細資訊，請參閱設定 [Office Web Apps server 與 Lync server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="69c18-111">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="69c18-112">除了 web 會議和 A/V 會議的需求之外，電話撥入式會議還使用下列 Lync Server 2013 元件：</span><span class="sxs-lookup"><span data-stu-id="69c18-112">In addition to the requirements for web conferencing and A/V conferencing, dial-in conferencing uses the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="69c18-113">**應用程式服務**    Application service 提供一個平臺，用以部署、主控和管理整合通訊 (UC) 應用程式。</span><span class="sxs-lookup"><span data-stu-id="69c18-113">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications (UC) applications.</span></span> <span data-ttu-id="69c18-114">電話撥入式會議使用需要 Application service 的兩個 UC 應用程式：會議助理和會議宣告。</span><span class="sxs-lookup"><span data-stu-id="69c18-114">Dial-in conferencing uses two UC applications that require Application service: Conferencing Attendant and Conferencing Announcement.</span></span> <span data-ttu-id="69c18-115">當您部署會議工作負載並選取 [電話撥入式會議] 選項時，預設會在前端集區中的每一部前端伺服器及每個 Standard Edition 伺服器上安裝及啟用應用程式服務。</span><span class="sxs-lookup"><span data-stu-id="69c18-115">Application service is installed and activated by default on every Front End Server in a Front End pool and on every Standard Edition server when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="69c18-116">**會議助理應用程式**    會議應答應用程式是一種整合通訊應用程式，可接受公用交換電話網路 (PSTN) 通話、播放提示，以及將通話加入 A/V 會議。</span><span class="sxs-lookup"><span data-stu-id="69c18-116">**Conferencing Attendant application**   Conferencing Attendant application is a unified communications application that accepts public switched telephone network (PSTN) calls, plays prompts, and joins the calls to an A/V conference.</span></span> <span data-ttu-id="69c18-117">當您部署會議工作負載並選取 [電話撥入式會議] 選項時，預設會安裝及啟用會議應答應用程式。</span><span class="sxs-lookup"><span data-stu-id="69c18-117">Conferencing Attendant application is installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="69c18-118">**會議宣告應用程式**    會議宣告應用程式是一種整合通訊應用程式，可在某些動作上為 PSTN 參與者播放色調和提示，例如當參與者加入或離開會議時，參與者會靜音或 unmuted、某人進入會議會議廳，或是鎖定或解除鎖定會議。</span><span class="sxs-lookup"><span data-stu-id="69c18-118">**Conferencing Announcement application**   Conferencing Announcement application is a unified communications application that plays tones and prompts to PSTN participants on certain actions, such as when participants join or leave a conference, participants are muted or unmuted, someone enters the conference lobby, or the conference is locked or unlocked.</span></span> <span data-ttu-id="69c18-119">會議宣告應用程式也支援雙聲調頻式訊號 (DTMF) 命令從電話鍵鍵盤。</span><span class="sxs-lookup"><span data-stu-id="69c18-119">Conferencing Announcement application also supports dual-tone multifrequency (DTMF) commands from the phone keypad.</span></span> <span data-ttu-id="69c18-120">會議宣告應用程式會在您部署會議工作負載及選取電話撥入式會議選項時，依預設自動安裝及啟用。</span><span class="sxs-lookup"><span data-stu-id="69c18-120">Conferencing Announcement application is automatically installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="69c18-121">**電話撥入式會議設定頁面**    [電話撥入式會議設定] 頁面會以可用的語言顯示會議撥入號碼、指派會議資訊 (，也就是針對不需要排程) 的會議，以及在會議 DTMF 控制項中管理的個人識別碼，並支援 (PIN) 和指派會議資訊的個人識別碼的管理。</span><span class="sxs-lookup"><span data-stu-id="69c18-121">**Dial-in Conferencing Settings page**   The Dial-in Conferencing Settings page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="69c18-122">[電話撥入式會議設定] 頁面會自動安裝為 Web 服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="69c18-122">The Dial-in Conferencing Settings page is automatically installed as part of Web Services.</span></span>

  - <span data-ttu-id="69c18-123">**Lync server 2013、轉送伺服器和 PSTN 閘道**    電話撥入式會議需要一台轉送伺服器，以在 Lync Server 2013 與 PSTN 閘道之間的某些設定) 中轉譯信號 (和媒體，以及在轉送伺服器和 PSTN 閘道之間轉譯信號和媒體的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="69c18-123">**Lync Server 2013, Mediation Server and PSTN gateway**   Dial-in conferencing requires a Mediation Server to translate signaling (and media, in some configurations) between Lync Server 2013 and the PSTN gateway, and a PSTN gateway to translate signaling and media between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="69c18-124">若為電話撥入式會議，您必須至少部署一個轉送伺服器，至少要有下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="69c18-124">For dial-in conferencing, you must deploy at least one Mediation Server and at least one of the following:</span></span>
    
      - <span data-ttu-id="69c18-125">PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="69c18-125">PSTN gateway</span></span>
    
      - <span data-ttu-id="69c18-126">IP-PBX</span><span class="sxs-lookup"><span data-stu-id="69c18-126">IP-PBX</span></span>
    
      - <span data-ttu-id="69c18-127">透過設定 SIP 主幹) 所連接的網際網路電話語音服務提供者 (SBC)  (的會話邊界控制器</span><span class="sxs-lookup"><span data-stu-id="69c18-127">Session Border Controller (SBC) (for an Internet telephony service provider to which you connect by configuring a SIP trunk)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="69c18-128">如果您也部署企業語音，轉送伺服器和 PSTN 閘道是企業語音部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="69c18-128">If you are also deploying Enterprise Voice, Mediation Server and PSTN gateways are part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="69c18-129">如果您不是部署企業語音，您必須至少部署一個轉送伺服器，以及至少一個 PSTN 閘道、IP-PBX 或 SBC 用於電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="69c18-129">If you are not deploying Enterprise Voice, you need to deploy at least one Mediation Server and at least one PSTN gateway, IP-PBX, or SBC for dial-in conferencing.</span></span>

    
    </div>

  - <span data-ttu-id="69c18-130">**檔存放區**    檔存放區用於記錄的名稱音訊檔。</span><span class="sxs-lookup"><span data-stu-id="69c18-130">**File store**   File store is used for recorded name audio files.</span></span> <span data-ttu-id="69c18-131">檔存放區是每個 Enterprise Edition 或 Standard Edition 部署中的標準元件。</span><span class="sxs-lookup"><span data-stu-id="69c18-131">File Store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="69c18-132">**使用者存放區**    使用者存放區用於儲存使用者 Lync Server 2013 Pin。</span><span class="sxs-lookup"><span data-stu-id="69c18-132">**User store**   User store is used to store user Lync Server 2013 PINs.</span></span> <span data-ttu-id="69c18-133">會散列 Pin。</span><span class="sxs-lookup"><span data-stu-id="69c18-133">PINs are hashed.</span></span> <span data-ttu-id="69c18-134">在每個 Enterprise Edition 或 Standard Edition 部署中，使用者存放區是一個標準元件。</span><span class="sxs-lookup"><span data-stu-id="69c18-134">The User store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="69c18-135">**Lync Server 控制台**    使用 Lync Server 控制台可以設定某些撥入設定。</span><span class="sxs-lookup"><span data-stu-id="69c18-135">**Lync Server Control Panel**   Some dial-in settings can be configured by using Lync Server Control Panel.</span></span>

  - <span data-ttu-id="69c18-136">**Lync Server 管理命令**     介面您可以使用 Lync Server 管理命令介面 Cmdlet 來設定所有撥入設定。</span><span class="sxs-lookup"><span data-stu-id="69c18-136">**Lync Server Management Shell**   All dial-in settings can be configured by using Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="69c18-137">Lync Server 管理命令介面 Cmdlet 可用於部署、設定、執行、監控會議應答應用程式和會議宣告應用程式，以及進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="69c18-137">Lync Server Management Shell cmdlets are available for deploying, configuring, running, monitoring, and troubleshooting Conferencing Attendant application and Conferencing Announcement application.</span></span> <span data-ttu-id="69c18-138">如需特定 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="69c18-138">For details about specific cmdlets, see Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="69c18-139">支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="69c18-139">Supported Topologies</span></span>

<span data-ttu-id="69c18-140">在 Lync Server 2013 中，執行會議服務的伺服器一定會組合前端伺服器或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="69c18-140">In Lync Server 2013, the server running conferencing services is always collocated with the Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="69c18-141">在初始部署期間，拓撲產生器可讓您選擇在拓撲中包含會議。</span><span class="sxs-lookup"><span data-stu-id="69c18-141">During your initial deployment, Topology Builder gives you the option to include conferencing in your topology.</span></span> <span data-ttu-id="69c18-142">您也可以使用拓撲產生器，將會議新增至現有的部署。</span><span class="sxs-lookup"><span data-stu-id="69c18-142">You can also use Topology Builder to add conferencing to an existing deployment.</span></span> <span data-ttu-id="69c18-143">如需詳細資訊，請參閱 [在 Lync Server 2013 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="69c18-143">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

<div>

## <a name="dial-in-conferencing-toplogies"></a><span data-ttu-id="69c18-144">電話撥入式會議 Toplogies</span><span class="sxs-lookup"><span data-stu-id="69c18-144">Dial in Conferencing Toplogies</span></span>

<span data-ttu-id="69c18-145">您可以在下列拓撲和設定中部署電話撥入式會議：</span><span class="sxs-lookup"><span data-stu-id="69c18-145">You can deploy dial-in conferencing in the following topologies and configurations:</span></span>

  - <span data-ttu-id="69c18-146">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="69c18-146">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="69c18-147">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="69c18-147">Lync Server 2013 Enterprise Edition</span></span>

  - <span data-ttu-id="69c18-148">有或沒有 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="69c18-148">With or without Enterprise Voice</span></span>

<span data-ttu-id="69c18-149">您可以在中央網站部署應用程式服務、會議應答應用程式和會議宣告應用程式，但不能在分支網站中。</span><span class="sxs-lookup"><span data-stu-id="69c18-149">You can deploy Application service, Conferencing Attendant application, and Conferencing Announcement application in a central site, but not in a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="69c18-150">如果您部署電話撥入式會議，則必須在每個部署 Lync Server 2013 會議的集區中部署它。</span><span class="sxs-lookup"><span data-stu-id="69c18-150">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="69c18-151">您不需要在每個集區中指派存取號碼，但是您必須在每個集區中部署電話撥入式會議功能。</span><span class="sxs-lookup"><span data-stu-id="69c18-151">You do not need to assign access numbers in every pool, but you must deploy the dial-in conferencing feature in every pool.</span></span> <span data-ttu-id="69c18-152">當使用者呼叫一個集區中的存取號碼，以在不同的集區加入 Lync Server 2013 會議時，此需求即支援記錄的名稱功能。</span><span class="sxs-lookup"><span data-stu-id="69c18-152">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a><span data-ttu-id="69c18-153">Lync Server 2013 和 Office Web Apps 支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="69c18-153">Supported Topologies for Lync Server 2013 and Office Web Apps</span></span>

<span data-ttu-id="69c18-154">Lync Server 2013 提供下列方式來設定 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="69c18-154">Lync Server 2013 provides the following ways to configure Office Web Apps Server.</span></span> <span data-ttu-id="69c18-155">視您的需求而定，您可以：</span><span class="sxs-lookup"><span data-stu-id="69c18-155">Depending on your needs you can:</span></span>

  - <span data-ttu-id="69c18-156">**在您組織的防火牆之後和相同的網路區域中，安裝 Lync Server 2013 和 Office Web Apps Server 內部部署。**</span><span class="sxs-lookup"><span data-stu-id="69c18-156">**Install both Lync Server 2013 and Office Web Apps Server on-premises behind your organization’s firewall, and in the same network zone.**</span></span> <span data-ttu-id="69c18-157">透過此拓撲，將會透過您的反向 proxy 伺服器提供外部存取的 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="69c18-157">With this topology, external access to Office Web Apps Server will be provided through your reverse proxy server.</span></span> <span data-ttu-id="69c18-158">[Lync Server 2013] 和 [Office Web Apps Server (] 或 [Office Web Apps Server 伺服器陣列]) 都會安裝在內部部署及組織防火牆之後。</span><span class="sxs-lookup"><span data-stu-id="69c18-158">Both Lync Server 2013 and Office Web Apps Server (or an Office Web Apps Server farm) are installed on-premises and behind your organization's firewall.</span></span> <span data-ttu-id="69c18-159">理想狀況下，您應將 Office Web Apps Server 安裝在與 Lync Server 相同的網路區域中。</span><span class="sxs-lookup"><span data-stu-id="69c18-159">Ideally, you should install Office Web Apps Server in the same network zone as Lync Server.</span></span>
    
    <span data-ttu-id="69c18-160">外部 Lync 用戶端可以使用反向 proxy 伺服器連線至 Lync Server 2013 和 Office Web Apps Server，這是一部伺服器，用來自網際網路的要求，並將它們轉寄給內部網路。</span><span class="sxs-lookup"><span data-stu-id="69c18-160">External Lync clients can connect to Lync Server 2013 and to Office Web Apps Server by using a reverse proxy server, which is a server that takes requests from the Internet and forwards them to the internal network.</span></span> <span data-ttu-id="69c18-161"> (內部用戶端不需要使用反向 proxy 伺服器，因為他們可以直接連線到 Office Web Apps Server。如果您想要使用僅供 Lync Server 2013 使用的專用 Office Web Apps Server 伺服器陣列，則 ) 此拓撲最適合運作。</span><span class="sxs-lookup"><span data-stu-id="69c18-161">(Internal clients do not need to use the reverse proxy server because they can connect to Office Web Apps Server directly.) This topology works best if you want to use a dedicated Office Web Apps Server farm that is only used by Lync Server 2013.</span></span>

  - <span data-ttu-id="69c18-162">**使用外部部署的 Office Web Apps Server**</span><span class="sxs-lookup"><span data-stu-id="69c18-162">**Using an externally deployed Office Web Apps Server**</span></span>
    
    <span data-ttu-id="69c18-163">在此拓撲中，會在內部部署 Lync Server 2013，並使用在 Lync Server 網路區域以外部署的 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="69c18-163">In this topology, Lync Server 2013 is deployed on-premises, and uses an Office Web Apps Server that is deployed outside of Lync Server network zone.</span></span> <span data-ttu-id="69c18-164">如果 Office Web Apps Server 在公司中的多個應用程式之間共用，而且部署在需要 Lync 伺服器以使用 Office Web Apps Server 的外部介面的網路中，則可能會發生這種情況，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="69c18-164">This may happen when Office Web Apps Server is shared across multiple applications in the corporation and is deployed in a network requiring Lync Server to use the external interface of Office Web Apps Server and vice versa.</span></span>
    
    <span data-ttu-id="69c18-165">您不需要安裝反向 proxy 伺服器;相反地，Office Web Apps Server 對 Lync Server 2013 的所有要求都是透過您的 Edge Server 路由傳送。</span><span class="sxs-lookup"><span data-stu-id="69c18-165">You do not need to install a reverse proxy server; instead, all the requests from the Office Web Apps Server to Lync Server 2013 are routed through your Edge Server.</span></span> <span data-ttu-id="69c18-166">您的內部和外部 Lync 用戶端會使用外部 URL 連線到 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="69c18-166">Both your internal and your external Lync clients connect to Office Web Apps Server using the external URL.</span></span>
    
    <span data-ttu-id="69c18-167">如果 Office Web Apps Server 部署在您的內部防火牆外，請選取 [ \*\*Office Web Apps server] 部署在拓撲產生器中的外部網路 (，也就是周邊/網際網路) \*\* 。</span><span class="sxs-lookup"><span data-stu-id="69c18-167">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** in Topology Builder.</span></span> <span data-ttu-id="69c18-168">如需詳細資訊，請參閱設定 [Office Web Apps Server 和 Lync Server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="69c18-168">For more details see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="69c18-169">不論您選取的拓撲為何，開啟正確的防火牆埠都很重要。</span><span class="sxs-lookup"><span data-stu-id="69c18-169">Regardless of the topology you select, it is critical that the correct firewall ports be opened.</span></span> <span data-ttu-id="69c18-170">您必須確定在 Office Web Apps Server、負載平衡器或 Lync Server 上，防火牆沒有封鎖 DNS 名稱、IP 位址和埠。</span><span class="sxs-lookup"><span data-stu-id="69c18-170">You must make sure that DNS names, IP addresses, and ports are not blocked by firewalls on the Office Web Apps Server, the load balancer, or Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="69c18-171">提供 Office Web Apps Server 外部存取的另一個選項是在周邊網路中部署伺服器。</span><span class="sxs-lookup"><span data-stu-id="69c18-171">Another option for providing external access to Office Web Apps Server is to deploy the server in the perimeter network.</span></span> <span data-ttu-id="69c18-172">如果您選擇執行這項操作，請記住，Office Web Apps Server 安裝程式需要伺服器電腦成為您的 Active Directory 網域的成員。</span><span class="sxs-lookup"><span data-stu-id="69c18-172">If you elect to do this, keep in mind that Office Web Apps Server setup requires the server computer to be a member of your Active Directory domain.</span></span> <span data-ttu-id="69c18-173">除非您的網路原則允許周邊網路中的電腦成為 Active Directory 網域成員，否則建議您不要在周邊網路中安裝 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="69c18-173">Unless your network policy allows computers in the perimeter network to be Active Directory domain members, it is recommended that you do not install Office Web Apps Server in the perimeter network.</span></span> <span data-ttu-id="69c18-174">相反地，您應該在內部網路上安裝 Office Web Apps Server，並透過反向 proxy 伺服器提供外部使用者存取。</span><span class="sxs-lookup"><span data-stu-id="69c18-174">Instead, you should install Office Web Apps Server in the internal network and provide external user access through your reverse proxy server.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

