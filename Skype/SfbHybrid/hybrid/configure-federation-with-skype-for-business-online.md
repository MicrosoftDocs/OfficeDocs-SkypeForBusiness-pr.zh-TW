---
title: 設定商務用 Skype 混合式
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
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
description: '摘要: 瞭解如何設定內部部署和商務用 Skype Online 之間的互通性。'
ms.openlocfilehash: 59f5f752e7a6d9fa4047e736f1a988819525955e
ms.sourcegitcommit: 1336f6c182043016c42660d5f21632d82febb658
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/31/2019
ms.locfileid: "36185524"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="36fe1-103">設定商務用 Skype 混合式</span><span class="sxs-lookup"><span data-stu-id="36fe1-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="36fe1-104">若要設定商務用 Skype 混合式, 您需要:</span><span class="sxs-lookup"><span data-stu-id="36fe1-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="36fe1-105">[設定您的內部部署環境服務以與 Office 365 聯盟](#configure-your-on-premises-edge-service-to-federate-with-office-365)。</span><span class="sxs-lookup"><span data-stu-id="36fe1-105">[Configure your on-premises environment service to federate with Office 365](#configure-your-on-premises-edge-service-to-federate-with-office-365).</span></span>
- <span data-ttu-id="36fe1-106">[將內部部署環境設定為信任 office 365, 並啟用 office 365 共用的 SIP 位址空間](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365)。</span><span class="sxs-lookup"><span data-stu-id="36fe1-106">[Configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).</span></span>
- <span data-ttu-id="36fe1-107">[在您的 Office 365 租使用者中啟用共用的 SIP 位址空間](#enable-shared-sip-address-space-in-your-office-365-tenant)。</span><span class="sxs-lookup"><span data-stu-id="36fe1-107">[Enable shared SIP address space in your Office 365 tenant](#enable-shared-sip-address-space-in-your-office-365-tenant).</span></span>

<span data-ttu-id="36fe1-108">請注意, 如果您有 Exchange 內部部署, 您可能會想要在 Exchange 內部部署和商務用 Skype Online 環境之間設定 OAuth。</span><span class="sxs-lookup"><span data-stu-id="36fe1-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="36fe1-109">如需詳細資訊, 請參閱[在商務用 Skype server 中管理伺服器對伺服器驗證](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications), 並[規劃整合商務用 skype 與 Exchange](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support)。</span><span class="sxs-lookup"><span data-stu-id="36fe1-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365"></a><span data-ttu-id="36fe1-110">設定您的內部部署邊緣服務以與 Office 365 聯盟</span><span class="sxs-lookup"><span data-stu-id="36fe1-110">Configure your on-premises Edge service to federate with Office 365</span></span>

<span data-ttu-id="36fe1-111">同盟可讓您內部部署中的使用者與貴組織中的 Office 365 使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="36fe1-111">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="36fe1-112">若要設定同盟, 請在商務用 Skype Server Management Shell 中執行下列 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="36fe1-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

<span data-ttu-id="36fe1-113">如果 [-EnablePartnerDiscovery] 的值設為 1, 商務用 Skype 伺服器將使用 DNS 記錄來嘗試並探索未列在 AllowedDomains 清單中的夥伴網域。</span><span class="sxs-lookup"><span data-stu-id="36fe1-113">If '-EnablePartnerDiscovery' value set to 1, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="36fe1-114">如果該值設定為 0, 商務用 Skype 伺服器將只會與 AllowedDomains 清單中的網域聯盟。</span><span class="sxs-lookup"><span data-stu-id="36fe1-114">If the value set to 0, Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="36fe1-115">如果使用 DNS 服務路由，則需要此參數。</span><span class="sxs-lookup"><span data-stu-id="36fe1-115">This parameter is required if you use DNS service routing.</span></span>



## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a><span data-ttu-id="36fe1-116">設定您的內部部署環境, 以使用 Office 365 啟用共用的 SIP 位址空間</span><span class="sxs-lookup"><span data-stu-id="36fe1-116">Configure your on-premises environment to enable shared SIP address space with Office 365</span></span>

<span data-ttu-id="36fe1-117">您也必須將內部部署環境設定為信任 Office 365, 並啟用 Office 365 共用的 SIP 位址空間。</span><span class="sxs-lookup"><span data-stu-id="36fe1-117">You must also configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365.</span></span> <span data-ttu-id="36fe1-118">這表示 Office 365 可能會將使用者帳戶與您的內部部署環境放在同一組 SIP 網域中, 而且可以在內部部署和線上的使用者之間路由訊息。</span><span class="sxs-lookup"><span data-stu-id="36fe1-118">This means Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="36fe1-119">您可以使用 ProxyFqdn = sipfed (如下所述) 來設定託管提供者來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="36fe1-119">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="36fe1-120">首先, 請檢查您是否已有擁有 ProxyFqdn = sipfed 的主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="36fe1-120">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="36fe1-121">如果有的話, 請使用下列命令將其移除:</span><span class="sxs-lookup"><span data-stu-id="36fe1-121">If one exists, then remove it by using the following command:</span></span>

```
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="36fe1-122">接著, 建立新的主機服務提供者, 請使用 CsHostingProvider Cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="36fe1-122">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a><span data-ttu-id="36fe1-123">在您的 Office 365 租使用者中啟用共用的 SIP 位址空間</span><span class="sxs-lookup"><span data-stu-id="36fe1-123">Enable shared SIP address space in your Office 365 tenant</span></span>
  
<span data-ttu-id="36fe1-124">除了您在內部部署部署中所做的變更之外, 您還需要在您的 Office 365 租使用者中進行對應的變更, 以啟用共用的 SIP 位址空間與您的內部部署。</span><span class="sxs-lookup"><span data-stu-id="36fe1-124">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Office 365 tenant to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="36fe1-125">若要在您的 Office 365 租使用者中啟用共用的 SIP 位址空間, 請使用商務用 Skype Online 建立遠端 PowerShell 會話, 然後執行下列 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="36fe1-125">To enable shared SIP address space in your Office 365 tenant, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="36fe1-126">SharedSipAddressSpace 屬性必須保留為「True」, 直到將其移至 [線上] 為最終狀態, 且沒有使用者保留內部部署。</span><span class="sxs-lookup"><span data-stu-id="36fe1-126">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="36fe1-127">若要建立與團隊或商務用 Skype Online 的遠端 PowerShell 會話, 您必須先安裝適用于 Windows PowerShell 的商務用 Skype Online 連接器模組, 您可以在[這裡](https://go.microsoft.com/fwlink/p/?LinkId=391911)找到。</span><span class="sxs-lookup"><span data-stu-id="36fe1-127">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="36fe1-128">安裝模組後, 您可以使用下列 Cmdlet 建立遠端會話:</span><span class="sxs-lookup"><span data-stu-id="36fe1-128">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

<span data-ttu-id="36fe1-129">如需有關如何使用商務用 Skype Online 建立遠端 PowerShell 會話, 以及如何使用商務用 Skype Online 連接器模組的詳細資訊, 請參閱[設定您的 Windows PowerShell 電腦](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="36fe1-129">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="36fe1-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="36fe1-130">See also</span></span>

[<span data-ttu-id="36fe1-131">新-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="36fe1-131">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

