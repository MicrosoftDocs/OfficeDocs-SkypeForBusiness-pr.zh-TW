---
title: 'Lync Server 2013: Enterprise Voice cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice cmdlets
ms:assetid: 7d7c6d94-3ead-4d99-95f7-c31b448ab9e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415658(v=OCS.15)
ms:contentKeyID: 48184613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea7503caa674a61de4f3e75f161e94865e1f748b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的 Enterprise Voice cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-03-19_

企業語音是 Microsoft 實作的 VoIP。 Cmdlet 可用於管理 Microsoft Lync Server 2013 中的 Enterprise Voice，將可讓您建立及修改撥號對應表 （之前稱為位置設定檔） 語音原則、 路由和正規化規則。

<div>

## <a name="enterprise-voice-cmdlets"></a>Enterprise Voice Cmdlet

大部分的管理工作適用於 Enterprise Voice 的可執行從 Lync Server Control Panel。 這些相同的工作可以使用 cmdlet 從 Lync Server 管理命令介面或從內執行的指令碼，讓您自動執行特定工作。 以下是 cmdlet 的與管理企業語音直接相關清單：

**[疑難排解 Lync Server 2013 中的 Enterprise Voice cmdlet](lync-server-2013-troubleshooting-enterprise-voice-cmdlets.md)**

  - <span></span>  
    [取得 CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398815(v=OCS.15))

  - <span></span>  
    [移除 CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398804(v=OCS.15))

  - <span></span>  
    [設定 CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398967(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [取得 Test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg412957(v=OCS.15))

  - <span></span>  
    [新 Test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398961(v=OCS.15))

  - <span></span>  
    [移除 Test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg412813(v=OCS.15))

  - <span></span>  
    [設定 Test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398614(v=OCS.15))

  - <span></span>  
    [測試 Test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398260(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-csdialplan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [測試來](https://technet.microsoft.com/library/Gg399003(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [測試 CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [測試 CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [測試 CsVoiceUser](https://technet.microsoft.com/library/Gg413013(v=OCS.15))

**[語音正規化規則在 Lync Server 2013 中的指令程式](lync-server-2013-voice-normalization-rules-cmdlets.md)**

  - <span></span>  
    [Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg398393(v=OCS.15))

  - <span></span>  
    [新來](https://technet.microsoft.com/library/Gg398240(v=OCS.15))

  - <span></span>  
    [移除來](https://technet.microsoft.com/library/Gg398501(v=OCS.15))

  - <span></span>  
    [Set-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg398491(v=OCS.15))

  - <span></span>  
    [測試來](https://technet.microsoft.com/library/Gg399003(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [新 CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))

**[Lync Server 2013 中的語音原則 cmdlet](lync-server-2013-voice-policy-cmdlets.md)**

  - <span></span>  
    [Get-csdialplan](https://technet.microsoft.com/library/Gg413043(v=OCS.15))

  - <span></span>  
    [Grant-csdialplan](https://technet.microsoft.com/library/Gg398547(v=OCS.15))

  - <span></span>  
    [新 CsDialPlan](https://technet.microsoft.com/library/Gg425860(v=OCS.15))

  - <span></span>  
    [移除 CsDialPlan](https://technet.microsoft.com/library/Gg398791(v=OCS.15))

  - <span></span>  
    [Set-csdialplan](https://technet.microsoft.com/library/Gg398644(v=OCS.15))

  - <span></span>  
    [Test-csdialplan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-cspstnusage](https://technet.microsoft.com/library/Gg412734(v=OCS.15))

  - <span></span>  
    [設定 CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csvoicepolicy](https://technet.microsoft.com/library/Gg398101(v=OCS.15))

  - <span></span>  
    [Grant-csvoicepolicy](https://technet.microsoft.com/library/Gg398828(v=OCS.15))

  - <span></span>  
    [新 CsVoicePolicy](https://technet.microsoft.com/library/Gg425856(v=OCS.15))

  - <span></span>  
    [移除 CsVoicePolicy](https://technet.microsoft.com/library/Gg398309(v=OCS.15))

  - <span></span>  
    [Set-csvoicepolicy](https://technet.microsoft.com/library/Gg399021(v=OCS.15))

  - <span></span>  
    [測試 CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))

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


[Lync Server 2013 中的進階的 Enterprise Voice cmdlet](lync-server-2013-advanced-enterprise-voice-cmdlets.md)  
[Lync Server 2013 中的語音應用程式 cmdlet](lync-server-2013-voice-application-cmdlets.md)  


[Lync Server PowerShell 部落格](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

