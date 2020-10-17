---
title: Lync Server 2013：安全性 Cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security cmdlets
ms:assetid: 9a6c654d-287d-434e-8d93-409f0d623f5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398799(v=OCS.15)
ms:contentKeyID: 48184968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d7ba707c613bcfafb23dd158025d253f9a03ac9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510450"
---
# <a name="security-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的安全性 Cmdlet

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

Microsoft Lync Server 2013 中包含的安全性 Cmdlet 主要是用來管理驗證，以及使用者權利和許可權。 有各種各樣的指令程式可用於管理驗證，包括憑證和個人識別碼 (PIN) 驗證的 Cmdlet。 此外，一些 Cmdlet 可讓您使用以新角色為基礎的存取控制 (RBAC) 功能，委派 Lync Server 的管理控制。

<div>

## <a name="security-cmdlets"></a>安全性 Cmdlet

許多套用至安全性設定的管理工作可以從 Lync Server 控制台執行。 其中一個主要例外是使用者許可權 Cmdlet。 不過，您可以使用 Lync Server 管理命令介面或腳本中的 Cmdlet 來執行所有的安全性管理工作。使用腳本可讓您自動執行某些工作。 以下是與管理安全性設定直接相關的 Cmdlet 清單：

**[Lync Server 2013 中的憑證和驗證 Cmdlet](lync-server-2013-certificate-and-authentication-cmdlets.md)**

  - <span></span>  
    [Get-CsCertificate](https://technet.microsoft.com/library/Gg398227(v=OCS.15))

  - <span></span>  
    [匯入-Update-cscertificate](https://technet.microsoft.com/library/Gg398688(v=OCS.15))

  - <span></span>  
    [Remove-Update-cscertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))

  - <span></span>  
    [Request-CsCertificate](https://technet.microsoft.com/library/Gg425723(v=OCS.15))

  - <span></span>  
    [Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsCertificateConfiguration](https://technet.microsoft.com/library/Gg398647(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsClientCertificate](https://technet.microsoft.com/library/Gg398143(v=OCS.15))

  - <span></span>  
    [Revoke-CsClientCertificate](https://technet.microsoft.com/library/Gg425748(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Lock-CsClientPin](https://technet.microsoft.com/library/Gg398650(v=OCS.15))

  - <span></span>  
    [Unlock-csclientpin](https://technet.microsoft.com/library/Gg398929(v=OCS.15))

  - <span></span>  
    [Unlock-CsClientPin](unhttps://technet.microsoft.com/library/Gg398650(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsClientPinInfo](https://technet.microsoft.com/library/Gg425947(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsKerberosAccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))

  - <span></span>  
    [New-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))

  - <span></span>  
    [Remove-Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))

  - <span></span>  
    [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))

  - <span></span>  
    [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsPinPolicy](https://technet.microsoft.com/library/Gg398262(v=OCS.15))

  - <span></span>  
    [授與 Get-cspinpolicy](https://technet.microsoft.com/library/Gg398871(v=OCS.15))

  - <span></span>  
    [新 Get-cspinpolicy](https://technet.microsoft.com/library/Gg398935(v=OCS.15))

  - <span></span>  
    [Remove-Get-cspinpolicy](https://technet.microsoft.com/library/Gg398431(v=OCS.15))

  - <span></span>  
    [Set-CsPinPolicy](https://technet.microsoft.com/library/Gg412997(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsProxyConfiguration](https://technet.microsoft.com/library/Gg399011(v=OCS.15))

  - <span></span>  
    [New-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398335(v=OCS.15))

  - <span></span>  
    [Remove-Set-csproxyconfiguration](https://technet.microsoft.com/library/Gg398553(v=OCS.15))

  - <span></span>  
    [Set-CsProxyConfiguration](https://technet.microsoft.com/library/Gg425796(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsSipDomain](https://technet.microsoft.com/library/Gg398701(v=OCS.15))

  - <span></span>  
    [New-CsSipDomain](https://technet.microsoft.com/library/Gg425857(v=OCS.15))

  - <span></span>  
    [Remove-Get-cssipdomain](https://technet.microsoft.com/library/Gg398865(v=OCS.15))

  - <span></span>  
    [Get-cssipdomain](https://technet.microsoft.com/library/Gg412949(v=OCS.15))

**[Lync Server 2013 中的使用者權限與許可權 Cmdlet](lync-server-2013-user-rights-and-permissions-cmdlets.md)**

  - <span></span>  
    [Get-CsAdminRole](https://technet.microsoft.com/library/Gg399050(v=OCS.15))

  - <span></span>  
    [New-CsAdminRole](https://technet.microsoft.com/library/Gg398271(v=OCS.15))

  - <span></span>  
    [Remove-CsAdminRole](https://technet.microsoft.com/library/Gg413036(v=OCS.15))

  - <span></span>  
    [Get-csadminrole where-object](https://technet.microsoft.com/library/Gg399066(v=OCS.15))

  - <span></span>  
    [Update-CsAdminRole](https://technet.microsoft.com/library/JJ204851(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsAdminRoleAssignment](https://technet.microsoft.com/library/Gg398434(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Grant-CsOUPermission](https://technet.microsoft.com/library/Gg425739(v=OCS.15))

  - <span></span>  
    [Revoke-CsOUPermission](https://technet.microsoft.com/library/Gg398977(v=OCS.15))

  - <span></span>  
    [Test-CsOUPermission](https://technet.microsoft.com/library/Gg398787(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Grant-CsSetupPermission](https://technet.microsoft.com/library/Gg398569(v=OCS.15))

  - <span></span>  
    [Revoke-CsSetupPermission](https://technet.microsoft.com/library/Gg425834(v=OCS.15))

  - <span></span>  
    [Test-CsSetupPermission](https://technet.microsoft.com/library/Gg398428(v=OCS.15))

**[Lync Server 2013 中的互通性 Cmdlet](lync-server-2013-interoperability-cmdlets.md)**

  - [Get-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))

  - [Set-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))

<!-- end list -->

  - [Get-CsOAuthServer](https://technet.microsoft.com/library/JJ205238(v=OCS.15))

  - [New-CsOAuthServer](https://technet.microsoft.com/library/JJ205206(v=OCS.15))

  - [Remove-CsOAuthServer](https://technet.microsoft.com/library/JJ205408(v=OCS.15))

  - [Set-CsOAuthServer](https://technet.microsoft.com/library/JJ204896(v=OCS.15))

<!-- end list -->

  - [Get-CsPartnerApplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))

  - [New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))

  - [Remove-CsPartnerApplication](https://technet.microsoft.com/library/JJ204820(v=OCS.15))

  - [Set-CsPartnerApplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))

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

