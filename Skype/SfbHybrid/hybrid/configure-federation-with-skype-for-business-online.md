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
ms.openlocfilehash: ccf140b62cdbad11605c99fe1cb0cc66aa1ee4dd
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780102"
---
# <a name="configure-skype-for-business-hybrid"></a>設定商務用 Skype 混合式

若要設定商務用 Skype 混合式，您必須：

- [設定您的內部部署 Edge service，以與 Office 365 或其他組織](#configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization)同盟。
- [設定您的內部部署環境，以信任 office 365 並啟用共用 SIP 位址空間與 office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365)。
- [在您的 Office 365 組織中啟用共用 SIP 位址空間](#enable-shared-sip-address-space-in-your-office-365-organization)。

請注意，如果您有 Exchange 內部部署，您可能想要在 Exchange 內部部署和商務用 Skype Online 環境之間設定 OAuth。 如需詳細資訊，請參閱[管理商務用 Skype server 中的伺服器對伺服器驗證](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications)，以及[規劃整合商務用 skype 與 Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support)。 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization"></a>設定內部部署 Edge service 以與 Office 365 或其他組織同盟

同盟可讓內部部署的使用者能夠與您組織中的 Microsoft 365 或 Office 365 使用者通訊。 若要設定同盟，請在商務用 Skype Server 管理命令介面中執行下列 Cmdlet：
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

如果 '-EnablePartnerDiscovery ' 值設定為 $True，商務用 Skype 伺服器會使用 DNS 記錄來嘗試並探索未列在 AllowedDomains 清單中的夥伴網域。 如果此值設為 $False，商務用 Skype 伺服器只會與 AllowedDomains 清單中找到的網域同盟。 如果使用 DNS 服務路由，則需要此參數。

> [!NOTE]
> 如需在您的內部部署商務用 Skype 部署使用者與商務用 skype Online 組織的使用者之間啟用同盟的詳細資訊，請參閱[在商務用 Skype Server 中設定商務用 Skype online 客戶的同盟支援](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support)。


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a>設定您的內部部署環境以啟用共用 SIP 位址空間與 Office 365

您也必須將內部部署環境設定為信任 Office 365，並啟用與 Office 365 共用 SIP 位址空間。 這表示 Office 365 可能會主控使用者帳戶與您的內部部署環境相同的 SIP 網域集，而且郵件可以在內部部署和線上的使用者間路由傳送。  您可以使用如下所述的 ProxyFqdn = sipfed 來設定裝載提供者來執行此動作。

首先，檢查您是否已有具有 ProxyFqdn = sipfed 的裝載提供者。 如果有的話，請使用下列命令將其移除：

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

然後建立新的主機服務提供者，使用 New-CsHostingProvider Cmdlet，如下所示： 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-organization"></a>在您的 Office 365 組織中啟用共用 SIP 位址空間
  
除了您在內部部署中所做的變更之外，您還需要在 Office 365 組織中進行對應的變更，以啟用內部部署的共用 SIP 位址空間。  

若要在 Office 365 組織中啟用共用 SIP 位址空間，請使用商務用 Skype Online 建立遠端 PowerShell 會話，然後執行下列 Cmdlet：
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> SharedSipAddressSpace 屬性必須保留為 "True"，直到移動至線上狀態為終稿，且沒有使用者保留內部部署。 
  
若要建立與小組或商務用 Skype Online 的遠端 PowerShell 會話，您必須先安裝適用于 Windows PowerShell 的商務用 Skype Online 連接器模組，您可以在[這裡](https://go.microsoft.com/fwlink/p/?LinkId=391911)找到。
  
安裝模組之後，您可以建立具有下列 Cmdlet 的遠端會話：
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

如需如何使用商務用 Skype Online 建立遠端 PowerShell 會話的詳細資訊，以及如何使用商務用 Skype Online 連接器模組，請參閱[設定您的電腦以進行 Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。
  


## <a name="see-also"></a>請參閱

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
