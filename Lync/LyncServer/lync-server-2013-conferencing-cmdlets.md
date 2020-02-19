---
title: Lync Server 2013： 會議 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing cmdlets
ms:assetid: 7ff94637-6319-4c45-9230-be34e8d81ede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398641(v=OCS.15)
ms:contentKeyID: 48184640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5399b2ee928cddf12575e99965729b373288d647
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140516"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencing-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的會議 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-09_

Microsoft Lync Server 2013 可讓使用者加入會議兩個不同的方式： 使用 Lync 2013，例如會議應用程式或使用電話撥號。 撥入的使用者無法執行檢視投影片或交換立即訊息等動作，但可以完整參與會議的音訊部分。

<div>

## <a name="conferencing-cmdlets"></a>會議 Cmdlet

**CsDialInConferencing** cmdlet 可用於設定電話撥入式會議內容，包括從指定的電話號碼的使用者可以呼叫才能加入會議可用的按鍵命令給他們之後他們加入會議 （例如，按下設為靜音或取消靜音電話 6）, 的所有項目。 大部分會議的其他功能 （例如，使用者可以錄製會議，可以使用者在會議期間共用的應用程式等等） 由使用**CsConferencingPolicy** cmdlet。

**[Lync Server 2013 中的電話撥入式會議 cmdlet](lync-server-2013-dial-in-conferencing-cmdlets.md)**

  - <span></span>  
    [Get-csconferencedirectory](https://technet.microsoft.com/library/Gg425771(v=OCS.15))

  - <span></span>  
    [Move-csconferencedirectory](https://technet.microsoft.com/library/Gg412968(v=OCS.15))

  - <span></span>  
    [新 CsConferenceDirectory](https://technet.microsoft.com/library/Gg413080(v=OCS.15))

  - <span></span>  
    [Remove-csconferencedirectory](rehttps://technet.microsoft.com/library/Gg412968(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-csdialinconferencing](https://technet.microsoft.com/library/Gg399013(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg413015(v=OCS.15))

  - <span></span>  
    [New-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg398818(v=OCS.15))

  - <span></span>  
    [Remove-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg412782(v=OCS.15))

  - <span></span>  
    [Set-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg425770(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg398575(v=OCS.15))

  - <span></span>  
    [新 CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg412816(v=OCS.15))

  - <span></span>  
    [移除 CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398174(v=OCS.15))

  - <span></span>  
    [Set-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg425825(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg398578(v=OCS.15))

  - <span></span>  
    [新 CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425792(v=OCS.15))

  - <span></span>  
    [移除 CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425894(v=OCS.15))

  - <span></span>  
    [Set-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg398860(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csdialinconferencinglanguagelist](https://technet.microsoft.com/library/Gg425869(v=OCS.15))

**[Lync Server 2013 中的 web 會議 cmdlet](lync-server-2013-web-conferencing-cmdlets.md)**

  - <span></span>  
    [Get-csconferencedisclaimer](https://technet.microsoft.com/library/Gg425714(v=OCS.15))

  - <span></span>  
    [移除 CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398243(v=OCS.15))

  - <span></span>  
    [設定 CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398776(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-csconferenceserver](https://technet.microsoft.com/library/Gg398738(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csconferencingconfiguration](https://technet.microsoft.com/library/Gg398965(v=OCS.15))

  - <span></span>  
    [New-csconferencingconfiguration](https://technet.microsoft.com/library/Gg412967(v=OCS.15))

  - <span></span>  
    [移除可](https://technet.microsoft.com/library/Gg412767(v=OCS.15))

  - <span></span>  
    [Set-csconferencingconfiguration](https://technet.microsoft.com/library/Gg412969(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csconferencingpolicy](https://technet.microsoft.com/library/Gg398293(v=OCS.15))

  - <span></span>  
    [Grant-csconferencingpolicy](https://technet.microsoft.com/library/Gg425937(v=OCS.15))

  - <span></span>  
    [New-csconferencingpolicy](https://technet.microsoft.com/library/Gg413019(v=OCS.15))

  - <span></span>  
    [Remove-csconferencingpolicy](https://technet.microsoft.com/library/Gg398728(v=OCS.15))

  - <span></span>  
    [Set-csmonitoringserver](https://technet.microsoft.com/library/Gg425788(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csmeetingconfiguration](https://technet.microsoft.com/library/Gg425875(v=OCS.15))

  - <span></span>  
    [新 CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15))

  - <span></span>  
    [Remove-csmeetingconfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15))

  - <span></span>  
    [Set-csmeetingconfiguration](https://technet.microsoft.com/library/Gg398648(v=OCS.15))

<!-- end list -->

  - [Disable-csmeetingroom](https://technet.microsoft.com/library/JJ204723(v=OCS.15))

  - [Enable-csmeetingroom](https://technet.microsoft.com/library/JJ205062(v=OCS.15))

  - [Get-csmeetingroom](https://technet.microsoft.com/library/JJ205277(v=OCS.15))

  - [Move-csmeetingroom](https://technet.microsoft.com/library/JJ204889(v=OCS.15))

  - [Set-csmeetingroom](https://technet.microsoft.com/library/JJ204831(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-csasconference](https://technet.microsoft.com/library/JJ205227(v=OCS.15))

  - <span></span>  
    [Test-csavconference](https://technet.microsoft.com/library/Gg412749(v=OCS.15))

  - <span></span>  
    [Test-csdataconference](https://technet.microsoft.com/library/JJ205219(v=OCS.15))

  - <span></span>  
    [Test-cswebapp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))

  - <span></span>  
    [Test-cswebappanonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))

  - <span></span>  
    [Test-cswebscheduler](https://technet.microsoft.com/library/JJ204829(v=OCS.15))

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

