---
title: 在商務用 Skype Server 中管理雙因素驗證
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 摘要：在商務用 Skype Server 中管理雙因素驗證。
---

# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>在商務用 Skype Server 中管理雙因素驗證
 
**總結：** 在商務用 Skype Server 中管理雙因素驗證。
  
雙因素驗證可要求使用者提供兩種形式的驗證或身分識別，亦即使用者名稱/密碼組合和 token 或憑證，以提升安全性。 這也稱為「您所掌握的專案」，您知道的是什麼。」 
  
具有憑證之雙因素驗證的典型範例是使用智慧卡。 智慧卡包含與使用者帳戶相關聯的憑證，而且可針對伺服器上儲存的使用者和憑證資訊驗證。 透過比較使用者資訊 (使用者名稱和密碼) 所提供的憑證，伺服器就會驗證認證，並驗證使用者。
  
設定商務用 Skype Server 環境以支援雙因素驗證時，請考慮下列主題。
  
## <a name="client-support"></a>用戶端支援

Lync Server 2013 的累計更新：7月2013的桌面用戶端和商務用 Skype 用戶端是唯一目前支援雙因素驗證的用戶端。
  
## <a name="topology-requirements"></a>拓撲需求

客戶鼓勵使用具有 Edge、Director 和使用者集區的專屬商務用 Skype Server，部署兩要素驗證。 若要為使用者啟用被動驗證，其他角色和服務必須停用其他驗證方法，包括下列各項：
  
|**配置類型**|**服務類型**|**伺服器角色**|**要停用的驗證類型**|
|:-----|:-----|:-----|:-----|
|Web 服務  <br/> |WebServer  <br/> |Director  <br/> |Kerberos、NTLM 和憑證  <br/> |
|Web 服務  <br/> |WebServer  <br/> |前端  <br/> |Kerberos、NTLM 和憑證  <br/> |
|代理  <br/> |Edgeserver atl-edge  <br/> |銳利  <br/> |Kerberos 和 NTLM  <br/> |
|代理  <br/> |處長  <br/> |前端  <br/> |Kerberos 和 NTLM  <br/> |
   
除非在服務層級停用這些驗證類型，否則在您的部署中啟用兩個要素驗證之後，所有其他版本的用戶端將無法順利登入。
  
## <a name="skype-for-business-service-discovery"></a>商務用 Skype 服務探索

內部和/或外部用戶端所使用的 DNS 記錄若要探索商務用 Skype 服務，應設定為解析成未啟用雙因素驗證的商務用 Skype 伺服器。 在此設定中，未啟用雙因素驗證的商務用 Skype 集區中的使用者不需要輸入 pin 碼以進行驗證，而啟用雙因素驗證的商務用 Skype 集區中的使用者則必須輸入其 pin 碼以進行驗證。
  
## <a name="exchange-authentication"></a>Exchange 驗證

已部署 Microsoft Exchange 的雙因素驗證的客戶可能會發現用戶端中的某些功能無法使用。 這種行為是設計所設計，因為商務用 Skype 用戶端不支援依存于 Exchange 整合的功能的兩個要素驗證。
  
## <a name="contacts"></a>Contacts

設定為使用整合連絡人存放區功能的商務用 Skype 使用者，會發現使用雙因素驗證來登入後，使用者的連絡人已不再可用。
  
您應該使用 **Invoke-CsUcsRollback** 指令程式，從整合連絡人存放區中移除現有的使用者連絡人，並將其儲存在商務用 Skype Server 中，再啟用雙因素驗證。
  
## <a name="skill-search"></a>技能搜尋

在商務用 Skype 環境中已設定技能搜尋功能的客戶，將會發現，當商務用 Skype 啟用雙因素驗證時，此功能無法運作。 這是設計，因為 Microsoft SharePoint 目前不支援雙因素驗證。
  
## <a name="credentials"></a>Credentials

有許多有關儲存商務用 Skype 認證的部署考慮，可能會影響設定為使用雙因素驗證的使用者。
  
### <a name="deleting-saved-credentials"></a>刪除儲存的認證

使用者必須先使用商務用 Skype 用戶端中的 [**刪除我的登入資訊**] 選項，並從%localappdata%\Microsoft\ Office \ 15.0 \ 商務用 Skype 中刪除其 SIP 設定檔資料夾，再嘗試使用雙因素驗證進行第一次簽署。
  
### <a name="disablentcredentials"></a>DisableNTCredentials

使用 Kerberos 或 NTLM 驗證方法時，會自動使用使用者的 Windows 憑證進行驗證。 在啟用 Kerberos 和/或 NTLM 以進行驗證的一般商務用 Skype Server 部署中，使用者在每次登入時都不應輸入其認證。
  
如果在提示使用者輸入 PIN 碼之前，無意提示使用者輸入其 PIN 碼，則可能會在用戶端電腦上無意間設定 **DisableNTCredentials** 登錄機碼（可能是透過「群組原則」）。
  
若要防止其他提示輸入認證，請在本機工作站上建立下列登錄專案，或使用商務用 Skype 系統管理範本，套用至使用群組原則的指定集區的所有使用者：
  
HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
REG_DWORD： DisableNTCredentials

值：0x0
  
### <a name="savepassword"></a>SavePassword

當使用者第一次登入商務用 Skype 時，系統會提示使用者儲存其密碼。 如果選取此選項，則會允許將使用者的用戶端憑證儲存在個人憑證存放區中，而將使用者的 Windows 認證儲存在本機電腦的認證管理員中。
  
當商務用 Skype 設定為支援雙因素驗證時，應停用 **SavePassword** 登錄設定。 若要防止使用者儲存其密碼，請變更本機工作站上的下列登錄專案，或使用商務用 Skype 系統管理範本，以套用至使用群組原則的指定集區的所有使用者：
  
HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
REG_DWORD： SavePassword
  
值：0x0
  
## <a name="ad-fs-20-token-replay"></a>AD FS 2.0 權杖重新播放

AD FS 2.0 提供的功能稱為「權杖重新顯示偵測」，可以偵測出使用相同權杖的多個權杖要求，然後再將其丟棄。 啟用此功能時，權杖重新顯示偵測會在 WS-Federation 被動式設定檔和 SAML WebSSO 設定檔中保護驗證要求的完整性，請確定永遠不會使用相同的權杖。
  
在安全性非常重要的情況下，例如使用亭時，應啟用此功能。 如需權杖重新顯示偵測的相關資訊，請參閱 [安全規劃及部署 AD FS 2.0 的最佳作法](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ff630160(v=ws.10))。
  
## <a name="guest-user-access"></a>來賓使用者存取

在下列主題中，設定 ADFS proxy 或反向 Proxy，以支援來自外部網路的商務用 Skype 雙因素驗證。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中設定雙因素驗證](configure-two-factor.md)
