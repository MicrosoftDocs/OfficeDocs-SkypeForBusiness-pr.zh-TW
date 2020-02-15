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
ms.openlocfilehash: 535574a47a9ea77b5db20e45dcdcbb62fab2e4b9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048126"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="0c3ad-102">在 Lync Server 2013 中設定為遠端呼叫控制的靜態路由</span><span class="sxs-lookup"><span data-stu-id="0c3ad-102">Configure a static route for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c3ad-103">_**主題上次修改日期：** 2012年-09-22_</span><span class="sxs-lookup"><span data-stu-id="0c3ad-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="0c3ad-104">遠端呼叫控制需要每個 Lync 伺服器集區都設有連接至專用交換機 (PBX) 的 SIP/CSTA 閘道從該集區的路徑。</span><span class="sxs-lookup"><span data-stu-id="0c3ad-104">Remote call control requires that every Lync Server pool is configured with a path from that pool to the SIP/CSTA gateway that connects to the private branch exchange (PBX).</span></span> <span data-ttu-id="0c3ad-105">此路徑需要每個集區有一個靜態路由集區將 proxy SIP 呼叫控制項郵件到 PBX 的通話相關聯的每個閘道。</span><span class="sxs-lookup"><span data-stu-id="0c3ad-105">This path requires that each pool has one static route for each gateway to which the pool will proxy SIP call control messages associated with calls to the PBX.</span></span> <span data-ttu-id="0c3ad-106">如果您設定為遠端呼叫控制的全域靜態路由，並未設定靜態路由集區層級與每個集區會使用全域靜態路由。</span><span class="sxs-lookup"><span data-stu-id="0c3ad-106">If you configure a global static route for remote call control, each pool that is not configured with a static route at the pool level will use the global static route.</span></span>

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a><span data-ttu-id="0c3ad-107">若要設定為遠端呼叫控制的靜態路由</span><span class="sxs-lookup"><span data-stu-id="0c3ad-107">To configure a static route for remote call control</span></span>

1.  <span data-ttu-id="0c3ad-108">登入 Lync Server 管理命令介面以 RTCUniversalServerAdmins 群組或您已對其指派**New-csstaticroute** cmdlet 的角色型存取控制 (RBAC) 角色的成員身分的安裝所在的電腦。</span><span class="sxs-lookup"><span data-stu-id="0c3ad-108">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsStaticRoute** cmdlet.</span></span>

