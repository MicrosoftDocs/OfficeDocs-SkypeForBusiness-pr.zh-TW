---
title: Lync Server 2013：設定被動式驗證
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
ms.openlocfilehash: 0a2e52f957a8aba7e69e97b0ec2100ffbc5a190c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a>設定 Lync Server 2013 被動式驗證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-11_

下列章節說明如何使用累積更新設定 Lync Server 2013：2013以支援被動驗證。 一旦啟用，即會要求啟用雙因素驗證的 Lync 使用者使用 [物理或虛擬智慧卡] 和有效的 PIN，以使用 Lync 2013，以累積更新的方式登入：2013用戶端年7月。

<div class="">


> [!NOTE]  
> 強烈建議客戶針對服務層級的註冊機構和 Web 服務啟用被動式驗證。 如果針對全域層級的註冊機構和 Web 服務啟用被動式驗證，可能會導致無法使用 Lync 2013 以累積更新登入的使用者，從而導致組織範圍的驗證失敗：2013用戶端電腦用戶端。



</div>

<div>

## <a name="web-service-configuration"></a>Web 服務設定

下列步驟說明如何為控制器、企業版池和標準版伺服器（將為被動驗證啟用）建立自訂的 web 服務設定。

**建立自訂的 web 服務設定**

1.  以累積更新登入您的 Lync Server 2013：使用 Lync 系統管理員帳戶的2013前端伺服器。

2.  啟動 Lync Server 2013 管理命令介面。

3.  從 Lync Server Management Shell 命令列，為每個主管、企業版池及標準版伺服器建立新的 Web 服務設定，只要執行下列命令，即可啟用被動式驗證：
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > WsFedPassiveMetadataUri FQDN 的值是您的 AD FS 2.0 伺服器的識別身分同盟服務名稱。 在 AD FS 2.0 管理主控台中，您可以在 [功能窗格] 中以滑鼠右鍵按一下 [<STRONG>服務</STRONG>]，然後選取 [<STRONG>編輯同盟服務屬性</STRONG>]，找到 [同盟服務名稱] 值。

    
    </div>

4.  執行下列命令，確認已正確設定 UseWsFedPassiveAuth 和 WsFedPassiveMetadataUri 值：
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  針對用戶端，被動式驗證是 webticket 驗證的最不可取的驗證方法。 針對將啟用被動式驗證的所有控制器、企業版池及標準版伺服器，您必須在 Lync Web 服務中執行下列命令停用所有其他驗證類型：
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  執行下列命令，確認所有其他驗證類型都已成功停用：
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a>Proxy 設定

當您針對 Lync Web 服務停用認證驗證時，Lync 用戶端會使用較不可取的喜好驗證類型（例如 Kerberos 或 NTLM）來驗證註冊機構服務。 您仍需要證書驗證來允許 Lync 用戶端檢索 webticket，不過，必須針對註冊機構服務停用 Kerberos 和 NTLM。

下列步驟說明如何針對要啟用被動式驗證的邊緣池、企業版池及標準版伺服器建立自訂 proxy 設定。

**建立自訂 proxy 配置**

1.  從 Lync Server Management Shell 命令列，使用累積更新為每個 Lync Server 2013 建立新的 proxy 設定：年 7 2013 月的邊緣池、企業版池及標準版伺服器（可透過執行）啟用下列命令：
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  執行下列命令，確認所有其他 proxy 驗證類型都已順利停用：
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

