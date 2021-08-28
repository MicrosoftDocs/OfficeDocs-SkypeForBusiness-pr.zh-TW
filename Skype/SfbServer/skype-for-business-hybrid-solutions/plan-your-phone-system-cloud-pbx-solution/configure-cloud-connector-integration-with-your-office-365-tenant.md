---
title: 設定與 Microsoft 365 或 Office 365 組織的雲端連接器整合
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: 瞭解如何設定 Cloud Connector 整合與您的 Microsoft 365 或 Office 365 組織。
ms.openlocfilehash: 5e6cf8033a4207b79ff2f7d0915849b19eec2b65
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628525"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a>設定與 Microsoft 365 或 Office 365 組織的雲端連接器整合

> [!Important] 
> 雲端連接器 Edition 會在2021年7月31日和商務用 Skype 線上時終止。 當您的組織升級至 Teams 後，請瞭解如何使用[直接路由](/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話網絡連線至 Teams。

瞭解如何設定 Cloud Connector 整合與您的 Microsoft 365 或 Office 365 組織。
  
商務用 Skype Cloud Connector Edition 安裝完成後，請執行本節中的步驟來設定您的部署，並將其連線至您的 Microsoft 365 或 Office 365 組織。
  
## <a name="configure-firewall-settings"></a>設定防火牆設定

為周邊網路設定內部和外部防火牆設定的防火牆設定，以開啟[計畫商務用 Skype Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)的[埠和通訊協定](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)中所述的必要端口。
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>設定公用交換電話網路 (PSTN) 閘道

在每個 PSTN 閘道上設定主幹，以指向所有裝置的轉送伺服器。 因為集區中所有伺服器的集區 FQDN 都是相同的，所以每個主幹應該指向一個轉送伺服器 FQDN 或 IP 位址，而非轉送伺服器集區 FQDN。 主幹應以相同的優先順序加以設定。
  
如果您使用的是轉送伺服器和閘道之間的 TLS，您必須將閘道和轉送伺服器設定為支援 MTLS，如下所示：
  
1. 從雲端連接器 Active Directory 電腦匯出根 CA。
    
2. 依照 PSTN 閘道廠商的指示，匯入根 CA。
    
3. 在轉送伺服器上，匯入發給您閘道之憑證的根 CA 憑證。 如果您需要取得閘道的 SSL 憑證，您可以使用雲端連接器 Active Directory 電腦上所執行的憑證授權單位服務，如下所示：
    
   - 修改現有的 Web 服務器範本，讓已驗證的使用者能夠註冊，或是建立新的網頁伺服器範本以設定其他屬性，並讓已驗證的使用者能夠進行註冊。 如需詳細指示，請參閱 [憑證範本](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11))。
    
   - 使用憑證嵌入式管理單元要求憑證選取您已啟用的 Web 服務器範本。 請務必在 [替代名稱] 中，使用「閘道的 FQDN」來新增 Subject 和 DNS 名稱中的 [一般名稱]，然後在 [主要選項] 下，確認已選取 [可匯出私密金鑰] 的私密金鑰。 
    
4. 使用私密金鑰匯出 SSL 憑證，並遵循您的 PSTN 閘道廠商的指示，以匯入憑證。
    
## <a name="update-the-domain-for-your-tenant"></a>更新租使用者的網域

