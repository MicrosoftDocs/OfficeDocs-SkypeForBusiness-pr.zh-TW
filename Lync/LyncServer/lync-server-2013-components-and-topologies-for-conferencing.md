---
title: 會議的 Lync Server 2013 元件和拓撲
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
ms.openlocfilehash: e4c843bbe5c34aaf0ad98ca73e8ebd33820b87d2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="3dff4-102">Lync Server 2013 中的會議的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="3dff4-102">Components and topologies for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3dff4-103">_**上次修改主題：** 2013年-02-04_</span><span class="sxs-lookup"><span data-stu-id="3dff4-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="3dff4-104">當您在拓撲產生器] 中選取會議時，會議部署為前端伺服器或 Standard Edition server 的一部分。</span><span class="sxs-lookup"><span data-stu-id="3dff4-104">When you select conferencing in Topology Builder, conferencing is deployed as part of the Front End Server or Standard Edition server.</span></span> <span data-ttu-id="3dff4-105">電話撥入式會議和 PowerPoint 共用需要額外的元件和設定。</span><span class="sxs-lookup"><span data-stu-id="3dff4-105">Dial-in conferencing and PowerPoint sharing requires additional components and configuration.</span></span> <span data-ttu-id="3dff4-106">下列各節說明支援的元件和拓撲 web 會議、 A / V 會議及電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="3dff4-106">The following sections describe the supported components and topologies for web conferencing, A/V conferencing, and dial-in conferencing.</span></span>

<div>

## <a name="supported-components"></a><span data-ttu-id="3dff4-107">支援的元件</span><span class="sxs-lookup"><span data-stu-id="3dff4-107">Supported Components</span></span>

<span data-ttu-id="3dff4-108">元件只有 web 會議和 A / V 會議要求是貴組織的前端伺服器或 Standard Edition 伺服器。</span><span class="sxs-lookup"><span data-stu-id="3dff4-108">The only components web conferencing and A/V conferencing require are your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="3dff4-109">前端伺服器和 Standard Edition server 的硬體和軟體需求清單，請參閱[支援 Lync Server 2013 的](lync-server-2013-supported-hardware.md)軟硬體[的 Server software and Lync Server 2013 中支援的基礎結構](lync-server-2013-server-software-and-infrastructure-support.md)。</span><span class="sxs-lookup"><span data-stu-id="3dff4-109">For a list of hardware and software requirements for the Front End Servers and Standard Edition servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

