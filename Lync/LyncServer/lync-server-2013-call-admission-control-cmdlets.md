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
ms.openlocfilehash: df8c589d6bceea4e0eec108d1d2d2c6c1ac70a37
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中通話許可控制 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-03-21_

通話許可控制 (CAC) 會決定是否有足夠的網路頻寬，若要建立即時的音訊或視訊工作階段的可接受的品質。 您可以管理 CAC configuraing 限制和設定網路、 網站及子網路以及它們之間的互動。

<div>

## <a name="call-admission-control-cmdlets"></a>Call Admission Control Cmdlets

使用下列 cmdlet 來從 Lync Server 管理命令介面管理 CAC。

**通話許可控制**

  - <span></span>  
    [取得 CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412727(v=OCS.15))

  - <span></span>  
    [新 CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398175(v=OCS.15))

  - <span></span>  
    [移除 CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398877(v=OCS.15))

  - <span></span>  
    [設定 CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412863(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csnetworkbandwidthpolicyprofile](https://technet.microsoft.com/library/Gg425815(v=OCS.15))

  - <span></span>  
    [新 CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398675(v=OCS.15))

  - <span></span>  
    [移除 CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398609(v=OCS.15))

  - <span></span>  
    [Set-csnetworkbandwidthpolicyprofile](https://technet.microsoft.com/library/Gg398338(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新 CsNetworkBWAlternatePath](https://technet.microsoft.com/library/Gg398732(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新 CsNetworkBWPolicy](https://technet.microsoft.com/library/Gg412916(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csnetworkconfiguration](https://technet.microsoft.com/library/Gg398140(v=OCS.15))

  - <span></span>  
    [移除 CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398938(v=OCS.15))

  - <span></span>  
    [設定 CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398927(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csnetworkinterregionroute](https://technet.microsoft.com/library/Gg425817(v=OCS.15))

  - <span></span>  
    [新 CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398779(v=OCS.15))

  - <span></span>  
    [移除 CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398743(v=OCS.15))

  - <span></span>  
    [設定 CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398410(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg412769(v=OCS.15))

  - <span></span>  
    [新 CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398994(v=OCS.15))

  - <span></span>  
    [Remove-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg398963(v=OCS.15))

  - <span></span>  
    [Set-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg398772(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csnetworkregion](https://technet.microsoft.com/library/Gg398406(v=OCS.15))

  - <span></span>  
    [新 CsNetworkRegion](https://technet.microsoft.com/library/Gg425829(v=OCS.15))

  - <span></span>  
    [移除 CsNetworkRegion](https://technet.microsoft.com/library/Gg398466(v=OCS.15))

  - <span></span>  
    [Set-csnetworkregion](https://technet.microsoft.com/library/Gg413089(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csnetworkregionlink](https://technet.microsoft.com/library/Gg398972(v=OCS.15))

  - <span></span>  
    [新 CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398437(v=OCS.15))

  - <span></span>  
    [移除 CsNetworkRegionLink](https://technet.microsoft.com/library/Gg413012(v=OCS.15))

  - <span></span>  
    [設定 CsNetworkRegionLink](https://technet.microsoft.com/library/Gg412867(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csnetworksite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))

  - <span></span>  
    [新 CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))

  - <span></span>  
    [移除 CsNetworkSite](https://technet.microsoft.com/library/Gg398135(v=OCS.15))

  - <span></span>  
    [Set-csnetworksite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csnetworksubnet](https://technet.microsoft.com/library/Gg412825(v=OCS.15))

  - <span></span>  
    [新 CsNetworkSubnet](https://technet.microsoft.com/library/Gg398226(v=OCS.15))

  - <span></span>  
    [移除 CsNetworkSubnet](https://technet.microsoft.com/library/Gg425726(v=OCS.15))

  - <span></span>  
    [設定 CsNetworkSubnet](https://technet.microsoft.com/library/Gg412739(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的通話許可控制的概觀](lync-server-2013-overview-of-call-admission-control.md)  


[Lync Server PowerShell 部落格](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

