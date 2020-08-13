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

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a>在 Lync Server 2013 中部署網路地區、網站和子網

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-12_

部署企業語音後，您必須設定：

  - 網路地區

  - 網路網站

  - 網路子網路

<div>

## <a name="define-network-regions"></a>定義網路地區

使用 Lync Server Windows PowerShell 命令、New-CsNetworkRegion 或 Lync Server 控制台定義網路地區。

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

如需詳細資訊，請參閱[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)。

在此範例中，下列 Windows PowerShell 命令會說明在此案例中定義的網路地區，地區 1 (印度) 。

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a>定義網路網站

使用 Lync Server Windows PowerShell 命令、New-CsNetworkSite 或 Lync Server 控制台來定義網路網站。

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

如需詳細資訊，請參閱[New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)。

在此範例中，下清單格和 Lync Server Windows PowerShell 命令會說明在此案例中定義的網站。 表格中只會包含針對位置基礎路由特有的設定，以供說明之用。

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
<th>Site 1 (新德里) </th>
<th>Site 2 (Hyderabad) </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>網站識別碼</p></td>
<td><p>Site 1 (新德里) </p></td>
<td><p>Site 2 (Hyderabad) </p></td>
</tr>
<tr class="even">
<td><p>地區識別碼</p></td>
<td><p>地區 1 (印度) </p></td>
<td><p>地區 1 (印度) </p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a>定義網路子網

使用 [Lync Server Windows PowerShell] 命令、New-CsNetworkSubnet 或 Lync Server 控制台來定義網路子網並將其指派給網路網站。

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

如需詳細資訊，請參閱[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。

在此範例中，下清單格和 Windows PowerShell 命令會說明如何將網路子網指派給在此案例中定義的網站（新德里和 Hyderabad）。 表格中只會包含針對位置基礎路由特有的設定，以供說明之用。

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
<th>Site 1 (新德里) </th>
<th>Site 2 (Hyderabad) </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>子網識別碼</p></td>
<td><p>192.168.0.0</p></td>
<td><p>192.168.1.0</p></td>
</tr>
<tr class="even">
<td><p>Mask</p></td>
<td><p>24</p></td>
<td><p>24</p></td>
</tr>
<tr class="odd">
<td><p>網站識別碼</p></td>
<td><p>Site 1 (新德里) </p></td>
<td><p>Site 2 (Hyderabad) </p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定位置基礎路由](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

