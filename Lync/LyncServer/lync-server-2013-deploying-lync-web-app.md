---
title: Lync Server 2013：部署 Lync Web App
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c355be1c1709cede9c032d59790d6beefb337ff6
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40976290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-web-app-in-lync-server-2013"></a>在 Lync Server 2013 中部署 Lync Web App

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-18_

Lync Web App 是與 Lync Server 2013 一起安裝的網際網路 Information Services （IIS） Web 用戶端，且預設為啟用。 若要在伺服器上啟用 Lync Web App，或將 Web 用戶端部署給使用者，則無需執行其他步驟。 每當使用者按一下會議 URL，但沒有安裝 Lync 2013 用戶端時，系統會顯示使用最新版本的 Lync Web App 加入會議的選項。

Lync Web App 中的 [語音]、[影片] 和 [共用] 功能需要 Microsoft ActiveX 控制項。 您可以在出現提示時，事先安裝 ActiveX 控制項或允許使用者安裝，這會在第一次使用 Lync Web App 時，或第一次存取需要 ActiveX 控制項的功能時進行安裝。

<div class=" ">


> [!NOTE]  
> 在 Lync Server 2013 Edge 伺服器部署中，Lync Web App 用戶端存取需要在周邊網路中使用 HTTPS 反向 proxy。 您也必須發佈簡單的 Url。 如需詳細資訊，請參閱為<A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync server 2013 設定反向 proxy 伺服器</A>以及<A href="lync-server-2013-planning-for-simple-urls.md">規劃 lync server 2013 中的簡單 url</A>。



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a>啟用 Lync Web App 的多重要素驗證

Lync Server 2013 版本的 Lync Web App 支援多重要素驗證。 除了使用者名稱和密碼之外，您還可以要求其他驗證方法（例如智慧卡或 Pin），以驗證在登入 Lync 會議時從外部網路加入的使用者。 您可以透過部署 Active Directory Federation Services （AD FS）同盟伺服器並啟用 Lync Server 2013 中的被動式驗證，來啟用多重要素驗證。 設定 AD FS 之後，試圖加入 Lync 會議的外部使用者會得到一個 AD FS 多重要素驗證網頁，其中包含使用者名稱和密碼質詢，以及您已設定的任何其他驗證方法.

<div class=" ">


> [!IMPORTANT]  
> 如果您打算針對多重要素驗證設定 AD FS，請務必考慮下列事項： 
> <UL>
> <LI>
> <P>如果會議參與者和召集人都在同一個組織中，或都來自 AD FS 同盟組織，則多重要素 ADFS 驗證就會運作。 因為 Lync server web 基礎結構目前不支援 Lync 聯盟使用者，所以多重要素 ADFS 驗證無法運作。</P>
> <LI>
> <P>如果您使用硬體負載平衡器，請在負載平衡器上啟用 cookie 暫留，讓 Lync Web App 用戶端的所有要求都是由同一個前端伺服器來處理。</P>
> <LI>
> <P>當您在 Lync Server 與 AD FS 伺服器之間建立信賴方信任時，請指派一個足夠長的權杖有效期，以超過 Lync 會議的最大長度。 通常，240分鐘的標記生活就足夠了。</P>
> <LI>
> <P>此設定不會套用至 Lync mobile 用戶端。</P></LI></UL>



</div>

**設定多重要素驗證**

1.  安裝 AD FS 同盟伺服器角色。 如需詳細資訊，請參閱 Active Directory Federation Services 2.0 部署指南，網址為<http://go.microsoft.com/fwlink/p/?linkid=267511>

2.  建立適用于 AD FS 的憑證。 如需詳細資訊，請參閱與部署 AD FS 之方案的 [同盟伺服器憑證] 區段，以便與單一登入主題搭配使用[http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)。

3.  從 Windows PowerShell 命令列介面，執行下列命令：
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  執行下列命令以建立合作關係：
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  設定下列信賴方規則：
    
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

Windows 7 和 Windows Server 2008 R2 中的 BranchCache 功能可能會干擾 Lync Web App 網頁元件。 若要避免 Lync Web App 使用者的問題，請確定未啟用 BranchCache。

如需有關停用 BranchCache 的詳細資訊，請參閱 BranchCache 部署指南，此手冊位於 Microsoft 下載中心[http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788)的 Word 格式中，在 Windows Server 2008 R2 技術文件庫的 HTML 格式[http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789)中提供。

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a>驗證 Lync Web App 部署

您可以使用 CsUcwaConference Cmdlet 來確認一組測試使用者可以使用整合通訊 Web API （UCWA）參與會議。 如需此 Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔中的[Test CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) 。

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a>Windows Server 2008 R2 上的外掛程式安裝疑難排解

如果您在執行 Windows Server 2008 R2 的電腦上安裝外掛程式失敗，您可能需要修改 Internet Explorer 安全性設定或 DisableMSI 登錄機碼設定。

**在 Internet Explorer 中修改安全性設定**

1.  開啟 Internet Explorer。

2.  按一下 [**工具**]，按一下 [**網際網路選項**]，然後按一下 [**高級**]。

3.  向下滾動至 [**安全性**] 區段。

4.  清除 [**不要將加密的網頁存到磁片**]，然後按一下 **[確定]**。
    
    <div class=" ">
    

    > [!NOTE]  
    > 如果選取此選項，當您嘗試從 Lync Web App 下載附件時，此設定也會導致錯誤。

    
    </div>

5.  重新加入會議。 外掛程式應該會下載，不會發生錯誤。

**修改 DisableMSI 註冊表設定**

1.  按一下 [**開始**]，然後按一下 [**執行**]。

2.  若要存取 [登錄編輯程式]，請輸入**regedit**。

3.  流覽至 HKEY\_本機\_電腦\\軟體\\原則\\Microsoft\\Windows\\安裝程式。

4.  編輯或新增類型為 REG\_DWORD 的 DisableMSI 登錄機碼，並將其設為0。

5.  重新加入會議。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中設定會議加入頁面](lync-server-2013-configuring-the-meeting-join-page.md)  
[Lync Web App 支援的 Lync Server 2013 平臺](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

