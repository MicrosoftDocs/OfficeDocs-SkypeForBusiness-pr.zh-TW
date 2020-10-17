---
title: Lync Server 2013：通話許可控制 Cmdlet
description: Lync Server 2013：通話許可控制 Cmdlet。
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
ms.openlocfilehash: 2d841273ef57c53b5bfa70ca5f2e54e679f70b7a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569199"
---
# <a name="call-admission-control-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的通話許可控制 Cmdlet

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-03-21_

通話許可控制 (CAC) 會判斷是否有足夠的網路頻寬，可為可接受的品質建立即時音訊或影片會話。 您可以 configuraing 網路、網站和子網的限制與設定，以及它們之間的互動來管理 CAC。

<div>

## <a name="call-admission-control-cmdlets"></a>Call Admission Control Cmdlets

使用下列 Cmdlet 來管理 Lync Server 管理命令介面的 CAC。

**通話許可控制**

  - <span></span>  
    [CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412727(v=OCS.15))

  - <span></span>  
    [新 CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398175(v=OCS.15))

  - <span></span>  
    [Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398877(v=OCS.15))

  - <span></span>  
    [CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412863(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg425815(v=OCS.15))

  - <span></span>  
    [New-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398675(v=OCS.15))

  - <span></span>  
    [Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398609(v=OCS.15))

  - <span></span>  
    [Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398338(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新 CsNetworkBWAlternatePath](https://technet.microsoft.com/library/Gg398732(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsNetworkBWPolicy](https://technet.microsoft.com/library/Gg412916(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398140(v=OCS.15))

  - <span></span>  
    [Remove-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398938(v=OCS.15))

  - <span></span>  
    [CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398927(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg425817(v=OCS.15))

  - <span></span>  
    [新 CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398779(v=OCS.15))

  - <span></span>  
    [Remove-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398743(v=OCS.15))

  - <span></span>  
    [CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398410(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg412769(v=OCS.15))

  - <span></span>  
    [新 CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398994(v=OCS.15))

  - <span></span>  
    [Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398963(v=OCS.15))

  - <span></span>  
    [Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398772(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkRegion](https://technet.microsoft.com/library/Gg398406(v=OCS.15))

  - <span></span>  
    [New-CsNetworkRegion](https://technet.microsoft.com/library/Gg425829(v=OCS.15))

  - <span></span>  
    [Remove-CsNetworkRegion](https://technet.microsoft.com/library/Gg398466(v=OCS.15))

  - <span></span>  
    [Set-CsNetworkRegion](https://technet.microsoft.com/library/Gg413089(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398972(v=OCS.15))

  - <span></span>  
    [新 CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398437(v=OCS.15))

  - <span></span>  
    [Remove-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg413012(v=OCS.15))

  - <span></span>  
    [CsNetworkRegionLink](https://technet.microsoft.com/library/Gg412867(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkSite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))

  - <span></span>  
    [New-CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))

  - <span></span>  
    [Remove-CsNetworkSite](https://technet.microsoft.com/library/Gg398135(v=OCS.15))

  - <span></span>  
    [Set-CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412825(v=OCS.15))

  - <span></span>  
    [New-CsNetworkSubnet](https://technet.microsoft.com/library/Gg398226(v=OCS.15))

  - <span></span>  
    [Remove-CsNetworkSubnet](https://technet.microsoft.com/library/Gg425726(v=OCS.15))

  - <span></span>  
    [CsNetworkSubnet](https://technet.microsoft.com/library/Gg412739(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的通話許可控制概覽](lync-server-2013-overview-of-call-admission-control.md)  


[Lync Server PowerShell 的博客](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

