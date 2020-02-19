---
title: Lync Server 2013： 通話許可控制 cmdlet
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
ms.openlocfilehash: a84235c2b9a0a6226360a6f2879adc7e0ce75d3e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-cmdlets-in-lync-server-2013"></a><span data-ttu-id="cf1a9-102">Lync Server 2013 中通話許可控制 cmdlet</span><span class="sxs-lookup"><span data-stu-id="cf1a9-102">Call admission control cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf1a9-103">_**主題上次修改日期：** 2012年-03-21_</span><span class="sxs-lookup"><span data-stu-id="cf1a9-103">_**Topic Last Modified:** 2012-03-21_</span></span>

<span data-ttu-id="cf1a9-104">通話許可控制 (CAC) 會決定是否有足夠的網路頻寬，若要建立即時的音訊或視訊工作階段的可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="cf1a9-104">Call admission control (CAC) determines whether there is sufficient network bandwidth to establish a real-time audio or video session of acceptable quality.</span></span> <span data-ttu-id="cf1a9-105">您可以管理 CAC configuraing 限制和設定網路、 網站及子網路以及它們之間的互動。</span><span class="sxs-lookup"><span data-stu-id="cf1a9-105">You manage CAC by configuraing limitations and settings for networks, sites, and subnets and the interactions between them.</span></span>

<div>

## <a name="call-admission-control-cmdlets"></a><span data-ttu-id="cf1a9-106">Call Admission Control Cmdlets</span><span class="sxs-lookup"><span data-stu-id="cf1a9-106">Call Admission Control Cmdlets</span></span>

<span data-ttu-id="cf1a9-107">使用下列 cmdlet 來從 Lync Server 管理命令介面管理 CAC。</span><span class="sxs-lookup"><span data-stu-id="cf1a9-107">Use the following cmdlets to manage CAC from the Lync Server Management Shell.</span></span>

<span data-ttu-id="cf1a9-108">**通話許可控制**</span><span class="sxs-lookup"><span data-stu-id="cf1a9-108">**Call Admission Control**</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-109">[取得 CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412727(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-109">[Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412727(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-110">[新 CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398175(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-110">[New-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398175(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-111">[移除 CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398877(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-111">[Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398877(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-112">[設定 CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412863(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-112">[Set-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412863(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cf1a9-113">[Get-csnetworkbandwidthpolicyprofile](https://technet.microsoft.com/library/Gg425815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-113">[Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg425815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-114">[新 CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398675(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-114">[New-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398675(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-115">[移除 CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398609(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-115">[Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398609(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-116">[Set-csnetworkbandwidthpolicyprofile](https://technet.microsoft.com/library/Gg398338(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-116">[Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398338(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cf1a9-117">[新 CsNetworkBWAlternatePath](https://technet.microsoft.com/library/Gg398732(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-117">[New-CsNetworkBWAlternatePath](https://technet.microsoft.com/library/Gg398732(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cf1a9-118">[新 CsNetworkBWPolicy](https://technet.microsoft.com/library/Gg412916(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-118">[New-CsNetworkBWPolicy](https://technet.microsoft.com/library/Gg412916(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cf1a9-119">[Get-csnetworkconfiguration](https://technet.microsoft.com/library/Gg398140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-119">[Get-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398140(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-120">[移除 CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-120">[Remove-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398938(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-121">[設定 CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-121">[Set-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398927(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cf1a9-122">[Get-csnetworkinterregionroute](https://technet.microsoft.com/library/Gg425817(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-122">[Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg425817(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-123">[新 CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398779(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-123">[New-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398779(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-124">[移除 CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398743(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-124">[Remove-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398743(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-125">[設定 CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398410(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-125">[Set-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398410(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cf1a9-126">[Get-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg412769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-126">[Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg412769(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-127">[新 CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398994(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-127">[New-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398994(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-128">[Remove-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg398963(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-128">[Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398963(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-129">[Set-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg398772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-129">[Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398772(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cf1a9-130">[Get-csnetworkregion](https://technet.microsoft.com/library/Gg398406(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-130">[Get-CsNetworkRegion](https://technet.microsoft.com/library/Gg398406(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-131">[新 CsNetworkRegion](https://technet.microsoft.com/library/Gg425829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-131">[New-CsNetworkRegion](https://technet.microsoft.com/library/Gg425829(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-132">[移除 CsNetworkRegion](https://technet.microsoft.com/library/Gg398466(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-132">[Remove-CsNetworkRegion](https://technet.microsoft.com/library/Gg398466(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-133">[Set-csnetworkregion](https://technet.microsoft.com/library/Gg413089(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-133">[Set-CsNetworkRegion](https://technet.microsoft.com/library/Gg413089(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cf1a9-134">[Get-csnetworkregionlink](https://technet.microsoft.com/library/Gg398972(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-134">[Get-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398972(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-135">[新 CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398437(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-135">[New-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398437(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-136">[移除 CsNetworkRegionLink](https://technet.microsoft.com/library/Gg413012(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-136">[Remove-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg413012(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-137">[設定 CsNetworkRegionLink](https://technet.microsoft.com/library/Gg412867(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-137">[Set-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg412867(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cf1a9-138">[Get-csnetworksite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-138">[Get-CsNetworkSite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-139">[新 CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-139">[New-CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-140">[移除 CsNetworkSite](https://technet.microsoft.com/library/Gg398135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-140">[Remove-CsNetworkSite](https://technet.microsoft.com/library/Gg398135(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-141">[Set-csnetworksite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-141">[Set-CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="cf1a9-142">[Get-csnetworksubnet](https://technet.microsoft.com/library/Gg412825(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-142">[Get-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412825(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-143">[新 CsNetworkSubnet](https://technet.microsoft.com/library/Gg398226(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-143">[New-CsNetworkSubnet](https://technet.microsoft.com/library/Gg398226(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-144">[移除 CsNetworkSubnet](https://technet.microsoft.com/library/Gg425726(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-144">[Remove-CsNetworkSubnet](https://technet.microsoft.com/library/Gg425726(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="cf1a9-145">[設定 CsNetworkSubnet](https://technet.microsoft.com/library/Gg412739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="cf1a9-145">[Set-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412739(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cf1a9-146">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cf1a9-146">See Also</span></span>


[<span data-ttu-id="cf1a9-147">Lync Server 2013 中的通話許可控制的概觀</span><span class="sxs-lookup"><span data-stu-id="cf1a9-147">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  


[<span data-ttu-id="cf1a9-148">Lync Server PowerShell 部落格</span><span class="sxs-lookup"><span data-stu-id="cf1a9-148">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

