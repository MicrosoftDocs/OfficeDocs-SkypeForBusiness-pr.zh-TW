---
title: Lync Server 2013： Cmdlet 索引
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
ms.openlocfilehash: 64dd8edcb3f21cbdbdaf2b5a29c7e813675c9136
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-index"></a>Lync Server 2013 Cmdlet 索引

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-04-12_

Microsoft Lync Server 2013 隨附超過700個 Cmdlet，可讓系統管理員從命令列管理 Lync Server 2013。 Lync Server Cmdlet 通常用於 Lync Server 管理命令介面。 使用 Lync Server 管理命令介面的其中一個方法是登入執行 Lync Server 服務或伺服器角色的電腦，按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。 管理命令介面開啟之後，您可以直接從命令列取得 Cmdlet 的說明，只要輸入類似以下的命令即可：

    Get-Help New-CsVoicePolicy -Full

上述命令會檢索**CsVoicePolicy** Cmdlet 提供的完整說明。 若要查看其他 Cmdlet 的說明，請以**新的 CsVoicePolicy**取代您要取得其說明的 Cmdlet 名稱。

若要取得可供管理 Lync Server 的完整 Cmdlet 清單，請在 Lync Server Management 命令介面命令提示字元輸入下列內容：

    Get-Command * -Module Lync -CommandType cmdlet

