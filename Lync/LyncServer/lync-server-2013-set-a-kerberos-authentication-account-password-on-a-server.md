---
title: Lync Server 2013：在伺服器上設定 Kerberos 驗證帳戶密碼
description: Lync Server 2013：在伺服器上設定 Kerberos 驗證帳戶密碼。
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
ms.openlocfilehash: 723392e670ca0b4bc9796cd62dab3b1a61f99dd1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574839"
---
# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a>在 Lync Server 2013 中的伺服器上設定 Kerberos 驗證帳戶密碼

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-01-16_

若要順利完成此程序，您應以 RTCUniversalServerAdmins 群組成員的使用者身分登入。

您必須針對每個具有前端伺服器、Standard Edition 伺服器及 Director 的網站，在 Kerberos 帳戶上設定密碼。 您可以在**Set-CsKerberosAccountPassword**   網站中的一部伺服器上執行 Set-CsKerberosAccountPassword Windows PowerShell Cmdlet，以設定密碼 (例如，一部前端伺服器) 。 您必須針對每個網站執行**Set-CsKerberosAccountPassword**   Cmdlet。 Cmdlet 會為 Web 服務服務設定網際網路資訊服務 (IIS) ，然後在 Active Directory 網域服務中設定電腦帳戶的密碼。 另一種方法是根據使用 Cmdlet 的參數，在一部伺服器上設定 IIS，使用另一部已設定為 Kerberos 帳戶密碼來源的伺服器。

當您使用 **Set-CsKerberosAccountPassword** Cmdlet 來設定密碼時，Kerberos 會將密碼設定為隨機產生的字串。 此 Cmdlet 會聯繫指派此帳戶的所有 Lync Server 2013 中央網站中的所有 IIS 實例。

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a>若要設定 Kerberos 驗證帳戶的密碼

1.  以 RTCUniversalServerAdmins 群組成員的身分登入安裝了 Lync Server 管理命令介面的任何網域電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在命令提示字元中執行下列命令：
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    例如：
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > 您必須使用 Domain\User 格式指定 UserAccount 參數。 User@Domain 副檔名格式不支援參照為 Kerberos 驗證目的所建立的電腦物件。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 在對 Kerberos 驗證進行任何變更（例如新增帳戶或移除帳戶）之後，您必須從 Lync Server 管理命令介面命令提示字元中執行 <STRONG>Enable-CsTopology</STRONG> 。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

