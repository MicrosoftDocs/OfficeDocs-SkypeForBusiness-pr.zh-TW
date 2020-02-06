---
title: 在商務用 Skype Server 中管理雙因素驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 摘要：在商務用 Skype Server 中管理雙因素驗證。
ms.openlocfilehash: 90dc286e247c0c6eeb75bb884071b85e57663278
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818715"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>在商務用 Skype Server 中管理雙因素驗證
 
**摘要：** 在商務用 Skype Server 中管理雙因素驗證。
  
雙因素驗證：要求使用者提供兩種驗證或識別形式（亦即使用者名稱/密碼組合以及權杖或憑證），提供改良的安全性。 這也稱為「您有任何問題，您知道」。 
  
使用智慧卡的一個典型的雙因素驗證範例。 智慧卡包含與使用者帳戶相關聯的憑證，而且可以對照儲存在伺服器上的使用者與憑證資訊驗證。 您可以將使用者資訊（使用者名稱和密碼）與提供的憑證進行比較，伺服器會驗證認證並驗證使用者。
  
將商務用 Skype Server 環境設定為支援雙因素驗證時，請考慮下列主題。
  
## <a name="client-support"></a>用戶端支援

Lync Server 2013 的累計更新：年 7 2013 月的電腦版用戶端和商務用 Skype 用戶端都是目前支援雙因素驗證的用戶端。
  
## <a name="topology-requirements"></a>拓撲需求

我們強烈建議客戶使用專用的商務用 Skype 伺服器（含邊緣、控制器和使用者池）來部署雙因素驗證。 若要為使用者啟用被動式驗證，必須針對其他角色和服務停用其他驗證方法，包括下列各項：
  
|**配置類型**|**服務類型**|**伺服器角色**|**要停用的驗證類型**|
|:-----|:-----|:-----|:-----|
|Web 服務  <br/> |System.webserver  <br/> |Director  <br/> |Kerberos、NTLM 和憑證  <br/> |
|Web 服務  <br/> |System.webserver  <br/> |前端  <br/> |Kerberos、NTLM 和憑證  <br/> |
|Proxy  <br/> |EdgeServer  <br/> |左邊  <br/> |Kerberos 和 NTLM  <br/> |
|Proxy  <br/> |註冊機構  <br/> |前端  <br/> |Kerberos 和 NTLM  <br/> |
   
除非在服務層級停用這些驗證類型，否則在您的部署中啟用兩個要素驗證之後，所有其他版本的用戶端將無法順利登入。
  
## <a name="skype-for-business-service-discovery"></a>商務用 Skype 服務探索

內部和/或外部用戶端所使用的 DNS 記錄，用來探索商務用 Skype 服務，應該設定為解析為無法針對雙因素驗證啟用的商務用 Skype 伺服器。 在這項設定中，沒有為雙因素驗證啟用的商務用 Skype 池中的使用者，不需要輸入 PIN 即可進行驗證，而商務用 Skype Pool 中啟用了雙因素驗證的使用者就會需要輸入其 PIN 才能進行驗證。
  
## <a name="exchange-authentication"></a>Exchange 驗證

已針對 Microsoft Exchange 部署雙因素驗證的客戶，可能會發現用戶端中的某些功能無法使用。 這是目前的設計，因為商務用 Skype 用戶端不支援依賴 Exchange 整合之功能的雙因素驗證。
  
## <a name="contacts"></a>連絡人

已設定為利用整合連絡人存放區功能的商務用 Skype 使用者，會在使用雙因素驗證登入後，發現他們的連絡人已不再提供使用。
  
您應該使用**CsUcsRollback** Cmdlet 來移除整合連絡人存放區中的現有使用者連絡人，並將其儲存在商務用 Skype 伺服器中，然後再啟用雙因素驗證。
  
## <a name="skill-search"></a>技能搜尋

在商務用 Skype 環境中設定技能搜尋功能的客戶，會發現當商務用 Skype 啟用雙因素驗證時，這項功能無法運作。 這是因為 Microsoft SharePoint 目前不支援雙因素驗證。
  
## <a name="credentials"></a>憑證

有幾個有關儲存 Skype for Business 認證的部署考慮，可能會影響設定為使用雙因素驗證的使用者。
  
### <a name="deleting-saved-credentials"></a>刪除儲存的認證

使用者應該使用商務用 Skype 用戶端中的 [**刪除我的登入資訊**] 選項，然後在嘗試使用雙因素驗證進行第一次登入時，從商務用%localappdata%\Microsoft\Office\15.0\Skype 刪除其 SIP 個人資料資料夾。
  
### <a name="disablentcredentials"></a>DisableNTCredentials

使用 Kerberos 或 NTLM 驗證方法時，系統會自動使用使用者的 Windows 認證來進行驗證。 在支援 Kerberos 和/或 NTLM 的一般商務用 Skype Server 部署中，使用者在每次登入時都不應輸入其認證。
  
如果在提示使用者輸入 PIN 前，系統不小心提示認證，可能是透過群組原則，在用戶端電腦上無意間設定**DisableNTCredentials**登錄機碼。
  
若要防止額外的認證提示，請在本機工作站上建立下列登錄專案，或使用 [商務用 Skype] 管理範本，以使用群組原則將指定之群組的所有使用者套用到其中：
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a>SavePassword

當使用者第一次登入商務用 Skype 時，系統會提示使用者儲存其密碼。 如果選取此選項，此選項可讓使用者的用戶端憑證儲存在個人憑證存放區，並將使用者的 Windows 認證儲存在本機電腦的認證管理員中。
  
當商務用 Skype 設定為支援雙因素驗證時，必須停用**SavePassword**登錄設定。 若要防止使用者儲存其密碼，請在本機工作站上變更下列登錄專案，或使用 [商務用 Skype] 管理範本，以使用群組原則將指定之群組的所有使用者套用到其中：
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a>AD FS 2.0 權杖重播

AD FS 2.0 提供稱為權杖重播偵測的功能，可讓您檢測到使用相同權杖的多個權杖要求，然後再將它丟棄。 啟用此功能時，權杖重放偵測會在 WS 同盟備用設定檔和 SAML WebSSO 設定檔中保護驗證要求的完整性，只要確認沒有多次使用相同的權杖。
  
在安全性非常重要的情況下（例如使用網亭時），應啟用此功能。 如需有關權杖重播偵測的詳細資訊，請參閱[安全規劃和部署 AD FS 2.0 的最佳做法](https://go.microsoft.com/fwlink/p/?LinkId=309215)。
  
## <a name="external-user-access"></a>外部使用者存取

在這些主題中，將 ADFS Proxy 或反向 Proxy 設定為支援商務用 Skype 的雙因素驗證。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中設定雙因素驗證](configure-two-factor.md)
  
