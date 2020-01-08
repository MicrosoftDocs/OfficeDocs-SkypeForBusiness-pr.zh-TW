---
title: Lync Server 2013：靜態路由 Cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Static routing cmdlets
ms:assetid: 71d5e0cd-8412-4383-818a-95b851a4da4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416492(v=OCS.15)
ms:contentKeyID: 48184496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca2171e66c9441dc2f2f0ff2a8475e03becefd1a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="static-routing-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的靜態路由 Cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-20_

在靜態路由中，系統管理員可以預先確定 SIP 訊息所採取的網路路由。 當伺服器收到訊息時，伺服器會檢查郵寄地址，然後將郵件轉寄到由系統管理員預先設定的下一個躍點伺服器。 如果設定正確，靜態路由會協助確保及時並正確地傳遞訊息，且在伺服器上只要最小限度的監聽。

<div>

## <a name="static-routing-cmdlets"></a>靜態路由 Cmdlet

除非 Microsoft 支援人員另行指示，否則應該使用[CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15)) Cmdlet 來建立針對 Microsoft Lync Server 2013 設定的靜態路由。 建立路由之後，您就可以使用 CsStaticRoutingConfiguration Cmdlet 將該路由新增到靜態路由集合。

**靜態路由**

  - <span></span>  
    [Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg398130(v=OCS.15))

  - <span></span>  
    [New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg413041(v=OCS.15))

  - <span></span>  
    [移除-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg412932(v=OCS.15))

  - <span></span>  
    [Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg425895(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新-CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398754(v=OCS.15))

  - <span></span>  
    [新-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425811(v=OCS.15))

  - <span></span>  
    [Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398668(v=OCS.15))

  - <span></span>  
    [Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398724(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyCustom](https://technet.microsoft.com/en-us/library/Gg425904(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新-CsSipProxyRealm](https://technet.microsoft.com/en-us/library/Gg413084(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新-CsSipProxyTCP](https://technet.microsoft.com/en-us/library/Gg425745(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新-CsSipProxyTLS](https://technet.microsoft.com/en-us/library/Gg398629(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyTransport](https://technet.microsoft.com/en-us/library/Gg398489(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新-CsSipProxyUseDefault](https://technet.microsoft.com/en-us/library/Gg398274(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新-CsSipProxyUseDefaultCert](https://technet.microsoft.com/en-us/library/Gg425858(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新-CsIssuedCertId](https://technet.microsoft.com/en-us/library/Gg425814(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server PowerShell 博客](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

