---
title: 管理組織的 Access Edge 設定
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 在部署一或多個 Edge 伺服器之後, 您必須透過您組織支援的邊緣伺服器來啟用外部網域或提供者存取的類型、遠端使用者存取權, 以及匿名使用者對會議的存取權。
ms.openlocfilehash: b79560d2cb0e570ab2b4fcf061a5b91c6a74a8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188857"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="6c0b2-103">管理組織的 Access Edge 設定</span><span class="sxs-lookup"><span data-stu-id="6c0b2-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="6c0b2-104">在部署一或多個 Edge 伺服器之後, 您必須透過您組織支援的邊緣伺服器來啟用外部網域或提供者存取的類型、遠端使用者存取權, 以及匿名使用者對會議的存取權。</span><span class="sxs-lookup"><span data-stu-id="6c0b2-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="6c0b2-105">這些選項包括可透過 [**存取邊緣**設定] 頁面進行設定的下列存取類型:</span><span class="sxs-lookup"><span data-stu-id="6c0b2-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="6c0b2-106">\*\*\*\*    如果您想要支援使用者存取聯盟夥伴網域, 請啟用同盟與公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="6c0b2-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="6c0b2-107">此設定會套用到針對 [**外部存取原則**] 頁面上的全域、網站或使用者範圍所設定的 SIP 同盟。</span><span class="sxs-lookup"><span data-stu-id="6c0b2-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="6c0b2-108">若要套用聯盟設定, 您必須在兩個頁面上都設定同盟支援。</span><span class="sxs-lookup"><span data-stu-id="6c0b2-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="6c0b2-109">有兩個選項是如何探索同盟夥伴的選擇性設定, 以及是否要封存免責聲明 (通知您與您的部署已啟用封存且通訊詳細資料將會傳送給連絡人:</span><span class="sxs-lookup"><span data-stu-id="6c0b2-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="6c0b2-110">**啟用合作夥伴網域探索**   選取此選項可讓您自動探索您可以與其聯盟的網域。</span><span class="sxs-lookup"><span data-stu-id="6c0b2-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="6c0b2-111">商務用 Skype 伺服器使用網域名稱系統 (DNS) 記錄來嘗試找出未列于 [允許的網域] 清單中的網域, 自動評估已探索聯盟夥伴的傳入流量, 並根據信任限制或封鎖該流量層級、流量數量及系統管理員設定。</span><span class="sxs-lookup"><span data-stu-id="6c0b2-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="6c0b2-112">如果您沒有選取此選項, 即會針對您在 [允許的網域] 清單中所包含的網域中的使用者啟用 [聯盟使用者存取]。</span><span class="sxs-lookup"><span data-stu-id="6c0b2-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="6c0b2-113">不論您是否選取此選項, 您都可以指定要封鎖或允許的個別網域, 包括限制對執行聯盟網域中之存取邊緣服務之特定伺服器的存取權。</span><span class="sxs-lookup"><span data-stu-id="6c0b2-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="6c0b2-114">如需詳細資訊, 請參閱[設定允許外部網域的支援](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="6c0b2-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="6c0b2-115">**傳送封存免責聲明給聯盟合作夥伴**   選取此選項可將封存免責聲明訊息傳送給聯盟夥伴, 以提醒他們已記錄溝通詳細資料。</span><span class="sxs-lookup"><span data-stu-id="6c0b2-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="6c0b2-116">如果您將外部通訊與同盟夥伴網域封存, 您應該啟用 [封存放棄免責聲明通知], 警告合作夥伴他們的訊息和通訊詳細資料是由您的部署所歸檔。</span><span class="sxs-lookup"><span data-stu-id="6c0b2-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="6c0b2-117">如需有關存檔的詳細資訊, 請參閱[啟用或停用將封存免責聲明傳送給聯盟合作夥伴](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)。</span><span class="sxs-lookup"><span data-stu-id="6c0b2-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="6c0b2-118">**[啟用遠端使用者存取**   ] 如果您想讓貴組織外部的使用者 (例如出差的遠端電腦和使用者) 能夠連線到商務用 Skype Server, 請啟用此選項。</span><span class="sxs-lookup"><span data-stu-id="6c0b2-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="6c0b2-119">如需詳細資訊, 請參閱[啟用或停用遠端使用者存取](enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="6c0b2-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="6c0b2-120">\*\*\*\*    如果您希望內部使用者向組織的會議邀請外部匿名使用者, 請啟用 [匿名使用者存取會議] 選項。</span><span class="sxs-lookup"><span data-stu-id="6c0b2-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="6c0b2-121">啟用此設定只允許匿名使用者進行會議。</span><span class="sxs-lookup"><span data-stu-id="6c0b2-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="6c0b2-122">除了啟用外部使用者存取支援之外, 您也可以在使用者提供任何類型的外部使用者存取之前, 設定策略來控制您組織中的遠端使用者存取權。</span><span class="sxs-lookup"><span data-stu-id="6c0b2-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="6c0b2-123">如需建立、設定及套用外部使用者存取原則的詳細資料, 請參閱[管理貴組織的外部存取原則](../external-access-policies/manage-external-access-policy-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="6c0b2-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="6c0b2-124">**使用 Windows PowerShell Cmdlet 來查看存取邊緣配置資訊**</span><span class="sxs-lookup"><span data-stu-id="6c0b2-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="6c0b2-125">您可以使用 Windows PowerShell 和**CsAccessEdgeConfiguration** Cmdlet 來查看存取邊緣配置資訊。</span><span class="sxs-lookup"><span data-stu-id="6c0b2-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="6c0b2-126">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6c0b2-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="6c0b2-127">若要查看所有存取邊緣設定的相關資訊, 請在商務用 Skype Server 管理命令介面中輸入下列命令, 然後按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="6c0b2-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="6c0b2-128">這會傳回如下所示的資訊:</span><span class="sxs-lookup"><span data-stu-id="6c0b2-128">That will return information similar to this:</span></span>
    
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

