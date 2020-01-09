---
title: 在商務用 Skype Server 中設定雙因素驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: 摘要：在商務用 Skype Server 中設定雙因素驗證。
ms.openlocfilehash: 768ee9c2697523eff6922f20fd610554e32c1f7c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992330"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>在商務用 Skype Server 中設定雙因素驗證

**摘要：** 在商務用 Skype Server 中設定雙因素驗證。

下列各節說明針對您的部署設定雙因素驗證所需的步驟。 如需有關雙因素驗證的詳細資訊，請參閱[啟用 Office 365 的多重要素驗證以進行線上系統管理員-格線使用者文章](https://go.microsoft.com/fwlink/p/?LinkId=313332)。

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>設定企業根憑證授權單位以支援智慧卡驗證

下列步驟說明如何將企業根 CA 設定為支援智慧卡驗證：

如需如何安裝企業根 CA 的詳細資訊，請參閱[安裝企業根憑證授權單位](https://go.microsoft.com/fwlink/p/?LinkID=313364)。

1. 使用網域系統管理員帳戶登入企業 CA 電腦。

2. 啟動系統管理員，然後確認已安裝憑證授權單位 Web 登記角色。

3. 從 [**管理工具**] 功能表，開啟 [**認證機構**管理] 主控台。

4. 在 [功能窗格] 中，展開 [**憑證授權單位**]。

5. 以滑鼠右鍵按一下**憑證範本**，選取 [**新增**]，然後選取 [**要頒發的憑證範本**]。

6. 選取 [**註冊代理程式**、**智慧卡使用者**和**智慧卡登**入]。

7. 按一下 [確定]****。

8. 以滑鼠右鍵按一下**憑證範本**。

9. 選取 [**管理**]。

10. 開啟 [智慧卡] 使用者範本的屬性。

11. 按一下 [**安全性**] 索引標籤。

12. 變更許可權，如下所示：

    - 新增具有讀取/註冊（允許）許可權的個別使用者廣告帳戶，或

    - 新增包含具有讀取/註冊（允許）許可權的智慧卡使用者的安全性群組，或

    - 新增具有讀取/註冊（允許）許可權的 [網域使用者] 群組

## <a name="configure-windows-8-for-virtual-smart-cards"></a>針對虛擬智慧卡設定 Windows 8

部署雙因素驗證與智慧卡技術時，要考慮的一個因素是實施成本。 Windows 8 提供許多新的安全性功能，其中一個最有趣的新功能就是支援虛擬智慧卡。

對於配備符合規範版本1.2 的可信平臺模組（TPM）晶片的電腦，組織現在可以取得智慧卡登入的優點，而不需要在硬體中進行任何額外的投資。 如需詳細資訊，請參閱[在 Windows 8 中使用虛擬智慧卡](https://go.microsoft.com/fwlink/p/?LinkId=313365)。

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>針對虛擬智慧卡設定 Windows 8

1. 使用商務用 Skype 使用者的認證登入 Windows 8 電腦。

2. 在 Windows 8 的 [開始] 畫面中，將游標移至畫面的右下角。

3. 選取 [**搜尋**] 選項，然後搜尋 [forCommand 提示]。

4. 以滑鼠右鍵按一下**命令提示**字元，然後選取 [以**系統管理員身分執行**]。

5. 執行下列命令以開啟可信平臺模組（TPM）管理主控台：

  ```console
  Tpm.msc
  ```

6. 從 TPM 管理主控台，確認您的 TPM 規格版本至少為1。2

    > [!NOTE]
    > 如果您收到對話方塊，指出找不到相容的信任平臺模組（TPM），請確認電腦有相容的 TPM 模組，且已在系統 BIOS 中啟用。

7. 關閉 TPM 管理主控台

8. 在命令提示字元中，使用下列命令建立新的虛擬智慧卡：

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > 若要在建立虛擬智慧卡時提供自訂 PIN 值，請改為使用/pin 提示。

9. 在命令提示字元中，執行下列命令以開啟 [電腦管理] 主控台：

  ```console
  CompMgmt.msc
  ```

10. 在 [電腦管理] 主控台中，選取 [**裝置管理**]。

11. 展開 [**智慧卡讀取器**]。

12. 確認已成功建立新的虛擬智慧卡讀卡機。

## <a name="enroll-users-for-smart-card-authentication"></a>註冊使用者的智慧卡驗證

有兩種方法可以為使用者註冊智慧卡驗證。 更簡單的方法是讓使用者使用 web 註冊直接註冊智慧卡驗證，而更複雜的方法則涉及使用註冊代理程式。 本主題主要針對智慧卡憑證的自行註冊。

如需將使用者註冊為註冊代理程式的詳細資訊，請參閱[代表其他使用者註冊證書](https://go.microsoft.com/fwlink/p/?LinkID=313367)。

### <a name="to-enroll-users-for-smart-card-authentication"></a>註冊使用者的智慧卡驗證

1. 使用商務用 Skype 使用者的認證登入 Windows 8 工作站。

2. 啟動 Internet Explorer。

3. 流覽至 [**憑證授權單位 Web 註冊**] 頁面（ https://MyCA.contoso.com/certsrv)例如

    > [!NOTE]
    > 如果您使用的是 Internet Explorer 10，您可能需要以相容模式查看此網站。

4. 在 [**歡迎**] 頁面上，選取 [**要求憑證**]。

5. 接著，選取 [**高級要求**]。

6. 選取 [**建立並提交此 CA 的要求**]。

7. 選取 [**憑證範本**] 區段底下的 [**智慧卡使用者**]，並以下列值完成高級憑證要求：

  - [**主要選項**] 請確認他追蹤下列設定：

    - 選取 [**建立新金鑰集**] 選項按鈕

    - 針對**CSP**，請選取 [ **Microsoft 基本智慧卡加密提供者**]

    - 如需**金鑰用法**，請選取 [ **Exchange** ] （這是唯一可用的選項）。

    - 針對**金鑰大小**，請輸入2048

    - 確認已選取 [**自動金鑰容器名稱**]

    - 不要選取其他方塊。

  - 在 [**其他選項**] 底下，確認下列值：

    - 針對**要求格式**，請選取 [ **CMC**]。

    - 針對**雜湊演算法**選取 [ **sha1**]。

    - 針對**易記的名稱**enterSmardcard 憑證。

8. 如果您使用的是物理智慧卡讀取器，請將智慧卡插入裝置中。

9. 按一下 [**提交**] 以提交證書申請。

10. 出現提示時，請輸入用來建立虛擬智慧卡的 PIN。

    > [!NOTE]
    > 預設的虛擬智慧卡 PIN 值是 "12345678"。

11. 在頒發憑證之後，按一下 [**安裝此憑證**] 以完成註冊程式。

    > [!NOTE]
    >  如果您的憑證要求失敗，並出現「此網頁瀏覽器不支援產生憑證要求」錯誤，有三種可能的方法可以解決此問題：

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>設定 Active Directory Federation Services （AD FS 2.0）

下列章節說明如何設定 Active Directory 同盟服務（AD FS 2.0）以支援多重要素驗證。 如需如何安裝 AD FS 2.0 的詳細資訊，請參閱[AD fs 2.0 逐步說明和操作指南](https://go.microsoft.com/fwlink/p/?LinkId=313374)。

> [!NOTE]
> 安裝 AD FS 2.0 時，請不要使用 Windows Server Manager 來新增 Active Directory 同盟服務角色。 相反地，請下載並安裝[Active Directory Federation Services 2.0 RTW 套件](https://go.microsoft.com/fwlink/p/?LinkId=313375)。

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>針對雙因素驗證設定 AD FS

1. 使用網域系統管理員帳戶登入 AD FS 2.0 電腦。

2. 啟動 Windows PowerShell。

3. 從 [Windows PowerShell] 命令列中，執行下列命令：

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. 您可以執行下列命令，以取代您的部署所專用的伺服器名稱，建立與每個伺服器的合作關係，以進行被動式驗證：

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. 從 [管理工具] 功能表中，啟動 [AD FS 2.0 管理主控台]。

6. 展開 [**信任關聯** > 性**信賴方信任**]。

7. 確認已為您的商務用 Skype 伺服器建立新的信任。

8. 若要使用 Windows PowerShell，請執行下列命令，為您的信賴方信任建立並指派發行授權規則：

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. 若要使用 Windows PowerShell，請執行下列命令，為您的信賴方信任建立並指派發行轉換規則：

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. 從 AD FS 2.0 管理主控台，以滑鼠右鍵按一下您的信賴方信任，然後選取 [**編輯宣告規則**]。

11. 選取 [**發佈授權規則**] 索引標籤，並確認已成功建立新的授權規則。

12. 選取 [**頒發轉換規則**] 索引標籤，並確認已成功建立新的轉換規則。

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>設定 AD FS 2.0 以支援用戶端驗證

有兩種可能的驗證類型可以設定為允許 AD FS 2.0 使用智慧卡支援驗證：

- 以表單為基礎的驗證（FBA）

- 傳輸層安全性用戶端驗證

使用以表單為基礎的驗證，您可以開發網頁，讓使用者可以使用他們的使用者名稱/密碼或使用其智慧卡和 PIN 來進行驗證。 本主題重點說明如何使用 AD FS 2.0 來實現傳輸層安全性用戶端驗證。 如需有關 AD FS 2.0 驗證類型的詳細資訊，請參閱[AD fs 2.0：如何變更本機驗證類型](https://go.microsoft.com/fwlink/p/?LinkId=313384)。

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>設定 AD FS 2.0 以支援用戶端驗證

1. 使用網域系統管理員帳戶登入 AD FS 2.0 電腦。

2. 啟動 Windows 資源管理器。

3. 流覽至 C:\inetpub\adfs\ls

4. 製作現有 web.config 檔案的備份複本。

5. 使用記事本開啟現有的 web.config 檔案。

6. 從功能表列中，選取 [**編輯**]，然後選取 [**尋找**]。

7. 搜尋\<localAuthenticationTypes\>。

    請注意，列出四個驗證類型，每行一個。

8. 將包含 TLSClient 驗證類型的行移至區段中清單的頂端。

9. 儲存並關閉 web.config 檔案。

10. 以較高的許可權啟動命令提示字元。

11. 執行下列命令以重新開機 IIS：

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>設定商務用 Skype Server 被動式驗證

下列章節說明如何設定商務用 Skype Server 以支援被動式驗證。 一旦啟用，即會要求啟用雙因素驗證的使用者使用物理或虛擬智慧卡和有效的 PIN 來使用商務用 Skype 用戶端登入。

> [!NOTE]
> 強烈建議客戶針對服務層級的註冊機構和 Web 服務啟用被動式驗證。 如果針對全域層級的註冊機構和 Web 服務啟用被動式驗證，可能會導致不是以支援的桌面用戶端登入的使用者進行組織範圍的驗證失敗。

### <a name="web-service-configuration"></a>Web 服務設定

下列步驟說明如何為控制器、企業版池和標準版伺服器（將為被動驗證啟用）建立自訂的 web 服務設定。

### <a name="to-create-a-custom-web-service-configuration"></a>建立自訂的 web 服務設定

1. 使用商務用 Skype 系統管理員帳戶登入商務用 Skype Server 前端伺服器。

2. 啟動商務用 Skype Server 管理命令介面。

3. 從商務用 Skype Server Management Shell 命令列，為每個主管、企業版池及標準版伺服器建立新的 Web 服務設定，只要執行下列命令，即可啟用被動式驗證：

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > WsFedPassiveMetadataUri FQDN 的值是您的 AD FS 2.0 伺服器的識別身分同盟服務名稱。 在 AD FS 2.0 管理主控台中，您可以在 [功能窗格] 中以滑鼠右鍵按一下 [**服務**]，然後選取 [**編輯同盟服務屬性**]，找到 [同盟服務名稱] 值。

4. 執行下列命令，確認已正確設定 UseWsFedPassiveAuth 和 WsFedPassiveMetadataUri 值：

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. 針對用戶端，被動式驗證是 webticket 驗證的最不可取的驗證方法。 針對所有要啟用被動式驗證的控制器、企業版池及標準版伺服器，您必須透過執行下列 Cmdlet，在商務用 Skype Web Services 中停用所有其他驗證類型：

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. 執行下列 Cmdlet，確認所有其他驗證類型都已成功停用：

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>Proxy 設定

針對商務用 Skype Web 服務停用證書驗證時，商務用 Skype 用戶端會使用較不可取的喜好驗證類型（例如 Kerberos 或 NTLM）來驗證註冊機構服務。 您仍需要證書驗證來允許用戶端檢索 webticket，不過，必須針對註冊機構服務停用 Kerberos 和 NTLM。

下列步驟說明如何針對要啟用被動式驗證的邊緣池、企業版池及標準版伺服器建立自訂 proxy 設定。

### <a name="to-create-a-custom-proxy-configuration"></a>建立自訂 proxy 配置

1. 從商務用 Skype Server Management Shell 命令列中，為每個商務用 Skype Server Edge 池、企業版池及標準版伺服器建立新的 proxy 設定，只要執行下列動作就能啟用被動式驗證指令

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. 執行下列命令，確認所有其他 proxy 驗證類型都已順利停用：

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中管理雙因素驗證](two-factor-authentication.md)

[在商務用 Skype 用戶端和商務用 Skype Server 上使用雙因素驗證](use-two-factor.md)