<span data-ttu-id="3dff4-110">Lync Server 2013 使用 Office Web Apps 與 Office Web Apps Server 來處理共用和 PowerPoint 簡報的轉譯。</span><span class="sxs-lookup"><span data-stu-id="3dff4-110">Lync Server 2013 uses Office Web Apps and the Office Web Apps Server to handle sharing and rendering of PowerPoint presentations.</span></span> <span data-ttu-id="3dff4-111">如需安裝及設定 Office Web Apps Server 的詳細資訊，請參閱[設定整合 Office Web Apps Server 與 Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="3dff4-111">For details about installing and configuring the Office Web Apps Server, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="3dff4-112">除了需求為 web 會議和 A / V 會議、 電話撥入式會議使用下列的 Lync Server 2013 元件：</span><span class="sxs-lookup"><span data-stu-id="3dff4-112">In addition to the requirements for web conferencing and A/V conferencing, dial-in conferencing uses the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="3dff4-113">**應用程式服務**   應用程式服務提供的平台的部署，裝載，及管理整合通訊 (UC) 應用程式。</span><span class="sxs-lookup"><span data-stu-id="3dff4-113">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications (UC) applications.</span></span> <span data-ttu-id="3dff4-114">電話撥入式會議使用兩個需要應用程式服務的 UC 應用程式： 會議服務員和會議宣告服務。</span><span class="sxs-lookup"><span data-stu-id="3dff4-114">Dial-in conferencing uses two UC applications that require Application service: Conferencing Attendant and Conferencing Announcement.</span></span> <span data-ttu-id="3dff4-115">應用程式服務已安裝並啟用每個前端伺服器上的前端集區中，每個 Standard Edition server 上的預設，當您部署會議工作負載，並選取撥入式會議選項。</span><span class="sxs-lookup"><span data-stu-id="3dff4-115">Application service is installed and activated by default on every Front End Server in a Front End pool and on every Standard Edition server when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="3dff4-116">**會議服務員應用程式**   會議服務員應用程式是可接受公用交換的電話網路 (PSTN) 來電、 播放提示，以及聯結的呼叫的整合的通訊應用程式 / V 會議。</span><span class="sxs-lookup"><span data-stu-id="3dff4-116">**Conferencing Attendant application**   Conferencing Attendant application is a unified communications application that accepts public switched telephone network (PSTN) calls, plays prompts, and joins the calls to an A/V conference.</span></span> <span data-ttu-id="3dff4-117">會議服務員應用程式已安裝並啟用根據預設，當您部署會議工作負載，並選取撥入式會議選項。</span><span class="sxs-lookup"><span data-stu-id="3dff4-117">Conferencing Attendant application is installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="3dff4-118">**會議宣告應用程式**   會議宣告應用程式是整合的通訊應用程式，會播放撥號音，並提示上執行某些動作 PSTN 參與者、 當參與者加入或離開會議，例如參與者都設為靜音或解除靜音、 某人輸入會議大廳，或會議已鎖定或解除鎖定。</span><span class="sxs-lookup"><span data-stu-id="3dff4-118">**Conferencing Announcement application**   Conferencing Announcement application is a unified communications application that plays tones and prompts to PSTN participants on certain actions, such as when participants join or leave a conference, participants are muted or unmuted, someone enters the conference lobby, or the conference is locked or unlocked.</span></span> <span data-ttu-id="3dff4-119">會議宣告應用程式也支援從電話鍵台複頻式訊號 (DTMF) 命令。</span><span class="sxs-lookup"><span data-stu-id="3dff4-119">Conferencing Announcement application also supports dual-tone multifrequency (DTMF) commands from the phone keypad.</span></span> <span data-ttu-id="3dff4-120">會議宣告應用程式會自動安裝及啟動依預設，當您部署會議工作負載，並選取撥入式會議選項。</span><span class="sxs-lookup"><span data-stu-id="3dff4-120">Conferencing Announcement application is automatically installed and activated by default when you deploy a Conferencing workload and select the dial-in conferencing option.</span></span>

  - <span data-ttu-id="3dff4-121">**電話撥入式會議設定] 頁面上**   電話撥入式會議設定 」 頁面會顯示會議撥入號碼與其可用的語言，指派會議資訊 (也就是不需要排定的會議)，在會議 DTMF 控制項，並支援管理個人識別碼 (PIN) 和指派的會議資訊。</span><span class="sxs-lookup"><span data-stu-id="3dff4-121">**Dial-in Conferencing Settings page**   The Dial-in Conferencing Settings page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="3dff4-122">[電話撥入式會議設定] 頁面上會自動安裝 Web 服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="3dff4-122">The Dial-in Conferencing Settings page is automatically installed as part of Web Services.</span></span>

  - <span data-ttu-id="3dff4-123">**Lync Server 2013、 中繼伺服器和 PSTN 閘道**   撥入式會議需要 Lync Server 2013 和 PSTN 閘道，與 PSTN 閘道之間翻譯訊號及媒體中繼伺服器和 PSTN 閘道之間的翻譯訊號的中繼伺服器 （和媒體上的，在某些組態中）。</span><span class="sxs-lookup"><span data-stu-id="3dff4-123">**Lync Server 2013, Mediation Server and PSTN gateway**   Dial-in conferencing requires a Mediation Server to translate signaling (and media, in some configurations) between Lync Server 2013 and the PSTN gateway, and a PSTN gateway to translate signaling and media between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="3dff4-124">電話撥入式會議，您必須部署至少一部中繼伺服器和至少其中一個下列：</span><span class="sxs-lookup"><span data-stu-id="3dff4-124">For dial-in conferencing, you must deploy at least one Mediation Server and at least one of the following:</span></span>
    
      - <span data-ttu-id="3dff4-125">PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="3dff4-125">PSTN gateway</span></span>
    
      - <span data-ttu-id="3dff4-126">IP PBX</span><span class="sxs-lookup"><span data-stu-id="3dff4-126">IP-PBX</span></span>
    
      - <span data-ttu-id="3dff4-127">工作階段界限控制器 (SBC) （適用於網際網路電話語音服務提供者您藉由設定 SIP 主幹連接）</span><span class="sxs-lookup"><span data-stu-id="3dff4-127">Session Border Controller (SBC) (for an Internet telephony service provider to which you connect by configuring a SIP trunk)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3dff4-128">如果您也要部署 Enterprise Voice，中繼伺服器和 PSTN 閘道屬於 Enterprise Voice 部署。</span><span class="sxs-lookup"><span data-stu-id="3dff4-128">If you are also deploying Enterprise Voice, Mediation Server and PSTN gateways are part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="3dff4-129">如果您不部署 Enterprise Voice，您需要針對撥入式會議部署至少一部中繼伺服器和至少一個 PSTN 閘道、 IP-PBX 或 SBC。</span><span class="sxs-lookup"><span data-stu-id="3dff4-129">If you are not deploying Enterprise Voice, you need to deploy at least one Mediation Server and at least one PSTN gateway, IP-PBX, or SBC for dial-in conferencing.</span></span>

    
    </div>

  - <span data-ttu-id="3dff4-130">**檔案存放區**   檔案存放區用於記錄名稱音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="3dff4-130">**File store**   File store is used for recorded name audio files.</span></span> <span data-ttu-id="3dff4-131">檔案存放區是每個 Enterprise Edition 或 Standard Edition 部署中的標準元件。</span><span class="sxs-lookup"><span data-stu-id="3dff4-131">File Store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="3dff4-132">**使用者存放區**   使用者存放區用來儲存使用者 Lync Server 2013 的 pin 碼。</span><span class="sxs-lookup"><span data-stu-id="3dff4-132">**User store**   User store is used to store user Lync Server 2013 PINs.</span></span> <span data-ttu-id="3dff4-133">Pin 碼都會雜湊。</span><span class="sxs-lookup"><span data-stu-id="3dff4-133">PINs are hashed.</span></span> <span data-ttu-id="3dff4-134">使用者存放區是每個 Enterprise Edition 或 Standard Edition 部署中的標準元件。</span><span class="sxs-lookup"><span data-stu-id="3dff4-134">The User store is a standard component in every Enterprise Edition or Standard Edition deployment.</span></span>

  - <span data-ttu-id="3dff4-135">**Lync Server Control Panel**   某些撥號對應表設定可以設定使用 Lync Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="3dff4-135">**Lync Server Control Panel**   Some dial-in settings can be configured by using Lync Server Control Panel.</span></span>

  - <span data-ttu-id="3dff4-136">**Lync Server 管理命令介面**   所有電話撥入式可以設定使用 Lync Server 管理命令介面指令程式。</span><span class="sxs-lookup"><span data-stu-id="3dff4-136">**Lync Server Management Shell**   All dial-in settings can be configured by using Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="3dff4-137">Lync Server 管理命令介面指令程式可供部署、 設定、 執行、 監視和疑難排解會議服務員應用程式和會議宣告應用程式。</span><span class="sxs-lookup"><span data-stu-id="3dff4-137">Lync Server Management Shell cmdlets are available for deploying, configuring, running, monitoring, and troubleshooting Conferencing Attendant application and Conferencing Announcement application.</span></span> <span data-ttu-id="3dff4-138">如需特定 cmdlet 的詳細資訊，請參閱 < Lync Server 管理命令介面文件。</span><span class="sxs-lookup"><span data-stu-id="3dff4-138">For details about specific cmdlets, see Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="3dff4-139">支援的拓撲</span><span class="sxs-lookup"><span data-stu-id="3dff4-139">Supported Topologies</span></span>

