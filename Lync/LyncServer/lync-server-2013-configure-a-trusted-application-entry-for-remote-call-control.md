---
title: 為遠端呼叫控制設定信任的應用程式項目
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trusted application entry for remote call control
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558636(v=OCS.15)
ms:contentKeyID: 48183829
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfaec78b0c7d64308b5899a6e7dc5fa95c1f53fb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trusted-application-entry-for-remote-call-control-in-lync-server-2013"></a>在 Lync Server 2013 中為遠端呼叫控制設定信任的應用程式項目

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-11-02_

SIP/CSTA 閘道必須設定為受信任的應用程式，Lync Server 才能套用靜態路由來路由呼叫至閘道。

<div>


> [!IMPORTANT]
> 如果您是從舊版的 Lync Server 部署中遷移使用者，請務必移除您在執行本主題中的程式之前，您針對 SIP/CSTA 閘道所建立的所有現有信任應用程式專案（先前稱為授權主項目目）。 如需詳細資訊，請參閱<A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">在 Lync Server 2013 中移除舊版授權主機（選用）</A>。<BR>如果您打算使用傳輸控制通訊協定（TCP）連線來部署新的遠端呼叫控制，您必須確認在現有信任的應用程式和池上，如果您想要針對新的受信任的應用程式使用相同的 TCP 埠，請將 [<STRONG>限制服務使用量</STRONG>] 設定在現有信任的應用程式和 pool 上。



</div>

<div>

## <a name="to-configure-a-trusted-application-entry-for-the-sipcsta-gateway"></a>針對 SIP/CSTA 閘道設定受信任的應用程式專案

1.  登入 Lync Server 管理命令介面已安裝為 RTCUniversalServerAdmins 群組成員的電腦，或是您已將**新的-CsTrustedApplicationPool** Cmdlet 指派給其的角色型存取控制（RBAC）角色。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  若要建立信任的應用程式專案，請執行下列其中一項操作：
    
      - 針對傳輸層安全性（TLS）連線，請在命令提示字元中輸入下列內容：
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        例如：
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - 如果是傳輸控制通訊協定（TCP）連線，請在命令提示字元中輸入下列內容：
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        例如：
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  若要將信任的應用程式新增至該資源庫，請執行下列其中一項操作：
    
      - 針對 TLS 連線，請在命令提示字元中輸入下列內容：
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        例如：
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - 針對 TCP 連線，請在命令提示字元中輸入下列內容：
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        例如：
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  若要執行您對拓撲所做的已發佈變更，請在命令提示字元輸入下列內容：
    
        Enable-CsTopology

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中設定遠端呼叫控制的靜態路由](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[在 Lync Server 2013 中定義 SIP/CSTA 閘道 IP 位址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

