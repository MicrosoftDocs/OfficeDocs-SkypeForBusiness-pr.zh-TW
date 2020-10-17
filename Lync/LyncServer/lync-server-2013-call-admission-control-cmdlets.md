---
title: Lync Server 2013：通話許可控制 Cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control cmdlets
ms:assetid: dd9d3912-b562-4839-a337-bfc5277cfb62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415676(v=OCS.15)
ms:contentKeyID: 48185602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e73869b70a571ca49026954f84d1111d57ddfbf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537250"
---
# <a name="call-admission-control-cmdlets-in-lync-server-2013"></a><span data-ttu-id="38efc-102">Lync Server 2013 中的通話許可控制 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="38efc-102">Call admission control cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38efc-103">_**主題上次修改日期：** 2012-03-21_</span><span class="sxs-lookup"><span data-stu-id="38efc-103">_**Topic Last Modified:** 2012-03-21_</span></span>

<span data-ttu-id="38efc-104">通話許可控制 (CAC) 會判斷是否有足夠的網路頻寬，可為可接受的品質建立即時音訊或影片會話。</span><span class="sxs-lookup"><span data-stu-id="38efc-104">Call admission control (CAC) determines whether there is sufficient network bandwidth to establish a real-time audio or video session of acceptable quality.</span></span> <span data-ttu-id="38efc-105">您可以 configuraing 網路、網站和子網的限制與設定，以及它們之間的互動來管理 CAC。</span><span class="sxs-lookup"><span data-stu-id="38efc-105">You manage CAC by configuraing limitations and settings for networks, sites, and subnets and the interactions between them.</span></span>

<div>

## <a name="call-admission-control-cmdlets"></a><span data-ttu-id="38efc-106">Call Admission Control Cmdlets</span><span class="sxs-lookup"><span data-stu-id="38efc-106">Call Admission Control Cmdlets</span></span>

<span data-ttu-id="38efc-107">使用下列 Cmdlet 來管理 Lync Server 管理命令介面的 CAC。</span><span class="sxs-lookup"><span data-stu-id="38efc-107">Use the following cmdlets to manage CAC from the Lync Server Management Shell.</span></span>

<span data-ttu-id="38efc-108">**通話許可控制**</span><span class="sxs-lookup"><span data-stu-id="38efc-108">**Call Admission Control**</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-109">[CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412727(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-109">[Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412727(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-110">[新 CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398175(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-110">[New-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398175(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-111">[Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398877(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-111">[Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398877(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-112">[CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412863(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-112">[Set-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412863(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="38efc-113">[Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg425815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-113">[Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg425815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-114">[New-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398675(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-114">[New-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398675(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-115">[Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398609(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-115">[Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398609(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-116">[Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398338(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-116">[Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398338(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="38efc-117">[新 CsNetworkBWAlternatePath](https://technet.microsoft.com/library/Gg398732(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-117">[New-CsNetworkBWAlternatePath](https://technet.microsoft.com/library/Gg398732(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="38efc-118">[New-CsNetworkBWPolicy](https://technet.microsoft.com/library/Gg412916(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-118">[New-CsNetworkBWPolicy](https://technet.microsoft.com/library/Gg412916(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="38efc-119">[Get-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-119">[Get-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398140(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-120">[Remove-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-120">[Remove-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398938(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-121">[CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-121">[Set-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398927(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="38efc-122">[Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg425817(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-122">[Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg425817(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-123">[新 CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398779(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-123">[New-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398779(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-124">[Remove-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398743(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-124">[Remove-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398743(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-125">[CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398410(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-125">[Set-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398410(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="38efc-126">[Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg412769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-126">[Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg412769(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-127">[新 CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398994(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-127">[New-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398994(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-128">[Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398963(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-128">[Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398963(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-129">[Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-129">[Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398772(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="38efc-130">[Get-CsNetworkRegion](https://technet.microsoft.com/library/Gg398406(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-130">[Get-CsNetworkRegion](https://technet.microsoft.com/library/Gg398406(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-131">[New-CsNetworkRegion](https://technet.microsoft.com/library/Gg425829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-131">[New-CsNetworkRegion](https://technet.microsoft.com/library/Gg425829(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-132">[Remove-CsNetworkRegion](https://technet.microsoft.com/library/Gg398466(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-132">[Remove-CsNetworkRegion](https://technet.microsoft.com/library/Gg398466(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-133">[Set-CsNetworkRegion](https://technet.microsoft.com/library/Gg413089(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-133">[Set-CsNetworkRegion](https://technet.microsoft.com/library/Gg413089(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="38efc-134">[Get-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398972(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-134">[Get-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398972(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-135">[新 CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398437(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-135">[New-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398437(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-136">[Remove-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg413012(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-136">[Remove-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg413012(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-137">[CsNetworkRegionLink](https://technet.microsoft.com/library/Gg412867(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-137">[Set-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg412867(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="38efc-138">[Get-CsNetworkSite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-138">[Get-CsNetworkSite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-139">[New-CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-139">[New-CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-140">[Remove-CsNetworkSite](https://technet.microsoft.com/library/Gg398135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-140">[Remove-CsNetworkSite](https://technet.microsoft.com/library/Gg398135(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-141">[Set-CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-141">[Set-CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="38efc-142">[Get-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412825(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-142">[Get-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412825(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-143">[New-CsNetworkSubnet](https://technet.microsoft.com/library/Gg398226(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-143">[New-CsNetworkSubnet](https://technet.microsoft.com/library/Gg398226(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-144">[Remove-CsNetworkSubnet](https://technet.microsoft.com/library/Gg425726(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-144">[Remove-CsNetworkSubnet](https://technet.microsoft.com/library/Gg425726(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="38efc-145">[CsNetworkSubnet](https://technet.microsoft.com/library/Gg412739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="38efc-145">[Set-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412739(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="38efc-146">另請參閱</span><span class="sxs-lookup"><span data-stu-id="38efc-146">See Also</span></span>


[<span data-ttu-id="38efc-147">Lync Server 2013 中的通話許可控制概覽</span><span class="sxs-lookup"><span data-stu-id="38efc-147">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  


[<span data-ttu-id="38efc-148">Lync Server PowerShell 的博客</span><span class="sxs-lookup"><span data-stu-id="38efc-148">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

