---
title: Lync Server 2013：將 Kerberos 驗證帳戶指派到網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a28efed0276fd1665746f55fdf2bdc14cef8e226
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a>在 Lync Server 2013 中指派 Kerberos 驗證帳戶至網站

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017-04-18_

若要順利完成此程序，您應以 RTCUniversalServerAdmins 群組成員的使用者身分登入。

建立 Kerberos 帳戶之後，您必須將它指派給網站。 這是 Lync Server 2013 網站，而非 Active Directory 網站。 每個部署可以建立多個 Kerberos 驗證帳戶，但只能指派一個帳戶給一個網站。 使用下列程序，可指派先前建立的 Kerberos 驗證帳戶給網站。 如需建立 Kerberos 帳戶的詳細資訊，請參閱 [在 Lync Server 2013 中建立 Kerberos 驗證帳戶](lync-server-2013-create-a-kerberos-authentication-account.md)。

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a>若要指派 Kerberos 驗證帳戶給網站

1.  以 RTCUniversalServerAdmins 群組成員的身分，登入執行 Lync Server 2013 的網域中的電腦，或登入已安裝系統管理工具的電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在命令提示字元中執行下列命令：
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```powershell
        Enable-CsTopology
       ```
    
    例如：
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```powershell
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > 您必須使用 Domain\User 格式指定 UserAccount 參數。不支援以 User@Domain.extension 格式來指稱基於 Kerberos 驗證目的而建立的電腦物件。

    
    </div>

4.  **選用**：您可以為 WebServices 設定覆寫的 FQDN (完整功能變數名稱) ，如 [每次 [變更 Lync Server 2013 中的 Web 服務 URL](lync-server-2013-change-the-web-services-url.md)]。 如果是這種情況，您也必須為此 FQDN 新增 SPN。 例如，如果 FQDN 是 webservices，您會執行：
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > 在對 Kerberos 驗證進行任何變更（例如新增帳戶或移除帳戶）之後，您必須從 Lync Server 管理命令介面命令提示字元中執行 <STRONG>Enable-CsTopology</STRONG> 。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

