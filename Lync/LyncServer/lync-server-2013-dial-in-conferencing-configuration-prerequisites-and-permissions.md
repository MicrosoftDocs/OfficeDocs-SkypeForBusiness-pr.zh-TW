---
title: 電話撥入式會議組態先決條件和權限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a60fc58e0ec40dadff044257d43629c2f3cb01ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a><span data-ttu-id="6e459-102">Lync Server 2013 中的電話撥入式會議組態先決條件和權限</span><span class="sxs-lookup"><span data-stu-id="6e459-102">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e459-103">_**主題上次修改日期：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="6e459-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="6e459-104">電話撥入式會議是 Lync Server 2013 會議工作負載的選用元件。</span><span class="sxs-lookup"><span data-stu-id="6e459-104">Dial-in conferencing is an optional component of the Lync Server 2013 Conferencing workload.</span></span> <span data-ttu-id="6e459-105">在您使用 [拓撲建立器] 設計拓撲，然後設定您的 [前端] 池或標準版伺服器之後，您必須先安裝所需的元件，才能設定電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="6e459-105">The components you need to install before you can configure dial-in conferencing are deployed when you use the Topology Builder to design your topology and then set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="6e459-106">本主題說明您必須先完成的工作，才能設定電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="6e459-106">This topic describes what you need to have accomplished before you can configure dial-in conferencing.</span></span>

<span data-ttu-id="6e459-107">本節假設您已閱讀與會議工作負載和電話撥入式會議相關的規劃區段。</span><span class="sxs-lookup"><span data-stu-id="6e459-107">This section assumes that you have read the planning sections related to the Conferencing workload and dial-in conferencing in particular.</span></span>

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a><span data-ttu-id="6e459-108">電話撥入式會議設定的先決條件</span><span class="sxs-lookup"><span data-stu-id="6e459-108">Dial-in Conferencing Configuration Prerequisites</span></span>

<span data-ttu-id="6e459-109">電話撥入式會議需要下列 Lync Server 2013 元件：</span><span class="sxs-lookup"><span data-stu-id="6e459-109">Dial-in conferencing requires the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="6e459-110">整合通訊應用程式服務（UCAS）（稱為*應用程式服務*）</span><span class="sxs-lookup"><span data-stu-id="6e459-110">Unified Communications Application Service (UCAS) (called the *Application service*)</span></span>

  - <span data-ttu-id="6e459-111">會議助理應用程式</span><span class="sxs-lookup"><span data-stu-id="6e459-111">Conferencing Attendant application</span></span>

  - <span data-ttu-id="6e459-112">會議公告應用程式</span><span class="sxs-lookup"><span data-stu-id="6e459-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="6e459-113">電話撥入式會議設定網頁</span><span class="sxs-lookup"><span data-stu-id="6e459-113">Dial-in Conferencing Settings webpage</span></span>

  - <span data-ttu-id="6e459-114">至少有一個 Lync Server 2013 轉送伺服器和至少一個 PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="6e459-114">At least one Lync Server 2013 Mediation Server and at least one PSTN gateway</span></span>