2.  <span data-ttu-id="0c3ad-109">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="0c3ad-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0c3ad-110">若要建立靜態路由，並將它放在變數 $TLSRoute 或 $TCPRoute，執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="0c3ad-110">To create a static route and put it in the variable $TLSRoute or $TCPRoute, do one of the following:</span></span>
    
    <div class="">
    

    > [!TIP]  
    > <span data-ttu-id="0c3ad-111">若要相符子網域的網域，您可以指定萬用字元值，在 MatchUri 參數中。</span><span class="sxs-lookup"><span data-stu-id="0c3ad-111">To match child domains of a domain, you can specify a wildcard value in the MatchUri parameter.</span></span> <span data-ttu-id="0c3ad-112">例如， <STRONG>\*。 contoso.net</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="0c3ad-112">For example, <STRONG>\*.contoso.net</STRONG>.</span></span> <span data-ttu-id="0c3ad-113">該值比對任何與後置詞<STRONG>contoso.net</STRONG>結束的網域。</span><span class="sxs-lookup"><span data-stu-id="0c3ad-113">That value matches any domain that ends with the suffix <STRONG>contoso.net</STRONG>.</span></span>

    
    </div>
    
      - <span data-ttu-id="0c3ad-114">若是傳輸層安全性 (TLS) 連線，請在命令提示字元中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="0c3ad-114">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        <span data-ttu-id="0c3ad-115">例如：</span><span class="sxs-lookup"><span data-stu-id="0c3ad-115">For example:</span></span>
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        <span data-ttu-id="0c3ad-116">如果 UseDefaultCertificate 設為 False，您必須指定 TLSCertIssuer 和 TLSCertSerialNumber 參數。</span><span class="sxs-lookup"><span data-stu-id="0c3ad-116">If UseDefaultCertificate is set to False, you must specify TLSCertIssuer and TLSCertSerialNumber parameters.</span></span> <span data-ttu-id="0c3ad-117">這些參數指出發行靜態路由，與 TLS 憑證，序號中分別使用憑證的憑證授權單位 (CA) 的名稱。</span><span class="sxs-lookup"><span data-stu-id="0c3ad-117">These parameters indicate the name of the certification authority (CA) that issued the certificate used in the static route, and the serial number of that TLS certificate, respectively.</span></span> <span data-ttu-id="0c3ad-118">如需有關這些參數的詳細資訊，請參閱 < Lync Server 管理命令介面說明的命令提示字元中輸入下列：</span><span class="sxs-lookup"><span data-stu-id="0c3ad-118">For details about these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - <span data-ttu-id="0c3ad-119">若是傳輸控制通訊協定 (TCP) 連線，請在命令提示字元中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="0c3ad-119">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
        <div class="">
        

        > [!NOTE]  
        > <span data-ttu-id="0c3ad-120">如果您指定的完整的網域名稱 (FQDN)，您必須先設定網域名稱系統 (DNS) A 記錄。</span><span class="sxs-lookup"><span data-stu-id="0c3ad-120">If you specify a fully qualified domain name (FQDN), you must configure a Domain Name System (DNS) A record first.</span></span>

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        <span data-ttu-id="0c3ad-121">例如：</span><span class="sxs-lookup"><span data-stu-id="0c3ad-121">For example:</span></span>
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        <span data-ttu-id="0c3ad-122">以下是靜態路由的選擇性參數的預設值：</span><span class="sxs-lookup"><span data-stu-id="0c3ad-122">The following are default values for optional parameters for static routes:</span></span>
        
          - <span data-ttu-id="0c3ad-123">啟用 = True</span><span class="sxs-lookup"><span data-stu-id="0c3ad-123">Enabled = True</span></span>
        
          - <span data-ttu-id="0c3ad-124">MatchOnlyPhoneUri = False</span><span class="sxs-lookup"><span data-stu-id="0c3ad-124">MatchOnlyPhoneUri = False</span></span>
        
          - <span data-ttu-id="0c3ad-125">ReplaceHostInRequestUri = False</span><span class="sxs-lookup"><span data-stu-id="0c3ad-125">ReplaceHostInRequestUri = False</span></span>
        
        <span data-ttu-id="0c3ad-126">我們強烈建議您不要變更這些預設值。</span><span class="sxs-lookup"><span data-stu-id="0c3ad-126">We strongly recommend that you do not change these default values.</span></span> <span data-ttu-id="0c3ad-127">不過，如果您必須變更任何這些參數，請參閱 < Lync Server 管理命令介面說明的命令提示字元中輸入下列：</span><span class="sxs-lookup"><span data-stu-id="0c3ad-127">However, if you must change any of these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  <span data-ttu-id="0c3ad-128">若要保存的中央管理存放區中的新建立靜態路由，執行下列其中一個下列項目，視：</span><span class="sxs-lookup"><span data-stu-id="0c3ad-128">To persist a newly created static route in the Central Management store, run one of the following, as appropriate:</span></span>
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0c3ad-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0c3ad-129">See Also</span></span>


[<span data-ttu-id="0c3ad-130">設定 Lync Server 2013 中的遠端呼叫控制的信任的應用程式項目</span><span class="sxs-lookup"><span data-stu-id="0c3ad-130">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[<span data-ttu-id="0c3ad-131">Lync Server 2013 中定義 SIP/CSTA 閘道 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0c3ad-131">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

