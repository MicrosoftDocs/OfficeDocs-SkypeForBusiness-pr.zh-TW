---
title: Lync Server 2013：伺服器角色和服務 Cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles and services cmdlets
ms:assetid: ff3561de-043e-4071-88f7-8de3cded52f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415683(v=OCS.15)
ms:contentKeyID: 48185971
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41b8d2de39f3aa6cce5b192147c2844e5d0f0f81
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510250"
---
# <a name="server-roles-and-services-cmdlets-in-lync-server-2013"></a>Lync Server 2013 中的伺服器角色和服務 Cmdlet

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-29_

許多 Microsoft Lync Server 2013 元件會以伺服器角色或服務的形式執行。 Lync Server 2013 隨附許多 Cmdlet，可讓您管理這些伺服器角色和服務。

<div>

## <a name="server-roles-and-services-cmdlets"></a>伺服器角色和服務 Cmdlet

許多 (，但並非所有套用至伺服器和服務角色的管理工作) ，都可以從 Lync Server 控制台執行。 例如，您可以使用 Lync Server 控制台管理封存伺服器設定，但不管理通訊錄服務器設定。 不過，您可以使用 Lync Server 管理命令介面或腳本中的 Cmdlet 來執行所有這些工作。使用腳本可讓您自動執行某些工作。 以下是與管理伺服器角色和服務直接相關的 Cmdlet 清單：

**[Lync Server 2013 中的通訊錄服務器 Cmdlet](lync-server-2013-address-book-server-cmdlets.md)**

  - <span></span>  
    [Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))

  - <span></span>  
    [New-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))

  - <span></span>  
    [Remove-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))

  - <span></span>  
    [Set-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Update-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Debug-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))

