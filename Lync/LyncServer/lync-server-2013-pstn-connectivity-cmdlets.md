---
title: 'Lync Server 2013: PSTN 連線 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN connectivity cmdlets
ms:assetid: b19ba43c-3987-410d-a704-aba0a4fb0498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415670(v=OCS.15)
ms:contentKeyID: 48185142
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19d4ef9b42c57470ca5072b8a56d766a557e1101
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pstn-connectivity-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的 PSTN 連線 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-09_

Enterprise Voice 會提供設定可讓呼叫到及傳送自公用交換的電話網路 (PSTN) 沒有任何下降的服務品質 (QoS)。 您可以設定這些設定到 cmdlet 可從 Lync Server 管理命令介面。

<div>

## <a name="pstn-connectivity-cmdlets"></a>PSTN 連線 Cmdlet

使用下列 cmdlet 來設定各種層面的 PSTN 連線能力。

**[Lync Server 2013 中的 PSTN 閘道 cmdlet](lync-server-2013-pstn-gateways-cmdlets.md)**

  - <span></span>  
    [Set-cspstngateway](https://technet.microsoft.com/library/Gg398408(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-cspstnoutboundcall](https://technet.microsoft.com/library/Gg398207(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-cspstnpeertopeercall](https://technet.microsoft.com/library/Gg398662(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-csmediationserver](https://technet.microsoft.com/library/Gg398213(v=OCS.15))

**[Lync Server 2013 中的靜態路由 cmdlet](lync-server-2013-static-routing-cmdlets.md)**

  - <span></span>  
    [Get-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg398130(v=OCS.15))

  - <span></span>  
    [New-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg413041(v=OCS.15))

  - <span></span>  
    [Remove-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg412932(v=OCS.15))

  - <span></span>  
    [Set-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg425895(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-csstaticroute](https://technet.microsoft.com/library/Gg398265(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csstaticroutingconfiguration](https://technet.microsoft.com/library/Gg398754(v=OCS.15))

  - <span></span>  
    [New-csstaticroutingconfiguration](https://technet.microsoft.com/library/Gg425811(v=OCS.15))

  - <span></span>  
    [移除 New-csstaticroutingconfiguration](https://technet.microsoft.com/library/Gg398668(v=OCS.15))

  - <span></span>  
    [Set-csstaticroutingconfiguration](https://technet.microsoft.com/library/Gg398724(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cssipproxycustom](https://technet.microsoft.com/library/Gg425904(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cssipproxyrealm](https://technet.microsoft.com/library/Gg413084(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cssipproxytcp](https://technet.microsoft.com/library/Gg425745(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cssipproxytls](https://technet.microsoft.com/library/Gg398629(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cssipproxytransport](https://technet.microsoft.com/library/Gg398489(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cssipproxyusedefault](https://technet.microsoft.com/library/Gg398274(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cssipproxyusedefaultcert](https://technet.microsoft.com/library/Gg425858(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-csissuedcertid](https://technet.microsoft.com/library/Gg425814(v=OCS.15))

**[Lync Server 2013 中的主幹組態 cmdlet](lync-server-2013-trunking-configuration-cmdlets.md)**

  - [Test-csintertrunkrouting](https://technet.microsoft.com/library/JJ204741(v=OCS.15))

<!-- end list -->

  - [Get-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ204962(v=OCS.15))

  - [New-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ205097(v=OCS.15))

  - [Remove-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ204836(v=OCS.15))

  - [Set-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ205400(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [取得 CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398104(v=OCS.15))

  - <span></span>  
    [新 CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg412803(v=OCS.15))

  - <span></span>  
    [移除 CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398556(v=OCS.15))

  - <span></span>  
    [設定 CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg413073(v=OCS.15))

<!-- end list -->

  - [Get-cstrunk](https://technet.microsoft.com/library/JJ205244(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg398224(v=OCS.15))

  - <span></span>  
    [新 Test-cstrunkconfiguration](https://technet.microsoft.com/library/Gg413021(v=OCS.15))

  - <span></span>  
    [Remove-cstrunkconfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15))

  - <span></span>  
    [Set-cstrunkconfiguration](https://technet.microsoft.com/library/Gg398238(v=OCS.15))

  - <span></span>  
    [測試 Test-cstrunkconfiguration](https://technet.microsoft.com/library/Gg398137(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新 CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))

**[語音路由 cmdlet 在 Lync Server 2013](lync-server-2013-voice-routing-cmdlets.md)**

  - <span></span>  
    [Get-csroutingconfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))

  - <span></span>  
    [新 CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))

  - <span></span>  
    [移除 CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))

  - <span></span>  
    [設定 CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csvoiceroute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))

  - <span></span>  
    [新 CsVoiceRoute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))

  - <span></span>  
    [移除 CsVoiceRoute](https://technet.microsoft.com/library/Gg398468(v=OCS.15))

  - <span></span>  
    [設定 CsVoiceRoute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))

  - <span></span>  
    [測試 CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))

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

