---
title: Lync Server 2013：部署 Lync Windows Store 應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aaae8df4d21e3aa766bd452c5ffd697dce30660a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507480"
---
# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a>在 Lync Server 2013 中部署 Lync Windows 應用商店應用程式

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-12-03_

讓使用者可以使用 Lync Windows Store 應用程式之前，請確定您的部署符合 [Lync Server 2013 的 Lync Windows 應用程式需求](lync-server-2013-lync-windows-store-app-requirements.md)。 如需設定 Lync Server 2013 以支援 Lync Windows Store 應用程式的詳細資訊，請參閱 NextHop 的博客文章：「Lync Server 自動探索」和 Lync Windows Store App，網址為 [https://go.microsoft.com/fwlink/?LinkId=271966](https://go.microsoft.com/fwlink/?linkid=271966) 。 正確設定伺服器環境之後，您可以搜尋 "Lync"，以引導使用者從 Windows 存放區下載 Lync 應用程式。

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a>啟用 Lync Windows Store 應用程式的 Multi-Factor 驗證

Lync Server 2013 的累計更新：六月2013新增對 Lync Windows Store 應用程式用戶端的多重要素驗證的支援。 除了使用者名稱和密碼之外，您還可以要求其他驗證方法，例如智慧卡或 Pin 碼，以便在外部使用者登入 Lync 會議時進行驗證。 若要啟用多重要素驗證，請在 Lync Server 2013 中部署 Active Directory Federation Service (AD FS) 同盟伺服器並啟用被動式驗證。 設定 AD FS 後，嘗試加入 Lync 會議的外部使用者會呈現一個 AD FS 多重要素驗證網頁，其中包含使用者名稱和密碼挑戰，以及您已設定的任何其他驗證方法。

<div class=" ">


> [!IMPORTANT]  
> 如果您打算設定 AD FS 以進行 Lync Windows Store 應用程式的多重要素驗證，則以下是重要考慮： 
> <UL>
> <LI>
> <P>Lync Server 2013 （具有 Lync Server 2013 的累計更新）：至少需要6月2013。 Lync 2013 桌面用戶端不需要 Lync Server 2013 的累計更新：6月2013，因此可能會顯示被動驗證可正常運作，因為 Lync 2013 用戶端可以進行驗證。 不過，Lync Windows Store 應用程式用戶端的驗證程式會無法完成，而且不會顯示任何通知或錯誤訊息。</P>
> <LI>
> <P>必須設定伺服器，讓被動驗證成為唯一提供的驗證類型。</P>
> <LI>
> <P>如果您使用硬體負載平衡器，請在負載平衡器上啟用 cookie 持久性，使來自 Lync Windows Store 應用程式用戶端的所有要求都是由同一部前端伺服器處理。</P>
> <LI>
> <P>當您在 Lync Server 和 AD FS 伺服器之間建立信賴憑證者信任時，請指派一個足夠長的權杖壽命，以橫跨 Lync 會議的最大長度。 通常，在240分鐘的標記壽命已足夠。</P></LI></UL>



</div>

**設定 Multi-Factor 驗證**

1.  安裝 AD FS 同盟伺服器角色。 如需詳細資訊，請參閱《 Active Directory Federation Services 2.0 部署指南》 <https://go.microsoft.com/fwlink/p/?linkid=267511> 。

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

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a>在執行 Lync Windows Store 應用程式的裝置上，未正確設定時間及日期

裝置上的時間設定必須與伺服器上的時間設定同步。 這對 Microsoft Surface 等裝置及其他執行 Windows RT 但未加入網域的裝置尤其重要。 若要在時間伺服器自動設定這些裝置上的時間，請在裝置上以提升許可權的命令提示字元執行下列命令：
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a>Lync Windows Store 應用程式無法存取 Lync 伺服器或服務

Lync Windows Store 應用程式可能無法透過網路介面卡（如 4G LTE USB 數據機）來存取 Lync server 或服務，其不會以 Windows 8 註冊為實體裝置。 即使桌面應用程式和瀏覽器可以存取其他伺服器和網站，Lync Windows Store 應用程式也可能會發生此問題。

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a>Lync Windows Store 應用程式無法使用 Lync Server 2010 和 Office 通訊伺服器 2007 R2 Edge Server 登入

如果您的拓撲包含 Lync Server 2010 與 Office 通訊伺服器 2007 R2 Edge Server，則您需要在 Lync Server 2010：7月2013的累計更新中，執行拓撲產生器的更新版本。 舊版的拓撲產生器不會建立所需的 Office 通訊伺服器 2007 Edge Server 對應，所以 Lync Windows Store 應用程式用戶端無法登入。 需要下列步驟：

1.  在 Lync Server 2010 集區和 Lync Server 2010 Director 上安裝 Lync Server 2010：7月2013的累計更新。

2.  執行下列動作，更新 Lync AutoDiscover 設定，以指出外部 SIP 輸入點為 Edge server 位址：
    
    1.  開啟 Lync Server 管理命令介面。
    
    2.  執行下列命令：
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a>因為憑證名稱驗證失敗，所以 Lync Windows Store 應用程式無法登入

未執行最新版本 Lync Windows Store 應用程式的 Microsoft 365 或 Office 365 使用者可能會發生登入問題。 使用多個網域時，通常會發生此問題 (例如，當 SIP URI 是 **userA@domainZ.com** ，但 Edge Server 是 **sip.domainX.com**) 。 若要修正此問題，使用者應安裝最新版的 Lync Windows Store 應用程式，該應用程式也需要 Windows 8.1。

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a>使用 Lync Windows Store 應用程式記錄檔來疑難排解問題

您可以使用在裝置上產生的記錄檔來疑難排解問題。 記錄檔會儲存在下列資料夾中：

% LocalAppData% \\ \\ LyncMX \_ 8wekyb3d8bbwe \\ LocalState \\ 追蹤

在您從使用者取得記錄之前，請確定已開啟記錄，然後要求使用者儲存記錄，以便儲存在記憶體中的所有資訊也都會儲存至硬碟上的檔案。

**開啟記錄**

1.  開啟裝置上的 Lync Windows Store 應用程式。

2.  從畫面右側滑動。 如果您是使用滑鼠，請指向螢幕的右上角，然後將滑鼠指標移至螢幕。

3.  選取 [ **設定**]，選取 [ **選項**]，然後將 [ **診斷記錄** ] 設定為 [ **開啟**]。

4.  如果 **診斷記錄** 先前已經關閉，您必須重新開機 Lync。 若要重新開機 Lync，請執行下列其中一項操作：
    
      - 重新開機裝置。
    
      - 結束 Lync 工作並重新啟動應用程式。 若要結束任務，請開啟 [Windows 工作管理員]，選取 [ **Lync**]，然後按 [ **結束**工作]。 如果未列出 Lync，請按一下 [ **更多詳細資料** ]，然後在 [ **背景處理**程式] 下尋找 lync。

**儲存記錄**

1.  開啟裝置上的 Lync Windows Store 應用程式。

2.  嘗試登入。

3.  從畫面右側滑動。 如果您是使用滑鼠，請指向螢幕的右上角，然後將滑鼠指標移至螢幕。

4.  選取 [ **設定**]，選取 [ **關於**]，然後選取 [ **儲存記錄**檔]。

</div>

</div>

<span> </span>

</div>

</div>

</div>

