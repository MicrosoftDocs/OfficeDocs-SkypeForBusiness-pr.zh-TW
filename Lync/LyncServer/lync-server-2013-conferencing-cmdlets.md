---
title: Lync Server 2013：會議 Cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferencing cmdlets
ms:assetid: 7ff94637-6319-4c45-9230-be34e8d81ede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398641(v=OCS.15)
ms:contentKeyID: 48184640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bd951904e14d864c165ff98c50088b96e42f04f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的會議 Cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

Microsoft Lync Server 2013 可讓使用者以兩種不同的方式加入會議：使用 Lync 2013 等會議應用程式，或使用電話撥入。 [撥入使用者] 無法進行 [查看投影片] 或 [exchange 立即訊息] 等動作，但他們可以完整參與會議的音訊部分。

<div>

## <a name="conferencing-cmdlets"></a>會議 Cmdlet

**CsDialInConferencing** Cmdlet 是用來設定電話撥入式會議屬性，包括指定使用者可以呼叫的電話號碼，以加入會議（例如，按6將電話加到靜音或取消靜音，就能加入會議）。 大多數的會議功能（例如，使用者可以錄製會議、使用者在會議期間共用應用程式，等等）都是使用**CsConferencingPolicy** Cmdlet 來管理。

**[Lync Server 2013 中的電話撥入式會議 Cmdlet](lync-server-2013-dial-in-conferencing-cmdlets.md)**

  - <span></span>  
    [CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg425771(v=OCS.15))

  - <span></span>  
    [Move-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))

  - <span></span>  
    [New-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg413080(v=OCS.15))

  - <span></span>  
    [Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsDialInConferencing](https://technet.microsoft.com/en-us/library/Gg399013(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg413015(v=OCS.15))

  - <span></span>  
    [新-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg398818(v=OCS.15))

  - <span></span>  
    [移除-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg412782(v=OCS.15))

  - <span></span>  
    [Set-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg425770(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398575(v=OCS.15))

  - <span></span>  
    [新-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412816(v=OCS.15))

  - <span></span>  
    [移除-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398174(v=OCS.15))

  - <span></span>  
    [Set-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg425825(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398578(v=OCS.15))

  - <span></span>  
    [新-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425792(v=OCS.15))

  - <span></span>  
    [移除-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425894(v=OCS.15))

  - <span></span>  
    [Set-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398860(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsDialInConferencingLanguageList](https://technet.microsoft.com/en-us/library/Gg425869(v=OCS.15))

**[Lync Server 2013 中的網路會議 Cmdlet](lync-server-2013-web-conferencing-cmdlets.md)**

  - <span></span>  
    [CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425714(v=OCS.15))

  - <span></span>  
    [移除-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398243(v=OCS.15))

  - <span></span>  
    [Set-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398776(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsConferenceServer](https://technet.microsoft.com/en-us/library/Gg398738(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398965(v=OCS.15))

  - <span></span>  
    [New-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412967(v=OCS.15))

  - <span></span>  
    [移除-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412767(v=OCS.15))

  - <span></span>  
    [Set-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412969(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398293(v=OCS.15))

  - <span></span>  
    [授與 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425937(v=OCS.15))

  - <span></span>  
    [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg413019(v=OCS.15))

  - <span></span>  
    [Remove-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398728(v=OCS.15))

  - <span></span>  
    [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425788(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg425875(v=OCS.15))

  - <span></span>  
    [New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15))

  - <span></span>  
    [移除-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15))

  - <span></span>  
    [Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398648(v=OCS.15))

<!-- end list -->

  - [Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204723(v=OCS.15))

  - [Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205062(v=OCS.15))

  - [Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205277(v=OCS.15))

  - [移動流覽 CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204889(v=OCS.15))

  - [Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204831(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsASConference](https://technet.microsoft.com/en-us/library/JJ205227(v=OCS.15))

  - <span></span>  
    [Test-CsAVConference](https://technet.microsoft.com/en-us/library/Gg412749(v=OCS.15))

  - <span></span>  
    [Test-CsDataConference](https://technet.microsoft.com/en-us/library/JJ205219(v=OCS.15))

  - <span></span>  
    [Test-CsWebApp](https://technet.microsoft.com/en-us/library/Hh689989(v=OCS.15))

  - <span></span>  
    [Test-CsWebAppAnonymous](https://technet.microsoft.com/en-us/library/Hh690041(v=OCS.15))

  - <span></span>  
    [Test-CsWebScheduler](https://technet.microsoft.com/en-us/library/JJ204829(v=OCS.15))

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

