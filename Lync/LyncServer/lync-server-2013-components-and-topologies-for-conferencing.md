---
title: Lync Server 2013 會議元件與拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5caf5ba33e863e08bf4f728d2bf11394f37f20b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="4eca4-102">Lync Server 2013 中的會議元件與拓撲</span><span class="sxs-lookup"><span data-stu-id="4eca4-102">Components and topologies for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4eca4-103">_**主題上次修改日期：** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="4eca4-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="4eca4-104">當您在 [拓撲建立器] 中選取 [會議] 時，會議會作為前端伺服器或標準版伺服器的一部分來部署。</span><span class="sxs-lookup"><span data-stu-id="4eca4-104">When you select conferencing in Topology Builder, conferencing is deployed as part of the Front End Server or Standard Edition server.</span></span> <span data-ttu-id="4eca4-105">電話撥入式會議與 PowerPoint 共用需要額外的元件和設定。</span><span class="sxs-lookup"><span data-stu-id="4eca4-105">Dial-in conferencing and PowerPoint sharing requires additional components and configuration.</span></span> <span data-ttu-id="4eca4-106">下列各節說明網路會議、A/V 會議和電話撥入式會議支援的元件與拓撲。</span><span class="sxs-lookup"><span data-stu-id="4eca4-106">The following sections describe the supported components and topologies for web conferencing, A/V conferencing, and dial-in conferencing.</span></span>

<div>

## <a name="supported-components"></a><span data-ttu-id="4eca4-107">支援的元件</span><span class="sxs-lookup"><span data-stu-id="4eca4-107">Supported Components</span></span>

<span data-ttu-id="4eca4-108">唯一的元件 web 會議與 A/V 會議需要您組織的前端伺服器或標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="4eca4-108">The only components web conferencing and A/V conferencing require are your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="4eca4-109">如需前端伺服器和標準版伺服器的硬體和軟體需求清單，請參閱 lync Server 2013[支援的 Lync server 2013](lync-server-2013-supported-hardware.md)和[伺服器軟體及基礎結構支援](lync-server-2013-server-software-and-infrastructure-support.md)的硬體。</span><span class="sxs-lookup"><span data-stu-id="4eca4-109">For a list of hardware and software requirements for the Front End Servers and Standard Edition servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

