---
title: Lync Server 2013：規劃混合式部署
description: Lync Server 2013：規劃混合式部署。
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
ms.openlocfilehash: 919f6058059fc9bfcb6bcb4f4c38140e53be6274
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561299"
---
# <a name="planning-for-lync-server-2013-hybrid-deployments"></a><span data-ttu-id="938cf-103">規劃 Lync Server 2013 混合式部署</span><span class="sxs-lookup"><span data-stu-id="938cf-103">Planning for Lync Server 2013 hybrid deployments</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="938cf-104">_**主題上次修改日期：** 2016-05-25_</span><span class="sxs-lookup"><span data-stu-id="938cf-104">_**Topic Last Modified:** 2016-05-25_</span></span>

<span data-ttu-id="938cf-105">在規劃混合式部署時，應考慮下列使用者和網路基礎結構的需求。</span><span class="sxs-lookup"><span data-stu-id="938cf-105">You should consider the following requirements for users and your network infrastructure while planning for a hybrid deployment.</span></span>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="938cf-106">基礎結構需求</span><span class="sxs-lookup"><span data-stu-id="938cf-106">Infrastructure Requirements</span></span>

<span data-ttu-id="938cf-107">您必須在您的環境中設定下列設定，才能實施及部署混合部署。</span><span class="sxs-lookup"><span data-stu-id="938cf-107">You must have the following configured in your environment in order to implement and deploy a hybrid deployment.</span></span>

  - <span data-ttu-id="938cf-108">啟用啟用商務用 Skype Online 的 Microsoft 365 或 Office 365 組織。</span><span class="sxs-lookup"><span data-stu-id="938cf-108">A Microsoft 365 or Office 365 organization with Skype for Business Online enabled.</span></span> <span data-ttu-id="938cf-109">請注意，您可以只對內部部署部署使用單一租使用者進行混合設定。</span><span class="sxs-lookup"><span data-stu-id="938cf-109">Note that you can use only a single tenant for a hybrid configuration with your on-premises deployment.</span></span>

  - <span data-ttu-id="938cf-110">單一內部部署 (基礎結構) ，可在支援的拓撲中部署商務用 Skype Server 或 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="938cf-110">A single on-premises deployment (infrastructure) of Skype for Business Server or Lync Server that is deployed in a supported topology.</span></span> <span data-ttu-id="938cf-111">請參閱拓撲的需求。</span><span class="sxs-lookup"><span data-stu-id="938cf-111">See Topology Requirements.</span></span>
    
    <span data-ttu-id="938cf-112">如需設定 Lync Server 2013 或 Lync Server 2010 部署以進行混合的詳細資訊，請參閱設定 [Lync server 2013 混合式部署](lync-server-2013-configuring-hybrid-deployments.md)。</span><span class="sxs-lookup"><span data-stu-id="938cf-112">For information about configuring your Lync Server 2013 or Lync Server 2010 deployment for hybrid, see [Configuring Lync Server 2013 hybrid deployments](lync-server-2013-configuring-hybrid-deployments.md).</span></span>

  - <span data-ttu-id="938cf-113">商務用 Skype Server 2015 系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="938cf-113">Skype for Business Server 2015 administrative tools.</span></span> <span data-ttu-id="938cf-114">如果您使用的是 Lync Server 2013 或 Lync Server 2010，您可以使用 Lync Server 2013 系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="938cf-114">If you are using Lync Server 2013 or Lync Server 2010, you can use the Lync Server 2013 administrative tools.</span></span>

  - <span data-ttu-id="938cf-115">若要支援使用 Microsoft 365 或 Office 365 進行單一登入，讓使用者可以使用相同的登入認證，以在內部部署時登入 Office，您可以使用 Azure Active Directory (AAD) Connect 的密碼同步功能。</span><span class="sxs-lookup"><span data-stu-id="938cf-115">To support Single Sign-on with Microsoft 365 or Office 365 so that users can use the same login credentials for signing in to Office as they do on-premises, you can use the password sync features of Azure Active Directory (AAD) Connect.</span></span> <span data-ttu-id="938cf-116">您也可以使用 Active Directory Federation Services (AD FS) ，以用於 Microsoft 365 或 Office 365 的單一登入。</span><span class="sxs-lookup"><span data-stu-id="938cf-116">You can also use Active Directory Federation Services (AD FS) for single sign-on with Microsoft 365 or Office 365.</span></span>
    
    <span data-ttu-id="938cf-117">如需詳細資訊，請參閱[將內部部署識別與 Azure Active Directory 整合](https://go.microsoft.com/fwlink/p/?linkid=619754)。</span><span class="sxs-lookup"><span data-stu-id="938cf-117">For more information, see [Integrating your on-premises identities with Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=619754).</span></span>

  - <span data-ttu-id="938cf-118">單一目錄同步處理解決方案，可讓您的內部部署和線上 Active Directory 物件同步處理。</span><span class="sxs-lookup"><span data-stu-id="938cf-118">A single directory synchronization solution to keep your on-premises and online Active Directory objects synchronized.</span></span> <span data-ttu-id="938cf-119">如需目錄同步處理的詳細資訊，請參閱 [目錄整合工具](https://go.microsoft.com/fwlink/p/?linkid=530320)。</span><span class="sxs-lookup"><span data-stu-id="938cf-119">For details about Directory Synchronization, see [Directory Integration Tools](https://go.microsoft.com/fwlink/p/?linkid=530320).</span></span>

</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="938cf-120">Lync 用戶端支援</span><span class="sxs-lookup"><span data-stu-id="938cf-120">Lync Client Support</span></span>

<span data-ttu-id="938cf-121">Lync 用戶端支援的功能有一些差異，以及內部部署和線上環境中可用的功能。</span><span class="sxs-lookup"><span data-stu-id="938cf-121">There are some differences in the features supported in Lync clients, as well as the features available in on-premises and online environments.</span></span> <span data-ttu-id="938cf-122">在您決定要在組織中家用使用者的位置之前，您可以針對 Lync Server 的各種設定來查看用戶端支援。</span><span class="sxs-lookup"><span data-stu-id="938cf-122">Before you decide where you want to home users in your organization, you can view the client support for the various configurations of Lync Server.</span></span> <span data-ttu-id="938cf-123">下列用戶端支援 Lync 混合式部署中的商務用 Skype Online：</span><span class="sxs-lookup"><span data-stu-id="938cf-123">The following clients are supported with Skype for Business Online in a Lync hybrid deployment:</span></span>

  - <span data-ttu-id="938cf-124">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="938cf-124">Lync 2010</span></span>

  - <span data-ttu-id="938cf-125">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="938cf-125">Lync 2013</span></span>

  - <span data-ttu-id="938cf-126">Lync Windows Store 應用程式</span><span class="sxs-lookup"><span data-stu-id="938cf-126">Lync Windows Store app</span></span>

  - <span data-ttu-id="938cf-127">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="938cf-127">Lync Web App</span></span>

  - <span data-ttu-id="938cf-128">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="938cf-128">Lync Mobile</span></span>

  - <span data-ttu-id="938cf-129">Lync for Mac 2011</span><span class="sxs-lookup"><span data-stu-id="938cf-129">Lync for Mac 2011</span></span>

  - <span data-ttu-id="938cf-130">Lync Room System</span><span class="sxs-lookup"><span data-stu-id="938cf-130">Lync Room System</span></span>

  - <span data-ttu-id="938cf-131">Lync Basic 2013</span><span class="sxs-lookup"><span data-stu-id="938cf-131">Lync Basic 2013</span></span>

<span data-ttu-id="938cf-132">如需用戶端支援的詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="938cf-132">For details about client support, see the following topics:</span></span>

  - [<span data-ttu-id="938cf-133">Lync Online 用戶端</span><span class="sxs-lookup"><span data-stu-id="938cf-133">Clients for Lync Online</span></span>](https://go.microsoft.com/fwlink/?linkid=281902)

  - [<span data-ttu-id="938cf-134">Lync Server 2013 的用戶端比較表</span><span class="sxs-lookup"><span data-stu-id="938cf-134">Client comparison tables for Lync Server 2013</span></span>](lync-server-2013-desktop-client-comparison-tables.md)

  - [<span data-ttu-id="938cf-135">Lync Server 2013 的行動用戶端比較表</span><span class="sxs-lookup"><span data-stu-id="938cf-135">Mobile client comparison tables for Lync Server 2013</span></span>](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="938cf-136">拓撲需求</span><span class="sxs-lookup"><span data-stu-id="938cf-136">Topology Requirements</span></span>

<span data-ttu-id="938cf-137">若要使用商務用 Skype Online 設定混合部署，您必須具備下列其中一種支援的拓撲：</span><span class="sxs-lookup"><span data-stu-id="938cf-137">To configure your deployment for hybrid with Skype for Business Online, you need to have one of the following supported topologies:</span></span>

  - <span data-ttu-id="938cf-138">商務用 Skype Server 2015 部署，包含所有執行商務用 Skype Server 2015 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="938cf-138">A Skype for Business Server 2015 deployment with all servers running Skype for Business Server 2015.</span></span>

  - <span data-ttu-id="938cf-139">Lync Server 2013 部署，包含所有執行 Lync Server 2013 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="938cf-139">A Lync Server 2013 deployment with all servers running Lync Server 2013.</span></span>

  - <span data-ttu-id="938cf-140">Lync Server 2010 部署，其中包含所有執行 Lync Server 2010 的伺服器及最新的累計更新。</span><span class="sxs-lookup"><span data-stu-id="938cf-140">A Lync Server 2010 deployment with all servers running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="938cf-141">同盟 edge server 與下一個躍點伺服器的同盟 Edge server 必須執行 Lync Server 2010 及最新的累計更新。</span><span class="sxs-lookup"><span data-stu-id="938cf-141">The federation Edge Server and next hop server from the federation Edge Server must be running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="938cf-142">商務用 Skype Server 2015 或 Lync Server 2013 系統管理工具必須至少安裝在一部伺服器或管理工作站上。</span><span class="sxs-lookup"><span data-stu-id="938cf-142">The Skype for Business Server 2015 or Lync Server 2013 Administrative Tools must be installed on at least one server or management workstation.</span></span>

  - <span data-ttu-id="938cf-143">在至少一個執行商務用 Skype Server 2015 的網站中，具有下列伺服器角色的混合 Lync Server 2013 和商務用 Skype Server 2015 部署：</span><span class="sxs-lookup"><span data-stu-id="938cf-143">A mixed Lync Server 2013 and Skype for Business Server 2015 deployment with the following server roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="938cf-144">至少一個 Enterprise 集區或 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="938cf-144">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="938cf-145">與 SIP 同盟關聯的 Director 集區（如果有的話）</span><span class="sxs-lookup"><span data-stu-id="938cf-145">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="938cf-146">與 SIP 同盟相關聯的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="938cf-146">The Edge Pool associated with SIP federation</span></span>

  - <span data-ttu-id="938cf-147">在至少一個執行商務用 Skype Server 2015 的網站中，混合的 Lync Server 2010 和商務用 Skype Server 2015 部署（包含下列伺服器角色）</span><span class="sxs-lookup"><span data-stu-id="938cf-147">A mixed Lync Server 2010 and Skype for Business Server 2015 deployment with the following servers roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="938cf-148">至少一個 Enterprise 集區或 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="938cf-148">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="938cf-149">與 SIP 同盟關聯的 Director 集區（如果有的話）</span><span class="sxs-lookup"><span data-stu-id="938cf-149">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="938cf-150">與網站的 SIP 同盟相關聯的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="938cf-150">The Edge Pool associated with SIP federation for the Site</span></span>

  - <span data-ttu-id="938cf-151">在至少一個執行 Lync Server 2013 的網站中，混合式 Lync Server 2010 和 Lync Server 2013 部署具有下列伺服器角色：</span><span class="sxs-lookup"><span data-stu-id="938cf-151">A mixed Lync Server 2010 and Lync Server 2013 deployment with the following server roles in at least one site running Lync Server 2013:</span></span>
    
      - <span data-ttu-id="938cf-152">網站中至少有一個 Enterprise 集區或 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="938cf-152">At least one Enterprise Pool or Standard Edition server in the site</span></span>
    
      - <span data-ttu-id="938cf-153">與 SIP 同盟關聯的 Director 集區（如果它存在於網站中）</span><span class="sxs-lookup"><span data-stu-id="938cf-153">The Director Pool associated with SIP federation, if it exists in the site</span></span>
    
      - <span data-ttu-id="938cf-154">與網站的 SIP 同盟相關聯的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="938cf-154">The Edge Pool associated with SIP federation for the site</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="938cf-155">所有的使用者管理（包括使用者在內部部署和 UNRESOLVED_TOKEN_VAL (skypeforbusiness) Online 之間移動）都必須使用最新安裝的系統管理工具版本執行。</span><span class="sxs-lookup"><span data-stu-id="938cf-155">All user management, including user moves between on-premises and UNRESOLVED_TOKEN_VAL(skypeforbusiness) Online, needs to be done using the latest installed version of the administrative tools.</span></span> <span data-ttu-id="938cf-156">系統管理工具必須安裝在另一部伺服器上，且該伺服器具有現有內部部署部署和網際網路的 connect 存取權。</span><span class="sxs-lookup"><span data-stu-id="938cf-156">The administrative tools must be installed on a separate server that has connect access to the existing on-premises deployment and to the Internet.</span></span> <span data-ttu-id="938cf-157">將內部部署的使用者移至 UNRESOLVED_TOKEN_VAL (skype16_online) 的 <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> Cmdlet 必須從連接至內部部署的系統管理工具執行。</span><span class="sxs-lookup"><span data-stu-id="938cf-157">The <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> cmdlet to move users from your on-premises deployment to UNRESOLVED_TOKEN_VAL(skype16_online) must be run from the administrative tools connected to your on-premises deployment.</span></span>



</div>

<span data-ttu-id="938cf-158">如需支援的拓撲的詳細資訊，請參閱 [Lync server 2013 中支援的拓撲](lync-server-2013-supported-topologies.md)，以及 [適用于企業混合式部署的 Lync Server 2013 參考拓撲](https://go.microsoft.com/fwlink/p/?linkid=398709)。</span><span class="sxs-lookup"><span data-stu-id="938cf-158">For more information about supported topologies, see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md), and [Lync Server 2013 Reference Topologies for Enterprise Hybrid Deployments](https://go.microsoft.com/fwlink/p/?linkid=398709).</span></span>

<span data-ttu-id="938cf-159">如需有關混合部署的疑難排解資訊，並將 PowerShell 連接至 Lync Online，請參閱 [Lync online： lync PowerShell 和混合式疑難排解](https://go.microsoft.com/fwlink/p/?linkid=306718)。</span><span class="sxs-lookup"><span data-stu-id="938cf-159">For troubleshooting information about hybrid deployments and connecting PowerShell to Lync Online, see [Lync Online: Lync PowerShell and Hybrid Troubleshooting](https://go.microsoft.com/fwlink/p/?linkid=306718).</span></span>

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a><span data-ttu-id="938cf-160">同盟允許/封鎖清單的需求</span><span class="sxs-lookup"><span data-stu-id="938cf-160">Requirements for Federation Allowed/Blocked Lists</span></span>

<span data-ttu-id="938cf-161">允許的網域清單包括已設定協力廠商 Edge 完全限定功能變數名稱 (FQDN) 的網域。</span><span class="sxs-lookup"><span data-stu-id="938cf-161">The Allowed domains list includes domains that have a partner Edge fully qualified domain name (FQDN) configured.</span></span> <span data-ttu-id="938cf-162">這兩種情況有時候稱為「 *允許的夥伴伺服器* 」或「 *直接同盟夥伴*」。</span><span class="sxs-lookup"><span data-stu-id="938cf-162">These are sometimes referred to as *allowed partner servers* or *direct federation partners*.</span></span> <span data-ttu-id="938cf-163">您應熟悉開放式同盟和封閉式同盟之間的差異，在內部部署中分別稱為「協力廠商 *探索* 」和「允許的協力廠商」 *網域清單*」。</span><span class="sxs-lookup"><span data-stu-id="938cf-163">You should be familiar with the difference between Open Federation and Closed Federation, referred to as *partner discovery* and *allowed partner domain list*, respectively, in on-premises deployments.</span></span>

<span data-ttu-id="938cf-164">若要成功設定混合式部署，必須符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="938cf-164">The following requirements must be met to successfully configure a hybrid deployment:</span></span>

  - <span data-ttu-id="938cf-165">您的內部部署和您的 Microsoft 365 或 Office 365 組織必須設定符合網域的功能。</span><span class="sxs-lookup"><span data-stu-id="938cf-165">Domain matching must be configured the same for your on-premises deployment and your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="938cf-166">如果已在內部部署上啟用夥伴探索，則必須為您的線上租使用者設定開啟同盟。</span><span class="sxs-lookup"><span data-stu-id="938cf-166">If partner discovery is enabled on the on-premises deployment, then open federation must be configured for your online tenant.</span></span> <span data-ttu-id="938cf-167">若未啟用夥伴探索，則必須為您的線上租使用者設定關閉的同盟。</span><span class="sxs-lookup"><span data-stu-id="938cf-167">If partner discovery is not enabled, then closed federation must be configured for your online tenant.</span></span>

  - <span data-ttu-id="938cf-168">內部部署部署中的封鎖網域清單必須完全符合您線上租使用者的封鎖網域清單。</span><span class="sxs-lookup"><span data-stu-id="938cf-168">The Blocked domains list in the on-premises deployment must exactly match the Blocked domains list for your online tenant.</span></span>

  - <span data-ttu-id="938cf-169">內部部署部署中的允許網域清單必須完全符合您線上租使用者的允許網域清單。</span><span class="sxs-lookup"><span data-stu-id="938cf-169">The Allowed domains list in the on-premises deployment must exactly match the Allowed domains list for your online tenant.</span></span>

  - <span data-ttu-id="938cf-170">您必須為使用 Lync Online 控制台所設定的線上租使用者啟用外部通訊的同盟。</span><span class="sxs-lookup"><span data-stu-id="938cf-170">Federation must be enabled for the external communications for the online tenant, which is configured by using the Lync Online Control Panel.</span></span>

</div>

<div>

## <a name="dns-settings"></a><span data-ttu-id="938cf-171">DNS 設定</span><span class="sxs-lookup"><span data-stu-id="938cf-171">DNS Settings</span></span>

<span data-ttu-id="938cf-172">在建立混合部署的 DNS 記錄時，所有 Lync 外部 DNS 記錄都應該指向內部部署基礎結構。</span><span class="sxs-lookup"><span data-stu-id="938cf-172">When creating DNS records for hybrid deployments, all Lync external DNS records should point to the on-premises infrastructure.</span></span> <span data-ttu-id="938cf-173">如需必要 DNS 記錄的詳細資訊，請參閱 [網域名稱系統 (Lync Server 2013 的 DNS) 需求](lync-server-2013-domain-name-system-dns-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="938cf-173">For details on required DNS records, please refer to [Domain Name System (DNS) requirements for Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span></span>

<span data-ttu-id="938cf-174">此外，您必須確定下表中所述的 DNS 解析度可在您的內部部署中運作：</span><span class="sxs-lookup"><span data-stu-id="938cf-174">Additionally you need to ensure that the DNS resolution described in the following table works in your on-premises deployment:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="938cf-175">DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="938cf-175">DNS record</span></span></p></td>
<td><p><span data-ttu-id="938cf-176">可解析的</span><span class="sxs-lookup"><span data-stu-id="938cf-176">Resolvable by</span></span></p></td>
<td><p><span data-ttu-id="938cf-177">DNS 需求</span><span class="sxs-lookup"><span data-stu-id="938cf-177">DNS requirement</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="938cf-178">_Sipfederationtls 的 DNS SRV 記錄。 _tcp c0/>sipdomain.com 以 &gt; 取得所有支援的 SIP 網域解析至存取 Edge 外部 IP (s) </span><span class="sxs-lookup"><span data-stu-id="938cf-178">DNS SRV record for _sipfederationtls._tcp.&lt;sipdomain.com&gt; for all supported SIP domains resolving to Access Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="938cf-179">Edge server (s) </span><span class="sxs-lookup"><span data-stu-id="938cf-179">Edge server(s)</span></span></p></td>
<td><p><span data-ttu-id="938cf-180">在混合式設定中啟用同盟通訊。</span><span class="sxs-lookup"><span data-stu-id="938cf-180">Enable federated communication in a hybrid configuration.</span></span> <span data-ttu-id="938cf-181">Edge Server 需要知道如何路由傳送內部部署和線上間的 SIP 網域的同盟流量。</span><span class="sxs-lookup"><span data-stu-id="938cf-181">The Edge Server needs to know where to route federated traffic for the SIP domain that is split between on premises and online.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="938cf-182">DNS A 記錄 (s) Edge Web 會議服務 FQDN，例如 webcon.contoso.com 解析為 Web 會議 Edge 外部 IP (s) </span><span class="sxs-lookup"><span data-stu-id="938cf-182">DNS A record(s) for Edge Web Conferencing Service FQDN, e.g. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="938cf-183">連線使用者電腦的內部公司網路</span><span class="sxs-lookup"><span data-stu-id="938cf-183">Internal corporate network connected users’ computers</span></span></p></td>
<td><p><span data-ttu-id="938cf-184">讓線上使用者可以在內部部署主控會議中呈現或查看內容。</span><span class="sxs-lookup"><span data-stu-id="938cf-184">Enable online users to present or view content in on-premises hosted meetings.</span></span> <span data-ttu-id="938cf-185">內容包括 PowerPoint 檔案、白板、投票和共用附注。</span><span class="sxs-lookup"><span data-stu-id="938cf-185">Content includes PowerPoint files, whiteboards, polls, and shared notes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="938cf-186">根據組織中設定 DNS 的方式，您可能需要將這些記錄新增至對應 SIP 網域的內部主控 DNS 區域， (s) 以提供對這些記錄的內部 DNS 解析。</span><span class="sxs-lookup"><span data-stu-id="938cf-186">Depending on how DNS is configured in your organization, you may need to add these records to the internal hosted DNS zone for the corresponding SIP domain(s) to provide internal DNS resolution to these records.</span></span>

</div>

<div>

## <a name="firewall-considerations"></a><span data-ttu-id="938cf-187">防火牆的考量</span><span class="sxs-lookup"><span data-stu-id="938cf-187">Firewall Considerations</span></span>

<span data-ttu-id="938cf-188">網路上的電腦必須能夠執行標準網際網路 DNS 查閱。</span><span class="sxs-lookup"><span data-stu-id="938cf-188">Computers on your network must be able to perform standard Internet DNS lookups.</span></span> <span data-ttu-id="938cf-189">若這些電腦可以搜尋標準網際網路網站，表示您的網路符合此需求。</span><span class="sxs-lookup"><span data-stu-id="938cf-189">If these computers can reach standard Internet sites, your network meets this requirement.</span></span>

<span data-ttu-id="938cf-190">根據您的 Microsoft 線上服務資料中心的位置，您也必須設定網路防火牆裝置，以接受以萬用字元功能變數名稱為基礎的連線 (例如，所有來自 \* outlook.com) 的流量。</span><span class="sxs-lookup"><span data-stu-id="938cf-190">Depending on the location of your Microsoft Online Services data center, you must also configure your network firewall devices to accept connections based on wildcard domain names (for example, all traffic from \*.outlook.com).</span></span> <span data-ttu-id="938cf-191">如果您組織的防火牆不支援萬用字元名稱設定，您必須手動判斷您要允許的 IP 位址範圍和指定的埠。</span><span class="sxs-lookup"><span data-stu-id="938cf-191">If your organization’s firewalls do not support wildcard name configurations, you will have to manually determine the IP address ranges that you would like to allow and the specified ports.</span></span>

<span data-ttu-id="938cf-192">請參閱 Help 主題 [Office 365 URLs 和 IP 位址範圍](https://go.microsoft.com/fwlink/p/?linkid=252942)。</span><span class="sxs-lookup"><span data-stu-id="938cf-192">Refer to the Help topic [Office 365 URLs and IP address ranges](https://go.microsoft.com/fwlink/p/?linkid=252942).</span></span>

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a><span data-ttu-id="938cf-193">埠和通訊協定需求</span><span class="sxs-lookup"><span data-stu-id="938cf-193">Port and Protocol Requirements</span></span>

<span data-ttu-id="938cf-194">除了內部 Lync Server 2013 通訊的埠需求之外，您還必須設定下列埠。</span><span class="sxs-lookup"><span data-stu-id="938cf-194">In addition to the port requirements for internal Lync Server 2013 communication, you must also configure the following ports.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="938cf-195">通訊協定/埠</span><span class="sxs-lookup"><span data-stu-id="938cf-195">Protocol / Port</span></span></th>
<th><span data-ttu-id="938cf-196">應用程式</span><span class="sxs-lookup"><span data-stu-id="938cf-196">Applications</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="938cf-197">TCP 443</span><span class="sxs-lookup"><span data-stu-id="938cf-197">TCP 443</span></span></p></td>
<td><p><span data-ttu-id="938cf-198">開放輸入</span><span class="sxs-lookup"><span data-stu-id="938cf-198">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="938cf-199">Active Directory Federation Services (同盟伺服器角色)</span><span class="sxs-lookup"><span data-stu-id="938cf-199">Active Directory Federation Services (federation server role)</span></span></p>
<p><span data-ttu-id="938cf-200">如需詳細資訊，請參閱 <a href="https://go.microsoft.com/fwlink/p/?linkid=281899">瞭解 AD FS 角色服務</a>。</span><span class="sxs-lookup"><span data-stu-id="938cf-200">For more information, see <a href="https://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS Role Services</a>.</span></span></p></li>
<li><p><span data-ttu-id="938cf-201">Active Directory Federation Services (Proxy 伺服器角色)</span><span class="sxs-lookup"><span data-stu-id="938cf-201">Active Directory Federation Services (proxy server role)</span></span></p></li>
<li><p><span data-ttu-id="938cf-202">Microsoft Online Services 入口網站</span><span class="sxs-lookup"><span data-stu-id="938cf-202">Microsoft Online Services Portal</span></span></p></li>
<li><p><span data-ttu-id="938cf-203">我的公司入口網站</span><span class="sxs-lookup"><span data-stu-id="938cf-203">My Company Portal</span></span></p></li>
<li><p><span data-ttu-id="938cf-204">Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="938cf-204">Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="938cf-205">Lync 用戶端 (從內部部署 Lync Server 的 Lync Online 通訊) </span><span class="sxs-lookup"><span data-stu-id="938cf-205">Lync client (communication to Lync Online from on-premises Lync Server)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="938cf-206">TCP 80 和443</span><span class="sxs-lookup"><span data-stu-id="938cf-206">TCP 80 and 443</span></span></p></td>
<td><p><span data-ttu-id="938cf-207">開放輸入</span><span class="sxs-lookup"><span data-stu-id="938cf-207">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="938cf-208">Microsoft Online Services 目錄同步作業工具</span><span class="sxs-lookup"><span data-stu-id="938cf-208">Microsoft Online Services Directory Synchronization Tool</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="938cf-209">TCP 5061</span><span class="sxs-lookup"><span data-stu-id="938cf-209">TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="938cf-210">開啟 Edge Server 上的輸入/輸出</span><span class="sxs-lookup"><span data-stu-id="938cf-210">Open inbound/outbound on the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="938cf-211">PSOM/TLS 443</span><span class="sxs-lookup"><span data-stu-id="938cf-211">PSOM/TLS 443</span></span></p></td>
<td><p><span data-ttu-id="938cf-212">開啟資料共用會話的輸入/輸出</span><span class="sxs-lookup"><span data-stu-id="938cf-212">Open inbound/outbound for data sharing sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="938cf-213">STUN/TCP 443</span><span class="sxs-lookup"><span data-stu-id="938cf-213">STUN/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="938cf-214">開啟輸入/輸出音訊、影片、應用程式共用會話</span><span class="sxs-lookup"><span data-stu-id="938cf-214">Open inbound/outbound for audio, video, application sharing sessions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="938cf-215">STUN/UDP 3478</span><span class="sxs-lookup"><span data-stu-id="938cf-215">STUN/UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="938cf-216">開啟音訊和影片的輸入/輸出</span><span class="sxs-lookup"><span data-stu-id="938cf-216">Open inbound/outbound for audio and video sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="938cf-217">RTP/TCP 50000-59999</span><span class="sxs-lookup"><span data-stu-id="938cf-217">RTP/TCP 50000-59999</span></span></p></td>
<td><p><span data-ttu-id="938cf-218">開啟音訊及視頻會話的輸出</span><span class="sxs-lookup"><span data-stu-id="938cf-218">Open outbound for audio and video sessions</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a><span data-ttu-id="938cf-219">使用者帳戶和資料</span><span class="sxs-lookup"><span data-stu-id="938cf-219">User Accounts and Data</span></span>

<span data-ttu-id="938cf-220">在 Lync Server 2013 混合式部署中，您想要在 Lync Online 中建立的任何使用者，必須先在內部部署中建立，以便在 Active Directory 網域服務中建立使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="938cf-220">In a Lync Server 2013 hybrid deployment, any user that you want to home in Lync Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="938cf-221">然後，您可以將使用者移至商務用 Skype Online，這會移動使用者的連絡人清單。</span><span class="sxs-lookup"><span data-stu-id="938cf-221">You can then move the user to Skype for Business Online, which will move the user’s contact list.</span></span>

<span data-ttu-id="938cf-222">當您使用 AD FS 和 Dirsync 在您的 Lync 內部部署和 Lync Online 部署之間同步處理使用者帳戶時，即使使用者未移至 Lync Online，您還是必須同步處理組織內部部署和線上 Lync 部署間所有 Lync 使用者的 AD 帳戶。</span><span class="sxs-lookup"><span data-stu-id="938cf-222">When you synchronize user accounts between your Lync on-premises and Lync Online deployments with AD FS and Dirsync, you need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="938cf-223">如果您未同步處理所有使用者，組織中內部部署與線上使用者之間的通訊可能無法如預期的方式運作。</span><span class="sxs-lookup"><span data-stu-id="938cf-223">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="938cf-224">如果使用者是使用 Microsoft 365 系統管理中心的線上入口網站建立，使用者帳戶將不會與內部部署 Active Directory 同步處理，而且使用者將不會存在於內部部署 Active Directory 中。</span><span class="sxs-lookup"><span data-stu-id="938cf-224">If the user is created by using the online portal for Microsoft 365 admin center, the user account will not be synchronized with on-premises Active Directory, and the user will not exist in the on-premises Active Directory.</span></span> <span data-ttu-id="938cf-225">如果您已在 Lync Online 中建立使用者，而且想要使用內部部署的 Lync 伺服器設定混合，請參閱在 <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Lync Server 2013 中將使用者從 Lync Online 移至 lync 內部部署</A>。</span><span class="sxs-lookup"><span data-stu-id="938cf-225">If you have already created users in Lync Online, and want to configure hybrid with an on-premises Lync Server, see <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="938cf-226">在規劃混合式部署時，您也應考慮下列使用者相關的問題。</span><span class="sxs-lookup"><span data-stu-id="938cf-226">You should also consider the following user-related issues when planning for a hybrid deployment.</span></span>

  - <span data-ttu-id="938cf-227">**使用者連絡人**    Lync Online 使用者的連絡人限制為250。</span><span class="sxs-lookup"><span data-stu-id="938cf-227">**User contacts**   The limit for contacts for Lync Online users is 250.</span></span> <span data-ttu-id="938cf-228">當帳戶移至 Lync Online 時，任何超出該號碼的連絡人都會從使用者的連絡人清單中移除。</span><span class="sxs-lookup"><span data-stu-id="938cf-228">Any contacts beyond that number will be removed from the user’s contact list when the account is moved to Lync Online.</span></span>

  - <span data-ttu-id="938cf-229">**立即訊息與顯示狀態**    使用者連絡人清單、群組和存取控制清單 (ACLs) 會以使用者帳戶一起遷移。</span><span class="sxs-lookup"><span data-stu-id="938cf-229">**Instant Messaging and Presence**   User contact lists, groups, and access control lists (ACLs) are migrated with the user account.</span></span>

  - <span data-ttu-id="938cf-230">**會議資料、會議內容及排程的會議**    此內容不會與使用者帳戶一起遷移。</span><span class="sxs-lookup"><span data-stu-id="938cf-230">**Conferencing data, meeting content, and scheduled meetings**   This content is not migrated with the user account.</span></span> <span data-ttu-id="938cf-231">使用者在將其帳戶遷移至 Lync Online 後，必須重新排定會議。</span><span class="sxs-lookup"><span data-stu-id="938cf-231">Users must reschedule meetings after their accounts are migrated to Lync Online.</span></span>

</div>

<div>

## <a name="user-policies-and-features"></a><span data-ttu-id="938cf-232">使用者原則及功能</span><span class="sxs-lookup"><span data-stu-id="938cf-232">User Policies and Features</span></span>

  - <span data-ttu-id="938cf-233">在 Lync Server 2013 混合式環境中，使用者可以在內部部署或線上上啟用立即訊息、語音和會議，但不能同時啟用兩者。</span><span class="sxs-lookup"><span data-stu-id="938cf-233">In a Lync Server 2013 hybrid environment, users can be enabled for Instant Messaging, voice, and meetings either on-premises or online, but not both simultaneously.</span></span>

  - <span data-ttu-id="938cf-234">**Lync 用戶端**    當某些使用者移至 Lync Online 時，可能需要新的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="938cf-234">**Lync Client**    Some users may require a new client version when they are moved to Lync Online.</span></span> <span data-ttu-id="938cf-235">若為 Office 通訊伺服器 2007 R2，使用者必須先移至 Lync Server 2013 集區，再遷移至 Lync Online。</span><span class="sxs-lookup"><span data-stu-id="938cf-235">For Office Communications Server 2007 R2, users must be moved to a Lync Server 2013 pool prior to migration to Lync Online.</span></span>
    
    <span data-ttu-id="938cf-236">如需用戶端支援的詳細資訊，請參閱 [用戶端的 Lync Online](https://go.microsoft.com/fwlink/p/?linkid=281902) 和 [支援的 lync 用戶端和網路埠](https://go.microsoft.com/fwlink/p/?linkid=281901)設定。</span><span class="sxs-lookup"><span data-stu-id="938cf-236">For more information about client support, see [Clients for Lync Online](https://go.microsoft.com/fwlink/p/?linkid=281902) and [Supported Lync clients and network port configurations](https://go.microsoft.com/fwlink/p/?linkid=281901).</span></span>

  - <span data-ttu-id="938cf-237">\*\*內部部署原則和設定 (非使用者) \*\*    線上和內部部署原則需要不同的設定。</span><span class="sxs-lookup"><span data-stu-id="938cf-237">**On-premises policies and configuration (non-user)**   Online and on-premises policies require separate configuration.</span></span> <span data-ttu-id="938cf-238">您無法設定適用于這兩者的全域原則。</span><span class="sxs-lookup"><span data-stu-id="938cf-238">You cannot set global policies that apply to both.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
