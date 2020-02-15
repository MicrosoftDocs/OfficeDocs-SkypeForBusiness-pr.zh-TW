---
title: Lync Server 2013： 靜態路由 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Static routing cmdlets
ms:assetid: 71d5e0cd-8412-4383-818a-95b851a4da4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416492(v=OCS.15)
ms:contentKeyID: 48184496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9e5b67153d353c0b08ba33853c76d16cd8ba3f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="static-routing-cmdlets-in-lync-server-2013"></a><span data-ttu-id="eba62-102">Lync Server 2013 中的靜態路由 cmdlet</span><span class="sxs-lookup"><span data-stu-id="eba62-102">Static routing cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eba62-103">_**主題上次修改日期：** 2012年-06-20 個_</span><span class="sxs-lookup"><span data-stu-id="eba62-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="eba62-104">靜態路由，以系統管理員可以預定 SIP 訊息所採取的網路路由。</span><span class="sxs-lookup"><span data-stu-id="eba62-104">With static routes, administrators can predetermine the network routes taken by SIP messages.</span></span> <span data-ttu-id="eba62-105">當伺服器收到郵件時，伺服器會檢查郵件地址，然後再將轉寄要由系統管理員預先設定的下一個躍點伺服器的郵件。</span><span class="sxs-lookup"><span data-stu-id="eba62-105">When a message is received by a server, the server checks the message address and then forwards the message to the next hop server preconfigured by an administrator.</span></span> <span data-ttu-id="eba62-106">如果設定正確，靜態路由有助於確保訊息即時且準確送達，而且可將伺服器竊聽減到最少。</span><span class="sxs-lookup"><span data-stu-id="eba62-106">If configured correctly, static routes help ensure timely, and accurate, delivery of messages, and with minimal overheard placed on servers.</span></span>

<div>

## <a name="static-routing-cmdlets"></a><span data-ttu-id="eba62-107">靜態路由 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="eba62-107">Static Routing Cmdlets</span></span>

<span data-ttu-id="eba62-108">除非另有指示由 Microsoft 支援人員，應該使用[New-csstaticroute](https://technet.microsoft.com/library/Gg398265(v=OCS.15)) cmdlet 建立靜態路由設定 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="eba62-108">Unless otherwise instructed by Microsoft support personnel, static routes configured for Microsoft Lync Server 2013 should be created using the [New-CsStaticRoute](https://technet.microsoft.com/library/Gg398265(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="eba62-109">在建立路由之後，您接著 cmdlet 可用於 New-csstaticroutingconfiguration 將該路由新增至靜態路由集合。</span><span class="sxs-lookup"><span data-stu-id="eba62-109">After a route has been created, you can then use the CsStaticRoutingConfiguration cmdlets to add that route to a static routing collection.</span></span>

<span data-ttu-id="eba62-110">**靜態路由**</span><span class="sxs-lookup"><span data-stu-id="eba62-110">**Static Routing**</span></span>

  - <span></span>  
    <span data-ttu-id="eba62-111">[Get-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg398130(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eba62-111">[Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg398130(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="eba62-112">[New-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg413041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eba62-112">[New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg413041(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="eba62-113">[Remove-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg412932(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eba62-113">[Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg412932(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="eba62-114">[Set-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg425895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eba62-114">[Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg425895(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="eba62-115">[New-csstaticroute](https://technet.microsoft.com/library/Gg398265(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eba62-115">[New-CsStaticRoute](https://technet.microsoft.com/library/Gg398265(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="eba62-116">[Get-csstaticroutingconfiguration](https://technet.microsoft.com/library/Gg398754(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eba62-116">[Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398754(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="eba62-117">[New-csstaticroutingconfiguration](https://technet.microsoft.com/library/Gg425811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eba62-117">[New-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg425811(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="eba62-118">[移除 New-csstaticroutingconfiguration](https://technet.microsoft.com/library/Gg398668(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eba62-118">[Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398668(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="eba62-119">[Set-csstaticroutingconfiguration](https://technet.microsoft.com/library/Gg398724(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eba62-119">[Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398724(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="eba62-120">[New-cssipproxycustom](https://technet.microsoft.com/library/Gg425904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eba62-120">[New-CsSipProxyCustom](https://technet.microsoft.com/library/Gg425904(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="eba62-121">[New-cssipproxyrealm](https://technet.microsoft.com/library/Gg413084(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eba62-121">[New-CsSipProxyRealm](https://technet.microsoft.com/library/Gg413084(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="eba62-122">[New-cssipproxytcp](https://technet.microsoft.com/library/Gg425745(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eba62-122">[New-CsSipProxyTCP](https://technet.microsoft.com/library/Gg425745(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="eba62-123">[New-cssipproxytls](https://technet.microsoft.com/library/Gg398629(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eba62-123">[New-CsSipProxyTLS](https://technet.microsoft.com/library/Gg398629(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="eba62-124">[New-cssipproxytransport](https://technet.microsoft.com/library/Gg398489(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eba62-124">[New-CsSipProxyTransport](https://technet.microsoft.com/library/Gg398489(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="eba62-125">[New-cssipproxyusedefault](https://technet.microsoft.com/library/Gg398274(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eba62-125">[New-CsSipProxyUseDefault](https://technet.microsoft.com/library/Gg398274(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="eba62-126">[New-cssipproxyusedefaultcert](https://technet.microsoft.com/library/Gg425858(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eba62-126">[New-CsSipProxyUseDefaultCert](https://technet.microsoft.com/library/Gg425858(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="eba62-127">[New-csissuedcertid](https://technet.microsoft.com/library/Gg425814(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="eba62-127">[New-CsIssuedCertId](https://technet.microsoft.com/library/Gg425814(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eba62-128">另請參閱</span><span class="sxs-lookup"><span data-stu-id="eba62-128">See Also</span></span>


[<span data-ttu-id="eba62-129">Lync Server PowerShell 部落格</span><span class="sxs-lookup"><span data-stu-id="eba62-129">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