<span data-ttu-id="6e459-115">當您使用 [拓撲建立器] 定義併發布拓撲，然後部署前端池或標準版伺服器時，就會部署這些元件。</span><span class="sxs-lookup"><span data-stu-id="6e459-115">You deploy these components when you use the Topology Builder to define and publish your topology and then deploy a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="6e459-116">如果您要部署企業語音，您應該先部署它，然後再設定電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="6e459-116">If you are deploying Enterprise Voice, you should deploy it before you configure dial-in conferencing.</span></span> <span data-ttu-id="6e459-117">如果您不是部署企業語音，您可以在部署前端池或標準版伺服器時，部署中繼伺服器和公用交換電話網絡（PSTN）閘道。</span><span class="sxs-lookup"><span data-stu-id="6e459-117">If you are not deploying Enterprise Voice, you can deploy a Mediation Server and a public switched telephone network (PSTN) gateway when you deploy your Front End pool or Standard Edition server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="6e459-118">如果您是從 Office 通訊伺服器 2007 R2 升級到 Lync Server 2013，請在您打算用來主持 Lync Server 2013 會議的每個池中部署電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="6e459-118">If you are upgrading from Office Communications Server 2007 R2 to Lync Server 2013, deploy dial-in conferencing in every pool that you plan to use to host Lync Server 2013 conferences.</span></span> <span data-ttu-id="6e459-119">如需有關移植電話撥入式會議的詳細資訊，請參閱<A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">從 Office 通訊伺服器 2007 R2 遷移到 Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="6e459-119">For details about migrating dial-in conferencing, see <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Migration from Office Communications Server 2007 R2 to Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="6e459-120">本節假設您已完成下列作業：</span><span class="sxs-lookup"><span data-stu-id="6e459-120">This section assumes that you have done the following:</span></span>

  - <span data-ttu-id="6e459-121">將最新的更新套用至您的 Office 通訊伺服器 2007 R2 環境（如果您要遷移至 Lync Server 2013）。</span><span class="sxs-lookup"><span data-stu-id="6e459-121">Applied the latest updates to your Office Communications Server 2007 R2 environment, if you are migrating to Lync Server 2013.</span></span>

  - <span data-ttu-id="6e459-122">使用 [拓撲建立器] 來設計及設定您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="6e459-122">Used Topology Builder to design and configure your topology.</span></span> <span data-ttu-id="6e459-123">在指定會議工作量時，您已選取 [電話撥入式會議] 選項。</span><span class="sxs-lookup"><span data-stu-id="6e459-123">While specifying the Conferencing workload, you selected the dial-in conferencing option.</span></span> <span data-ttu-id="6e459-124">如需定義拓朴的詳細資料，請參閱部署檔中的[Lync Server 2013 中的定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="6e459-124">For details about defining your topology, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="6e459-125">已發佈您的拓撲，並設定前端池或標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="6e459-125">Published your topology, and set up the Front End pool or Standard Edition server.</span></span> <span data-ttu-id="6e459-126">如需發佈拓撲及安裝 Lync Server 2013 的詳細資料，請參閱部署檔中的 [[部署 Lync server 2013](lync-server-2013-deploying-lync-server.md) ]。</span><span class="sxs-lookup"><span data-stu-id="6e459-126">For details about publishing the topology and installing Lync Server 2013, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="6e459-127">當您安裝已發佈的拓撲時，系統會在前端伺服器或標準版伺服器上安裝 [電話撥入式會議設定] 網頁，成為 Web 服務的一部分。</span><span class="sxs-lookup"><span data-stu-id="6e459-127">When you install your published topology, the Dial-in Conferencing Settings webpage is installed on the Front End Server or Standard Edition server as part of Web Services.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="6e459-128">如果您在部署 Lync Server 2013 之後，在 [拓撲建立器] 中變更了檔案存放區的路徑，您必須重新開機會議助理與會議發佈應用程式，才能使用新的路徑。</span><span class="sxs-lookup"><span data-stu-id="6e459-128">If you change the path for the File Store in Topology Builder after you deploy Lync Server 2013, you need to restart the Conferencing Attendant and Conferencing Announcement applications to use the new path.</span></span>

    
    </div>

  - <span data-ttu-id="6e459-129">已部署企業語音。</span><span class="sxs-lookup"><span data-stu-id="6e459-129">Deployed Enterprise Voice.</span></span> <span data-ttu-id="6e459-130">如果您不是部署企業語音，您可以在企業版前端伺服器或標準版伺服器上 collocated 中繼伺服器，或部署獨立的中繼伺服器，且已部署 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="6e459-130">If you are not deploying Enterprise Voice, you either collocated a Mediation Server on the Enterprise Edition Front End Server or the Standard Edition server, or you deployed a stand-alone Mediation Server, and you deployed a PSTN gateway.</span></span> <span data-ttu-id="6e459-131">如需部署企業語音的詳細資料，請參閱部署檔中的[Lync Server 2013 中的部署企業語音](lync-server-2013-deploying-enterprise-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="6e459-131">For details about deploying Enterprise Voice, see [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span> <span data-ttu-id="6e459-132">如需安裝獨立的中繼伺服器和 PSTN 閘道的詳細資訊，請參閱部署檔中的在[Lync Server 2013 中部署轉送伺服器和定義對等](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)。</span><span class="sxs-lookup"><span data-stu-id="6e459-132">For details about installing a stand-alone Mediation Server and PSTN gateway, see [Deploying Mediation Servers and defining peers in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) in the Deployment documentation.</span></span>

<span data-ttu-id="6e459-133">下列流程圖顯示您必須執行的步驟，才能設定電話撥入式會議，以及設定電話撥入式會議所需執行的步驟。</span><span class="sxs-lookup"><span data-stu-id="6e459-133">The following flowchart shows the steps that you must perform before you can configure dial-in conferencing and the steps that you perform to configure dial-in conferencing.</span></span>

<span data-ttu-id="6e459-134">**部署電話撥入式會議**</span><span class="sxs-lookup"><span data-stu-id="6e459-134">**Deploying dial-in conferencing**</span></span>

<span data-ttu-id="6e459-135">![電話撥入式會議部署流程圖][(images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "電話撥入式會議] 部署流程圖")</span><span class="sxs-lookup"><span data-stu-id="6e459-135">![Dial-in Conferencing Deployment flowchart](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Dial-in Conferencing Deployment flowchart")</span></span>

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a><span data-ttu-id="6e459-136">電話撥入式會議許可權</span><span class="sxs-lookup"><span data-stu-id="6e459-136">Dial-in Conferencing Permissions</span></span>

<span data-ttu-id="6e459-137">若要設定電話撥入式會議，您需要使用下列管理工具：</span><span class="sxs-lookup"><span data-stu-id="6e459-137">To configure dial-in conferencing, you need to use the following administrative tools:</span></span>

  - <span data-ttu-id="6e459-138">Lync Server 2013 [控制台]</span><span class="sxs-lookup"><span data-stu-id="6e459-138">Lync Server 2013 Control Panel</span></span>

  - <span data-ttu-id="6e459-139">Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="6e459-139">Lync Server Management Shell</span></span>

<span data-ttu-id="6e459-140">您可以使用這些管理工具來設定電話撥入式會議設定，以及撥號方案、原則及其他電話撥入式會議所需的設定。</span><span class="sxs-lookup"><span data-stu-id="6e459-140">You use these administrative tools to configure dial-in conferencing settings, and the dial plans, policies, and other settings that dial-in conferencing requires.</span></span>

<span data-ttu-id="6e459-141">設定電話撥入式會議需要下列任何一個管理角色，視任務而定：</span><span class="sxs-lookup"><span data-stu-id="6e459-141">Configuring dial-in conferencing requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="6e459-142">**CsVoiceAdministrator**   此系統管理員角色可以建立、設定及管理語音相關設定與原則。</span><span class="sxs-lookup"><span data-stu-id="6e459-142">**CsVoiceAdministrator**   This administrator role can create, configure, and manage voice-related settings and policies.</span></span>

  - <span data-ttu-id="6e459-143">**CsUserAdministrator**   此系統管理員角色可以啟用和停用 Lync Server 的使用者，並將現有的原則（例如會議原則及 PIN 原則）指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="6e459-143">**CsUserAdministrator**   This administrator role can enable and disable users for Lync Server and assign existing policies, such as conferencing policies and PIN policies, to users.</span></span>

  - <span data-ttu-id="6e459-144">**CsAdministrator**   此系統管理員角色可以執行 CsVoiceAdministrator 和 CsUserAdministrator 的所有工作。</span><span class="sxs-lookup"><span data-stu-id="6e459-144">**CsAdministrator**   This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6e459-145">請參閱</span><span class="sxs-lookup"><span data-stu-id="6e459-145">See Also</span></span>


[<span data-ttu-id="6e459-146">在 Lync Server 2013 中部署企業版語音</span><span class="sxs-lookup"><span data-stu-id="6e459-146">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

