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
# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="7aacc-103">在 Lync Server 2013 中設定遠端呼叫控制的靜態路由</span><span class="sxs-lookup"><span data-stu-id="7aacc-103">Configure a static route for remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7aacc-104">_**主題上次修改日期：** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="7aacc-104">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="7aacc-105">遠端呼叫控制要求將每個 Lync Server 集區都設定為從該集區的路徑，到連接至專用 exchange (PBX) 的 SIP/CSTA 閘道。</span><span class="sxs-lookup"><span data-stu-id="7aacc-105">Remote call control requires that every Lync Server pool is configured with a path from that pool to the SIP/CSTA gateway that connects to the private branch exchange (PBX).</span></span> <span data-ttu-id="7aacc-106">此路徑需要每個集區都有一個靜態路由，以供集區針對與 PBX 通話相關聯的每個閘道進行 proxy。</span><span class="sxs-lookup"><span data-stu-id="7aacc-106">This path requires that each pool has one static route for each gateway to which the pool will proxy SIP call control messages associated with calls to the PBX.</span></span> <span data-ttu-id="7aacc-107">如果您為遠端呼叫控制設定全域靜態路由，則在集區層級未使用靜態路由設定的每個集區都將使用全域靜態路由。</span><span class="sxs-lookup"><span data-stu-id="7aacc-107">If you configure a global static route for remote call control, each pool that is not configured with a static route at the pool level will use the global static route.</span></span>

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a><span data-ttu-id="7aacc-108">設定遠端呼叫控制的靜態路由</span><span class="sxs-lookup"><span data-stu-id="7aacc-108">To configure a static route for remote call control</span></span>

1.  <span data-ttu-id="7aacc-109">登入安裝了 Lync Server 管理命令介面的電腦，做為 RTCUniversalServerAdmins 群組的成員或以角色為基礎的存取控制 (RBAC) 角色（已指派 **New-CsStaticRoute** Cmdlet）。</span><span class="sxs-lookup"><span data-stu-id="7aacc-109">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsStaticRoute** cmdlet.</span></span>

2.  <span data-ttu-id="7aacc-110">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="7aacc-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7aacc-111">若要建立靜態路由，並將它放在變數 $TLSRoute 或 $TCPRoute 中，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="7aacc-111">To create a static route and put it in the variable $TLSRoute or $TCPRoute, do one of the following:</span></span>
    
    <div class="">
    

    > [!TIP]  
    > <span data-ttu-id="7aacc-112">若要符合網域的子域，您可以在 MatchUri 參數中指定萬用字元值。</span><span class="sxs-lookup"><span data-stu-id="7aacc-112">To match child domains of a domain, you can specify a wildcard value in the MatchUri parameter.</span></span> <span data-ttu-id="7aacc-113">例如， <STRONG>contoso.net</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="7aacc-113">For example, <STRONG>\*.contoso.net</STRONG>.</span></span> <span data-ttu-id="7aacc-114">該值會符合任何以後綴 <STRONG>contoso.net</STRONG>結尾的網域。</span><span class="sxs-lookup"><span data-stu-id="7aacc-114">That value matches any domain that ends with the suffix <STRONG>contoso.net</STRONG>.</span></span>

    
    </div>
    
      - <span data-ttu-id="7aacc-115">若是傳輸層安全性 (TLS) 連線，請在命令提示字元中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="7aacc-115">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        <span data-ttu-id="7aacc-116">例如：</span><span class="sxs-lookup"><span data-stu-id="7aacc-116">For example:</span></span>
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        <span data-ttu-id="7aacc-117">如果 UseDefaultCertificate 設定為 False，您必須指定 TLSCertIssuer 和 TLSCertSerialNumber 參數。</span><span class="sxs-lookup"><span data-stu-id="7aacc-117">If UseDefaultCertificate is set to False, you must specify TLSCertIssuer and TLSCertSerialNumber parameters.</span></span> <span data-ttu-id="7aacc-118">這些參數會指出在靜態路由中所使用之憑證的憑證授權單位單位 (CA) 名稱，以及該 TLS 憑證的序號碼。</span><span class="sxs-lookup"><span data-stu-id="7aacc-118">These parameters indicate the name of the certification authority (CA) that issued the certificate used in the static route, and the serial number of that TLS certificate, respectively.</span></span> <span data-ttu-id="7aacc-119">如需這些參數的詳細資訊，請在命令提示字元處輸入下列命令，以參閱 Lync Server Management Shell Help：</span><span class="sxs-lookup"><span data-stu-id="7aacc-119">For details about these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - <span data-ttu-id="7aacc-120">若是傳輸控制通訊協定 (TCP) 連線，請在命令提示字元中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="7aacc-120">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
        <div class="">
        

        > [!NOTE]  
        > <span data-ttu-id="7aacc-121">如果您指定 (FQDN) 的完整功能變數名稱，必須先設定網域名稱系統 (DNS) 記錄。</span><span class="sxs-lookup"><span data-stu-id="7aacc-121">If you specify a fully qualified domain name (FQDN), you must configure a Domain Name System (DNS) A record first.</span></span>

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        <span data-ttu-id="7aacc-122">例如：</span><span class="sxs-lookup"><span data-stu-id="7aacc-122">For example:</span></span>
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        <span data-ttu-id="7aacc-123">下列為靜態路由的選擇性參數的預設值：</span><span class="sxs-lookup"><span data-stu-id="7aacc-123">The following are default values for optional parameters for static routes:</span></span>
        
          - <span data-ttu-id="7aacc-124">Enabled = True</span><span class="sxs-lookup"><span data-stu-id="7aacc-124">Enabled = True</span></span>
        
          - <span data-ttu-id="7aacc-125">MatchOnlyPhoneUri = False</span><span class="sxs-lookup"><span data-stu-id="7aacc-125">MatchOnlyPhoneUri = False</span></span>
        
          - <span data-ttu-id="7aacc-126">ReplaceHostInRequestUri = False</span><span class="sxs-lookup"><span data-stu-id="7aacc-126">ReplaceHostInRequestUri = False</span></span>
        
        <span data-ttu-id="7aacc-127">強烈建議您不要變更這些預設值。</span><span class="sxs-lookup"><span data-stu-id="7aacc-127">We strongly recommend that you do not change these default values.</span></span> <span data-ttu-id="7aacc-128">不過，如果您必須變更這些參數中的任何一個，請在命令提示字元中輸入下列命令，以參閱 Lync Server Management Shell Help：</span><span class="sxs-lookup"><span data-stu-id="7aacc-128">However, if you must change any of these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  <span data-ttu-id="7aacc-129">若要在中央管理存放區中保存新建立的靜態路由，請視需要執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="7aacc-129">To persist a newly created static route in the Central Management store, run one of the following, as appropriate:</span></span>
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7aacc-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7aacc-130">See Also</span></span>


[<span data-ttu-id="7aacc-131">在 Lync Server 2013 中為遠端呼叫控制設定信任的應用程式專案</span><span class="sxs-lookup"><span data-stu-id="7aacc-131">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[<span data-ttu-id="7aacc-132">在 Lync Server 2013 中定義 SIP/CSTA 閘道 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7aacc-132">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

