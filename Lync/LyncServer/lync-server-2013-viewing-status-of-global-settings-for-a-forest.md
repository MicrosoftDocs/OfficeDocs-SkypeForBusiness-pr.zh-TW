---
title: Lync Server 2013：查看樹系的全域設定狀態
description: Lync Server 2013：查看樹系全域設定的狀態。
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
ms.openlocfilehash: d9f722ea66f6c54c816703bd1af1d3def57bbd84
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567589"
---
# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a>在 Lync Server 2013 中查看樹系全域設定的狀態

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-20_

管理員應該每月檢查 Lync Server 2013 部署的全域設定。 目標是複查針對一組已知設定所實施的設定，這是一個基準設定，可協助保證設定有效，並判斷是否應該更新基準檔。 對全域設定所做的變更應透過應包含記錄新設定的變更控制過程來實施。

下列各節將說明應該檢查的全域設定：

<div>

## <a name="check-general-settings"></a>檢查一般設定

檢查 [一般設定]，包括 Lync Server 2013 (SIP) 網域的支援的會話初始通訊協定。

SIP 網域資訊可使用 Windows PowerShell 和 **Get-CsSipDomain** Cmdlet 傳回。 若要傳回此資訊，請執行 `Get-CsSipDomain` Windows PowerShell 命令。

Get-CsSipDomain 會針對所有已獲授權的 SIP 網域，傳回類似以下的資訊：

身分識別名稱 IsDefault

\-------- ---- ---------

fabrikam.com fabrikam.com True

na.fabrikam.com na.fabrikam.com False

如果 IsDefault 屬性設定為 True，對應的網域就是您的預設 SIP 網域。 您可以使用 Set-CsSipDomain Cmdlet 變更組織的預設 SIP 網域。 不過，您不能只刪除預設的 SIP 網域，因為這會讓您沒有預設網域。 如果您想要刪除 fabrikam.com 網域 (如先前範例) 所示，您必須先將 na.fabrikam.com 設定為您的預設網域。

</div>

<div>

## <a name="check-meeting-settings"></a>檢查會議設定

會議設定包括會議原則定義，以及在會議中參與匿名使用者的支援。

您可以使用 Windows PowerShell 和 **Get-CsMeetingConfiguration** Cmdlet 來找回會議設定設定。 例如，下列命令會傳回全域會議設定的相關資訊：

Get-CsMeetingConfiguration –身分識別 "Global" 會議設定設定也可以在網站範圍設定。 因此，您可能會想要使用下列命令，該命令會傳回所有會議設定的相關資訊：

`Get-CsMeetingConfiguration`

**Get-CsMeetingConfiguration** Cmdlet 會傳回類似下列的資訊：

身分識別：全域

PstnCallersBypassLobby： True

EnableAssignedConferenceType： True

DesignateAsPresenter：公司

AssignedConferenceTypeByDefault： True

AdmitAnonymousUsersByDefault： True

同樣地，清單中的最後一個專案會 **AdmitAnonymousUsersByDefault**，啟用或停用匿名使用者參與會議的功能。

檢查會議設定時，您可能會發現比較目前設定與預設對等專案是很有用的。 您可以執行下列命令來查看預設會議設定設定：

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

上一個命令會建立全域會議設定（僅限記憶體）實例的全域會議設定，此範例會使用每個屬性的預設值。 當您執行此命令時，並不會建立實際的會議設定。 不過，所有的預設屬性值都會顯示在螢幕上。

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a>檢查 Edge Server 及其設定

您可以使用 Windows PowerShell 來找回 Edge Server 資訊。 此命令會傳回設定供組織使用之所有 Edge Server 的資訊。

`Get-CsService -EdgeServer`

傳回的資訊包含各 Edge Server 的所有 FQDN 和埠設定：

Identity： Edgeserver atl-edge： dc.fabrikam.com

註冊機構：報名者： LYNC-SE.fabrikam.com

AccessEdgeInternalSipPort：5061

AccessEdgeExternalSipPort：5061

AccessEdgeClientPort：443

DataPsomServerPort：8057

DataPsomClientPort：444

MediaRelayAuthEdgePort：5062

MediaRelayAuthInternalTurnTcpPort：443

MediaRelayAuthExternalTurnTcpPort：445

MediaRelayAuthInternalTurnUdpPort：3478

MediaRelayAuthExternalTurnUdpPort：3478

MediaCommunicationPortStart：50000

MediaComunicationPortCount：10000

AccessEdgeExternalFqdn： dc.fabrikam.com

DataEdgeExternalFqdn： dc.fabrikam.com

AVEdgeExternalFqdn :

InternalInterfaceFqdn :

ExternalMrasFqdn： dc.fabrikam.com

DependentServiceList： {註冊機構： LYNC-SE.fabrikam.com，

ConferencingServer： LYNC-SE。 fabrikam

com，MediationServer： LYNC-SE。

fabrikam.com}

ServiceId： fabrikam.com-Edgeserver atl-edge-2

SiteId：網站:fabrikam

PoolFqdn： dc.fabrikam.com

