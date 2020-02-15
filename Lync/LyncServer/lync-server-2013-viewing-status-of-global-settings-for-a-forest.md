---
title: Lync Server 2013： 檢視狀態的樹系的通用設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a5381445a866da924a8ff0f511ee48353ab5c91
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041970"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a>檢視狀態的 Lync Server 2013 中的樹系的全域設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-05-20 個_

系統管理員應該檢閱每月的 Lync Server 2013 部署的全域設定。 目標是將檢閱實作的設定對一組已知的設定 — 基準組態，以協助確保設定均有效，並判斷是否應更新文件的基準。 變更全域設定應該實作透過應該包含記載的新設定的變更控制程序。

下列各節將說明應檢閱的全域設定：

<div>

## <a name="check-general-settings"></a>檢查一般設定

檢查一般設定，包括針對 Lync Server 2013 支援的工作階段初始通訊協定 (SIP) 網域。

使用 Windows PowerShell 和**Get-cssipdomain**指令程式，可以傳回 SIP 網域資訊。 若要傳回這項資訊，請執行`Get-CsSipDomain`Windows PowerShell 命令。

Get-cssipdomain 會傳回類似的所有授權的 SIP 網域的資訊：

Identity 名稱 IsDefault

\-------- ---- ---------

fabrikam.com fabrikam.com True

na.fabrikam.com na.fabrikam.com False

如果的 IsDefault 屬性設為 True，對應的網域就會是預設 SIP 網域。 您可以使用 Set CsSipDomain 指令程式來變更預設 SIP 網域，為您的組織。 不過，您只是無法刪除預設 SIP 網域，因為這樣會讓您沒有預設網域。 如果您想要刪除 fabrikam.com 網域 （如上述範例所示），您必須先設定 na.fabrikam.com 設為預設網域。

</div>

<div>

## <a name="check-meeting-settings"></a>請檢查會議設定

會議的設定包括會議原則定義，並參與會議的匿名使用者支援。

使用 Windows PowerShell 和**Get-csmeetingconfiguration** cmdlet 可以擷取會議組態設定。 例如，此命令會傳回的資訊將全域會議組態設定：

Get-csmeetingconfiguration – Identity"Global"會議組態設定也可以在網站範圍設定。 因此，您可能想要使用下列命令，它會傳回所有會議的相關資訊的組態設定：

`Get-CsMeetingConfiguration`

**Get-csmeetingconfiguration** cmdlet 會傳回類似下列資訊：

身分識別： 全域

PstnCallersBypassLobby: True

EnableAssignedConferenceType: True

DesignateAsPresenter： 公司

AssignedConferenceTypeByDefault: True

AdmitAnonymousUsersByDefault: True

同樣地，最後一個項目在清單中， **AdmitAnonymousUsersByDefault**，啟用或停用匿名使用者能夠參與會議。

當檢查會議組態設定，您可能會覺得比較目前的設定，針對預設的等同項目。 您可以檢視預設的會議組態設定執行下列命令：

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

上述命令會建立在記憶體-僅限執行個體全域會議組態設定，每個屬性會使用預設值的執行個體。 不實際會議的組態設定執行命令時建立。 不過，將螢幕上顯示的預設屬性值。

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a>檢查 Edge Server 以及其設定

可以使用 Windows PowerShell 擷取 edge 伺服器資訊。 此命令會傳回設定供組織使用的所有 Edge Server 的相關資訊：

`Get-CsService -EdgeServer`

傳回的資訊包括所有的 FQDN 和連接埠設定為每部 Edge Server:

身分識別： EdgeServer: dc.fabrikam.com

登錄器： Registrar: LYNC SE.fabrikam.com

AccessEdgeInternalSipPort: 5061

AccessEdgeExternalSipPort: 5061

AccessEdgeClientPort: 443

DataPsomServerPort: 8057

DataPsomClientPort: 444

MediaRelayAuthEdgePort: 5062

MediaRelayAuthInternalTurnTcpPort: 443

MediaRelayAuthExternalTurnTcpPort: 445

MediaRelayAuthInternalTurnUdpPort: 3478

MediaRelayAuthExternalTurnUdpPort: 3478

MediaCommunicationPortStart: 50000

MediaComunicationPortCount: 10000

AccessEdgeExternalFqdn: dc.fabrikam.com

DataEdgeExternalFqdn: dc.fabrikam.com

AVEdgeExternalFqdn:

InternalInterfaceFqdn:

ExternalMrasFqdn: dc.fabrikam.com

DependentServiceList: {Registrar: LYNC-SE.fabrikam.com，

ConferencingServer:LYNC-SE.fabrikam

com、 MediationServer:LYNC-SE。

fabrikam.com}

ServiceId: fabrikam.com-EdgeServer-2

SiteId: site:fabrikam.com

PoolFqdn: dc.fabrikam.com

版： 5

角色： EdgeServer

<div>

## <a name="check-federation-settings"></a>檢查同盟設定

