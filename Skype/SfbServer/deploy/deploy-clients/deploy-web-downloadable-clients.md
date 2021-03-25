---
title: 在商務用 Skype Server 中部署 Web 可下載的用戶端
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 摘要：部署商務用 Skype 的商務用 Skype Web App 和 Skype 會議應用程式。
ms.openlocfilehash: 20489dddb244b179908f8c8a565bb1f4d539a5a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122127"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>在商務用 Skype Server 中部署 Web 可下載的用戶端

**摘要：** 部署商務用 skype Server 所使用的商務用 Skype 2015 Web App 和 Skype 會議應用程式。

商務用 skype Web App 是安裝在執行商務用 Skype Server 之伺服器上的網際網路資訊服務 (IIS) 網頁用戶端，而且預設會根據需要將其部署到尚未擁有商務用 Skype 用戶端的會議使用者。 這兩個會議使用者的使用者頻率高於無法從您的網路外部連線。 每當使用者按一下會議 URL，但未安裝商務用 Skype 用戶端時，使用者就會看到使用最新版的商務用 Skype Web App、Skype 會議應用程式或商務用 Skype for Mac 來加入會議的選項。

商務用 Skype Web App 中的語音、影片和共用功能，需要使用 Microsoft ActiveX 控制項，以供使用者瀏覽器做為外掛程式使用。 您可以在系統提示時，預先安裝 ActiveX 控制項，或讓使用者安裝它，這會在第一次使用商務用 Skype Web App 時，或第一次存取需要 ActiveX 控制項的功能時發生。

> [!NOTE]
> 在商務用 Skype Server Edge Server 部署中，需要在周邊網路中使用 HTTPS 反向 proxy，才能進行商務用 Skype Web App 用戶端存取。 您也必須發佈簡易 URLs。 如需詳細資訊，請參閱[為商務用 Skype Server 中的簡易 URLs](../../plan-your-deployment/network-requirements/simple-urls.md)[設定反向 Proxy 伺服器](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-reverse-proxy-servers)和 DNS 需求。

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>啟用商務用 Skype Web App 的 Multi-Factor 驗證
<a name="MFA"> </a>

商務用 skype Web App、Skype 會議應用程式和商務用 Skype for Mac 支援多重要素驗證。 除了使用者名稱和密碼之外，您還可以要求其他驗證方法（例如智慧卡或 Pin 碼），以驗證在使用者登入商務用 Skype 會議時加入外部網路的使用者。 您可以在商務用 Skype Server 中部署 Active Directory Federation Service (AD FS) 同盟伺服器及啟用被動式驗證，以啟用多重要素驗證。 設定 AD FS 後，嘗試加入商務用 Skype 會議的外部使用者，會呈現一個 AD FS 多重要素驗證網頁，其中包含使用者名稱和密碼挑戰，以及您設定的任何其他驗證方法。

> [!IMPORTANT]
> 如果您打算設定 AD FS 以進行多重要素驗證，請注意下列事項：

- 如果會議參與者和召集人都位於相同的組織中，或是兩者皆來自 AD FS 同盟組織，多重因素 ADFS 驗證便會運作。 因為 Lync server web 基礎結構目前不支援 Lync 同盟使用者，所以多重要素 ADFS 驗證無法運作。

- 如果您使用硬體負載平衡器，請在負載平衡器上啟用 cookie 暫留，使來自商務用 Skype Web App 或會議應用程式用戶端的所有要求都是由同一部前端伺服器處理。

- 當您在商務用 Skype Server 和 AD FS 伺服器之間建立信賴憑證者信任時，請指派足夠長的權杖有效期，以橫跨商務用 Skype 會議的最大長度。 通常，在240分鐘的標記壽命已足夠。

- 此設定不適用於 Lync 行動用戶端。

### <a name="configure-multi-factor-authentication"></a>設定 Multi-Factor 驗證

1. 安裝 AD FS 同盟伺服器角色。 如需詳細資訊，請參閱 [Active Directory Federation Services 2.0 部署指南](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd807092(v=ws.10))

2. 建立 AD FS 的憑證。 如需詳細資訊，請參閱規劃及部署 AD FS 的「 [同盟伺服器憑證](/previous-versions/azure/azure-services/jj205462(v=azure.100)) 」一節，以搭配單一登入主題使用。

3. 在 [Windows PowerShell] 命令列介面中，執行下列命令：

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. 執行下列命令來建立合作關係：

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. 設定下列信賴憑證者規則：

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>停用 BranchCache
<a name="MFA"> </a>

