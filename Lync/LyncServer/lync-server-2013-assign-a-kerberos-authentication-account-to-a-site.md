---
title: Lync Server 2013：將 Kerberos 驗證帳戶指派到網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb755f7e7b814d4ca643bd04ddfc0241b4d96d60
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40976934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a>在 Lync Server 2013 中將 Kerberos 驗證帳戶指派到網站

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017-04-18_

若要成功完成此程式，您應該以 RTCUniversalServerAdmins 群組成員的使用者身分登入。

建立 Kerberos 帳戶之後，您必須將它指派給網站。 這是 Lync Server 2013 網站，不是 Active Directory 網站。 您可以針對每個部署建立多個 Kerberos 驗證帳戶，但您只能將一個帳戶指派至網站。 使用下列程式，將先前建立的 Kerberos 驗證帳戶指派至網站。 如需有關建立 Kerberos 帳戶的詳細資訊，請參閱[在 Lync Server 2013 中建立 Kerberos 驗證帳戶](lync-server-2013-create-a-kerberos-authentication-account.md)。

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a>將 Kerberos 驗證帳戶指派給網站

1.  如果您是 RTCUniversalServerAdmins 群組的成員，請登入執行 Lync Server 2013 的網域中的電腦，或登入安裝管理工具的電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  從命令列執行下列兩個命令：
    
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
    > 您必須使用 [Domain\User] 格式指定 UserAccount 參數。 在針對 Kerberos 驗證目的所建立的電腦物件上，不支援 User@Domain 副檔名格式。

    
    </div>

4.  **選用**：您可能已針對您的 WebServices 設定覆寫 FQDN （完整功能變數名稱），如[[在 Lync Server 2013 中變更 Web 服務 URL](lync-server-2013-change-the-web-services-url.md)]。 如果是這種情況，您也需要為此 FQDN 新增 SPN。 例如，如果 FQDN 是 webservices，您將會執行：
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > 在對 Kerberos 驗證進行任何變更之後（例如新增帳戶或移除帳戶），您必須從 Lync Server Management Shell 命令提示字元執行<STRONG>Enable-CsTopology</STRONG> 。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