檢查同盟設定，例如是否設定，若答案為"yes，"，FQDN 和連接埠。 啟用並使用 Access Edge 組態設定的全域集合來停用同盟。 除此之外，這些表示同盟已根據全： 同盟啟用整個組織或整個組織的已停用同盟

使用 Windows PowerShell，可以傳回 Access Edge 組態設定。 若要這麼做，請執行下列 Windows PowerShell 命令：

`Get-CsAccessEdgeConfiguration`

接著，該命令會傳回資料類似這樣：

身分識別： 全域

AllowAnonymousUsers: False

AllowFederatedUsers: False

AllowOutsideUsers: False

BeClearingHouse: False

將 EnablePartnerDiscovery: False

EnableArchivingDisclaimer: False

KeepCrlsUpToDateForPeers: True

MarkSourceVerifiableOnOutgoingMessages: True

OutgoingTlsCountForFederatedPartners: 4

RoutingMethod: UseDnsSrvRouting

如果**AllowFederatedUsers**屬性設為 True，這表示，為您的組織啟用同盟。 （設定為 True 也會表示，在分割網域案例中，您的內部部署使用者將能夠與您在雲端使用者順暢地溝通**AllowFederatedUsers** ）。

若要擷取的 FQDN 和連接埠設定為您的 Edge Server，請參閱 < 在之前的工作 （Edge Server 和其設定）。

啟用全域範圍的聯盟只表示使用者可能可以與同盟使用者進行通訊。 若要判斷任何個別的使用者是否可以與同盟使用者實際通訊需要您檢查指派給該使用者的外部使用者存取原則。

使用 Windows PowerShell，可以傳回外部使用者存取資訊。 例如，此命令會傳回通用的外部使用者存取原則的資訊：

`Get-CsExternalAccessPolicy -Identity "Global"`

而此命令會傳回所有外部使用者存取原則的資訊：

`Get-CsExternalAccessPolicy`

傳回的資訊會類似這樣：

身分識別： False

描述：

EnableFederationAccess: False

EnablePublicCloudAccess: False

EnablePublicCloudAccessAudioVideoAccess: False

EnableOutsideAccess: False

**EnableFederationAccess**設定為 True，如果指定的原則所管理的使用者能夠與同盟使用者。

</div>

</div>

<div>

## <a name="check-archiving-settings"></a>檢查封存設定

檢查內部和同盟通訊的封存設定值。前驗證設定內部和外部封存，您應該確認已啟用封存。

使用 Windows PowerShell 和 Get-csarchivingconfiguration cmdlet 可驗證封存組態設定：

`Get-CsArchivingConfiguration -Identity "Global"`

請注意，封存設定也可以設定在網站範圍。 若要傳回所有封存設定的相關資訊，請使用此命令：

`Get-CsArchivingConfiguration`

Get-csarchivingconfiguration cmdlet 會傳回類似下列的資料：

身分識別： 全域

EnableArchiving: False

EnablePurging: False

PurgeExportedArchivesOnly: False

BlockOnArchiveFailure: False

KeepArchivingDataForDays: 14

PurgeHourOfDay: 2

ArchiveDuplicateMessages: True

CachePurgingInterval: 24

如果 EnableArchiving 屬性設為 False，表示沒有通訊工作階段將會封存。 如果您想要封存立即訊息工作階段僅，使用如下所示的命令來啟用 IM 工作階段的封存：

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

若要封存會議工作階段和立即訊息工作階段，請使用此命令：

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

如果您想要比較目前的封存設定具有預設設定，請執行下列 Windows PowerShell 命令：

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

該命令會建立全域封存組態設定中的記憶體-僅限執行個體。 這不是實際的設定集合使用的 Lync Server。 不過，它並未顯示所有的封存設定屬性的預設值。

您也可以使用此命令來傳回一部封存伺服器的 FQDN:

`Get-CsService -ArchivingServer`

確認啟用封存之後，然後，您就可以檢視您封存原則，以判斷是否內部及封存外部通訊工作階段。

使用 Get-csarchivingpolicy 指令程式可以擷取封存原則資訊。 例如，此命令會傳回通用的封存原則的相關資訊：

`Get-CsArchivingPolicy -Identity "Global"`

因為封存原則也可以在網站和個別使用者範圍設定，您可能還想要使用此命令，它會傳回所有的封存原則的相關資訊：

`Get-CsArchivingPolicy`

您收到來自 Get-csarchivingpolicy 的資訊會類似這樣：

身分識別： 全域

描述：

將 ArchiveInternal: False

ArchiveExternal: False

請注意，根據預設，內部和外部封存中會停用封存原則。

</div>

<div>

## <a name="check-cdr-settings"></a>請檢查 CDR 設定

檢查端對端、 會議及語音詳細通話記錄的詳細通話記錄 (CDR) 設定。 使用**Get-cscdrconfiguration** cmdlet，可以傳回關於 CDR 設定的詳細的資訊。 例如，此命令會傳回關於 CDR 全域集合的組態設定：

`Get-CsCdrConfiguration -Identity "Global"`

