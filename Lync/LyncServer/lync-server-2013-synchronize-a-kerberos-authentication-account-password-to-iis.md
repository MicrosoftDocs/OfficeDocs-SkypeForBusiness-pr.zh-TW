---
title: 同步處理 Kerberos 驗證帳戶密碼至 IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bc56da26961caaad236857c88d601676e12cefc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a>在 Lync Server 2013 中同步處理 Kerberos 驗證帳戶密碼至 IIS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2010-11-08_

若要成功完成此程式，您應該以 RTCUniversalServerAdmins 群組成員的使用者身分登入。

在網站、前端伺服器、標準版伺服器和控制器上，都可以使用 Kerberos 驗證帳戶來驗證要求至 Web 服務服務的需求。 這個程式會在已指派 Kerberos 帳戶的網站中，尋找每個執行 Web 服務的伺服器，並更新 Internet Information Services （IIS）設定，以使用 Kerberos 帳戶。 如需詳細資訊，請參閱在[Lync server 2013 的伺服器上設定 Kerberos 驗證帳戶密碼](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)。

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a>設定和設定 Kerberos 驗證帳戶密碼

1.  以 RTCUniversalServerAdmins 群組成員的身分登入來源電腦（例如 fe01.contoso.com）。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  從 Lync Server Management Shell 命令列，執行下列兩個命令：
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    例如：
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > 來源電腦和目的電腦的名稱必須是伺服器的完整功能變數名稱（FQDN）名稱。 除非 [池名稱] 與您用來做為來源電腦或目的電腦的電腦名稱稱相同，否則您無法使用 [池 FQDN]。

    
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

