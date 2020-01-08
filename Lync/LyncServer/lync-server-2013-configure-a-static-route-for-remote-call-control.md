---
title: Lync Server 2013：設定遠端呼叫控制的靜態路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a11b24fc8d4be54f5645853c050891d3821945e4
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40982633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="8e80c-102">在 Lync Server 2013 中設定遠端呼叫控制的靜態路由</span><span class="sxs-lookup"><span data-stu-id="8e80c-102">Configure a static route for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e80c-103">_**主題上次修改日期：** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="8e80c-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="8e80c-104">遠端呼叫控制要求每個 Lync Server 池都設定了從該資源庫的路徑到連接到私人分支 exchange （PBX）的 SIP/CSTA 閘道。</span><span class="sxs-lookup"><span data-stu-id="8e80c-104">Remote call control requires that every Lync Server pool is configured with a path from that pool to the SIP/CSTA gateway that connects to the private branch exchange (PBX).</span></span> <span data-ttu-id="8e80c-105">這個路徑要求每個池都有一個針對每個閘道都有一個靜態路由，每個閘道都有一個針對與 PBX 呼叫相關聯的 proxy 通訊控制訊息。</span><span class="sxs-lookup"><span data-stu-id="8e80c-105">This path requires that each pool has one static route for each gateway to which the pool will proxy SIP call control messages associated with calls to the PBX.</span></span> <span data-ttu-id="8e80c-106">如果您設定了 [遠端通話控制] 的全域靜態路由，則每個未使用 [池] 層級的靜態路由設定的池都會使用全域靜態路由。</span><span class="sxs-lookup"><span data-stu-id="8e80c-106">If you configure a global static route for remote call control, each pool that is not configured with a static route at the pool level will use the global static route.</span></span>

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a><span data-ttu-id="8e80c-107">設定遠端通話控制的靜態路由</span><span class="sxs-lookup"><span data-stu-id="8e80c-107">To configure a static route for remote call control</span></span>

1.  <span data-ttu-id="8e80c-108">登入 Lync Server 管理命令介面已安裝為 RTCUniversalServerAdmins 群組成員的電腦，或是您已指派**新的 CsStaticRoute** Cmdlet 的角色式存取控制（RBAC）角色。</span><span class="sxs-lookup"><span data-stu-id="8e80c-108">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsStaticRoute** cmdlet.</span></span>

2.  <span data-ttu-id="8e80c-109">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="8e80c-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="8e80c-110">若要建立靜態路由並將它放在 $TLSRoute 或 $TCPRoute 的變數中，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="8e80c-110">To create a static route and put it in the variable $TLSRoute or $TCPRoute, do one of the following:</span></span>
    
    <div class="">
    

    > [!TIP]  
    > <span data-ttu-id="8e80c-111">若要與網域的子域相符，您可以在 MatchUri 參數中指定一個萬用字元值。</span><span class="sxs-lookup"><span data-stu-id="8e80c-111">To match child domains of a domain, you can specify a wildcard value in the MatchUri parameter.</span></span> <span data-ttu-id="8e80c-112">例如， <STRONG>\*. contoso.net</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="8e80c-112">For example, <STRONG>\*.contoso.net</STRONG>.</span></span> <span data-ttu-id="8e80c-113">這個值會與以後綴<STRONG>contoso.net</STRONG>結尾的任何網域相符。</span><span class="sxs-lookup"><span data-stu-id="8e80c-113">That value matches any domain that ends with the suffix <STRONG>contoso.net</STRONG>.</span></span>

    
    </div>
    
      - <span data-ttu-id="8e80c-114">針對傳輸層安全性（TLS）連線，請在命令提示字元中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="8e80c-114">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        <span data-ttu-id="8e80c-115">例如：</span><span class="sxs-lookup"><span data-stu-id="8e80c-115">For example:</span></span>
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        <span data-ttu-id="8e80c-116">如果 UseDefaultCertificate 設定為 False，您必須指定 TLSCertIssuer 和 TLSCertSerialNumber 參數。</span><span class="sxs-lookup"><span data-stu-id="8e80c-116">If UseDefaultCertificate is set to False, you must specify TLSCertIssuer and TLSCertSerialNumber parameters.</span></span> <span data-ttu-id="8e80c-117">這些參數表示頒發在靜態路由中使用之憑證的憑證授權單位（CA）名稱，以及該 TLS 憑證的序列值。</span><span class="sxs-lookup"><span data-stu-id="8e80c-117">These parameters indicate the name of the certification authority (CA) that issued the certificate used in the static route, and the serial number of that TLS certificate, respectively.</span></span> <span data-ttu-id="8e80c-118">如需這些參數的詳細資訊，請在命令提示字元中輸入以下內容，以查看 Lync Server Management 命令介面說明：</span><span class="sxs-lookup"><span data-stu-id="8e80c-118">For details about these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - <span data-ttu-id="8e80c-119">如果是傳輸控制通訊協定（TCP）連線，請在命令提示字元中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="8e80c-119">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
        <div class="">
        

        > [!NOTE]  
        > <span data-ttu-id="8e80c-120">如果您指定完整的功能變數名稱（FQDN），您必須先設定網域名稱系統（DNS） A 記錄。</span><span class="sxs-lookup"><span data-stu-id="8e80c-120">If you specify a fully qualified domain name (FQDN), you must configure a Domain Name System (DNS) A record first.</span></span>

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        <span data-ttu-id="8e80c-121">例如：</span><span class="sxs-lookup"><span data-stu-id="8e80c-121">For example:</span></span>
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        <span data-ttu-id="8e80c-122">下列是靜態路由選用參數的預設值：</span><span class="sxs-lookup"><span data-stu-id="8e80c-122">The following are default values for optional parameters for static routes:</span></span>
        
          - <span data-ttu-id="8e80c-123">Enabled = True</span><span class="sxs-lookup"><span data-stu-id="8e80c-123">Enabled = True</span></span>
        
          - <span data-ttu-id="8e80c-124">MatchOnlyPhoneUri = False</span><span class="sxs-lookup"><span data-stu-id="8e80c-124">MatchOnlyPhoneUri = False</span></span>
        
          - <span data-ttu-id="8e80c-125">ReplaceHostInRequestUri = False</span><span class="sxs-lookup"><span data-stu-id="8e80c-125">ReplaceHostInRequestUri = False</span></span>
        
        <span data-ttu-id="8e80c-126">我們強烈建議您不要變更這些預設值。</span><span class="sxs-lookup"><span data-stu-id="8e80c-126">We strongly recommend that you do not change these default values.</span></span> <span data-ttu-id="8e80c-127">不過，如果您必須變更這些參數中的任何一個，請在命令提示字元中輸入以下內容，以查看 Lync Server 管理命令介面說明：</span><span class="sxs-lookup"><span data-stu-id="8e80c-127">However, if you must change any of these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  <span data-ttu-id="8e80c-128">若要在中央管理儲存體中保留新建立的靜態路由，請視需要執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="8e80c-128">To persist a newly created static route in the Central Management store, run one of the following, as appropriate:</span></span>
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8e80c-129">請參閱</span><span class="sxs-lookup"><span data-stu-id="8e80c-129">See Also</span></span>


[<span data-ttu-id="8e80c-130">在 Lync Server 2013 中為遠端呼叫控制設定信任的應用程式項目</span><span class="sxs-lookup"><span data-stu-id="8e80c-130">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[<span data-ttu-id="8e80c-131">在 Lync Server 2013 中定義 SIP/CSTA 閘道 IP 位址</span><span class="sxs-lookup"><span data-stu-id="8e80c-131">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

