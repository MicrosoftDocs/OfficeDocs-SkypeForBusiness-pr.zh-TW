---
title: Lync Server 2013：增強型 9-1-1 Cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enhanced 9-1-1 cmdlets
ms:assetid: e560c688-7b34-4bd7-8104-24f390644105
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415678(v=OCS.15)
ms:contentKeyID: 48185650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bdea8e9aeed89a52b6e288be00afb9ed5fbeb27
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533210"
---
# <a name="enhanced-9-1-1-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的增強型 9-1-1 Cmdlet

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-20_

Microsoft Lync Server 2013 隨附 Cmdlet，可讓您實施及管理增強型 9-1-1 (E9-1-1) 企業語音解決方案的實施。 您可以使用這些 Cmdlet，將連線點對應至實體位址，並設定企業語音使用者所需的設定，以順利完成緊急通話，並自動將位置傳送至緊急服務提供者。 您無法從 Lync Server [控制台] 設定 E9-1-1，您必須使用 Cmdlet。

<div>

## <a name="enhanced-9-1-1-cmdlets"></a>Enhanced 9-1-1 Cmdlets

使用下列 Cmdlet 來設定 E9-1-1。

**增強型 9-1-1**

  - <span></span>  
    [CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg412877(v=OCS.15))

  - <span></span>  
    [Remove-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg425810(v=OCS.15))

  - <span></span>  
    [CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg398620(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsLisCivicAddress](https://technet.microsoft.com/library/Gg398459(v=OCS.15))

  - <span></span>  
    [Test-CsLisCivicAddress](https://technet.microsoft.com/library/Gg425914(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Export-CsLisConfiguration](https://technet.microsoft.com/library/Gg398539(v=OCS.15))

  - <span></span>  
    [匯入-Export-cslisconfiguration](https://technet.microsoft.com/library/Gg398380(v=OCS.15))

  - <span></span>  
    [Export-cslisconfiguration](https://technet.microsoft.com/library/Gg398710(v=OCS.15))

  - <span></span>  
    [Test-CsLisConfiguration](https://technet.microsoft.com/library/Gg398497(v=OCS.15))

  - <span></span>  
    [Export-cslisconfiguration 發佈](https://technet.microsoft.com/library/Gg398364(v=OCS.15))

  - <span></span>  
    [取消發佈-Export-cslisconfiguration](unhttps://technet.microsoft.com/library/Gg398364(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsLisLocation](https://technet.microsoft.com/library/Gg412834(v=OCS.15))

  - <span></span>  
    [Remove-CsLisLocation](https://technet.microsoft.com/library/Gg425722(v=OCS.15))

  - <span></span>  
    [CsLisLocation](https://technet.microsoft.com/library/Gg398757(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsLisPort](https://technet.microsoft.com/library/Gg398820(v=OCS.15))

  - <span></span>  
    [Remove-CsLisPort](https://technet.microsoft.com/library/Gg412899(v=OCS.15))

  - <span></span>  
    [CsLisPort](https://technet.microsoft.com/library/Gg398700(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsLisServiceProvider](https://technet.microsoft.com/library/Gg398116(v=OCS.15))

  - <span></span>  
    [Remove-CsLisServiceProvider](https://technet.microsoft.com/library/Gg398904(v=OCS.15))

  - <span></span>  
    [CsLisServiceProvider](https://technet.microsoft.com/library/Gg425911(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsLisSubnet](https://technet.microsoft.com/library/Gg398473(v=OCS.15))

  - <span></span>  
    [Remove-CsLisSubnet](https://technet.microsoft.com/library/Gg413053(v=OCS.15))

  - <span></span>  
    [CsLisSubnet](https://technet.microsoft.com/library/Gg399016(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsLisSwitch](https://technet.microsoft.com/library/Gg425769(v=OCS.15))

  - <span></span>  
    [Remove-CsLisSwitch](https://technet.microsoft.com/library/Gg398352(v=OCS.15))

  - <span></span>  
    [CsLisSwitch](https://technet.microsoft.com/library/Gg412823(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398117(v=OCS.15))

  - <span></span>  
    [Remove-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398461(v=OCS.15))

  - <span></span>  
    [CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg412723(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsLocationPolicy](https://technet.microsoft.com/library/Gg398911(v=OCS.15))

  - <span></span>  
    [Grant-CsLocationPolicy](https://technet.microsoft.com/library/Gg413049(v=OCS.15))

  - <span></span>  
    [New-CsLocationPolicy](https://technet.microsoft.com/library/Gg398231(v=OCS.15))

  - <span></span>  
    [Remove-CsLocationPolicy](https://technet.microsoft.com/library/Gg398727(v=OCS.15))

  - <span></span>  
    [Set-CsLocationPolicy](https://technet.microsoft.com/library/Gg412987(v=OCS.15))

  - <span></span>  
    [Test-CsLocationPolicy](https://technet.microsoft.com/library/Gg425962(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsNetworkSite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))

  - <span></span>  
    [New-CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))

  - <span></span>  
    [Remove-CsNetworkSite](https://technet.microsoft.com/library/Gg398135(v=OCS.15))

  - <span></span>  
    [Set-CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server PowerShell 的博客](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

