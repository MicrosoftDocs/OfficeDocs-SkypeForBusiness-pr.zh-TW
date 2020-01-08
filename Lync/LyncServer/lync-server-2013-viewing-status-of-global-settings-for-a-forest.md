---
title: Lync Server 2013：查看林中全域設定的狀態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2215e0514f019e94467a204ae86e604dcc0da61
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a>在 Lync Server 2013 中查看林中全域設定的狀態

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-20_

系統管理員應該每月查看 Lync Server 2013 部署的全域設定。 這個目標就是針對一組已知的設定來查看已實施的設定，這是一種比較基準設定，可協助保證設定有效，並判斷是否應該更新基準檔。 全域設定的變更應該透過變更控制程式來實現，此程式應該包括記錄新設定。

在下列各節中將說明應審查的全域設定：

<div>

## <a name="check-general-settings"></a>檢查一般設定

檢查 [一般設定]，包括 Lync Server 2013 支援的會話初始通訊協定（SIP）網域。

SIP 網域資訊可以使用 Windows PowerShell 和**CsSipDomain** Cmdlet 傳回。 若要返回此資訊，請`Get-CsSipDomain`執行 Windows PowerShell 命令。

CsSipDomain 將會針對所有授權 SIP 網域傳回類似以下所示的資訊：

身分識別名稱 IsDefault

\-------- ---- ---------

fabrikam.com fabrikam.com True

na.fabrikam.com na.fabrikam.com False

如果 IsDefault 屬性設定為 True，對應的網域就是您的預設 SIP 網域。 您可以使用 CsSipDomain Cmdlet 來變更貴組織的預設 SIP 網域。 不過，您無法只刪除預設的 SIP 網域，因為這樣會讓您不需要預設網域。 如果您想要刪除 fabrikam.com 網域（如上一個範例所示），您必須先將 na.fabrikam.com 設定為預設網域。

</div>

<div>

## <a name="check-meeting-settings"></a>檢查會議設定

會議設定包括會議原則定義，以及在會議中參與匿名使用者的支援。

您可以使用 Windows PowerShell 和**CsMeetingConfiguration** Cmdlet 來檢索會議設定設定。 例如，以下命令會傳回有關全域會議設定設定的資訊：

CsMeetingConfiguration –身分識別 "全域" 會議設定設定也可以在網站範圍設定。 因此，您可能會想要使用下列命令，以傳回所有會議設定設定的相關資訊：

`Get-CsMeetingConfiguration`

**CsMeetingConfiguration** Cmdlet 會傳回如下所示的資訊：

身分識別：全域

PstnCallersBypassLobby： True

EnableAssignedConferenceType： True

DesignateAsPresenter：公司

AssignedConferenceTypeByDefault： True

AdmitAnonymousUsersByDefault： True

同樣地，清單中的最後一個專案**AdmitAnonymousUsersByDefault**，可以啟用或停用匿名使用者參與會議的功能。

檢查會議設定時，您可能會發現比較目前的設定與預設對等專案很有用。 您可以執行下列命令來查看預設會議設定設定：

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

[上一個] 命令會建立全域會議設定設定的純記憶體實例，該實例會使用每個屬性的預設值。 當您執行命令時，不會建立實際的會議設定。 不過，所有預設屬性值都會顯示在畫面上。

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a>檢查邊緣伺服器及其設定

您可以使用 Windows PowerShell 來檢索 Edge 伺服器資訊。 這個命令會傳回您在組織中設定為使用的所有邊緣伺服器的相關資訊：

`Get-CsService -EdgeServer`

傳回的資訊包含每個 Edge 伺服器的所有 FQDN 和埠設定：

身分識別： EdgeServer： dc.fabrikam.com

註冊機構：註冊機構： LYNC-SE.fabrikam.com

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

ConferencingServer： LYNC SE. fabrikam

com、MediationServer： LYNC-SE。

fabrikam.com}

ServiceId： fabrikam.com-EdgeServer-2

SiteId： site:fabrikam

PoolFqdn： dc.fabrikam.com

版本：5

角色： EdgeServer

<div>

## <a name="check-federation-settings"></a>檢查同盟設定

檢查同盟設定（例如是否已設定），如果答案是 "是，"，FQDN 和埠。 同盟是透過使用存取邊緣設定的全域集合來啟用和停用。 在其他專案中，這些代表將同盟設定為全或全是完全相同：針對整個組織啟用同盟，或針對整個組織停用同盟