版本：5

角色： Edgeserver atl-edge

<div>

## <a name="check-federation-settings"></a>檢查同盟設定

檢查同盟設定，例如是否已設定，以及是否為「是」，FQDN 和埠。 使用 Access Edge 設定的全域集合，啟用並停用同盟。 此外，這些也意味著同盟設定為全部或無基準：已為整個組織啟用同盟，或對整個組織停用同盟

您可以使用 Windows PowerShell 傳回您的 Access Edge 設定設定。 若要這麼做，請執行下列 Windows PowerShell 命令：

`Get-CsAccessEdgeConfiguration`

接著，該命令會傳回類似以下的資料：

身分識別：全域

AllowAnonymousUsers： False

AllowFederatedUsers： False

AllowOutsideUsers： False

BeClearingHouse： False

EnablePartnerDiscovery： False

EnableArchivingDisclaimer： False

KeepCrlsUpToDateForPeers： True

MarkSourceVerifiableOnOutgoingMessages： True

OutgoingTlsCountForFederatedPartners：4

RoutingMethod： UseDnsSrvRouting

如果 **AllowFederatedUsers** 屬性設定為 True，表示您的組織已啟用同盟。  (設定 **AllowFederatedUsers** 設定為 True 也表示，在分割網域案例中，您的內部部署使用者將能夠與您的雲端使用者無縫通訊。 ) 

若要取得 Edge Server 的 FQDN 及埠設定，請參閱上一個工作 (Edge Server 及其設定) 。

在全域範圍啟用同盟，只表示使用者可能會與同盟使用者通訊。 若要判斷是否有任何個別使用者可以實際與同盟使用者通訊，需要檢查指派給該使用者的外部使用者存取原則。

您可以使用 Windows PowerShell 傳回外部使用者存取訊號。 例如，下列命令會傳回全域外部使用者存取原則的資訊：

`Get-CsExternalAccessPolicy -Identity "Global"`

而且，此命令會傳回所有外部使用者存取原則的資訊：

`Get-CsExternalAccessPolicy`

傳回的資訊將如下所示：

身分識別： False

描述：

EnableFederationAccess： False

EnablePublicCloudAccess： False

EnablePublicCloudAccessAudioVideoAccess： False

EnableOutsideAccess： False

如果 **EnableFederationAccess** 設定為 True，則指定原則所管理的使用者可以與同盟使用者通訊。

</div>

</div>

<div>

## <a name="check-archiving-settings"></a>檢查封存設定

檢查內部及同盟通訊的封存設定。在驗證內部和外部封存的設定之前，您應該確認已啟用封存。

您可以使用 Windows PowerShell 和 Get-CsArchivingConfiguration Cmdlet 來驗證封存設定設定：

`Get-CsArchivingConfiguration -Identity "Global"`

請注意，也可以在網站範圍中設定封存設定。 若要傳回所有封存設定的資訊，請使用下列命令：

`Get-CsArchivingConfiguration`

Get-CsArchivingConfiguration Cmdlet 會傳回類似以下的資料：

身分識別：全域

EnableArchiving： False

EnablePurging： False

PurgeExportedArchivesOnly： False

BlockOnArchiveFailure： False

KeepArchivingDataForDays：14

PurgeHourOfDay：2

ArchiveDuplicateMessages： True

CachePurgingInterval：24

如果 EnableArchiving 屬性設定為 False，表示將不會封存任何通訊會話。 如果您只想要封存立即訊息會話，請使用類似下列的命令來啟用 IM 會話的封存：

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

若要封存會議會話和立即訊息會話，請使用此命令：

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

如果您想要將目前的封存設定與預設設定進行比較，請執行下列 Windows PowerShell 命令：

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

該命令會為全域封存設定設定建立僅限記憶體的實例。 這不是 Lync Server 所使用之實際設定的集合。 不過，它會顯示所有封存配置屬性的預設值。

您也可以使用此命令傳回封存伺服器的 FQDN：

`Get-CsService -ArchivingServer`

在您確認封存已啟用之後，您就可以查看封存原則，判斷是否要封存內部和外部通訊會話。

您可以使用 Get-CsArchivingPolicy Cmdlet 來檢索封存原則資訊。 例如，下列命令會傳回全域封存原則的相關資訊：

`Get-CsArchivingPolicy -Identity "Global"`

因為封存原則也可以在網站和個別使用者範圍內設定，所以您也可以使用此命令，傳回所有封存原則的相關資訊：

`Get-CsArchivingPolicy`

您從 Get-CsArchivingPolicy 取得的資訊如下所示：

身分識別：全域

描述：

ArchiveInternal： False

ArchiveExternal： False

請注意，預設會停用封存原則中的內部和外部封存。

</div>

<div>

## <a name="check-cdr-settings"></a>檢查 CDR 設定

檢查 (CDR) 設定對等、會議及語音通話詳細資料記錄的詳細通話記錄。 您可以使用 **Get-CsCdrConfiguration** CMDLET 傳回 CDR 設定的詳細資訊。 例如，下列命令會傳回全域 CDR 設定設定集合的資訊：