CDR 也可以在網站範圍設定，因為您可能還想要執行此命令，傳回所有 CDR 組態設定的相關資訊：

`Get-CsCdrConfiguration`

Get-cscdrconfiguration cmdlet 會傳回每個集合的 CDR 組態設定這類似下列的資訊：

身分識別： 全域

EnableCDR: True

EnablePurging: True

KeepCallDetailForDays: 60

KeepErrorReportForDays: 60

PurgeHourOfDay: 2

類似的資訊可以被傳回 qoe 監控使用 Get-csqoeconfiguration 指令程式。 例如，此命令會傳回全域的 QoE 組態設定集合的相關資訊：

`Get-QoEConfiguration -Identity "Global"`

該資訊將會看起來像：

身分識別： 全域

ExternalConsumerIssuedCertId:

EnablePurging: True

KeepQoEDataForDays: 60

PurgeHourOfDay: 1

EnableExternalConsumer: False

ExternalConsumerName:

ExternalConsumerURL:

EnableQoE: True

如果您想要比較目前的 CDR 設定與預設 CDR 設定，可以執行這個命令檢閱預設值：

`New-CsCdrConfiguration -Identity "Global" -InMemory`

同樣地，可以使用此命令擷取 QoE 監控的預設值：

`New-CsQoEConfiguration -Identity "Global" -InMemory`

您也可以藉由執行此命令傳回的監控伺服器的 FQDN:

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a>請檢查語音設定

系統管理員通常是重要的語音設定都包含在語音原則和語音路由： 語音原則包含判斷對個別使用者 （例如能夠順向或轉接電話），同時公開功能的設定語音路由決定如何 （以及如果） PSTN 之間路由傳送通話。

可以使用 Windows PowerShell 擷取語音原則資訊。 例如，此命令會傳回全域語音原則的相關資訊：

`Get-CsVoicePolicy -Identity "Global"`

而此命令會傳回設定供組織使用的所有語音原則的相關資訊：

`Get-CsVoicePolicy`

Get-csvoicepolicy cmdlet 所傳回的資訊類似如下：

身分識別： 全域

PstnUsages:{}

描述：

AllowSimulRing: True

AllowCallForwarding: True

AllowPSTNReRouting: True

名稱： DefaultPolicy

EnableDelegation: True

EnableTeamCall: True

EnableCallTransfer: True

EnableCallPark: False

EnableMaliciousCallTracing: False

EnableBWPolicyOverride: False

PreventPSTNTollBypass: False

您也可以建立傳回您的語音原則的子集的查詢。 例如，此命令會傳回所有允許來電轉接的語音原則：

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

而此命令會傳回所有不允許來電轉接的語音原則：

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

在 Windows PowerShell 中使用 Get-CsVoiceRouting cmdlet 傳回語音路由的資訊：

`Get-CsVoiceRoute`

該命令會傳回這項目的所有語音路由的資訊：

身分識別： LocalRoute

優先順序： 0

描述：

NumberPattern: ^ (\\+ 1\[0-9\]{10}) $

PstnUsages:{}

PstnGatewayList:{}

名稱： LocalRoute

SuppressCallerId:

AlternateCallerId:

Lync Server 可讓您建立語音路由，不需要 PSTN 使用方式，而且未指定 PSTN 閘道。 不過，您不能透過語音路由，不需要設定下列兩個屬性值實際上路由通話。 因此，您可能會覺得定期執行此命令，它會傳回任何不需要 PSTN 使用方式的語音路由的身分識別：

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

同樣地，此命令會傳回任何尚未設定為有 PSTN 閘道的語音路由的身分識別：

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a>請檢查會議服務員設定

檢查 PSTN 電話撥入式會議的會議服務員設定。 僅能使用**Get-csdialinconferencingconfiguration**指令程式擷取會議服務員設定。 這些設定不在 Lync Server Control Panel 中使用。 若要檢視您的會議服務員設定，請使用類似下列項目，它會傳回會議服務員設定全域集合的 Windows PowerShell 命令：

`Get-CsDialInConferencingConfiguration -Identity "Global"`

請注意也可以在網站範圍設定會議服務員設定。 若要傳回所有會議服務員設定的相關資訊，請改為使用此命令：

`Get-CsDialInConferencingConfiguration`

Get-csdialinconferencingconfiguration cmdlet 會傳回類似下列的資料：

身分識別： 全域

EntryExitAnnouncementsType: UseNames

EnableNameRecording: True

EntryExitAnnouncementsEnabledByDefault: False

如果 EntryExitAnnouncementsEnabledByDefault 設為 False，表示會議宣告已停用。 若要啟用進入與離開宣告，執行 Windows PowerShell 命令類似這樣：

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a>另請參閱


[Get-cssipdomain](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[Get-csmeetingconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[Get-csservice](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Get-csaccessedgeconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[Get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Get-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[Get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[Get-csqoeconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[Get-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get-csvoiceroute](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[Get-csdialinconferencingconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

