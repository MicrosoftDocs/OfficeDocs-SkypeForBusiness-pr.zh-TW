---
title: Lync Server 2013：部署 Lync Web App
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8babb6bf37e3dd75f2051dd08f0b2ebf3a4f093b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-web-app-in-lync-server-2013"></a>在 Lync Server 2013 中部署 Lync Web App

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-18_

Lync Web App 是以 Lync Server 2013 安裝的網際網路資訊服務 (IIS) 網頁用戶端，且預設為啟用。 若要在伺服器上啟用 Lync Web App 或將網頁用戶端部署至使用者，則不需要執行其他步驟。 每當使用者按一下會議 URL，但未安裝 Lync 2013 用戶端時，使用者就會看到可使用最新版本的 Lync Web App 加入會議的選項。

Lync Web App 中的語音、影片和共用功能需要 Microsoft ActiveX 控制項。 您可以在系統提示時，預先安裝 ActiveX 控制項，或允許使用者安裝它，這會在第一次使用 Lync Web App 時或第一次存取需要 ActiveX 控制項的功能時發生。

<div class=" ">


> [!NOTE]  
> 在 Lync Server 2013 Edge Server 部署中，Lync Web App 用戶端存取需要在周邊網路中使用 HTTPS 反向 proxy。 您也必須發佈簡易 URLs。 如需詳細資訊，請參閱設定 lync server <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">2013 的反向 proxy 伺服器</A> 及 <A href="lync-server-2013-planning-for-simple-urls.md">在 Lync Server 2013 中規劃簡易 URLs</A>。



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a>啟用 Lync Web App 的 Multi-Factor 驗證

Lync Server 2013 版本的 Lync Web App 支援多重要素驗證。 除了使用者名稱和密碼之外，您還可以要求其他驗證方法（例如智慧卡或 Pin 碼），以驗證在使用者登入 Lync 會議時加入外部網路的使用者。 您可以在 Lync Server 2013 中部署 Active Directory Federation Service (AD FS) 同盟伺服器並啟用被動式驗證，以啟用多重要素驗證。 設定 AD FS 後，嘗試加入 Lync 會議的外部使用者會呈現一個 AD FS 多重要素驗證網頁，其中包含使用者名稱和密碼挑戰，以及您已設定的任何其他驗證方法。

<div class=" ">


> [!IMPORTANT]  
> 如果您打算設定 AD FS 以進行多重要素驗證，請注意下列事項： 
> <UL>
> <LI>
> <P>如果會議參與者和召集人都位於相同的組織中，或是兩者皆來自 AD FS 同盟組織，多重因素 ADFS 驗證便會運作。 因為 Lync server web 基礎結構目前不支援 Lync 同盟使用者，所以多重要素 ADFS 驗證無法運作。</P>
> <LI>
> <P>如果您使用硬體負載平衡器，請在負載平衡器上啟用 cookie 持久性，讓 Lync Web App 用戶端的所有要求都是由同一部前端伺服器處理。</P>
> <LI>
> <P>當您在 Lync Server 和 AD FS 伺服器之間建立信賴憑證者信任時，請指派一個足夠長的權杖壽命，以橫跨 Lync 會議的最大長度。 通常，在240分鐘的標記壽命已足夠。</P>
> <LI>
> <P>此設定不適用於 Lync 行動用戶端。</P></LI></UL>



</div>

**設定 Multi-Factor 驗證**

1.  安裝 AD FS 同盟伺服器角色。 如需詳細資訊，請參閱《 Active Directory Federation Services 2.0 部署指南》，網址為 <https://go.microsoft.com/fwlink/p/?linkid=267511>

2.  建立 AD FS 的憑證。 如需詳細資訊，請參閱規劃及部署 AD FS 的「同盟伺服器憑證」一節，以與單一登入主題搭配使用 [https://go.microsoft.com/fwlink/p/?LinkId=285376](https://go.microsoft.com/fwlink/p/?linkid=285376) 。

3.  在 [Windows PowerShell] 命令列介面中，執行下列命令：
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  執行下列命令來建立合作關係：
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  設定下列信賴憑證者規則：
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="branchcache-configuration"></a>BranchCache 設定

Windows 7 和 Windows Server 2008 R2 中的 [BranchCache] 功能可能會干擾 Lync Web App Web 元件。 若要防止 Lync Web App 使用者發生問題，請確定未啟用 BranchCache。

如需停用 BranchCache 的詳細資訊，請參閱《 BranchCache 部署指南》，可在 Microsoft 下載中心 [https://go.microsoft.com/fwlink/p/?LinkId=268788](https://go.microsoft.com/fwlink/p/?linkid=268788) 和 HTML 格式的 Windows Server 2008 R2 技術文件庫中，以 HTML 格式使用 [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?linkid=268789) 。

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a>驗證 Lync Web App 部署

您可以使用 Test-CsUcwaConference Cmdlet，以驗證一對測試使用者是否可以使用整合通訊 Web API (UCWA) 參與會議。 如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔中的 [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) 。

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a>在 Windows Server 2008 R2 上疑難排解外掛程式安裝

如果執行 Windows Server 2008 R2 的電腦上的外掛程式安裝失敗，您可能需要修改 Internet Explorer 安全性設定或 DisableMSI 登錄機碼設定。

**修改 Internet Explorer 中的安全性設定**

1.  開啟 Internet Explorer。

2.  依序按一下 [ **工具**] 及 [ **網際網路選項**]，然後按一下 [ **高級**]。

3.  向中向左下到 [ **安全性** ] 區段。

4.  清除 [ **不要將加密的頁面儲存至磁片**]，然後按一下 **[確定]**。
    
    <div class=" ">
    

    > [!NOTE]  
    > 若選取此設定，當嘗試從 Lync Web App 下載附件時，也會發生錯誤。

    
    </div>

5.  重新加入會議。 外掛程式應該不會發生錯誤的下載。

**修改 DisableMSI 登錄設定**

1.  按一下 **[開始]**，再按一下 **[執行]**。

2.  若要存取登錄編輯程式，請輸入 **regedit**。

3.  流覽至 HKEY \_ LOCAL \_ MACHINE \\ 軟體 \\ 原則 \\ Microsoft \\ Windows \\ Installer。

4.  編輯或加入類型為 REG DWORD 的 DisableMSI 登錄機碼 \_ ，並將其設定為0。

5.  重新加入會議。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定會議加入頁面](lync-server-2013-configuring-the-meeting-join-page.md)  
[Lync Server 2013 的 lync Web App 支援平臺](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