您可以使用 Windows PowerShell 傳回您的存取邊緣設定。 若要執行此動作，請執行下列 Windows PowerShell 命令：

`Get-CsAccessEdgeConfiguration`

接著，該命令會傳回如下所示的資料：

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

RoutingMethod : UseDnsSrvRouting

如果**AllowFederatedUsers**屬性設為 True，則表示您的組織已啟用同盟。 （將**AllowFederatedUsers**設定為 True 也表示，在分割網域案例中，您的內部部署使用者將能夠與雲端使用者順暢地溝通。）

若要取得邊緣伺服器的 FQDN 和埠設定，請參閱上一個工作（邊緣伺服器及其設定）。

在全域範圍中啟用同盟，只表示使用者可能會與聯盟使用者通訊。 若要判斷是否有任何個別的使用者都能實際與同盟使用者通訊，需要您檢查指派給該使用者的外部使用者存取原則。

外部使用者存取訊號可以使用 Windows PowerShell 傳回。 例如，這個命令會傳回全域外部使用者存取原則的資訊：

`Get-CsExternalAccessPolicy -Identity "Global"`

這個命令會傳回所有外部使用者存取原則的資訊：

`Get-CsExternalAccessPolicy`

傳回的資訊將如下所示：

身分識別： False

說明

EnableFederationAccess： False

EnablePublicCloudAccess： False

EnablePublicCloudAccessAudioVideoAccess： False

EnableOutsideAccess： False

如果**EnableFederationAccess**設定為 True，則由指定原則管理的使用者可以與聯盟使用者通訊。

</div>

</div>

<div>

## <a name="check-archiving-settings"></a>檢查存檔設定

檢查內部和聯盟通訊的封存設定。在驗證內部和外部封存的設定前，您應該確認已啟用封存。

您可以使用 Windows PowerShell 和 CsArchivingConfiguration Cmdlet 來驗證封存配置設定：

`Get-CsArchivingConfiguration -Identity "Global"`

請注意，您也可以在網站範圍中設定存檔設定。 若要傳回所有存檔設定的相關資訊，請使用此命令：

`Get-CsArchivingConfiguration`

CsArchivingConfiguration Cmdlet 會傳回類似以下所示的資料：

身分識別：全域

EnableArchiving： False

EnablePurging： False

PurgeExportedArchivesOnly： False

BlockOnArchiveFailure： False

KeepArchivingDataForDays：14

PurgeHourOfDay：2

ArchiveDuplicateMessages： True

CachePurgingInterval：24

如果 EnableArchiving 屬性設為 False，即表示不會封存任何通訊會話。 如果您只想封存立即訊息會話，請使用如下所示的命令來啟用 IM 會話的存檔：

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

若要封存會議會話與立即訊息會話，請使用此命令：

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

如果您想要將目前的存檔設定與預設設定進行比較，請執行下列 Windows PowerShell 命令：

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

該命令會建立全域存檔設定的內部記憶體式實例。 這不是 Lync Server 所使用的真正設定集合。 不過，它會顯示所有存檔設定屬性的預設值。

您也可以使用這個命令來傳回封存伺服器的 FQDN：

`Get-CsService -ArchivingServer`

確認已啟用封存之後，您就可以查看您的封存原則，判斷內部和外部通訊會話是否已歸檔。

您可以使用 CsArchivingPolicy Cmdlet 來檢索存檔原則資訊。 例如，這個命令會傳回全域存檔原則的相關資訊：

`Get-CsArchivingPolicy -Identity "Global"`

因為歸檔原則也可以在網站和每個使用者的範圍內設定，所以您可能也會想要使用此命令，以傳回所有歸檔原則的相關資訊：

`Get-CsArchivingPolicy`

從 CsArchivingPolicy 收到的資訊將如下所示：

身分識別：全域

說明

ArchiveInternal： False

ArchiveExternal： False

請注意，在預設情況下，內部和外部封存都會在歸檔原則中停用。

</div>

<div>

## <a name="check-cdr-settings"></a>檢查 CDR 設定

檢查對等、會議和語音通話詳細資料錄製的通話詳細資料記錄（CDR）設定。 您的 CDR 設定的詳細資訊可以使用**CsCdrConfiguration** Cmdlet 傳回。 例如，這個命令會傳回有關 CDR 配置設定的全域集合的資訊：

`Get-CsCdrConfiguration -Identity "Global"`

