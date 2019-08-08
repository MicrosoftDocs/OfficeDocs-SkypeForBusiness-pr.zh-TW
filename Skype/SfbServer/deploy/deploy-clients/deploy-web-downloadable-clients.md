---
title: 在商務用 Skype Server 中部署網頁下載用戶端
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: '摘要: 在商務用 Skype 中部署商務用 Skype Web App 和 Skype 會議應用程式。'
ms.openlocfilehash: 8f2449fde2f270834bda50602fe163829f3b725f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234391"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>在商務用 Skype Server 中部署網頁下載用戶端

**摘要:** 部署適用于商務用 Skype Server 的商務用 Skype 2015 Web App 和 Skype 會議應用程式。

商務用 skype Web App 是已安裝在執行商務用 Skype Server 的伺服器上的網際網路資訊服務 (IIS) web 用戶端, 而且預設會依需求部署至尚未擁有商務用 Skype 用戶端的會議使用者。 這些會議使用者的頻率通常是無法從您的網路外部連線。 每當使用者按一下會議 URL, 但沒有安裝商務用 Skype 用戶端時, 系統會顯示使用最新版本的商務用 Skype Web App、Skype 會議應用程式或 Mac 版商務用 Skype 來加入會議的選項。

商務用 Skype Web App 中的 [語音]、[影片] 和 [共用] 功能需要由使用者瀏覽器用來做為外掛程式的 Microsoft ActiveX 控制項。 您可以在出現提示時, 事先安裝 ActiveX 控制項或允許使用者安裝, 這會在第一次使用商務用 Skype Web App 時, 或第一次存取需要 ActiveX 控制項的功能時進行安裝。

> [!NOTE]
> 在商務用 Skype Server Edge 伺服器部署中, 商務用 Skype Web App 用戶端存取需要在周邊網路中使用 HTTPS 反向 proxy。 您也必須發佈簡單的 Url。 如需詳細資訊, 請參閱針對[商務用 Skype Server 中的簡單 Url](../../plan-your-deployment/network-requirements/simple-urls.md)[設定反向 Proxy 伺服器](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx)與 DNS 需求。

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>針對商務用 Skype Web App 啟用多重要素驗證
<a name="MFA"> </a>

商務用 skype Web App、Skype 會議應用程式, 以及 Mac 版商務用 Skype 支援多重要素驗證。 除了使用者名稱和密碼之外, 您還可以要求其他驗證方法 (例如智慧卡或 Pin), 以驗證在登入商務用 Skype 會議時, 從外部網路加入的使用者。 您可以透過部署 Active Directory Federation Services (AD FS) 同盟伺服器並啟用商務用 Skype Server 中的被動式驗證, 來啟用多重要素驗證。 在設定 AD FS 之後, 嘗試加入商務用 Skype 會議的外部使用者會有一個 AD FS 多重要素驗證網頁, 其中包含使用者名稱和密碼質詢, 以及您所使用的任何其他驗證方法已設定。

> [!IMPORTANT]
> 如果您打算針對多重要素驗證設定 AD FS, 請務必考慮下列事項:

- 如果會議參與者和召集人都在同一個組織中, 或都來自 AD FS 同盟組織, 則多重要素 ADFS 驗證就會運作。 因為 Lync server web 基礎結構目前不支援 Lync 聯盟使用者, 所以多重要素 ADFS 驗證無法運作。

- 如果您使用硬體負載平衡器, 請在負載平衡器上啟用 cookie 暫留, 以便從商務用 Skype Web App 或會議 App 用戶端的所有要求都是由同一個前端伺服器來處理。

- 當您在商務用 Skype Server 和 AD FS 伺服器之間建立信賴方信任時, 請指派一個足夠長的權杖有效期, 有效期能超過商務用 Skype 會議的最大長度。 通常, 240 分鐘的標記生活就足夠了。

- 此設定不會套用至 Lync mobile 用戶端。

### <a name="configure-multi-factor-authentication"></a>設定多重要素驗證

