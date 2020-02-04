---
title: Lync Server 2013：部署網路區域、網站和子網
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
ms.openlocfilehash: 04c39a18147bad3f84bd345ec0a56b606db4cae4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="7629d-102">在 Lync Server 2013 中部署網路區域、網站和子網</span><span class="sxs-lookup"><span data-stu-id="7629d-102">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7629d-103">_**主題上次修改日期：** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="7629d-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="7629d-104">部署企業語音之後，您必須設定：</span><span class="sxs-lookup"><span data-stu-id="7629d-104">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="7629d-105">網路區域</span><span class="sxs-lookup"><span data-stu-id="7629d-105">Network regions</span></span>

  - <span data-ttu-id="7629d-106">網路網站</span><span class="sxs-lookup"><span data-stu-id="7629d-106">Network sites</span></span>

  - <span data-ttu-id="7629d-107">網路子網</span><span class="sxs-lookup"><span data-stu-id="7629d-107">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="7629d-108">定義網路區域</span><span class="sxs-lookup"><span data-stu-id="7629d-108">Define Network Regions</span></span>

<span data-ttu-id="7629d-109">使用 Lync Server Windows PowerShell 命令、新 CsNetworkRegion 或 Lync Server [控制台] 定義網路區域。</span><span class="sxs-lookup"><span data-stu-id="7629d-109">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="7629d-110">如需詳細資訊，請參閱[新 CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)。</span><span class="sxs-lookup"><span data-stu-id="7629d-110">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="7629d-111">在這個範例中，下列 Windows PowerShell 命令會說明在此案例中定義的網路區域： region 1 （印度）。</span><span class="sxs-lookup"><span data-stu-id="7629d-111">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="7629d-112">定義網路網站</span><span class="sxs-lookup"><span data-stu-id="7629d-112">Define Network Sites</span></span>

<span data-ttu-id="7629d-113">使用 Lync Server Windows PowerShell 命令、新 CsNetworkSite 或 Lync Server [控制台] 定義網路網站。</span><span class="sxs-lookup"><span data-stu-id="7629d-113">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="7629d-114">如需詳細資訊，請參閱[新 CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)。</span><span class="sxs-lookup"><span data-stu-id="7629d-114">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="7629d-115">在這個範例中，下清單格和 Lync Server Windows PowerShell 命令說明在此案例中定義的網路網站。</span><span class="sxs-lookup"><span data-stu-id="7629d-115">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="7629d-116">只有針對位置式路由的特定設定才會包含在表格中，以供圖例之用。</span><span class="sxs-lookup"><span data-stu-id="7629d-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="7629d-117">Site 1 （新德里）</span><span class="sxs-lookup"><span data-stu-id="7629d-117">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="7629d-118">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="7629d-118">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7629d-119">網站識別碼</span><span class="sxs-lookup"><span data-stu-id="7629d-119">Site ID</span></span></p></td>
<td><p><span data-ttu-id="7629d-120">Site 1 （新德里）</span><span class="sxs-lookup"><span data-stu-id="7629d-120">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="7629d-121">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="7629d-121">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7629d-122">地區識別碼</span><span class="sxs-lookup"><span data-stu-id="7629d-122">Region ID</span></span></p></td>
<td><p><span data-ttu-id="7629d-123">地區1（印度）</span><span class="sxs-lookup"><span data-stu-id="7629d-123">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="7629d-124">地區1（印度）</span><span class="sxs-lookup"><span data-stu-id="7629d-124">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="7629d-125">定義網路子網</span><span class="sxs-lookup"><span data-stu-id="7629d-125">Define Network Subnets</span></span>

<span data-ttu-id="7629d-126">使用 Lync Server Windows PowerShell 命令、新 CsNetworkSubnet 或 Lync Server [控制台] 來定義網路子網，並將其指派給網路網站。</span><span class="sxs-lookup"><span data-stu-id="7629d-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="7629d-127">如需詳細資訊，請參閱[新 CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。</span><span class="sxs-lookup"><span data-stu-id="7629d-127">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="7629d-128">在這個範例中，下清單格和 Windows PowerShell 命令說明在這個案例中定義的網路子網的指派給 network sites、新德里與 Hyderabad。</span><span class="sxs-lookup"><span data-stu-id="7629d-128">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="7629d-129">只有針對位置式路由的特定設定才會包含在表格中，以供圖例之用。</span><span class="sxs-lookup"><span data-stu-id="7629d-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="7629d-130">Site 1 （新德里）</span><span class="sxs-lookup"><span data-stu-id="7629d-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="7629d-131">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="7629d-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7629d-132">子網識別碼</span><span class="sxs-lookup"><span data-stu-id="7629d-132">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="7629d-133">含</span><span class="sxs-lookup"><span data-stu-id="7629d-133">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="7629d-134">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="7629d-134">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7629d-135">遮罩</span><span class="sxs-lookup"><span data-stu-id="7629d-135">Mask</span></span></p></td>
<td><p><span data-ttu-id="7629d-136">24</span><span class="sxs-lookup"><span data-stu-id="7629d-136">24</span></span></p></td>
<td><p><span data-ttu-id="7629d-137">24</span><span class="sxs-lookup"><span data-stu-id="7629d-137">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7629d-138">網站識別碼</span><span class="sxs-lookup"><span data-stu-id="7629d-138">Site ID</span></span></p></td>
<td><p><span data-ttu-id="7629d-139">Site 1 （新德里）</span><span class="sxs-lookup"><span data-stu-id="7629d-139">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="7629d-140">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="7629d-140">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7629d-141">請參閱</span><span class="sxs-lookup"><span data-stu-id="7629d-141">See Also</span></span>


[<span data-ttu-id="7629d-142">在 Lync Server 2013 中設定位置基礎路由</span><span class="sxs-lookup"><span data-stu-id="7629d-142">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

