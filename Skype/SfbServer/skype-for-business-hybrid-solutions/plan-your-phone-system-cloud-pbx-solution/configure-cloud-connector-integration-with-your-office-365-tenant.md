---
title: 設定雲端連接器與您的 Office 365 租使用者整合
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: 瞭解如何設定雲端連接器與您的 Office 365 租使用者整合。
ms.openlocfilehash: 1742fbadec95eb72e46fb6cc46f006e1baeaf8f1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190873"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a>設定雲端連接器與您的 Office 365 租使用者整合
 
瞭解如何設定雲端連接器與您的 Office 365 租使用者整合。
  
在商務用 Skype 雲端連接器版本安裝完成後, 請執行本節中的步驟來設定您的部署, 並將其連線至您的 Office 365 租使用者。
  
## <a name="configure-firewall-settings"></a>設定防火牆設定

針對您的周邊網路設定您的內部和外部防火牆設定的防火牆設定, 以開啟 [[商務用 Skype 雲端連接器版本規劃](plan-skype-for-business-cloud-connector-edition.md)中的[埠和通訊協定](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)] 中所述的必要端口。
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>設定公用交換電話網絡 (PSTN) 閘道

在每個 PSTN 閘道設定 trunks, 以指向所有裝置的中繼伺服器。 因為對於池中的所有伺服器而言, 池 FQDN 都是相同的, 所以每個幹線都應該指向一個中繼伺服器 FQDN 或 IP 位址, 而不是中繼伺服器池 FQDN。 Trunks 應設定為相同的優先順序。
  
如果您使用的是在中繼伺服器和閘道之間的 TLS, 您必須設定閘道和中繼伺服器來支援 MTLS, 如下所示:
  
1. 從雲端連接器 Active Directory 電腦匯出根 CA。
    
2. 請依照 PSTN 閘道供應商的說明進行, 以匯入根 CA。
    
