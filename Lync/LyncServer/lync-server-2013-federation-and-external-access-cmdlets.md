---
title: Lync Server 2013：同盟與外部存取 Cmdlet
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
ms.openlocfilehash: b206d8de27f2cdeebab5db0c125012c2a29c65b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765131"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="federation-and-external-access-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的同盟與外部存取 Cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-26_

同盟和外部存取提供兩項重要的功能：同盟可讓使用者與組織外部的人員通訊，而外部存取可讓使用者從內部網路外部連線到 Microsoft Lync Server 2013。 您可以在 Lync Server 2013 中管理同盟和外部存取的 Cmdlet，讓您判斷使用者可以（和無法）與哪些人通訊，並判斷這些使用者是否可以連線到 Lync Server，而不需要登入內部局域網.

<div>

## <a name="federation-and-external-access-cmdlets"></a>同盟與外部存取 Cmdlet

大多數適用于同盟和外部存取的管理工作，都可以從 Lync Server [控制台] 執行。 您可以使用 Lync Server 管理命令介面或腳本中的 Cmdlet 來執行這些相同的工作;使用腳本可讓您自動執行特定工作。 以下是直接與管理同盟及外部存取相關的 Cmdlet 清單：

  - <span></span>  
    [CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398164(v=OCS.15))

  - <span></span>  
    [New-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398628(v=OCS.15))

  - <span></span>  
    [移除-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398913(v=OCS.15))

  - <span></span>  
    [Set-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398931(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398424(v=OCS.15))

  - <span></span>  
    [新-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398822(v=OCS.15))

  - <span></span>  
    [移除-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg425832(v=OCS.15))

  - <span></span>  
    [Set-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398090(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))

  - <span></span>  
    [授與 CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425942(v=OCS.15))

  - <span></span>  
    [New-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398441(v=OCS.15))

  - <span></span>  
    [Remove-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg399057(v=OCS.15))

  - <span></span>  
    [Set-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398916(v=OCS.15))

<!-- end list -->

  - [CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ204904(v=OCS.15))

  - [新-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205114(v=OCS.15))

  - [移除-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205201(v=OCS.15))

  - [Set-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205084(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398481(v=OCS.15))

  - <span></span>  
    [Enable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398166(v=OCS.15))

  - <span></span>  
    [CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))

  - <span></span>  
    [新-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))

  - <span></span>  
    [移除-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg425809(v=OCS.15))

  - <span></span>  
    [Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398984(v=OCS.15))

  - <span></span>  
    [Enable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398780(v=OCS.15))

  - <span></span>  
    [CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412945(v=OCS.15))

  - <span></span>  
    [New-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398161(v=OCS.15))

  - <span></span>  
    [移除-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412906(v=OCS.15))

  - <span></span>  
    [Set-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg413087(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsFederatedPartner](https://technet.microsoft.com/en-us/library/Gg398281(v=OCS.15))

<!-- end list -->

  - [CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))

  - [新-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204631(v=OCS.15))

  - [移除-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ205055(v=OCS.15))

  - [Set-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204686(v=OCS.15))

<!-- end list -->

  - [CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))

  - [Set-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204769(v=OCS.15))

<!-- end list -->

  - [Test-CsXmppIM](https://technet.microsoft.com/en-us/library/JJ205423(v=OCS.15))

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

