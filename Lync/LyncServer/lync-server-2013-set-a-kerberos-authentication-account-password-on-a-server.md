---
title: Lync Server 2013： 在伺服器上設定 Kerberos 驗證帳戶密碼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aeef318392540aaa0600a4b61f20a296df25ca5f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a>在 Lync Server 2013 中的伺服器上設定 Kerberos 驗證帳戶密碼

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-01-16_

若要順利完成此程序，您應以 RTCUniversalServerAdmins 群組成員的使用者身分登入。

您必須設定上有前端伺服器、 Standard Edition server 和 Director 每個網站的 Kerberos 帳戶的密碼。 您可以藉由執行**Set-cskerberosaccountpassword**設定密碼 網站 （例如，一部前端伺服器） 中的一部伺服器上的 Windows PowerShell cmdlet。 對於每個網站，您必須執行**Set-cskerberosaccountpassword** 指令程式。 指令程式的 Web 服務 」 服務，設定網際網路資訊服務 (IIS)，並接著在 Active Directory 網域服務中的電腦帳戶上設定的密碼。 使用已設定為來源的 Kerberos 帳戶密碼的另一部伺服器時，替代方法，根據哪一個參數可搭配指令程式，可設定 IIS 一部伺服器上。

當您使用**Set-cskerberosaccountpassword** cmdlet 來設定密碼時，Kerberos 會將密碼設為隨機產生的字串。 此指令程式的連絡人中所有指派給此帳戶的 Lync Server 2013 管理中心網站的所有 IIS 執行個體。

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a>若要設定 Kerberos 驗證帳戶密碼

1.  使用 Lync Server 管理命令介面安裝 RTCUniversalServerAdmins 群組成員身分登入網域的任何電腦。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  在命令提示字元中執行下列命令：
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    例如：
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > 您必須使用 Domain\User 格式指定 UserAccount 參數。 User@Domain.extension 格式不是支援參照建立用於 Kerberos 驗證的電腦物件。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 對 Kerberos 驗證，如新增帳戶或移除帳戶進行任何變更之後您必須從 Lync Server 管理命令介面命令提示字元執行<STRONG>Enable-cstopology</STRONG> 。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