3. 匯入您在中繼伺服器上頒發給閘道之憑證的根 CA 憑證。 如果您需要取得閘道的 SSL 憑證, 您可以使用在雲端連接器 Active Directory 電腦上執行的憑證授權單位服務來執行此動作, 如下所示:
    
   - 修改現有的 Web 服務器範本, 讓經過驗證的使用者可以進行註冊, 或建立新的 Web 服務器範本來設定其他屬性, 並讓經過驗證的使用者可以進行註冊。 如需詳細指示, 請參閱[憑證範本](https://technet.microsoft.com/en-us/library/cc730705.aspx)。
    
   - 使用 [憑證] 管理單元來申請憑證, 選取您已啟用的 Web 服務器範本。 請務必在 [主題] 和 [DNS 名稱] 中的 [Subject] 和 [DNS 名稱] 中新增常見名稱, 並在 [主要選項] 底下選取 [可匯出私密金鑰] 的 [私人金鑰]。 
    
4. 使用私人金鑰匯出 SSL 憑證, 然後依照 PSTN 閘道廠商的指示匯入憑證。
    
## <a name="update-the-domain-for-your-tenant"></a>為您的租使用者更新網域

請確定您已完成 Office 365 中更新網域的步驟, 並具備新增 DNS 記錄的功能。 如需如何在 Office 365 中設定網域的詳細資訊, 請參閱[將網域新增至 office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a>在 Office 365 中新增您 Edge 的 DNS 記錄

將下列 DNS 記錄新增至您的 Office 365 租使用者。 如需如何將 DNS 記錄新增至您的 Office 365 租使用者的相關資訊, 請參閱[在 office 365 中新增或編輯自訂 DNS 記錄](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)。
  
1. 新增 Access Edge 的 DNS A 記錄。
    
2. 您可以透過 Office 365 和部署腳本來自動建立 SRV 記錄。 確認您可以在 Edge 上查詢下列兩個 SIP 服務: _sip 和 _sipfederationtls。
    
     ![已確認 SRV 記錄](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a>在雲端連接器版本與 Office 365 之間設定混合式連接

若要設定您的商務用 Skype 雲端連接器版本部署與您的 Office 365 租使用者之間的混合式連線性, 請在遠端 PowerShell 會話中執行下列 Cmdlet。 若要瞭解如何建立遠端 PowerShell 會話, 請參閱:[設定您的 Windows PowerShell 電腦](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)。
  
這個 Cmdlet 會設定存取邊緣外部 FQDN。 在第一個命令中, \<外部存取邊緣 FQDN 應該是\> SIP 存取邊緣角色的 FQDN。 根據預設, 這應該是 [ap\<. 功能變數名稱\>]。
  
```
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> 針對對等目的地使用的外部存取邊緣 FQDN 應該設定為 PSTN 網站, 只有當使用者未指派給 PSTN 網站時, 才會將它當作備用物件使用。 如需詳細資訊, 請參閱[在雲端連接器中部署單一網站](deploy-a-single-site-in-cloud-connector.md), 並[在雲端連接器中部署多個網站](deploy-multiple-sites-in-cloud-connector.md)。 
  
## <a name="set-up-pstn-gateways"></a>設定 PSTN 閘道

在每個 PSTN 閘道設定 trunks, 以指向所有裝置的中繼伺服器。 每個幹線都應該指向一個中繼伺服器 FQDN 或 IP 位址 (而非轉送轉送伺服器池 FQDN), 因為對於池中的所有伺服器而言, 該池 FQDN 都是相同的。 Trunks 應設定為相同的優先順序。
  
如果您使用的是在中繼伺服器和閘道之間的 TLS, 您必須設定閘道和中繼伺服器來支援 MTLS, 如下所示:
  
1. 從雲端連接器 Active Directory 電腦匯出根 CA。
    
2. 請依照 PSTN 閘道供應商的說明進行, 以匯入根 CA。
    
3. 匯入您在中繼伺服器上頒發給閘道之憑證的根 CA 憑證。 如果您需要取得閘道的 SSL 憑證, 您可以使用在雲端連接器 Active Directory 電腦上執行的憑證授權單位服務來執行此動作, 如下所示:
    
   - 修改現有的 Web 服務器範本, 讓經過驗證的使用者可以進行註冊, 或建立新的 Web 服務器範本來設定其他屬性, 並讓經過驗證的使用者可以進行註冊。 如需詳細指示, 請參閱[憑證範本](https://technet.microsoft.com/library/cc730705.aspx)。
    
   - 使用 [憑證] 管理單元來申請憑證, 選取您已啟用的 Web 服務器範本。 請務必在 [主題] 和 [DNS 名稱] 中的 [Subject] 和 [DNS 名稱] 中新增常見名稱, 並在 [主要選項] 底下選取 [可匯出私密金鑰] 的 [私人金鑰]。 
    
4. 使用私人金鑰匯出 SSL 憑證, 然後依照 PSTN 閘道廠商的指示匯入憑證。
    
5. 一個 PSTN 網站中的 PSTN 閘道應該只會連接到相同網站中的中繼伺服器。
    
## <a name="set-up-your-users-in-office-365"></a>在 Office 365 中設定您的使用者

登入 Office 365 系統管理入口網站, 新增將可供線上語音服務使用的使用者, 並在 Office 365 附加元件中將 E5 授權或電話系統指派給這些使用者的 E3 授權。 如需新增使用者的相關資訊, 請參閱[將使用者新增至商務用 Office 365](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)。
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a>在 Office 365 語音及語音信箱服務中啟用手機系統使用者

將使用者新增至 Office 365 之後, 在 Office 365 語音服務 (包括語音信箱) 中啟用其電話系統帳戶。 若要啟用這些功能, 您必須使用 Office 365 全域系統管理員角色的帳戶登入 Office 365 租使用者, 並且能夠執行遠端 PowerShell。 若要瞭解如何建立遠端 PowerShell 會話, 請參閱:[設定您的 Windows PowerShell 電腦](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)
  
- 將原則指派給您的使用者, 並設定使用者的商務語音電話號碼, 並以身分**識別**參數的值來指定:
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > 您也可以透過其 SIP 位址、使用者主體名稱 (UPN)、功能變數名稱與使用者名稱 ([Bob]), 以及 Active Directory 中的顯示名稱來指定使用者的身分識別 (「Bob 凱利」)。 
  
然後, 您可以使用下列腳本確認已新增並啟用使用者:
  
```
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

您必須決定您的使用者是否可以進行國際通話。 根據預設, 國際通話是啟用的。 您可以使用線上商務用 Skype 系統管理中心來停用或啟用使用者的國際撥號。
  
若要針對每位使用者停用國際通話, 請在商務用 Skype Online PowerShell 中執行下列 Cmdlet:
  
```
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

若要在已停用每個使用者的情況下, 針對每個使用者重新啟用國際通話, 請執行相同的 Cmdlet, 但將**PolicyName**的值變更為*InternationalCallsAllowed* 。
  
## <a name="assign-users-to-pstn-sites"></a>將使用者指派至 PSTN 網站

即使您只部署單一網站, 也可以使用租使用者遠端 PowerShell 將網站指派給使用者。 若要瞭解如何建立遠端 PowerShell 會話, 請參閱:[設定您的 Windows PowerShell 電腦](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)。
  
```
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> 如果沒有 PSTN 網站指派給使用者, 您的商務用 Skype 雲端連接器版本部署與您的 Office 365 租使用者之間的混合式連接, 就會回到使用租使用者層級預設值 (對等目的地), 以便完成通話。 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>設定線上混合式轉送轉送伺服器設定
<a name="BKMK_ConfigureMediationServer"> </a>

當 P2P 通話升級至 PSTN 會議時, 商務用 Skype Online 會議服務器會將邀請傳送給雲端連接器中繼伺服器。 若要確保 Office 365 能成功地路由此邀請, 您需要針對每個雲端連接器中繼伺服器設定線上租使用者的設定, 如下所示: 
  
1. 在 Office 365 系統管理入口網站中建立使用者。 使用任何您想要的使用者名稱, 例如 "MediationServer1"。
    
    使用雲端連接器的預設 SIP 網域 (.ini 檔案中的第一個 SIP 網域) 作為使用者網域。
    
    請注意, 只有在使用者傳播到商務用 Skype online 目錄時, 才需要授權指派。 將 Office 365 授權 (例如 E5) 指派給您所建立的帳戶, 最多允許一個小時來傳播變更, 確認使用者帳戶已透過執行下列 Cmdlet 正確地提供給商務用 Skype online 目錄, 然後移除此帳戶的授權。
    ```
   Gets-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. 使用您的全域或使用者管理員認證啟動租使用者 Azure AD 遠端 PowerShell 會話, 然後執行下列 Cmdlet, 將步驟1中設定的 Azure AD 使用者帳戶設定為「HybridMediationServer」:

   ```
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. 使用您的商務用 Skype 租使用者管理員認證啟動租使用者商務用 Skype 遠端 PowerShell 會話, 然後執行下列 Cmdlet, 將轉送伺服器和 Edge 伺服器 FQDN 設定為該使用者帳戶, 取代\<DisplayName\>使用您在步驟1中建立之帳戶的使用者顯示名稱:
    
   ```
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    針對 [身分識別], 請使用您為此中繼伺服器建立的 Office 365 使用者帳戶的顯示名稱。
    
    若是*MediationServerFQDN* , 請使用針對您的中繼伺服器定義的內部 FQDN。
    
    若是*EdgeServerExternalFQDN* , 請使用針對 Edge 伺服器訪問 Proxy 定義的外部 FQDN。 如果有多個雲端連接器 PSTN 網站, 請選擇指派給中繼伺服器所在之網站的邊緣伺服器訪問 Proxy FQDN。
    
4. 如果有多個雲端連接器中繼伺服器 (多個網站、HA), 請針對每個伺服器重複上述步驟。
    