1. 安裝 AD FS 同盟伺服器角色。 如需詳細資訊, 請參閱[Active Directory Federation Services 2.0 部署指南](https://go.microsoft.com/fwlink/p/?linkid=267511)

2. 建立適用于 AD FS 的憑證。 如需詳細資訊, 請參閱和部署 AD FS 之方案的[[同盟伺服器憑證]](https://go.microsoft.com/fwlink/p/?LinkId=285376)區段, 以便與單一登入主題搭配使用。

3. 從 Windows PowerShell 命令列介面, 執行下列命令:

    ```
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. 執行下列命令以建立合作關係:

    ```
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. 設定下列信賴方規則:

    ```
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>停用 BranchCache
<a name="MFA"> </a>

Windows 7 和 Windows Server 2008 R2 中的 BranchCache 功能可能會干擾商務用 Skype Web App 網頁元件。 若要防止商務用 Skype Web App 使用者的問題, 請確定未啟用 BranchCache。

如需有關停用 BranchCache 的詳細資訊, 請參閱[BranchCache 部署指南](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)。

## <a name="verifying-skype-for-business-web-app-deployment"></a>驗證商務用 Skype Web App 部署
<a name="MFA"> </a>

您可以使用 CsUcwaConference Cmdlet 來確認一組測試使用者可以使用整合通訊 Web API (UCWA) 參與會議。 如需此 Cmdlet 的詳細資訊, 請參閱商務用 Skype Server Management Shell 檔中的[測試 CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) 。

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Windows Server 2008 R2 上的外掛程式安裝疑難排解
<a name="MFA"> </a>

如果您在執行 Windows Server 2008 R2 的電腦上安裝外掛程式失敗, 您可能需要修改 Internet Explorer 安全性設定或 DisableMSI 登錄機碼設定。

### <a name="modify-the-security-setting-in-internet-explorer"></a>修改 Internet Explorer 中的安全性設定

1. 開啟 Internet Explorer。

2. 按一下 [**工具**], 按一下 [**網際網路選項**], 然後按一下 [**高級**]。

3. 向下滾動至 [**安全性**] 區段。

4. 清除 [**不要將加密的網頁存到磁片**], 然後按一下 **[確定]**。

    > [!NOTE]
    > 如果選取此選項, 當您嘗試從商務用 Skype Web App 下載附件時, 此設定也會導致錯誤。

5. 重新加入會議。 外掛程式應該會下載, 不會發生錯誤。

### <a name="modify-the-disablemsi-registry-setting"></a>修改 DisableMSI 註冊表設定

1. 按一下 [**開始**], 然後按一下 [**執行**]。

2. 若要存取 [登錄編輯程式], 請輸入**regedit**。

3. 流覽至 HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer。

4. 編輯或新增類型 REG_DWORD 的 DisableMSI 登錄機碼, 並將它設為0。

5. 重新加入會議。

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>[啟用 Skype 會議] App 以取代商務用 Skype Web App (選用、商務用 Skype Server 2015)
<a name="SMA_Enable"> </a>

這個程式是選用的, 且適用于商務用 Skype Server 2015 CU5 及更新版本。 如果您不使用它, 外部使用者將會繼續使用商務用 Skype Web App 加入會議。

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>啟用簡化的會議加入與 Skype 會議應用程式

1. 當您啟用內容傳遞網路 (CDN) 的存取權時, 使用者將能夠連線至 CDN 線上並取得 Skype 會議應用程式 (在 Windows 上) 和商務用 Skype for Mac (Mac), 並將使用簡化的會議加入體驗。

   ```
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. [允許用戶端從會議加入網頁] 或 [Skype 會議] App 傳送至 Microsoft server (預設為 false)。

   ```
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    傳送給 Microsoft 的資訊與[商務用 Skype 資料收集做法](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices)嚴格相容。

3. 如果沒有提供 CDN, 請先設定超時, 然後再回到本機託管的商務用 Skype Web App 體驗。 預設值是6秒。 如果此值設定為 0, 就不會有超時。

   ```
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

## <a name="see-also"></a>另請參閱
<a name="SMA_Enable"> </a>

[規劃會議用戶端 (Web App 與會議應用程式)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[在商務用 Skype Server 中設定會議加入頁面](../../manage/conferencing/meeting-join-page.md)

[Microsoft Online 服務隱私權聲明](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)

[授權條款與檔](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
