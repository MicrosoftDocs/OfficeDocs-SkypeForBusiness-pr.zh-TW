---
title: 在商務用 Skype Server 中設定雙因素驗證
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
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 摘要：在商務用 Skype Server 中設定雙因素驗證。
ms.openlocfilehash: 447039a5dd137482c330325fcf479dade583f395
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014367"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>在商務用 Skype Server 中設定雙因素驗證

**摘要：** 設定商務用 Skype Server 中的兩個要素驗證。

下列各節說明為您的部署設定雙因素驗證所需的步驟。 如需有關雙因素驗證的詳細資訊，請參閱[啟用線上系統管理員格線使用者文章的 Office 365 多重要素驗證](https://go.microsoft.com/fwlink/p/?LinkId=313332)。

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>設定 Enterprise 的根憑證授權以支援智慧卡驗證

下列步驟說明如何設定 Enterprise 的根 CA，以支援智慧卡驗證：

如需如何安裝 Enterprise 根 CA 的詳細資訊，請參閱[install a Enterprise Root 核證機關](/previous-versions/windows/it-pro/windows-server-2003/cc776709(v=ws.10))。

1. 使用網域管理員帳戶登入 Enterprise CA 電腦。

2. 啟動系統管理員，並確認已安裝 [憑證授權單位網站] 註冊角色。

3. 在 [系統 **管理工具** ] 功能表中，開啟 [ **憑證授權單位** 管理主控台]。

4. 在功能窗格中，展開 [ **憑證授權單位** 單位]。

5. 以滑鼠右鍵按一下 [ **憑證範本**]，選取 [ **新增**]，然後選取 [ **要發出的憑證範本**]。

6. 選取 [ **註冊代理程式**、 **智慧卡使用者** 及 **智慧卡登** 入]。

7. 按一下 [確定]。

8. 以滑鼠右鍵按一下 [ **憑證範本**]。

9. 選取 [ **管理**]。

10. 開啟智慧卡使用者範本的屬性。

11. 按一下 [ **安全性** ] 索引標籤。

12. 變更許可權，如下所示：

    - 使用讀取/註冊，新增個別使用者的 AD 帳戶。 (允許) 許可權，或

    - 使用讀取/註冊，新增包含智慧卡使用者的安全性群組。 (允許) 許可權，或

    - 新增具有讀取/註冊的網域使用者群組 (允許) 許可權

## <a name="configure-windows-8-for-virtual-smart-cards"></a>設定虛擬智慧卡的 Windows 8

部署雙因素驗證和智慧卡技術時，要考慮的一個因素是實施成本。 Windows 8 提供許多新的安全性功能，而且其中一個最有意思的新功能是支援虛擬智慧卡。

針對配備受信任平臺模組的電腦 (符合規格版本1.2 的 TPM) 晶片，組織現在可以取得智慧卡登入的優勢，而不需要在硬體上進行任何額外的投資。 如需詳細資訊，請參閱搭配[Windows 8 使用虛擬智慧卡](https://go.microsoft.com/fwlink/p/?LinkId=313365)。

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>設定虛擬智慧卡的 Windows 8

1. 使用具備商務用 Skype 功能之使用者的認證登入 Windows 8 電腦。

2. 在 [Windows 8 開始] 畫面上，將游標移至螢幕的右下角。

3. 選取 [ **搜尋** ] 選項，然後搜尋 forCommand Prompt。

4. 在 **命令提示** 字元上按一下滑鼠右鍵，然後選取 [ **以系統管理員身分執行**]。

5. 執行下列命令，以 (TPM) 管理主控台開啟受信任的平臺模組：

   ```console
   Tpm.msc
   ```

6. 在 [TPM 管理主控台] 中，確認您的 TPM 規格版本至少是1。2

    > [!NOTE]
    > 如果您收到的對話方塊指出無法找到相容的信任平臺模組 (TPM) ，請確認該電腦具有相容的 TPM 模組，且已在系統 BIOS 中啟用。

7. 關閉 TPM 管理主控台

8. 在命令提示字元處，使用下列命令建立新的虛擬智慧卡：

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

   > [!NOTE]
   > 若要在建立虛擬智慧卡時提供自訂 PIN 碼值，請改用/pin prompt。

9. 在命令提示字元中執行下列命令，以開啟 [電腦管理] 主控台：

  ```console
  CompMgmt.msc
  ```

10. 在 [電腦管理] 主控台中，選取 [ **裝置管理**]。

11. 展開 [ **智慧卡讀取器**]。

12. 確認已成功建立新的虛擬智慧卡讀取器。

## <a name="enroll-users-for-smart-card-authentication"></a>註冊使用者的智慧卡驗證

有兩種方法可供您登記智慧卡驗證的使用者。 較簡單的方法是讓使用者直接註冊使用 web 註冊的智慧卡驗證，而更複雜的方法則是使用註冊代理程式。 本主題著重于智慧卡憑證的自我註冊。

如需以登錄代理程式名義註冊使用者的詳細資訊，請參閱 [代表其他使用者註冊憑證](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770802(v=ws.11))。

### <a name="to-enroll-users-for-smart-card-authentication"></a>註冊使用者的智慧卡驗證

1. 使用具備商務用 Skype 功能之使用者的認證登入 Windows 8 工作站。

2. 啟動 Internet Explorer。

3. 流覽至 [ **憑證授權單位 Web 登記** ] 頁面 (https://MyCA.contoso.com/certsrv) 例如，

    > [!NOTE]
    > 如果您使用 Internet Explorer 10，您可能需要在相容性模式中查看此網站。

4. 在 [ **歡迎** ] 頁面上，選取 [ **要求憑證**]。

5. 接下來，選取 [ **高級要求**]。

6. 選取 [ **建立並提交此 CA 的要求**]。

7. 在 [**憑證範本**] 區段中選取 [**智慧卡使用者**]，並以下列值完成「高級憑證要求」：

  - **主要選項** 確認他的下列設定：

    - 選取 [ **建立新的按鍵集** ] 選項按鈕

    - 若為 **CSP**，請選取 [ **Microsoft 基本智慧卡加密提供者**]

    - 若要 **使用主要用法**，請選取 [ **Exchange** (這是唯一可用的選項) 。

    - 若為 **金鑰大小**，請輸入2048

    - 確認已選取 [ **自動機碼容器名稱** ]

    - 請不要選取其他方塊。

  - 在 [ **其他選項** ] 下，確認下列值：

    - 若為 **要求格式** ，請選取 **CMC**。

    - 若為 **雜湊演算法** ，請選取 **sha1**。

    - 適用于 **易記名稱** enterSmardcard 憑證。

8. 如果您使用的是實體智慧卡讀卡機，請將智慧卡插入裝置中。

9. 按一下 [ **提交** ] 提交憑證要求。

10. 出現提示時，請輸入用來建立虛擬智慧卡的 PIN 碼。

    > [!NOTE]
    > 預設虛擬智慧卡 PIN 碼值為 ' 12345678 '。

11. 簽發憑證後，按一下 [ **安裝此憑證** ] 以完成註冊程式。

    > [!NOTE]
    >  如果憑證要求失敗，錯誤為「此網頁瀏覽器不支援產生憑證要求」，有三種方法可以解決問題：
    >- 在 Internet Explorer 中啟用相容性檢視。
    >- 啟用 Internet Explorer 中的 [開啟內部網路設定] 選項。
    >- 選取 [Internet Explorer 選項] 功能表中 [安全性] 索引標籤底下的 [將所有區域重設為預設層級] 設定。

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>設定 Active Directory Federation Services (AD FS 2.0) 

下列章節說明如何設定 Active Directory Federation Services (AD FS 2.0) 以支援多重要素驗證。 如需如何安裝 AD FS 2.0 的詳細資訊，請參閱 [AD fs 2.0 逐步和操作方法指南](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10))。

> [!NOTE]
> 安裝 AD FS 2.0 時，請勿使用 Windows 伺服器管理員來新增 Active Directory Federation Services 角色。 相反地，請下載並安裝 [Active Directory Federation Services](/troubleshoot/windows-server/identity/availability-description-afds)。

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>設定用於雙因素驗證的 AD FS

1. 使用網域系統管理員帳戶登入 AD FS 2.0 電腦。

2. 啟動 Windows PowerShell。

3. 從 Windows PowerShell 命令列中，執行下列命令：

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. 執行下列命令，以建立與每一部要啟用被動驗證的伺服器的合作關係，以取代您的部署特有的伺服器名稱。

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. 在 [系統管理工具] 功能表中，啟動 [AD FS 2.0 管理主控台]。

6. 展開 [**信任關係**  >  **信賴** 憑證者信任]。

7. 確認已為您的商務用 Skype Server 建立新的信任。

8. 執行下列命令，為您的信賴憑證者信任建立並指派發行授權規則 Windows PowerShell：

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. 執行下列命令，使用 Windows PowerShell 建立並指派對信賴憑證者信任的發行轉換規則：

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. 在 AD FS 2.0 管理主控台中，以滑鼠右鍵按一下您的信賴憑證者信任，然後選取 [ **編輯宣告規則**]。

11. 選取 [ **發行授權規則** ] 索引標籤，並確認已成功建立新的授權規則。

12. 選取 [ **發行轉換規則** ] 索引標籤，並確認已成功建立新的轉換規則。

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>設定 AD FS 2.0 以支援用戶端驗證

有兩種可能的驗證類型可設定為允許 AD FS 2.0 支援使用智慧卡的驗證：

- 以表單為基礎的驗證 (FBA) 

- 傳輸層安全性用戶端驗證

使用以表單為基礎的驗證，您可以開發一個網頁，讓使用者可以使用其使用者名稱/密碼或使用智慧卡和 PIN 碼進行驗證。 本主題著重于如何使用 AD FS 2.0 來執行傳輸層安全性用戶端驗證。 如需 AD FS 2.0 驗證類型的相關資訊，請參閱 [AD fs 2.0：如何變更本機驗證類型](https://go.microsoft.com/fwlink/p/?LinkId=313384)。

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>設定 AD FS 2.0 以支援用戶端驗證

1. 使用網域系統管理員帳戶登入 AD FS 2.0 電腦。

2. 啟動 Windows Explorer。

3. 流覽至 C:\inetpub\adfs\ls

4. 請備份現有的 web.config 檔。

5. 使用記事本開啟現有的 web.config 檔案。

6. 從功能表列中，選取 [ **編輯** ]，然後選取 [ **尋找**]。

7. 搜尋 \<localAuthenticationTypes\> 。

    請注意，列出了四種驗證類型，每行一個。

8. 將包含 TLSClient 驗證類型的行移至區段中清單的頂端。

9. 儲存並關閉 web.config 檔案。

10. 以較高的許可權啟動命令提示字元。

11. 執行下列命令以重新啟動 IIS：

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>設定商務用 Skype Server 被動式驗證

下列章節說明如何設定商務用 Skype Server 以支援被動式驗證。 啟用兩個要素驗證之後，將需要使用實體或虛擬智慧卡和有效 PIN 碼來登入使用商務用 Skype 用戶端的使用者。

> [!NOTE]
> 強烈建議客戶在服務層級為註冊機構和 Web 服務啟用被動式驗證。 如果已為全域層級的註冊機構和 Web 服務啟用被動式驗證，則對於不是以支援的桌面用戶端登入的使用者而言，這可能會導致組織範圍的驗證失敗。

### <a name="web-service-configuration"></a>Web 服務設定

下列步驟說明如何針對 director、Enterprise 集區和將為被動驗證啟用 Standard Edition 伺服器建立自訂 web 服務設定。

### <a name="to-create-a-custom-web-service-configuration"></a>建立自訂 web 服務設定

1. 使用商務用 Skype 系統管理員帳戶登入您的商務用 Skype Server 前端伺服器。

2. 啟動商務用 Skype Server 管理命令介面。

3. 從商務用 Skype Server 管理命令介面命令列，為每個 Director、Enterprise 集區和 Standard Edition 伺服器建立新的 Web 服務設定，並執行下列命令來啟用被動驗證：

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

   > [!CAUTION]
   > WsFedPassiveMetadataUri FQDN 的值為 AD FS 2.0 伺服器的同盟服務名稱。 您可以在 AD FS 2.0 管理主控台中，以滑鼠右鍵按一下功能窗格中的 [ **服務** ]，然後選取 [ **編輯同盟服務屬性**]，即可找到 [同盟服務名稱] 值。

4. 執行下列命令，確認 UseWsFedPassiveAuth 和 WsFedPassiveMetadataUri 值已正確設定：

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. 若為用戶端，被動式驗證是 webticket 驗證的最低偏好驗證方法。 針對將啟用被動驗證的所有 director、Enterprise 集區和 Standard Edition 伺服器，所有其他驗證類型都必須透過執行下列 Cmdlet 商務用 Skype Web 服務中停用：

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. 執行下列 Cmdlet，確認已成功停用所有其他驗證類型：

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>Proxy 設定

當您為商務用 Skype Web 服務停用憑證驗證時，商務用 Skype 用戶端將使用較不習慣的驗證類型（例如 Kerberos 或 NTLM）來驗證註冊器服務。 仍然需要使用憑證驗證，讓用戶端可以找回 webticket，但必須停用註冊器服務的 Kerberos 和 NTLM。

下列步驟說明如何為 Edge 集區、Enterprise 集區，以及將為被動驗證啟用 Standard Edition 伺服器建立自訂 proxy 設定。

### <a name="to-create-a-custom-proxy-configuration"></a>建立自訂 proxy 設定

1. 從商務用 Skype Server 管理命令介面命令列，為每個商務用 Skype Server Edge 集區、Enterprise 集區和 Standard Edition 伺服器建立新的 proxy 設定，以執行下列命令來啟用被動驗證：

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. 執行下列命令，確認已成功停用所有其他 proxy 驗證類型：

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中管理雙因素驗證](two-factor-authentication.md)

[搭配商務用 Skype 用戶端和商務用 Skype Server 使用雙因素驗證](use-two-factor.md)
