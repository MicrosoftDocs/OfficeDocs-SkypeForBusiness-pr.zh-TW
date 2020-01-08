---
title: Lync Server 2013：部署網路區域、網站和子網
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying network regions, sites, and subnets
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994067(v=OCS.15)
ms:contentKeyID: 51803978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e75c18a582be046755a54656e9f367edabdda3e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a>在 Lync Server 2013 中部署網路區域、網站和子網

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-12_

部署企業語音之後，您必須設定：

  - 網路區域

  - 網路網站

  - 網路子網

<div>

## <a name="define-network-regions"></a>定義網路區域

使用 Lync Server Windows PowerShell 命令、新 CsNetworkRegion 或 Lync Server [控制台] 定義網路區域。

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

如需詳細資訊，請參閱[新 CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)。

在這個範例中，下列 Windows PowerShell 命令會說明在此案例中定義的網路區域： region 1 （印度）。

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a>定義網路網站

使用 Lync Server Windows PowerShell 命令、新 CsNetworkSite 或 Lync Server [控制台] 定義網路網站。

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

如需詳細資訊，請參閱[新 CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)。

在這個範例中，下清單格和 Lync Server Windows PowerShell 命令說明在此案例中定義的網路網站。 只有針對位置式路由的特定設定才會包含在表格中，以供圖例之用。

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
<th>Site 1 （新德里）</th>
<th>Site 2 （Hyderabad）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>網站識別碼</p></td>
<td><p>Site 1 （新德里）</p></td>
<td><p>Site 2 （Hyderabad）</p></td>
</tr>
<tr class="even">
<td><p>地區識別碼</p></td>
<td><p>地區1（印度）</p></td>
<td><p>地區1（印度）</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a>定義網路子網

使用 Lync Server Windows PowerShell 命令、新 CsNetworkSubnet 或 Lync Server [控制台] 來定義網路子網，並將其指派給網路網站。

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

如需詳細資訊，請參閱[新 CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。

在這個範例中，下清單格和 Windows PowerShell 命令說明在這個案例中定義的網路子網的指派給 network sites、新德里與 Hyderabad。 只有針對位置式路由的特定設定才會包含在表格中，以供圖例之用。

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
<th>Site 1 （新德里）</th>
<th>Site 2 （Hyderabad）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>子網識別碼</p></td>
<td><p>含</p></td>
<td><p>192.168.1.0</p></td>
</tr>
<tr class="even">
<td><p>遮罩</p></td>
<td><p>24</p></td>
<td><p>24</p></td>
</tr>
<tr class="odd">
<td><p>網站識別碼</p></td>
<td><p>Site 1 （新德里）</p></td>
<td><p>Site 2 （Hyderabad）</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中設定位置基礎路由](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

