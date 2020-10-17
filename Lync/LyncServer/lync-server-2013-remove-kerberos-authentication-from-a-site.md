---
title: Lync Server 2013：從網站移除 Kerberos 驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7fdf5a304d428efb3b1192d02ade0187f052171
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536410"
---
# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a>在 Lync Server 2013 中，移除網站的 Kerberos 驗證

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-01-16_

若要順利完成此程序，您應以 RTCUniversalServerAdmins 群組成員的使用者身分登入。

如果您需要從網站移除 Kerberos 驗證或淘汰網站，您必須使用 **get-cskerberosaccountassignment** 指令程式，從網站移除 kerberos 驗證帳戶指派。 使用下列程式可移除 Kerberos 驗證帳戶指派，這會移除網站中所有電腦的指派。

<div class=" ">


> [!WARNING]  
> 如果您永久淘汰已啟用 Kerberos 的帳戶，您應該在移除指派後，使用 Active Directory 使用者和電腦從 Active Directory 網域服務中刪除。 如果您打算今後使用該物件，您可能會想要保留 Active Directory 物件。



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a>移除網站的 Kerberos 驗證

1.  以 RTCUniversalServerAdmins 群組成員的身分，登入執行 Lync Server 2013 的網域中的電腦，或登入已安裝系統管理工具的電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在命令提示字元中執行下列命令：
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    例如：
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > 在對 Kerberos 驗證進行任何變更（例如新增帳戶或移除帳戶）之後，您必須從 Lync Server 管理命令介面命令提示字元中執行 <STRONG>Enable-CsTopology</STRONG> 。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

