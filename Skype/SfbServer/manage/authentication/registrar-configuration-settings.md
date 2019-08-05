---
title: 在商務用 Skype Server 中管理註冊機構配置設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: '摘要: 管理商務用 Skype Server 的註冊機構配置設定。'
ms.openlocfilehash: 4ad7815da0744a78cd72208ef390362bff26c2ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191863"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中管理註冊機構配置設定
 
**摘要:** 管理商務用 Skype Server 的註冊機構配置設定。
  
您可以使用註冊機構來設定 proxy 伺服器驗證方法。 您指定的驗證通訊協定決定了將池中的伺服器問題到用戶端所面臨的挑戰類型。 可用的通訊協定包括:
  
- **Kerberos**這是用戶端可用的最強式密碼驗證配置, 但通常只有企業用戶端才能使用, 因為它需要用戶端連線到金鑰發佈中心 (Kerberos 網網域控制站)。 此設定適用于伺服器只驗證企業用戶端的情況。
    
- **NTLM**這是在密碼上使用質詢回應雜湊配置的用戶端所能使用的密碼驗證。 這是不需連線到金鑰發佈中心 (Kerberos 網網域控制站) (例如遠端使用者) 的用戶端可使用的唯一驗證形式。 如果伺服器只驗證遠端使用者, 您應該選擇 [NTLM]。
    
- **憑證驗證**當伺服器需要從 Lync Phone Edition 用戶端、常用的區域電話、商務用 Skype 和 Lync Windows Store 應用程式取得憑證時, 這是新的驗證方法。 在 Lync Phone Edition 用戶端上, 使用者登入並透過提供個人識別碼 (PIN) 來成功驗證之後, 商務用 Skype 伺服器接著將 SIP URI 提供給手機, 並供應商務用 Skype 伺服器已簽署身分識別 Joe (Ex: SN=joe@contoso.com) 至手機的憑證或使用者認證。 這個憑證是用來向註冊機構和 Web 服務進行驗證。
    
> [!NOTE]
> 我們建議您在伺服器同時支援遠端與企業用戶端的驗證時, 同時啟用 Kerberos 和 NTLM。 邊緣伺服器與內部伺服器通訊, 以確保只提供 NTLM 驗證給遠端用戶端。 如果在這些伺服器上只啟用 Kerberos, 就無法驗證遠端使用者。 如果企業使用者也要針對伺服器進行驗證, 則會使用 Kerberos。 
  
如果您要使用 Lync Windows Store app 用戶端, 您必須啟用憑證驗證。
  
### <a name="to-create-new-registrar-configuration-settings"></a>建立新的註冊機構配置設定

1.  從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權利), 或指派給 CsServerAdministrator 或 CsAdministrator 角色, 登入您在其中部署商務用 Skype Server 的網路中的任何電腦.
    
2. 開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。  
    
3. 在左側導覽列中, 按一下 [**安全性**], 然後按一下 [**註冊機**]。
    
4. 在 [**註冊機**] 頁面上, 按一下 [**新增**]
    
5. 在 [**選取服務**] 中, 按一下要套用註冊機構的服務, 然後按一下 **[確定]**。
    
6. 在 [**新的註冊機構設定**] 中, 根據您的環境中用戶端和支援的功能, 選取下列一或多個專案:
    
   - 使用 Kerberos 驗證來**啟用 kerberos 驗證**, 讓伺服器在池中有問題的挑戰。
    
   - **啟用 ntlm 驗證**, 以讓池中的伺服器面臨使用 NTLM 的問題。
    
   - **啟用憑證驗證**, 將池中的伺服器頒發憑證給用戶端。
    
7. 按一下 [認可]****。
    
## <a name="modify-existing-registrar-configuration-settings"></a>修改現有的註冊機構配置設定

您可以使用註冊機構來設定 proxy 伺服器驗證通訊協定。 
  
> [!NOTE]
> 我們建議您在伺服器同時支援遠端與企業用戶端的驗證時, 同時啟用 Kerberos 和 NTLM。 邊緣伺服器與內部伺服器通訊, 以確保只提供 NTLM 驗證給遠端用戶端。 如果在這些伺服器上只啟用 Kerberos, 就無法驗證遠端使用者。 如果企業使用者也要針對伺服器進行驗證, 則會使用 Kerberos。 
  
請依照這些步驟來修改現有的註冊機構。 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a>修改現有的註冊機構配置設定

1.  從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權利), 或指派給 CsServerAdministrator 或 CsAdministrator 角色, 登入您在其中部署商務用 Skype Server 的網路中的任何電腦.
    
2. 開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。  
    
3. 在左側導覽列中, 按一下 [**安全性**], 然後按一下 [**註冊機**]。
    
4. 在 [**註冊機構**] 頁面上, 按一下服務, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。
    
5. 在 [**編輯註冊機構設定**] 中, 根據您的環境中用戶端和支援的功能, 選取下列一或多項:
    
   - 使用 Kerberos 驗證來**啟用 kerberos 驗證**, 讓伺服器在池中有問題的挑戰。
    
   - **啟用 ntlm 驗證**, 以讓池中的伺服器面臨使用 NTLM 的問題。
    
   - **啟用憑證驗證**, 將池中的伺服器頒發憑證給用戶端。
    
6. 按一下 [認可]****。
    
### <a name="to-delete-registrar-configuration-settings"></a>刪除註冊機構配置設定

1. 從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權利), 或指派給 CsServerAdministrator 或 CsAdministrator 角色, 登入您在其中部署商務用 Skype Server 的網路中的任何電腦.
    
2. 開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。 
    
3. 在左側導覽列中, 按一下 [**安全性**], 然後按一下 [**註冊機**]。
    
4. 在 [**註冊機**] 頁面上, 于 [搜尋] 欄位中, 輸入您要刪除之註冊機構的全部或部分名稱。
    
5. 在清單中, 按一下您想要的註冊機構, 按一下 [**編輯**], 然後按一下 [**刪除**]。
    
6. 按一下 [確定]****。
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除註冊機構配置設定

您可以使用 Windows PowerShell 和**CsProxyConfiguration** Cmdlet 來刪除註冊機構設定設定。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料, 請參閱博客文章[: 「快速入門: 使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 在商務用 Skype 伺服器中, 程式是一樣的。
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>移除一組特定的註冊機構安全設定

- 下列命令會移除已套用至 edge Server atl-edge-011.litwareinc.com 的註冊機構安全性設定:
    
  ```
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>若要移除所有套用至網站範圍的註冊機構安全性設定

- 下列命令會移除所有已套用至註冊機構服務的註冊機構安全性設定:
    
  ```
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>若要移除所有允許 NTLM 驗證的註冊機構安全性設定

- 下列命令會刪除所有註冊機構安全性設定, 以允許使用 NTLM 進行用戶端驗證:
    
  ```
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

如需詳細資訊, 請參閱[移除-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps)。
  

