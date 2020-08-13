---
title: Lync Server 2013：部署網路地區、網站及子網
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying network regions, sites, and subnets
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994067(v=OCS.15)
ms:contentKeyID: 51803978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 188b2a85e8961a0460bee819e3281d33a6069ddd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="8ff90-102">在 Lync Server 2013 中部署網路地區、網站和子網</span><span class="sxs-lookup"><span data-stu-id="8ff90-102">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ff90-103">_**主題上次修改日期：** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="8ff90-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="8ff90-104">部署企業語音後，您必須設定：</span><span class="sxs-lookup"><span data-stu-id="8ff90-104">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="8ff90-105">網路地區</span><span class="sxs-lookup"><span data-stu-id="8ff90-105">Network regions</span></span>

  - <span data-ttu-id="8ff90-106">網路網站</span><span class="sxs-lookup"><span data-stu-id="8ff90-106">Network sites</span></span>

  - <span data-ttu-id="8ff90-107">網路子網路</span><span class="sxs-lookup"><span data-stu-id="8ff90-107">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="8ff90-108">定義網路地區</span><span class="sxs-lookup"><span data-stu-id="8ff90-108">Define Network Regions</span></span>

<span data-ttu-id="8ff90-109">使用 Lync Server Windows PowerShell 命令、New-CsNetworkRegion 或 Lync Server 控制台定義網路地區。</span><span class="sxs-lookup"><span data-stu-id="8ff90-109">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="8ff90-110">如需詳細資訊，請參閱[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)。</span><span class="sxs-lookup"><span data-stu-id="8ff90-110">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="8ff90-111">在此範例中，下列 Windows PowerShell 命令會說明在此案例中定義的網路地區，地區 1 (印度) 。</span><span class="sxs-lookup"><span data-stu-id="8ff90-111">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="8ff90-112">定義網路網站</span><span class="sxs-lookup"><span data-stu-id="8ff90-112">Define Network Sites</span></span>

<span data-ttu-id="8ff90-113">使用 Lync Server Windows PowerShell 命令、New-CsNetworkSite 或 Lync Server 控制台來定義網路網站。</span><span class="sxs-lookup"><span data-stu-id="8ff90-113">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="8ff90-114">如需詳細資訊，請參閱[New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)。</span><span class="sxs-lookup"><span data-stu-id="8ff90-114">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="8ff90-115">在此範例中，下清單格和 Lync Server Windows PowerShell 命令會說明在此案例中定義的網站。</span><span class="sxs-lookup"><span data-stu-id="8ff90-115">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="8ff90-116">表格中只會包含針對位置基礎路由特有的設定，以供說明之用。</span><span class="sxs-lookup"><span data-stu-id="8ff90-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
    New-CsNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="8ff90-117">Site 1 (新德里) </span><span class="sxs-lookup"><span data-stu-id="8ff90-117">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="8ff90-118">Site 2 (Hyderabad) </span><span class="sxs-lookup"><span data-stu-id="8ff90-118">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ff90-119">網站識別碼</span><span class="sxs-lookup"><span data-stu-id="8ff90-119">Site ID</span></span></p></td>
<td><p><span data-ttu-id="8ff90-120">Site 1 (新德里) </span><span class="sxs-lookup"><span data-stu-id="8ff90-120">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="8ff90-121">Site 2 (Hyderabad) </span><span class="sxs-lookup"><span data-stu-id="8ff90-121">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ff90-122">地區識別碼</span><span class="sxs-lookup"><span data-stu-id="8ff90-122">Region ID</span></span></p></td>
<td><p><span data-ttu-id="8ff90-123">地區 1 (印度) </span><span class="sxs-lookup"><span data-stu-id="8ff90-123">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="8ff90-124">地區 1 (印度) </span><span class="sxs-lookup"><span data-stu-id="8ff90-124">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="8ff90-125">定義網路子網</span><span class="sxs-lookup"><span data-stu-id="8ff90-125">Define Network Subnets</span></span>

<span data-ttu-id="8ff90-126">使用 [Lync Server Windows PowerShell] 命令、New-CsNetworkSubnet 或 Lync Server 控制台來定義網路子網並將其指派給網路網站。</span><span class="sxs-lookup"><span data-stu-id="8ff90-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="8ff90-127">如需詳細資訊，請參閱[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。</span><span class="sxs-lookup"><span data-stu-id="8ff90-127">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="8ff90-128">在此範例中，下清單格和 Windows PowerShell 命令會說明如何將網路子網指派給在此案例中定義的網站（新德里和 Hyderabad）。</span><span class="sxs-lookup"><span data-stu-id="8ff90-128">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="8ff90-129">表格中只會包含針對位置基礎路由特有的設定，以供說明之用。</span><span class="sxs-lookup"><span data-stu-id="8ff90-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
    New-CsNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="8ff90-130">Site 1 (新德里) </span><span class="sxs-lookup"><span data-stu-id="8ff90-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="8ff90-131">Site 2 (Hyderabad) </span><span class="sxs-lookup"><span data-stu-id="8ff90-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ff90-132">子網識別碼</span><span class="sxs-lookup"><span data-stu-id="8ff90-132">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="8ff90-133">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="8ff90-133">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="8ff90-134">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="8ff90-134">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ff90-135">Mask</span><span class="sxs-lookup"><span data-stu-id="8ff90-135">Mask</span></span></p></td>
<td><p><span data-ttu-id="8ff90-136">24</span><span class="sxs-lookup"><span data-stu-id="8ff90-136">24</span></span></p></td>
<td><p><span data-ttu-id="8ff90-137">24</span><span class="sxs-lookup"><span data-stu-id="8ff90-137">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ff90-138">網站識別碼</span><span class="sxs-lookup"><span data-stu-id="8ff90-138">Site ID</span></span></p></td>
<td><p><span data-ttu-id="8ff90-139">Site 1 (新德里) </span><span class="sxs-lookup"><span data-stu-id="8ff90-139">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="8ff90-140">Site 2 (Hyderabad) </span><span class="sxs-lookup"><span data-stu-id="8ff90-140">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8ff90-141">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8ff90-141">See Also</span></span>


[<span data-ttu-id="8ff90-142">在 Lync Server 2013 中設定位置基礎路由</span><span class="sxs-lookup"><span data-stu-id="8ff90-142">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

