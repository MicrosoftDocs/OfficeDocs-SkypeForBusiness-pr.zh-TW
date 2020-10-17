---
title: Lync Server 2013：同盟及外部訪問 Cmdlet
description: Lync Server 2013：同盟及外部訪問 Cmdlet。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Federation and external access cmdlets
ms:assetid: 4a384a57-257f-47a6-98d9-54cea2c647b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415651(v=OCS.15)
ms:contentKeyID: 48184018
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 930de66a54d3f8db07394baf2d8470affe5090e9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543389"
---
# <a name="federation-and-external-access-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的同盟與外部訪問 Cmdlet

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-26_

同盟和外部存取提供兩項重要功能：同盟可讓使用者與組織外部的人員進行通訊，而外部存取可讓使用者從內部網路以外的地方連接至 Microsoft Lync Server 2013。 在 Lync Server 2013 中可用於管理同盟和外部存取的 Cmdlet，可讓您判斷使用者可以 (且無法與) 通訊，以及決定使用者是否可以連線至 Lync Server，而不必登入內部網路。

<div>

## <a name="federation-and-external-access-cmdlets"></a>同盟和外部存取 Cmdlet

您可以從 Lync Server 控制台執行大多數適用于同盟與外部存取的管理工作。 您可以使用 Lync Server 管理命令介面或腳本中的 Cmdlet 執行這些相同的工作。使用腳本可讓您自動執行某些工作。 以下列出與管理同盟和外部存取直接相關的 Cmdlet：

  - <span></span>  
    [Get-CsAllowedDomain](https://technet.microsoft.com/library/Gg398164(v=OCS.15))

  - <span></span>  
    [New-CsAllowedDomain](https://technet.microsoft.com/library/Gg398628(v=OCS.15))

  - <span></span>  
    [Remove-CsAllowedDomain](https://technet.microsoft.com/library/Gg398913(v=OCS.15))

  - <span></span>  
    [Set-CsAllowedDomain](https://technet.microsoft.com/library/Gg398931(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsBlockedDomain](https://technet.microsoft.com/library/Gg398424(v=OCS.15))

  - <span></span>  
    [New-CsBlockedDomain](https://technet.microsoft.com/library/Gg398822(v=OCS.15))

  - <span></span>  
    [Remove-CsBlockedDomain](https://technet.microsoft.com/library/Gg425832(v=OCS.15))

  - <span></span>  
    [CsBlockedDomain](https://technet.microsoft.com/library/Gg398090(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))

  - <span></span>  
    [授與 Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg425942(v=OCS.15))

  - <span></span>  
    [新 Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg398441(v=OCS.15))

  - <span></span>  
    [Remove-Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg399057(v=OCS.15))

  - <span></span>  
    [Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg398916(v=OCS.15))

<!-- end list -->

  - [Get-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ204904(v=OCS.15))

  - [New-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205114(v=OCS.15))

  - [Remove-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205201(v=OCS.15))

  - [Set-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205084(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [停用 Get-cshostingprovider](https://technet.microsoft.com/library/Gg398481(v=OCS.15))

  - <span></span>  
    [Enable-Get-cshostingprovider](https://technet.microsoft.com/library/Gg398166(v=OCS.15))

  - <span></span>  
    [Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))

  - <span></span>  
    [New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))

  - <span></span>  
    [Remove-Get-cshostingprovider](https://technet.microsoft.com/library/Gg425809(v=OCS.15))

  - <span></span>  
    [Get-cshostingprovider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [停用 CsPublicProvider](https://technet.microsoft.com/library/Gg398984(v=OCS.15))

  - <span></span>  
    [Enable-CsPublicProvider](https://technet.microsoft.com/library/Gg398780(v=OCS.15))

  - <span></span>  
    [CsPublicProvider](https://technet.microsoft.com/library/Gg412945(v=OCS.15))

  - <span></span>  
    [新 CsPublicProvider](https://technet.microsoft.com/library/Gg398161(v=OCS.15))

  - <span></span>  
    [Remove-CsPublicProvider](https://technet.microsoft.com/library/Gg412906(v=OCS.15))

  - <span></span>  
    [CsPublicProvider](https://technet.microsoft.com/library/Gg413087(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsFederatedPartner](https://technet.microsoft.com/library/Gg398281(v=OCS.15))

<!-- end list -->

  - [Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))

  - [New-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204631(v=OCS.15))

  - [Remove-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ205055(v=OCS.15))

  - [Set-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204686(v=OCS.15))

<!-- end list -->

  - [Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))

  - [Set-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204769(v=OCS.15))

<!-- end list -->

  - [Test-CsXmppIM](https://technet.microsoft.com/library/JJ205423(v=OCS.15))

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

