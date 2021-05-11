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
description: 摘要：瞭解如何設定內部部署與 Teams 之間的互通性。
ms.openlocfilehash: 2c6fda43b939a616071009be2b8d28e636036101
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305967"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="49287-103">設定商務用 Skype 混合式</span><span class="sxs-lookup"><span data-stu-id="49287-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="49287-104">若要設定商務用 Skype 混合式，您必須：</span><span class="sxs-lookup"><span data-stu-id="49287-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="49287-105">[設定內部部署 Edge service 以與 Teams](#configure-your-on-premises-edge-service-to-federate-with-teams)同盟。</span><span class="sxs-lookup"><span data-stu-id="49287-105">[Configure your on-premises Edge service to federate with Teams](#configure-your-on-premises-edge-service-to-federate-with-teams).</span></span>
- <span data-ttu-id="49287-106">[設定您的內部部署環境，以信任 Teams 並啟用共用 SIP 位址空間](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams)。</span><span class="sxs-lookup"><span data-stu-id="49287-106">[Configure your on-premises environment to trust Teams and enable shared SIP address space](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams).</span></span>
- <span data-ttu-id="49287-107">[在您的 Teams 組織中啟用共用 SIP 位址空間](#enable-shared-sip-address-space-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="49287-107">[Enable shared SIP address space in your Teams organization](#enable-shared-sip-address-space-in-your-organization).</span></span>

<span data-ttu-id="49287-108">如果您有 Exchange 內部部署，您可能想要設定 Exchange 內部部署與商務用 Skype 線上環境之間的 OAuth。</span><span class="sxs-lookup"><span data-stu-id="49287-108">If you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="49287-109">如需詳細資訊，請參閱[Manage server to server authentication in 商務用 Skype Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md)及[Plan to 整合商務用 Skype 和 Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)。</span><span class="sxs-lookup"><span data-stu-id="49287-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) and [Plan to integrate Skype for Business and Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-teams"></a><span data-ttu-id="49287-110">設定內部部署 Edge service 與 Teams 同盟</span><span class="sxs-lookup"><span data-stu-id="49287-110">Configure your on-premises Edge service to federate with Teams</span></span>

<span data-ttu-id="49287-111">同盟可讓內部部署中的使用者與 Teams 和商務用 Skype 組織中的線上使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="49287-111">Federation allows users in your on-premises deployment to communicate with Teams and Skype for Business Online  users in your organization.</span></span> <span data-ttu-id="49287-112">若要設定同盟，請在商務用 Skype Server 管理命令介面中執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="49287-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="49287-113">如果 '-EnablePartnerDiscovery ' 值設定為 $True，商務用 Skype Server 將使用 DNS 記錄來嘗試並探索未列在 AllowedDomains 清單中的夥伴網域。</span><span class="sxs-lookup"><span data-stu-id="49287-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="49287-114">如果此值設為 $False，商務用 Skype Server 只會與 AllowedDomains 清單中找到的網域同盟。</span><span class="sxs-lookup"><span data-stu-id="49287-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="49287-115">如果使用 DNS 服務路由，則需要此參數。</span><span class="sxs-lookup"><span data-stu-id="49287-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="49287-116">如需在內部部署商務用 Skype 部署的使用者與 Microsoft 365 組織的使用者之間啟用同盟的詳細資訊，請參閱[在商務用 Skype Server 中設定 Microsoft 365 客戶的同盟支援](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md)。</span><span class="sxs-lookup"><span data-stu-id="49287-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Microsoft 365 organization, see [Configuring federation support for a Microsoft 365 customer in Skype for Business Server](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams"></a><span data-ttu-id="49287-117">設定內部部署環境以使用 Teams 啟用共用 SIP 位址空間</span><span class="sxs-lookup"><span data-stu-id="49287-117">Configure your on-premises environment to enable shared SIP address space with Teams</span></span>

<span data-ttu-id="49287-118">您也必須設定內部部署環境，以信任 Teams 和啟用共用 SIP 位址空間。</span><span class="sxs-lookup"><span data-stu-id="49287-118">You must also configure your on-premises environment to trust Teams and enable shared SIP address space.</span></span> <span data-ttu-id="49287-119">此設定表示 Teams 可以將相同組 SIP 網域的使用者帳戶作為您的內部部署環境，而且可以在內部部署和線上的使用者之間路由傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="49287-119">This configuration means Teams can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span> <span data-ttu-id="49287-120">您可以如下所述，依照 ProxyFqdn = sipfed，設定裝載提供者。</span><span class="sxs-lookup"><span data-stu-id="49287-120">You configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="49287-121">首先，檢查您是否已有具有 ProxyFqdn = sipfed 的裝載提供者。</span><span class="sxs-lookup"><span data-stu-id="49287-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="49287-122">如果有的話，請在商務用 Skype Server 管理命令介面中使用下列命令將其移除：</span><span class="sxs-lookup"><span data-stu-id="49287-122">If one exists, then remove it by using the following command in the Skype for Business Server Management Shell:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="49287-123">然後使用 New-CsHostingProvider Cmdlet 建立新的主控提供者，如下所示：</span><span class="sxs-lookup"><span data-stu-id="49287-123">Then create a new hosting provider by using the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a><span data-ttu-id="49287-124">在您的組織中啟用共用 SIP 位址空間</span><span class="sxs-lookup"><span data-stu-id="49287-124">Enable shared SIP address space in your organization</span></span>
  
<span data-ttu-id="49287-125">除了您在內部部署中所做的變更之外，您還需要在您的 Teams 組織中進行對應的變更，以啟用內部部署的共用 SIP 位址空間。</span><span class="sxs-lookup"><span data-stu-id="49287-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Teams organization to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="49287-126">若要在組織中啟用共用 SIP 位址空間，請使用 Teams 建立遠端 PowerShell 會話，然後執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="49287-126">To enable shared SIP address space in your organization, establish a remote PowerShell session with Teams, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="49287-127">SharedSipAddressSpace 屬性必須保留為 "True"，直到移動至線上狀態為終稿，且沒有使用者保留內部部署。</span><span class="sxs-lookup"><span data-stu-id="49287-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="49287-128">若要使用 Teams (或商務用 Skype 線上) 建立遠端 PowerShell 會話，您必須先安裝[Teams PowerShell 模組](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="49287-128">To establish a remote PowerShell session with Teams (or Skype for Business Online), you first need to install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span> <span data-ttu-id="49287-129">Teams PowerShell 模組會取代已撤銷的 Busines Online 連接器模組 Skype。</span><span class="sxs-lookup"><span data-stu-id="49287-129">The Teams PowerShell module replaces the Skype for Busines Online Connector module, which has been retired.</span></span>
  
<span data-ttu-id="49287-130">安裝模組之後，您可以建立具有下列 Cmdlet 的遠端會話：</span><span class="sxs-lookup"><span data-stu-id="49287-130">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

<span data-ttu-id="49287-131">如需如何使用 Teams 建立遠端 PowerShell 會話的詳細資訊，以及如何使用 Teams PowerShell 模組，請參閱[設定您的電腦以進行 Windows PowerShell](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="49287-131">For more information about how to establish a remote PowerShell session with Teams, and how to use the Teams PowerShell module, see [Set up your computer for Windows PowerShell](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="49287-132">請參閱</span><span class="sxs-lookup"><span data-stu-id="49287-132">See also</span></span>

[<span data-ttu-id="49287-133">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="49287-133">New-CsHostingProvider</span></span>](/powershell/module/skype/new-cshostingprovider?view=skype-ps)
