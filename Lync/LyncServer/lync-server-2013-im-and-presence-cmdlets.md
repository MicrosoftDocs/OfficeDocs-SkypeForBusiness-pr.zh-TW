---
title: 'Lync Server 2013: IM 和目前狀態 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence cmdlets
ms:assetid: 7b882480-f3d5-44a2-bb75-fffb7e5caede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398611(v=OCS.15)
ms:contentKeyID: 48184589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a39f195bf6424f76a98e2b5c25dc4bf21942911
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="im-and-presence-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的 IM 和目前狀態 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-06-26_

立即訊息 (IM) 和目前狀態的指令程式可讓您管理這些用戶端的功能，透過 Windows PowerShell。 您可以在全域、站台或個別使用者範圍設定使用者所適用的顯示狀態原則。 您也可以設定各種隱私權和 IM 功能。

<div>

## <a name="im-and-presence-cmdlets"></a>IM 和顯示狀態 Cmdlet

若要設定 IM 和顯示狀態，請使用下列 Cmdlet：

  - <span></span>  
    [Get-cspresencepolicy](https://technet.microsoft.com/library/Gg398463(v=OCS.15))

  - <span></span>  
    [Grant-cspresencepolicy](https://technet.microsoft.com/library/Gg398571(v=OCS.15))

  - <span></span>  
    [New-cspresencepolicy](https://technet.microsoft.com/library/Gg412747(v=OCS.15))

  - <span></span>  
    [移除 CsPresencePolicy](https://technet.microsoft.com/library/Gg399070(v=OCS.15))

  - <span></span>  
    [Set-csmonitoringserver](https://technet.microsoft.com/library/Gg425782(v=OCS.15))

<!-- end list -->

  - [Get-cspresenceprovider](https://technet.microsoft.com/library/JJ204705(v=OCS.15))

  - [New-cspresenceprovider](https://technet.microsoft.com/library/JJ204895(v=OCS.15))

  - [Remove-cspresenceprovider](https://technet.microsoft.com/library/JJ205036(v=OCS.15))

  - [Set-cspresenceprovider](https://technet.microsoft.com/library/JJ204833(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csprivacyconfiguration](https://technet.microsoft.com/library/Gg413002(v=OCS.15))

  - <span></span>  
    [New-csprivacyconfiguration](https://technet.microsoft.com/library/Gg398807(v=OCS.15))

  - <span></span>  
    [移除 CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg425821(v=OCS.15))

  - <span></span>  
    [Set-csprivacyconfiguration](https://technet.microsoft.com/library/Gg398484(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [設定 CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csuserservicesconfiguration](https://technet.microsoft.com/library/Gg398133(v=OCS.15))

  - <span></span>  
    [New-csuserservicesconfiguration](https://technet.microsoft.com/library/Gg412926(v=OCS.15))

  - <span></span>  
    [移除 CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398722(v=OCS.15))

  - <span></span>  
    [Set-csuserservicesconfiguration](https://technet.microsoft.com/library/Gg398340(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csfiletransferfilterconfiguration](https://technet.microsoft.com/library/Gg398527(v=OCS.15))

  - <span></span>  
    [New-csfiletransferfilterconfiguration](https://technet.microsoft.com/library/Gg425897(v=OCS.15))

  - <span></span>  
    [Remove-csfiletransferfilterconfiguration](https://technet.microsoft.com/library/Gg413064(v=OCS.15))

  - <span></span>  
    [Set-csfiletransferfilterconfiguration](https://technet.microsoft.com/library/Gg425736(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csimfilterconfiguration](https://technet.microsoft.com/library/Gg398980(v=OCS.15))

  - <span></span>  
    [新 CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398244(v=OCS.15))

  - <span></span>  
    [移除 CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398171(v=OCS.15))

  - <span></span>  
    [設定 CsImFilterConfiguration](https://technet.microsoft.com/library/Gg412960(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-csgroupexpansion](https://technet.microsoft.com/library/Gg399009(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-csgroupim](https://technet.microsoft.com/library/Gg398273(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-csim](https://technet.microsoft.com/library/Gg425802(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-csp2pav](https://technet.microsoft.com/library/Gg412821(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-cspresence](https://technet.microsoft.com/library/Gg398148(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的用戶端管理 cmdlet](lync-server-2013-client-management-cmdlets.md)  


[Lync Server PowerShell 部落格](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