請確定您已完成 Microsoft 365 或 Office 365 中的網域更新的步驟，且具有新增 DNS 記錄的能力。 如需如何在 Microsoft 365 或 Office 365 中設定網域的詳細資訊，請參閱[Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。
  
## <a name="add-dns-records-for-your-edge"></a>新增您 Edge 的 DNS 記錄

將下列 DNS 記錄新增至您的 Microsoft 365 或 Office 365 組織。 如需如何新增 DNS 記錄的相關資訊，請參閱[在 Microsoft 365 或 Office 365 中新增或編輯自訂 DNS 記錄](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)。
  
1. 新增 Access Edge 的 DNS A 記錄。
    
2. SRV 記錄會由 Microsoft 365 或 Office 365 和部署腳本自動建立。 請確認您可以在 Edge： sip 和 sipfederationtls 查看下列兩種 SIP 服務 \_ \_ 。
    
     ![SRV 記錄確認](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a>設定 Cloud Connector Edition 和 Microsoft 365 或 Office 365 之間的混合式連線

若要設定商務用 Skype Cloud Connector Edition 部署與 Microsoft 365 或 Office 365 組織之間的混合式連線，請在遠端 PowerShell 會話中執行下列 Cmdlet。 若要瞭解如何建立遠端 PowerShell 會話，請參閱：[設定您的電腦以進行 Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
  
Cmdlet 會設定 Access Edge 的外部 FQDN。 在第一個命令中， \<External Access Edge FQDN\> 應該是 SIP Access Edge role 的一個。 根據預設，這應該是 \<Domain Name\> ap。
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> 用於對等目的地的外部存取 Edge FQDN 應該設定為 PSTN 網站，只有當使用者未被指派給 PSTN 網站時，才會將其當作回退使用。 如需詳細資訊，請參閱 [deploy a site In Cloud connector](deploy-a-single-site-in-cloud-connector.md) 和 [Deploy in cloud connector 中的多個網站](deploy-multiple-sites-in-cloud-connector.md)。 
  
## <a name="set-up-pstn-gateways"></a>設定 PSTN 閘道

在每個 PSTN 閘道上設定主幹，以指向所有裝置的轉送伺服器。 每個主幹應該指向一個轉送伺服器 FQDN 或 IP 位址，而非轉送伺服器集區 FQDN，因為集區中所有伺服器的集區 FQDN 都相同。 主幹應以相同的優先順序加以設定。
  
如果您使用的是轉送伺服器和閘道之間的 TLS，您必須將閘道和轉送伺服器設定為支援 MTLS，如下所示：
  
1. 從雲端連接器 Active Directory 電腦匯出根 CA。
    
2. 依照 PSTN 閘道廠商的指示，匯入根 CA。
    
3. 在轉送伺服器上，匯入發給您閘道之憑證的根 CA 憑證。 如果您需要取得閘道的 SSL 憑證，您可以使用雲端連接器 Active Directory 電腦上所執行的憑證授權單位服務，如下所示：
    
   - 修改現有的 Web 服務器範本，讓已驗證的使用者能夠註冊，或是建立新的網頁伺服器範本以設定其他屬性，並讓已驗證的使用者能夠進行註冊。 如需詳細指示，請參閱 [憑證範本](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11))。
    
   - 使用憑證嵌入式管理單元要求憑證選取您已啟用的 Web 服務器範本。 請務必在 [替代名稱] 中，使用「閘道的 FQDN」來新增 Subject 和 DNS 名稱中的 [一般名稱]，然後在 [主要選項] 下，確認已選取 [可匯出私密金鑰] 的私密金鑰。 
    
4. 使用私密金鑰匯出 SSL 憑證，並遵循您的 PSTN 閘道廠商的指示，以匯入憑證。
    
5. PSTN 閘道 (s) 在一個 PSTN 網站中應該只會連線至同一個網站中 (s) 的轉送伺服器。
    
## <a name="set-up-your-users"></a>設定使用者

登入 Microsoft 365 系統管理中心，新增將為線上語音服務啟用的使用者，並指派 E5 授權或電話系統附加至這些使用者的 E3 授權。 如需新增使用者的詳細資訊，請參閱[將使用者新增至商務 Microsoft 365](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)。
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a>為使用者啟用電話系統語音及語音信箱服務
 
將使用者新增至 Microsoft 365 或 Office 365 後，請為電話系統語音服務（包括語音信箱）啟用其帳戶。 若要啟用這些功能，您必須以全域系統管理員角色的帳戶登入 Microsoft 365 或 Office 365 組織，且能夠執行遠端 PowerShell。 若要瞭解如何建立遠端 PowerShell 會話，請參閱：[設定您的電腦以進行 Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
- 將原則指派給您的使用者，並設定使用者的商務語音電話號碼，並以 **Identity** 參數的值來指定：
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > 使用者身分識別可以使用使用者的 SIP 位址、使用者主體名稱 (UPN) 或使用者的 Active Directory 顯示名稱來指定 (例如，「小明凱利」 ) 。 星號 (\*) 字元也可以與使用者身分識別的顯示名稱搭配使用。 例如，身分識別 " \* smith" 會傳回顯示名稱結尾為字串值 "Smith" 的所有使用者。
  
然後，您可以使用下列腳本確認使用者已新增及啟用：
  
```powershell
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

您必須決定您的使用者是否應該能夠撥打國際電話。 依預設，會啟用國際通話。 您可以使用線上商務用 Skype 系統管理中心，停用或啟用使用者進行國際撥號的功能。
  
若要以每位使用者為基礎停用國際電話，請在商務用 Skype Online 中執行下列 Cmdlet PowerShell:
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

若要在每一使用者停用時以每個使用者為基礎重新啟用國際電話，請執行相同的 Cmdlet，但將 **PolicyName** 的值變更為 *InternationalCallsAllowed*  。
  
## <a name="assign-users-to-pstn-sites"></a>將使用者指派至 PSTN 網站

使用租使用者遠端 PowerShell 將網站指派給使用者，即使您只部署了單一網站也是一樣。 若要瞭解如何建立遠端 PowerShell 會話，請參閱：[設定您的電腦以進行 Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> 如果沒有 PSTN 網站指派給使用者，您的商務用 Skype Cloud Connector Edition 部署與 Microsoft 365 或 Office 365 組織之間的混合式連線將會回退，以使用租使用者層級的預設一個 (對等目的地) ，這樣通話才能完成。 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>設定線上混合轉送伺服器設定
<a name="BKMK_ConfigureMediationServer"> </a>

當 P2P 呼叫呈報給 PSTN 會議時，商務用 Skype 線上會議服務器會將邀請傳送至雲端連接器轉送伺服器。 為了確保 Microsoft 365 或 Office 365 能夠成功路由傳送此邀請，您必須為每個雲端連接器轉送伺服器設定線上承租人中的設定，如下所示： 
  
1. 在 Microsoft 365 系統管理中心中建立使用者。 使用任何您想要的使用者名稱，例如 "MediationServer1"。
    
    使用雲端連接器的預設 SIP 網域 (.ini 檔案中的第一個 SIP 網域) 為使用者網域。
    
    請注意，使用者必須將授權指派傳播至商務用 Skype 線上目錄。 將 Microsoft 365 或 Office 365 授權 (（如 E5) ）指派至您建立的帳戶，允許最多一個小時來傳播變更，請執行下列 Cmdlet，以確認使用者帳戶已正確布建至商務用 Skype 的 online 目錄，請執行下列 Cmdlet，然後從此帳戶中移除授權。
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. 使用您的全域或使用者系統管理員認證來啟動租 Azure AD remote PowerShell 會話，然後執行下列 Cmdlet，將步驟1中設定之 Azure AD 使用者帳戶的部門設定為 "HybridMediationServer"：

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. 使用您的商務用 Skype 租使用者系統管理員認證來啟動租使用者商務用 Skype remote PowerShell 會話，然後執行下列 Cmdlet，將轉送伺服器和 Edge Server FQDN 設定為該使用者帳戶，並以 \<DisplayName\> 您在步驟1中建立之帳戶的使用者顯示名稱取代：
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    針對 [身分識別]，使用您為此轉送伺服器建立的使用者帳戶顯示名稱。
    
    針對  *MediationServerFQDN*  ，使用為您的轉送伺服器定義的內部 FQDN。
    
    針對  *EdgeServerExternalFQDN*  ，使用為 Edge Server Access Proxy 定義的外部 FQDN。 如果有多個雲端連接器 PSTN 網站，請選擇指派給轉送伺服器所在之網站的 Edge Server Access Proxy FQDN。
    
4. 如果有多個 Cloud Connector 轉送伺服器 (多個網站的 HA) ，請對每個伺服器重複上述步驟。
