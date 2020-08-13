---
title: 為遠端呼叫控制設定信任的應用程式專案
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
ms.openlocfilehash: 0135d26f0483b10752c8a823fdbda15ab9ba37b0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-trusted-application-entry-for-remote-call-control-in-lync-server-2013"></a>在 Lync Server 2013 中為遠端呼叫控制設定信任的應用程式專案

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-11-02_

SIP/CSTA 閘道必須設定為信任的應用程式，Lync 伺服器才能套用靜態路由，將通話路由傳送至閘道。

<div>


> [!IMPORTANT]
> 如果您要從舊版的 Lync Server 部署遷移使用者，請確定您已移除所有現有的受信任應用程式專案 (先前稱為已授權的主項目目) 您在執行本主題中的程式之前，您已為 SIP/CSTA 閘道建立。 如需詳細資訊，請參閱<A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a 舊版授權主機 In Lync Server 2013 (選用) </A>。<BR>如果您打算使用傳輸控制通訊協定 (TCP) 連線來部署新的遠端呼叫控制，您必須在現有信任的應用程式和集區上，確認必須在現有信任的應用程式和集區上設定 [<STRONG>限制服務使用方式</STRONG>]，如果您想要對新的受信任應用程式使用相同的 TCP 通訊埠。



</div>

<div>

## <a name="to-configure-a-trusted-application-entry-for-the-sipcsta-gateway"></a>若要設定 SIP/CSTA 閘道的受信任應用程式項目

1.  登入安裝了 Lync Server 管理命令介面的電腦，做為 RTCUniversalServerAdmins 群組的成員或以角色為基礎的存取控制 (RBAC) 角色（已指派**New-CsTrustedApplicationPool** Cmdlet）。

2.  啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  若要建立受信任應用程式項目，請執行下列其中一項作業：
    
      - 若是傳輸層安全性 (TLS) 連線，請在命令提示字元中輸入下列命令：
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        例如：
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - 若是傳輸控制通訊協定 (TCP) 連線，請在命令提示字元中輸入下列命令：
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        例如：
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  若要將受信任應用程式新增至集區，請執行下列其中一項作業：
    
      - 若是 TLS 連線，請在命令提示字元中輸入下列命令：
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        例如：
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - 若是 TCP 連線，請在命令提示字元中輸入下列命令：
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        例如：
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  若要實作您已發行的拓撲變更，請在命令提示字元中輸入下列命令：
    
        Enable-CsTopology

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定遠端呼叫控制的靜態路由](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[在 Lync Server 2013 中定義 SIP/CSTA 閘道 IP 位址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