如需使用 Lync Server 管理命令介面的詳細資訊，請參閱 Lync Server Windows PowerShell [http://go.microsoft.com/fwlink/p/?linkId=203150](http://go.microsoft.com/fwlink/p/?linkid=203150)博客（位於）。

<div>

## <a name="lync-server-2013-cmdlets"></a>Lync Server 2013 Cmdlet

以下是 Lync Server 2013 隨附的 Cmdlet 清單：

  - [附加 CsSlaDelegates](https://technet.microsoft.com/en-us/library/Mt703199(v=OCS.15))

  - [核准-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398949(v=OCS.15))

  - [備份-CsPool](https://technet.microsoft.com/en-us/library/JJ204955(v=OCS.15))

  - [Clear-CsDeviceUpdateFile](https://technet.microsoft.com/en-us/library/Gg425835(v=OCS.15))

  - [Clear-CsDeviceUpdateLog](https://technet.microsoft.com/en-us/library/Gg412738(v=OCS.15))

  - [Clear-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204976(v=OCS.15))

  - [Convert-CsUserData](https://technet.microsoft.com/en-us/library/JJ205337(v=OCS.15))

  - [Debug-CsAddressBookReplication](https://technet.microsoft.com/en-us/library/JJ205232(v=OCS.15))

  - [Debug-CsIntraPoolReplication](https://technet.microsoft.com/en-us/library/JJ205103(v=OCS.15))

  - [調試-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398710(v=OCS.15))

  - [Disable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398785(v=OCS.15))

  - [Disable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg398122(v=OCS.15))

  - [Disable-CsComputer](https://technet.microsoft.com/en-us/library/Gg399023(v=OCS.15))

  - [Disable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398481(v=OCS.15))

  - [Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204723(v=OCS.15))

  - [Disable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398984(v=OCS.15))

  - [Disable-Move-csuser](https://technet.microsoft.com/en-us/library/Gg398747(v=OCS.15))

  - [Enable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg412764(v=OCS.15))

  - [Enable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg425713(v=OCS.15))

  - [Enable-CsComputer](https://technet.microsoft.com/en-us/library/Gg412815(v=OCS.15))

  - [Enable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398166(v=OCS.15))

  - [Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205062(v=OCS.15))

  - [Enable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398780(v=OCS.15))

  - [Enable-CsReplica](https://technet.microsoft.com/en-us/library/Gg425965(v=OCS.15))

  - [Enable-CsTopology](https://technet.microsoft.com/en-us/library/Gg398398(v=OCS.15))

  - [Enable-Move-csuser](https://technet.microsoft.com/en-us/library/Gg398711(v=OCS.15))

  - [Export-CsArchivingData](https://technet.microsoft.com/en-us/library/Gg398452(v=OCS.15))

  - [Export-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398627(v=OCS.15))

  - [Export-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398539(v=OCS.15))

  - [Export-CsPersistentChatData](https://technet.microsoft.com/en-us/library/JJ205378(v=OCS.15))

  - [Export-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/JJ205011(v=OCS.15))

  - [Export-CsUserData](https://technet.microsoft.com/en-us/library/JJ204897(v=OCS.15))

  - [CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398574(v=OCS.15))

  - [CsAdContact](https://technet.microsoft.com/en-us/library/Gg412776(v=OCS.15))

  - [CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398453(v=OCS.15))

  - [CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398132(v=OCS.15))

  - [CsAdForest](https://technet.microsoft.com/en-us/library/Gg412995(v=OCS.15))

  - [CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399050(v=OCS.15))

  - [CsAdminRoleAssignment](https://technet.microsoft.com/en-us/library/Gg398434(v=OCS.15))

  - [CsAdPrincipal](https://technet.microsoft.com/en-us/library/JJ205326(v=OCS.15))

  - [CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg413070(v=OCS.15))

  - [CsAdUser](https://technet.microsoft.com/en-us/library/Gg398592(v=OCS.15))

  - [CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398164(v=OCS.15))

  - [CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg398748(v=OCS.15))

  - [CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg398937(v=OCS.15))

  - [CsApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398655(v=OCS.15))

  - [CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg399012(v=OCS.15))

  - [Get-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg425731(v=OCS.15))

  - [CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg412984(v=OCS.15))

  - [CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690014(v=OCS.15))

  - [CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413008(v=OCS.15))

  - [CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205087(v=OCS.15))

  - [CsBackupServiceStatus](https://technet.microsoft.com/en-us/library/JJ205032(v=OCS.15))

  - [CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412727(v=OCS.15))

  - [CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398424(v=OCS.15))

  - [CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398554(v=OCS.15))

  - [CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398298(v=OCS.15))

  - [CsCertificate](https://technet.microsoft.com/en-us/library/Gg398227(v=OCS.15))

  - [CsClientAccessLicense](https://technet.microsoft.com/en-us/library/JJ204853(v=OCS.15))

  - [CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg398143(v=OCS.15))

  - [Get-CsClientPinInfo](https://technet.microsoft.com/en-us/library/Gg425947(v=OCS.15))

  - [Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398830(v=OCS.15))

  - [CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399072(v=OCS.15))

  - [Get-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398957(v=OCS.15))

  - [Get-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg413048(v=OCS.15))

  - [CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204879(v=OCS.15))

  - [CsClsSearchTerm](https://technet.microsoft.com/en-us/library/JJ205061(v=OCS.15))

  - [CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205091(v=OCS.15))

  - [CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ205285(v=OCS.15))

  - [CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg412934(v=OCS.15))

  - [CsComputer](https://technet.microsoft.com/en-us/library/Gg425959(v=OCS.15))

  - [CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg425771(v=OCS.15))

  - [CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425714(v=OCS.15))

  - [CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398965(v=OCS.15))

  - [Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398293(v=OCS.15))

  - [CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg412814(v=OCS.15))

  - [CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398948(v=OCS.15))

  - [Get-CsDatabaseMirrorState](https://technet.microsoft.com/en-us/library/JJ204845(v=OCS.15))

  - [CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg399030(v=OCS.15))

  - [CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398215(v=OCS.15))

  - [CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg413034(v=OCS.15))

  - [CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg412774(v=OCS.15))

  - [CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg413015(v=OCS.15))

  - [CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398575(v=OCS.15))

  - [CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398578(v=OCS.15))

  - [CsDialInConferencingLanguageList](https://technet.microsoft.com/en-us/library/Gg425869(v=OCS.15))

  - [CsDialPlan](https://technet.microsoft.com/en-us/library/Gg413043(v=OCS.15))

  - [CsEffectivePolicy](https://technet.microsoft.com/en-us/library/JJ204636(v=OCS.15))

  - [CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg412877(v=OCS.15))

  - [Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))

  - [CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412725(v=OCS.15))

  - [CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398527(v=OCS.15))

  - [CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ204904(v=OCS.15))

  - [CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398667(v=OCS.15))

  - [CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398348(v=OCS.15))

  - [CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))

  - [CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398980(v=OCS.15))

  - [Get-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398526(v=OCS.15))

  - [CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg398459(v=OCS.15))

  - [CsLisLocation](https://technet.microsoft.com/en-us/library/Gg412834(v=OCS.15))

  - [CsLisPort](https://technet.microsoft.com/en-us/library/Gg398820(v=OCS.15))

  - [CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398116(v=OCS.15))

  - [CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg398473(v=OCS.15))

  - [CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg425769(v=OCS.15))

  - [CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398117(v=OCS.15))

  - [Get-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398911(v=OCS.15))

  - [CsManagementConnection](https://technet.microsoft.com/en-us/library/Gg412849(v=OCS.15))

  - [CsManagementStoreReplicationStatus](https://technet.microsoft.com/en-us/library/Gg399052(v=OCS.15))

  - [CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690031(v=OCS.15))

  - [CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg398128(v=OCS.15))

  - [CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg425875(v=OCS.15))

  - [Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205277(v=OCS.15))

  - [Get-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690017(v=OCS.15))

  - [CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg425815(v=OCS.15))

  - [CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398140(v=OCS.15))

  - [CsNetworkInterface](https://technet.microsoft.com/en-us/library/Gg398121(v=OCS.15))

  - [CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg425817(v=OCS.15))

  - [CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg412769(v=OCS.15))

  - [CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398406(v=OCS.15))

  - [CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398972(v=OCS.15))

  - [CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))

  - [CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412825(v=OCS.15))

  - [Get-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ205155(v=OCS.15))

  - [CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205238(v=OCS.15))

  - [CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204962(v=OCS.15))

  - [CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398104(v=OCS.15))

  - [CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ205128(v=OCS.15))

  - [CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204670(v=OCS.15))

  - [CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204771(v=OCS.15))

  - [CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204625(v=OCS.15))

  - [CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205140(v=OCS.15))

  - [CsPersistentChatEligiblePrincipal](https://technet.microsoft.com/en-us/library/JJ204891(v=OCS.15))

  - [CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204764(v=OCS.15))

  - [Get-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ204673(v=OCS.15))

  - [CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ205123(v=OCS.15))

  - [Get-CsPersistentChatState](https://technet.microsoft.com/en-us/library/JJ204915(v=OCS.15))

  - [Get-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398262(v=OCS.15))

  - [CsPool](https://technet.microsoft.com/en-us/library/Gg398992(v=OCS.15))

  - [CsPoolBackupRelationship](https://technet.microsoft.com/en-us/library/JJ204745(v=OCS.15))

  - [Get-CsPoolUpgradeReadinessState](https://technet.microsoft.com/en-us/library/JJ204689(v=OCS.15))

  - [Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398463(v=OCS.15))

  - [CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204705(v=OCS.15))

  - [CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg413002(v=OCS.15))

  - [CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg399011(v=OCS.15))

  - [CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg412734(v=OCS.15))

  - [CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412945(v=OCS.15))

  - [CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690049(v=OCS.15))

  - [CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg399004(v=OCS.15))

  - [CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398483(v=OCS.15))

  - [CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ205356(v=OCS.15))

  - [CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg425793(v=OCS.15))

  - [CsRgsConfiguration](https://technet.microsoft.com/en-us/library/Gg412762(v=OCS.15))

  - [Get-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg412983(v=OCS.15))

  - [CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg398284(v=OCS.15))

  - [CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg412759(v=OCS.15))

  - [CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg425766(v=OCS.15))

  - [CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425851(v=OCS.15))

  - [CsServerApplication](https://technet.microsoft.com/en-us/library/Gg425948(v=OCS.15))

  - [CsServerVersion](https://technet.microsoft.com/en-us/library/Gg398470(v=OCS.15))

  - [Get-CsService](https://technet.microsoft.com/en-us/library/Gg413038(v=OCS.15))

  - [Get-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg398392(v=OCS.15))

  - [CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398701(v=OCS.15))

  - [Get-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg398130(v=OCS.15))

  - [CsSlaConfiguration](https://technet.microsoft.com/en-us/library/Mt703200(v=OCS.15))

  - [CsSite](https://technet.microsoft.com/en-us/library/Gg398185(v=OCS.15))

  - [CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398754(v=OCS.15))

  - [CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398304(v=OCS.15))

  - [CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ204759(v=OCS.15))

  - [CsTopology](https://technet.microsoft.com/en-us/library/Gg412824(v=OCS.15))

  - [CsTrunk](https://technet.microsoft.com/en-us/library/JJ205244(v=OCS.15))

  - [Get-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398224(v=OCS.15))

  - [CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg399025(v=OCS.15))

  - [CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg425843(v=OCS.15))

  - [CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg413035(v=OCS.15))

  - [CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg413055(v=OCS.15))

  - [CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398070(v=OCS.15))

  - [CsUICulture](https://technet.microsoft.com/en-us/library/Gg412900(v=OCS.15))

  - [CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg412792(v=OCS.15))

  - [Get-CsUser](https://technet.microsoft.com/en-us/library/Gg398125(v=OCS.15))

  - [CsUserAcp](https://technet.microsoft.com/en-us/library/Gg398978(v=OCS.15))

  - [CsUserDatabaseState](https://technet.microsoft.com/en-us/library/Gg398831(v=OCS.15))

  - [CsUserPoolInfo](https://technet.microsoft.com/en-us/library/Gg398615(v=OCS.15))

  - [Get-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398548(v=OCS.15))

  - [CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398133(v=OCS.15))

  - [CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ204838(v=OCS.15))

  - [CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398815(v=OCS.15))

  - [CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425732(v=OCS.15))

  - [CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398393(v=OCS.15))

  - [CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398101(v=OCS.15))

  - [CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425926(v=OCS.15))

  - [CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ204940(v=OCS.15))

  - [CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412957(v=OCS.15))

  - [CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204739(v=OCS.15))

  - [CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg425751(v=OCS.15))

  - [CsWindowsService](https://technet.microsoft.com/en-us/library/Gg398803(v=OCS.15))

  - [CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))

  - [CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))

  - [授與 CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg398475(v=OCS.15))

  - [授與 CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg412942(v=OCS.15))

  - [授與 CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg412903(v=OCS.15))

  - [授與 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425937(v=OCS.15))

  - [授與 CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398547(v=OCS.15))

  - [授與 CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425942(v=OCS.15))

  - [授與 CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412829(v=OCS.15))

  - [授與 CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg413049(v=OCS.15))

  - [授與 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690038(v=OCS.15))

  - [授與 CsOUPermission](https://technet.microsoft.com/en-us/library/Gg425739(v=OCS.15))

  - [授與 CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ204907(v=OCS.15))

  - [授與 CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398871(v=OCS.15))

  - [授與 CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398571(v=OCS.15))

  - [授與 CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398569(v=OCS.15))

  - [授與 CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ205388(v=OCS.15))

  - [授與 CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398828(v=OCS.15))

  - [授與 CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205141(v=OCS.15))

  - [匯入-CsAnnouncementFile](https://technet.microsoft.com/en-us/library/Gg398472(v=OCS.15))

  - [匯入-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398688(v=OCS.15))

  - [匯入-CsConfiguration](https://technet.microsoft.com/en-us/library/Gg398800(v=OCS.15))

  - [匯入-CsDeviceUpdate](https://technet.microsoft.com/en-us/library/Gg398861(v=OCS.15))

  - [匯入-CsLegacyConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg398418(v=OCS.15))

  - [匯入-CsLegacyConfiguration](https://technet.microsoft.com/en-us/library/Gg412923(v=OCS.15))

  - [匯入-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398380(v=OCS.15))

  - [匯入-CsPersistentChatData](https://technet.microsoft.com/en-us/library/JJ204709(v=OCS.15))

  - [匯入-CsRgsAudioFile](https://technet.microsoft.com/en-us/library/Gg412830(v=OCS.15))

  - [匯入-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/JJ205245(v=OCS.15))

  - [匯入-CsUserData](https://technet.microsoft.com/en-us/library/JJ205373(v=OCS.15))

  - [Install-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg398681(v=OCS.15))

  - [Install-CsDatabase](https://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))

  - [Install-CsMirrorDatabase](https://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))

  - [Invoke-CsArchivingDatabasePurge](https://technet.microsoft.com/en-us/library/JJ204627(v=OCS.15))

  - [Invoke-CsBackupServiceSync](https://technet.microsoft.com/en-us/library/JJ205374(v=OCS.15))

  - [Invoke-CsCdrDatabasePurge](https://technet.microsoft.com/en-us/library/JJ205113(v=OCS.15))

  - [Invoke-CsDatabaseFailover](https://technet.microsoft.com/en-us/library/JJ204744(v=OCS.15))

  - [Invoke-CsManagementServerFailover](https://technet.microsoft.com/en-us/library/JJ204647(v=OCS.15))

  - [Invoke-CsManagementStoreReplication](https://technet.microsoft.com/en-us/library/Gg413060(v=OCS.15))

  - [Invoke-CsPoolFailBack](https://technet.microsoft.com/en-us/library/JJ204873(v=OCS.15))

  - [Invoke-CsPoolFailOver](https://technet.microsoft.com/en-us/library/JJ205189(v=OCS.15))

  - [Invoke-CsQoEDatabasePurge](https://technet.microsoft.com/en-us/library/JJ205247(v=OCS.15))

  - [Invoke-CsUcsRollback](https://technet.microsoft.com/en-us/library/JJ204661(v=OCS.15))

  - [Lock-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))

  - [合併-CsLegacyTopology](https://technet.microsoft.com/en-us/library/Gg425870(v=OCS.15))

  - [移動流覽 CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg398816(v=OCS.15))

  - [移動流覽 CsApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398188(v=OCS.15))

  - [移動流覽 CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg412837(v=OCS.15))

  - [Move-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))

  - [移動流覽 CsExUmContact](https://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))

  - [移動流覽 CsLegacyUser](https://technet.microsoft.com/en-us/library/Gg413025(v=OCS.15))

  - [移動流覽 CsManagementServer](https://technet.microsoft.com/en-us/library/Gg412921(v=OCS.15))

  - [移動流覽 CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204889(v=OCS.15))

  - [Move-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/Gg398782(v=OCS.15))

  - [移動流覽 Move-csuser](https://technet.microsoft.com/en-us/library/Gg398528(v=OCS.15))

  - [New-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398395(v=OCS.15))

  - [新-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg398271(v=OCS.15))

  - [New-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398628(v=OCS.15))

  - [新-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg412937(v=OCS.15))

  - [新-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg398522(v=OCS.15))

  - [新-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg398471(v=OCS.15))

  - [New-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg399032(v=OCS.15))

  - [New-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690022(v=OCS.15))

  - [新-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))

  - [新-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398175(v=OCS.15))

  - [新-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398822(v=OCS.15))

  - [新-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398936(v=OCS.15))

  - [新-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg399018(v=OCS.15))

  - [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425949(v=OCS.15))

  - [新-CsClientPolicyEntry](https://technet.microsoft.com/en-us/library/Gg399046(v=OCS.15))

  - [新-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15))

  - [New-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398709(v=OCS.15))

  - [New-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398905(v=OCS.15))

  - [新-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204658(v=OCS.15))

  - [新-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205022(v=OCS.15))

  - [新-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ205359(v=OCS.15))

  - [新-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg398430(v=OCS.15))

  - [New-CsConferenceDirectory](https://technet.microsoft.com/en-us/library/Gg413080(v=OCS.15))

  - [New-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412967(v=OCS.15))

  - [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg413019(v=OCS.15))

  - [新-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412919(v=OCS.15))

  - [新-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15))

  - [新-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg398733(v=OCS.15))

  - [New-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398350(v=OCS.15))

  - [新-CsDiagnosticsFilter](https://technet.microsoft.com/en-us/library/Gg413009(v=OCS.15))

  - [新-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg398818(v=OCS.15))

  - [新-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412816(v=OCS.15))

  - [新-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425792(v=OCS.15))

  - [新-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg425860(v=OCS.15))

  - [新-CsExtendedTest](https://technet.microsoft.com/en-us/library/JJ205275(v=OCS.15))

  - [New-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398441(v=OCS.15))

  - [新-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg398139(v=OCS.15))

  - [新-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425897(v=OCS.15))

  - [新-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205114(v=OCS.15))

  - [新-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg398718(v=OCS.15))

  - [新-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398653(v=OCS.15))

  - [新-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))

  - [新-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398244(v=OCS.15))

  - [新-CsIssuedCertId](https://technet.microsoft.com/en-us/library/Gg425814(v=OCS.15))

  - [新-CsKerberosAccount](https://technet.microsoft.com/en-us/library/Gg398485(v=OCS.15))

  - [New-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398074(v=OCS.15))

  - [New-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398231(v=OCS.15))

  - [新-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690035(v=OCS.15))

  - [新-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg425881(v=OCS.15))

  - [New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15))

  - [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh689987(v=OCS.15))

  - [新-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398675(v=OCS.15))

  - [新-CsNetworkBWAlternatePath](https://technet.microsoft.com/en-us/library/Gg398732(v=OCS.15))

  - [新-CsNetworkBWPolicy](https://technet.microsoft.com/en-us/library/Gg412916(v=OCS.15))

  - [新-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398779(v=OCS.15))

  - [新-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398994(v=OCS.15))

  - [新-New-csnetworkmediabypassconfiguration](https://technet.microsoft.com/en-us/library/Gg425718(v=OCS.15))

  - [新-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg425829(v=OCS.15))

  - [新-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398437(v=OCS.15))

  - [新-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))

  - [新-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg398226(v=OCS.15))

  - [New-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205206(v=OCS.15))

  - [新-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205097(v=OCS.15))

  - [New-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg412803(v=OCS.15))

  - [New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15))

  - [New-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204641(v=OCS.15))

  - [新-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204803(v=OCS.15))

  - [新-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ205163(v=OCS.15))

  - [新-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205330(v=OCS.15))

  - [新-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204811(v=OCS.15))

  - [New-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205396(v=OCS.15))

  - [新-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ205166(v=OCS.15))

  - [New-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398935(v=OCS.15))

  - [New-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg412747(v=OCS.15))

  - [新-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204895(v=OCS.15))

  - [新-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398807(v=OCS.15))

  - [New-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398335(v=OCS.15))

  - [New-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398161(v=OCS.15))

  - [新-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690027(v=OCS.15))

  - [新-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg398325(v=OCS.15))

  - [新-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg425893(v=OCS.15))

  - [新-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ204787(v=OCS.15))

  - [新-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg413065(v=OCS.15))

  - [新-CsRgsAnswer](https://technet.microsoft.com/en-us/library/Gg412812(v=OCS.15))

  - [新-CsRgsCallAction](https://technet.microsoft.com/en-us/library/Gg398136(v=OCS.15))

  - [新-CsRgsHoliday](https://technet.microsoft.com/en-us/library/Gg398075(v=OCS.15))

  - [New-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg398403(v=OCS.15))

  - [新-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg398291(v=OCS.15))

  - [新-CsRgsPrompt](https://technet.microsoft.com/en-us/library/Gg398486(v=OCS.15))

  - [新-CsRgsQuestion](https://technet.microsoft.com/en-us/library/Gg398186(v=OCS.15))

  - [新-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg398989(v=OCS.15))

  - [新-CsRgsTimeRange](https://technet.microsoft.com/en-us/library/Gg399040(v=OCS.15))

  - [新-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg398246(v=OCS.15))

  - [新-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg399056(v=OCS.15))

  - [新-CsServerApplication](https://technet.microsoft.com/en-us/library/Gg398096(v=OCS.15))

  - [New-CsSimpleUrl](https://technet.microsoft.com/en-us/library/Gg398180(v=OCS.15))

  - [New-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg425813(v=OCS.15))

  - [New-CsSimpleUrlEntry](https://technet.microsoft.com/en-us/library/Gg425902(v=OCS.15))

  - [新-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg425857(v=OCS.15))

  - [New-CsSipProxyCustom](https://technet.microsoft.com/en-us/library/Gg425904(v=OCS.15))

  - [新-CsSipProxyRealm](https://technet.microsoft.com/en-us/library/Gg413084(v=OCS.15))

  - [新-CsSipProxyTCP](https://technet.microsoft.com/en-us/library/Gg425745(v=OCS.15))

  - [新-CsSipProxyTLS](https://technet.microsoft.com/en-us/library/Gg398629(v=OCS.15))

  - [New-CsSipProxyTransport](https://technet.microsoft.com/en-us/library/Gg398489(v=OCS.15))

  - [新-CsSipProxyUseDefault](https://technet.microsoft.com/en-us/library/Gg398274(v=OCS.15))

  - [新-CsSipProxyUseDefaultCert](https://technet.microsoft.com/en-us/library/Gg425858(v=OCS.15))

  - [New-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg413041(v=OCS.15))

  - [新-CsStaticRoute](https://technet.microsoft.com/en-us/library/Gg398265(v=OCS.15))

  - [新-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425811(v=OCS.15))

  - [新-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg425899(v=OCS.15))

  - [新-New-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg413021(v=OCS.15))

  - [新-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg398259(v=OCS.15))

  - [新-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg398405(v=OCS.15))

  - [New-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398594(v=OCS.15))

  - [新-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg425804(v=OCS.15))

  - [新-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15))

  - [New-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg398651(v=OCS.15))

  - [New-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg399059(v=OCS.15))

  - [新-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg412926(v=OCS.15))

  - [New-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ205072(v=OCS.15))

  - [新-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425849(v=OCS.15))

  - [新-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398240(v=OCS.15))

  - [New-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg425856(v=OCS.15))

  - [新-CsVoiceRegex](https://technet.microsoft.com/en-us/library/Gg412751(v=OCS.15))

  - [新-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398197(v=OCS.15))

  - [新-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205135(v=OCS.15))

  - [新-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398961(v=OCS.15))

  - [New-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ205254(v=OCS.15))

  - [新-CsWebLink](https://technet.microsoft.com/en-us/library/Hh690053(v=OCS.15))

  - [New-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398440(v=OCS.15))

  - [新-CsWebTrustedCACertificate](https://technet.microsoft.com/en-us/library/Gg412746(v=OCS.15))

  - [新-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204631(v=OCS.15))

  - [發佈-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))

  - [發佈-CsTopology](https://technet.microsoft.com/en-us/library/Gg398953(v=OCS.15))

  - [移除-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg398934(v=OCS.15))

  - [移除-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg413036(v=OCS.15))

  - [移除-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398913(v=OCS.15))

  - [移除-CsAnalogDevice](rehttps://technet.microsoft.com/en-us/library/Gg398816(v=OCS.15))

  - [移除-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg412766(v=OCS.15))

  - [移除-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg398951(v=OCS.15))

  - [Remove-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg425924(v=OCS.15))

  - [移除-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh690054(v=OCS.15))

  - [移除-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg398786(v=OCS.15))

  - [移除-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ204903(v=OCS.15))

  - [移除-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398877(v=OCS.15))

  - [移除-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg425832(v=OCS.15))

  - [移除-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg412901(v=OCS.15))

  - [移除-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398451(v=OCS.15))

  - [移除-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))

  - [Remove-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425772(v=OCS.15))

  - [移除-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15))

  - [Remove-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg425801(v=OCS.15))

  - [Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398541(v=OCS.15))

  - [移除-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204971(v=OCS.15))

  - [移除-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ205010(v=OCS.15))

  - [移除-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15))

  - [移除-CsCommonAreaPhone](rehttps://technet.microsoft.com/en-us/library/Gg412837(v=OCS.15))

  - [Remove-CsConferenceDirectory](rehttps://technet.microsoft.com/en-us/library/Gg412968(v=OCS.15))

  - [移除-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398243(v=OCS.15))

  - [移除-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412767(v=OCS.15))

  - [Remove-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398728(v=OCS.15))

  - [移除-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398214(v=OCS.15))

  - [移除-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398358(v=OCS.15))

  - [移除-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425933(v=OCS.15))

  - [移除-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg425930(v=OCS.15))

  - [移除-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg412853(v=OCS.15))

  - [移除-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg398941(v=OCS.15))

  - [移除-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg412782(v=OCS.15))

  - [移除-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398174(v=OCS.15))

  - [移除-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg425894(v=OCS.15))

  - [移除-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398791(v=OCS.15))

  - [移除-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425810(v=OCS.15))

  - [Remove-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg399057(v=OCS.15))

  - [移除-CsExUmContact](rehttps://technet.microsoft.com/en-us/library/Gg425842(v=OCS.15))

  - [移除-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg413064(v=OCS.15))

  - [移除-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205201(v=OCS.15))

  - [移除-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425794(v=OCS.15))

  - [移除-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg398211(v=OCS.15))

  - [移除-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg425809(v=OCS.15))

  - [移除-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398171(v=OCS.15))

  - [Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg413052(v=OCS.15))

  - [移除-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg425722(v=OCS.15))

  - [移除-CsLisPort](https://technet.microsoft.com/en-us/library/Gg412899(v=OCS.15))

  - [移除-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398904(v=OCS.15))

  - [移除-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg413053(v=OCS.15))

  - [移除-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg398352(v=OCS.15))

  - [移除-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398461(v=OCS.15))

  - [Remove-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398727(v=OCS.15))

  - [移除-CsManagementConnection](https://technet.microsoft.com/en-us/library/Gg425803(v=OCS.15))

  - [移除-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690026(v=OCS.15))

  - [移除-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg398705(v=OCS.15))

  - [移除-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15))

  - [Remove-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690048(v=OCS.15))

  - [移除-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398609(v=OCS.15))

  - [移除-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398938(v=OCS.15))

  - [移除-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398743(v=OCS.15))

  - [移除-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398963(v=OCS.15))

  - [移除-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398466(v=OCS.15))

  - [移除-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg413012(v=OCS.15))

  - [移除-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))

  - [移除-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg425726(v=OCS.15))

  - [移除-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205408(v=OCS.15))

  - [移除-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ204836(v=OCS.15))

  - [移除-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg398556(v=OCS.15))

  - [移除-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204820(v=OCS.15))

  - [移除-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ205350(v=OCS.15))

  - [移除-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204660(v=OCS.15))

  - [移除-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204767(v=OCS.15))

  - [移除-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ204927(v=OCS.15))

  - [移除-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204626(v=OCS.15))

  - [移除-CsPersistentChatMessage](https://technet.microsoft.com/en-us/library/JJ204668(v=OCS.15))

  - [Remove-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205301(v=OCS.15))

  - [移除-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204639(v=OCS.15))

  - [Remove-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398431(v=OCS.15))

  - [Remove-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg399070(v=OCS.15))

  - [移除-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ205036(v=OCS.15))

  - [移除-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg425821(v=OCS.15))

  - [移除-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398553(v=OCS.15))

  - [移除-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412906(v=OCS.15))

  - [移除-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690028(v=OCS.15))

  - [移除-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg425879(v=OCS.15))

  - [移除-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398482(v=OCS.15))

  - [移除-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ204711(v=OCS.15))

  - [移除-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg398969(v=OCS.15))

  - [Remove-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg398521(v=OCS.15))

  - [移除-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg398568(v=OCS.15))

  - [移除-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg398576(v=OCS.15))

  - [移除-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg398765(v=OCS.15))

  - [移除-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398643(v=OCS.15))

  - [移除-CsServerApplication](https://technet.microsoft.com/en-us/library/Gg398366(v=OCS.15))

  - [Remove-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg398515(v=OCS.15))

  - [移除-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398865(v=OCS.15))

  - [移除-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg412932(v=OCS.15))

  - [移除-CsSlaConfiguration](https://technet.microsoft.com/en-us/library/Mt703201(v=OCS.15))

  - [移除-CsSlaDelegates](https://technet.microsoft.com/en-us/library/Mt703203(v=OCS.15))

  - [Remove-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398668(v=OCS.15))

  - [移除-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398790(v=OCS.15))

  - [移除-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ204870(v=OCS.15))

  - [移除-New-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15))

  - [移除-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg398176(v=OCS.15))

  - [移除-CsTrustedApplicationComputer](https://technet.microsoft.com/en-us/library/Gg398838(v=OCS.15))

  - [移除-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398837(v=OCS.15))

  - [移除-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg398750(v=OCS.15))

  - [移除-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15))

  - [移除-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg398209(v=OCS.15))

  - [移除-CsUserAcp](https://technet.microsoft.com/en-us/library/Gg398982(v=OCS.15))

  - [Remove-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg425738(v=OCS.15))

  - [移除-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398722(v=OCS.15))

  - [移除-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ204629(v=OCS.15))

  - [移除-CsUserStoreBackupData](https://technet.microsoft.com/en-us/library/JJ205003(v=OCS.15))

  - [移除-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398804(v=OCS.15))

  - [移除-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398573(v=OCS.15))

  - [移除-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398501(v=OCS.15))

  - [移除-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398309(v=OCS.15))

  - [移除-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398468(v=OCS.15))

  - [移除-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ204799(v=OCS.15))

  - [移除-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412813(v=OCS.15))

  - [移除-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204926(v=OCS.15))

  - [移除-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398266(v=OCS.15))

  - [移除-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ205055(v=OCS.15))

  - [要求-CsCertificate](https://technet.microsoft.com/en-us/library/Gg425723(v=OCS.15))

  - [Reset-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398181(v=OCS.15))

  - [Restore-CsDeviceUpdateRule](https://technet.microsoft.com/en-us/library/Gg398305(v=OCS.15))

  - [吊銷-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg425748(v=OCS.15))

  - [吊銷-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398977(v=OCS.15))

  - [吊銷-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg425834(v=OCS.15))

  - [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))

  - [Set-CsAddressBookConfiguration](https://technet.microsoft.com/en-us/library/Gg412784(v=OCS.15))

  - [Set-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399066(v=OCS.15))

  - [Set-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398931(v=OCS.15))

  - [Set-CsAnalogDevice](https://technet.microsoft.com/en-us/library/Gg412843(v=OCS.15))

  - [Set-CsAnnouncement](https://technet.microsoft.com/en-us/library/Gg425752(v=OCS.15))

  - [Set-CsApplicationServer](https://technet.microsoft.com/en-us/library/Gg398562(v=OCS.15))

  - [Set-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg413030(v=OCS.15))

  - [Set-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg398294(v=OCS.15))

  - [Set-CsArchivingServer](https://technet.microsoft.com/en-us/library/Gg398923(v=OCS.15))

  - [Set-CsAudioTestServiceApplication](https://technet.microsoft.com/en-us/library/Gg398907(v=OCS.15))

  - [Set-CsAutodiscoverConfiguration](https://technet.microsoft.com/en-us/library/Hh689980(v=OCS.15))

  - [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))

  - [Set-CsBackupServiceConfiguration](https://technet.microsoft.com/en-us/library/JJ205006(v=OCS.15))

  - [Set-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412863(v=OCS.15))

  - [Set-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398090(v=OCS.15))

  - [Set-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398796(v=OCS.15))

  - [Set-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/en-us/library/Gg412836(v=OCS.15))

  - [Set-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398774(v=OCS.15))

  - [Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))

  - [Set-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398929(v=OCS.15))

  - [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398300(v=OCS.15))

  - [Set-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15))

  - [Set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15))

  - [Set-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg425790(v=OCS.15))

  - [Set-CsClsRegion](https://technet.microsoft.com/en-us/library/JJ204746(v=OCS.15))

  - [Set-CsClsScenario](https://technet.microsoft.com/en-us/library/JJ204622(v=OCS.15))

  - [Set-CsClsSearchTerm](https://technet.microsoft.com/en-us/library/JJ204911(v=OCS.15))

  - [Set-CsClsSecurityGroup](https://technet.microsoft.com/en-us/library/JJ204700(v=OCS.15))

  - [Set-CsCommonAreaPhone](https://technet.microsoft.com/en-us/library/Gg398579(v=OCS.15))

  - [Set-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398776(v=OCS.15))

  - [Set-CsConferenceServer](https://technet.microsoft.com/en-us/library/Gg398738(v=OCS.15))

  - [Set-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412969(v=OCS.15))

  - [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425788(v=OCS.15))

  - [Set-CsConfigurationStoreLocation](https://technet.microsoft.com/en-us/library/Gg398258(v=OCS.15))

  - [Set-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412721(v=OCS.15))

  - [Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15))

  - [Set-CsDiagnosticConfiguration](https://technet.microsoft.com/en-us/library/Gg425734(v=OCS.15))

  - [Set-CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/en-us/library/Gg399045(v=OCS.15))

  - [Set-CsDialInConferencingAccessNumber](https://technet.microsoft.com/en-us/library/Gg425770(v=OCS.15))

  - [Set-CsDialInConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg425825(v=OCS.15))

  - [Set-CsDialInConferencingDtmfConfiguration](https://technet.microsoft.com/en-us/library/Gg398860(v=OCS.15))

  - [Set-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398644(v=OCS.15))Set-CsDialPlan

  - [Set-CsDirector](https://technet.microsoft.com/en-us/library/Gg398565(v=OCS.15))

  - [Set-CsEdgeServer](https://technet.microsoft.com/en-us/library/Gg398859(v=OCS.15))

  - [Set-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398620(v=OCS.15))

  - [Set-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398916(v=OCS.15))

  - [Set-CsExUmContact](https://technet.microsoft.com/en-us/library/Gg412944(v=OCS.15))

  - [Set-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425736(v=OCS.15))

  - [Set-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205084(v=OCS.15))

  - [Set-CsHealthMonitoringConfiguration](https://technet.microsoft.com/en-us/library/Gg425847(v=OCS.15))

  - [Set-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/Gg412722(v=OCS.15))

  - [Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))

  - [Set-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg412960(v=OCS.15))

  - [Set-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398232(v=OCS.15))

  - [Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15))

  - [Set-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg398757(v=OCS.15))

  - [Set-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398700(v=OCS.15))

  - [Set-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg425911(v=OCS.15))

  - [Set-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg399016(v=OCS.15))

  - [Set-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg412823(v=OCS.15))

  - [Set-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg412723(v=OCS.15))

  - [Set-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg412987(v=OCS.15))

  - [Set-CsManagementConnection](https://technet.microsoft.com/en-us/library/Gg413045(v=OCS.15))

  - [Set-CsMcxConfiguration](https://technet.microsoft.com/en-us/library/Hh690050(v=OCS.15))

  - [Set-CsManagementServer](https://technet.microsoft.com/en-us/library/Gg398465(v=OCS.15))

  - [Set-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg398580(v=OCS.15))

  - [Set-CsMediationServer](https://technet.microsoft.com/en-us/library/Gg398213(v=OCS.15))

  - [Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398648(v=OCS.15))

  - [Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204831(v=OCS.15))

  - [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/Hh690021(v=OCS.15))

  - [Set-CsMonitoringServer](https://technet.microsoft.com/en-us/library/Gg425776(v=OCS.15))

  - [Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398338(v=OCS.15))

  - [Set-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398927(v=OCS.15))

  - [Set-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398410(v=OCS.15))

  - [Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398772(v=OCS.15))

  - [Set-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg413089(v=OCS.15))

  - [Set-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg412867(v=OCS.15))

  - [Set-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))

  - [Set-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412739(v=OCS.15))

  - [Set-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ204841(v=OCS.15))

  - [Set-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ204896(v=OCS.15))

  - [Set-CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/en-us/library/JJ205400(v=OCS.15))

  - [Set-CsOutboundTranslationRule](https://technet.microsoft.com/en-us/library/Gg413073(v=OCS.15))

  - [Set-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204755(v=OCS.15))

  - [Set-CsPersistentChatActiveServer](https://technet.microsoft.com/en-us/library/JJ205065(v=OCS.15))

  - [Set-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204721(v=OCS.15))

  - [Set-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204952(v=OCS.15))

  - [Set-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204949(v=OCS.15))

  - [Set-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205122(v=OCS.15))

  - [Set-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205192(v=OCS.15))

  - [Set-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204801(v=OCS.15))

  - [Set-CsPersistentChatState](https://technet.microsoft.com/en-us/library/JJ205109(v=OCS.15))

  - [Set-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg412997(v=OCS.15))

  - [Set-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg425782(v=OCS.15))

  - [Set-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204833(v=OCS.15))

  - [Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398484(v=OCS.15))

  - [Set-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg425796(v=OCS.15))

  - [Set-CsPstnGateway](https://technet.microsoft.com/en-us/library/Gg398408(v=OCS.15))

  - [Set-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg399069(v=OCS.15))

  - [Set-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg413087(v=OCS.15))

  - [Set-CsPushNotificationConfiguration](https://technet.microsoft.com/en-us/library/Hh690013(v=OCS.15))

  - [Set-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg398245(v=OCS.15))

  - [Set-CsRegistrar](https://technet.microsoft.com/en-us/library/Gg398993(v=OCS.15))

  - [Set-CsRegistrarConfiguration](https://technet.microsoft.com/en-us/library/Gg398764(v=OCS.15))

  - [Set-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ205075(v=OCS.15))

  - [Set-CsRgsAgentGroup](https://technet.microsoft.com/en-us/library/Gg425955(v=OCS.15))

  - [Set-CsRgsConfiguration](https://technet.microsoft.com/en-us/library/Gg425728(v=OCS.15))

  - [Set-CsRgsHolidaySet](https://technet.microsoft.com/en-us/library/Gg398736(v=OCS.15))

  - [Set-CsRgsHoursOfBusiness](https://technet.microsoft.com/en-us/library/Gg412929(v=OCS.15))

  - [Set-CsRgsQueue](https://technet.microsoft.com/en-us/library/Gg412947(v=OCS.15))

  - [Set-CsRgsWorkflow](https://technet.microsoft.com/en-us/library/Gg425845(v=OCS.15))

  - [Set-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412811(v=OCS.15))

  - [Set-CsServerApplication](https://technet.microsoft.com/en-us/library/Gg412850(v=OCS.15))

  - [Set-CsSimpleUrlConfiguration](https://technet.microsoft.com/en-us/library/Gg412991(v=OCS.15))

  - [Set-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg412949(v=OCS.15))

  - [Set-CsSipResponseCodeTranslationRule](https://technet.microsoft.com/en-us/library/Gg425895(v=OCS.15))

  - [Set-CsSite](https://technet.microsoft.com/en-us/library/Gg413023(v=OCS.15))

  - [Set-CsSlaConfiguration](https://technet.microsoft.com/en-us/library/Mt703202(v=OCS.15))

  - [Set-CsStaticRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398724(v=OCS.15))

  - [Set-CsTestDevice](https://technet.microsoft.com/en-us/library/Gg398156(v=OCS.15))

  - [Set-CsTrunkConfiguration](https://technet.microsoft.com/en-us/library/Gg398238(v=OCS.15))

  - [Set-CsTrustedApplication](https://technet.microsoft.com/en-us/library/Gg425840(v=OCS.15))

  - [Set-CsTrustedApplicationEndpoint](https://technet.microsoft.com/en-us/library/Gg398509(v=OCS.15))

  - [Set-CsTrustedApplicationPool](https://technet.microsoft.com/en-us/library/Gg398187(v=OCS.15))

  - [Set-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg413042(v=OCS.15))

  - [Set-CsUICulture](https://technet.microsoft.com/en-us/library/Gg398354(v=OCS.15))

  - [Set-CsUnassignedNumber](https://technet.microsoft.com/en-us/library/Gg399033(v=OCS.15))

  - [Set-Move-csuser](https://technet.microsoft.com/en-us/library/Gg398510(v=OCS.15))

  - [Set-CsUserAcp](https://technet.microsoft.com/en-us/library/Gg413018(v=OCS.15))

  - [Set-CsUserDatabaseState](https://technet.microsoft.com/en-us/library/Gg412973(v=OCS.15))

  - [Set-CsUserReplicatorConfiguration](https://technet.microsoft.com/en-us/library/Gg398540(v=OCS.15))

  - [Set-CsUserServer](https://technet.microsoft.com/en-us/library/Gg413026(v=OCS.15))

  - [Set-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398340(v=OCS.15))

  - [Set-CsUserServicesPolicy](https://technet.microsoft.com/en-us/library/JJ205414(v=OCS.15))

  - [Set-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398967(v=OCS.15))

  - [Set-CsVoicemailReroutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412948(v=OCS.15))

  - [Set-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398491(v=OCS.15))

  - [Set-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg399021(v=OCS.15))

  - [Set-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg412893(v=OCS.15))

  - [Set-CsVoiceRoutingPolicy](https://technet.microsoft.com/en-us/library/JJ205313(v=OCS.15))

  - [Set-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398614(v=OCS.15))

  - [Set-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204620(v=OCS.15))

  - [Set-CsWebServer](https://technet.microsoft.com/en-us/library/Gg398759(v=OCS.15))

  - [Set-CsWebServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398396(v=OCS.15))

  - [Set-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204686(v=OCS.15))

  - [Set-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204769(v=OCS.15))

  - [開始-CsWindowsService](https://technet.microsoft.com/en-us/library/Gg398561(v=OCS.15))

  - [停止 CsWindowsService](https://technet.microsoft.com/en-us/library/Gg398426(v=OCS.15))

  - [同步處理-CsUserData](https://technet.microsoft.com/en-us/library/JJ205242(v=OCS.15))

  - [Test-CsAddressBookService](https://technet.microsoft.com/en-us/library/Gg398661(v=OCS.15))

  - [Test-CsAddressBookWebQuery](https://technet.microsoft.com/en-us/library/Gg398773(v=OCS.15))

  - [Test-CsASConference](https://technet.microsoft.com/en-us/library/JJ205227(v=OCS.15))

  - [Test-CsAudioConferencingProvider](https://technet.microsoft.com/en-us/library/JJ205117(v=OCS.15))

  - [Test-CsAVConference](https://technet.microsoft.com/en-us/library/Gg412749(v=OCS.15))

  - [Test-CsAVEdgeConnectivity](https://technet.microsoft.com/en-us/library/JJ205138(v=OCS.15))

  - [Test-CsCertificateConfiguration](https://technet.microsoft.com/en-us/library/Gg398647(v=OCS.15))

  - [Test-CsComputer](https://technet.microsoft.com/en-us/library/Gg398162(v=OCS.15))

  - [Test-CsDatabase](https://technet.microsoft.com/en-us/library/JJ204839(v=OCS.15))

  - [Test-CsDataConference](https://technet.microsoft.com/en-us/library/JJ205219(v=OCS.15))

  - [Test-CsDialInConferencing](https://technet.microsoft.com/en-us/library/Gg399013(v=OCS.15))

  - [Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))

  - [Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15))

  - [Test-CsExStorageNotification](https://technet.microsoft.com/en-us/library/JJ205331(v=OCS.15))

  - [Test-CsExUMConnectivity](https://technet.microsoft.com/en-us/library/JJ204784(v=OCS.15))

  - [Test-CsExUMVoiceMail](https://technet.microsoft.com/en-us/library/JJ205058(v=OCS.15))

  - [Test-CsFederatedPartner](https://technet.microsoft.com/en-us/library/Gg398281(v=OCS.15))

  - [Test-CsGroupExpansion](https://technet.microsoft.com/en-us/library/Gg399009(v=OCS.15))

  - [Test-CsGroupIM](https://technet.microsoft.com/en-us/library/Gg398273(v=OCS.15))

  - [Test-CsIM](https://technet.microsoft.com/en-us/library/Gg425802(v=OCS.15))

  - [Test-CsInterTrunkRouting](https://technet.microsoft.com/en-us/library/JJ204741(v=OCS.15))

  - [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))

  - [Test-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg425914(v=OCS.15))

  - [Test-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398497(v=OCS.15))

  - [Test-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg425962(v=OCS.15))

  - [Test-CsMcxConference](https://technet.microsoft.com/en-us/library/Hh690045(v=OCS.15))

  - [Test-CsMcxP2PIM](https://technet.microsoft.com/en-us/library/Hh690020(v=OCS.15))

  - [Test-CsMcxPushNotification](https://technet.microsoft.com/en-us/library/Hh690043(v=OCS.15))

  - [Test-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398787(v=OCS.15))

  - [Test-CsP2PAV](https://technet.microsoft.com/en-us/library/Gg412821(v=OCS.15))

  - [Test-CsPersistentChatMessage](https://technet.microsoft.com/en-us/library/JJ204656(v=OCS.15))

  - [Test-CsPhoneBootstrap](https://technet.microsoft.com/en-us/library/Gg412852(v=OCS.15))

  - [Test-CsPresence](https://technet.microsoft.com/en-us/library/Gg398148(v=OCS.15))

  - [Test-CsPstnOutboundCall](https://technet.microsoft.com/en-us/library/Gg398207(v=OCS.15))

  - [Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/en-us/library/Gg398662(v=OCS.15))

  - [Test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15))

  - [Test-CsReplica](https://technet.microsoft.com/en-us/library/JJ205289(v=OCS.15))

  - [Test-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398428(v=OCS.15))

  - [Test-CsTopology](https://technet.microsoft.com/en-us/library/Gg398127(v=OCS.15))

  - [Test-New-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg398137(v=OCS.15))

  - [Test-CsUnifiedContactStore](https://technet.microsoft.com/en-us/library/JJ204662(v=OCS.15))

  - [Test-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg399003(v=OCS.15))

  - [Test-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))

  - [Test-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))

  - [Test-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398260(v=OCS.15))

  - [Test-CsVoiceUser](https://technet.microsoft.com/en-us/library/Gg413013(v=OCS.15))

  - [Test-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204652(v=OCS.15))

  - [Test-CsWebApp](https://technet.microsoft.com/en-us/library/Hh689989(v=OCS.15))

  - [Test-CsWebAppAnonymous](https://technet.microsoft.com/en-us/library/Hh690041(v=OCS.15))

  - [Test-CsWebScheduler](https://technet.microsoft.com/en-us/library/JJ204829(v=OCS.15))

  - [Test-CsXmppIM](https://technet.microsoft.com/en-us/library/JJ205423(v=OCS.15))

  - [Uninstall-CsDatabase](unhttps://technet.microsoft.com/en-us/library/Gg399044(v=OCS.15))

  - [Uninstall-CsMirrorDatabase](unhttps://technet.microsoft.com/en-us/library/JJ204986(v=OCS.15))

  - [解除鎖定-CsClientPin](unhttps://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))

  - [取消發佈-CsLisConfiguration](unhttps://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))

  - [更新-CsAddressBook](https://technet.microsoft.com/en-us/library/Gg398194(v=OCS.15))

  - [更新-CsAdminRole](https://technet.microsoft.com/en-us/library/JJ204851(v=OCS.15))

  - [Update-CsTenantMeetingUrl](https://technet.microsoft.com/en-us/library/Dn424754(v=OCS.15))

  - [Update-CsUserData](https://technet.microsoft.com/en-us/library/JJ205358(v=OCS.15))

  - [更新-CsUserDatabase](https://technet.microsoft.com/en-us/library/Gg398682(v=OCS.15))

</div>

</div>

<span> </span>

</div>

</div>

</div>

