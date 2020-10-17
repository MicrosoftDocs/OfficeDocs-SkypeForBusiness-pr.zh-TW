---
title: Lync Server 2013： PSTN 連通性 Cmdlet
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
ms.openlocfilehash: d58f168c858a8fd231d2a6cefe692a2f7535da82
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513050"
---
# <a name="pstn-connectivity-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的 PSTN 連線 Cmdlet

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

Enterprise Voice 提供的設定允許公用交換電話網路 (PSTN) 的來電，而不需任何服務品質 (QoS) 。 您可以透過 Lync Server 管理命令介面中提供的 Cmdlet 來設定這些設定。

<div>

## <a name="pstn-connectivity-cmdlets"></a>PSTN 連通性 Cmdlet

使用下列 Cmdlet 來設定 PSTN 連線的各個層面。

**[Lync Server 2013 中的 PSTN 閘道 Cmdlet](lync-server-2013-pstn-gateways-cmdlets.md)**

  - <span></span>  
    [Set-CsPstnGateway](https://technet.microsoft.com/library/Gg398408(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsPstnOutboundCall](https://technet.microsoft.com/library/Gg398207(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/library/Gg398662(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsMediationServer](https://technet.microsoft.com/library/Gg398213(v=OCS.15))

**[Lync Server 2013 中的靜態路由 Cmdlet](lync-server-2013-static-routing-cmdlets.md)**

  - <span></span>  
    [Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg398130(v=OCS.15))

  - <span></span>  
    [New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg413041(v=OCS.15))

  - <span></span>  
    [Remove-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg412932(v=OCS.15))

  - <span></span>  
    [Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg425895(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsStaticRoute](https://technet.microsoft.com/library/Gg398265(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398754(v=OCS.15))

  - <span></span>  
    [New-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg425811(v=OCS.15))

  - <span></span>  
    [Remove-Get-csstaticroutingconfiguration](https://technet.microsoft.com/library/Gg398668(v=OCS.15))

  - <span></span>  
    [Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398724(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyCustom](https://technet.microsoft.com/library/Gg425904(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyRealm](https://technet.microsoft.com/library/Gg413084(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyTCP](https://technet.microsoft.com/library/Gg425745(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyTLS](https://technet.microsoft.com/library/Gg398629(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyTransport](https://technet.microsoft.com/library/Gg398489(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyUseDefault](https://technet.microsoft.com/library/Gg398274(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSipProxyUseDefaultCert](https://technet.microsoft.com/library/Gg425858(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsIssuedCertId](https://technet.microsoft.com/library/Gg425814(v=OCS.15))

**[Lync Server 2013 中的中繼設定 Cmdlet](lync-server-2013-trunking-configuration-cmdlets.md)**

  - [Test-CsInterTrunkRouting](https://technet.microsoft.com/library/JJ204741(v=OCS.15))

<!-- end list -->

  - [Get-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ204962(v=OCS.15))

  - [New-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ205097(v=OCS.15))

  - [Remove-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ204836(v=OCS.15))

  - [Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ205400(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398104(v=OCS.15))

  - <span></span>  
    [New-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg412803(v=OCS.15))

  - <span></span>  
    [Remove-CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398556(v=OCS.15))

  - <span></span>  
    [CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg413073(v=OCS.15))

<!-- end list -->

  - [Get-CsTrunk](https://technet.microsoft.com/library/JJ205244(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398224(v=OCS.15))

  - <span></span>  
    [新 Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg413021(v=OCS.15))

  - <span></span>  
    [Remove-Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15))

  - <span></span>  
    [Set-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398238(v=OCS.15))

  - <span></span>  
    [Test-CsTrunkConfiguration](https://technet.microsoft.com/library/Gg398137(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新 CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))

**[Lync Server 2013 中的語音路由 Cmdlet](lync-server-2013-voice-routing-cmdlets.md)**

  - <span></span>  
    [Get-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))

  - <span></span>  
    [新 CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))

  - <span></span>  
    [Remove-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))

  - <span></span>  
    [CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsVoiceRoute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))

  - <span></span>  
    [New-CsVoiceRoute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))

  - <span></span>  
    [Remove-Get-csvoiceroute](https://technet.microsoft.com/library/Gg398468(v=OCS.15))

  - <span></span>  
    [Get-csvoiceroute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))

  - <span></span>  
    [測試-Get-csvoiceroute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))

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

