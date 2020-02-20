---
title: Lync Server 2013： 設定被動驗證
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
ms.openlocfilehash: 8da93bc579bf1e58ac48acda397beb6092f32ab3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a>設定 Lync Server 2013 被動驗證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-07-11_

下節說明如何設定 Lync Server 2013 累計更新： 7 月 2013 以支援被動驗證。 雙因素驗證已啟用 Lync 之使用者啟用之後，必須使用實體或虛擬智慧卡及有效的 pin 碼登入 Lync 2013 累計更新： 7 月 2013年用戶端。

<div class="">


> [!NOTE]  
> 強烈建議客戶啟用被動驗證的登錄器，並在服務層級的 Web 服務。 如果被動驗證已啟用的登錄器，並在全域層級的 Web 服務，可能會導致整個組織的驗證失敗的使用者未登入 Lync 2013 累計更新： 7 月 2013年用戶端桌面用戶端。



</div>

<div>

## <a name="web-service-configuration"></a>Web 服務組態

下列步驟說明如何建立自訂 web 服務設定 Director、 Enterprise 集區和 Standard Edition server，將啟用被動驗證。

**若要建立自訂 web 服務組態**

1.  登入您 Lync Server 2013 累計更新： 7 月 2013年使用 Lync 系統管理員帳戶的前端伺服器。

2.  啟動 Lync Server 2013 管理命令介面。

3.  從 Lync Server 管理命令介面命令列，建立新的 Web 服務組態的每個 Director、 Enterprise 集區和 Standard Edition 伺服器，將啟用被動驗證，藉由執行下列命令：
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > WsFedPassiveMetadataUri FQDN 的值是同盟服務名稱的 AD FS 2.0 伺服器。 同盟服務名稱值可以中找到的 AD FS 2.0 管理主控台<STRONG>服務</STRONG>上從功能窗格中按一下滑鼠右鍵，然後選取 [<STRONG>編輯同盟服務內容</STRONG>。

    
    </div>

4.  確認 [UseWsFedPassiveAuth] 和 [WsFedPassiveMetadataUri 值已正確設定，藉由執行下列命令：
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  用戶端，被動驗證是 webticket 驗證的最低慣用的驗證方法。 所有 Director、 Enterprise 集區和 Standard Edition server，將啟用被動驗證，其他所有驗證類型必須停都都用 Lync Web 服務中執行下列命令：
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  確認所有其他驗證類型有已成功停用來執行下列命令：
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a>Proxy 組態

Lync Web 服務停用憑證驗證時，Lync 用戶端會使用佳的驗證類型，例如 Kerberos 或 ntlm 驗證，來對登錄器服務進行驗證。 仍然需要允許擷取 webticket Lync 用戶端憑證驗證，不過，Kerberos 及 NTLM 必須停用的登錄器服務。

下列步驟說明如何建立自訂的 proxy 設定 Edge 集區、 Enterprise 集區和 Standard Edition server，將啟用被動驗證。

**若要建立自訂的 proxy 設定**

1.  從 Lync Server 管理命令介面命令列，建立新的 proxy 設定每個 Lync Server 2013 的累計更新： 7 月 2013年將啟用被動驗證，藉由執行的 Edge 集區、 Enterprise 集區和 Standard Edition server下列命令：
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  確認所有其他 proxy 驗證類型有已成功停用來執行下列命令：
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

