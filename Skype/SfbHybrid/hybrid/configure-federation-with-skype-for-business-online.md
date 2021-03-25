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
ms.openlocfilehash: e2af514ef1a10d652abae7bdd39a923dc52e1c4a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118942"
---
# <a name="configure-skype-for-business-hybrid"></a>設定商務用 Skype 混合式

若要設定商務用 Skype 混合式，您必須：

- [將內部部署 Edge Service 設定為與 Microsoft 365 或 Office 365](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365)同盟。
- [設定您的內部部署環境，以信任 Microsoft 365 或 Office 365 並啟用共用 SIP 位址空間](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365)。
- [在 Microsoft 365 或 Office 365 組織中啟用共用 SIP 位址空間](#enable-shared-sip-address-space-in-your-organization)。

請注意，如果您有 Exchange 內部部署，您可能想要在 Exchange 內部部署和商務用 Skype Online 環境之間設定 OAuth。 如需詳細資訊，請參閱  [管理商務用 Skype server 中的伺服器對伺服器驗證](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) ，以及 [規劃整合商務用 skype 與 Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)。 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a>將內部部署 Edge service 設定為與 Microsoft 365 或 Office 365 同盟

同盟可讓內部部署的使用者能夠與您組織中的 Microsoft 365 或 Office 365 使用者通訊。 若要設定同盟，請在商務用 Skype Server 管理命令介面中執行下列 Cmdlet：
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

如果 '-EnablePartnerDiscovery ' 值設定為 $True，商務用 Skype 伺服器會使用 DNS 記錄來嘗試並探索未列在 AllowedDomains 清單中的夥伴網域。 如果此值設為 $False，商務用 Skype 伺服器只會與 AllowedDomains 清單中找到的網域同盟。 如果使用 DNS 服務路由，則需要此參數。

> [!NOTE]
> 如需在您的內部部署商務用 Skype 部署使用者與商務用 skype Online 組織的使用者之間啟用同盟的詳細資訊，請參閱 [在商務用 Skype Server 中設定商務用 Skype online 客戶的同盟支援](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md)。


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a>設定您的內部部署環境，以啟用共用 SIP 位址空間與 Microsoft 365 或 Office 365

您也必須設定內部部署環境，以信任 Microsoft 365 或 Office 365 並啟用共用 SIP 位址空間。 這表示 Microsoft 365 或 Office 365 可能會主控使用者帳戶，使其與您的內部部署環境具有相同組 SIP 網域，而且郵件可以在內部部署和線上的使用者間路由傳送。  您可以使用如下所述的 ProxyFqdn = sipfed 來設定裝載提供者來執行此動作。

首先，檢查您是否已有具有 ProxyFqdn = sipfed 的裝載提供者。 如果有的話，請使用下列命令將其移除：

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

然後建立新的主機服務提供者，使用 New-CsHostingProvider Cmdlet，如下所示： 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>在您的組織中啟用共用 SIP 位址空間
  
除了您在內部部署中所做的變更之外，您還需要在您的內部部署環境中，進行 Microsoft 365 或 Office 365 組織中的對應變更，以啟用共用 SIP 位址空間。  

若要在組織中啟用共用 SIP 位址空間，請使用商務用 Skype Online 建立遠端 PowerShell 會話，然後執行下列 Cmdlet：
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> SharedSipAddressSpace 屬性必須保留為 "True"，直到移動至線上狀態為終稿，且沒有使用者保留內部部署。 
  
若要建立與小組或商務用 Skype Online 的遠端 PowerShell 會話，您必須先將 [團隊安裝 PowerShell 模組](/microsoftteams/teams-powershell-install)。
  
安裝模組之後，您可以建立具有下列 Cmdlet 的遠端會話：
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

如需如何使用商務用 Skype Online 建立遠端 PowerShell 會話的詳細資訊，以及如何使用商務用 Skype Online 連接器模組，請參閱 [設定您的電腦以進行 Windows PowerShell](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
  


## <a name="see-also"></a>另請參閱

[New-CsHostingProvider](/powershell/module/skype/new-cshostingprovider?view=skype-ps)