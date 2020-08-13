---
title: 電話撥入式會議設定必要條件和許可權
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 791fa7e697622a4274655a77a2f02a6cdee140cb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a><span data-ttu-id="31446-102">Lync Server 2013 中的電話撥入式會議設定必要條件和許可權</span><span class="sxs-lookup"><span data-stu-id="31446-102">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31446-103">_**主題上次修改日期：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="31446-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="31446-104">電話撥入式會議是 Lync Server 2013 會議工作負載的選用元件。</span><span class="sxs-lookup"><span data-stu-id="31446-104">Dial-in conferencing is an optional component of the Lync Server 2013 Conferencing workload.</span></span> <span data-ttu-id="31446-105">在您使用拓撲產生器來設計拓撲，然後設定前端集區或 Standard Edition server 之前，您需要先安裝的元件，才能設定電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="31446-105">The components you need to install before you can configure dial-in conferencing are deployed when you use the Topology Builder to design your topology and then set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="31446-106">本主題說明您必須完成的工作，才能設定電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="31446-106">This topic describes what you need to have accomplished before you can configure dial-in conferencing.</span></span>

<span data-ttu-id="31446-107">本節假設您已閱讀與會議工作負載和電話撥入式會議具體相關的規劃區段。</span><span class="sxs-lookup"><span data-stu-id="31446-107">This section assumes that you have read the planning sections related to the Conferencing workload and dial-in conferencing in particular.</span></span>

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a><span data-ttu-id="31446-108">電話撥入式會議設定必要條件</span><span class="sxs-lookup"><span data-stu-id="31446-108">Dial-in Conferencing Configuration Prerequisites</span></span>

<span data-ttu-id="31446-109">電話撥入式會議需要下列 Lync Server 2013 元件：</span><span class="sxs-lookup"><span data-stu-id="31446-109">Dial-in conferencing requires the following Lync Server 2013 components:</span></span>

  - <span data-ttu-id="31446-110">整合通訊應用程式服務 (UCAS)  (稱為*Application Service*) </span><span class="sxs-lookup"><span data-stu-id="31446-110">Unified Communications Application Service (UCAS) (called the *Application service*)</span></span>

  - <span data-ttu-id="31446-111">Conferencing Attendant application</span><span class="sxs-lookup"><span data-stu-id="31446-111">Conferencing Attendant application</span></span>

  - <span data-ttu-id="31446-112">Conferencing Announcement application</span><span class="sxs-lookup"><span data-stu-id="31446-112">Conferencing Announcement application</span></span>

  - <span data-ttu-id="31446-113">電話撥入式會議設定網頁</span><span class="sxs-lookup"><span data-stu-id="31446-113">Dial-in Conferencing Settings webpage</span></span>

  - <span data-ttu-id="31446-114">至少一部 Lync Server 2013 轉送伺服器和至少一部 PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="31446-114">At least one Lync Server 2013 Mediation Server and at least one PSTN gateway</span></span>