**[Lync Server 2013 中的封存與監控 Cmdlet](lync-server-2013-archiving-and-monitoring-cmdlets.md)**

  - <span></span>  
    [Get-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg399012(v=OCS.15))

  - <span></span>  
    [New-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg398471(v=OCS.15))

  - <span></span>  
    [Remove-CsArchivingConfiguration](https://technet.microsoft.com/library/Gg398951(v=OCS.15))

  - <span></span>  
    [Get-csarchivingconfiguration](https://technet.microsoft.com/library/Gg413030(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Export-CsArchivingData](https://technet.microsoft.com/library/Gg398452(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Invoke-CsArchivingDatabasePurge](https://technet.microsoft.com/library/JJ204627(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsArchivingPolicy](https://technet.microsoft.com/library/Gg425731(v=OCS.15))

  - <span></span>  
    [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/Gg398475(v=OCS.15))

  - <span></span>  
    [New-CsArchivingPolicy](https://technet.microsoft.com/library/Gg399032(v=OCS.15))

  - <span></span>  
    [Remove-Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg425924(v=OCS.15))

  - <span></span>  
    [Set-CsArchivingPolicy](https://technet.microsoft.com/library/Gg398294(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsArchivingServer](https://technet.microsoft.com/library/Gg398923(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398298(v=OCS.15))

  - <span></span>  
    [新 CsCdrConfiguration](https://technet.microsoft.com/library/Gg399018(v=OCS.15))

  - <span></span>  
    [Remove-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398451(v=OCS.15))

  - <span></span>  
    [Set-CsCdrConfiguration](https://technet.microsoft.com/library/Gg398774(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsMonitoringServer](https://technet.microsoft.com/library/Gg425776(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsQoEConfiguration](https://technet.microsoft.com/library/Gg399004(v=OCS.15))

  - <span></span>  
    [新 CsQoEConfiguration](https://technet.microsoft.com/library/Gg398325(v=OCS.15))

  - <span></span>  
    [Remove-CsQoEConfiguration](https://technet.microsoft.com/library/Gg425879(v=OCS.15))

  - <span></span>  
    [Set-CsQoEConfiguration](https://technet.microsoft.com/library/Gg398245(v=OCS.15))

[Invoke-CsCdrDatabasePurge](https://technet.microsoft.com/library/JJ205113(v=OCS.15))

  - <span></span>  
    [Export-CsArchivingData](https://technet.microsoft.com/library/Gg398452(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Invoke-CsQoEDatabasePurge](https://technet.microsoft.com/library/JJ205247(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsReportingConfiguration](https://technet.microsoft.com/library/JJ205356(v=OCS.15))

  - <span></span>  
    [New-CsReportingConfiguration](https://technet.microsoft.com/library/JJ204787(v=OCS.15))

  - <span></span>  
    [Remove-CsReportingConfiguration](https://technet.microsoft.com/library/JJ204711(v=OCS.15))

  - <span></span>  
    [Set-CsReportingConfiguration](https://technet.microsoft.com/library/JJ205075(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsTestUserCredential](https://technet.microsoft.com/library/JJ204759(v=OCS.15))

  - <span></span>  
    [Remove-CsTestUserCredential](https://technet.microsoft.com/library/JJ204870(v=OCS.15))

  - <span></span>  
    [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204739(v=OCS.15))

  - <span></span>  
    [New-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ205254(v=OCS.15))

  - <span></span>  
    [Remove-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204926(v=OCS.15))

  - <span></span>  
    [Set-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204620(v=OCS.15))

  - <span></span>  
    [Test-CsWatcherNodeConfiguration](https://technet.microsoft.com/library/JJ204652(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsExtendedTest](https://technet.microsoft.com/library/JJ205275(v=OCS.15))

**[Lync Server 2013 中的資料庫和管理伺服器 Cmdlet](lync-server-2013-database-and-management-server-cmdlets.md)**

  - <span></span>  
    [Get-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))

  - <span></span>  
    [Remove-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398214(v=OCS.15))

  - <span></span>  
    [Set-CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Install-CsDatabase](https://technet.microsoft.com/library/Gg399044(v=OCS.15))

  - <span></span>  
    [Test-CsDatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))

  - <span></span>  
    [Uninstall-CsDatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))

<!-- end list -->

  - [Invoke-CsDatabaseFailover](https://technet.microsoft.com/library/JJ204744(v=OCS.15))

<!-- end list -->

  - [Get-CsDatabaseMirrorState](https://technet.microsoft.com/library/JJ204845(v=OCS.15))

<!-- end list -->

  - [Install-CsMirrorDatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))

  - [Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsUserDatabaseState](https://technet.microsoft.com/library/Gg398831(v=OCS.15))

  - <span></span>  
    [CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [更新-CsUserDatabase](https://technet.microsoft.com/library/Gg398682(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Move-CsManagementServer](https://technet.microsoft.com/library/Gg412921(v=OCS.15))

  - <span></span>  
    [Set-CsManagementServer](https://technet.microsoft.com/library/Gg398465(v=OCS.15))

<!-- end list -->

  - [Invoke-CsManagementServerFailover](https://technet.microsoft.com/library/JJ204647(v=OCS.15))

**[Lync Server 2013 中的 Edge Server Cmdlet](lync-server-2013-edge-server-cmdlets.md)**

  - <span></span>  
    [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))

  - <span></span>  
    [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))

  - <span></span>  
    [新 CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))

  - <span></span>  
    [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))

  - <span></span>  
    [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsAVEdgeConnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsEdgeServer](https://technet.microsoft.com/library/Gg398859(v=OCS.15))

**[Lync Server 2013 中的其他伺服器角色 Cmdlet](lync-server-2013-other-server-role-cmdlets.md)**

  - <span></span>  
    [Set-CsConferenceServer](https://technet.microsoft.com/library/Gg398738(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))

**[Lync Server 2013 中的註冊機構和 Director Cmdlet](lync-server-2013-registrar-and-director-cmdlets.md)**

  - <span></span>  
    [CsDirector](https://technet.microsoft.com/library/Gg398565(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Reset-CsPoolRegistrarState](https://technet.microsoft.com/library/JJ619172(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsRegistrar](https://technet.microsoft.com/library/Gg398993(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398483(v=OCS.15))

  - <span></span>  
    [New-CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg425893(v=OCS.15))

  - <span></span>  
    [Remove-Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg398482(v=OCS.15))

  - <span></span>  
    [Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg398764(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15))

**[Lync Server 2013 中的服務 Cmdlet](lync-server-2013-services-cmdlets.md)**

  - <span></span>  
    [Get-CsService](https://technet.microsoft.com/library/Gg413038(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsWindowsService](https://technet.microsoft.com/library/Gg398803(v=OCS.15))

  - <span></span>  
    [Start-CsWindowsService](https://technet.microsoft.com/library/Gg398561(v=OCS.15))

  - <span></span>  
    [Stop-CsWindowsService](https://technet.microsoft.com/library/Gg398426(v=OCS.15))

**[在 Lync Server 2013 中疑難排解伺服器角色和服務 Cmdlet](lync-server-2013-troubleshooting-server-roles-and-services-cmdlets.md)**

  - <span></span>  
    [Get-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg412984(v=OCS.15))

  - <span></span>  
    [Set-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg398907(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398667(v=OCS.15))

  - <span></span>  
    [New-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398718(v=OCS.15))

  - <span></span>  
    [Remove-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425794(v=OCS.15))

  - <span></span>  
    [Set-CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425847(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg413034(v=OCS.15))

  - <span></span>  
    [New-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg398733(v=OCS.15))

  - <span></span>  
    [Remove-Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg412853(v=OCS.15))

  - <span></span>  
    [Set-CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg425734(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsDiagnosticsFilter](https://technet.microsoft.com/library/Gg413009(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg412774(v=OCS.15))

  - <span></span>  
    [New-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398350(v=OCS.15))

  - <span></span>  
    [Remove-Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg398941(v=OCS.15))

  - <span></span>  
    [Set-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg399045(v=OCS.15))

**[Lync Server 2013 中的網頁伺服器和服務 Cmdlet](lync-server-2013-web-server-and-services-cmdlets.md)**

  - <span></span>  
    [New-CsSimpleUrl](https://technet.microsoft.com/library/Gg398180(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))

  - <span></span>  
    [New-CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))

  - <span></span>  
    [Remove-Get-cssimpleurlconfiguration](https://technet.microsoft.com/library/Gg398515(v=OCS.15))

  - <span></span>  
    [Get-cssimpleurlconfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsSimpleUrlEntry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsWebServer](https://technet.microsoft.com/library/Gg398759(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))

  - <span></span>  
    [New-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))

  - <span></span>  
    [Remove-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398266(v=OCS.15))

  - <span></span>  
    [Set-CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsWebTrustedCACertificate](https://technet.microsoft.com/library/Gg412746(v=OCS.15))

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

  - [Test-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))

  - [Test-CsWebAppAnonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))

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

