---
title: Lync Server 2013： 電話和裝置 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Phones and devices cmdlets
ms:assetid: 6ebeba4b-43ce-4a31-9060-50d249b7564c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415657(v=OCS.15)
ms:contentKeyID: 48184467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1075c96c586f2b1568edc2420873415268edbf58
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phones-and-devices-cmdlets-in-lync-server-2013"></a>Lync Server 2013 的電話和裝置 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-06-28_

Microsoft Lync Server 2013 提供許多 cmdlet 可讓您管理電話及其他硬體裝置。 這包括諸如 Voice over IP (VoIP) 電話;公共區域電話 （例如，電話中建置大廳、 餐廳或其他公用的位置）;與即使類比電話、 不能執行 Lync Phone Edition 的電話。

<div>

## <a name="phones-and-devices-cmdlets"></a>電話和裝置 Cmdlet

**CsDeviceUpdate** cmdlet 可用來管理裝置更新 Web 服務，可讓系統管理員可以將韌體更新至電話及其他執行 Lync Phone Edition 的裝置的 Lync Server 元件。

  - <span></span>  
    [Get-csanalogdevice](https://technet.microsoft.com/library/Gg398748(v=OCS.15))

  - <span></span>  
    [Move-csanalogdevice](https://technet.microsoft.com/library/Gg398816(v=OCS.15))

  - <span></span>  
    [New-csanalogdevice](https://technet.microsoft.com/library/Gg412937(v=OCS.15))

  - <span></span>  
    [Remove-csanalogdevice](rehttps://technet.microsoft.com/library/Gg398816(v=OCS.15))

  - <span></span>  
    [Set-CsAnalogDevice](https://technet.microsoft.com/library/Gg412843(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-cscommonareaphone](https://technet.microsoft.com/library/Gg412934(v=OCS.15))

  - <span></span>  
    [Move-cscommonareaphone](https://technet.microsoft.com/library/Gg412837(v=OCS.15))

  - <span></span>  
    [New-cscommonareaphone](https://technet.microsoft.com/library/Gg398430(v=OCS.15))

  - <span></span>  
    [Remove-cscommonareaphone](rehttps://technet.microsoft.com/library/Gg412837(v=OCS.15))

  - <span></span>  
    [設定 CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398579(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csucphoneconfiguration](https://technet.microsoft.com/library/Gg398070(v=OCS.15))

  - <span></span>  
    [新 CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))

  - <span></span>  
    [移除 CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15))

  - <span></span>  
    [Set-csucphoneconfiguration](https://technet.microsoft.com/library/Gg413042(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Import-csdeviceupdate](https://technet.microsoft.com/library/Gg398861(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csdeviceupdateconfiguration](https://technet.microsoft.com/library/Gg399030(v=OCS.15))

  - <span></span>  
    [新 CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15))

  - <span></span>  
    [移除 CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425933(v=OCS.15))

  - <span></span>  
    [設定 CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [清除 CsDeviceUpdateFile](https://technet.microsoft.com/library/Gg425835(v=OCS.15))

  - <span></span>  
    [清除 CsDeviceUpdateLog](https://technet.microsoft.com/library/Gg412738(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [核准 CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398949(v=OCS.15))

  - <span></span>  
    [Get-csdeviceupdaterule](https://technet.microsoft.com/library/Gg398215(v=OCS.15))

  - <span></span>  
    [移除 CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg425930(v=OCS.15))

  - <span></span>  
    [重設 CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398181(v=OCS.15))

  - <span></span>  
    [還原 CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398305(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [測試 CsPhoneBootstrap](https://technet.microsoft.com/library/Gg412852(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-cstestdevice](https://technet.microsoft.com/library/Gg398304(v=OCS.15))

  - <span></span>  
    [新 CsTestDevice](https://technet.microsoft.com/library/Gg425899(v=OCS.15))

  - <span></span>  
    [移除 CsTestDevice](https://technet.microsoft.com/library/Gg398790(v=OCS.15))

  - <span></span>  
    [設定 CsTestDevice](https://technet.microsoft.com/library/Gg398156(v=OCS.15))

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

