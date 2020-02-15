---
title: Lync Server 2013： 同盟和外部存取 cmdlet
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
ms.openlocfilehash: 032258e6fe7d77808b3bf4731049ee9df49d1162
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="federation-and-external-access-cmdlets-in-lync-server-2013"></a>同盟和 Lync Server 2013 中的外部存取 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-06-26_

同盟和外部存取提供兩個重要功能： 同盟可讓使用者能夠與組織外的人員時外部存取可讓使用者連線到 Microsoft Lync Server 2013 中從內部網路之外。 可用於管理同盟與外部存取 Lync Server 2013 中的 cmdlet 可讓您決定您的使用者可以 （而且也無法） 通訊，並決定這些使用者可以連線至 Lync Server 而不必登入內部網路。

<div>

## <a name="federation-and-external-access-cmdlets"></a>同盟和外部存取 Cmdlet

從 Lync Server Control Panel 可執行大部分適用於同盟和外部存取的管理工作。 這些相同的工作可以使用 cmdlet 從 Lync Server 管理命令介面或從內執行的指令碼;使用指令碼，可讓您自動執行特定工作。 以下列出與管理同盟和外部存取直接相關的 Cmdlet：

  - <span></span>  
    [Get-csalloweddomain](https://technet.microsoft.com/library/Gg398164(v=OCS.15))

  - <span></span>  
    [新 CsAllowedDomain](https://technet.microsoft.com/library/Gg398628(v=OCS.15))

  - <span></span>  
    [移除 CsAllowedDomain](https://technet.microsoft.com/library/Gg398913(v=OCS.15))

  - <span></span>  
    [Set-csalloweddomain](https://technet.microsoft.com/library/Gg398931(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csblockeddomain](https://technet.microsoft.com/library/Gg398424(v=OCS.15))

  - <span></span>  
    [新 New-csblockeddomain](https://technet.microsoft.com/library/Gg398822(v=OCS.15))

  - <span></span>  
    [移除 New-csblockeddomain](https://technet.microsoft.com/library/Gg425832(v=OCS.15))

  - <span></span>  
    [設定 New-csblockeddomain](https://technet.microsoft.com/library/Gg398090(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))

  - <span></span>  
    [Grant-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg425942(v=OCS.15))

  - <span></span>  
    [新 CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398441(v=OCS.15))

  - <span></span>  
    [Remove-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg399057(v=OCS.15))

  - <span></span>  
    [設定 CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398916(v=OCS.15))

<!-- end list -->

  - [Get-csfipsconfiguration](https://technet.microsoft.com/library/JJ204904(v=OCS.15))

  - [New-csfipsconfiguration](https://technet.microsoft.com/library/JJ205114(v=OCS.15))

  - [Remove-csfipsconfiguration](https://technet.microsoft.com/library/JJ205201(v=OCS.15))

  - [Set-csfipsconfiguration](https://technet.microsoft.com/library/JJ205084(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [停用 CsHostingProvider](https://technet.microsoft.com/library/Gg398481(v=OCS.15))

  - <span></span>  
    [啟用 CsHostingProvider](https://technet.microsoft.com/library/Gg398166(v=OCS.15))

  - <span></span>  
    [Get-cshostingprovider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))

  - <span></span>  
    [新 CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))

  - <span></span>  
    [移除 CsHostingProvider](https://technet.microsoft.com/library/Gg425809(v=OCS.15))

  - <span></span>  
    [設定 CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [停用 CsPublicProvider](https://technet.microsoft.com/library/Gg398984(v=OCS.15))

  - <span></span>  
    [啟用 CsPublicProvider](https://technet.microsoft.com/library/Gg398780(v=OCS.15))

  - <span></span>  
    [取得 CsPublicProvider](https://technet.microsoft.com/library/Gg412945(v=OCS.15))

  - <span></span>  
    [新 CsPublicProvider](https://technet.microsoft.com/library/Gg398161(v=OCS.15))

  - <span></span>  
    [移除 CsPublicProvider](https://technet.microsoft.com/library/Gg412906(v=OCS.15))

  - <span></span>  
    [設定 CsPublicProvider](https://technet.microsoft.com/library/Gg413087(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-csfederatedpartner](https://technet.microsoft.com/library/Gg398281(v=OCS.15))

<!-- end list -->

  - [Get-csxmppallowedpartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))

  - [New-csxmppallowedpartner](https://technet.microsoft.com/library/JJ204631(v=OCS.15))

  - [Remove-csxmppallowedpartner](https://technet.microsoft.com/library/JJ205055(v=OCS.15))

  - [Set-csxmppallowedpartner](https://technet.microsoft.com/library/JJ204686(v=OCS.15))

<!-- end list -->

  - [Get-csxmppgatewayconfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))

  - [Set-csxmppgatewayconfiguration](https://technet.microsoft.com/library/JJ204769(v=OCS.15))

<!-- end list -->

  - [Test-csxmppim](https://technet.microsoft.com/library/JJ205423(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server PowerShell 部落格](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

