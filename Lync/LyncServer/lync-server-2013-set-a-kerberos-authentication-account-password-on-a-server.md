---
title: Lync Server 2013：在伺服器上設定 Kerberos 驗證帳戶密碼
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
ms.openlocfilehash: 97130b93052c0e14e1e4b4863be8ceea6118db05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a>在 Lync Server 2013 中於伺服器上設定 Kerberos 驗證帳戶密碼

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-01-16_

若要成功完成此程式，您應該以 RTCUniversalServerAdmins 群組成員的使用者身分登入。

您必須針對每個擁有前端伺服器、標準版伺服器和控制器的網站，在 Kerberos 帳戶上設定密碼。 您可以在網站中的一個伺服器（例如，一個前端伺服器）上執行**設定 CsKerberosAccountPassword** 的 Windows PowerShell Cmdlet，以設定密碼。 針對每個網站，您必須執行**CsKerberosAccountPassword** Cmdlet。 Cmdlet 會針對 Web 服務服務設定網際網路資訊服務（IIS），然後在 Active Directory 網域服務的電腦帳戶上設定密碼。 根據與 Cmdlet 搭配使用的參數，替代方法是在一台伺服器上設定 IIS，而您使用的是另一台已設定為 Kerberos 帳戶密碼來源的伺服器。

當您使用**CsKerberosAccountPassword** Cmdlet 設定密碼時，Kerberos 會將密碼設定為隨機產生的字串。 這個 Cmdlet 會在指派這個帳戶的所有 Lync Server 2013 中央網站中，聯絡所有 IIS 實例。

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a>若要設定 Kerberos 驗證帳戶的密碼

1.  使用 Lync Server 管理命令介面，以 RTCUniversalServerAdmins 群組成員的身分登入任何網域電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  從命令列執行下列兩個命令：
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    例如：
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > 您必須使用 [Domain\User] 格式指定 UserAccount 參數。 不支援 User@Domain 副檔名格式，以參照為 Kerberos 驗證目的所建立的電腦物件。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 在對 Kerberos 驗證進行任何變更之後（例如新增帳戶或移除帳戶），您必須從 Lync Server Management Shell 命令提示字元執行<STRONG>Enable-CsTopology</STRONG> 。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

