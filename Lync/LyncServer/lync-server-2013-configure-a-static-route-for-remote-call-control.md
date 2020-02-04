---
title: Lync Server 2013：設定遠端呼叫控制的靜態路由
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
ms.openlocfilehash: dfb825e51a9beec7010f9f46ed0fc649267897fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a>在 Lync Server 2013 中設定遠端呼叫控制的靜態路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-22_

遠端呼叫控制要求每個 Lync Server 池都設定了從該資源庫的路徑到連接到私人分支 exchange （PBX）的 SIP/CSTA 閘道。 這個路徑要求每個池都有一個針對每個閘道都有一個靜態路由，每個閘道都有一個針對與 PBX 呼叫相關聯的 proxy 通訊控制訊息。 如果您設定了 [遠端通話控制] 的全域靜態路由，則每個未使用 [池] 層級的靜態路由設定的池都會使用全域靜態路由。

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a>設定遠端通話控制的靜態路由

1.  登入 Lync Server 管理命令介面已安裝為 RTCUniversalServerAdmins 群組成員的電腦，或是您已指派**新的 CsStaticRoute** Cmdlet 的角色式存取控制（RBAC）角色。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  若要建立靜態路由並將它放在 $TLSRoute 或 $TCPRoute 的變數中，請執行下列其中一項操作：
    
    <div class="">
    

    > [!TIP]  
    > 若要與網域的子域相符，您可以在 MatchUri 參數中指定一個萬用字元值。 例如， <STRONG>*. contoso.net</STRONG>。 這個值會與以後綴<STRONG>contoso.net</STRONG>結尾的任何網域相符。

    
    </div>
    
      - 針對傳輸層安全性（TLS）連線，請在命令提示字元中輸入下列內容：
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        例如：
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        如果 UseDefaultCertificate 設定為 False，您必須指定 TLSCertIssuer 和 TLSCertSerialNumber 參數。 這些參數表示頒發在靜態路由中使用之憑證的憑證授權單位（CA）名稱，以及該 TLS 憑證的序列值。 如需這些參數的詳細資訊，請在命令提示字元中輸入以下內容，以查看 Lync Server Management 命令介面說明：
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - 如果是傳輸控制通訊協定（TCP）連線，請在命令提示字元中輸入下列內容：
        
        <div class="">
        

        > [!NOTE]  
        > 如果您指定完整的功能變數名稱（FQDN），您必須先設定網域名稱系統（DNS） A 記錄。

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        例如：
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        下列是靜態路由選用參數的預設值：
        
          - Enabled = True
        
          - MatchOnlyPhoneUri = False
        
          - ReplaceHostInRequestUri = False
        
        我們強烈建議您不要變更這些預設值。 不過，如果您必須變更這些參數中的任何一個，請在命令提示字元中輸入以下內容，以查看 Lync Server 管理命令介面說明：
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  若要在中央管理儲存體中保留新建立的靜態路由，請視需要執行下列其中一項操作：
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中為遠端呼叫控制設定信任的應用程式項目](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[在 Lync Server 2013 中定義 SIP/CSTA 閘道 IP 位址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