<span data-ttu-id="4eca4-110">Lync Server 2013 使用 Office Web Apps 和 Office Web Apps 伺服器來處理 PowerPoint 簡報的共用和轉譯。</span><span class="sxs-lookup"><span data-stu-id="4eca4-110">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="4eca4-111">如需安裝及設定 Office Web Apps 伺服器的詳細資料，請參閱設定[與 Office Web Apps server 和 Lync Server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="4eca4-111">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="4eca4-112">除了適用于 web 會議和 A/V 會議的需求之外，電話撥入式會議還使用下列 Lync Server 2013 元件：</span><span class="sxs-lookup"><span data-stu-id="4eca4-112">In addition to the requirements for web conferencing and A/V conferencing, dial-in conferencing uses the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="4eca4-113">**應用程式服務**   應用程式服務提供部署、託管及管理整合通訊（UC）應用程式的平臺。</span><span class="sxs-lookup"><span data-stu-id="4eca4-113">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications (UC) applications.</span></span> <span data-ttu-id="4eca4-114">電話撥入式會議使用兩個需要應用程式服務的 UC 應用程式：會議助理與會議公告。</span><span class="sxs-lookup"><span data-stu-id="4eca4-114">Dial-in conferencing uses two UC applications that require Application service: Conferencing Attendant and Conferencing Announcement.</span></span> <span data-ttu-id="4eca4-115">當您部署會議工作負載並選取 [電話撥入式會議] 選項時，應用程式服務預設會安裝並在每個標準版 server 上的每個前端伺服器上啟用。</span><span class="sxs-lookup"><span data-stu-id="4eca4-115">Application service is installed and activated by default on every Front End Server in a Front End pool and on every Standard Edition server when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="4eca4-116">**會議助理應用**   程式會議助理應用程式是一種整合通訊應用程式，可接受公用交換電話網絡（PSTN）通話、播放提示，以及將呼叫加入 a/V 會議。</span><span class="sxs-lookup"><span data-stu-id="4eca4-116">**Conferencing Attendant application**   Conferencing Attendant application is a unified communications application that accepts public switched telephone network (PSTN) calls, plays prompts, and joins the calls to an A/V conference.</span></span> <span data-ttu-id="4eca4-117">在您部署會議工作負載及選取電話撥入式會議選項時，會議助理應用程式預設會安裝並啟用。</span><span class="sxs-lookup"><span data-stu-id="4eca4-117">Conferencing Attendant application is installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="4eca4-118">**會議發佈應用程式**   會議公告應用程式是一種整合式通訊應用程式，它會在特定動作上對 PSTN 參與者播放聲音和提示，例如當參與者加入或離開會議時，參與者是靜音或已取消靜音、有人進入會議會議廳，或會議已鎖定或解除鎖定。</span><span class="sxs-lookup"><span data-stu-id="4eca4-118">**Conferencing Announcement application**   Conferencing Announcement application is a unified communications application that plays tones and prompts to PSTN participants on certain actions, such as when participants join or leave a conference, participants are muted or unmuted, someone enters the conference lobby, or the conference is locked or unlocked.</span></span> <span data-ttu-id="4eca4-119">[會議公告] 應用程式也支援來自電話鍵台的雙音調 multifrequency （DTMF）命令。</span><span class="sxs-lookup"><span data-stu-id="4eca4-119">Conferencing Announcement application also supports dual-tone multifrequency (DTMF) commands from the phone keypad.</span></span> <span data-ttu-id="4eca4-120">當您部署會議工作負載並選取 [電話撥入式會議] 選項時，會議宣告應用程式預設會自動安裝並啟用。</span><span class="sxs-lookup"><span data-stu-id="4eca4-120">Conferencing Announcement application is automatically installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="4eca4-121">\*\*\*\*[電話撥入式會議設定] 頁面： [電話撥入式會議設定] 頁面會以其可用語言顯示會議撥入號碼、指派會議資訊（也就是，對於不需要排程的會議）以及會議 DTMF 控制，並支援個人識別碼（PIN）及指派會議資訊的管理。   </span><span class="sxs-lookup"><span data-stu-id="4eca4-121">**Dial-in Conferencing Settings page**   The Dial-in Conferencing Settings page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="4eca4-122">[電話撥入式會議設定] 頁面會自動安裝為 Web 服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="4eca4-122">The Dial-in Conferencing Settings page is automatically installed as part of Web Services.</span></span>

  - <span data-ttu-id="4eca4-123">**Lync server 2013、中繼伺服器和 pstn 閘道**   電話撥入式會議需要一個中繼伺服器來轉譯 Lync server 2013 和 pstn 閘道之間的信號（以及在部分設定中的媒體），以及在中繼伺服器與 pstn 閘道之間轉譯信號與媒體的 pstn 閘道。</span><span class="sxs-lookup"><span data-stu-id="4eca4-123">**Lync Server 2013, Mediation Server and PSTN gateway**   Dial-in conferencing requires a Mediation Server to translate signaling (and media, in some configurations) between Lync Server 2013 and the PSTN gateway, and a PSTN gateway to translate signaling and media between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="4eca4-124">若是電話撥入式會議，您必須至少部署一個中繼伺服器，並至少進行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="4eca4-124">For dial-in conferencing, you must deploy at least one Mediation Server and at least one of the following:</span></span>
    
      - <span data-ttu-id="4eca4-125">PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="4eca4-125">PSTN gateway</span></span>
    
      - <span data-ttu-id="4eca4-126">IP-PBX</span><span class="sxs-lookup"><span data-stu-id="4eca4-126">IP-PBX</span></span>
    
      - <span data-ttu-id="4eca4-127">會話邊界控制器（SBC）（適用于您透過設定 SIP 主幹來連接的網際網路電話服務提供者）</span><span class="sxs-lookup"><span data-stu-id="4eca4-127">Session Border Controller (SBC) (for an Internet telephony service provider to which you connect by configuring a SIP trunk)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4eca4-128">如果您也要部署企業語音，中繼伺服器和 PSTN 閘道是企業語音部署的一部分。</span><span class="sxs-lookup"><span data-stu-id="4eca4-128">If you are also deploying Enterprise Voice, Mediation Server and PSTN gateways are part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="4eca4-129">如果您沒有部署企業語音，您必須至少部署一個中繼伺服器以及至少一個 PSTN 閘道、IP PBX 或 SBC （適用于電話撥入式會議）。</span><span class="sxs-lookup"><span data-stu-id="4eca4-129">If you are not deploying Enterprise Voice, you need to deploy at least one Mediation Server and at least one PSTN gateway, IP-PBX, or SBC for dial-in conferencing.</span></span>

    
    </div>

  - <span data-ttu-id="4eca4-130">**[檔案存放區**   ] 檔案存放區用於記錄的名稱音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="4eca4-130">**File store**   File store is used for recorded name audio files.</span></span> <span data-ttu-id="4eca4-131">檔案存放區是每個企業版或標準版部署中的標準元件。</span><span class="sxs-lookup"><span data-stu-id="4eca4-131">File Store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="4eca4-132">**[使用者商店**   ] 使用者商店是用來儲存使用者 Lync Server 2013 pin。</span><span class="sxs-lookup"><span data-stu-id="4eca4-132">**User store**   User store is used to store user Lync Server 2013 PINs.</span></span> <span data-ttu-id="4eca4-133">Pin 會散列。</span><span class="sxs-lookup"><span data-stu-id="4eca4-133">PINs are hashed.</span></span> <span data-ttu-id="4eca4-134">使用者存放區是每個企業版或標準版部署中的標準元件。</span><span class="sxs-lookup"><span data-stu-id="4eca4-134">The User store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="4eca4-135">**Lync server [控制台**   ] 中的某些撥入設定可以使用 Lync Server [控制台] 進行設定。</span><span class="sxs-lookup"><span data-stu-id="4eca4-135">**Lync Server Control Panel**   Some dial-in settings can be configured by using Lync Server Control Panel.</span></span>

  - <span data-ttu-id="4eca4-136">**Lync server 管理命令**   介面：您可以使用 lync server 管理命令介面 Cmdlet 來設定所有撥入設定。</span><span class="sxs-lookup"><span data-stu-id="4eca4-136">**Lync Server Management Shell**   All dial-in settings can be configured by using Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="4eca4-137">Lync Server 管理命令介面 Cmdlet 可用於部署、設定、執行、監控，以及疑難排解會議助理應用程式與會議發佈應用程式。</span><span class="sxs-lookup"><span data-stu-id="4eca4-137">Lync Server Management Shell cmdlets are available for deploying, configuring, running, monitoring, and troubleshooting Conferencing Attendant application and Conferencing Announcement application.</span></span> <span data-ttu-id="4eca4-138">如需特定 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="4eca4-138">For details about specific cmdlets, see Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="4eca4-139">支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="4eca4-139">Supported Topologies</span></span>

<span data-ttu-id="4eca4-140">在 Lync Server 2013 中，執行會議服務的伺服器總是與前端伺服器或標準版伺服器 collocated。</span><span class="sxs-lookup"><span data-stu-id="4eca4-140">In Lync Server 2013, the server running conferencing services is always collocated with the Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="4eca4-141">在初始部署期間，拓撲建立器可讓您選擇在拓撲中包含會議。</span><span class="sxs-lookup"><span data-stu-id="4eca4-141">During your initial deployment, Topology Builder gives you the option to include conferencing in your topology.</span></span> <span data-ttu-id="4eca4-142">您也可以使用拓撲建立器，將會議新增至現有的部署。</span><span class="sxs-lookup"><span data-stu-id="4eca4-142">You can also use Topology Builder to add conferencing to an existing deployment.</span></span> <span data-ttu-id="4eca4-143">如需詳細資訊，請參閱[在 Lync Server 2013 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="4eca4-143">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

<div>

## <a name="dial-in-conferencing-toplogies"></a><span data-ttu-id="4eca4-144">電話撥入式會議 Toplogies</span><span class="sxs-lookup"><span data-stu-id="4eca4-144">Dial in Conferencing Toplogies</span></span>

<span data-ttu-id="4eca4-145">您可以在下列拓撲和配置中部署電話撥入式會議：</span><span class="sxs-lookup"><span data-stu-id="4eca4-145">You can deploy dial-in conferencing in the following topologies and configurations:</span></span>

  - <span data-ttu-id="4eca4-146">Lync Server 2013 標準版</span><span class="sxs-lookup"><span data-stu-id="4eca4-146">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="4eca4-147">Lync Server 2013 企業版</span><span class="sxs-lookup"><span data-stu-id="4eca4-147">Lync Server 2013 Enterprise Edition</span></span>

  - <span data-ttu-id="4eca4-148">具備或不使用企業語音</span><span class="sxs-lookup"><span data-stu-id="4eca4-148">With or without Enterprise Voice</span></span>

<span data-ttu-id="4eca4-149">您可以在中央網站中部署應用程式服務、會議助理應用程式及會議公告應用程式，但不能在分支網站中進行。</span><span class="sxs-lookup"><span data-stu-id="4eca4-149">You can deploy Application service, Conferencing Attendant application, and Conferencing Announcement application in a central site, but not in a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4eca4-150">如果您要部署電話撥入式會議，您必須在部署 Lync Server 2013 會議的每個池中部署它。</span><span class="sxs-lookup"><span data-stu-id="4eca4-150">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="4eca4-151">您不需要在每個池中指派存取號碼，但您必須在每個池中部署電話撥入式會議功能。</span><span class="sxs-lookup"><span data-stu-id="4eca4-151">You do not need to assign access numbers in every pool, but you must deploy the dial-in conferencing feature in every pool.</span></span> <span data-ttu-id="4eca4-152">當使用者從某個池中呼叫存取號碼以在不同的池中加入 Lync Server 2013 會議時，此需求支援所記錄的名稱功能。</span><span class="sxs-lookup"><span data-stu-id="4eca4-152">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a><span data-ttu-id="4eca4-153">Lync Server 2013 與 Office Web Apps 支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="4eca4-153">Supported Topologies for Lync Server 2013 and Office Web Apps</span></span>

<span data-ttu-id="4eca4-154">Lync Server 2013 提供下列配置 Office Web Apps 伺服器的方式。</span><span class="sxs-lookup"><span data-stu-id="4eca4-154">Lync Server 2013 provides the following ways to configure Office Web Apps Server.</span></span> <span data-ttu-id="4eca4-155">視您的需求而定，您可以：</span><span class="sxs-lookup"><span data-stu-id="4eca4-155">Depending on your needs you can:</span></span>

  - <span data-ttu-id="4eca4-156">**在您組織的防火牆之後及同一網路區域中，安裝 Lync Server 2013 與 Office Web Apps Server 內部部署。**</span><span class="sxs-lookup"><span data-stu-id="4eca4-156">**Install both Lync Server 2013 and Office Web Apps Server on-premises behind your organization’s firewall, and in the same network zone.**</span></span> <span data-ttu-id="4eca4-157">透過此拓朴，系統將會透過您的反向 proxy 伺服器提供對 Office Web Apps 伺服器的外部存取。</span><span class="sxs-lookup"><span data-stu-id="4eca4-157">With this topology, external access to Office Web Apps Server will be provided through your reverse proxy server.</span></span> <span data-ttu-id="4eca4-158">Lync Server 2013 與 Office Web Apps Server （或 Office Web Apps 伺服器群）都是在內部部署和組織的防火牆後安裝。</span><span class="sxs-lookup"><span data-stu-id="4eca4-158">Both Lync Server 2013 and Office Web Apps Server (or an Office Web Apps Server farm) are installed on-premises and behind your organization's firewall.</span></span> <span data-ttu-id="4eca4-159">在理想的情況下，您應該在與 Lync Server 相同的網路區域中安裝 Office Web Apps 伺服器。</span><span class="sxs-lookup"><span data-stu-id="4eca4-159">Ideally, you should install Office Web Apps Server in the same network zone as Lync Server.</span></span>
    
    <span data-ttu-id="4eca4-160">外部 Lync 用戶端可以使用反向 proxy 伺服器連線至 Lync Server 2013 與 Office Web Apps 伺服器，該伺服器是接受網際網路要求並將其轉寄給內部網路的伺服器。</span><span class="sxs-lookup"><span data-stu-id="4eca4-160">External Lync clients can connect to Lync Server 2013 and to Office Web Apps Server by using a reverse proxy server, which is a server that takes requests from the Internet and forwards them to the internal network.</span></span> <span data-ttu-id="4eca4-161">（內部用戶端不需要使用反向 proxy 伺服器，因為它們可以直接連線到 Office Web Apps 伺服器）。如果您想要使用僅供 Lync Server 2013 使用的專用 Office Web Apps 伺服器群，此拓朴效果最佳。</span><span class="sxs-lookup"><span data-stu-id="4eca4-161">(Internal clients do not need to use the reverse proxy server because they can connect to Office Web Apps Server directly.) This topology works best if you want to use a dedicated Office Web Apps Server farm that is only used by Lync Server 2013.</span></span>

  - <span data-ttu-id="4eca4-162">**使用外部部署的 Office Web Apps 伺服器**</span><span class="sxs-lookup"><span data-stu-id="4eca4-162">**Using an externally deployed Office Web Apps Server**</span></span>
    
    <span data-ttu-id="4eca4-163">在此拓朴中，Lync Server 2013 是在內部部署，並使用在 Lync Server 網路區域外部部署的 Office Web Apps 伺服器。</span><span class="sxs-lookup"><span data-stu-id="4eca4-163">In this topology, Lync Server 2013 is deployed on-premises, and uses an Office Web Apps Server that is deployed outside of Lync Server network zone.</span></span> <span data-ttu-id="4eca4-164">當 Office Web Apps Server 在公司中的多個應用程式間共用，且已部署在要求 Lync Server 使用 Office Web Apps Server 外部介面的網路（反之亦然）時，可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="4eca4-164">This may happen when Office Web Apps Server is shared across multiple applications in the corporation and is deployed in a network requiring Lync Server to use the external interface of Office Web Apps Server and vice versa.</span></span>
    
    <span data-ttu-id="4eca4-165">您不需要安裝反向 proxy 伺服器;相反地，從 Office Web Apps 伺服器到 Lync Server 2013 的所有要求都會透過您的邊緣伺服器進行路由。</span><span class="sxs-lookup"><span data-stu-id="4eca4-165">You do not need to install a reverse proxy server; instead, all the requests from the Office Web Apps Server to Lync Server 2013 are routed through your Edge Server.</span></span> <span data-ttu-id="4eca4-166">您的內部和外部 Lync 用戶端都是使用外部 URL 連線到 Office Web Apps 伺服器。</span><span class="sxs-lookup"><span data-stu-id="4eca4-166">Both your internal and your external Lync clients connect to Office Web Apps Server using the external URL.</span></span>
    
    <span data-ttu-id="4eca4-167">如果 Office Web Apps 伺服器是在您的內部防火牆外部署，請選取 [ **Office Web Apps 伺服器] 部署在拓撲結構建立器中的外部網路（也就是 [週邊/網際網路]）** 。</span><span class="sxs-lookup"><span data-stu-id="4eca4-167">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** in Topology Builder.</span></span> <span data-ttu-id="4eca4-168">如需詳細資訊，請參閱設定[與 Office Web Apps server 和 Lync Server 2013 的整合](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="4eca4-168">For more details see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="4eca4-169">不論您選取何種拓撲，請務必開啟正確的防火牆埠。</span><span class="sxs-lookup"><span data-stu-id="4eca4-169">Regardless of the topology you select, it is critical that the correct firewall ports be opened.</span></span> <span data-ttu-id="4eca4-170">您必須確認無法透過 Office Web Apps 伺服器、負載平衡器或 Lync Server 上的防火牆封鎖 DNS 名稱、IP 位址和埠。</span><span class="sxs-lookup"><span data-stu-id="4eca4-170">You must make sure that DNS names, IP addresses, and ports are not blocked by firewalls on the Office Web Apps Server, the load balancer, or Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4eca4-171">提供外部 Office Web Apps 伺服器存取權的另一個選項就是在周邊網路中部署伺服器。</span><span class="sxs-lookup"><span data-stu-id="4eca4-171">Another option for providing external access to Office Web Apps Server is to deploy the server in the perimeter network.</span></span> <span data-ttu-id="4eca4-172">如果您選擇這樣做，請記住 Office Web Apps Server 安裝程式需要伺服器電腦成為您 Active Directory 網域的成員。</span><span class="sxs-lookup"><span data-stu-id="4eca4-172">If you elect to do this, keep in mind that Office Web Apps Server setup requires the server computer to be a member of your Active Directory domain.</span></span> <span data-ttu-id="4eca4-173">除非您的網路原則允許周邊網路中的電腦成為 Active Directory 網域成員，否則建議您不要在周邊網路中安裝 Office Web Apps 伺服器。</span><span class="sxs-lookup"><span data-stu-id="4eca4-173">Unless your network policy allows computers in the perimeter network to be Active Directory domain members, it is recommended that you do not install Office Web Apps Server in the perimeter network.</span></span> <span data-ttu-id="4eca4-174">相反地，您應該在內部網路中安裝 Office Web Apps 伺服器，並透過您的反向 proxy 伺服器提供外部使用者存取。</span><span class="sxs-lookup"><span data-stu-id="4eca4-174">Instead, you should install Office Web Apps Server in the internal network and provide external user access through your reverse proxy server.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

