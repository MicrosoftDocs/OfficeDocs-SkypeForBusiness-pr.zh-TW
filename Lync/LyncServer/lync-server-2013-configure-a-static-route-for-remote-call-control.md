---
title: Lync Server 2013： 設定為遠端呼叫控制的靜態路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46fe499cdf622315ae0d0d789f0a3ed4283d78c1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a>在 Lync Server 2013 中設定為遠端呼叫控制的靜態路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-22_

遠端呼叫控制需要每個 Lync 伺服器集區都設有連接至專用交換機 (PBX) 的 SIP/CSTA 閘道從該集區的路徑。 此路徑需要每個集區有一個靜態路由集區將 proxy SIP 呼叫控制項郵件到 PBX 的通話相關聯的每個閘道。 如果您設定為遠端呼叫控制的全域靜態路由，並未設定靜態路由集區層級與每個集區會使用全域靜態路由。

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a>若要設定為遠端呼叫控制的靜態路由

1.  登入 Lync Server 管理命令介面以 RTCUniversalServerAdmins 群組或您已對其指派**New-csstaticroute** cmdlet 的角色型存取控制 (RBAC) 角色的成員身分的安裝所在的電腦。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  若要建立靜態路由，並將它放在變數 $TLSRoute 或 $TCPRoute，執行下列其中一項：
    
    <div class="">
    

    > [!TIP]  
    > 若要相符子網域的網域，您可以指定萬用字元值，在 MatchUri 參數中。 例如， <STRONG>*。 contoso.net</STRONG>。 該值比對任何與後置詞<STRONG>contoso.net</STRONG>結束的網域。

    
    </div>
    
      - 若是傳輸層安全性 (TLS) 連線，請在命令提示字元中輸入下列命令：
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        例如：
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        如果 UseDefaultCertificate 設為 False，您必須指定 TLSCertIssuer 和 TLSCertSerialNumber 參數。 這些參數指出發行靜態路由，與 TLS 憑證，序號中分別使用憑證的憑證授權單位 (CA) 的名稱。 如需有關這些參數的詳細資訊，請參閱 < Lync Server 管理命令介面說明的命令提示字元中輸入下列：
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - 若是傳輸控制通訊協定 (TCP) 連線，請在命令提示字元中輸入下列命令：
        
        <div class="">
        

        > [!NOTE]  
        > 如果您指定的完整的網域名稱 (FQDN)，您必須先設定網域名稱系統 (DNS) A 記錄。

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        例如：
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        以下是靜態路由的選擇性參數的預設值：
        
          - 啟用 = True
        
          - MatchOnlyPhoneUri = False
        
          - ReplaceHostInRequestUri = False
        
        我們強烈建議您不要變更這些預設值。 不過，如果您必須變更任何這些參數，請參閱 < Lync Server 管理命令介面說明的命令提示字元中輸入下列：
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  若要保存的中央管理存放區中的新建立靜態路由，執行下列其中一個下列項目，視：
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a>另請參閱


[設定 Lync Server 2013 中的遠端呼叫控制的信任的應用程式項目](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[Lync Server 2013 中定義 SIP/CSTA 閘道 IP 位址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

