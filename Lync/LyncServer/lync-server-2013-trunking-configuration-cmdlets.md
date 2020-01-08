---
title: Lync Server 2013：中繼配置 Cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Trunking configuration cmdlets
ms:assetid: 2c36b03a-b80f-4321-a448-6ba26b9357f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416489(v=OCS.15)
ms:contentKeyID: 48183703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec65e877d480924f3fcc312b3972cc329ad4ed34
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="trunking-configuration-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的中繼配置 Cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-08_

幹線配置 Cmdlet 是用來定義中繼對等實體的設定，例如公用交換電話網絡（PSTN）閘道、IP-公用分支 exchange （PBX），或服務提供者的會話邊界控制器（SBC）。 這些設定所設定的項目包括此主幹是否啟用媒體旁路、是否在特定情況下傳送即時傳輸控制通訊協定 (RTCP) 封包，以及是否需要安全即時通訊協定 (SRTP) 加密。

<div>

## <a name="trunking-configuration-cmdlets"></a>中繼配置 Cmdlet

使用下列 Cmdlet 進行中繼設定。

**中繼設定**

  - [Test-CsInterTrunkRouting](https://technet.microsoft.com/en-us/library/JJ204741(v=OCS.15))

<!-- end list -->

  - [CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204962(v=OCS.15))

  - [新-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205097(v=OCS.15))

  - [移除-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204836(v=OCS.15))

  - [Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205400(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398104(v=OCS.15))

  - <span></span>  
    [New-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg412803(v=OCS.15))

  - <span></span>  
    [移除-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398556(v=OCS.15))

  - <span></span>  
    [Set-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg413073(v=OCS.15))

<!-- end list -->

  - [CsTrunk](https://technet.microsoft.com/en-us/library/JJ205244(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398224(v=OCS.15))

  - <span></span>  
    [新-New-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg413021(v=OCS.15))

  - <span></span>  
    [移除-New-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15))

  - <span></span>  
    [Set-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398238(v=OCS.15))

  - <span></span>  
    [Test-New-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg398137(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新-CsVoiceRegex](https://technet.microsoft.com/en-us/library/Gg412751(v=OCS.15))

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