`Get-CsCdrConfiguration -Identity "Global"`

因為 CDR 也可以在網站範圍上進行設定，所以您也可能會想要執行此命令，以傳回所有 CDR 設定設定的相關資訊：

`Get-CsCdrConfiguration`

Get-CsCdrConfiguration Cmdlet 會針對每個 CDR 設定設定的集合，傳回類似以下的資訊：

身分識別：全域

EnableCDR： True

EnablePurging： True

KeepCallDetailForDays：60

KeepErrorReportForDays：60

PurgeHourOfDay：2

您可以透過使用 Get-CsQoEConfiguration Cmdlet，傳回 QoE 監視的類似資訊。 例如，下列命令會傳回全域 QoE 配置設定集合的資訊：

`Get-QoEConfiguration -Identity "Global"`

此資訊會類似如下：

身分識別：全域

ExternalConsumerIssuedCertId :

EnablePurging： True

KeepQoEDataForDays：60

PurgeHourOfDay：1

EnableExternalConsumer： False

ExternalConsumerName :

ExternalConsumerURL :

EnableQoE： True

如果您想要將目前的 CDR 設定與預設 CDR 設定進行比較，可以執行下列命令來複查預設值：

`New-CsCdrConfiguration -Identity "Global" -InMemory`

同樣地，您可以使用下列命令來檢索 QoE 監視的預設值：

`New-CsQoEConfiguration -Identity "Global" -InMemory`

您也可以執行下列命令，傳回監控伺服器的 FQDN：

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a>檢查語音設定

語音設定通常對系統管理員來說包含在語音原則和語音路由中：語音原則包含決定個別使用者的功能 (例如轉寄或轉接) 呼叫的功能）的設定，而語音路由會決定) 呼叫在 PSTN 間路由 (和呼叫的方式。

語音原則資訊可透過使用 Windows PowerShell 進行檢索。 例如，下列命令會傳回有關通用語音原則的資訊：

`Get-CsVoicePolicy -Identity "Global"`

而且此命令會傳回設定供組織使用之所有語音原則的資訊。

`Get-CsVoicePolicy`

Get-CsVoicePolicy Cmdlet 所傳回的資訊如下所示：

身分識別：全域

PstnUsages： {}

描述：

AllowSimulRing： True

AllowCallForwarding： True

AllowPSTNReRouting： True

名稱： DefaultPolicy

EnableDelegation： True

EnableTeamCall： True

EnableCallTransfer： True

EnableCallPark： False

EnableMaliciousCallTracing： False

EnableBWPolicyOverride： False

PreventPSTNTollBypass： False

您也可以建立傳回語音原則子集的查詢。 例如，此命令會傳回所有允許來電轉接的語音原則：

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

而且，此命令會傳回所有不允許來電轉接的語音原則：

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

在 [Windows PowerShell] 中，使用 Get-CsVoiceRouting Cmdlet 傳回語音路由的相關資訊：

`Get-CsVoiceRoute`

該命令會傳回所有語音路由的資訊，例如：

身分識別： LocalRoute

優先順序：0

描述：

NumberPattern： ^ (\\ + 1 \[ 0-9 \] {10}) $

PstnUsages： {}

PstnGatewayList： {}

名稱： LocalRoute

SuppressCallerId：

AlternateCallerId：

Lync Server 可讓您建立沒有 PSTN 使用方式的語音路由，也不會指定 PSTN 閘道。 不過，您實際上無法透過未設定這兩個屬性值的語音路由路由傳送呼叫。 因此，您可能會發現定期執行此命令會非常有用，它會傳回所有沒有 PSTN 使用狀況的語音路由的身分識別：

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

同樣地，此命令會傳回尚未設定為具有 PSTN 閘道之任何語音路由的身分識別：

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a>檢查會議助理設定

檢查 PSTN 電話撥入式會議的會議照管設定。 會議助理設定只能使用 **Get-CsDialInConferencingConfiguration** Cmdlet 來檢索。 在 Lync Server 控制台中無法使用這些設定。 若要查看會議助理設定，請使用與下列類似的 Windows PowerShell 命令，以傳回全域會議應答設定的集合：

`Get-CsDialInConferencingConfiguration -Identity "Global"`

請注意，也可以在網站範圍設定會議助理設定。 若要傳回所有會議助理設定的資訊，請改用下列命令：

`Get-CsDialInConferencingConfiguration`

Get-CsDialInConferencingConfiguration Cmdlet 會傳回類似以下的資料：

身分識別：全域

EntryExitAnnouncementsType： UseNames

EnableNameRecording： True

EntryExitAnnouncementsEnabledByDefault： False

如果 EntryExitAnnouncementsEnabledByDefault 設定為 False，表示停用會議宣告。 若要啟用進入和關閉宣告，請執行類似下列的 Windows PowerShell 命令：

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a>另請參閱


[Get-CsSipDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Get-CsAccessEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Get-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[Get-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[Get-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[Get-CsVoiceRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[Get-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

