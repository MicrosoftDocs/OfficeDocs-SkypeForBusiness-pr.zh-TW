---
title: Lync Server 2013：規劃混合式部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0902150170d51aa590afc8b3d02c887968a2031
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a><span data-ttu-id="4a71d-102">規劃 Lync Server 2013 混合式部署</span><span class="sxs-lookup"><span data-stu-id="4a71d-102">Planning for Lync Server 2013 hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a71d-103">_**主題上次修改日期：** 2016-05-25_</span><span class="sxs-lookup"><span data-stu-id="4a71d-103">_**Topic Last Modified:** 2016-05-25_</span></span>

<span data-ttu-id="4a71d-104">規劃混合式部署時，請考慮下列使用者與網路基礎結構的需求。</span><span class="sxs-lookup"><span data-stu-id="4a71d-104">You should consider the following requirements for users and your network infrastructure while planning for a hybrid deployment.</span></span>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="4a71d-105">基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="4a71d-105">Infrastructure Requirements</span></span>

<span data-ttu-id="4a71d-106">您必須在您的環境中設定下列設定，才能實現及部署混合式部署。</span><span class="sxs-lookup"><span data-stu-id="4a71d-106">You must have the following configured in your environment in order to implement and deploy a hybrid deployment.</span></span>

  - <span data-ttu-id="4a71d-107">已啟用商務用 Skype Online 的 Microsoft Office 365 租使用者。</span><span class="sxs-lookup"><span data-stu-id="4a71d-107">A Microsoft Office 365 tenant with Skype for Business Online enabled.</span></span> <span data-ttu-id="4a71d-108">請注意，您只能使用單一租使用者進行混合式設定與您的內部部署。</span><span class="sxs-lookup"><span data-stu-id="4a71d-108">Note that you can use only a single tenant for a hybrid configuration with your on-premises deployment.</span></span>

  - <span data-ttu-id="4a71d-109">在支援的拓朴中部署的商務用 Skype Server 或 Lync Server 的單一內部部署（基礎架構）。</span><span class="sxs-lookup"><span data-stu-id="4a71d-109">A single on-premises deployment (infrastructure) of Skype for Business Server or Lync Server that is deployed in a supported topology.</span></span> <span data-ttu-id="4a71d-110">請參閱拓撲需求。</span><span class="sxs-lookup"><span data-stu-id="4a71d-110">See Topology Requirements.</span></span>
    
    <span data-ttu-id="4a71d-111">如需針對混合式設定 Lync Server 2013 或 Lync Server 2010 部署的相關資訊，請參閱設定[Lync server 2013 混合式部署](lync-server-2013-configuring-hybrid-deployments.md)。</span><span class="sxs-lookup"><span data-stu-id="4a71d-111">For information about configuring your Lync Server 2013 or Lync Server 2010 deployment for hybrid, see [Configuring Lync Server 2013 hybrid deployments](lync-server-2013-configuring-hybrid-deployments.md).</span></span>

  - <span data-ttu-id="4a71d-112">商務用 Skype Server 2015 系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="4a71d-112">Skype for Business Server 2015 administrative tools.</span></span> <span data-ttu-id="4a71d-113">如果您使用的是 Lync Server 2013 或 Lync Server 2010，您可以使用 Lync Server 2013 系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="4a71d-113">If you are using Lync Server 2013 or Lync Server 2010, you can use the Lync Server 2013 administrative tools.</span></span>

  - <span data-ttu-id="4a71d-114">若要支援單一登入與 Office 365，讓使用者可以使用相同的登入認證，在他們在內部部署時登入 Office，您可以使用 Azure Active Directory （AAD） Connect 的密碼同步處理功能。</span><span class="sxs-lookup"><span data-stu-id="4a71d-114">To support Single Sign-on with Office 365 so that users can use the same login credentials for signing in to Office as they do on-premises, you can use the password sync features of Azure Active Directory (AAD) Connect.</span></span> <span data-ttu-id="4a71d-115">您也可以使用 Active Directory Federation Services （AD FS）進行單一登入與 Office 365。</span><span class="sxs-lookup"><span data-stu-id="4a71d-115">You can also use Active Directory Federation Services (AD FS) for single sign-on with Office 365.</span></span>
    
    <span data-ttu-id="4a71d-116">如需詳細資訊，請參閱[整合內部部署身分識別與 Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754)。</span><span class="sxs-lookup"><span data-stu-id="4a71d-116">For more information, see [Integrating your on-premises identities with Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754).</span></span>

  - <span data-ttu-id="4a71d-117">讓您的內部部署和線上 Active Directory 物件同步處理的單一目錄同步處理解決方案。</span><span class="sxs-lookup"><span data-stu-id="4a71d-117">A single directory synchronization solution to keep your on-premises and online Active Directory objects synchronized.</span></span> <span data-ttu-id="4a71d-118">如需目錄同步處理的詳細資訊，請參閱[目錄整合工具](http://go.microsoft.com/fwlink/p/?linkid=530320)。</span><span class="sxs-lookup"><span data-stu-id="4a71d-118">For details about Directory Synchronization, see [Directory Integration Tools](http://go.microsoft.com/fwlink/p/?linkid=530320).</span></span>

</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="4a71d-119">Lync 用戶端支援</span><span class="sxs-lookup"><span data-stu-id="4a71d-119">Lync Client Support</span></span>

<span data-ttu-id="4a71d-120">Lync 用戶端支援的功能有一些差異，以及內部部署和線上環境中提供的功能。</span><span class="sxs-lookup"><span data-stu-id="4a71d-120">There are some differences in the features supported in Lync clients, as well as the features available in on-premises and online environments.</span></span> <span data-ttu-id="4a71d-121">在您決定您要在組織中的哪些位置，您可以針對不同的 Lync Server 設定，查看用戶端支援。</span><span class="sxs-lookup"><span data-stu-id="4a71d-121">Before you decide where you want to home users in your organization, you can view the client support for the various configurations of Lync Server.</span></span> <span data-ttu-id="4a71d-122">Lync 混合式部署中的商務用 Skype Online 支援下列用戶端：</span><span class="sxs-lookup"><span data-stu-id="4a71d-122">The following clients are supported with Skype for Business Online in a Lync hybrid deployment:</span></span>

  - <span data-ttu-id="4a71d-123">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="4a71d-123">Lync 2010</span></span>

  - <span data-ttu-id="4a71d-124">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="4a71d-124">Lync 2013</span></span>

  - <span data-ttu-id="4a71d-125">Lync Windows Store 應用程式</span><span class="sxs-lookup"><span data-stu-id="4a71d-125">Lync Windows Store app</span></span>

  - <span data-ttu-id="4a71d-126">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="4a71d-126">Lync Web App</span></span>

  - <span data-ttu-id="4a71d-127">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="4a71d-127">Lync Mobile</span></span>

  - <span data-ttu-id="4a71d-128">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="4a71d-128">Lync for Mac 2011</span></span>

  - <span data-ttu-id="4a71d-129">Lync 會議室系統</span><span class="sxs-lookup"><span data-stu-id="4a71d-129">Lync Room System</span></span>

  - <span data-ttu-id="4a71d-130">Lync Basic 2013</span><span class="sxs-lookup"><span data-stu-id="4a71d-130">Lync Basic 2013</span></span>

<span data-ttu-id="4a71d-131">如需用戶端支援的詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="4a71d-131">For details about client support, see the following topics:</span></span>

  - [<span data-ttu-id="4a71d-132">Lync Online 的用戶端</span><span class="sxs-lookup"><span data-stu-id="4a71d-132">Clients for Lync Online</span></span>](http://go.microsoft.com/fwlink/?linkid=281902)

  - [<span data-ttu-id="4a71d-133">Lync Server 2013 的用戶端比較表</span><span class="sxs-lookup"><span data-stu-id="4a71d-133">Client comparison tables for Lync Server 2013</span></span>](lync-server-2013-desktop-client-comparison-tables.md)

  - [<span data-ttu-id="4a71d-134">Lync Server 2013 行動用戶端比較表</span><span class="sxs-lookup"><span data-stu-id="4a71d-134">Mobile client comparison tables for Lync Server 2013</span></span>](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="4a71d-135">拓撲需求</span><span class="sxs-lookup"><span data-stu-id="4a71d-135">Topology Requirements</span></span>

<span data-ttu-id="4a71d-136">若要在商務用 Skype Online 中設定混合式部署，您必須具備下列其中一個受支援拓撲：</span><span class="sxs-lookup"><span data-stu-id="4a71d-136">To configure your deployment for hybrid with Skype for Business Online, you need to have one of the following supported topologies:</span></span>

  - <span data-ttu-id="4a71d-137">商務用 Skype Server 2015 部署與所有執行商務用 Skype Server 2015 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="4a71d-137">A Skype for Business Server 2015 deployment with all servers running Skype for Business Server 2015.</span></span>

  - <span data-ttu-id="4a71d-138">Lync Server 2013 部署與所有執行 Lync Server 2013 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="4a71d-138">A Lync Server 2013 deployment with all servers running Lync Server 2013.</span></span>

  - <span data-ttu-id="4a71d-139">Lync Server 2010 部署，其中所有執行 Lync Server 2010 的伺服器都有最新的累計更新。</span><span class="sxs-lookup"><span data-stu-id="4a71d-139">A Lync Server 2010 deployment with all servers running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="4a71d-140">同盟邊緣伺服器與同盟 Edge 伺服器的下一個躍點伺服器必須執行 Lync Server 2010，並提供最新的累加更新。</span><span class="sxs-lookup"><span data-stu-id="4a71d-140">The federation Edge Server and next hop server from the federation Edge Server must be running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="4a71d-141">商務用 Skype Server 2015 或 Lync Server 2013 系統管理工具必須安裝在至少一個伺服器或管理工作站上。</span><span class="sxs-lookup"><span data-stu-id="4a71d-141">The Skype for Business Server 2015 or Lync Server 2013 Administrative Tools must be installed on at least one server or management workstation.</span></span>

  - <span data-ttu-id="4a71d-142">混合式 Lync Server 2013 和商務用 Skype Server 2015 部署，在至少有一個執行商務用 Skype Server 2015 的網站中，都有下列伺服器角色：</span><span class="sxs-lookup"><span data-stu-id="4a71d-142">A mixed Lync Server 2013 and Skype for Business Server 2015 deployment with the following server roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="4a71d-143">至少有一個企業版池或標準版伺服器</span><span class="sxs-lookup"><span data-stu-id="4a71d-143">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="4a71d-144">與 SIP 同盟相關聯的控制器池（如果有的話）</span><span class="sxs-lookup"><span data-stu-id="4a71d-144">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="4a71d-145">與 SIP 同盟相關聯的邊緣池</span><span class="sxs-lookup"><span data-stu-id="4a71d-145">The Edge Pool associated with SIP federation</span></span>

  - <span data-ttu-id="4a71d-146">混合式 Lync Server 2010 和商務用 Skype Server 2015 部署，在至少一個執行商務用 Skype Server 2015 的網站中，都有下列伺服器角色：</span><span class="sxs-lookup"><span data-stu-id="4a71d-146">A mixed Lync Server 2010 and Skype for Business Server 2015 deployment with the following servers roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="4a71d-147">至少有一個企業版池或標準版伺服器</span><span class="sxs-lookup"><span data-stu-id="4a71d-147">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="4a71d-148">與 SIP 同盟相關聯的控制器池（如果有的話）</span><span class="sxs-lookup"><span data-stu-id="4a71d-148">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="4a71d-149">與網站 SIP 同盟相關聯的邊緣池</span><span class="sxs-lookup"><span data-stu-id="4a71d-149">The Edge Pool associated with SIP federation for the Site</span></span>

  - <span data-ttu-id="4a71d-150">混合式 Lync Server 2010 和 Lync Server 2013 部署，在至少一個執行 Lync Server 2013 的網站中，都有下列伺服器角色：</span><span class="sxs-lookup"><span data-stu-id="4a71d-150">A mixed Lync Server 2010 and Lync Server 2013 deployment with the following server roles in at least one site running Lync Server 2013:</span></span>
    
      - <span data-ttu-id="4a71d-151">網站中至少有一個企業版池或標準版伺服器</span><span class="sxs-lookup"><span data-stu-id="4a71d-151">At least one Enterprise Pool or Standard Edition server in the site</span></span>
    
      - <span data-ttu-id="4a71d-152">與 SIP 同盟相關聯的控制器池（如果它存在於網站中）</span><span class="sxs-lookup"><span data-stu-id="4a71d-152">The Director Pool associated with SIP federation, if it exists in the site</span></span>
    
      - <span data-ttu-id="4a71d-153">與網站 SIP 同盟相關聯的邊緣池</span><span class="sxs-lookup"><span data-stu-id="4a71d-153">The Edge Pool associated with SIP federation for the site</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4a71d-154">所有的使用者管理，包括使用者在線上內部部署和 UNRESOLVED_TOKEN_VAL （com.microsoft.skypeforbusiness.plugin.plist）之間移動，都需要使用最新安裝的系統管理工具來完成。</span><span class="sxs-lookup"><span data-stu-id="4a71d-154">All user management, including user moves between on-premises and UNRESOLVED_TOKEN_VAL(skypeforbusiness) Online, needs to be done using the latest installed version of the administrative tools.</span></span> <span data-ttu-id="4a71d-155">[管理工具] 必須安裝在可連線存取現有內部部署和網際網路的個別伺服器上。</span><span class="sxs-lookup"><span data-stu-id="4a71d-155">The administrative tools must be installed on a separate server that has connect access to the existing on-premises deployment and to the Internet.</span></span> <span data-ttu-id="4a71d-156">您必須從連線到內部部署的管理工具執行<A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">move-csuser</A> Cmdlet，才能將使用者從內部部署部署移至 UNRESOLVED_TOKEN_VAL （skype16_online）。</span><span class="sxs-lookup"><span data-stu-id="4a71d-156">The <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> cmdlet to move users from your on-premises deployment to UNRESOLVED_TOKEN_VAL(skype16_online) must be run from the administrative tools connected to your on-premises deployment.</span></span>



</div>

<span data-ttu-id="4a71d-157">如需支援的拓撲的詳細資訊，請參閱[Lync server 2013 支援的拓撲](lync-server-2013-supported-topologies.md)，以及[適用于企業混合式部署的 Lync server 2013 參考資料拓撲](http://go.microsoft.com/fwlink/p/?linkid=398709)。</span><span class="sxs-lookup"><span data-stu-id="4a71d-157">For more information about supported topologies, see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md), and [Lync Server 2013 Reference Topologies for Enterprise Hybrid Deployments](http://go.microsoft.com/fwlink/p/?linkid=398709).</span></span>

<span data-ttu-id="4a71d-158">如需混合式部署和將 PowerShell 連線至 Lync Online 的疑難排解資訊，請參閱[Lync online： Lync PowerShell 及混合式疑難排解](http://go.microsoft.com/fwlink/p/?linkid=306718)。</span><span class="sxs-lookup"><span data-stu-id="4a71d-158">For troubleshooting information about hybrid deployments and connecting PowerShell to Lync Online, see [Lync Online: Lync PowerShell and Hybrid Troubleshooting](http://go.microsoft.com/fwlink/p/?linkid=306718).</span></span>

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a><span data-ttu-id="4a71d-159">同盟允許/封鎖清單的需求</span><span class="sxs-lookup"><span data-stu-id="4a71d-159">Requirements for Federation Allowed/Blocked Lists</span></span>

<span data-ttu-id="4a71d-160">[允許的網域] 清單包含已設定「合作夥伴邊緣」完全限定功能變數名稱（FQDN）的網域。</span><span class="sxs-lookup"><span data-stu-id="4a71d-160">The Allowed domains list includes domains that have a partner Edge fully qualified domain name (FQDN) configured.</span></span> <span data-ttu-id="4a71d-161">這些有時稱為「*允許夥伴伺服器*」或「*直接聯盟夥伴*」。</span><span class="sxs-lookup"><span data-stu-id="4a71d-161">These are sometimes referred to as *allowed partner servers* or *direct federation partners*.</span></span> <span data-ttu-id="4a71d-162">在內部部署部署中，您應該熟悉開啟同盟與封閉式同盟之間的差異，分別稱為「*合作夥伴探索*」和「*允許的合作夥伴網域清單*」。</span><span class="sxs-lookup"><span data-stu-id="4a71d-162">You should be familiar with the difference between Open Federation and Closed Federation, referred to as *partner discovery* and *allowed partner domain list*, respectively, in on-premises deployments.</span></span>

<span data-ttu-id="4a71d-163">若要成功設定混合式部署，必須符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="4a71d-163">The following requirements must be met to successfully configure a hybrid deployment:</span></span>

  - <span data-ttu-id="4a71d-164">您的內部部署和 Office 365 租使用者的網域相符設定必須相同。</span><span class="sxs-lookup"><span data-stu-id="4a71d-164">Domain matching must be configured the same for your on-premises deployment and your Office 365 tenant.</span></span> <span data-ttu-id="4a71d-165">如果在內部部署部署上啟用合作夥伴探索，則必須針對您的線上租使用者設定開啟同盟。</span><span class="sxs-lookup"><span data-stu-id="4a71d-165">If partner discovery is enabled on the on-premises deployment, then open federation must be configured for your online tenant.</span></span> <span data-ttu-id="4a71d-166">如果未啟用合作夥伴探索，則必須針對您的線上租使用者設定關閉的同盟。</span><span class="sxs-lookup"><span data-stu-id="4a71d-166">If partner discovery is not enabled, then closed federation must be configured for your online tenant.</span></span>

  - <span data-ttu-id="4a71d-167">內部部署部署中的 [封鎖的網域] 清單必須完全符合您線上租使用者的封鎖網域清單。</span><span class="sxs-lookup"><span data-stu-id="4a71d-167">The Blocked domains list in the on-premises deployment must exactly match the Blocked domains list for your online tenant.</span></span>

  - <span data-ttu-id="4a71d-168">內部部署部署中的 [允許的網域] 清單必須完全符合您線上租使用者的「允許」網域清單。</span><span class="sxs-lookup"><span data-stu-id="4a71d-168">The Allowed domains list in the on-premises deployment must exactly match the Allowed domains list for your online tenant.</span></span>

  - <span data-ttu-id="4a71d-169">聯盟必須針對線上租使用者啟用，且使用 Lync Online 控制台進行設定。</span><span class="sxs-lookup"><span data-stu-id="4a71d-169">Federation must be enabled for the external communications for the online tenant, which is configured by using the Lync Online Control Panel.</span></span>

</div>

<div>

## <a name="dns-settings"></a><span data-ttu-id="4a71d-170">DNS 設定</span><span class="sxs-lookup"><span data-stu-id="4a71d-170">DNS Settings</span></span>

<span data-ttu-id="4a71d-171">針對混合式部署建立 DNS 記錄時，所有 Lync 外部 DNS 記錄都應該指向內部部署基礎結構。</span><span class="sxs-lookup"><span data-stu-id="4a71d-171">When creating DNS records for hybrid deployments, all Lync external DNS records should point to the on-premises infrastructure.</span></span> <span data-ttu-id="4a71d-172">如需必要 DNS 記錄的詳細資料，請參閱[Lync Server 2013 的網域名稱系統（DNS）需求](lync-server-2013-domain-name-system-dns-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4a71d-172">For details on required DNS records, please refer to [Domain Name System (DNS) requirements for Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span></span>

<span data-ttu-id="4a71d-173">此外，您還需要確保下表所述的 DNS 解析度可在您的內部部署中運作：</span><span class="sxs-lookup"><span data-stu-id="4a71d-173">Additionally you need to ensure that the DNS resolution described in the following table works in your on-premises deployment:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a71d-174">DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="4a71d-174">DNS record</span></span></p></td>
<td><p><span data-ttu-id="4a71d-175">可解析的方式</span><span class="sxs-lookup"><span data-stu-id="4a71d-175">Resolvable by</span></span></p></td>
<td><p><span data-ttu-id="4a71d-176">DNS 需求</span><span class="sxs-lookup"><span data-stu-id="4a71d-176">DNS requirement</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a71d-177">_Sipfederationtls _tcp 的 DNS SRV 記錄。&lt;針對&gt;所有支援的 SIP 網域 Sipdomain.com，解析為存取邊緣外部 IP （s）</span><span class="sxs-lookup"><span data-stu-id="4a71d-177">DNS SRV record for _sipfederationtls._tcp.&lt;sipdomain.com&gt; for all supported SIP domains resolving to Access Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="4a71d-178">Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="4a71d-178">Edge server(s)</span></span></p></td>
<td><p><span data-ttu-id="4a71d-179">在混合式設定中啟用聯盟通訊。</span><span class="sxs-lookup"><span data-stu-id="4a71d-179">Enable federated communication in a hybrid configuration.</span></span> <span data-ttu-id="4a71d-180">Edge 伺服器需要知道在內部部署與線上之間分割之 SIP 網域的聯盟流量。</span><span class="sxs-lookup"><span data-stu-id="4a71d-180">The Edge Server needs to know where to route federated traffic for the SIP domain that is split between on premises and online.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a71d-181">針對 Edge Web 會議服務 FQDN 的 DNS A 記錄，例如 webcon.contoso.com 解析為網路會議 Edge 外部 IP （s）</span><span class="sxs-lookup"><span data-stu-id="4a71d-181">DNS A record(s) for Edge Web Conferencing Service FQDN, e.g. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="4a71d-182">已連接內部公司網路的使用者電腦</span><span class="sxs-lookup"><span data-stu-id="4a71d-182">Internal corporate network connected users’ computers</span></span></p></td>
<td><p><span data-ttu-id="4a71d-183">讓線上使用者在內部部署的託管會議中展示或查看內容。</span><span class="sxs-lookup"><span data-stu-id="4a71d-183">Enable online users to present or view content in on-premises hosted meetings.</span></span> <span data-ttu-id="4a71d-184">內容包括 PowerPoint 檔案、白板、投票和共用筆記。</span><span class="sxs-lookup"><span data-stu-id="4a71d-184">Content includes PowerPoint files, whiteboards, polls, and shared notes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4a71d-185">根據貴組織中的 DNS 設定方式，您可能需要將這些記錄新增到對應 SIP 網域的內部託管 DNS 區域中，以提供這些記錄的內部 DNS 解析。</span><span class="sxs-lookup"><span data-stu-id="4a71d-185">Depending on how DNS is configured in your organization, you may need to add these records to the internal hosted DNS zone for the corresponding SIP domain(s) to provide internal DNS resolution to these records.</span></span>

</div>

<div>

## <a name="firewall-considerations"></a><span data-ttu-id="4a71d-186">防火牆考慮</span><span class="sxs-lookup"><span data-stu-id="4a71d-186">Firewall Considerations</span></span>

<span data-ttu-id="4a71d-187">您網路上的電腦必須能夠執行標準的網際網路 DNS 查閱。</span><span class="sxs-lookup"><span data-stu-id="4a71d-187">Computers on your network must be able to perform standard Internet DNS lookups.</span></span> <span data-ttu-id="4a71d-188">如果這些電腦能達到標準的網際網路網站，您的網路就能滿足這個需求。</span><span class="sxs-lookup"><span data-stu-id="4a71d-188">If these computers can reach standard Internet sites, your network meets this requirement.</span></span>

<span data-ttu-id="4a71d-189">根據您的 Microsoft Online 服務資料中心的位置，您也必須設定您的網路防火牆裝置，以根據萬用字元功能變數名稱（例如，所有來自 outlook.com 的\*流量）來接受連線。</span><span class="sxs-lookup"><span data-stu-id="4a71d-189">Depending on the location of your Microsoft Online Services data center, you must also configure your network firewall devices to accept connections based on wildcard domain names (for example, all traffic from \*.outlook.com).</span></span> <span data-ttu-id="4a71d-190">如果貴組織的防火牆不支援萬用字元名稱設定，您將必須手動判斷您想要允許的 IP 位址範圍，以及指定的埠。</span><span class="sxs-lookup"><span data-stu-id="4a71d-190">If your organization’s firewalls do not support wildcard name configurations, you will have to manually determine the IP address ranges that you would like to allow and the specified ports.</span></span>

<span data-ttu-id="4a71d-191">請參閱[Office 365 url 和 IP 位址範圍](http://go.microsoft.com/fwlink/p/?linkid=252942)的說明主題。</span><span class="sxs-lookup"><span data-stu-id="4a71d-191">Refer to the Help topic [Office 365 URLs and IP address ranges](http://go.microsoft.com/fwlink/p/?linkid=252942).</span></span>

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a><span data-ttu-id="4a71d-192">埠與通訊協定需求</span><span class="sxs-lookup"><span data-stu-id="4a71d-192">Port and Protocol Requirements</span></span>

<span data-ttu-id="4a71d-193">除了內部 Lync Server 2013 通訊的埠需求之外，您還必須設定下列埠。</span><span class="sxs-lookup"><span data-stu-id="4a71d-193">In addition to the port requirements for internal Lync Server 2013 communication, you must also configure the following ports.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a71d-194">通訊協定/埠</span><span class="sxs-lookup"><span data-stu-id="4a71d-194">Protocol / Port</span></span></th>
<th><span data-ttu-id="4a71d-195">程式</span><span class="sxs-lookup"><span data-stu-id="4a71d-195">Applications</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a71d-196">TCP 443</span><span class="sxs-lookup"><span data-stu-id="4a71d-196">TCP 443</span></span></p></td>
<td><p><span data-ttu-id="4a71d-197">開啟入站</span><span class="sxs-lookup"><span data-stu-id="4a71d-197">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="4a71d-198">Active Directory 同盟服務（同盟伺服器角色）</span><span class="sxs-lookup"><span data-stu-id="4a71d-198">Active Directory Federation Services (federation server role)</span></span></p>
<p><span data-ttu-id="4a71d-199">如需詳細資訊，請參閱<a href="http://go.microsoft.com/fwlink/p/?linkid=281899">瞭解 AD FS 角色服務</a>。</span><span class="sxs-lookup"><span data-stu-id="4a71d-199">For more information, see <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS Role Services</a>.</span></span></p></li>
<li><p><span data-ttu-id="4a71d-200">Active Directory 同盟服務（proxy 伺服器角色）</span><span class="sxs-lookup"><span data-stu-id="4a71d-200">Active Directory Federation Services (proxy server role)</span></span></p></li>
<li><p><span data-ttu-id="4a71d-201">Microsoft Online 服務入口網站</span><span class="sxs-lookup"><span data-stu-id="4a71d-201">Microsoft Online Services Portal</span></span></p></li>
<li><p><span data-ttu-id="4a71d-202">我的公司入口網站</span><span class="sxs-lookup"><span data-stu-id="4a71d-202">My Company Portal</span></span></p></li>
<li><p><span data-ttu-id="4a71d-203">Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="4a71d-203">Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="4a71d-204">Lync 用戶端（從內部部署 Lync Server 與 Lync Online 的通訊）</span><span class="sxs-lookup"><span data-stu-id="4a71d-204">Lync client (communication to Lync Online from on-premises Lync Server)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a71d-205">TCP 80 和443</span><span class="sxs-lookup"><span data-stu-id="4a71d-205">TCP 80 and 443</span></span></p></td>
<td><p><span data-ttu-id="4a71d-206">開啟入站</span><span class="sxs-lookup"><span data-stu-id="4a71d-206">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="4a71d-207">Microsoft Online Services 目錄同步處理工具</span><span class="sxs-lookup"><span data-stu-id="4a71d-207">Microsoft Online Services Directory Synchronization Tool</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a71d-208">TCP 5061</span><span class="sxs-lookup"><span data-stu-id="4a71d-208">TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="4a71d-209">開啟邊緣伺服器的入站/出站</span><span class="sxs-lookup"><span data-stu-id="4a71d-209">Open inbound/outbound on the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a71d-210">PSOM/TLS 443</span><span class="sxs-lookup"><span data-stu-id="4a71d-210">PSOM/TLS 443</span></span></p></td>
<td><p><span data-ttu-id="4a71d-211">開啟資料共用會話的輸入/輸出</span><span class="sxs-lookup"><span data-stu-id="4a71d-211">Open inbound/outbound for data sharing sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a71d-212">STUN/TCP 443</span><span class="sxs-lookup"><span data-stu-id="4a71d-212">STUN/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="4a71d-213">開啟音訊、影片、應用程式共用會話的輸入/輸出</span><span class="sxs-lookup"><span data-stu-id="4a71d-213">Open inbound/outbound for audio, video, application sharing sessions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a71d-214">STUN/UDP 3478</span><span class="sxs-lookup"><span data-stu-id="4a71d-214">STUN/UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="4a71d-215">開啟音訊及視頻會話的輸入/輸出</span><span class="sxs-lookup"><span data-stu-id="4a71d-215">Open inbound/outbound for audio and video sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a71d-216">RTP/TCP 50000-59999</span><span class="sxs-lookup"><span data-stu-id="4a71d-216">RTP/TCP 50000-59999</span></span></p></td>
<td><p><span data-ttu-id="4a71d-217">開啟音訊及視頻會話的輸出</span><span class="sxs-lookup"><span data-stu-id="4a71d-217">Open outbound for audio and video sessions</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a><span data-ttu-id="4a71d-218">使用者帳戶和資料</span><span class="sxs-lookup"><span data-stu-id="4a71d-218">User Accounts and Data</span></span>

<span data-ttu-id="4a71d-219">在 Lync Server 2013 混合式部署中，您要在家中的任何使用者都必須先在內部部署中建立，才能在 Active Directory 網域服務中建立使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="4a71d-219">In a Lync Server 2013 hybrid deployment, any user that you want to home in Lync Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="4a71d-220">然後，您可以將使用者移至商務用 Skype Online，這會移動使用者的連絡人清單。</span><span class="sxs-lookup"><span data-stu-id="4a71d-220">You can then move the user to Skype for Business Online, which will move the user’s contact list.</span></span>

<span data-ttu-id="4a71d-221">當您在您的 Lync 內部部署和 Lync Online 部署與 AD FS 和 Dirsync 之間同步處理使用者帳戶時，您必須在內部部署和線上 Lync 部署之間同步處理貴組織中所有 Lync 使用者的廣告帳戶，即使使用者不會移至 Lync Online。</span><span class="sxs-lookup"><span data-stu-id="4a71d-221">When you synchronize user accounts between your Lync on-premises and Lync Online deployments with AD FS and Dirsync, you need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="4a71d-222">如果您不同步處理所有使用者，貴組織中內部部署與線上使用者之間的通訊可能無法如期運作。</span><span class="sxs-lookup"><span data-stu-id="4a71d-222">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4a71d-223">如果使用者是使用 Office 365 的線上入口網站建立，使用者帳戶將不會與內部部署的 Active Directory 同步處理，而且使用者將不會存在於內部部署的 Active Directory 中。</span><span class="sxs-lookup"><span data-stu-id="4a71d-223">If the user is created by using the online portal for Office 365, the user account will not be synchronized with on-premises Active Directory, and the user will not exist in the on-premises Active Directory.</span></span> <span data-ttu-id="4a71d-224">如果您已在 Lync Online 中建立使用者，並且想要設定混合式與內部部署的 Lync Server，請參閱在<A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Lync server 2013 中將使用者從 Lync Online 移至 lync 內部部署</A>。</span><span class="sxs-lookup"><span data-stu-id="4a71d-224">If you have already created users in Lync Online, and want to configure hybrid with an on-premises Lync Server, see <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="4a71d-225">規劃混合式部署時，您也應該考慮下列與使用者相關的問題。</span><span class="sxs-lookup"><span data-stu-id="4a71d-225">You should also consider the following user-related issues when planning for a hybrid deployment.</span></span>

  - <span data-ttu-id="4a71d-226">**使用者連絡人**   Lync Online 使用者的連絡人限制是250。</span><span class="sxs-lookup"><span data-stu-id="4a71d-226">**User contacts**   The limit for contacts for Lync Online users is 250.</span></span> <span data-ttu-id="4a71d-227">當帳戶移至 Lync Online 時，該號碼以外的任何連絡人都會從使用者的連絡人清單中移除。</span><span class="sxs-lookup"><span data-stu-id="4a71d-227">Any contacts beyond that number will be removed from the user’s contact list when the account is moved to Lync Online.</span></span>

  - <span data-ttu-id="4a71d-228">**立即訊息和目前狀態**   使用者連絡人清單、群組和存取控制清單（acl）會與使用者帳戶一起遷移。</span><span class="sxs-lookup"><span data-stu-id="4a71d-228">**Instant Messaging and Presence**   User contact lists, groups, and access control lists (ACLs) are migrated with the user account.</span></span>

  - <span data-ttu-id="4a71d-229">**會議資料、會議內容和排程會議**   此內容不會與使用者帳戶一起遷移。</span><span class="sxs-lookup"><span data-stu-id="4a71d-229">**Conferencing data, meeting content, and scheduled meetings**   This content is not migrated with the user account.</span></span> <span data-ttu-id="4a71d-230">使用者必須在帳戶遷移至 Lync Online 後重新排程會議。</span><span class="sxs-lookup"><span data-stu-id="4a71d-230">Users must reschedule meetings after their accounts are migrated to Lync Online.</span></span>

</div>

<div>

## <a name="user-policies-and-features"></a><span data-ttu-id="4a71d-231">使用者原則與功能</span><span class="sxs-lookup"><span data-stu-id="4a71d-231">User Policies and Features</span></span>

  - <span data-ttu-id="4a71d-232">在 Lync Server 2013 混合式環境中，使用者可在內部部署或線上使用立即訊息、語音及會議，但不能同時使用這兩個功能。</span><span class="sxs-lookup"><span data-stu-id="4a71d-232">In a Lync Server 2013 hybrid environment, users can be enabled for Instant Messaging, voice, and meetings either on-premises or online, but not both simultaneously.</span></span>

  - <span data-ttu-id="4a71d-233">**Lync 用戶端**   在使用者移至 Lync Online 時，可能需要新的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="4a71d-233">**Lync Client**    Some users may require a new client version when they are moved to Lync Online.</span></span> <span data-ttu-id="4a71d-234">若是 Office 通訊伺服器 2007 R2，在遷移至 Lync Online 之前，必須先將使用者移至 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="4a71d-234">For Office Communications Server 2007 R2, users must be moved to a Lync Server 2013 pool prior to migration to Lync Online.</span></span>
    
    <span data-ttu-id="4a71d-235">如需用戶端支援的詳細資訊，請參閱[Lync Online 的用戶端](http://go.microsoft.com/fwlink/p/?linkid=281902)和[支援的 lync 用戶端和網路埠](http://go.microsoft.com/fwlink/p/?linkid=281901)設定。</span><span class="sxs-lookup"><span data-stu-id="4a71d-235">For more information about client support, see [Clients for Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) and [Supported Lync clients and network port configurations](http://go.microsoft.com/fwlink/p/?linkid=281901).</span></span>

  - <span data-ttu-id="4a71d-236">**內部部署原則與設定（非使用者）**   線上和內部部署原則都需要個別的配置。</span><span class="sxs-lookup"><span data-stu-id="4a71d-236">**On-premises policies and configuration (non-user)**   Online and on-premises policies require separate configuration.</span></span> <span data-ttu-id="4a71d-237">您無法設定適用于這兩者的全域原則。</span><span class="sxs-lookup"><span data-stu-id="4a71d-237">You cannot set global policies that apply to both.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

