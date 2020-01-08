---
title: Lync Server 2013：移除網站中的 Kerberos 驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f030083bc49822f1d41e297388f6ca7dbf66d397
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a>在 Lync Server 2013 中從網站移除 Kerberos 驗證

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-01-16_

若要成功完成此程式，您應該以 RTCUniversalServerAdmins 群組成員的使用者身分登入。

如果您需要從網站移除 Kerberos 驗證或淘汰網站，您必須使用**CsKerberosAccountAssignment** Cmdlet，從網站移除 kerberos 驗證帳戶指派。 使用下列程式來移除 Kerberos 驗證帳戶指派，這會從網站中的所有電腦移除作業。

<div class=" ">


> [!WARNING]  
> 如果您要永久淘汰已啟用 Kerberos 的帳戶，您應該在移除作業之後，使用 Active Directory 使用者和電腦從 Active Directory 網域服務中刪除該帳戶。 如果您打算將來使用該物件，您可能會想要保留 Active Directory 物件。



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a>從網站移除 Kerberos 驗證

1.  如果您是 RTCUniversalServerAdmins 群組的成員，請登入執行 Lync Server 2013 的網域中的電腦，或登入安裝管理工具的電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  從命令列執行下列兩個命令：
    
       ```
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```
        Enable-CsTopology
       ```
    
    例如：
    
       ```
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > 在對 Kerberos 驗證進行任何變更之後（例如新增帳戶或移除帳戶），您必須從 Lync Server Management Shell 命令提示字元執行<STRONG>Enable-CsTopology</STRONG> 。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