<span data-ttu-id="3dff4-140">在 Lync Server 2013 中，執行會議服務之伺服器一律與前端伺服器或 Standard Edition server 組合。</span><span class="sxs-lookup"><span data-stu-id="3dff4-140">In Lync Server 2013, the server running conferencing services is always collocated with the Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="3dff4-141">在您初始部署期間拓撲產生器] 讓您選擇来包含在您的拓撲中的會議。</span><span class="sxs-lookup"><span data-stu-id="3dff4-141">During your initial deployment, Topology Builder gives you the option to include conferencing in your topology.</span></span> <span data-ttu-id="3dff4-142">您也可以使用拓撲產生器將會議新增至現有的部署。</span><span class="sxs-lookup"><span data-stu-id="3dff4-142">You can also use Topology Builder to add conferencing to an existing deployment.</span></span> <span data-ttu-id="3dff4-143">如需詳細資訊，請參閱[定義和設定 Lync Server 2013 中的拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="3dff4-143">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

<div>

## <a name="dial-in-conferencing-toplogies"></a><span data-ttu-id="3dff4-144">撥入式會議拓撲</span><span class="sxs-lookup"><span data-stu-id="3dff4-144">Dial in Conferencing Toplogies</span></span>

<span data-ttu-id="3dff4-145">您可以部署電話撥入式會議中的下列拓撲和設定：</span><span class="sxs-lookup"><span data-stu-id="3dff4-145">You can deploy dial-in conferencing in the following topologies and configurations:</span></span>

  - <span data-ttu-id="3dff4-146">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="3dff4-146">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="3dff4-147">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="3dff4-147">Lync Server 2013 Enterprise Edition</span></span>

  - <span data-ttu-id="3dff4-148">包含或不含 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="3dff4-148">With or without Enterprise Voice</span></span>

<span data-ttu-id="3dff4-149">您可以部署應用程式服務、 會議服務員應用程式和會議宣告應用程式在中央網站，但不是在分支網站。</span><span class="sxs-lookup"><span data-stu-id="3dff4-149">You can deploy Application service, Conferencing Attendant application, and Conferencing Announcement application in a central site, but not in a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3dff4-150">如果您部署電話撥入式會議，您必須將它部署中部署 Lync Server 2013 會議每個集區。</span><span class="sxs-lookup"><span data-stu-id="3dff4-150">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="3dff4-151">您不需要指派存取號碼，在每個集區，但您必須部署中每個集區的撥入式會議功能。</span><span class="sxs-lookup"><span data-stu-id="3dff4-151">You do not need to assign access numbers in every pool, but you must deploy the dial-in conferencing feature in every pool.</span></span> <span data-ttu-id="3dff4-152">這項要求支援錄製的名稱 」 功能，當使用者從一個集區加入 Lync Server 2013 會議的不同的集區中呼叫的存取號碼。</span><span class="sxs-lookup"><span data-stu-id="3dff4-152">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a><span data-ttu-id="3dff4-153">支援的 Lync Server 2013 和 Office Web Apps 的拓撲</span><span class="sxs-lookup"><span data-stu-id="3dff4-153">Supported Topologies for Lync Server 2013 and Office Web Apps</span></span>

<span data-ttu-id="3dff4-154">Lync Server 2013 提供下列方法來設定 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="3dff4-154">Lync Server 2013 provides the following ways to configure Office Web Apps Server.</span></span> <span data-ttu-id="3dff4-155">您可以根據您的需求：</span><span class="sxs-lookup"><span data-stu-id="3dff4-155">Depending on your needs you can:</span></span>

  - <span data-ttu-id="3dff4-156">**安裝 Lync Server 2013 與 Office Web Apps Server 內部部署組織的防火牆後面，並位於相同的網路地區。**</span><span class="sxs-lookup"><span data-stu-id="3dff4-156">**Install both Lync Server 2013 and Office Web Apps Server on-premises behind your organization’s firewall, and in the same network zone.**</span></span> <span data-ttu-id="3dff4-157">與此拓撲中，將透過您的反向 proxy 伺服器提供 Office Web Apps Server 的外部存取。</span><span class="sxs-lookup"><span data-stu-id="3dff4-157">With this topology, external access to Office Web Apps Server will be provided through your reverse proxy server.</span></span> <span data-ttu-id="3dff4-158">同時 Lync Server 2013 和 Office Web Apps Server 安裝 （或 Office Web Apps Server 伺服器陣列） 會在內部和貴組織的防火牆後方。</span><span class="sxs-lookup"><span data-stu-id="3dff4-158">Both Lync Server 2013 and Office Web Apps Server (or an Office Web Apps Server farm) are installed on-premises and behind your organization's firewall.</span></span> <span data-ttu-id="3dff4-159">理想狀況下，您應該在 Lync Server 位於相同網路地區中安裝 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="3dff4-159">Ideally, you should install Office Web Apps Server in the same network zone as Lync Server.</span></span>
    
    <span data-ttu-id="3dff4-160">外部的 Lync 用戶端可以將使用反向 proxy 伺服器，也就是會接受來自網際網路的要求，並將其轉寄至內部網路的伺服器連線到 Lync Server 2013 以及 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="3dff4-160">External Lync clients can connect to Lync Server 2013 and to Office Web Apps Server by using a reverse proxy server, which is a server that takes requests from the Internet and forwards them to the internal network.</span></span> <span data-ttu-id="3dff4-161">（內部用戶端不需要使用反向 proxy 伺服器，因為他們可以直接連線至 Office Web Apps Server）。如果您想要使用專用的 Office Web Apps Server 伺服器陣列只使用 Lync Server 2013，這種拓撲的效果最佳。</span><span class="sxs-lookup"><span data-stu-id="3dff4-161">(Internal clients do not need to use the reverse proxy server because they can connect to Office Web Apps Server directly.) This topology works best if you want to use a dedicated Office Web Apps Server farm that is only used by Lync Server 2013.</span></span>

  - <span data-ttu-id="3dff4-162">**使用外部部署的 Office Web Apps Server**</span><span class="sxs-lookup"><span data-stu-id="3dff4-162">**Using an externally deployed Office Web Apps Server**</span></span>
    
    <span data-ttu-id="3dff4-163">在此拓撲中，Lync Server 2013 內部部署，且使用 Lync Server 網路區域外部署 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="3dff4-163">In this topology, Lync Server 2013 is deployed on-premises, and uses an Office Web Apps Server that is deployed outside of Lync Server network zone.</span></span> <span data-ttu-id="3dff4-164">當 Office Web Apps Server 跨公司內的多個應用程式共用，並需要 Lync Server 以使用 Office Web Apps server，反之亦然的外部介面的網路中部署可能發生這種情形。</span><span class="sxs-lookup"><span data-stu-id="3dff4-164">This may happen when Office Web Apps Server is shared across multiple applications in the corporation and is deployed in a network requiring Lync Server to use the external interface of Office Web Apps Server and vice versa.</span></span>
    
    <span data-ttu-id="3dff4-165">您不需要安裝的反向 proxy 伺服器;相反地，會透過 Edge Server 路由傳送的所有要求與 Office Web Apps Server 到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="3dff4-165">You do not need to install a reverse proxy server; instead, all the requests from the Office Web Apps Server to Lync Server 2013 are routed through your Edge Server.</span></span> <span data-ttu-id="3dff4-166">您的內部和外部的 Lync 用戶端連線至 Office Web Apps Server 使用的外部 URL。</span><span class="sxs-lookup"><span data-stu-id="3dff4-166">Both your internal and your external Lync clients connect to Office Web Apps Server using the external URL.</span></span>
    
    <span data-ttu-id="3dff4-167">如果 Office Web Apps Server 部署在內部防火牆外，然後選取 [ **Office Web Apps Server 部署在外部網路 （亦即周邊/網際網路）** ] 選項，在拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="3dff4-167">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** in Topology Builder.</span></span> <span data-ttu-id="3dff4-168">如需詳細資訊請參閱[設定整合 Office Web Apps Server 與 Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="3dff4-168">For more details see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="3dff4-169">不論您選擇的拓撲，很重要，開啟正確的防火牆連接埠。</span><span class="sxs-lookup"><span data-stu-id="3dff4-169">Regardless of the topology you select, it is critical that the correct firewall ports be opened.</span></span> <span data-ttu-id="3dff4-170">您必須確定的 DNS 名稱、 IP 位址和連接埠不被防火牆封鎖 Office Web Apps Server、 負載平衡器或 Lync Server 上。</span><span class="sxs-lookup"><span data-stu-id="3dff4-170">You must make sure that DNS names, IP addresses, and ports are not blocked by firewalls on the Office Web Apps Server, the load balancer, or Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3dff4-171">Office Web Apps Server 來提供外部存取的另一個選項是部署在周邊網路中的伺服器。</span><span class="sxs-lookup"><span data-stu-id="3dff4-171">Another option for providing external access to Office Web Apps Server is to deploy the server in the perimeter network.</span></span> <span data-ttu-id="3dff4-172">如果您選擇若要這麼做，請記住，Office Web Apps Server 安裝程式需要伺服器電腦是 Active Directory 網域的成員。</span><span class="sxs-lookup"><span data-stu-id="3dff4-172">If you elect to do this, keep in mind that Office Web Apps Server setup requires the server computer to be a member of your Active Directory domain.</span></span> <span data-ttu-id="3dff4-173">除非您的網路原則允許在周邊網路 Active Directory 網域成員電腦，否則建議您不要在周邊網路中安裝 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="3dff4-173">Unless your network policy allows computers in the perimeter network to be Active Directory domain members, it is recommended that you do not install Office Web Apps Server in the perimeter network.</span></span> <span data-ttu-id="3dff4-174">相反地，您應該在內部網路中安裝 Office Web Apps Server，並提供透過反向 proxy 伺服器的外部使用者存取。</span><span class="sxs-lookup"><span data-stu-id="3dff4-174">Instead, you should install Office Web Apps Server in the internal network and provide external user access through your reverse proxy server.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

