---
title: 設定商務用 Skype 混合式
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 摘要：瞭解如何設定內部部署和商務用 Skype Online 之間的互通性。
ms.openlocfilehash: 0df507fcc47157a9290018a199e1362cb203048b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221447"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="70069-103">設定商務用 Skype 混合式</span><span class="sxs-lookup"><span data-stu-id="70069-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="70069-104">若要設定商務用 Skype 混合式，您必須：</span><span class="sxs-lookup"><span data-stu-id="70069-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="70069-105">[將內部部署 Edge Service 設定為與 Microsoft 365 或 Office 365](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365)同盟。</span><span class="sxs-lookup"><span data-stu-id="70069-105">[Configure your on-premises Edge service to federate with Microsoft 365 or Office 365](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365).</span></span>
- <span data-ttu-id="70069-106">[設定您的內部部署環境，以信任 Microsoft 365 或 Office 365 並啟用共用 SIP 位址空間](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365)。</span><span class="sxs-lookup"><span data-stu-id="70069-106">[Configure your on-premises environment to trust Microsoft 365 or Office 365 and enable shared SIP address space](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365).</span></span>
- <span data-ttu-id="70069-107">[在 Microsoft 365 或 Office 365 組織中啟用共用 SIP 位址空間](#enable-shared-sip-address-space-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="70069-107">[Enable shared SIP address space in your Microsoft 365 or Office 365 organization](#enable-shared-sip-address-space-in-your-organization).</span></span>

<span data-ttu-id="70069-108">請注意，如果您有 Exchange 內部部署，您可能想要在 Exchange 內部部署和商務用 Skype Online 環境之間設定 OAuth。</span><span class="sxs-lookup"><span data-stu-id="70069-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="70069-109">如需詳細資訊，請參閱[管理商務用 Skype server 中的伺服器對伺服器驗證](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications)，以及[規劃整合商務用 skype 與 Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support)。</span><span class="sxs-lookup"><span data-stu-id="70069-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a><span data-ttu-id="70069-110">將內部部署 Edge service 設定為與 Microsoft 365 或 Office 365 同盟</span><span class="sxs-lookup"><span data-stu-id="70069-110">Configure your on-premises Edge service to federate with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="70069-111">同盟可讓內部部署的使用者能夠與您組織中的 Microsoft 365 或 Office 365 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="70069-111">Federation allows users in your on-premises deployment to communicate with Microsoft 365 or Office 365 users in your organization.</span></span> <span data-ttu-id="70069-112">若要設定同盟，請在商務用 Skype Server 管理命令介面中執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="70069-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="70069-113">如果 '-EnablePartnerDiscovery ' 值設定為 $True，商務用 Skype 伺服器會使用 DNS 記錄來嘗試並探索未列在 AllowedDomains 清單中的夥伴網域。</span><span class="sxs-lookup"><span data-stu-id="70069-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="70069-114">如果此值設為 $False，商務用 Skype 伺服器只會與 AllowedDomains 清單中找到的網域同盟。</span><span class="sxs-lookup"><span data-stu-id="70069-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="70069-115">如果使用 DNS 服務路由，則需要此參數。</span><span class="sxs-lookup"><span data-stu-id="70069-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="70069-116">如需在您的內部部署商務用 Skype 部署使用者與商務用 skype Online 組織的使用者之間啟用同盟的詳細資訊，請參閱[在商務用 Skype Server 中設定商務用 Skype online 客戶的同盟支援](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support)。</span><span class="sxs-lookup"><span data-stu-id="70069-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Skype for Business Online organization, see [Configuring federation support for a Skype for Business Online customer in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a><span data-ttu-id="70069-117">設定您的內部部署環境，以啟用共用 SIP 位址空間與 Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="70069-117">Configure your on-premises environment to enable shared SIP address space with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="70069-118">您也必須設定內部部署環境，以信任 Microsoft 365 或 Office 365 並啟用共用 SIP 位址空間。</span><span class="sxs-lookup"><span data-stu-id="70069-118">You must also configure your on-premises environment to trust Microsoft 365 or Office 365 and enable shared SIP address space.</span></span> <span data-ttu-id="70069-119">這表示 Microsoft 365 或 Office 365 可能會主控使用者帳戶，使其與您的內部部署環境具有相同組 SIP 網域，而且郵件可以在內部部署和線上的使用者間路由傳送。</span><span class="sxs-lookup"><span data-stu-id="70069-119">This means Microsoft 365 or Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="70069-120">您可以使用如下所述的 ProxyFqdn = sipfed 來設定裝載提供者來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="70069-120">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="70069-121">首先，檢查您是否已有具有 ProxyFqdn = sipfed 的裝載提供者。</span><span class="sxs-lookup"><span data-stu-id="70069-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="70069-122">如果有的話，請使用下列命令將其移除：</span><span class="sxs-lookup"><span data-stu-id="70069-122">If one exists, then remove it by using the following command:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="70069-123">然後建立新的主機服務提供者，使用 New-CsHostingProvider Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="70069-123">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a><span data-ttu-id="70069-124">在您的組織中啟用共用 SIP 位址空間</span><span class="sxs-lookup"><span data-stu-id="70069-124">Enable shared SIP address space in your organization</span></span>
  
<span data-ttu-id="70069-125">除了您在內部部署中所做的變更之外，您還需要在您的內部部署環境中，進行 Microsoft 365 或 Office 365 組織中的對應變更，以啟用共用 SIP 位址空間。</span><span class="sxs-lookup"><span data-stu-id="70069-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Microsoft 365 or Office 365 organization to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="70069-126">若要在組織中啟用共用 SIP 位址空間，請使用商務用 Skype Online 建立遠端 PowerShell 會話，然後執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="70069-126">To enable shared SIP address space in your organization, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="70069-127">SharedSipAddressSpace 屬性必須保留為 "True"，直到移動至線上狀態為終稿，且沒有使用者保留內部部署。</span><span class="sxs-lookup"><span data-stu-id="70069-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="70069-128">若要建立與小組或商務用 Skype Online 的遠端 PowerShell 會話，您必須先安裝適用于 Windows PowerShell 的商務用 Skype Online 連接器模組，您可以在[這裡](https://go.microsoft.com/fwlink/p/?LinkId=391911)找到。</span><span class="sxs-lookup"><span data-stu-id="70069-128">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="70069-129">安裝模組之後，您可以建立具有下列 Cmdlet 的遠端會話：</span><span class="sxs-lookup"><span data-stu-id="70069-129">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

<span data-ttu-id="70069-130">如需如何使用商務用 Skype Online 建立遠端 PowerShell 會話的詳細資訊，以及如何使用商務用 Skype Online 連接器模組，請參閱[設定您的電腦以進行 Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="70069-130">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="70069-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="70069-131">See also</span></span>

[<span data-ttu-id="70069-132">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="70069-132">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
