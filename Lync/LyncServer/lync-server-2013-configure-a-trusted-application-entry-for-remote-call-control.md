---
title: 為遠端呼叫控制設定信任的應用程式項目
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a trusted application entry for remote call control
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558636(v=OCS.15)
ms:contentKeyID: 48183829
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be0dda3eedc73e5c64f7c275714955f3ce92af3a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trusted-application-entry-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="68025-102">在 Lync Server 2013 中為遠端呼叫控制設定信任的應用程式項目</span><span class="sxs-lookup"><span data-stu-id="68025-102">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68025-103">_**主題上次修改日期：** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="68025-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="68025-104">SIP/CSTA 閘道必須設定為受信任的應用程式，Lync Server 才能套用靜態路由來路由呼叫至閘道。</span><span class="sxs-lookup"><span data-stu-id="68025-104">The SIP/CSTA gateway must be configured as a trusted application in order for Lync Server to apply a static route to route calls to the gateway.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="68025-105">如果您是從舊版的 Lync Server 部署中遷移使用者，請務必移除您在執行本主題中的程式之前，您針對 SIP/CSTA 閘道所建立的所有現有信任應用程式專案（先前稱為授權主項目目）。</span><span class="sxs-lookup"><span data-stu-id="68025-105">If you're migrating users from a previous version of Lync Server deployment, be sure that you removed all existing trusted application entries (previously known as authorized host entries) you created for the SIP/CSTA gateway before following the procedures in this topic.</span></span> <span data-ttu-id="68025-106">如需詳細資訊，請參閱<A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">在 Lync Server 2013 中移除舊版授權主機（選用）</A>。</span><span class="sxs-lookup"><span data-stu-id="68025-106">For details, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span><BR><span data-ttu-id="68025-107">如果您打算使用傳輸控制通訊協定（TCP）連線來部署新的遠端呼叫控制，您必須確認在現有信任的應用程式和池上，如果您想要針對新的受信任的應用程式使用相同的 TCP 埠，請將 [<STRONG>限制服務使用量</STRONG>] 設定在現有信任的應用程式和 pool 上。</span><span class="sxs-lookup"><span data-stu-id="68025-107">If you plan to deploy new remote call control by using a Transmission Control Protocol (TCP) connection, you need to verify that <STRONG>Limit service usage to selected IP addresses</STRONG> should be set on existing trusted applications and pools, if you want to use the same TCP port for the new trusted application.</span></span>



</div>

<div>

## <a name="to-configure-a-trusted-application-entry-for-the-sipcsta-gateway"></a><span data-ttu-id="68025-108">針對 SIP/CSTA 閘道設定受信任的應用程式專案</span><span class="sxs-lookup"><span data-stu-id="68025-108">To configure a trusted application entry for the SIP/CSTA gateway</span></span>

1.  <span data-ttu-id="68025-109">登入 Lync Server 管理命令介面已安裝為 RTCUniversalServerAdmins 群組成員的電腦，或是您已將**新的-CsTrustedApplicationPool** Cmdlet 指派給其的角色型存取控制（RBAC）角色。</span><span class="sxs-lookup"><span data-stu-id="68025-109">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsTrustedApplicationPool** cmdlet.</span></span>

2.  <span data-ttu-id="68025-110">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="68025-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="68025-111">若要建立信任的應用程式專案，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="68025-111">To create a trusted application entry, do one of the following:</span></span>
    
      - <span data-ttu-id="68025-112">針對傳輸層安全性（TLS）連線，請在命令提示字元中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="68025-112">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        <span data-ttu-id="68025-113">例如：</span><span class="sxs-lookup"><span data-stu-id="68025-113">For example:</span></span>
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - <span data-ttu-id="68025-114">如果是傳輸控制通訊協定（TCP）連線，請在命令提示字元中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="68025-114">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        <span data-ttu-id="68025-115">例如：</span><span class="sxs-lookup"><span data-stu-id="68025-115">For example:</span></span>
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  <span data-ttu-id="68025-116">若要將信任的應用程式新增至該資源庫，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="68025-116">To add the trusted application to the pool, do one of the following:</span></span>
    
      - <span data-ttu-id="68025-117">針對 TLS 連線，請在命令提示字元中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="68025-117">For a TLS connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        <span data-ttu-id="68025-118">例如：</span><span class="sxs-lookup"><span data-stu-id="68025-118">For example:</span></span>
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - <span data-ttu-id="68025-119">針對 TCP 連線，請在命令提示字元中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="68025-119">For a TCP connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        <span data-ttu-id="68025-120">例如：</span><span class="sxs-lookup"><span data-stu-id="68025-120">For example:</span></span>
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  <span data-ttu-id="68025-121">若要執行您對拓撲所做的已發佈變更，請在命令提示字元輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="68025-121">To implement the published changes you have made to the topology, type the following at the command prompt:</span></span>
    
        Enable-CsTopology

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="68025-122">請參閱</span><span class="sxs-lookup"><span data-stu-id="68025-122">See Also</span></span>


[<span data-ttu-id="68025-123">在 Lync Server 2013 中設定遠端呼叫控制的靜態路由</span><span class="sxs-lookup"><span data-stu-id="68025-123">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="68025-124">在 Lync Server 2013 中定義 SIP/CSTA 閘道 IP 位址</span><span class="sxs-lookup"><span data-stu-id="68025-124">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

