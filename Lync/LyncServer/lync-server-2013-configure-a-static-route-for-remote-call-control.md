---
title: Lync Server 2013：設定遠端呼叫控制的靜態路由
description: Lync Server 2013：設定遠端呼叫控制的靜態路由。
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
ms.openlocfilehash: 8ecf6478d4fb7ab4f04f8a452d4837b327ba254a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551689"
---
# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a>在 Lync Server 2013 中設定遠端呼叫控制的靜態路由

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-22_

遠端呼叫控制要求將每個 Lync Server 集區都設定為從該集區的路徑，到連接至專用 exchange (PBX) 的 SIP/CSTA 閘道。 此路徑需要每個集區都有一個靜態路由，以供集區針對與 PBX 通話相關聯的每個閘道進行 proxy。 如果您為遠端呼叫控制設定全域靜態路由，則在集區層級未使用靜態路由設定的每個集區都將使用全域靜態路由。

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a>設定遠端呼叫控制的靜態路由

1.  登入安裝了 Lync Server 管理命令介面的電腦，做為 RTCUniversalServerAdmins 群組的成員或以角色為基礎的存取控制 (RBAC) 角色（已指派 **New-CsStaticRoute** Cmdlet）。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  若要建立靜態路由，並將它放在變數 $TLSRoute 或 $TCPRoute 中，請執行下列其中一項操作：
    
    <div class="">
    

    > [!TIP]  
    > 若要符合網域的子域，您可以在 MatchUri 參數中指定萬用字元值。 例如， <STRONG>contoso.net</STRONG>。 該值會符合任何以後綴 <STRONG>contoso.net</STRONG>結尾的網域。

    
    </div>
    
      - 若是傳輸層安全性 (TLS) 連線，請在命令提示字元中輸入下列命令：
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        例如：
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        如果 UseDefaultCertificate 設定為 False，您必須指定 TLSCertIssuer 和 TLSCertSerialNumber 參數。 這些參數會指出在靜態路由中所使用之憑證的憑證授權單位單位 (CA) 名稱，以及該 TLS 憑證的序號碼。 如需這些參數的詳細資訊，請在命令提示字元處輸入下列命令，以參閱 Lync Server Management Shell Help：
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - 若是傳輸控制通訊協定 (TCP) 連線，請在命令提示字元中輸入下列命令：
        
        <div class="">
        

        > [!NOTE]  
        > 如果您指定 (FQDN) 的完整功能變數名稱，必須先設定網域名稱系統 (DNS) 記錄。

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        例如：
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        下列為靜態路由的選擇性參數的預設值：
        
          - Enabled = True
        
          - MatchOnlyPhoneUri = False
        
          - ReplaceHostInRequestUri = False
        
        強烈建議您不要變更這些預設值。 不過，如果您必須變更這些參數中的任何一個，請在命令提示字元中輸入下列命令，以參閱 Lync Server Management Shell Help：
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  若要在中央管理存放區中保存新建立的靜態路由，請視需要執行下列其中一項：
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中為遠端呼叫控制設定信任的應用程式專案](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[在 Lync Server 2013 中定義 SIP/CSTA 閘道 IP 位址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