因為 CDR 也可以在網站範圍進行設定，所以您可能也想要執行此命令，以傳回所有 CDR 設定設定的相關資訊：

`Get-CsCdrConfiguration`

CsCdrConfiguration Cmdlet 會針對每個 CDR 設定設定的集合傳回如下所示的資訊：

身分識別：全域

EnableCDR： True

EnablePurging： True

KeepCallDetailForDays：60

KeepErrorReportForDays：60

PurgeHourOfDay：2

您可以使用 CsQoEConfiguration Cmdlet 傳回 QoE 監視的類似資訊。 例如，這個命令會傳回 QoE 設定的全域集合資訊：

`Get-QoEConfiguration -Identity "Global"`

該資訊將如下所示：

身分識別：全域

ExternalConsumerIssuedCertId :

EnablePurging： True

KeepQoEDataForDays：60

PurgeHourOfDay：1

EnableExternalConsumer： False

ExternalConsumerName :

ExternalConsumerURL :

EnableQoE： True

如果您想要將目前的 CDR 設定與預設的 CDR 設定進行比較，您可以執行以下命令來查看預設值：

`New-CsCdrConfiguration -Identity "Global" -InMemory`

同樣地，您可以使用此命令來檢索 QoE 監視的預設值：

`New-CsQoEConfiguration -Identity "Global" -InMemory`

您也可以執行此命令，以傳回監視伺服器的 FQDN：

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a>檢查語音設定

在語音原則和語音路由中，語音原則通常都包含管理員的重要資訊：語音原則包含決定個別使用者所公開之功能的設定（例如轉寄或轉接來電的能力），同時語音路由決定如何在 PSTN 上路由（以及 if）通話。

您可以使用 Windows PowerShell 來檢索語音原則資訊。 例如，這個命令會傳回有關全域語音原則的資訊：

`Get-CsVoicePolicy -Identity "Global"`

這個命令會傳回已設定為在組織中使用之所有語音原則的相關資訊：

`Get-CsVoicePolicy`

CsVoicePolicy Cmdlet 傳回的資訊如下所示：

身分識別：全域

PstnUsages :{}

說明

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

您也可以建立傳回您語音原則子集的查詢。 例如，這個命令會傳回所有允許來電轉接的語音原則：

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

這個命令會傳回所有不允許來電轉接的語音原則：

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

在 Windows PowerShell 中，請使用 CsVoiceRouting Cmdlet 傳回有關語音路由的資訊：

`Get-CsVoiceRoute`

該命令會傳回所有語音路由等相關資訊：

身分識別： LocalRoute

優先順序：0

說明

NumberPattern： ^ （\\+ 1\[0-9\]{10}） $

PstnUsages :{}

PstnGatewayList :{}

名稱： LocalRoute

SuppressCallerId :

AlternateCallerId :

Lync Server 可讓您建立沒有 PSTN 使用狀況且沒有指定 PSTN 閘道的語音路由。 不過，您無法實際路由呼叫的語音路線沒有設定這兩個屬性值。 因此，您可能會發現定期執行此命令會很有用，這會傳回沒有 PSTN 用法之任何語音路由的身分識別：

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

同樣地，這個命令會傳回尚未設定為有 PSTN 閘道之任何語音路由的身分識別：

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a>檢查會議助理設定

查看 PSTN 電話撥入式會議的會議助理設定。 只能使用**CsDialInConferencingConfiguration** Cmdlet 來檢索會議助理設定。 [Lync Server 控制台] 無法使用這些設定。 若要查看您的會議助理設定，請使用類似下列的 Windows PowerShell 命令，這會傳回會議助理設定的全域集合：

`Get-CsDialInConferencingConfiguration -Identity "Global"`

請注意，會議助理設定也可以在網站範圍中設定。 若要傳回所有會議助理設定的相關資訊，請改為使用此命令：

`Get-CsDialInConferencingConfiguration`

CsDialInConferencingConfiguration Cmdlet 會傳回類似以下所示的資料：

身分識別：全域

EntryExitAnnouncementsType : UseNames

EnableNameRecording： True

EntryExitAnnouncementsEnabledByDefault： False

如果 EntryExitAnnouncementsEnabledByDefault 設定為 False，即表示會議宣告已停用。 若要啟用進入及結束宣告，請執行如下所示的 Windows PowerShell 命令：

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a>請參閱


[CsSipDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[CsAccessEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[CsVoiceRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

