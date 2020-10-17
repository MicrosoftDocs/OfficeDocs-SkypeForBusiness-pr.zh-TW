---
title: Lync Server 2013：架構屬性和描述
description: Lync Server 2013：架構屬性和描述。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18888d20a772b3e84970e7d874bd6b6964affc75
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557189"
---
# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a>Lync Server 2013 中的架構屬性和描述

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

本節說明 Lync Server 2013 所使用的所有架構屬性。 如需與屬性相關聯的類別，請參閱 [在 Lync Server 2013 中依類別的架構屬性](lync-server-2013-schema-attributes-by-class.md)。 如需 Lync Server 2013 中新的類別和屬性清單，請參閱 [Lync server 2013 中的架構變更](lync-server-2013-schema-changes-in-lync-server-2013.md)。

連結成對的屬性會指定為正向連結或反向連結。 參照至另一個物件的屬性是轉寄連結;參照至第一個物件的另一個物件的屬性是 back 連結。 轉寄連結是可更新的，而 back 連結是唯讀的。

有些屬性具有位元遮罩值。 針對這些屬性，每個設定都是以位表示，顯示的十進位值代表位位置。 位位置以位0開始。 例如，1 (二進位) 為 bit 0 設定，而 10000 (二進位) 是位4集。 每個位代表一個屬性。 以下是一些範例：

  - 10000 (二進位) 具有十進位值 16 (，也就是設定) 的位4。

  - 100000000 (二進位) 的十進位值為 256 (也就是設定) 的位8。

  - 1100 (二進位) 的十進位值為 12 (，也就是設定位2和 3;) 啟用兩個位代表的屬性。

  - 1111000001 (二進位) 具有十進位值 961 (也就是設定位0、6、7、8和9。這兩個位的屬性都已) 啟用。

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a>Lync Server 2013 的架構屬性

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>屬性</th>
<th>描述</th>
<th>註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dnsHostName</p></td>
<td><p>現在與 <strong>MsRTCSIP 集</strong> 區及 <strong>msRTCSIP MonitoringServer</strong> 類別相關聯之 Active Directory 網域服務中的現有屬性。 此屬性會指定集區或監控伺服器的完整功能變數名稱 (FQDN) 。</p>
<p>每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</p></td>
<td><p>Microsoft Office Live 通訊伺服器2005中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msDS-SourceObjectDN</p></td>
<td><p>此屬性包含另一個樹系中物件的辨識名稱 (DN) 的字串標記法，該物件會對應至此物件。 此屬性用於通訊群組擴充和自動出勤。 此屬性是在 Windows Server 2003 R2 的預設 Active Directory 架構中定義的。</p>
<p>為了避免需要將 AD DS 升級為 Windows Server 2003 R2，Active Directory 架構準備會以此屬性定義延伸 Windows Server 2003 架構。</p></td>
<td><p>Microsoft Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="odd">
<td><p>msExchUCVoiceMailSettings</p></td>
<td><p>此多重值屬性包含語音信箱設定。 此屬性與 Exchange 整合通訊 (UM) 共用。</p></td>
<td><p>Microsoft Lync Server 2010 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>此多重值屬性包含適用于使用者之保留原則的識別碼。 保留原則會在保留期間保留使用者的信箱專案。 此屬性與 Exchange 2013 共用。</p></td>
<td><p>Lync Server 2013 的新增功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP AcpInfo</p></td>
<td><p>此屬性會儲存使用者的音訊會議提供者資訊。</p></td>
<td><p>Lync Server 2010 的新增功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP ApplicationDestination</p></td>
<td><p>此屬性指向應用程式連絡人的信任服務專案。</p></td>
<td><p>Microsoft Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP ApplicationList</p></td>
<td><p>此屬性包含應用程式伺服器上的主控應用程式清單。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP ApplicationOptions</p></td>
<td><p>此屬性會指定應用程式連絡人的選項。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP ApplicationPrimaryLanguage</p></td>
<td><p>此屬性包含應用程式連絡人的主要語言。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP ApplicationSecondaryLanguages</p></td>
<td><p>此多重值屬性包含應用程式連絡人的次要語言。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP ApplicationServerBL</p></td>
<td><p>此屬性包含隸屬于此集區的應用程式伺服器清單。 此反向連結屬性的對應正向連結是 <strong>msRTCSIP-ApplicationServerPoolLink</strong>。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP ApplicationServerPoolLink</p></td>
<td><p>此屬性指向此應用程式伺服器所屬的集區。 這是轉寄連結。 對應的 [反向] 連結是 <strong>msRTCSIP-ApplicationServerBL</strong>。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveDefault (過時) </p></td>
<td><p>-</p></td>
<td><p>在即時通訊伺服器2005中新增。</p>
<p>在 Office 通訊伺服器2007中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveDefaultFlags (過時) </p></td>
<td><p>此屬性指定樹系界限內的全域預設值，以封存所有使用者通訊。 這是由封存代理程式層強制執行。 此屬性的值範圍如下：</p>
<ul>
<li><p><strong>TRUE</strong>：封存所有使用者</p></li>
<li><p><strong>FALSE</strong>：不封存所有使用者</p></li>
</ul>
<p>此屬性會在樹系界限內，全域控制如何封存內部網路中的使用者通訊。</p>
<p><strong>即時通訊伺服器2005行為 (現已撤銷) </strong></p>
<p>此屬性的值範圍如下：</p>
<ul>
<li><p>0：封存郵件本文 [位 0]</p></li>
<li><p>1：不要封存郵件本文 [位 0]</p></li>
</ul>
<p><strong>Office 通訊伺服器2007行為</strong></p>
<p>此屬性的值範圍如下：</p>
<ul>
<li><p>0： ArchiveFederationDefaultWithoutBody (撤銷) </p></li>
<li><p>1-2： ArchiveInternalCommunications</p></li>
<li><p>3-4： ArchiveFederatedCommunications</p></li>
<li><p>5： RecordPresenceRegistrations</p></li>
<li><p>6： RecordIMCallDetails</p></li>
<li><p>7： RecordGroupIMCallDetails</p></li>
<li><p>8： RecordFileTransferInstances</p></li>
<li><p>9： RecordAudioCallDetails</p></li>
<li><p>10： RecordVideoCallDetails</p></li>
<li><p>11： RecordRemoteAssistanceCallDetails</p></li>
<li><p>12： RecordApplicationSharingDetails</p></li>
<li><p>13： RecordMeetingInstantiations</p></li>
<li><p>14： RecordMeetingJoins</p></li>
<li><p>15： RecordDataJoins</p></li>
<li><p>16： RecordAVJoins</p></li>
</ul></td>
<td><p>在即時通訊伺服器2005中新增。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveFederationDefault (過時) </p></td>
<td><p>-</p></td>
<td><p>在即時通訊伺服器2005中新增。</p>
<p>在 Office 通訊伺服器2007中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveFederationDefaultFlags (過時) </p></td>
<td><p>-</p></td>
<td><p>在即時通訊伺服器2005中新增。</p>
<p>在 Office 通訊伺服器2007中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP ArchivingEnabled</p></td>
<td><p>此屬性是一種整數，用來控制是否要封存單一使用者的通訊的位欄位。 此控制項是由封存代理程式層強制執行。 它會標示為進行通用類別目錄複寫。</p>
<p>此屬性的範圍是單一使用者或連絡人特有的。 在 Lync Server 中)  (和關聯位位置的有效值如下：</p>
<ul>
<li><p>0：不封存 (未設定任何位) </p></li>
<li><p>1：已撤銷 (位位置 0) </p></li>
<li><p>2：已撤銷 (位位置 1) </p></li>
<li><p>4：封存內部通訊 (位位置 2) </p></li>
<li><p>8：封存同盟通訊 (位位置 3) </p></li>
</ul>
<p>Live 迅 Server 2005 中先前有效的值如下：</p>
<ul>
<li><p>0：使用依下列優先順序 <strong>msRTCSIP-ArchiveDefault</strong> 和 <strong>msRTCSIP-ArchiveFederation</strong> 所定義的預設值：</p>
<ul>
<li><p>1：封存</p></li>
<li><p>2：不要封存</p></li>
<li><p>3：不含郵件內文的封存</p></li>
</ul></li>
</ul></td>
<td><p>在即時通訊伺服器2005中新增。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchivingServerData (過時) </p></td>
<td><p>此屬性保留供日後使用。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServerVersion (過時) </p></td>
<td><p>此屬性會定義封存服務的版本。 此屬性是隨每個官方產品發行增加的 monotonously 增加整數類型。 可能的有效值為：</p>
<ul>
<li><p>未定義： Live 通訊伺服器2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 with SP1</p></li>
<li><p>3： Office 通訊伺服器2007</p></li>
<li><p>4： Office 通訊伺服器 2007 R2</p></li>
</ul></td>
<td><p>Office 通訊伺服器2007的新增功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP BackEndServer</p></td>
<td><p>此屬性指定集區後端伺服器的 FQDN。 因為每個集區只能有一個後端伺服器，所以這是單一值屬性。</p>
<p>每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</p></td>
<td><p>在即時通訊伺服器2005中新增。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP ConferenceDirectoryHomePool</p></td>
<td><p>此屬性包含主控會議目錄之集區的識別碼。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP ConferenceDirectoryId</p></td>
<td><p>此屬性包含會議目錄的識別碼。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP ConferenceDirectoryTargetPool</p></td>
<td><p>此屬性包含會議目錄移動所在集區的識別碼。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-預設值</p></td>
<td><p>這個 Boolean 屬性定義電話使用方式是否為預設使用量。 如果此屬性設定為 <strong>TRUE</strong>，則系統會使用電話的預設值，且無法由系統管理員刪除。 如果此屬性設為 <strong>FALSE</strong>，則可刪除使用方式。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP DefaultCWAExternalURL</p></td>
<td><p>此屬性會識別組織外部使用者的 Communicator Web Access URL。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP DefaultCWAInternalURL</p></td>
<td><p>此屬性會識別組織內部使用者的 Communicator Web Access URL。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultLocationProfileLink (過時) </p></td>
<td><p>這個單一值屬性包含指派給它的位置設定檔類別物件 (DN) 的辨識名稱。</p>
<p>轉寄連結： <strong>連結 ID 11036</strong></p>
<p>對應的反向連結 <strong>msRTCSIP-ServerReferenceBL</strong>。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultPolicy (過時) </p></td>
<td><p>這個布林值屬性指定原則是否為預設原則。 原則是設定為 <strong>TRUE</strong>時的預設原則。</p></td>
<td><p>Office 通訊伺服器2007的新增功能</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultRouteToEdgeProxy (過時) </p></td>
<td><p>此屬性指定執行 Access Edge service 之 Edge Server 的 FQDN （如果可以直接存取），或指定執行 Access Edge service 之伺服器集區的硬體負載平衡器的 FQDN。 如果執行 Access Edge service 的伺服器只能透過一或多個 Director 存取，則此屬性會指定 FQDN，並選擇性地指定 Director 或硬體負載平衡器服務 Director 集區的埠號碼。</p>
<p>每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</p></td>
<td><p>在即時通訊伺服器2005中新增。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultRouteToEdgeProxyPort (過時) </p></td>
<td><p>此屬性代表應該用來連線至執行 Access Edge service 之伺服器的埠號碼。</p>
<p>有效的值是指定要使用的埠的整數值。 預設值為5061。</p></td>
<td><p>在即時通訊伺服器2005中新增。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefPresenceSubscriptionTimeout (過時) </p></td>
<td><p>此屬性代表預設的目前狀態訂閱超時期間。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefRegistrationTimeout (過時) </p></td>
<td><p>此屬性代表預設的註冊超時視窗。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefRoamingDataSubscriptionTimeout (過時) </p></td>
<td><p>此屬性代表預設的漫遊資料訂閱超時視窗。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP DeploymentLocator</p></td>
<td><p>此屬性會用於分割的網域拓撲，並包含完整功能變數名稱 (FQDN) 。</p></td>
<td><p>Lync Server 2010 的新增功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Description (過時) </p></td>
<td><p>這個單一值的 UNICODE 字串屬性包含此電話路由或正常化規則的易記描述。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP DomainData</p></td>
<td><p>此屬性保留供日後使用。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DomainName</p></td>
<td><p>此屬性代表針對註冊機構所設定的網域。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP EdgeProxyData</p></td>
<td><p>此屬性保留供日後使用。</p></td>
<td><p>在即時通訊伺服器2005中新增。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP EdgeProxyFQDN</p></td>
<td><p>此屬性指定執行 Access Edge service 之伺服器的 FQDN。</p>
<p>每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</p></td>
<td><p>在即時通訊伺服器2005中新增。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnableBestEffortNotify (過時) </p></td>
<td><p>此屬性會控制伺服器是否會產生最佳的努力，以回應用戶端的訂閱要求 (BENOTIFY) 要求，而不是通知要求。 BENOTIFY 是對訂閱通知握手的效能擴充擴充，伺服器會產生 BENOTIFY 要求，而不是一般通知要求。 效能好處是 BENOTIFY 要求不需要用戶端的 200 OK 回應，因為 NOTIFY 要求會執行。</p>
<p>有效值為 <strong>TRUE</strong> 或 <strong>FALSE</strong>。</p>
<div>

> [!NOTE]  
> 即時通訊伺服器2003不支援 BENOTIFY 要求。 若要與使用 live 迅 Server 2005 和協力廠商伺服器上執行的即時通訊伺服器2003伺服器 API 撰寫的伺服器應用程式互動，可將其值設為 <STRONG>FALSE</STRONG>，以停用 BENOTIFY 要求。 BENOTIFY 目前不屬於 IETF (網際網路工程工作小組) SIP 標準化處理常式。


</div></td>
<td><p>在即時通訊伺服器2005中新增。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnableFederation (過時) </p></td>
<td><p>此屬性是一種全域參數，由 IT 系統管理員用來設定是否允許使用者與其他組織的使用者進行通訊。 它可讓系統管理員覆寫個別使用者的 <strong>FederationEnabled</strong> 屬性。 此屬性可用來協助保護內部網路免受來自公司的蠕蟲、病毒或目標攻擊可能造成的網際網路攻擊。</p>
<p>有效值 (和相關聯的位位置) 如下：</p>
<ul>
<li><p>1：啟用公用 IM 連線 (位位置 0) </p></li>
<li><p>2：保留 (位位置 1) </p></li>
<li><p>4：保留 (位位置 2) </p></li>
<li><p>8：保留 (位位置 3) </p></li>
<li><p>16：已啟用遠端呼叫控制 [電話語音] (位位置 4) </p></li>
<li><p>64： AllowOrganizeMeetingWithAnonymousParticipants (允許使用者邀請匿名使用者加入會議 (位位置 6) </p></li>
<li><p>128： UCEnabled (為使用者啟用整合通訊)  (位位置 7) </p></li>
<li><p>256： EnabledForEnhancedPresence (啟用使用者的公用 IM 連線)  (位位置 8) </p></li>
<li><p>512： RemoteCallControlDualMode (位位置 9) </p></li>
</ul></td>
<td><p>在即時通訊伺服器2005中新增。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP EnterpriseServices</p></td>
<td><p>此屬性會指出是否在指定的伺服器上載入企業服務。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP ExtensionData</p></td>
<td><p>此屬性保留供日後使用。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP ExternalAccessCode</p></td>
<td><p>此屬性包含外部存取的撥號代碼。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP FederationEnabled</p></td>
<td><p>此屬性控制是否為單一使用者啟用同盟。 它會由企業服務層強制執行。 它會標示為進行通用類別目錄複寫。</p>
<p>有效值為 <strong>TRUE</strong> 或 <strong>FALSE</strong>。</p></td>
<td><p>在即時通訊伺服器2005中新增。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-FrontEndServers</p></td>
<td><p>此屬性是與集區相關聯之所有 Enterprise Edition 伺服器的功能變數名稱的多重值清單。</p>
<p>反向連結： <strong>連結 ID 11023</strong></p>
<p>此反向連結的對應正向連結是 <strong>msRTCSIP-PoolAddress</strong>。</p></td>
<td><p>在即時通訊伺服器2005中新增。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Gateways (過時) </p></td>
<td><p>這個多重值字串屬性包含每個閘道)  (的閘道和埠清單。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalSettingsData (過時) </p></td>
<td><p>此屬性會儲存 [名稱：值] 配對。 已定義的 name： value 對適用于 <strong>允許輪詢顯示狀態</strong> 設定。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GroupingID</p></td>
<td><p>此屬性是群組的唯一識別碼，可用來群組通訊錄專案。</p></td>
<td><p>Lync Server 2010 的新增功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeServer (過時) </p></td>
<td><p>-</p></td>
<td><p>Live 通訊伺服器2003中的新增功能 (未使用) 。</p>
<p>在即時通訊伺服器2005中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-HomeServerString (過時) </p></td>
<td><p>-</p></td>
<td><p>在即時通訊伺服器2003中新增。</p>
<p>在即時通訊伺服器2005中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeUsers (過時) </p></td>
<td><p>-</p></td>
<td><p>Live 通訊伺服器2003中的新增功能 (未使用) 。</p>
<p>在即時通訊伺服器2005中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP InternetAccessEnabled</p></td>
<td><p>此屬性控制是否單一使用者啟用外部使用者存取。 它會由企業服務層強制執行。 它會標示為進行通用類別目錄複寫。</p>
<p>有效值為 <strong>TRUE</strong> 或 <strong>FALSE</strong>。</p></td>
<td><p>在即時通訊伺服器2005中新增。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-IsMaster (過時) </p></td>
<td><p>-</p></td>
<td><p>即時通訊伺服器2003中的新功能</p>
<p>在即時通訊伺服器2005中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP 線</p></td>
<td><p>這個單一值屬性包含裝置識別碼 (使用者控制之電話的 SIP URI 或電話 URI，以供 Lync 用於電話語音) 使用。 此屬性標示為進行通用類別目錄複寫，而且已編制索引。 如果使用者已啟用 Enterprise Voice，則此屬性會儲存為 e.164 的使用者電話號碼版本（164）。</p></td>
<td><p>Microsoft Office Live 通訊伺服器2005與 SP1 的新增功能</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP LineServer</p></td>
<td><p>這個單一值屬性包含 CSTA-SIP 閘道伺服器的 SIP URI。 此屬性標示為通用類別目錄複寫，但沒有編制索引。</p></td>
<td><p>Microsoft Office Live 通訊伺服器2005與 SP1 的新增功能</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationData (過時) </p></td>
<td><p>此屬性保留供日後使用。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalizationLinks (過時) </p></td>
<td><p>此多重值屬性包含本機正規化辨別名稱的清單，這些名稱是 (DN) 與此位置設定檔相關聯。 此屬性的類型是 DN 二進位。 位置設定檔和本機正規化規則之間有一對多的關聯性。 本機正規化 DNs 清單的順序必須依管理員所指定的順序來維護。 順序保留是由 DN 二進位的二進位部分所維護，它會指定順序索引。</p>
<p>轉寄連結： <strong>連結 ID 11034</strong></p>
<p>此 forward link 屬性的對應反向連結是 <strong>msRTCSIP-LocationProfileBL</strong>。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP LocalNormalizationOptions</p></td>
<td><p>此屬性包含正常化規則的選項清單。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationName (過時) </p></td>
<td><p>這個單一值屬性包含位置設定檔的易記名稱，表示此設定檔所代表的位置。 因為可以有多個位置設定檔，所以系統管理員需要一種方式來區分不同的設定檔。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-locationProfileBL (過時) </p></td>
<td><p>此多重值屬性包含位置設定檔辨別名稱的清單。 此屬性指定指向一或多個位置設定檔的後退連結。</p>
<p>反向連結： <strong>連結 ID 11035</strong></p>
<p>此屬性會對應至 [轉寄] 連結 <strong>msRTCSIP-LocalNormalizationLinks</strong>。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfileData (過時) </p></td>
<td><p>此屬性保留供日後使用。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP LocationProfileOptions</p></td>
<td><p>此屬性包含位置設定檔的選項。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP MappingContact</p></td>
<td><p>此多重值屬性包含應用程式連絡人的清單。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP MappingLocation</p></td>
<td><p>此多重值屬性包含位置設定檔的清單。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxNumOutstandingSearchPerServer (過時) </p></td>
<td><p>此屬性代表每個伺服器上的未完成搜尋要求數目上限。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxNumSubscriptionsPerUser (過時) </p></td>
<td><p>此屬性代表每位使用者的訂閱數目上限。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxPresenceSubscriptionTimeout (過時) </p></td>
<td><p>此屬性代表 [訂閱超時] 視窗的最大值。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxRegistrationsTimeout (過時) </p></td>
<td><p>此屬性代表 [註冊超時] 視窗的最大值。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxRoamingDataSubscriptionTimeout (過時) </p></td>
<td><p>此屬性代表最大的漫遊資料訂閱超時視窗。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP MCUData</p></td>
<td><p>此屬性保留供日後使用。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryAddress</p></td>
<td><p>此屬性是電腦類別下的服務控制點屬性，可指定回其所屬的 multipoint 控制項單位 (MCU) 的連結。 這種服務控制點和屬性是針對每家 Microsoft MCU 而建立的。 每個 Microsoft MCU 都必須尋找所屬集區的後端伺服器，以便從該伺服器中取得集區層級設定。</p>
<p>此屬性的值是 MCU 工廠 (DN) 的辨別名稱。 這是單一值屬性，並標示為進行通用類別目錄複寫。</p>
<p>轉寄連結： <strong>連結 ID 11026</strong></p>
<p>此 forward link 屬性的對應反向連結是 <strong>msRTCSIP-MCUServers</strong>。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP MCUFactoryData</p></td>
<td><p>這是多字串保留屬性。 儲存在此屬性中的設定會以名稱 = 值一組來表示。 目前定義的 name = 值組為：</p>
<ul>
<li><p>FactoryURL = &lt; URL&gt;</p></li>
</ul></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryPath</p></td>
<td><p>這是單一值屬性，包含與集區相關聯之單一 MCU 工廠 (DN) 的辨識名稱。</p>
<p>轉寄連結： <strong>連結 ID 11024</strong></p>
<p>此 forward link 屬性的對應反向連結是 <strong>msRTCSIP-PoolAddresses</strong>。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP MCUFactoryProviderID</p></td>
<td><p>此屬性是單一值字串，用來指定 MCU 工廠提供者的 GUID。 根據 GUID 值，MCU 出廠過程會決定是否要為此 MCU 類型服務。 如果 GUID 值為 <strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>，則預設會在 Lync Server 中使用 MCU factory 程式 () 將會處理該流程。 對於任何其他 GUID 值，MCU 工廠處理常式將不會為 MCU 類型提供服務。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUServers</p></td>
<td><p>此屬性是多值的辨識名稱清單 (DN) 。 此屬性包含與這個 MCU 工廠相關聯之相同類型及廠商的所有 MCU 伺服器清單。 每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</p>
<p>反向連結：連結 ID 11027</p>
<p>此反向連結的對應正向連結是 <strong>msRTCSIP-MCUFactoryAddress</strong>。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP MCUType</p></td>
<td><p>此屬性是單一值字串，用來指定 MCU 可以處理的媒體。</p>
<p>支援的有效類型包括：</p>
<ul>
<li><p>會議</p></li>
<li><p>音訊-影片</p></li>
<li><p>聊天</p></li>
<li><p>電話會議</p></li>
</ul></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP MCUVendor</p></td>
<td><p>此屬性是單一值字串，用來指定 MCU 廠商的名稱。 所有 Microsoft MCUs 都會將此屬性指定為 <strong>Microsoft Corporation</strong>。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MeetingFlags (過時) </p></td>
<td><p>此屬性會定義針對所有使用者或連絡人物件全域啟用的不同會議選項。 此屬性是整數類型的位元遮罩值。</p>
<p>有效值 (和相關聯的位位置) 如下：</p>
<ul>
<li><p>0： AllowOrganizeMeetingWithAnonymousParticipants 為 None (不允許使用者邀請匿名使用者加入會議)  (未設定 bits) </p></li>
<li><p>4： AllowOrganizeMeetingWithAnonymousParticipants 每個人 (允許所有使用者邀請匿名使用者加入會議)  (位位置 2) </p></li>
<li><p>8： AllowOrganizeMeetingWithAnonymousParticipants UsePerUserSetting (允許使用者以每位使用者的使用者邀請匿名使用者為會議設定)  (位位置 3) </p></li>
<li><p>16： UserPerUserMeetingPolicy (的會議原則是針對每位使用者定義)  (位位置 4) </p></li>
</ul></td>
<td><p>Office 通訊伺服器2007的新增功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MeetingPolicy (過時) </p></td>
<td><p>此屬性指定系統管理員為此使用者指派成單一值屬性的原則 (DN) 辨別名稱。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinPresenceSubscriptionTimeout (過時) </p></td>
<td><p>此屬性代表最小顯示狀態訂閱超時視窗。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MinRegistrationTimeout (過時) </p></td>
<td><p>此屬性代表 [註冊超時] 視窗的最小值。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinRoamingDataSubscriptionTimeout (過時) </p></td>
<td><p>此屬性代表最小的漫遊資料訂閱超時視窗。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP MirrorBackEndServer</p></td>
<td><p>此屬性用來儲存前端集區所使用的鏡像 SQL Server 後端。</p></td>
<td><p>Lync Server 2013 的新增功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP MobilityFlags</p></td>
<td><p>此屬性包含定義行動性設定的選項和旗標。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP MobilityPolicy</p></td>
<td><p>此屬性包含行動性原則物件的 DN。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-NumDevicesPerUser (過時) </p></td>
<td><p>此屬性代表允許的裝置數目，使用者可以在這些裝置上登錄 SIP 通訊並訂閱顯示狀態。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP OptionFlags</p></td>
<td><p>此屬性會指定為 user 或 contact 物件啟用的選項。 此屬性是整數類型的位元遮罩值。 每個選項都是以位表示。 此屬性標示為進行通用類別目錄複寫。</p>
<p>有效值 (和相關聯的位位置) 如下：</p>
<ul>
<li><p>1：啟用公用立即訊息 (IM) connectivity (位位置 0) </p></li>
<li><p>2：保留 (位位置 1) </p></li>
<li><p>4：保留 (位位置 2) </p></li>
<li><p>8：保留 (位位置 3) </p></li>
<li><p>16：已啟用遠端呼叫控制 [電話語音] (位位置 4) </p></li>
<li><p>64： AllowOrganizeMeetingWithAnonymousParticipants (允許使用者邀請匿名使用者加入會議 (位位置 6) </p></li>
<li><p>128： UCEnabled (啟用使用者的 UC)  (位位置 7) </p></li>
<li><p>256： EnabledForEnhancedPresence (啟用使用者的公用 IM 連線)  (位位置 8) </p></li>
<li><p>512： RemoteCallControlDualMode (位位置 9) </p></li>
</ul></td>
<td><p>使用 SP1 即時通訊伺服器2005中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-OriginatorSID</p></td>
<td><p>在資源與中央樹系拓撲中，會使用此屬性來啟用單一登入時，當使用者從 Windows NT 伺服器主體帳戶 ObjectSID 至此屬性時，會將此屬性複製到資源或中央樹系中對應的使用者或連絡人物件的此屬性。 Communicator Web Access 使用此屬性或使用者的 ObjectSID 在 AD DS 中搜尋使用者。 此屬性標示為進行通用類別目錄複寫。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP OwnerUrn</p></td>
<td><p>此屬性是應用程式連絡人擁有者的統一資源名稱 (URN) 。</p></td>
<td><p>Lync Server 2010 的新增功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Pattern (過時) </p></td>
<td><p>這個單一值字串屬性包含的模式，用來比對 e.164 格式的撥號號碼。 如果撥號號碼符合此模式，就會將轉譯套用至撥號號碼。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteBL (過時) </p></td>
<td><p>此多重值屬性包含電話路由辨別名稱 (DN) 清單。 此屬性指定指向一或多個電話路由的反向連結。</p>
<p>反向連結： <strong>連結 ID 11033</strong></p>
<p>此屬性會對應至 [轉寄] 連結 <strong>msRTCSIP-RouteUsageLinks</strong>。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRouteData (過時) </p></td>
<td><p>此屬性保留供日後使用。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteName (過時) </p></td>
<td><p>這個單一值的 UNICODE 字串屬性可指定電話路由的易記名稱，以便系統管理員輕易參考該名稱。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneUsageData (過時) </p></td>
<td><p>此屬性保留供日後使用。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyContent (過時) </p></td>
<td><p>此屬性是單一值的 Unicode 字串。 這個字串屬性包含 XML 格式的原則定義。 XML 架構定義在不同的原則類型中是通用的，每個原則類型的設定值都各不相同。</p>
<p>XML 架構定義 (XSD) 定義如下：</p>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;xs:schema id=&quot;instance&quot; xmlns=&quot;&quot; xmlns:xs=&quot;http://www.w3.org/2001/XMLSchema&quot; xmlns:msdata=&quot;urn:schemas-microsoft-com:xml-msdata&quot;&gt;
  &lt;xs:element name=&quot;instance&quot; msdata:IsDataSet=&quot;true&quot;&gt;
    &lt;xs:complexType&gt;
      &lt;xs:choice maxOccurs=&quot;unbounded&quot;&gt;
        &lt;xs:element name=&quot;property&quot; nillable=&quot;true&quot;&gt;
          &lt;xs:complexType&gt;
            &lt;xs:simpleContent msdata:ColumnName=&quot;property_Text&quot; msdata:Ordinal=&quot;1&quot;&gt;
              &lt;xs:extension base=&quot;xs:string&quot;&gt;
                &lt;xs:attribute name=&quot;name&quot; type=&quot;xs:string&quot; /&gt;
              &lt;/xs:extension&gt;
            &lt;/xs:simpleContent&gt;
          &lt;/xs:complexType&gt;
        &lt;/xs:element&gt;
      &lt;/xs:choice&gt;
    &lt;/xs:complexType&gt;
  &lt;/xs:element&gt;
&lt;/xs:schema&gt;</code></pre></td>
<td><p>Office 通訊伺服器2007的新增功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PolicyData (過時) </p></td>
<td><p>此屬性保留供日後使用。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyType (過時) </p></td>
<td><p>這個單一值的 Unicode 字串屬性包含原則類型。 有效的原則類型如下：</p>
<ul>
<li><p>會議</p></li>
<li><p>電話</p></li>
</ul></td>
<td><p>Office 通訊伺服器2007的新增功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolAddress</p></td>
<td><p>此屬性指定的連結會傳回電腦所屬的集區。 不論電腦正在執行 Standard Edition 還是 Lync Server Enterprise Edition，都設定此屬性。 此屬性標示為進行通用類別目錄複寫。</p>
<p>有效的值是集區的功能變數名稱。</p>
<p>轉寄連結： <strong>連結 ID 11022</strong></p>
<p>此 forward link 屬性的對應反向連結是 <strong>msRTCSIP-FrontEndServers</strong>。</p></td>
<td><p>在即時通訊伺服器2005中新增。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolAddresses</p></td>
<td><p>此多重值屬性包含與 MCU 工廠關聯之集區 (DN) 的辨識名稱清單。</p>
<p>反向連結： <strong>連結 ID 11025</strong></p>
<p>此反向連結的對應正向連結是 <strong>msRTCSIP-MCUFactoryPath</strong>。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP PoolData</p></td>
<td><p>此屬性保留供日後使用。</p></td>
<td><p>使用 SP1 即時通訊伺服器2005中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP PoolDisplayName</p></td>
<td><p>此屬性會指定管理主控台所顯示集區的任意名稱。 系統管理員可以變更此名稱。</p>
<p>有效的值是代表集區名稱的字串。</p></td>
<td><p>在即時通訊伺服器2005中新增。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP PoolDomainFQDN</p></td>
<td><p>此屬性是單一值字串值。 當此屬性的值為時，如果系統管理員想要建立前端集區的 FQDN 不符合建立前端集區的 Active Directory 網域結構，則此屬性的值會代表集區的網域 FQDN (例如，SIP 命名空間會從網域名稱系統中脫離 (DNS) 命名空間) 。</p>
<p>建議您將前端集區域 FQDN 對應到功能變數名稱部分，以作為集區所在的 Active Directory 網域。 因此，當此屬性沒有任何值時，前端集區 FQDN 會預設為 Active Directory 功能變數名稱結構（由 <strong>dnsHostName</strong> 屬性工作表示）。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP PoolFunctionality</p></td>
<td><p>所有與集區相關聯之 Lync Server、Enterprise Edition Server 的功能變數名稱的多重值清單。 Type integer 的此屬性可定義集區是否可以立即訊息 (IM) 和目前狀態，以及會議。</p>
<p>可能的有效值類型如下：</p>
<ul>
<li><p>未定義： IM 和目前狀態服務 (即時通訊伺服器2005和 2003) </p></li>
<li><p>1： IM 和目前狀態服務 (Lync Server) </p></li>
<li><p>2： IM 及目前狀態和會議服務 (Lync Server) </p></li>
</ul></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP PoolType</p></td>
<td><p>此屬性會指定伺服器集區是否正在執行 Standard Edition server 或 Enterprise Edition server。 此屬性是整數類型的位元遮罩值。 每個選項都是以位表示。</p>
<p>有效值 (和相關聯的位位置) 如下：</p>
<ul>
<li><p>1： Standard Edition server，主控使用者 (位位置 0) </p></li>
<li><p>2： Enterprise Edition 伺服器，主控使用者 (位位置 1) </p></li>
<li><p>4： Standard Edition server，主控應用程式 (位位置 2) </p></li>
<li><p>8： Enterprise Edition 伺服器，主控應用程式 (位位置 3) </p></li>
</ul>
<p>因為 Lync Server 不支援僅裝載應用程式的集區，所以唯一有效的值如下：</p>
<ul>
<li><p>5： Standard Edition server，主控使用者和應用程式 (位位置0和 2) </p></li>
<li><p>10： Enterprise Edition 伺服器，主控使用者和應用程式 (位位置1和 3) </p></li>
</ul></td>
<td><p>在即時通訊伺服器2005中新增。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP PoolVersion</p></td>
<td><p>此屬性會定義集區的版本。 它是一種每一主要產品版本遞增的整數類型。</p>
<p>可能的有效值類型如下：</p>
<ul>
<li><p>0： Live 通訊伺服器2003</p></li>
<li><p>1： Live 通訊伺服器2005</p></li>
<li><p>2： Live 通訊伺服器2005與 SP1</p></li>
<li><p>3： Office 通訊伺服器2007</p></li>
<li><p>4： Office 通訊伺服器 2007 R2</p></li>
<li><p>5： Lync Server 2010</p></li>
</ul></td>
<td><p>即時通訊伺服器2005與 SP1。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP PresenceFlags</p></td>
<td><p>此屬性包含定義顯示狀態設定的選項和旗標。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP Microsoft.rtc.management.writableconfig.policy.presence.presencepolicy</p></td>
<td><p>此屬性包含目前狀態原則物件的 DN。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrimaryHomeServer</p></td>
<td><p>此屬性可讓使用者或連絡人進行 SIP 訊息。 因為在中央樹系拓撲中，連絡人物件（而非使用者物件）已啟用 SIP，所以它會新增至連絡人類別。</p>
<p>有效值是使用者所在之 Standard Edition server 或 Enterprise Edition 前端集區的 DN。</p></td>
<td><p>在即時通訊伺服器2005中新增。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>此屬性包含指定使用者的 SIP 位址。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrivateLine</p></td>
<td><p>此屬性包含專用線路裝置的設備識別碼。</p></td>
<td><p>Lync Server 2010 的新增功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP 路由</p></td>
<td><p>此屬性是 Boolean 屬性，用來判斷是否已授權 Lync Server 使用其 GRUU 位址路由傳送至此服務。 如果此值設為 <strong>TRUE</strong>，則會授權 Lync Server 路由傳送至此服務。 如果此值設為 <strong>FALSE</strong>，Lync Server 就不會獲得路由傳送到此服務的授權。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsageAttribute (過時) </p></td>
<td><p>這個單一值的 UNICODE 字串屬性定義的屬性會限定電話路由的使用方式。 電話路由的選取取決於兩個元素：指派給電話路由的使用方式屬性，以及來電者的允許原則使用屬性。 已選取具有與來電者允許之使用狀況屬性相符的第一個電話路由。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsageLinks (過時) </p></td>
<td><p>此多重值辨別名稱 (DN) 屬性包含路由流量辨別名稱的清單。</p>
<p>轉寄連結： <strong>連結 ID 11032</strong></p>
<p>此屬性是對應的反向連結 <strong>msRTCSIP-PhoneRouteBL</strong>的向前連結。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP RoutingPoolDN</p></td>
<td><p>此屬性包含 DN，該 DN 指向所有 SIP 流量定址至此 MCU 或受信任的服務必須經過的集區。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RuleName (過時) </p></td>
<td><p>這個單一值的 UNICODE 字串屬性會指定正規化規則的易記名稱，因此系統管理員可以輕易參考該名稱。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SchemaVersion</p></td>
<td><p>此屬性代表組織中目前部署的架構版本。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SearchMaxRequests (過時) </p></td>
<td><p>當使用者使用 Communicator 搜尋連絡人時，此屬性會限制目錄搜尋傳回的搜尋結果數目。 此屬性會覆寫用戶端提供的值。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SearchMaxResults (過時) </p></td>
<td><p>此屬性會限制傳回的搜尋要求數目。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerBL</p></td>
<td><p>此多重值屬性是一個 back 連結，其中包含可辨識名稱清單 (DN) 。 這些 DNs 指向集區或 <strong>TrustedService</strong> 物件。</p>
<p>此屬性會對應至 [轉寄] 連結 <strong>msRTCSIP-TrustedServiceLinks</strong>。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP ServerData</p></td>
<td><p>此屬性保留供日後使用。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerReferenceBL (過時) </p></td>
<td><p>此多重值屬性包含辨識名稱的清單。 這些辨別名稱是指參照其他可指派預設位置設定檔之伺服器物件的連結。</p>
<p>反向連結： <strong>連結 ID 11037</strong></p>
<p>此反向連結的對應正向連結是 <strong>msRTCSIP-DefaultLocationProfileLink</strong>。</p>
<p>此反向連結屬性只會參照集區和轉送伺服器。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP ServerVersion</p></td>
<td><p>此屬性會定義伺服器的版本資訊。 此版本編號適用于所有伺服器角色。 它是隨每個官方產品發行增加的 monotonously 增加整數。</p>
<p>可能的有效值如下：</p>
<ul>
<li><p>未定義： Live 通訊伺服器2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 with SP1</p></li>
<li><p>3： Office 通訊伺服器2007</p></li>
<li><p>4： Office 通訊伺服器 2007 R2</p></li>
<li><p>5： Lync Server 2010</p></li>
<li><p>6： Lync Server 2013</p></li>
</ul></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP SourceObjectType</p></td>
<td><p>整數類型的這個單一值屬性指定 <strong>msDS-SourceObjectDN</strong> 指向的物件類型，如下所示：</p>
<ul>
<li><p>null |0x00000001：代表來自不同樹系的 Windows NT 伺服器主體使用者物件</p></li>
<li><p>下列屬性代表通訊群組擴充的不同樹系中的群組類型：</p>
<ul>
<li><p>0x00000002： ADS_GROUP_TYPE_GLOBAL_GROUP</p></li>
<li><p>0x00000004： ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</p></li>
<li><p>0x00000004： ADS_GROUP_TYPE_LOCAL_GROUP</p></li>
<li><p>0x00000008： ADS_GROUP_TYPE_UNIVERSAL_GROUP</p></li>
<li><p>0x80000000： ADS_GROUP_TYPE_SECURITY_ENABLED</p></li>
<li><p>0x90000000：代表來自相同樹系或不同樹系的自動語音應答或訂戶存取物件</p></li>
</ul></li>
</ul></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SubscriptionAuthRequired (過時) </p></td>
<td><p>-</p></td>
<td><p>在即時通訊伺服器2003中新增。</p>
<p>在即時通訊伺服器2005中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP TargetHomeServer</p></td>
<td><p>此屬性可讓您將使用者或連絡人物件從一個 Lync 伺服器集區移至另一個。 此屬性會新增至連絡人類別，因為在中央樹系拓撲中，連絡人物件（而非使用者物件）已啟用 SIP。</p>
<p>有效值是要移動使用者之目的地 Standard Edition 伺服器或前端集區的 DN。</p></td>
<td><p>在即時通訊伺服器2005中新增。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TargetPhoneNumber (過時) </p></td>
<td><p>這個單一值字串屬性包含電話號碼模式或範圍，以路由傳送至 <strong>msRTCSIP-Gateways</strong>中定義的指定閘道。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP TargetUserPolicies</p></td>
<td><p>此屬性會儲存 Lync Server 使用者之目標原則的名稱-值對。</p></td>
<td><p>Lync Server 2010 的新增功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP TenantId</p></td>
<td><p>此屬性會儲存租使用者的唯一識別碼。</p></td>
<td><p>Lync Server 2010 的新增功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Translation (過時) </p></td>
<td><p>此屬性是 Lync Server 的語音功能使用的，且包含翻譯字串以套用至撥號號碼（如果找到相符的號碼）。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP TrustedMCUData</p></td>
<td><p>此屬性保留供日後使用。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP TrustedMCUFQDN</p></td>
<td><p>此屬性是包含 MCU FQDN 的字串值。 這是單一值屬性。 每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP TrustedProxyData</p></td>
<td><p>此屬性保留供日後使用。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP TrustedProxyFQDN</p></td>
<td><p>此屬性是包含執行 Proxy 伺服器之伺服器的 FQDN 的字串值。 此屬性是單一值屬性。 每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP TrustedServerData</p></td>
<td><p>此屬性保留供日後使用。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP TrustedServerFQDN</p></td>
<td><p>此屬性是單一值屬性，代表受信任伺服器的 FQDN。</p></td>
<td><p>在即時通訊伺服器2005中新增。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP TrustedServerVersion</p></td>
<td><p>此屬性會指定受信任的伺服器清單中伺服器的版本號碼。</p>
<p>可能的有效值如下：</p>
<ul>
<li><p>Null： Live 通訊伺服器2003</p></li>
<li><p>2： Live 通訊伺服器2005</p></li>
<li><p>3： Office 通訊伺服器2007</p></li>
<li><p>4： Office 通訊伺服器 2007 R2</p></li>
<li><p>5： Lync Server 2010</p></li>
<li><p>6： Lync Server 2013</p></li>
</ul></td>
<td><p>在即時通訊伺服器2005中新增。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP TrustedServiceFlags</p></td>
<td><p>此屬性會定義為受信任的服務啟用的選項。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceLinks</p></td>
<td><p>此多重值屬性包含辨識名稱清單 (DN) 參考信任的服務物件，例如媒體轉送驗證服務。 執行 A/V 會議服務之 Edge Server 上的媒體轉送驗證服務 (實際組合) 必須與集區相關聯，以支援遠端使用者的音訊案例。</p>
<p>此 forward link 屬性的對應反向連結是 <strong>msRTCSIP-ServerBL</strong>。</p></td>
<td><p>Uc</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP TrustedServicePort</p></td>
<td><p>此屬性是一個整數，用來定義用來連線到此 GRUU 服務的埠號碼。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP TrustedServiceType</p></td>
<td><p>此屬性是定義其所代表之 GRUU 服務類型的字串值。</p>
<p>有效的 GRUU 服務類型如下：</p>
<ul>
<li><p>MediationServer</p></li>
<li><p>閘道</p></li>
<li><p>媒體轉送驗證服務 (MRAS) </p></li>
<li><p>QoSM</p></li>
<li><p>msRTCSIP-UserExtension CWA</p></li>
</ul></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP TrustedWebComponentsServerData</p></td>
<td><p>此屬性保留供日後使用。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP TrustedWebComponentsServerFQDN</p></td>
<td><p>此屬性是包含執行 Lync Server Web 服務之 IIS 之 FQDN 的字串值。 這是單一值屬性。 每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UCFlags (過時) </p></td>
<td><p>此屬性定義不同的 UC 選項，可供全域對所有的使用者或連絡人物件啟用。 此屬性是整數類型的位元遮罩值。 每個選項都是以一位的狀態來表示。</p>
<p>可能有效的值 (和關聯的位位置) 如下：</p>
<ul>
<li><p>4： UsePerUserUCPolicy (位位置 2) </p></li>
</ul>
<p>設定此位時，即會定義每位使用者的 UC 原則。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UCPolicy (過時) </p></td>
<td><p>這個單一值屬性包含系統管理員為此使用者指派的 UC 原則 (DN) 辨別名稱。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserDomainList (過時) </p></td>
<td><p>此屬性提供樹系中所有主控 SIP-enabled 使用者的網域清單。 預設值為空白清單，表示樹系中的所有網域都已 SIP-enabled。</p>
<p>有效的值為多個字串，代表個別網域的功能變數名稱。</p></td>
<td><p>在即時通訊伺服器2005中新增。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserEnabled</p></td>
<td><p>此屬性會決定使用者目前是否已啟用 Lync Server。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP UserExtension</p></td>
<td><p>此多重值屬性以 name = value 的格式包含名稱-值對的清單 &quot; 。 &quot; 此屬性標示為進行通用類別目錄複寫。</p></td>
<td><p>使用 SP1 即時通訊伺服器2005中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP UserLocationProfile</p></td>
<td><p>此屬性包含指向位置設定檔物件 (DN) 的辨識名稱。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP UserPolicies</p></td>
<td><p>此屬性儲存使用者原則的名稱-值對。</p></td>
<td><p>Lync Server 2010 的新增功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP UserPolicy</p></td>
<td><p>這是多重值屬性，包含具有二進位 (DN_WITH_BINARY) 指向全域使用者原則的不同類型的辨識名稱清單。 二進位部分會指出 DN 部分指向的原則類型。</p>
<p>有效的二進位值如下：</p>
<ul>
<li><p>0x00000001：會議原則</p></li>
<li><p>0x00000002： UC 原則</p></li>
<li><p>0x00000005：顯示狀態原則</p></li>
</ul></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP UserRoutingGroupId</p></td>
<td><p>這是 SIP 路由群組識別碼。 相同群組中的使用者會註冊到同一個前端伺服器。</p></td>
<td><p>Lync Server 2013 的新增功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP WebComponentsData</p></td>
<td><p>這是多重值屬性。 此屬性保留供日後使用。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsPoolAddress</p></td>
<td><p>這個單一值屬性會指向網頁元件所屬的集區或 Standard Edition server。</p>
<p>轉寄連結： <strong>連結 ID 11028</strong></p>
<p>此 forward link 屬性的對應反向連結是 <strong>msRTCSIP-WebComponentsServers</strong>。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsServers</p></td>
<td><p>此屬性是多重值的辨識名稱清單。 此屬性包含與此集區相關聯之所有網頁伺服器的清單。</p>
<p>反向連結： <strong>連結 ID 11029</strong></p>
<p>此反向連結的對應正向連結是 <strong>msRTCSIP-WebComponentsPoolAddress</strong>。</p></td>
<td><p>Office 通訊伺服器2007的新增功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WMIInstanceId (過時) </p></td>
<td><p>-</p></td>
<td><p>在即時通訊伺服器2003中新增。</p>
<p>在即時通訊伺服器2005中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>OtherIPPhone</p></td>
<td><p>電話語音會使用這個現有的 Active Directory 屬性來指定電話的備用 TCP/IP 地址清單。</p></td>
<td><p>Windows Server 2008 作業系統中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>PhoneOfficeOther</p></td>
<td><p>Lync Server 中的語音元件會使用這個現有的 Active Directory 屬性，針對連絡人物件，以供路由呼叫至整合通訊自動語音應答和使用者存取號碼的目的。 無條件呼叫轉寄位址會儲存在此多重值屬性中。 此帳戶是針對自動語音應答和使用者存取的特定用途而建立。 管理員不應修改這個帳戶的屬性。</p></td>
<td><p>Windows 2000 作業系統中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>ProxyAddresses</p></td>
<td><p>這個現有的 Active Directory 多重值屬性是 Windows 2000 中所引進之基礎 Active Directory 架構的一部分。 此屬性包含使用者電子郵件的各種 X400、X500 及 SMTP 位址。 在即時通訊伺服器2003和更新版本中，會使用 [sip：] 標記將使用者的 SIP URI 新增至此清單 &quot; &quot; 。</p>
<p>下列應用程式會從此屬性搜尋使用者的 SIP URI：</p>
<ul>
<li><p>Microsoft Office Outlook 2003 訊息與共同作業用戶端</p></li>
<li><p>Microsoft Office SharePoint Server 2007</p></li>
</ul></td>
<td><p>Windows 2000 作業系統中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>TelephoneNumber</p></td>
<td><p>這個現有的 Active Directory 屬性包含使用者的電話號碼。</p></td>
<td><p>Windows 2000 作業系統中的新功能。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

