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
ms.openlocfilehash: 0f8175a351d13675c048efce7a2f831af7ab2c31
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523060"
---
# <a name="configure-a-trusted-application-entry-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="21739-102">在 Lync Server 2013 中為遠端呼叫控制設定信任的應用程式專案</span><span class="sxs-lookup"><span data-stu-id="21739-102">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21739-103">_**主題上次修改日期：** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="21739-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="21739-104">SIP/CSTA 閘道必須設定為信任的應用程式，Lync 伺服器才能套用靜態路由，將通話路由傳送至閘道。</span><span class="sxs-lookup"><span data-stu-id="21739-104">The SIP/CSTA gateway must be configured as a trusted application in order for Lync Server to apply a static route to route calls to the gateway.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="21739-105">如果您要從舊版的 Lync Server 部署遷移使用者，請確定您已移除所有現有的受信任應用程式專案 (先前稱為已授權的主項目目) 您在執行本主題中的程式之前，您已為 SIP/CSTA 閘道建立。</span><span class="sxs-lookup"><span data-stu-id="21739-105">If you're migrating users from a previous version of Lync Server deployment, be sure that you removed all existing trusted application entries (previously known as authorized host entries) you created for the SIP/CSTA gateway before following the procedures in this topic.</span></span> <span data-ttu-id="21739-106">如需詳細資訊，請參閱 <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a 舊版授權主機 In Lync Server 2013 (選用) </A>。</span><span class="sxs-lookup"><span data-stu-id="21739-106">For details, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span><BR><span data-ttu-id="21739-107">如果您打算使用傳輸控制通訊協定 (TCP) 連線來部署新的遠端呼叫控制，您必須在現有信任的應用程式和集區上，確認必須在現有信任的應用程式和集區上設定 [ <STRONG>限制服務使用方式</STRONG> ]，如果您想要對新的受信任應用程式使用相同的 TCP 通訊埠。</span><span class="sxs-lookup"><span data-stu-id="21739-107">If you plan to deploy new remote call control by using a Transmission Control Protocol (TCP) connection, you need to verify that <STRONG>Limit service usage to selected IP addresses</STRONG> should be set on existing trusted applications and pools, if you want to use the same TCP port for the new trusted application.</span></span>



</div>

<div>

## <a name="to-configure-a-trusted-application-entry-for-the-sipcsta-gateway"></a><span data-ttu-id="21739-108">若要設定 SIP/CSTA 閘道的受信任應用程式項目</span><span class="sxs-lookup"><span data-stu-id="21739-108">To configure a trusted application entry for the SIP/CSTA gateway</span></span>

1.  <span data-ttu-id="21739-109">登入安裝了 Lync Server 管理命令介面的電腦，做為 RTCUniversalServerAdmins 群組的成員或以角色為基礎的存取控制 (RBAC) 角色（已指派 **New-CsTrustedApplicationPool** Cmdlet）。</span><span class="sxs-lookup"><span data-stu-id="21739-109">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsTrustedApplicationPool** cmdlet.</span></span>

2.  <span data-ttu-id="21739-110">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="21739-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="21739-111">若要建立受信任應用程式項目，請執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="21739-111">To create a trusted application entry, do one of the following:</span></span>
    
      - <span data-ttu-id="21739-112">若是傳輸層安全性 (TLS) 連線，請在命令提示字元中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="21739-112">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        <span data-ttu-id="21739-113">例如：</span><span class="sxs-lookup"><span data-stu-id="21739-113">For example:</span></span>
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - <span data-ttu-id="21739-114">若是傳輸控制通訊協定 (TCP) 連線，請在命令提示字元中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="21739-114">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        <span data-ttu-id="21739-115">例如：</span><span class="sxs-lookup"><span data-stu-id="21739-115">For example:</span></span>
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  <span data-ttu-id="21739-116">若要將受信任應用程式新增至集區，請執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="21739-116">To add the trusted application to the pool, do one of the following:</span></span>
    
      - <span data-ttu-id="21739-117">若是 TLS 連線，請在命令提示字元中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="21739-117">For a TLS connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        <span data-ttu-id="21739-118">例如：</span><span class="sxs-lookup"><span data-stu-id="21739-118">For example:</span></span>
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - <span data-ttu-id="21739-119">若是 TCP 連線，請在命令提示字元中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="21739-119">For a TCP connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        <span data-ttu-id="21739-120">例如：</span><span class="sxs-lookup"><span data-stu-id="21739-120">For example:</span></span>
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  <span data-ttu-id="21739-121">若要實作您已發行的拓撲變更，請在命令提示字元中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="21739-121">To implement the published changes you have made to the topology, type the following at the command prompt:</span></span>
    
        Enable-CsTopology

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="21739-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="21739-122">See Also</span></span>


[<span data-ttu-id="21739-123">在 Lync Server 2013 中設定遠端呼叫控制的靜態路由</span><span class="sxs-lookup"><span data-stu-id="21739-123">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="21739-124">在 Lync Server 2013 中定義 SIP/CSTA 閘道 IP 位址</span><span class="sxs-lookup"><span data-stu-id="21739-124">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

