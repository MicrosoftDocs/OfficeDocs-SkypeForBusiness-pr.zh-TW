---
title: Lync Server 2013：部署 Lync Windows Store 應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eef2e96b1e58bb9a92b2dc9748624d38f605965f
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40978276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a>在 Lync Server 2013 中部署 Lync Windows Store 應用程式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-12-03_

在讓使用者使用 Lync Windows Store 應用程式之前，請確定您的部署符合[Lync Server 2013 的 Lync Windows store 應用程式需求](lync-server-2013-lync-windows-store-app-requirements.md)。 如需設定 Lync Server 2013 以支援 Lync Windows Store 應用程式的詳細資訊，請參閱 NextHop 博客文章：「Lync Server 自動探索和 Lync Windows Store App [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966)」。 在伺服器環境設定正確之後，您可以搜尋「Lync」，讓使用者從 Windows 網上商店下載 Lync 應用程式。

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a>啟用 Lync Windows Store 應用程式的多重要素驗證

Lync Server 2013 的累計更新：2013年6月新增 Lync Windows Store 應用程式用戶端的多重要素驗證支援。 除了使用者名稱和密碼之外，您還可以要求其他驗證方法（例如智慧卡或 Pin），在使用者登入 Lync 會議時驗證外部使用者。 若要啟用多重要素驗證，您需要在 Lync Server 2013 中部署 Active Directory Federation Services （AD FS）同盟伺服器並啟用被動式驗證。 設定 AD FS 之後，試圖加入 Lync 會議的外部使用者會得到一個 AD FS 多重要素驗證網頁，其中包含使用者名稱和密碼質詢，以及您已設定的任何其他驗證方法.

<div class=" ">


> [!IMPORTANT]  
> 如果您打算針對 Lync Windows Store 應用程式設定針對多重要素驗證的 AD FS，請務必考慮下列事項： 
> <UL>
> <LI>
> <P>Lync Server 2013 含 Lync Server 2013 的累積更新：至少需要6月2013。 Lync 2013 傳統型用戶端不需要 Lync Server 2013 的累計更新：年6月2013，因此可能會顯示被動驗證，因為 Lync 2013 用戶端可以進行驗證。 不過，Lync Windows Store app 用戶端的驗證程式將無法完成，且不會顯示任何通知或錯誤訊息。</P>
> <LI>
> <P>伺服器必須設定為 [被動驗證] 是提供的唯一驗證類型。</P>
> <LI>
> <P>如果您使用硬體負載平衡器，請在負載平衡器上啟用 cookie 暫留，讓來自 Lync Windows Store 應用程式用戶端的所有要求都是由同一個前端伺服器來處理。</P>
> <LI>
> <P>當您在 Lync Server 與 AD FS 伺服器之間建立信賴方信任時，請指派一個足夠長的權杖有效期，以超過 Lync 會議的最大長度。 通常，240分鐘的標記生活就足夠了。</P></LI></UL>



</div>

**設定多重要素驗證**

1.  安裝 AD FS 同盟伺服器角色。 如需詳細資訊，請參閱 Active Directory Federation Services 2.0 部署<http://go.microsoft.com/fwlink/p/?linkid=267511>指南，網址為。

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
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a>可避免登入的已知問題

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a>在執行 Lync Windows Store 應用程式的裝置上未正確設定時間與日期

裝置上的 [時間] 設定必須與伺服器上的 [時間] 設定同步處理。 對於 Microsoft Surface 之類的裝置，以及執行未加入網域之 Windows RT 的其他裝置而言，這一點尤為重要。 若要從時間伺服器自動設定這些裝置上的時間，請在裝置上提升許可權的命令提示字元執行下列命令：
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a>Lync Windows Store app 無法存取 Lync server 或服務

Lync Windows Store 應用程式可能無法透過網路介面卡（例如 4G LTE USB 數據機）來存取 Lync server 或服務，而不會在 Windows 8 中以物理裝置的方式進行註冊。 即使傳統型應用程式和瀏覽器能夠存取其他伺服器和網站，Lync Windows Store 應用程式也可能會有這個問題。

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a>Lync Windows Store 應用程式無法使用 Lync Server 2010 和 Office 通訊伺服器 2007 R2 Edge 伺服器登入

如果您的拓朴是由 Lync Server 2010 與 Office 通訊伺服器 2007 R2 Edge 伺服器組成，您將需要執行 Lync Server 2010 累積更新中提供的更新版本的拓撲產生器：年 7 2013 月。 較舊版本的拓撲建立器不會建立 Office 通訊伺服器 2007 Edge 伺服器所需的對應，因此 Lync Windows Store 應用程式用戶端無法登入。 必須執行下列步驟：

1.  安裝 Lync Server 2010 的累積更新： Lync Server 2010 pool 和 Lync Server 2010 控制器上的2013。

2.  您可以執行下列動作，更新 Lync 自動探索設定，以指出外部 SIP 輸入點為邊緣伺服器位址：
    
    1.  開啟 Lync Server 管理命令介面。
    
    2.  執行下列命令：
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a>Lync Windows Store 應用程式無法登入，因為證書名稱驗證失敗

未執行最新版本 Lync Windows Store 應用程式的 Office 365 使用者可能會發生登入問題。 這個問題通常會在使用多個網域時（例如，當 SIP URI 為**userA@domainZ.com**但邊緣伺服器為**sip.domainX.com**時）。 若要修正此問題，使用者應該安裝最新版本的 Lync Windows Store 應用程式，這也需要 Windows 8.1。

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a>使用 Lync Windows Store 應用程式記錄來排查問題

您可以使用裝置上產生的記錄來疑難排解問題。 記錄會儲存在下列資料夾中：

% LocalAppData%\\\\LyncMX\_8wekyb3d8bbwe\\LocalState\\追蹤

在您從使用者取得記錄前，請確定已開啟記錄，然後要求使用者儲存記錄，讓儲存在記憶體中的所有資訊都儲存在硬碟上的檔案中。

**開啟記錄**

1.  在裝置上開啟 Lync Windows Store 應用程式。

2.  從畫面右側滑動。 如果您是使用滑鼠，請指向畫面右上角，然後將滑鼠指標向下移動畫面。

3.  選取 [**設定**]，選取 [**選項**]，然後將 [**診斷記錄**] 設定為 [**開啟**]。

4.  如果您先前已關閉**診斷記錄**，您必須重新開機 Lync。 若要重新開機 Lync，請執行下列其中一項操作：
    
      - 重新開機裝置。
    
      - 結束 Lync 工作並再次啟動 app。 若要結束工作，請開啟 Windows [工作管理員]，選取 [ **Lync**]，然後按一下 [**結束**工作]。 如果沒有列出 Lync，請在 [**背景處理**程式] 下，按一下 [**更多詳細資料**]，然後尋找 lync。

**儲存記錄**

1.  在裝置上開啟 Lync Windows Store 應用程式。

2.  嘗試登入。

3.  從畫面右側滑動。 如果您是使用滑鼠，請指向畫面右上角，然後將滑鼠指標向下移動畫面。

4.  選取 [**設定**]，選取 [**關於**]，然後選取 [**儲存記錄**]。

</div>

</div>

<span> </span>

</div>

</div>

</div>

