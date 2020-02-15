---
title: 'Lync Server 2013: cmdlet 索引'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 cmdlets index
ms:assetid: cd37aba7-3d27-4db9-b69f-3a6da1fb4b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398867(v=OCS.15)
ms:contentKeyID: 48185661
ms.date: 04/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ca2367ebe47d5abde48a11f06be49d4a6d6ea35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-index"></a>Lync Server 2013 cmdlet 索引

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016年-04-12_

Microsoft Lync Server 2013 隨附於多個 700 cmdlet 可讓系統管理員可以從命令列管理 Lync Server 2013。 Lync Server cmdlet 通常會搭配 Lync Server 管理命令介面。 若要使用 Lync Server 管理命令介面的一種方式是登入執行 Lync Server 服務或伺服器角色的電腦，按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下 [ **Lync Server 管理命令介面**。 管理命令介面是開啟之後可以輸入與下列類似的命令，以擷取直接從命令列指令程式的說明：

    Get-Help New-CsVoicePolicy -Full

上述命令會擷取可用**New-csvoicepolicy** cmdlet 的完整說明。 若要檢視不同 cmdlet 的說明，請替換**New-csvoicepolicy**您要擷取說明的指令程式的名稱。

若要擷取 cmdlet 可用於管理 Lync Server 的完整清單，請在 Lync Server 管理命令介面命令提示字元處輸入下列命令：

    Get-Command * -Module Lync -CommandType cmdlet

如需使用 Lync Server 管理命令介面的詳細資訊，請參閱 Lync Server Windows PowerShell 部落格[http://go.microsoft.com/fwlink/p/?linkId=203150](http://go.microsoft.com/fwlink/p/?linkid=203150)。

<div>

## <a name="lync-server-2013-cmdlets"></a>Lync Server 2013 Cmdlet

以下是隨附 Lync Server 2013 的 cmdlet 清單：

  - [新增 CsSlaDelegates](https://technet.microsoft.com/library/Mt703199(v=OCS.15))

  - [核准 CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398949(v=OCS.15))

  - [Backup-cspool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))

  - [清除 CsDeviceUpdateFile](https://technet.microsoft.com/library/Gg425835(v=OCS.15))

  - [清除 CsDeviceUpdateLog](https://technet.microsoft.com/library/Gg412738(v=OCS.15))

  - [Clear-cspersistentchatroom](https://technet.microsoft.com/library/JJ204976(v=OCS.15))

  - [Convert-csuserdata](https://technet.microsoft.com/library/JJ205337(v=OCS.15))

  - [Debug-csaddressbookreplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))

  - [Debug-csintrapoolreplication](https://technet.microsoft.com/library/JJ205103(v=OCS.15))

  - [偵錯 CsLisConfiguration](https://technet.microsoft.com/library/Gg398710(v=OCS.15))

  - [Disable-csaddomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))

  - [Disable-csadforest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))

  - [Disable-cscomputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))

  - [停用 CsHostingProvider](https://technet.microsoft.com/library/Gg398481(v=OCS.15))

  - [Disable-csmeetingroom](https://technet.microsoft.com/library/JJ204723(v=OCS.15))

  - [停用 CsPublicProvider](https://technet.microsoft.com/library/Gg398984(v=OCS.15))

  - [Disable-csuser](https://technet.microsoft.com/library/Gg398747(v=OCS.15))

  - [Enable-csaddomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))

  - [Enable-csadforest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))

  - [Enable-cscomputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))

  - [啟用 CsHostingProvider](https://technet.microsoft.com/library/Gg398166(v=OCS.15))

  - [Enable-csmeetingroom](https://technet.microsoft.com/library/JJ205062(v=OCS.15))

  - [啟用 CsPublicProvider](https://technet.microsoft.com/library/Gg398780(v=OCS.15))

  - [Enable-csreplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))

  - [Enable-cstopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))

  - [啟用 Get-csuser](https://technet.microsoft.com/library/Gg398711(v=OCS.15))

  - [Export-csarchivingdata](https://technet.microsoft.com/library/Gg398452(v=OCS.15))

  - [Export-csconfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))

  - [Export-cslisconfiguration](https://technet.microsoft.com/library/Gg398539(v=OCS.15))

  - [Export-cspersistentchatdata](https://technet.microsoft.com/library/JJ205378(v=OCS.15))

  - [Export-csrgsconfiguration](https://technet.microsoft.com/library/JJ205011(v=OCS.15))

  - [Export-csuserdata](https://technet.microsoft.com/library/JJ204897(v=OCS.15))

  - [Get-csaccessedgeconfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))

  - [Get-csadcontact](https://technet.microsoft.com/library/Gg412776(v=OCS.15))

  - [Get-csaddomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))

  - [Get-csaddressbookconfiguration cmdlet](https://technet.microsoft.com/library/Gg398132(v=OCS.15))

  - [Get-csadforest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))

  - [Get-csadminrole](https://technet.microsoft.com/library/Gg399050(v=OCS.15))

  - [Get-csadminroleassignment](https://technet.microsoft.com/library/Gg398434(v=OCS.15))

  - [Get-csadprincipal](https://technet.microsoft.com/library/JJ205326(v=OCS.15))

  - [Get-csadserverschema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))

  - [Get-csaduser](https://technet.microsoft.com/library/Gg398592(v=OCS.15))

  - [Get-csalloweddomain](https://technet.microsoft.com/library/Gg398164(v=OCS.15))

  - [Get-csanalogdevice](https://technet.microsoft.com/library/Gg398748(v=OCS.15))

  - [取得 CsAnnouncement](https://technet.microsoft.com/library/Gg398937(v=OCS.15))

  - [取得 CsApplicationEndpoint](https://technet.microsoft.com/library/Gg398655(v=OCS.15))

  - [Get-csarchivingconfiguration](https://technet.microsoft.com/library/Gg399012(v=OCS.15))

  - [Get-csarchivingpolicy](https://technet.microsoft.com/library/Gg425731(v=OCS.15))

  - [Get-csaudiotestserviceapplication](https://technet.microsoft.com/library/Gg412984(v=OCS.15))

  - [Get-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh690014(v=OCS.15))

  - [Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))

  - [Get-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ205087(v=OCS.15))

  - [Get-csbackupservicestatus](https://technet.microsoft.com/library/JJ205032(v=OCS.15))

  - [取得 CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412727(v=OCS.15))

  - [Get-csblockeddomain](https://technet.microsoft.com/library/Gg398424(v=OCS.15))

  - [Get-cscallparkorbit](https://technet.microsoft.com/library/Gg398554(v=OCS.15))

  - [Get-cscdrconfiguration](https://technet.microsoft.com/library/Gg398298(v=OCS.15))

  - [Get-cscertificate](https://technet.microsoft.com/library/Gg398227(v=OCS.15))

  - [Get-csclientaccesslicense](https://technet.microsoft.com/library/JJ204853(v=OCS.15))

  - [Get-csclientcertificate](https://technet.microsoft.com/library/Gg398143(v=OCS.15))

  - [Get-csclientpininfo](https://technet.microsoft.com/library/Gg425947(v=OCS.15))

  - [Get-csclientpolicy](https://technet.microsoft.com/library/Gg398830(v=OCS.15))

  - [Get-csclientversionconfiguration](https://technet.microsoft.com/library/Gg399072(v=OCS.15))

  - [Get-csclientversionpolicy](https://technet.microsoft.com/library/Gg398957(v=OCS.15))

  - [Get-csclientversionpolicyrule](https://technet.microsoft.com/library/Gg413048(v=OCS.15))

  - [Get-csclsregion](https://technet.microsoft.com/library/JJ204879(v=OCS.15))

  - [Get-csclssearchterm](https://technet.microsoft.com/library/JJ205061(v=OCS.15))

  - [Get-csclsscenario](https://technet.microsoft.com/library/JJ205091(v=OCS.15))

  - [Get-csclssecuritygroup](https://technet.microsoft.com/library/JJ205285(v=OCS.15))

  - [Get-cscommonareaphone](https://technet.microsoft.com/library/Gg412934(v=OCS.15))

  - [Get-cscomputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))

  - [Get-csconferencedirectory](https://technet.microsoft.com/library/Gg425771(v=OCS.15))

  - [Get-csconferencedisclaimer](https://technet.microsoft.com/library/Gg425714(v=OCS.15))

  - [Get-csconferencingconfiguration](https://technet.microsoft.com/library/Gg398965(v=OCS.15))

  - [Get-csconferencingpolicy](https://technet.microsoft.com/library/Gg398293(v=OCS.15))

  - [Get-csconfigurationstorelocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))

  - [取得 CsCpsConfiguration](https://technet.microsoft.com/library/Gg398948(v=OCS.15))

  - [Get-csdatabasemirrorstate](https://technet.microsoft.com/library/JJ204845(v=OCS.15))

  - [Get-csdeviceupdateconfiguration](https://technet.microsoft.com/library/Gg399030(v=OCS.15))

  - [Get-csdeviceupdaterule](https://technet.microsoft.com/library/Gg398215(v=OCS.15))

  - [Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg413034(v=OCS.15))

  - [Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg412774(v=OCS.15))

  - [Get-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg413015(v=OCS.15))

  - [Get-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg398575(v=OCS.15))

  - [Get-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg398578(v=OCS.15))

  - [Get-csdialinconferencinglanguagelist](https://technet.microsoft.com/library/Gg425869(v=OCS.15))

  - [Get-csdialplan](https://technet.microsoft.com/library/Gg413043(v=OCS.15))

  - [Get-cseffectivepolicy](https://technet.microsoft.com/library/JJ204636(v=OCS.15))

  - [取得 CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg412877(v=OCS.15))

  - [Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))

  - [Get-csexumcontact](https://technet.microsoft.com/library/Gg412725(v=OCS.15))

  - [Get-csfiletransferfilterconfiguration](https://technet.microsoft.com/library/Gg398527(v=OCS.15))

  - [Get-csfipsconfiguration](https://technet.microsoft.com/library/JJ204904(v=OCS.15))

  - [Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg398667(v=OCS.15))

  - [Get-cshostedvoicemailpolicy](https://technet.microsoft.com/library/Gg398348(v=OCS.15))

  - [Get-cshostingprovider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))

  - [Get-csimfilterconfiguration](https://technet.microsoft.com/library/Gg398980(v=OCS.15))

  - [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))

  - [取得 CsLisCivicAddress](https://technet.microsoft.com/library/Gg398459(v=OCS.15))

  - [Get-cslislocation](https://technet.microsoft.com/library/Gg412834(v=OCS.15))

  - [取得 CsLisPort](https://technet.microsoft.com/library/Gg398820(v=OCS.15))

  - [取得 CsLisServiceProvider](https://technet.microsoft.com/library/Gg398116(v=OCS.15))

  - [取得 CsLisSubnet](https://technet.microsoft.com/library/Gg398473(v=OCS.15))

  - [取得 CsLisSwitch](https://technet.microsoft.com/library/Gg425769(v=OCS.15))

  - [取得 CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398117(v=OCS.15))

  - [Get-cslocationpolicy](https://technet.microsoft.com/library/Gg398911(v=OCS.15))

  - [Get-csmanagementconnection](https://technet.microsoft.com/library/Gg412849(v=OCS.15))

  - [Get-csmanagementstorereplicationstatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))

  - [Get-csmcxconfiguration](https://technet.microsoft.com/library/Hh690031(v=OCS.15))

  - [Get-csmediaconfiguration cmdlet](https://technet.microsoft.com/library/Gg398128(v=OCS.15))

  - [Get-csmeetingconfiguration](https://technet.microsoft.com/library/Gg425875(v=OCS.15))

  - [Get-csmeetingroom](https://technet.microsoft.com/library/JJ205277(v=OCS.15))

  - [Get-csmobilitypolicy](https://technet.microsoft.com/library/Hh690017(v=OCS.15))

  - [Get-csnetworkbandwidthpolicyprofile](https://technet.microsoft.com/library/Gg425815(v=OCS.15))

  - [Get-csnetworkconfiguration](https://technet.microsoft.com/library/Gg398140(v=OCS.15))

  - [Get-csnetworkinterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))

  - [Get-csnetworkinterregionroute](https://technet.microsoft.com/library/Gg425817(v=OCS.15))

  - [Get-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg412769(v=OCS.15))

  - [Get-csnetworkregion](https://technet.microsoft.com/library/Gg398406(v=OCS.15))

  - [Get-csnetworkregionlink](https://technet.microsoft.com/library/Gg398972(v=OCS.15))

  - [Get-csnetworksite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))

  - [Get-csnetworksubnet](https://technet.microsoft.com/library/Gg412825(v=OCS.15))

  - [Get-csoauthconfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))

  - [Get-csoauthserver](https://technet.microsoft.com/library/JJ205238(v=OCS.15))

  - [Get-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ204962(v=OCS.15))

  - [取得 CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398104(v=OCS.15))

  - [Get-cspartnerapplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))

  - [Get-cspersistentchataddin](https://technet.microsoft.com/library/JJ204670(v=OCS.15))

  - [Get-cspersistentchatcategory](https://technet.microsoft.com/library/JJ204771(v=OCS.15))

  - [Get-cspersistentchatcomplianceconfiguration](https://technet.microsoft.com/library/JJ204625(v=OCS.15))

  - [Get-cspersistentchatconfiguration](https://technet.microsoft.com/library/JJ205140(v=OCS.15))

  - [Get-cspersistentchateligibleprincipal](https://technet.microsoft.com/library/JJ204891(v=OCS.15))

  - [Get-cspersistentchatendpoint](https://technet.microsoft.com/library/JJ204764(v=OCS.15))

  - [Get-cspersistentchatpolicy](https://technet.microsoft.com/library/JJ204673(v=OCS.15))

  - [Get-cspersistentchatroom](https://technet.microsoft.com/library/JJ205123(v=OCS.15))

  - [Get-cspersistentchatstate](https://technet.microsoft.com/library/JJ204915(v=OCS.15))

  - [Get-cspinpolicy](https://technet.microsoft.com/library/Gg398262(v=OCS.15))

  - [Get-cspool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))

  - [Get-cspoolbackuprelationship](https://technet.microsoft.com/library/JJ204745(v=OCS.15))

  - [Get-cspoolupgradereadinessstate](https://technet.microsoft.com/library/JJ204689(v=OCS.15))

  - [Get-cspresencepolicy](https://technet.microsoft.com/library/Gg398463(v=OCS.15))

  - [Get-cspresenceprovider](https://technet.microsoft.com/library/JJ204705(v=OCS.15))

  - [Get-csprivacyconfiguration](https://technet.microsoft.com/library/Gg413002(v=OCS.15))

  - [Get-csproxyconfiguration](https://technet.microsoft.com/library/Gg399011(v=OCS.15))

  - [Get-cspstnusage](https://technet.microsoft.com/library/Gg412734(v=OCS.15))

  - [取得 CsPublicProvider](https://technet.microsoft.com/library/Gg412945(v=OCS.15))

  - [Get-cspushnotificationconfiguration](https://technet.microsoft.com/library/Hh690049(v=OCS.15))

  - [Get-csqoeconfiguration](https://technet.microsoft.com/library/Gg399004(v=OCS.15))

  - [Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg398483(v=OCS.15))

  - [Get-csreportingconfiguration](https://technet.microsoft.com/library/JJ205356(v=OCS.15))

  - [Get-csrgsagentgroup](https://technet.microsoft.com/library/Gg425793(v=OCS.15))

  - [Get-csrgsconfiguration](https://technet.microsoft.com/library/Gg412762(v=OCS.15))

  - [Get-csrgsholidayset](https://technet.microsoft.com/library/Gg412983(v=OCS.15))

  - [Get-csrgshoursofbusiness](https://technet.microsoft.com/library/Gg398284(v=OCS.15))

  - [Get-csrgsqueue](https://technet.microsoft.com/library/Gg412759(v=OCS.15))

  - [Get-csrgsworkflow](https://technet.microsoft.com/library/Gg425766(v=OCS.15))

  - [Get-csroutingconfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))

  - [Get-csserverapplication](https://technet.microsoft.com/library/Gg425948(v=OCS.15))

  - [Get-csserverversion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))

  - [Get-csservice](https://technet.microsoft.com/library/Gg413038(v=OCS.15))

  - [Get-cssimpleurlconfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))

  - [Get-cssipdomain](https://technet.microsoft.com/library/Gg398701(v=OCS.15))

  - [Get-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg398130(v=OCS.15))

  - [取得 CsSlaConfiguration](https://technet.microsoft.com/library/Mt703200(v=OCS.15))

  - [Get-cssite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))

  - [Get-csstaticroutingconfiguration](https://technet.microsoft.com/library/Gg398754(v=OCS.15))

  - [Get-cstestdevice](https://technet.microsoft.com/library/Gg398304(v=OCS.15))

  - [Get-cstestusercredential](https://technet.microsoft.com/library/JJ204759(v=OCS.15))

  - [Get-cstopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))

  - [Get-cstrunk](https://technet.microsoft.com/library/JJ205244(v=OCS.15))

  - [Get-cstrunkconfiguration](https://technet.microsoft.com/library/Gg398224(v=OCS.15))

  - [Get-cstrustedapplication](https://technet.microsoft.com/library/Gg399025(v=OCS.15))

  - [取得 CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg425843(v=OCS.15))

  - [取得 CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg413035(v=OCS.15))

  - [取得 CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg413055(v=OCS.15))

  - [Get-csucphoneconfiguration](https://technet.microsoft.com/library/Gg398070(v=OCS.15))

  - [Get-csuiculture](https://technet.microsoft.com/library/Gg412900(v=OCS.15))

  - [取得 CsUnassignedNumber](https://technet.microsoft.com/library/Gg412792(v=OCS.15))

  - [Get-csuser](https://technet.microsoft.com/library/Gg398125(v=OCS.15))

  - [Get-csuseracp](https://technet.microsoft.com/library/Gg398978(v=OCS.15))

  - [Get-csuserdatabasestate](https://technet.microsoft.com/library/Gg398831(v=OCS.15))

  - [Get-csuserpoolinfo](https://technet.microsoft.com/library/Gg398615(v=OCS.15))

  - [Get-csuserreplicatorconfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))

  - [Get-csuserservicesconfiguration](https://technet.microsoft.com/library/Gg398133(v=OCS.15))

  - [Get-csuserservicespolicy](https://technet.microsoft.com/library/JJ204838(v=OCS.15))

  - [取得 CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398815(v=OCS.15))

  - [Get-csvoicemailreroutingconfiguration](https://technet.microsoft.com/library/Gg425732(v=OCS.15))

  - [Get-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg398393(v=OCS.15))

  - [Get-csvoicepolicy](https://technet.microsoft.com/library/Gg398101(v=OCS.15))

  - [Get-csvoiceroute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))

  - [Get-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ204940(v=OCS.15))

  - [取得 Test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg412957(v=OCS.15))

  - [Get-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204739(v=OCS.15))

  - [Get-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))

  - [Get-cswindowsservice](https://technet.microsoft.com/library/Gg398803(v=OCS.15))

  - [Get-csxmppallowedpartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))

  - [Get-csxmppgatewayconfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))

  - [Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg398475(v=OCS.15))

  - [Grant-csclientpolicy](https://technet.microsoft.com/library/Gg412942(v=OCS.15))

  - [Grant-csclientversionpolicy](https://technet.microsoft.com/library/Gg412903(v=OCS.15))

  - [Grant-csconferencingpolicy](https://technet.microsoft.com/library/Gg425937(v=OCS.15))

  - [Grant-csdialplan](https://technet.microsoft.com/library/Gg398547(v=OCS.15))

  - [Grant-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg425942(v=OCS.15))

  - [授與 CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg412829(v=OCS.15))

  - [Grant-cslocationpolicy](https://technet.microsoft.com/library/Gg413049(v=OCS.15))

  - [Grant-csmobilitypolicy](https://technet.microsoft.com/library/Hh690038(v=OCS.15))

  - [Grant-csoupermission](https://technet.microsoft.com/library/Gg425739(v=OCS.15))

  - [授與 CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ204907(v=OCS.15))

  - [授與 CsPinPolicy](https://technet.microsoft.com/library/Gg398871(v=OCS.15))

  - [Grant-cspresencepolicy](https://technet.microsoft.com/library/Gg398571(v=OCS.15))

  - [Grant-cssetuppermission](https://technet.microsoft.com/library/Gg398569(v=OCS.15))

  - [Grant-csuserservicespolicy](https://technet.microsoft.com/library/JJ205388(v=OCS.15))

  - [Grant-csvoicepolicy](https://technet.microsoft.com/library/Gg398828(v=OCS.15))

  - [Grant-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ205141(v=OCS.15))

  - [Import-csannouncementfile](https://technet.microsoft.com/library/Gg398472(v=OCS.15))

  - [匯入 Set-cscertificate](https://technet.microsoft.com/library/Gg398688(v=OCS.15))

  - [Import-csconfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))

  - [Import-csdeviceupdate](https://technet.microsoft.com/library/Gg398861(v=OCS.15))

  - [Import-cslegacyconferencedirectory cmdlet](https://technet.microsoft.com/library/Gg398418(v=OCS.15))

  - [Import-cslegacyconfiguration](https://technet.microsoft.com/library/Gg412923(v=OCS.15))

  - [匯入 CsLisConfiguration](https://technet.microsoft.com/library/Gg398380(v=OCS.15))

  - [Import-cspersistentchatdata](https://technet.microsoft.com/library/JJ204709(v=OCS.15))

  - [Import-csrgsaudiofile](https://technet.microsoft.com/library/Gg412830(v=OCS.15))

  - [Import-csrgsconfiguration](https://technet.microsoft.com/library/JJ205245(v=OCS.15))

  - [Import-csuserdata](https://technet.microsoft.com/library/JJ205373(v=OCS.15))

  - [Install-csadserverschema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))

  - [Install-csdatabase](https://technet.microsoft.com/library/Gg399044(v=OCS.15))

  - [Install-csmirrordatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))

  - [Invoke-csarchivingdatabasepurge](https://technet.microsoft.com/library/JJ204627(v=OCS.15))

  - [叫用 CsBackupServiceSync](https://technet.microsoft.com/library/JJ205374(v=OCS.15))

  - [Invoke-cscdrdatabasepurge](https://technet.microsoft.com/library/JJ205113(v=OCS.15))

  - [叫用 CsDatabaseFailover](https://technet.microsoft.com/library/JJ204744(v=OCS.15))

  - [叫用 CsManagementServerFailover](https://technet.microsoft.com/library/JJ204647(v=OCS.15))

  - [Invoke-csmanagementstorereplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))

  - [叫用 CsPoolFailBack](https://technet.microsoft.com/library/JJ204873(v=OCS.15))

  - [叫用 CsPoolFailOver](https://technet.microsoft.com/library/JJ205189(v=OCS.15))

  - [Invoke-csqoedatabasepurge](https://technet.microsoft.com/library/JJ205247(v=OCS.15))

  - [叫用 CsUcsRollback](https://technet.microsoft.com/library/JJ204661(v=OCS.15))

  - [Lock-csclientpin](https://technet.microsoft.com/library/Gg398650(v=OCS.15))

  - [Merge-cslegacytopology](https://technet.microsoft.com/library/Gg425870(v=OCS.15))

  - [Move-csanalogdevice](https://technet.microsoft.com/library/Gg398816(v=OCS.15))

  - [Move-csapplicationendpoint](https://technet.microsoft.com/library/Gg398188(v=OCS.15))

  - [Move-cscommonareaphone](https://technet.microsoft.com/library/Gg412837(v=OCS.15))

  - [Move-csconferencedirectory](https://technet.microsoft.com/library/Gg412968(v=OCS.15))

  - [Move-csexumcontact](https://technet.microsoft.com/library/Gg425842(v=OCS.15))

  - [Move-cslegacyuser](https://technet.microsoft.com/library/Gg413025(v=OCS.15))

  - [Move-csmanagementserver](https://technet.microsoft.com/library/Gg412921(v=OCS.15))

  - [Move-csmeetingroom](https://technet.microsoft.com/library/JJ204889(v=OCS.15))

  - [Move-csrgsconfiguration](https://technet.microsoft.com/library/Gg398782(v=OCS.15))

  - [Move-csuser](https://technet.microsoft.com/library/Gg398528(v=OCS.15))

  - [New-csaddressbookconfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))

  - [New-csadminrole](https://technet.microsoft.com/library/Gg398271(v=OCS.15))

  - [新 CsAllowedDomain](https://technet.microsoft.com/library/Gg398628(v=OCS.15))

  - [New-csanalogdevice](https://technet.microsoft.com/library/Gg412937(v=OCS.15))

  - [新 CsAnnouncement](https://technet.microsoft.com/library/Gg398522(v=OCS.15))

  - [New-csarchivingconfiguration](https://technet.microsoft.com/library/Gg398471(v=OCS.15))

  - [New-csarchivingpolicy](https://technet.microsoft.com/library/Gg399032(v=OCS.15))

  - [New-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh690022(v=OCS.15))

  - [新 CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))

  - [新 CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398175(v=OCS.15))

  - [新 New-csblockeddomain](https://technet.microsoft.com/library/Gg398822(v=OCS.15))

  - [新 CsCallParkOrbit](https://technet.microsoft.com/library/Gg398936(v=OCS.15))

  - [新 CsCdrConfiguration](https://technet.microsoft.com/library/Gg399018(v=OCS.15))

  - [New-csclientpolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15))

  - [New-csclientpolicyentry](https://technet.microsoft.com/library/Gg399046(v=OCS.15))

  - [新 CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15))

  - [New-csclientversionpolicy](https://technet.microsoft.com/library/Gg398709(v=OCS.15))

  - [New-csclientversionpolicyrule](https://technet.microsoft.com/library/Gg398905(v=OCS.15))

  - [New-csclsregion](https://technet.microsoft.com/library/JJ204658(v=OCS.15))

  - [New-csclsscenario](https://technet.microsoft.com/library/JJ205022(v=OCS.15))

  - [New-csclssecuritygroup](https://technet.microsoft.com/library/JJ205359(v=OCS.15))

  - [New-cscommonareaphone](https://technet.microsoft.com/library/Gg398430(v=OCS.15))

  - [新 CsConferenceDirectory](https://technet.microsoft.com/library/Gg413080(v=OCS.15))

  - [New-csconferencingconfiguration](https://technet.microsoft.com/library/Gg412967(v=OCS.15))

  - [New-csconferencingpolicy](https://technet.microsoft.com/library/Gg413019(v=OCS.15))

  - [新 CsCpsConfiguration](https://technet.microsoft.com/library/Gg412919(v=OCS.15))

  - [新 CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15))

  - [New-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg398733(v=OCS.15))

  - [New-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg398350(v=OCS.15))

  - [New-csdiagnosticsfilter](https://technet.microsoft.com/library/Gg413009(v=OCS.15))

  - [New-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg398818(v=OCS.15))

  - [新 CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg412816(v=OCS.15))

  - [新 CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425792(v=OCS.15))

  - [新 CsDialPlan](https://technet.microsoft.com/library/Gg425860(v=OCS.15))

  - [New-csextendedtest](https://technet.microsoft.com/library/JJ205275(v=OCS.15))

  - [新 CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398441(v=OCS.15))

  - [New-csexumcontact](https://technet.microsoft.com/library/Gg398139(v=OCS.15))

  - [New-csfiletransferfilterconfiguration](https://technet.microsoft.com/library/Gg425897(v=OCS.15))

  - [New-csfipsconfiguration](https://technet.microsoft.com/library/JJ205114(v=OCS.15))

  - [New-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg398718(v=OCS.15))

  - [新 CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398653(v=OCS.15))

  - [新 CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))

  - [新 CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398244(v=OCS.15))

  - [New-csissuedcertid](https://technet.microsoft.com/library/Gg425814(v=OCS.15))

  - [New-cskerberosaccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))

  - [New-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))

  - [新則 CsLocationPolicy](https://technet.microsoft.com/library/Gg398231(v=OCS.15))

  - [新 CsMcxConfiguration](https://technet.microsoft.com/library/Hh690035(v=OCS.15))

  - [新 CsMediaConfiguration](https://technet.microsoft.com/library/Gg425881(v=OCS.15))

  - [新 CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15))

  - [新 CsMobilityPolicy](https://technet.microsoft.com/library/Hh689987(v=OCS.15))

  - [新 CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398675(v=OCS.15))

  - [新 CsNetworkBWAlternatePath](https://technet.microsoft.com/library/Gg398732(v=OCS.15))

  - [新 CsNetworkBWPolicy](https://technet.microsoft.com/library/Gg412916(v=OCS.15))

  - [新 CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398779(v=OCS.15))

  - [新 CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398994(v=OCS.15))

  - [新 CsNetworkMediaBypassConfiguration](https://technet.microsoft.com/library/Gg425718(v=OCS.15))

  - [新 CsNetworkRegion](https://technet.microsoft.com/library/Gg425829(v=OCS.15))

  - [新 CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398437(v=OCS.15))

  - [新 CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))

  - [新 CsNetworkSubnet](https://technet.microsoft.com/library/Gg398226(v=OCS.15))

  - [New-csoauthserver](https://technet.microsoft.com/library/JJ205206(v=OCS.15))

  - [New-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ205097(v=OCS.15))

  - [新 CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg412803(v=OCS.15))

  - [New-cspartnerapplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))

  - [New-cspersistentchataddin](https://technet.microsoft.com/library/JJ204641(v=OCS.15))

  - [New-cspersistentchatcategory](https://technet.microsoft.com/library/JJ204803(v=OCS.15))

  - [New-cspersistentchatcomplianceconfiguration](https://technet.microsoft.com/library/JJ205163(v=OCS.15))

  - [New-cspersistentchatconfiguration](https://technet.microsoft.com/library/JJ205330(v=OCS.15))

  - [New-cspersistentchatendpoint](https://technet.microsoft.com/library/JJ204811(v=OCS.15))

  - [New-cspersistentchatpolicy](https://technet.microsoft.com/library/JJ205396(v=OCS.15))

  - [New-cspersistentchatroom](https://technet.microsoft.com/library/JJ205166(v=OCS.15))

  - [新 CsPinPolicy](https://technet.microsoft.com/library/Gg398935(v=OCS.15))

  - [New-cspresencepolicy](https://technet.microsoft.com/library/Gg412747(v=OCS.15))

  - [New-cspresenceprovider](https://technet.microsoft.com/library/JJ204895(v=OCS.15))

  - [New-csprivacyconfiguration](https://technet.microsoft.com/library/Gg398807(v=OCS.15))

  - [New-csproxyconfiguration](https://technet.microsoft.com/library/Gg398335(v=OCS.15))

  - [新 CsPublicProvider](https://technet.microsoft.com/library/Gg398161(v=OCS.15))

  - [New-cspushnotificationconfiguration](https://technet.microsoft.com/library/Hh690027(v=OCS.15))

  - [新 CsQoEConfiguration](https://technet.microsoft.com/library/Gg398325(v=OCS.15))

  - [New-csregistrarconfiguration](https://technet.microsoft.com/library/Gg425893(v=OCS.15))

  - [New-csreportingconfiguration](https://technet.microsoft.com/library/JJ204787(v=OCS.15))

  - [New-csrgsagentgroup](https://technet.microsoft.com/library/Gg413065(v=OCS.15))

  - [新 CsRgsAnswer](https://technet.microsoft.com/library/Gg412812(v=OCS.15))

  - [新 CsRgsCallAction](https://technet.microsoft.com/library/Gg398136(v=OCS.15))

  - [New-csrgsholiday](https://technet.microsoft.com/library/Gg398075(v=OCS.15))

  - [New-csrgsholidayset](https://technet.microsoft.com/library/Gg398403(v=OCS.15))

  - [新 CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg398291(v=OCS.15))

  - [New-csrgsprompt](https://technet.microsoft.com/library/Gg398486(v=OCS.15))

  - [New-csrgsquestion](https://technet.microsoft.com/library/Gg398186(v=OCS.15))

  - [New-csrgsqueue](https://technet.microsoft.com/library/Gg398989(v=OCS.15))

  - [New-csrgstimerange](https://technet.microsoft.com/library/Gg399040(v=OCS.15))

  - [New-csrgsworkflow](https://technet.microsoft.com/library/Gg398246(v=OCS.15))

  - [新 CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))

  - [New-csserverapplication](https://technet.microsoft.com/library/Gg398096(v=OCS.15))

  - [New-cssimpleurl](https://technet.microsoft.com/library/Gg398180(v=OCS.15))

  - [New-cssimpleurlconfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))

  - [New-cssimpleurlentry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))

  - [New-cssipdomain](https://technet.microsoft.com/library/Gg425857(v=OCS.15))

  - [New-cssipproxycustom](https://technet.microsoft.com/library/Gg425904(v=OCS.15))

  - [New-cssipproxyrealm](https://technet.microsoft.com/library/Gg413084(v=OCS.15))

  - [New-cssipproxytcp](https://technet.microsoft.com/library/Gg425745(v=OCS.15))

  - [New-cssipproxytls](https://technet.microsoft.com/library/Gg398629(v=OCS.15))

  - [New-cssipproxytransport](https://technet.microsoft.com/library/Gg398489(v=OCS.15))

  - [New-cssipproxyusedefault](https://technet.microsoft.com/library/Gg398274(v=OCS.15))

  - [New-cssipproxyusedefaultcert](https://technet.microsoft.com/library/Gg425858(v=OCS.15))

  - [New-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg413041(v=OCS.15))

  - [New-csstaticroute](https://technet.microsoft.com/library/Gg398265(v=OCS.15))

  - [New-csstaticroutingconfiguration](https://technet.microsoft.com/library/Gg425811(v=OCS.15))

  - [新 CsTestDevice](https://technet.microsoft.com/library/Gg425899(v=OCS.15))

  - [新 Test-cstrunkconfiguration](https://technet.microsoft.com/library/Gg413021(v=OCS.15))

  - [新 CsTrustedApplication](https://technet.microsoft.com/library/Gg398259(v=OCS.15))

  - [新 CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398405(v=OCS.15))

  - [新 CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398594(v=OCS.15))

  - [新 CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg425804(v=OCS.15))

  - [新 CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))

  - [新 CsUnassignedNumber](https://technet.microsoft.com/library/Gg398651(v=OCS.15))

  - [New-csuserreplicatorconfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))

  - [New-csuserservicesconfiguration](https://technet.microsoft.com/library/Gg412926(v=OCS.15))

  - [New-csuserservicespolicy](https://technet.microsoft.com/library/JJ205072(v=OCS.15))

  - [新 CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg425849(v=OCS.15))

  - [新來](https://technet.microsoft.com/library/Gg398240(v=OCS.15))

  - [新 CsVoicePolicy](https://technet.microsoft.com/library/Gg425856(v=OCS.15))

  - [新 CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))

  - [新 CsVoiceRoute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))

  - [New-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ205135(v=OCS.15))

  - [新 Test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398961(v=OCS.15))

  - [New-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ205254(v=OCS.15))

  - [新 CsWebLink](https://technet.microsoft.com/library/Hh690053(v=OCS.15))

  - [New-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))

  - [New-cswebtrustedcacertificate](https://technet.microsoft.com/library/Gg412746(v=OCS.15))

  - [New-csxmppallowedpartner](https://technet.microsoft.com/library/JJ204631(v=OCS.15))

  - [發佈 CsLisConfiguration](https://technet.microsoft.com/library/Gg398364(v=OCS.15))

  - [Publish-cstopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))

  - [Remove-csaddressbookconfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))

  - [Remove-csadminrole](https://technet.microsoft.com/library/Gg413036(v=OCS.15))

  - [移除 CsAllowedDomain](https://technet.microsoft.com/library/Gg398913(v=OCS.15))

  - [Remove-csanalogdevice](rehttps://technet.microsoft.com/library/Gg398816(v=OCS.15))

  - [移除 CsAnnouncement](https://technet.microsoft.com/library/Gg412766(v=OCS.15))

  - [Remove-csarchivingconfiguration](https://technet.microsoft.com/library/Gg398951(v=OCS.15))

  - [Remove-csarchivingpolicy](https://technet.microsoft.com/library/Gg425924(v=OCS.15))

  - [Remove-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh690054(v=OCS.15))

  - [Remove-csavedgeconfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))

  - [Remove-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ204903(v=OCS.15))

  - [移除 CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398877(v=OCS.15))

  - [移除 New-csblockeddomain](https://technet.microsoft.com/library/Gg425832(v=OCS.15))

  - [Remove-cscallparkorbit](https://technet.microsoft.com/library/Gg412901(v=OCS.15))

  - [Remove-cscdrconfiguration](https://technet.microsoft.com/library/Gg398451(v=OCS.15))

  - [移除 Set-cscertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))

  - [Remove-csclientpolicy](https://technet.microsoft.com/library/Gg425772(v=OCS.15))

  - [移除 CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15))

  - [Remove-csclientversionpolicy](https://technet.microsoft.com/library/Gg425801(v=OCS.15))

  - [移除 CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398541(v=OCS.15))

  - [Remove-csclsregion](https://technet.microsoft.com/library/JJ204971(v=OCS.15))

  - [Remove-csclsscenario](https://technet.microsoft.com/library/JJ205010(v=OCS.15))

  - [Remove-csclssecuritygroup](https://technet.microsoft.com/library/JJ204958(v=OCS.15))

  - [Remove-cscommonareaphone](rehttps://technet.microsoft.com/library/Gg412837(v=OCS.15))

  - [Remove-csconferencedirectory](rehttps://technet.microsoft.com/library/Gg412968(v=OCS.15))

  - [移除 CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398243(v=OCS.15))

  - [移除可](https://technet.microsoft.com/library/Gg412767(v=OCS.15))

  - [Remove-csconferencingpolicy](https://technet.microsoft.com/library/Gg398728(v=OCS.15))

  - [Remove-csconfigurationstorelocation](https://technet.microsoft.com/library/Gg398214(v=OCS.15))

  - [移除 CsCpsConfiguration](https://technet.microsoft.com/library/Gg398358(v=OCS.15))

  - [移除 CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425933(v=OCS.15))

  - [移除 CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg425930(v=OCS.15))

  - [移除 CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg412853(v=OCS.15))

  - [移除 CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398941(v=OCS.15))

  - [Remove-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg412782(v=OCS.15))

  - [移除 CsDialInConferencingConfiguration](https://technet.microsoft.com/library/Gg398174(v=OCS.15))

  - [移除 CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/library/Gg425894(v=OCS.15))

  - [移除 CsDialPlan](https://technet.microsoft.com/library/Gg398791(v=OCS.15))

  - [移除 CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg425810(v=OCS.15))

  - [Remove-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg399057(v=OCS.15))

  - [移除 Get-csexumcontact](rehttps://technet.microsoft.com/library/Gg425842(v=OCS.15))

  - [Remove-csfiletransferfilterconfiguration](https://technet.microsoft.com/library/Gg413064(v=OCS.15))

  - [Remove-csfipsconfiguration](https://technet.microsoft.com/library/JJ205201(v=OCS.15))

  - [Remove-csclientpolicy](https://technet.microsoft.com/library/Gg425794(v=OCS.15))

  - [移除 CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398211(v=OCS.15))

  - [移除 CsHostingProvider](https://technet.microsoft.com/library/Gg425809(v=OCS.15))

  - [移除 CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398171(v=OCS.15))

  - [移除 CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))

  - [移除 CsLisLocation](https://technet.microsoft.com/library/Gg425722(v=OCS.15))

  - [移除 CsLisPort](https://technet.microsoft.com/library/Gg412899(v=OCS.15))

  - [移除 CsLisServiceProvider](https://technet.microsoft.com/library/Gg398904(v=OCS.15))

  - [移除 CsLisSubnet](https://technet.microsoft.com/library/Gg413053(v=OCS.15))

  - [移除 CsLisSwitch](https://technet.microsoft.com/library/Gg398352(v=OCS.15))

  - [移除 CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398461(v=OCS.15))

  - [移除則 CsLocationPolicy](https://technet.microsoft.com/library/Gg398727(v=OCS.15))

  - [移除 CsManagementConnection](https://technet.microsoft.com/library/Gg425803(v=OCS.15))

  - [Remove-csmcxconfiguration](https://technet.microsoft.com/library/Hh690026(v=OCS.15))

  - [移除 CsMediaConfiguration](https://technet.microsoft.com/library/Gg398705(v=OCS.15))

  - [Remove-csmeetingconfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15))

  - [Remove-csmobilitypolicy](https://technet.microsoft.com/library/Hh690048(v=OCS.15))

  - [移除 CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398609(v=OCS.15))

  - [移除 CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398938(v=OCS.15))

  - [移除 CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398743(v=OCS.15))

  - [Remove-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg398963(v=OCS.15))

  - [移除 CsNetworkRegion](https://technet.microsoft.com/library/Gg398466(v=OCS.15))

  - [移除 CsNetworkRegionLink](https://technet.microsoft.com/library/Gg413012(v=OCS.15))

  - [移除 CsNetworkSite](https://technet.microsoft.com/library/Gg398135(v=OCS.15))

  - [移除 CsNetworkSubnet](https://technet.microsoft.com/library/Gg425726(v=OCS.15))

  - [Remove-csoauthserver](https://technet.microsoft.com/library/JJ205408(v=OCS.15))

  - [Remove-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ204836(v=OCS.15))

  - [移除 CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398556(v=OCS.15))

  - [Remove-cspartnerapplication](https://technet.microsoft.com/library/JJ204820(v=OCS.15))

  - [移除 CsPersistentChatAddin](https://technet.microsoft.com/library/JJ205350(v=OCS.15))

  - [移除 CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204660(v=OCS.15))

  - [Remove-cspersistentchatcomplianceconfiguration](https://technet.microsoft.com/library/JJ204767(v=OCS.15))

  - [Remove-cspersistentchatconfiguration](https://technet.microsoft.com/library/JJ204927(v=OCS.15))

  - [Remove-cspersistentchatendpoint](https://technet.microsoft.com/library/JJ204626(v=OCS.15))

  - [移除 CsPersistentChatMessage](https://technet.microsoft.com/library/JJ204668(v=OCS.15))

  - [Remove-cspersistentchatpolicy](https://technet.microsoft.com/library/JJ205301(v=OCS.15))

  - [Remove-cspersistentchatroom](https://technet.microsoft.com/library/JJ204639(v=OCS.15))

  - [Remove-cspinpolicy](https://technet.microsoft.com/library/Gg398431(v=OCS.15))

  - [移除 CsPresencePolicy](https://technet.microsoft.com/library/Gg399070(v=OCS.15))

  - [Remove-cspresenceprovider](https://technet.microsoft.com/library/JJ205036(v=OCS.15))

  - [移除 CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg425821(v=OCS.15))

  - [Remove-csproxyconfiguration](https://technet.microsoft.com/library/Gg398553(v=OCS.15))

  - [移除 CsPublicProvider](https://technet.microsoft.com/library/Gg412906(v=OCS.15))

  - [Remove-cspushnotificationconfiguration](https://technet.microsoft.com/library/Hh690028(v=OCS.15))

  - [Remove-csqoeconfiguration](https://technet.microsoft.com/library/Gg425879(v=OCS.15))

  - [移除 CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398482(v=OCS.15))

  - [Remove-csreportingconfiguration](https://technet.microsoft.com/library/JJ204711(v=OCS.15))

  - [Remove-csrgsagentgroup](https://technet.microsoft.com/library/Gg398969(v=OCS.15))

  - [Remove-csrgsholidayset](https://technet.microsoft.com/library/Gg398521(v=OCS.15))

  - [移除 CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg398568(v=OCS.15))

  - [Remove-csrgsqueue](https://technet.microsoft.com/library/Gg398576(v=OCS.15))

  - [Remove-csrgsworkflow](https://technet.microsoft.com/library/Gg398765(v=OCS.15))

  - [移除 CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))

  - [Remove-csserverapplication](https://technet.microsoft.com/library/Gg398366(v=OCS.15))

  - [移除 CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398515(v=OCS.15))

  - [移除 CsSipDomain](https://technet.microsoft.com/library/Gg398865(v=OCS.15))

  - [Remove-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg412932(v=OCS.15))

  - [移除 CsSlaConfiguration](https://technet.microsoft.com/library/Mt703201(v=OCS.15))

  - [移除 CsSlaDelegates](https://technet.microsoft.com/library/Mt703203(v=OCS.15))

  - [移除 New-csstaticroutingconfiguration](https://technet.microsoft.com/library/Gg398668(v=OCS.15))

  - [移除 CsTestDevice](https://technet.microsoft.com/library/Gg398790(v=OCS.15))

  - [Remove-cstestusercredential](https://technet.microsoft.com/library/JJ204870(v=OCS.15))

  - [Remove-cstrunkconfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15))

  - [Remove-cstrustedapplication](https://technet.microsoft.com/library/Gg398176(v=OCS.15))

  - [移除 CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398838(v=OCS.15))

  - [移除 CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398837(v=OCS.15))

  - [移除 CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg398750(v=OCS.15))

  - [移除 CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15))

  - [移除 CsUnassignedNumber](https://technet.microsoft.com/library/Gg398209(v=OCS.15))

  - [移除 CsUserAcp](https://technet.microsoft.com/library/Gg398982(v=OCS.15))

  - [移除 CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))

  - [移除 CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398722(v=OCS.15))

  - [Remove-csuserservicespolicy](https://technet.microsoft.com/library/JJ204629(v=OCS.15))

  - [Remove-csuserstorebackupdata](https://technet.microsoft.com/library/JJ205003(v=OCS.15))

  - [移除 CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398804(v=OCS.15))

  - [移除 CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg398573(v=OCS.15))

  - [移除來](https://technet.microsoft.com/library/Gg398501(v=OCS.15))

  - [移除 CsVoicePolicy](https://technet.microsoft.com/library/Gg398309(v=OCS.15))

  - [移除 CsVoiceRoute](https://technet.microsoft.com/library/Gg398468(v=OCS.15))

  - [Remove-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ204799(v=OCS.15))

  - [移除 Test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg412813(v=OCS.15))

  - [Remove-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204926(v=OCS.15))

  - [Remove-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398266(v=OCS.15))

  - [Remove-csxmppallowedpartner](https://technet.microsoft.com/library/JJ205055(v=OCS.15))

  - [Request-cscertificate](https://technet.microsoft.com/library/Gg425723(v=OCS.15))

  - [重設 CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398181(v=OCS.15))

  - [還原 CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398305(v=OCS.15))

  - [Revoke-csclientcertificate](https://technet.microsoft.com/library/Gg425748(v=OCS.15))

  - [Revoke-csoupermission](https://technet.microsoft.com/library/Gg398977(v=OCS.15))

  - [Revoke-cssetuppermission](https://technet.microsoft.com/library/Gg425834(v=OCS.15))

  - [Set-csaccessedgeconfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))

  - [Set-csaddressbookconfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))

  - [設定 Get-csadminrole](https://technet.microsoft.com/library/Gg399066(v=OCS.15))

  - [Set-csalloweddomain](https://technet.microsoft.com/library/Gg398931(v=OCS.15))

  - [Set-CsAnalogDevice](https://technet.microsoft.com/library/Gg412843(v=OCS.15))

  - [設定 CsAnnouncement](https://technet.microsoft.com/library/Gg425752(v=OCS.15))

  - [設定 CsApplicationServer](https://technet.microsoft.com/library/Gg398562(v=OCS.15))

  - [Set-csarchivingconfiguration](https://technet.microsoft.com/library/Gg413030(v=OCS.15))

  - [Set-csarchivingpolicy](https://technet.microsoft.com/library/Gg398294(v=OCS.15))

  - [設定 CsArchivingServer](https://technet.microsoft.com/library/Gg398923(v=OCS.15))

  - [Set-csaudiotestserviceapplication](https://technet.microsoft.com/library/Gg398907(v=OCS.15))

  - [Set-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh689980(v=OCS.15))

  - [Set-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))

  - [Set-csbackupserviceconfiguration](https://technet.microsoft.com/library/JJ205006(v=OCS.15))

  - [設定 CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412863(v=OCS.15))

  - [設定 New-csblockeddomain](https://technet.microsoft.com/library/Gg398090(v=OCS.15))

  - [設定 CsCallParkOrbit](https://technet.microsoft.com/library/Gg398796(v=OCS.15))

  - [Set-cscallparkservicemusiconholdfile](https://technet.microsoft.com/library/Gg412836(v=OCS.15))

  - [Set-cscdrconfiguration](https://technet.microsoft.com/library/Gg398774(v=OCS.15))

  - [Set-cscertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))

  - [Set-CsClientPin](https://technet.microsoft.com/library/Gg398929(v=OCS.15))

  - [Set-csclientpolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15))

  - [Set-csclientversionconfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15))

  - [Set-csclientversionpolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15))

  - [Set-csmonitoringserver](https://technet.microsoft.com/library/Gg425790(v=OCS.15))

  - [Set-csclsregion](https://technet.microsoft.com/library/JJ204746(v=OCS.15))

  - [Set-csclsscenario](https://technet.microsoft.com/library/JJ204622(v=OCS.15))

  - [Set-csclssearchterm](https://technet.microsoft.com/library/JJ204911(v=OCS.15))

  - [Set-csclssecuritygroup](https://technet.microsoft.com/library/JJ204700(v=OCS.15))

  - [設定 CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398579(v=OCS.15))

  - [設定 CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398776(v=OCS.15))

  - [Set-csconferenceserver](https://technet.microsoft.com/library/Gg398738(v=OCS.15))

  - [Set-csconferencingconfiguration](https://technet.microsoft.com/library/Gg412969(v=OCS.15))

  - [Set-csmonitoringserver](https://technet.microsoft.com/library/Gg425788(v=OCS.15))

  - [Set-csconfigurationstorelocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))

  - [Set-cscpsconfiguration](https://technet.microsoft.com/library/Gg412721(v=OCS.15))

  - [設定 CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15))

  - [Set-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg425734(v=OCS.15))

  - [Set-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg399045(v=OCS.15))

  - [Set-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg425770(v=OCS.15))

  - [Set-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg425825(v=OCS.15))

  - [Set-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg398860(v=OCS.15))

  - [Set-csdialplan](https://technet.microsoft.com/library/Gg398644(v=OCS.15))Set-csdialplan

  - [設定 CsDirector](https://technet.microsoft.com/library/Gg398565(v=OCS.15))

  - [Set-csedgeserver](https://technet.microsoft.com/library/Gg398859(v=OCS.15))

  - [Set-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg398620(v=OCS.15))

  - [設定 CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398916(v=OCS.15))

  - [Set-csexumcontact](https://technet.microsoft.com/library/Gg412944(v=OCS.15))

  - [Set-csfiletransferfilterconfiguration](https://technet.microsoft.com/library/Gg425736(v=OCS.15))

  - [Set-csfipsconfiguration](https://technet.microsoft.com/library/JJ205084(v=OCS.15))

  - [設定 CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425847(v=OCS.15))

  - [Set-cshostedvoicemailpolicy](https://technet.microsoft.com/library/Gg412722(v=OCS.15))

  - [設定 CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))

  - [設定 CsImFilterConfiguration](https://technet.microsoft.com/library/Gg412960(v=OCS.15))

  - [設定 CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))

  - [Set-cskerberosaccountpassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))

  - [設定 CsLisLocation](https://technet.microsoft.com/library/Gg398757(v=OCS.15))

  - [設定 CsLisPort](https://technet.microsoft.com/library/Gg398700(v=OCS.15))

  - [設定 CsLisServiceProvider](https://technet.microsoft.com/library/Gg425911(v=OCS.15))

  - [設定 CsLisSubnet](https://technet.microsoft.com/library/Gg399016(v=OCS.15))

  - [設定 CsLisSwitch](https://technet.microsoft.com/library/Gg412823(v=OCS.15))

  - [設定 CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg412723(v=OCS.15))

  - [設定則 CsLocationPolicy](https://technet.microsoft.com/library/Gg412987(v=OCS.15))

  - [Set-csmanagementconnection](https://technet.microsoft.com/library/Gg413045(v=OCS.15))

  - [Set-csmcxconfiguration](https://technet.microsoft.com/library/Hh690050(v=OCS.15))

  - [Set-csmanagementserver](https://technet.microsoft.com/library/Gg398465(v=OCS.15))

  - [設定 CsMediaConfiguration](https://technet.microsoft.com/library/Gg398580(v=OCS.15))

  - [Set-csmediationserver](https://technet.microsoft.com/library/Gg398213(v=OCS.15))

  - [Set-csmeetingconfiguration](https://technet.microsoft.com/library/Gg398648(v=OCS.15))

  - [Set-csmeetingroom](https://technet.microsoft.com/library/JJ204831(v=OCS.15))

  - [Set-csmobilitypolicy](https://technet.microsoft.com/library/Hh690021(v=OCS.15))

  - [設定 CsMonitoringServer](https://technet.microsoft.com/library/Gg425776(v=OCS.15))

  - [Set-csnetworkbandwidthpolicyprofile](https://technet.microsoft.com/library/Gg398338(v=OCS.15))

  - [設定 CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398927(v=OCS.15))

  - [設定 CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398410(v=OCS.15))

  - [Set-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg398772(v=OCS.15))

  - [Set-csnetworkregion](https://technet.microsoft.com/library/Gg413089(v=OCS.15))

  - [設定 CsNetworkRegionLink](https://technet.microsoft.com/library/Gg412867(v=OCS.15))

  - [Set-csnetworksite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))

  - [設定 CsNetworkSubnet](https://technet.microsoft.com/library/Gg412739(v=OCS.15))

  - [Set-csoauthconfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))

  - [Set-csoauthserver](https://technet.microsoft.com/library/JJ204896(v=OCS.15))

  - [Set-csoutboundcallingnumbertranslationrule](https://technet.microsoft.com/library/JJ205400(v=OCS.15))

  - [設定 CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg413073(v=OCS.15))

  - [Set-cspartnerapplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))

  - [Set-cspersistentchatactiveserver](https://technet.microsoft.com/library/JJ205065(v=OCS.15))

  - [Set-cspersistentchataddin](https://technet.microsoft.com/library/JJ204721(v=OCS.15))

  - [Set-cspersistentchatcategory](https://technet.microsoft.com/library/JJ204952(v=OCS.15))

  - [Set-cspersistentchatcomplianceconfiguration](https://technet.microsoft.com/library/JJ204949(v=OCS.15))

  - [Set-cspersistentchatconfiguration](https://technet.microsoft.com/library/JJ205122(v=OCS.15))

  - [Set-cspersistentchatpolicy](https://technet.microsoft.com/library/JJ205192(v=OCS.15))

  - [Set-cspersistentchatroom](https://technet.microsoft.com/library/JJ204801(v=OCS.15))

  - [Set-cspersistentchatstate](https://technet.microsoft.com/library/JJ205109(v=OCS.15))

  - [Set-cspinpolicy](https://technet.microsoft.com/library/Gg412997(v=OCS.15))

  - [Set-csmonitoringserver](https://technet.microsoft.com/library/Gg425782(v=OCS.15))

  - [Set-cspresenceprovider](https://technet.microsoft.com/library/JJ204833(v=OCS.15))

  - [Set-csprivacyconfiguration](https://technet.microsoft.com/library/Gg398484(v=OCS.15))

  - [Set-csproxyconfiguration](https://technet.microsoft.com/library/Gg425796(v=OCS.15))

  - [Set-cspstngateway](https://technet.microsoft.com/library/Gg398408(v=OCS.15))

  - [設定 CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))

  - [設定 CsPublicProvider](https://technet.microsoft.com/library/Gg413087(v=OCS.15))

  - [Set-cspushnotificationconfiguration](https://technet.microsoft.com/library/Hh690013(v=OCS.15))

  - [Set-csqoeconfiguration](https://technet.microsoft.com/library/Gg398245(v=OCS.15))

  - [設定 CsRegistrar](https://technet.microsoft.com/library/Gg398993(v=OCS.15))

  - [Set-csregistrarconfiguration](https://technet.microsoft.com/library/Gg398764(v=OCS.15))

  - [Set-csreportingconfiguration](https://technet.microsoft.com/library/JJ205075(v=OCS.15))

  - [設定 CsRgsAgentGroup](https://technet.microsoft.com/library/Gg425955(v=OCS.15))

  - [Set-csrgsconfiguration](https://technet.microsoft.com/library/Gg425728(v=OCS.15))

  - [設定 CsRgsHolidaySet](https://technet.microsoft.com/library/Gg398736(v=OCS.15))

  - [設定 CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg412929(v=OCS.15))

  - [Set-csrgsqueue](https://technet.microsoft.com/library/Gg412947(v=OCS.15))

  - [Set-csrgsworkflow](https://technet.microsoft.com/library/Gg425845(v=OCS.15))

  - [設定 CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))

  - [設定 CsServerApplication](https://technet.microsoft.com/library/Gg412850(v=OCS.15))

  - [設定 CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))

  - [設定 CsSipDomain](https://technet.microsoft.com/library/Gg412949(v=OCS.15))

  - [Set-cssipresponsecodetranslationrule](https://technet.microsoft.com/library/Gg425895(v=OCS.15))

  - [設定 CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))

  - [設定 CsSlaConfiguration](https://technet.microsoft.com/library/Mt703202(v=OCS.15))

  - [Set-csstaticroutingconfiguration](https://technet.microsoft.com/library/Gg398724(v=OCS.15))

  - [設定 CsTestDevice](https://technet.microsoft.com/library/Gg398156(v=OCS.15))

  - [Set-cstrunkconfiguration](https://technet.microsoft.com/library/Gg398238(v=OCS.15))

  - [設定 CsTrustedApplication](https://technet.microsoft.com/library/Gg425840(v=OCS.15))

  - [設定 CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398509(v=OCS.15))

  - [設定 CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg398187(v=OCS.15))

  - [Set-csucphoneconfiguration](https://technet.microsoft.com/library/Gg413042(v=OCS.15))

  - [Set-csuiculture](https://technet.microsoft.com/library/Gg398354(v=OCS.15))

  - [Set-csunassignednumber](https://technet.microsoft.com/library/Gg399033(v=OCS.15))

  - [Set-csuser](https://technet.microsoft.com/library/Gg398510(v=OCS.15))

  - [設定 CsUserAcp](https://technet.microsoft.com/library/Gg413018(v=OCS.15))

  - [設定 CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))

  - [設定 CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))

  - [設定 CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))

  - [Set-csuserservicesconfiguration](https://technet.microsoft.com/library/Gg398340(v=OCS.15))

  - [Set-csuserservicespolicy](https://technet.microsoft.com/library/JJ205414(v=OCS.15))

  - [設定 CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398967(v=OCS.15))

  - [設定 CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg412948(v=OCS.15))

  - [Set-csvoicenormalizationrule](https://technet.microsoft.com/library/Gg398491(v=OCS.15))

  - [Set-csvoicepolicy](https://technet.microsoft.com/library/Gg399021(v=OCS.15))

  - [設定 CsVoiceRoute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))

  - [Set-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ205313(v=OCS.15))

  - [設定 Test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398614(v=OCS.15))

  - [Set-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204620(v=OCS.15))

  - [Set-cswebserver](https://technet.microsoft.com/library/Gg398759(v=OCS.15))

  - [Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))

  - [Set-csxmppallowedpartner](https://technet.microsoft.com/library/JJ204686(v=OCS.15))

  - [Set-csxmppgatewayconfiguration](https://technet.microsoft.com/library/JJ204769(v=OCS.15))

  - [使用 Start-cswindowsservice](https://technet.microsoft.com/library/Gg398561(v=OCS.15))

  - [Stop-cswindowsservice](https://technet.microsoft.com/library/Gg398426(v=OCS.15))

  - [Sync-csuserdata](https://technet.microsoft.com/library/JJ205242(v=OCS.15))

  - [Test-csaddressbookservice](https://technet.microsoft.com/library/Gg398661(v=OCS.15))

  - [Test-csaddressbookwebquery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))

  - [Test-csasconference](https://technet.microsoft.com/library/JJ205227(v=OCS.15))

  - [Test-csaudioconferencingprovider](https://technet.microsoft.com/library/JJ205117(v=OCS.15))

  - [Test-csavconference](https://technet.microsoft.com/library/Gg412749(v=OCS.15))

  - [Test-csavedgeconnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))

  - [Test-cscertificateconfiguration](https://technet.microsoft.com/library/Gg398647(v=OCS.15))

  - [Test-cscomputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))

  - [Test-csdatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))

  - [Test-csdataconference](https://technet.microsoft.com/library/JJ205219(v=OCS.15))

  - [Test-csdialinconferencing](https://technet.microsoft.com/library/Gg399013(v=OCS.15))

  - [Test-csdialplan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))

  - [Test-csexstorageconnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15))

  - [Test-csexstoragenotification](https://technet.microsoft.com/library/JJ205331(v=OCS.15))

  - [Test-csexumconnectivity](https://technet.microsoft.com/library/JJ204784(v=OCS.15))

  - [Test-csexumvoicemail](https://technet.microsoft.com/library/JJ205058(v=OCS.15))

  - [Test-csfederatedpartner](https://technet.microsoft.com/library/Gg398281(v=OCS.15))

  - [Test-csgroupexpansion](https://technet.microsoft.com/library/Gg399009(v=OCS.15))

  - [Test-csgroupim](https://technet.microsoft.com/library/Gg398273(v=OCS.15))

  - [Test-csim](https://technet.microsoft.com/library/Gg425802(v=OCS.15))

  - [Test-csintertrunkrouting](https://technet.microsoft.com/library/JJ204741(v=OCS.15))

  - [Test-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))

  - [Test-csliscivicaddress](https://technet.microsoft.com/library/Gg425914(v=OCS.15))

  - [Test-cslisconfiguration](https://technet.microsoft.com/library/Gg398497(v=OCS.15))

  - [Test-cslocationpolicy](https://technet.microsoft.com/library/Gg425962(v=OCS.15))

  - [Test-csmcxconference](https://technet.microsoft.com/library/Hh690045(v=OCS.15))

  - [Test-csmcxp2pim](https://technet.microsoft.com/library/Hh690020(v=OCS.15))

  - [Test-csmcxpushnotification](https://technet.microsoft.com/library/Hh690043(v=OCS.15))

  - [Test-csoupermission](https://technet.microsoft.com/library/Gg398787(v=OCS.15))

  - [Test-csp2pav](https://technet.microsoft.com/library/Gg412821(v=OCS.15))

  - [Test-cspersistentchatmessage](https://technet.microsoft.com/library/JJ204656(v=OCS.15))

  - [測試 CsPhoneBootstrap](https://technet.microsoft.com/library/Gg412852(v=OCS.15))

  - [Test-cspresence](https://technet.microsoft.com/library/Gg398148(v=OCS.15))

  - [Test-cspstnoutboundcall](https://technet.microsoft.com/library/Gg398207(v=OCS.15))

  - [Test-cspstnpeertopeercall](https://technet.microsoft.com/library/Gg398662(v=OCS.15))

  - [Test-csregistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15))

  - [Test-csreplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))

  - [Test-cssetuppermission](https://technet.microsoft.com/library/Gg398428(v=OCS.15))

  - [Test-cstopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))

  - [測試 Test-cstrunkconfiguration](https://technet.microsoft.com/library/Gg398137(v=OCS.15))

  - [Test-csunifiedcontactstore](https://technet.microsoft.com/library/JJ204662(v=OCS.15))

  - [測試來](https://technet.microsoft.com/library/Gg399003(v=OCS.15))

  - [測試 CsVoicePolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))

  - [測試 CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))

  - [測試 Test-csvoicetestconfiguration](https://technet.microsoft.com/library/Gg398260(v=OCS.15))

  - [測試 CsVoiceUser](https://technet.microsoft.com/library/Gg413013(v=OCS.15))

  - [Test-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204652(v=OCS.15))

  - [Test-cswebapp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))

  - [Test-cswebappanonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))

  - [Test-cswebscheduler](https://technet.microsoft.com/library/JJ204829(v=OCS.15))

  - [Test-csxmppim](https://technet.microsoft.com/library/JJ205423(v=OCS.15))

  - [Uninstall-csdatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))

  - [解除安裝 CsMirrorDatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))

  - [解除鎖定-CsClientPin](unhttps://technet.microsoft.com/library/Gg398650(v=OCS.15))

  - [解除發佈 CsLisConfiguration](unhttps://technet.microsoft.com/library/Gg398364(v=OCS.15))

  - [Update-csaddressbook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))

  - [Update-csadminrole](https://technet.microsoft.com/library/JJ204851(v=OCS.15))

  - [更新 CsTenantMeetingUrl](https://technet.microsoft.com/library/Dn424754(v=OCS.15))

  - [Update-csuserdata](https://technet.microsoft.com/library/JJ205358(v=OCS.15))

  - [更新 CsUserDatabase](https://technet.microsoft.com/library/Gg398682(v=OCS.15))

</div>

</div>

<span> </span>

</div>

</div>

</div>

