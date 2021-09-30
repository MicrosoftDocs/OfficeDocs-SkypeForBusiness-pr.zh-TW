---
title: 管理商務用 Skype Server 中的註冊器設定設定
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 摘要：管理商務用 Skype Server 的註冊機設定設定。
ms.openlocfilehash: 8413d7d1604a598b8c46cebe753d408d9300d823
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2021
ms.locfileid: "60015007"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a>管理商務用 Skype Server 中的註冊器設定設定
 
**摘要：** 管理商務用 Skype Server 的註冊機設定設定。
  
您可以使用註冊機構來設定 proxy 伺服器驗證方法。 您指定的驗證通訊協定會決定集區中的伺服器在用戶端上面臨的挑戰類型。 可用的通訊協定包括：
  
- **Kerberos** 這是可供用戶端使用的最強式密碼型驗證配置，但通常只適用于企業用戶端，因為它需要用戶端連線至金鑰發佈中心 (Kerberos 網域控制站) 。 此設定適用于伺服器只驗證企業用戶端的情況。
    
- **NTLM** 這是以密碼為基礎的驗證，可供在密碼上使用挑戰回應雜湊配置的用戶端使用。 這是唯一可供用戶端使用的驗證表單，但不連接到金鑰發佈中心 (Kerberos 網域控制站) （例如遠端使用者）。 如果伺服器只驗證遠端使用者，您應該選擇 [NTLM]。
    
- **憑證驗證** 當伺服器需要從 Lync Phone Edition 用戶端、公共區域電話、商務用 Skype 和 Lync Windows Store 應用程式取得憑證時，這是一種新的驗證方法。 在 Lync Phone Edition 用戶端上，使用者登入並透過提供個人識別碼 (PIN) 來成功驗證之後，商務用 Skype 伺服器便會將 SIP URI 布建到電話，並布建商務用 Skype Server 簽署憑證，或是識別 Joe (Ex： SN=joe@contoso.com ) 至電話的使用者憑證。 此憑證用來驗證註冊機構和 Web 服務。
    
> [!NOTE]
> 當伺服器同時支援遠端和企業用戶端的驗證時，建議您啟用 Kerberos 和 NTLM。 Edge Server 和內部伺服器會進行通訊，以確保只會向遠端用戶端提供 NTLM 驗證。 如果這些伺服器上只啟用 Kerberos，則無法驗證遠端使用者。 如果企業使用者也會驗證服務器，則會使用 Kerberos。 
  
如果您要使用 Lync Windows Store 應用程式用戶端，則必須啟用憑證驗證。
  
### <a name="to-create-new-registrar-configuration-settings"></a>若要建立新的註冊機配置設定

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。  
    
3. 在左導覽列中，按一下 [ **安全性** ]，然後按一下 [ **註冊**]。
    
4. 在 [**註冊機**] 頁面上，按一下 [**新增**]
    
5. 在 [ **選取服務**] 中，按一下要套用註冊器的服務，然後按一下 **[確定]**。
    
6. 在 [ **新註冊機] 設定** 中，根據用戶端的功能和您環境中的支援，選取下列其中一項或多項：
    
   - **啟用 kerberos 驗證** 讓集區中的伺服器使用 Kerberos 驗證，提出挑戰。
    
   - **啟用 ntlm 驗證** 讓集區中的伺服器使用 NTLM 時面臨挑戰。
    
   - [**啟用憑證驗證**] 以讓集區中的伺服器對用戶端發出憑證。
    
7. 按一下 **[認可]**。
    
## <a name="modify-existing-registrar-configuration-settings"></a>修改現有的註冊機配置設定

您可以使用註冊機構來設定 proxy 伺服器驗證通訊協定。 
  
> [!NOTE]
> 當伺服器同時支援遠端和企業用戶端的驗證時，建議您啟用 Kerberos 和 NTLM。 Edge Server 和內部伺服器會進行通訊，以確保只會向遠端用戶端提供 NTLM 驗證。 如果這些伺服器上只啟用 Kerberos，則無法驗證遠端使用者。 如果企業使用者也會驗證服務器，則會使用 Kerberos。 
  
請遵循下列步驟來修改現有的註冊機。 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a>若要修改現有的註冊器配置設定

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。  
    
3. 在左導覽列中，按一下 [ **安全性** ]，然後按一下 [ **註冊**]。
    
4. 在 [ **註冊機構** ] 頁面上，按一下服務，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]。
    
5. 在 [ **編輯註冊機設定**] 中，依據用戶端的功能和您環境中的支援，選取下列其中一項或多項：
    
   - **啟用 kerberos 驗證** 讓集區中的伺服器使用 Kerberos 驗證，提出挑戰。
    
   - **啟用 ntlm 驗證** 讓集區中的伺服器使用 NTLM 時面臨挑戰。
    
   - [**啟用憑證驗證**] 以讓集區中的伺服器對用戶端發出憑證。
    
6. 按一下 **[認可]**。
    
### <a name="to-delete-registrar-configuration-settings"></a>若要刪除註冊機配置設定

1. 從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。 
    
3. 在左導覽列中，按一下 [ **安全性** ]，然後按一下 [ **註冊**]。
    
4. 在 [ **註冊機** ] 頁面上的搜尋欄位中，輸入您要刪除之註冊機構的全部或部分名稱。
    
5. 在清單中，按一下您想要的註冊機構，按一下 [ **編輯**]，然後按一下 [ **刪除**]。
    
6. 按一下 [確定]。
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除註冊機設定設定

您可以使用 Windows PowerShell 和 **set-csproxyconfiguration** Cmdlet 來刪除註冊機設定設定。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端工作階段執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至商務用 Skype 伺服器的詳細資訊，請參閱 [Microsoft Lync remote PowerShell 管理](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>移除一組特定的註冊機構安全性設定

- 下列命令會移除已套用至 edge Server atl-edge-011.litwareinc.com 的註冊機安全性設定：
    
  ```PowerShell
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>若要移除所有套用至網站範圍的註冊機構安全性設定

- 下列命令會移除所有已套用至註冊機構服務的註冊機安全性設定：
    
  ```PowerShell
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>移除所有允許 NTLM 驗證的註冊機構安全性設定

- 下列命令會刪除所有的註冊器安全性設定，這些設定允許使用 NTLM 進行用戶端驗證：
    
  ```PowerShell
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

如需詳細資訊，請參閱 [Remove-set-csproxyconfiguration](/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps)。
