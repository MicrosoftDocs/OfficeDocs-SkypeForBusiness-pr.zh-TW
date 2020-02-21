---
title: Lync Server 2013： 增強型 9-1-1 cmdlet
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
ms.openlocfilehash: b6afb04e0eabcc1c45ae8b0be3904a333852e843
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enhanced-9-1-1-cmdlets-in-lync-server-2013"></a>增強型 9-1-1 Lync Server 2013 中的 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-06-20 個_

Microsoft Lync Server 2013 隨附 cmdlet 可讓您實作和管理企業語音解決方案的增強型 9-1-1 (E9-1-1) 實作。 使用這些 cmdlet 來對應連接點，實體的地址並設定所需的企業語音使用者能成功完成的緊急通話，並自動傳送給緊急服務提供者的 [位置。 您無法設定 E9-1-1 從 Lync Server Control Panel，您必須使用指令程式。

<div>

## <a name="enhanced-9-1-1-cmdlets"></a>Enhanced 9-1-1 Cmdlets

使用下列 cmdlet 設定 E9-1-1。

**增強型 9-1-1**

  - <span></span>  
    [取得 CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg412877(v=OCS.15))

  - <span></span>  
    [移除 CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg425810(v=OCS.15))

  - <span></span>  
    [Set-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg398620(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [取得 CsLisCivicAddress](https://technet.microsoft.com/library/Gg398459(v=OCS.15))

  - <span></span>  
    [Test-csliscivicaddress](https://technet.microsoft.com/library/Gg425914(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Export-cslisconfiguration](https://technet.microsoft.com/library/Gg398539(v=OCS.15))

  - <span></span>  
    [匯入 CsLisConfiguration](https://technet.microsoft.com/library/Gg398380(v=OCS.15))

  - <span></span>  
    [偵錯 CsLisConfiguration](https://technet.microsoft.com/library/Gg398710(v=OCS.15))

  - <span></span>  
    [Test-cslisconfiguration](https://technet.microsoft.com/library/Gg398497(v=OCS.15))

  - <span></span>  
    [發佈 CsLisConfiguration](https://technet.microsoft.com/library/Gg398364(v=OCS.15))

  - <span></span>  
    [解除發佈 CsLisConfiguration](unhttps://technet.microsoft.com/library/Gg398364(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-cslislocation](https://technet.microsoft.com/library/Gg412834(v=OCS.15))

  - <span></span>  
    [移除 CsLisLocation](https://technet.microsoft.com/library/Gg425722(v=OCS.15))

  - <span></span>  
    [設定 CsLisLocation](https://technet.microsoft.com/library/Gg398757(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [取得 CsLisPort](https://technet.microsoft.com/library/Gg398820(v=OCS.15))

  - <span></span>  
    [移除 CsLisPort](https://technet.microsoft.com/library/Gg412899(v=OCS.15))

  - <span></span>  
    [設定 CsLisPort](https://technet.microsoft.com/library/Gg398700(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [取得 CsLisServiceProvider](https://technet.microsoft.com/library/Gg398116(v=OCS.15))

  - <span></span>  
    [移除 CsLisServiceProvider](https://technet.microsoft.com/library/Gg398904(v=OCS.15))

  - <span></span>  
    [設定 CsLisServiceProvider](https://technet.microsoft.com/library/Gg425911(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [取得 CsLisSubnet](https://technet.microsoft.com/library/Gg398473(v=OCS.15))

  - <span></span>  
    [移除 CsLisSubnet](https://technet.microsoft.com/library/Gg413053(v=OCS.15))

  - <span></span>  
    [設定 CsLisSubnet](https://technet.microsoft.com/library/Gg399016(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [取得 CsLisSwitch](https://technet.microsoft.com/library/Gg425769(v=OCS.15))

  - <span></span>  
    [移除 CsLisSwitch](https://technet.microsoft.com/library/Gg398352(v=OCS.15))

  - <span></span>  
    [設定 CsLisSwitch](https://technet.microsoft.com/library/Gg412823(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [取得 CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398117(v=OCS.15))

  - <span></span>  
    [移除 CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398461(v=OCS.15))

  - <span></span>  
    [設定 CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg412723(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-cslocationpolicy](https://technet.microsoft.com/library/Gg398911(v=OCS.15))

  - <span></span>  
    [Grant-cslocationpolicy](https://technet.microsoft.com/library/Gg413049(v=OCS.15))

  - <span></span>  
    [新則 CsLocationPolicy](https://technet.microsoft.com/library/Gg398231(v=OCS.15))

  - <span></span>  
    [移除則 CsLocationPolicy](https://technet.microsoft.com/library/Gg398727(v=OCS.15))

  - <span></span>  
    [設定則 CsLocationPolicy](https://technet.microsoft.com/library/Gg412987(v=OCS.15))

  - <span></span>  
    [Test-cslocationpolicy](https://technet.microsoft.com/library/Gg425962(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csnetworksite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))

  - <span></span>  
    [新 CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))

  - <span></span>  
    [移除 CsNetworkSite](https://technet.microsoft.com/library/Gg398135(v=OCS.15))

  - <span></span>  
    [Set-csnetworksite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server PowerShell 部落格](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