Windows 7 和 Windows Server 2008 R2 中的 [BranchCache] 功能可能會干擾商務用 Skype Web App web 元件。 若要防止商務用 Skype Web App 使用者的問題，請確定未啟用 BranchCache。

如需停用 BranchCache 的詳細資訊，請參閱 [BranchCache 部署指南](/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)。

## <a name="verifying-skype-for-business-web-app-deployment"></a>驗證商務用 Skype Web App 部署
<a name="MFA"> </a>

您可以使用 Test-CsUcwaConference Cmdlet，以驗證一對測試使用者是否可以使用整合通訊 Web API (UCWA) 參與會議。 如需此 Cmdlet 的詳細資訊，請參閱商務用 Skype Server 管理命令介面檔中的 [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) 。

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>在 Windows Server 2008 R2 上疑難排解外掛程式安裝
<a name="MFA"> </a>

如果執行 Windows Server 2008 R2 的電腦上的外掛程式安裝失敗，您可能需要修改 Internet Explorer 安全性設定或 DisableMSI 登錄機碼設定。

### <a name="modify-the-security-setting-in-internet-explorer"></a>修改 Internet Explorer 中的安全性設定

1. 開啟 Internet Explorer。

2. 依序按一下 [ **工具**] 及 [ **網際網路選項**]，然後按一下 [ **高級**]。

3. 向中向左下到 [ **安全性** ] 區段。

4. 清除 [ **不要將加密的頁面儲存至磁片**]，然後按一下 **[確定]**。

    > [!NOTE]
    > 若選取此設定，當您嘗試從商務用 Skype Web App 下載附件時，也會發生錯誤。

5. 重新加入會議。 外掛程式應該不會發生錯誤的下載。

### <a name="modify-the-disablemsi-registry-setting"></a>修改 DisableMSI 登錄設定

1. 按一下 **[開始]**，再按一下 **[執行]**。

2. 若要存取登錄編輯程式，請輸入 **regedit**。

3. 流覽至 HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer。

4. 編輯或加入 REG_DWORD 類型的 DisableMSI 登錄機碼，並將其設定為0。

5. 重新加入會議。

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>啟用 Skype 會議應用程式以取代商務用 Skype Web App (選用，僅限商務用 Skype Server 2015) 
<a name="SMA_Enable"> </a>

此程式是選用的，且適用于商務用 Skype Server 2015 CU5 和更新版本。 如果您不使用它，外部使用者將繼續使用商務用 Skype Web App 加入會議。

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>啟用簡化的會議加入和 Skype 會議應用程式

1. 當您啟用存取內容傳遞網路 (CDN) 時，使用者將能夠連線至 CDN online，並取得 Windows) 上的 Skype 會議應用程式 (和商務用 Skype for Mac (mac) ，而且會使用簡化的會議加入體驗。

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. 允許用戶端從會議加入網頁或 Skype 會議應用程式傳送至 Microsoft 伺服器的用戶端記錄遙測 (此命令的預設值為 false) 。

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    傳送給 Microsoft 的資訊嚴格遵循商務用 [Skype 資料收集慣例](/skypeforbusiness/legal-and-regulatory/data-collection-practices)。

3. 若未提供 CDN，請先設定超時，再回到本機主控的商務用 Skype Web App 體驗。 預設值為6秒。 如果此值設為0，則不會有任何超時。

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> 使用 MeetingUxUseCdn in 商務用 Skype Server 2015 累計更新5時，預設值會設為 False。 這會造成問題：商務用 Skype for Mac 用戶端無法將非同盟夥伴的會議加入為來賓，即使商務用 Skype 管理員已將 MeetingUxUseCdn 設定為 True 也是一樣。 為了運作，商務用 Skype Server 2015 必須有累計更新7、6.0.9319.534 或更新版本。 請參閱 [啟用 Skype 會議應用程式以取代商務用 Skype Server 2015 中的商務用 Skype Web App](https://support.microsoft.com/kb/4132312)。


## <a name="see-also"></a>另請參閱
<a name="SMA_Enable"> </a>

[規劃會議用戶端 (Web 應用程式和會議應用程式) ](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[在商務用 Skype Server 中設定會議加入頁面](../../manage/conferencing/meeting-join-page.md)

[Microsoft Online Services 隱私權聲明](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[授權條款與文件](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)