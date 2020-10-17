---
title: 同步處理 Kerberos 驗證帳戶密碼至 IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ac886bf4eba4261a733241aa8d1d5396c4acc86
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523850"
---
# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a>在 Lync Server 2013 中同步處理 Kerberos 驗證帳戶密碼至 IIS

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2010-11-08_

若要順利完成此程序，您應以 RTCUniversalServerAdmins 群組成員的使用者身分登入。

在網站中，前端伺服器、Standard Edition 伺服器及 Director 可以使用 Kerberos 驗證帳戶，以驗證要求 Web 服務服務的要求。 此程式會在已獲指派 Kerberos 帳戶的網站中，找出每一部執行 Web 服務的伺服器，並更新 Internet Information Services (IIS) 設定設定為使用 Kerberos 帳戶。 如需詳細資訊，請參閱在 [Lync server 2013 中的伺服器上設定 Kerberos 驗證帳戶密碼](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)。

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a>若要設定 Kerberos 驗證帳戶密碼

1.  以 RTCUniversalServerAdmins 群組成員的身分登入來源電腦 (例如 fe01.contoso.com)。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在 [Lync Server 管理命令介面] 命令列中，執行下列兩個命令：
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    例如：
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > 來源電腦和目的地電腦的名稱必須是伺服器的完整網域名稱 (FQDN)。除非 FQDN 集區名稱與您作為來源電腦或目的地電腦使用的電腦名稱相同，否則您無法使用該集區 FQDN。

    
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

