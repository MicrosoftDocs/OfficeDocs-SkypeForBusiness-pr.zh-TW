---
title: Lync Server 2013：設定被動驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 780b539aeaf6a6bc6956fc5f8b6185092675632b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532490"
---
# <a name="configuring-lync-server-2013-passive-authentication"></a>設定 Lync Server 2013 被動驗證

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-11_

下列章節說明如何設定具有累積更新的 Lync Server 2013：7月2013以支援被動式驗證。 一旦啟用，啟用兩個要素驗證的 Lync 使用者將需要使用實體或虛擬智慧卡和有效 PIN 碼，使用 Lync 2013 搭配累計更新來登入：7月2013用戶端。

<div class="">


> [!NOTE]  
> 強烈建議客戶在服務層級為註冊機構和 Web 服務啟用被動式驗證。 如果已為全域層級的註冊機構和 Web 服務啟用被動式驗證，則對於不是使用具有累積更新的 Lync 2013 登入的使用者，這可能會導致組織範圍的驗證失敗：2013用戶端桌面用戶端。



</div>

<div>

## <a name="web-service-configuration"></a>Web 服務設定

下列步驟說明如何針對 Director、Enterprise Pool 和 Standard Edition server 建立自訂 web 服務設定，以進行被動式驗證。

**建立自訂 web 服務設定**

1.  使用 Lync 系統管理員帳戶，以累計更新登入 Lync Server 2013： 7 2013 月前端伺服器。

2.  啟動 Lync Server 2013 管理命令介面。

3.  從 [Lync Server 管理命令介面] 命令列中，執行下列命令，為每個 Director、Enterprise 集區和 Standard Edition Server 建立新的 Web 服務設定，以進行被動式驗證：
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > WsFedPassiveMetadataUri FQDN 的值為 AD FS 2.0 伺服器的同盟服務名稱。 您可以在 AD FS 2.0 管理主控台中，以滑鼠右鍵按一下功能窗格中的 [ <STRONG>服務</STRONG> ]，然後選取 [ <STRONG>編輯同盟服務屬性</STRONG>]，即可找到 [同盟服務名稱] 值。

    
    </div>

4.  執行下列命令，確認 UseWsFedPassiveAuth 和 WsFedPassiveMetadataUri 值已正確設定：
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  若為用戶端，被動式驗證是 webticket 驗證的最低偏好驗證方法。 針對將啟用被動驗證的所有 Director、Enterprise Pool 和 Standard Edition server，您必須執行下列命令來停用 Lync Web 服務中的所有其他驗證類型：
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  執行下列命令，確認已成功停用所有其他驗證類型：
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a>Proxy 設定

停用 Lync Web 服務的憑證驗證時，Lync 用戶端會使用較不習慣的驗證類型，例如 Kerberos 或 NTLM，以驗證註冊機構服務。 仍需要憑證驗證，讓 Lync 用戶端能夠取得 webticket，但必須停用註冊器服務的 Kerberos 和 NTLM。

下列步驟說明如何針對將啟用被動驗證的 Edge 集區、Enterprise 集區和 Standard Edition server 建立自訂 proxy 設定。

**建立自訂 proxy 設定**

1.  從 [Lync Server 管理命令介面] 命令列中，為每個 Lync Server 2013 建立新的 proxy 設定，其累計更新為：7月 2013 Edge 集區、Enterprise Pool 和 Standard Edition Server，可執行下列命令來啟用被動驗證：
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  執行下列命令，確認已成功停用所有其他 proxy 驗證類型：
    ```powershell
    Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
     ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

