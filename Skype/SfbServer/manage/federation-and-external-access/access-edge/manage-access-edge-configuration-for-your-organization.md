---
title: 管理貴組織的 Access Edge 設定
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 部署一或多部 Edge Server 之後，您必須透過您組織支援的 Edge Server，啟用外部網域或提供者存取的類型、遠端使用者存取和匿名使用者對會議的存取。
ms.openlocfilehash: 63d33a5dd3459aef5f657d8ab5772515a16e7915
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817333"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="ea9c8-103">管理貴組織的 Access Edge 設定</span><span class="sxs-lookup"><span data-stu-id="ea9c8-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="ea9c8-104">部署一或多部 Edge Server 之後，您必須透過您組織支援的 Edge Server，啟用外部網域或提供者存取的類型、遠端使用者存取和匿名使用者對會議的存取。</span><span class="sxs-lookup"><span data-stu-id="ea9c8-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="ea9c8-105">下列選項包含可透過「Access Edge 設定」頁面設定的存取類型：</span><span class="sxs-lookup"><span data-stu-id="ea9c8-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="ea9c8-106">**啟用同盟和公用 IM**   連線  如果您想要支援使用者對同盟夥伴網域的存取，請啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="ea9c8-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="ea9c8-107">此設定適用于針對 [ **外部存取原則** ] 頁面上的全域、網站或使用者範圍所設定的 SIP 同盟。</span><span class="sxs-lookup"><span data-stu-id="ea9c8-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="ea9c8-108">若要套用同盟設定，您必須在這兩個頁面上設定同盟支援。</span><span class="sxs-lookup"><span data-stu-id="ea9c8-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="ea9c8-109">有兩個選項是如何探索同盟協力廠商的選用設定，以及封存免責聲明是否 (通知，告知您的部署已啟用封存，而且會將通訊詳細資料封存) 傳送給連絡人：</span><span class="sxs-lookup"><span data-stu-id="ea9c8-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="ea9c8-110">**啟用夥伴網域探索**   選取此選項可自動探索您可以同盟的網域。</span><span class="sxs-lookup"><span data-stu-id="ea9c8-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="ea9c8-111">商務用 Skype Server 使用網域名稱系統 (DNS) 記錄，以嘗試找出未列在 [允許的網域] 清單中的網域、自動評估已發現同盟夥伴的內送流量，並根據信任層級、流量量和系統管理員設定來限制或封鎖該流量。</span><span class="sxs-lookup"><span data-stu-id="ea9c8-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="ea9c8-112">如果您未選取此選項，則只有您在允許的網域清單上所包含之網域中的使用者啟用同盟使用者存取。</span><span class="sxs-lookup"><span data-stu-id="ea9c8-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="ea9c8-113">不論是否選取此選項，您都可以指定要封鎖或允許的個別網域，包括限制存取同盟網域中的 Access Edge service 的特定伺服器。</span><span class="sxs-lookup"><span data-stu-id="ea9c8-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="ea9c8-114">如需詳細資訊，請參閱 [Configure support for a 允許的外部網域](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="ea9c8-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="ea9c8-115">**將封存免責聲明傳送給同盟夥伴**   選取此選項可讓您將封存免責聲明郵件傳送給同盟協力廠商，以告知其會記錄通訊詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ea9c8-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="ea9c8-116">如果您封存與同盟協力廠商網域的外部通訊，應啟用封存免責聲明通知，以警告合作夥伴您的部署已封存其郵件和通訊詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ea9c8-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="ea9c8-117">如需有關封存的詳細資訊，請參閱 [啟用或停用將封存免責聲明傳送給](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)同盟協力廠商。</span><span class="sxs-lookup"><span data-stu-id="ea9c8-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="ea9c8-118">**啟用遠端使用者存取**   如果您想要在您的組織中的使用者（例如出差的遠端辦公和使用者）可以連線到商務用 Skype Server，請啟用此選項。</span><span class="sxs-lookup"><span data-stu-id="ea9c8-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="ea9c8-119">如需詳細資訊，請參閱 [啟用或停用遠端使用者存取](enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="ea9c8-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="ea9c8-120">**讓匿名使用者能夠存取會議**   如果您希望內部使用者邀請外部匿名使用者加入其組織的會議，請啟用此選項。</span><span class="sxs-lookup"><span data-stu-id="ea9c8-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="ea9c8-121">啟用此設定只允許匿名使用者進行會議。</span><span class="sxs-lookup"><span data-stu-id="ea9c8-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="ea9c8-122">除了啟用外部使用者存取支援，您還可以設定相關原則以控制組織遠端使用者存取，接著才將任何類型的外部使用者存取功能提供給使用者。</span><span class="sxs-lookup"><span data-stu-id="ea9c8-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="ea9c8-123">如需建立、設定及套用外部使用者存取之原則的詳細資訊，請參閱 [管理組織的外部存取原則](../external-access-policies/manage-external-access-policy-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="ea9c8-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="ea9c8-124">**使用 Windows PowerShell Cmdlet 來查看 Access Edge 設定資訊**</span><span class="sxs-lookup"><span data-stu-id="ea9c8-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="ea9c8-125">使用 Windows PowerShell 和 **Get-CsAccessEdgeConfiguration** Cmdlet 可以查看 Access Edge 設定資訊。</span><span class="sxs-lookup"><span data-stu-id="ea9c8-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="ea9c8-126">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ea9c8-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="ea9c8-127">若要查看所有 Access Edge 設定設定的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="ea9c8-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="ea9c8-128">如此將傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="ea9c8-128">That will return information similar to this:</span></span>
    
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

