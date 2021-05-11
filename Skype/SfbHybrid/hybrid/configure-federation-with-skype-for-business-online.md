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
# <a name="configure-skype-for-business-hybrid"></a>設定商務用 Skype 混合式

若要設定商務用 Skype 混合式，您必須：

- [設定內部部署 Edge service 以與 Teams](#configure-your-on-premises-edge-service-to-federate-with-teams)同盟。
- [設定您的內部部署環境，以信任 Teams 並啟用共用 SIP 位址空間](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams)。
- [在您的 Teams 組織中啟用共用 SIP 位址空間](#enable-shared-sip-address-space-in-your-organization)。

如果您有 Exchange 內部部署，您可能想要設定 Exchange 內部部署與商務用 Skype 線上環境之間的 OAuth。 如需詳細資訊，請參閱[Manage server to server authentication in 商務用 Skype Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md)及[Plan to 整合商務用 Skype 和 Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)。 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-teams"></a>設定內部部署 Edge service 與 Teams 同盟

同盟可讓內部部署中的使用者與 Teams 和商務用 Skype 組織中的線上使用者進行通訊。 若要設定同盟，請在商務用 Skype Server 管理命令介面中執行下列 Cmdlet：
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

如果 '-EnablePartnerDiscovery ' 值設定為 $True，商務用 Skype Server 將使用 DNS 記錄來嘗試並探索未列在 AllowedDomains 清單中的夥伴網域。 如果此值設為 $False，商務用 Skype Server 只會與 AllowedDomains 清單中找到的網域同盟。 如果使用 DNS 服務路由，則需要此參數。

> [!NOTE]
> 如需在內部部署商務用 Skype 部署的使用者與 Microsoft 365 組織的使用者之間啟用同盟的詳細資訊，請參閱[在商務用 Skype Server 中設定 Microsoft 365 客戶的同盟支援](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md)。


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams"></a>設定內部部署環境以使用 Teams 啟用共用 SIP 位址空間

您也必須設定內部部署環境，以信任 Teams 和啟用共用 SIP 位址空間。 此設定表示 Teams 可以將相同組 SIP 網域的使用者帳戶作為您的內部部署環境，而且可以在內部部署和線上的使用者之間路由傳送郵件。 您可以如下所述，依照 ProxyFqdn = sipfed，設定裝載提供者。

首先，檢查您是否已有具有 ProxyFqdn = sipfed 的裝載提供者。 如果有的話，請在商務用 Skype Server 管理命令介面中使用下列命令將其移除：

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

然後使用 New-CsHostingProvider Cmdlet 建立新的主控提供者，如下所示： 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>在您的組織中啟用共用 SIP 位址空間
  
除了您在內部部署中所做的變更之外，您還需要在您的 Teams 組織中進行對應的變更，以啟用內部部署的共用 SIP 位址空間。  

若要在組織中啟用共用 SIP 位址空間，請使用 Teams 建立遠端 PowerShell 會話，然後執行下列 Cmdlet：
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> SharedSipAddressSpace 屬性必須保留為 "True"，直到移動至線上狀態為終稿，且沒有使用者保留內部部署。 
  
若要使用 Teams (或商務用 Skype 線上) 建立遠端 PowerShell 會話，您必須先安裝[Teams PowerShell 模組](/microsoftteams/teams-powershell-install)。 Teams PowerShell 模組會取代已撤銷的 Busines Online 連接器模組 Skype。
  
安裝模組之後，您可以建立具有下列 Cmdlet 的遠端會話：
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

如需如何使用 Teams 建立遠端 PowerShell 會話的詳細資訊，以及如何使用 Teams PowerShell 模組，請參閱[設定您的電腦以進行 Windows PowerShell](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
  


## <a name="see-also"></a>請參閱

[New-CsHostingProvider](/powershell/module/skype/new-cshostingprovider?view=skype-ps)