<span data-ttu-id="31446-115">當您使用拓撲產生器來定義及發行拓撲，然後部署前端集區或 Standard Edition server 時，您就可以部署這些元件。</span><span class="sxs-lookup"><span data-stu-id="31446-115">You deploy these components when you use the Topology Builder to define and publish your topology and then deploy a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="31446-116">如果您部署的是企業語音，您應該先部署它，再設定電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="31446-116">If you are deploying Enterprise Voice, you should deploy it before you configure dial-in conferencing.</span></span> <span data-ttu-id="31446-117">如果您不是部署企業語音，您可以在部署前端集區或 Standard Edition Server 時，部署轉送伺服器和公用交換電話網路 (PSTN) 閘道。</span><span class="sxs-lookup"><span data-stu-id="31446-117">If you are not deploying Enterprise Voice, you can deploy a Mediation Server and a public switched telephone network (PSTN) gateway when you deploy your Front End pool or Standard Edition server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="31446-118">如果您要從 Office 通訊伺服器 2007 R2 升級至 Lync Server 2013，請在您計畫用於主控 Lync Server 2013 會議的每個集區中部署電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="31446-118">If you are upgrading from Office Communications Server 2007 R2 to Lync Server 2013, deploy dial-in conferencing in every pool that you plan to use to host Lync Server 2013 conferences.</span></span> <span data-ttu-id="31446-119">如需遷移電話撥入式會議的詳細資訊，請參閱<A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">從 Office 通訊伺服器 2007 R2 遷移至 Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="31446-119">For details about migrating dial-in conferencing, see <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Migration from Office Communications Server 2007 R2 to Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="31446-120">本節假設您已完成下列作業：</span><span class="sxs-lookup"><span data-stu-id="31446-120">This section assumes that you have done the following:</span></span>

  - <span data-ttu-id="31446-121">如果您要遷移至 Lync Server 2013，請將最新的更新套用至 Office 通訊伺服器 2007 R2 環境。</span><span class="sxs-lookup"><span data-stu-id="31446-121">Applied the latest updates to your Office Communications Server 2007 R2 environment, if you are migrating to Lync Server 2013.</span></span>

  - <span data-ttu-id="31446-122">使用拓撲產生器來設計及設定拓撲。</span><span class="sxs-lookup"><span data-stu-id="31446-122">Used Topology Builder to design and configure your topology.</span></span> <span data-ttu-id="31446-123">在指定會議工作負載時，您已選取 [電話撥入式會議] 選項。</span><span class="sxs-lookup"><span data-stu-id="31446-123">While specifying the Conferencing workload, you selected the dial-in conferencing option.</span></span> <span data-ttu-id="31446-124">如需定義拓撲的詳細資訊，請參閱部署檔中的在[Lync Server 2013 中定義及設定拓撲](lync-server-2013-defining-and-configuring-the-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="31446-124">For details about defining your topology, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="31446-125">已發行您的拓撲，並設定前端集區或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="31446-125">Published your topology, and set up the Front End pool or Standard Edition server.</span></span> <span data-ttu-id="31446-126">如需發行拓撲及安裝 Lync Server 2013 的詳細資訊，請參閱部署檔中的[部署 Lync server 2013](lync-server-2013-deploying-lync-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="31446-126">For details about publishing the topology and installing Lync Server 2013, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="31446-127">當您安裝已發佈的拓撲時，電話撥入式會議設定網頁會安裝在 Web 服務中的前端伺服器或 Standard Edition server 上。</span><span class="sxs-lookup"><span data-stu-id="31446-127">When you install your published topology, the Dial-in Conferencing Settings webpage is installed on the Front End Server or Standard Edition server as part of Web Services.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="31446-128">如果您在部署 Lync Server 2013 之後，在拓撲產生器中變更檔存放區的路徑，您必須重新開機會議助理和會議宣告應用程式，才能使用新的路徑。</span><span class="sxs-lookup"><span data-stu-id="31446-128">If you change the path for the File Store in Topology Builder after you deploy Lync Server 2013, you need to restart the Conferencing Attendant and Conferencing Announcement applications to use the new path.</span></span>

    
    </div>

  - <span data-ttu-id="31446-129">已部署的 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="31446-129">Deployed Enterprise Voice.</span></span> <span data-ttu-id="31446-130">如果您不是部署企業語音，您可以組合 Enterprise Edition 前端伺服器或 Standard Edition server 上的轉送伺服器，或是部署了獨立轉送伺服器，並已部署 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="31446-130">If you are not deploying Enterprise Voice, you either collocated a Mediation Server on the Enterprise Edition Front End Server or the Standard Edition server, or you deployed a stand-alone Mediation Server, and you deployed a PSTN gateway.</span></span> <span data-ttu-id="31446-131">如需部署企業語音的詳細資訊，請參閱部署檔中的在[Lync Server 2013 中部署 Enterprise Voice](lync-server-2013-deploying-enterprise-voice.md) 。</span><span class="sxs-lookup"><span data-stu-id="31446-131">For details about deploying Enterprise Voice, see [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span> <span data-ttu-id="31446-132">如需安裝獨立轉送伺服器和 PSTN 閘道的詳細資訊，請參閱部署檔中的部署中繼[伺服器及定義 Lync Server 2013 中的對等](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)專案。</span><span class="sxs-lookup"><span data-stu-id="31446-132">For details about installing a stand-alone Mediation Server and PSTN gateway, see [Deploying Mediation Servers and defining peers in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) in the Deployment documentation.</span></span>

<span data-ttu-id="31446-133">下列流程圖顯示您必須執行的步驟，才能設定電話撥入式會議，以及設定電話撥入式會議所執行的步驟。</span><span class="sxs-lookup"><span data-stu-id="31446-133">The following flowchart shows the steps that you must perform before you can configure dial-in conferencing and the steps that you perform to configure dial-in conferencing.</span></span>

<span data-ttu-id="31446-134">**部署電話撥入式會議**</span><span class="sxs-lookup"><span data-stu-id="31446-134">**Deploying dial-in conferencing**</span></span>

<span data-ttu-id="31446-135">![電話撥入式會議部署流程圖](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "電話撥入式會議部署流程圖")</span><span class="sxs-lookup"><span data-stu-id="31446-135">![Dial-in Conferencing Deployment flowchart](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Dial-in Conferencing Deployment flowchart")</span></span>

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a><span data-ttu-id="31446-136">電話撥入式會議許可權</span><span class="sxs-lookup"><span data-stu-id="31446-136">Dial-in Conferencing Permissions</span></span>

<span data-ttu-id="31446-137">若要設定電話撥入式會議，您需要使用下列系統管理工具：</span><span class="sxs-lookup"><span data-stu-id="31446-137">To configure dial-in conferencing, you need to use the following administrative tools:</span></span>

  - <span data-ttu-id="31446-138">Lync Server 2013 控制台</span><span class="sxs-lookup"><span data-stu-id="31446-138">Lync Server 2013 Control Panel</span></span>

  - <span data-ttu-id="31446-139">Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="31446-139">Lync Server Management Shell</span></span>

<span data-ttu-id="31446-140">您可以使用這些系統管理工具來設定電話撥入式會議設定，以及電話撥入式會議所需的撥號對應表、原則及其他設定。</span><span class="sxs-lookup"><span data-stu-id="31446-140">You use these administrative tools to configure dial-in conferencing settings, and the dial plans, policies, and other settings that dial-in conferencing requires.</span></span>

<span data-ttu-id="31446-141">設定電話撥入式會議需要下列任何系統管理角色，視任務而定：</span><span class="sxs-lookup"><span data-stu-id="31446-141">Configuring dial-in conferencing requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="31446-142">**CsVoiceAdministrator**    此系統管理員角色可以建立、設定及管理語音相關的設定和原則。</span><span class="sxs-lookup"><span data-stu-id="31446-142">**CsVoiceAdministrator**   This administrator role can create, configure, and manage voice-related settings and policies.</span></span>

  - <span data-ttu-id="31446-143">**CsUserAdministrator**    此系統管理員角色可以啟用和停用 Lync Server 的使用者，並將現有的原則（例如會議原則和 PIN 碼原則）指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="31446-143">**CsUserAdministrator**   This administrator role can enable and disable users for Lync Server and assign existing policies, such as conferencing policies and PIN policies, to users.</span></span>

  - <span data-ttu-id="31446-144">**CsAdministrator**    此系統管理員角色可以執行 CsVoiceAdministrator 和 CsUserAdministrator 的所有工作。</span><span class="sxs-lookup"><span data-stu-id="31446-144">**CsAdministrator**   This administrator role can perform all of the tasks of CsVoiceAdministrator and CsUserAdministrator.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="31446-145">另請參閱</span><span class="sxs-lookup"><span data-stu-id="31446-145">See Also</span></span>


[<span data-ttu-id="31446-146">在 Lync Server 2013 中部署企業語音</span><span class="sxs-lookup"><span data-stu-id="31446-146">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

