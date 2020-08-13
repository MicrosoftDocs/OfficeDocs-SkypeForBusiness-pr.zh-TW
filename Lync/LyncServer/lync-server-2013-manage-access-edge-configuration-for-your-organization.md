---
title: Lync Server 2013：管理組織的 Access Edge 設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Access Edge Configuration for your organization
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31aa51647fa19a11cb4944829c2ab5e8eb10f2e7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a><span data-ttu-id="2137f-102">在 Lync Server 2013 中管理組織的 Access Edge 設定</span><span class="sxs-lookup"><span data-stu-id="2137f-102">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2137f-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2137f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2137f-104">這是初步檔，而且可能會變更。</span><span class="sxs-lookup"><span data-stu-id="2137f-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="2137f-105">空白主題會以預留位置形式包含。</span><span class="sxs-lookup"><span data-stu-id="2137f-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="2137f-106">部署一或多部 Edge Server 之後，您必須透過您組織支援的 Edge Server，啟用外部網域或提供者存取的類型、遠端使用者存取和匿名使用者對會議的存取。</span><span class="sxs-lookup"><span data-stu-id="2137f-106">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="2137f-107">下列選項包含可透過「Access Edge 設定」\*\*\*\* 頁面設定的存取類型：</span><span class="sxs-lookup"><span data-stu-id="2137f-107">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="2137f-108">**啟用同盟和公用 IM**     連線如果您想要支援使用者對同盟夥伴網域的存取，請啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="2137f-108">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="2137f-109">此設定會套用到針對 [**外部存取原則**] 頁面上的全域、網站或使用者範圍所設定的 SIP 同盟和 XMPP 同盟。</span><span class="sxs-lookup"><span data-stu-id="2137f-109">This setting applies to both SIP federation and XMPP federation that are configured for global, site or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="2137f-110">若要套用同盟設定，您必須在這兩個頁面上設定同盟支援。</span><span class="sxs-lookup"><span data-stu-id="2137f-110">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="2137f-111">此外，還提供兩個選用設定選項：同盟協力廠商的探索方式，以及是否將封存免責聲明傳送給連絡人 (通知與您進行通訊的同盟連絡人，您的部署已啟用封存，因此將會封存通訊詳細資料)。</span><span class="sxs-lookup"><span data-stu-id="2137f-111">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts</span></span>
    
      - <span data-ttu-id="2137f-112">**啟用夥伴網域探索**    選取此選項可自動探索您可以同盟的網域。</span><span class="sxs-lookup"><span data-stu-id="2137f-112">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="2137f-113">Lync Server 2013 使用網域名稱系統 (DNS) 記錄，以嘗試找出未列在 [允許的網域] 清單中的網域、自動評估已發現同盟夥伴的內送流量，並根據信任層級、流量量和系統管理員設定來限制或封鎖該流量。</span><span class="sxs-lookup"><span data-stu-id="2137f-113">Lync Server 2013 uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="2137f-114">如果您未選取此選項，則只有您在允許的網域清單上所包含之網域中的使用者啟用同盟使用者存取。</span><span class="sxs-lookup"><span data-stu-id="2137f-114">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="2137f-115">不論是否選取此選項，您都可以指定要封鎖或允許的個別網域，包括限制存取同盟網域中的 Access Edge service 的特定伺服器。</span><span class="sxs-lookup"><span data-stu-id="2137f-115">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="2137f-116">如需詳細資訊，請參閱[Configure support for 允許的外部網域 In Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md)。</span><span class="sxs-lookup"><span data-stu-id="2137f-116">For details, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>
    
      - <span data-ttu-id="2137f-117">**將封存免責聲明傳送給同盟夥伴**    選取此選項可讓您將封存免責聲明郵件傳送給同盟協力廠商，以告知其會記錄通訊詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2137f-117">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="2137f-118">如果您封存與同盟協力廠商網域的外部通訊，應啟用封存免責聲明通知，以警告合作夥伴您的部署已封存其郵件和通訊詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2137f-118">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="2137f-119">如需有關封存的詳細資訊，請參閱[在 Lync Server 2013 中定義您的封存需求](lync-server-2013-defining-your-requirements-for-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="2137f-119">For details on archiving, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span></span>

  - <span data-ttu-id="2137f-120">**啟用遠端使用者存取**    如果您想要在您的組織中的使用者（例如出差的遠端辦公和使用者）能夠連線至 Lync Server，請啟用此選項。</span><span class="sxs-lookup"><span data-stu-id="2137f-120">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server.</span></span> <span data-ttu-id="2137f-121">如需詳細資訊，請參閱[Enable or disable remote user access In Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="2137f-121">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="2137f-122">**讓匿名使用者能夠存取會議**    如果您希望內部使用者邀請外部匿名使用者加入其組織的會議，請啟用此選項。</span><span class="sxs-lookup"><span data-stu-id="2137f-122">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="2137f-123">啟用此設定只允許匿名使用者進行會議。</span><span class="sxs-lookup"><span data-stu-id="2137f-123">Enabling this setting only allows anonymous users for conferences.</span></span> <span data-ttu-id="2137f-124">若要設定會議經驗和選項，以定義使用者如何使用會議及包含匿名使用者執行的工作，請參閱[建立或修改會議使用者經驗的網站或使用者](https://technet.microsoft.com/library/gg429715\(v=ocs.15\))和[會議原則設定參考（適用于 Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)）。</span><span class="sxs-lookup"><span data-stu-id="2137f-124">To configure the conferencing experience and options that will define how and what your users can do with conferences and for the inclusion of anonymous users, see details at [Create or Modify Conferencing User Experience for a Site or Users](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) and [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2137f-125">除了啟用外部使用者存取支援，您還可以設定相關原則以控制組織遠端使用者存取，接著才將任何類型的外部使用者存取功能提供給使用者。</span><span class="sxs-lookup"><span data-stu-id="2137f-125">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="2137f-126">如需建立、設定及套用外部使用者存取之原則的詳細資訊，請參閱<A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy In Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="2137f-126">For details about creating, configuring, and applying policies for external user access, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="2137f-127">**使用 Windows PowerShell Cmdlet 來查看 Access Edge 設定資訊**</span><span class="sxs-lookup"><span data-stu-id="2137f-127">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="2137f-128">使用 Windows PowerShell 和**Get-CsAccessEdgeConfiguration** Cmdlet 可以查看 Access Edge 設定資訊。</span><span class="sxs-lookup"><span data-stu-id="2137f-128">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="2137f-129">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2137f-129">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2137f-130">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="2137f-130">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="2137f-131">若要查看所有 Access Edge 設定設定的資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="2137f-131">To view information about all your Access Edge configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsAccessEdgeConfiguration
    
    <span data-ttu-id="2137f-132">如此將傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="2137f-132">That will return information similar to this:</span></span>
    
        Identity                               : Global
        AllowAnonymousUsers                    : False
        AllowFederatedUsers                    : False
        AllowOutsideUsers                      : True
        BeClearingHouse                        : False
        EnablePartnerDiscovery                 : False
        EnableArchivingDisclaimer              : False
        EnableUserReplicator                   : True
        KeepCrlsUpToDateForPeers               : True
        MarkSourceVerifiableOnOutgoingMessages : True
        OutgoingTlsCountForFederatedPartners   : 4
        DiscoveredPartnerStandardRate          : 20
        EnableDiscoveredPartnerContactsLimit   : True
        MaxContactsPerDiscoveredPartner        : 1000
        DiscoveredPartnerReportPeriodMinutes   : 60
        MaxAcceptedCertificatesStored          : 1000
        MaxRejectedCertificatesStored          : 500
        CertificatesDeletedPercentage          : 20
        RoutingMethod                          : UseDnsSrvRouting

<div>

## <a name="in-this-section"></a><span data-ttu-id="2137f-133">本章節內容</span><span class="sxs-lookup"><span data-stu-id="2137f-133">In This Section</span></span>

  - [<span data-ttu-id="2137f-134">在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="2137f-134">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [<span data-ttu-id="2137f-135">在 Lync Server 2013 中啟用或停用同盟協力廠商的探索</span><span class="sxs-lookup"><span data-stu-id="2137f-135">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [<span data-ttu-id="2137f-136">在 Lync Server 2013 中啟用或停用傳送封存免責聲明至同盟合作夥伴的功能</span><span class="sxs-lookup"><span data-stu-id="2137f-136">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="2137f-137">在 Lync Server 2013 中啟用或停用遠端使用者存取</span><span class="sxs-lookup"><span data-stu-id="2137f-137">Enable or disable remote user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [<span data-ttu-id="2137f-138">在 Lync Server 2013 中啟用或停用匿名使用者存取</span><span class="sxs-lookup"><span data-stu-id="2137f-138">Enable or disable anonymous user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [<span data-ttu-id="2137f-139">在 Lync Server 2013 中指派會議原則以支援匿名使用者</span><span class="sxs-lookup"><span data-stu-id="2137f-139">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

