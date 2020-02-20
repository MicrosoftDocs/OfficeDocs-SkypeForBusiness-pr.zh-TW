---
title: Lync Server 2013： 安全性指令程式
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
ms.openlocfilehash: 8b1461c006a68dff3241d859f5daf91db09e4be0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="security-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的安全性指令程式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-09_

含 Microsoft Lync Server 2013 的安全性指令程式主要用於管理驗證及使用者權限及權限。 各種不同的指令程式可供管理驗證，包括指令程式的憑證及個人識別碼 (pin) 驗證。 此外，許多 cmdlet 可讓您使用新的角色型存取控制 (RBAC) 功能委派管理的 Lync Server 控制。

<div>

## <a name="security-cmdlets"></a>安全性指令程式

從 Lync Server Control Panel 可執行許多適用於安全性設定的管理工作。 其中一個主要的例外是使用者權限指令程式。 不過，所有安全性管理工作可以使用都執行指令程式從 Lync Server 管理命令介面或從內的指令碼;使用指令碼，可讓您自動執行特定工作。 以下是 cmdlet 的與管理安全性設定直接相關清單：

**[Lync Server 2013 中的憑證和驗證 cmdlet](lync-server-2013-certificate-and-authentication-cmdlets.md)**

  - <span></span>  
    [Get-cscertificate](https://technet.microsoft.com/library/Gg398227(v=OCS.15))

  - <span></span>  
    [匯入 Set-cscertificate](https://technet.microsoft.com/library/Gg398688(v=OCS.15))

  - <span></span>  
    [移除 Set-cscertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))

  - <span></span>  
    [Request-cscertificate](https://technet.microsoft.com/library/Gg425723(v=OCS.15))

  - <span></span>  
    [Set-cscertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-cscertificateconfiguration](https://technet.microsoft.com/library/Gg398647(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csclientcertificate](https://technet.microsoft.com/library/Gg398143(v=OCS.15))

  - <span></span>  
    [Revoke-csclientcertificate](https://technet.microsoft.com/library/Gg425748(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Lock-csclientpin](https://technet.microsoft.com/library/Gg398650(v=OCS.15))

  - <span></span>  
    [Set-CsClientPin](https://technet.microsoft.com/library/Gg398929(v=OCS.15))

  - <span></span>  
    [解除鎖定-CsClientPin](unhttps://technet.microsoft.com/library/Gg398650(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csclientpininfo](https://technet.microsoft.com/library/Gg425947(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cskerberosaccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))

  - <span></span>  
    [New-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))

  - <span></span>  
    [移除 CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))

  - <span></span>  
    [設定 CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))

  - <span></span>  
    [Test-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-cskerberosaccountpassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-cspinpolicy](https://technet.microsoft.com/library/Gg398262(v=OCS.15))

  - <span></span>  
    [授與 CsPinPolicy](https://technet.microsoft.com/library/Gg398871(v=OCS.15))

  - <span></span>  
    [新 CsPinPolicy](https://technet.microsoft.com/library/Gg398935(v=OCS.15))

  - <span></span>  
    [Remove-cspinpolicy](https://technet.microsoft.com/library/Gg398431(v=OCS.15))

  - <span></span>  
    [Set-cspinpolicy](https://technet.microsoft.com/library/Gg412997(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csproxyconfiguration](https://technet.microsoft.com/library/Gg399011(v=OCS.15))

  - <span></span>  
    [New-csproxyconfiguration](https://technet.microsoft.com/library/Gg398335(v=OCS.15))

  - <span></span>  
    [Remove-csproxyconfiguration](https://technet.microsoft.com/library/Gg398553(v=OCS.15))

  - <span></span>  
    [Set-csproxyconfiguration](https://technet.microsoft.com/library/Gg425796(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-cssipdomain](https://technet.microsoft.com/library/Gg398701(v=OCS.15))

  - <span></span>  
    [New-cssipdomain](https://technet.microsoft.com/library/Gg425857(v=OCS.15))

  - <span></span>  
    [移除 CsSipDomain](https://technet.microsoft.com/library/Gg398865(v=OCS.15))

  - <span></span>  
    [設定 CsSipDomain](https://technet.microsoft.com/library/Gg412949(v=OCS.15))

**[Lync Server 2013 中的使用者權利和權限 cmdlet](lync-server-2013-user-rights-and-permissions-cmdlets.md)**

  - <span></span>  
    [Get-csadminrole](https://technet.microsoft.com/library/Gg399050(v=OCS.15))

  - <span></span>  
    [New-csadminrole](https://technet.microsoft.com/library/Gg398271(v=OCS.15))

  - <span></span>  
    [Remove-csadminrole](https://technet.microsoft.com/library/Gg413036(v=OCS.15))

  - <span></span>  
    [設定 Get-csadminrole](https://technet.microsoft.com/library/Gg399066(v=OCS.15))

  - <span></span>  
    [Update-csadminrole](https://technet.microsoft.com/library/JJ204851(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csadminroleassignment](https://technet.microsoft.com/library/Gg398434(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Grant-csoupermission](https://technet.microsoft.com/library/Gg425739(v=OCS.15))

  - <span></span>  
    [Revoke-csoupermission](https://technet.microsoft.com/library/Gg398977(v=OCS.15))

  - <span></span>  
    [Test-csoupermission](https://technet.microsoft.com/library/Gg398787(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Grant-cssetuppermission](https://technet.microsoft.com/library/Gg398569(v=OCS.15))

  - <span></span>  
    [Revoke-cssetuppermission](https://technet.microsoft.com/library/Gg425834(v=OCS.15))

  - <span></span>  
    [Test-cssetuppermission](https://technet.microsoft.com/library/Gg398428(v=OCS.15))

**[Lync Server 2013 中的互通性 cmdlet](lync-server-2013-interoperability-cmdlets.md)**

  - [Get-csoauthconfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))

  - [Set-csoauthconfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))

<!-- end list -->

  - [Get-csoauthserver](https://technet.microsoft.com/library/JJ205238(v=OCS.15))

  - [New-csoauthserver](https://technet.microsoft.com/library/JJ205206(v=OCS.15))

  - [Remove-csoauthserver](https://technet.microsoft.com/library/JJ205408(v=OCS.15))

  - [Set-csoauthserver](https://technet.microsoft.com/library/JJ204896(v=OCS.15))

<!-- end list -->

  - [Get-cspartnerapplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))

  - [New-cspartnerapplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))

  - [Remove-cspartnerapplication](https://technet.microsoft.com/library/JJ204820(v=OCS.15))

  - [Set-cspartnerapplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))

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

