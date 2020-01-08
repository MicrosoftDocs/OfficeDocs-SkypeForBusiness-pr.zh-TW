---
title: Lync Server 2013：架構屬性和描述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc18b4b074302ba3c233670f21fd8479bbd0b0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a>Lync Server 2013 中的架構屬性和描述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

本節將說明 Lync Server 2013 使用的所有架構屬性。 針對與屬性相關聯的類別，請參閱[Lync Server 2013 中的 [依類別的架構屬性](lync-server-2013-schema-attributes-by-class.md)]。 如需 Lync Server 2013 中新類別和屬性的清單，請參閱[Lync server 2013 中的架構變更](lync-server-2013-schema-changes-in-lync-server-2013.md)。

連結對的屬性會指定為轉寄連結或返回連結。 參照另一個物件的屬性是轉寄連結;參照第一個物件的另一個物件屬性是 [上一頁] 連結。 [轉寄] 連結是可更新的，而 [返回] 連結則是唯讀的。

有些屬性有位元遮罩值。 針對這些屬性，每個設定都是由一個位來表示，而顯示的十進位值代表位位置。 位位置從位0開始。 例如，1（binary）為 bit 0，而10000（binary）為 bit 4。 每個位代表一個屬性。 以下是一些範例：

  - 10000（binary）的十進位值是16（也就是位4已設定）。

  - 100000000（binary）的十進位值是256（也就是已設定位8）。

  - 1100（binary）的十進位值是12（也就是設定的位2和 3; 兩位都已啟用）。

  - 1111000001（binary）的十進位值是961（也就是位0、6、7、8和9）; 每個這些位的屬性都已啟用。

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
<th>Attribute</th>
<th>描述</th>
<th>批註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dnsHostName</p></td>
<td><p>Active Directory 網域服務中現有的屬性，現在與<strong>msRTCSIP-Pool</strong>和<strong>msRTCSIP MonitoringServer</strong>類別相關聯。 這個屬性會指定池或監視伺服器的完整功能變數名稱（FQDN）。</p>
<p>每個區段的有效值為63字元;整個 FQDN 的有效值為255個字元。</p></td>
<td><p>Microsoft Office Live 通訊伺服器2005中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>SourceObjectDN</p></td>
<td><p>這個屬性包含與這個物件相對應之另一個目錄林中之物件辨識名稱（DN）的字串標記法。 這個屬性是用於通訊群組延伸及自動出席。 這個屬性是在 Windows Server 2003 R2 的預設 Active Directory 架構中定義。</p>
<p>若要避免需要將 AD DS 升級至 Windows Server 2003 R2，Active Directory 架構準備會將 Windows Server 2003 架構與此屬性定義延伸。</p></td>
<td><p>Microsoft Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msExchUCVoiceMailSettings</p></td>
<td><p>這個多重值屬性會儲存語音信箱設定。 這個屬性會與 Exchange 整合通訊（UM）共用。</p></td>
<td><p>Microsoft Lync Server 2010 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>這個多重值屬性包含適用于使用者的保留原則的識別碼。 保留原則在保留期間保留使用者的信箱專案。 這個屬性是與 Exchange 2013 共用的。</p></td>
<td><p>Lync Server 2013 的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-AcpInfo</p></td>
<td><p>這個屬性會儲存使用者的音訊會議提供者資訊。</p></td>
<td><p>Lync Server 2010 的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationDestination</p></td>
<td><p>這個屬性指向應用程式連絡人的信任服務專案。</p></td>
<td><p>Microsoft Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationList</p></td>
<td><p>這個屬性包含應用程式伺服器上已託管的應用程式清單。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationOptions</p></td>
<td><p>這個屬性指定應用程式連絡人的選項。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationPrimaryLanguage</p></td>
<td><p>這個屬性包含應用程式連絡人的主要語言。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationSecondaryLanguages</p></td>
<td><p>這個多重值屬性包含應用程式連絡人的次要語言。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerBL</p></td>
<td><p>這個屬性包含屬於這個 pool 的應用程式伺服器清單。 此 back link 屬性的相對應轉寄連結為<strong>msRTCSIP-ApplicationServerPoolLink</strong>。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerPoolLink</p></td>
<td><p>這個屬性會指向該應用程式伺服器所屬的池。 這是 [轉寄] 連結。 對應的 [向後] 連結為<strong>msRTCSIP-ApplicationServerBL</strong>。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveDefault （已過時）</p></td>
<td><p>-</p></td>
<td><p>即時通訊伺服器2005中的新功能。</p>
<p>在 Office 通訊伺服器2007中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveDefaultFlags （已過時）</p></td>
<td><p>這個屬性會指定林邊界內的全域預設值，以封存所有的使用者通訊。 這是由 [存檔代理程式] 層級強制執行。 此屬性的值範圍如下所示：</p>
<ul>
<li><p><strong>TRUE</strong>：封存所有使用者</p></li>
<li><p><strong>FALSE</strong>：不封存所有使用者</p></li>
</ul>
<p>這個屬性在林邊界內，全域控制如何將內部網路中的使用者通訊歸檔。</p>
<p><strong>即時通訊伺服器2005行為（現已停用）</strong></p>
<p>此屬性的值範圍如下所示：</p>
<ul>
<li><p>0：封存郵件正文 [bit 0]</p></li>
<li><p>1：不要封存郵件本文的內容 [bit 0]</p></li>
</ul>
<p><strong>Office 通訊伺服器2007行為</strong></p>
<p>此屬性的值範圍如下所示：</p>
<ul>
<li><p>0： ArchiveFederationDefaultWithoutBody （已停用）</p></li>
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
<td><p>即時通訊伺服器2005中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveFederationDefault （已過時）</p></td>
<td><p>-</p></td>
<td><p>即時通訊伺服器2005中的新功能。</p>
<p>在 Office 通訊伺服器2007中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveFederationDefaultFlags （已過時）</p></td>
<td><p>-</p></td>
<td><p>即時通訊伺服器2005中的新功能。</p>
<p>在 Office 通訊伺服器2007中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingEnabled</p></td>
<td><p>這個屬性是一個整數，用來做為位欄位，以控制是否要封存單一使用者的通訊。 此控制項是由 [存檔代理程式] 層級強制執行。 它標示為供全域編目複製。</p>
<p>這個屬性的範圍是針對單一使用者或連絡人。 Lync Server 中的有效值（以及相關聯的位位置）如下所示：</p>
<ul>
<li><p>0：不封存（沒有位組）</p></li>
<li><p>1：已停用（位位置0）</p></li>
<li><p>2：已停用（位位置1）</p></li>
<li><p>4：封存內部通訊（位位置2）</p></li>
<li><p>8：封存聯盟通訊（位位置3）</p></li>
</ul>
<p>在即時通訊伺服器2005中先前有效的值如下所示：</p>
<ul>
<li><p>0：使用<strong>msRTCSIP-ArchiveDefault</strong>和<strong>msRTCSIP-ArchiveFederation</strong>所定義的預設值，並以下列優先順序順序排列：</p>
<ul>
<li><p>1：封存</p></li>
<li><p>2：不要封存</p></li>
<li><p>3：不含郵件正文的封存</p></li>
</ul></li>
</ul></td>
<td><p>即時通訊伺服器2005中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchivingServerData （已過時）</p></td>
<td><p>這個屬性已保留供日後使用。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServerVersion （已過時）</p></td>
<td><p>這個屬性會定義 [存檔服務] 的版本。 這個屬性是一種 monotonously 增加的整數類型，每個正式產品發行都會增加。 可能的有效值為：</p>
<ul>
<li><p>未定義：即時通訊伺服器2003</p>
<p>                 [即時通訊伺服器] 2005</p>
<p>                 使用 SP1 進行即時通訊伺服器2005</p></li>
<li><p>3： Office 通訊伺服器2007</p></li>
<li><p>4： Office 通訊伺服器 2007 R2</p></li>
</ul></td>
<td><p>Office 通訊伺服器2007中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-BackEndServer</p></td>
<td><p>這個屬性會指定池後端伺服器的 FQDN。 因為每個池只能有一個後端伺服器，所以這是單一值屬性。</p>
<p>每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</p></td>
<td><p>即時通訊伺服器2005中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryHomePool</p></td>
<td><p>這個屬性包含主持會議目錄之池的識別碼。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectoryId</p></td>
<td><p>這個屬性包含會議目錄的識別碼。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryTargetPool</p></td>
<td><p>這個屬性包含要將會議目錄移到哪個池的識別碼。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-預設值</p></td>
<td><p>這個布林值屬性可定義電話使用方式是否為預設用法。 如果此屬性設定為<strong>TRUE</strong>，系統會使用電話的預設使用量，且無法由系統管理員刪除。 如果此屬性設定為<strong>FALSE</strong>，則可以刪除此用法。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWAExternalURL</p></td>
<td><p>這個屬性會針對組織外的使用者識別 Communicator Web 存取 URL。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultCWAInternalURL</p></td>
<td><p>這個屬性會針對組織內的使用者識別 Communicator Web 存取 URL。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultLocationProfileLink （已過時）</p></td>
<td><p>這個單一值屬性包含指派給它之位置設定檔類別物件的辨識名稱（DN）。</p>
<p>轉寄連結：<strong>連結識別碼 11036</strong></p>
<p>對應的 [向後] 連結為<strong>msRTCSIP-ServerReferenceBL</strong>。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultPolicy （已過時）</p></td>
<td><p>這個布林屬性指定原則是否為預設原則。 原則是設定為<strong>TRUE</strong>時的預設原則。</p></td>
<td><p>Office 通訊伺服器2007中的新功能</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultRouteToEdgeProxy （已過時）</p></td>
<td><p>這個屬性會指定執行存取邊緣服務的邊緣伺服器（如果可以直接存取）或硬體負載平衡器（在執行 Access Edge 服務的伺服器池中）的 FQDN。 如果只能透過一或多個控制器存取執行存取邊緣服務的伺服器，這個屬性會指定 FQDN，以及（也可以選擇）控制器的埠號碼，或硬體負載平衡器為主管池提供服務。</p>
<p>每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</p></td>
<td><p>即時通訊伺服器2005中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultRouteToEdgeProxyPort （已過時）</p></td>
<td><p>這個屬性代表應該用來連線到執行存取邊緣服務之伺服器的埠號碼。</p>
<p>有效的值是指定要使用的埠的整數值。 預設值為5061。</p></td>
<td><p>即時通訊伺服器2005中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefPresenceSubscriptionTimeout （已過時）</p></td>
<td><p>這個屬性代表預設的目前狀態訂閱超時期間。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefRegistrationTimeout （已過時）</p></td>
<td><p>這個屬性代表預設的 [註冊超時] 視窗。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefRoamingDataSubscriptionTimeout （已過時）</p></td>
<td><p>這個屬性代表預設的 [漫遊資料訂閱超時] 視窗。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DeploymentLocator</p></td>
<td><p>這個屬性是在分割網域拓撲中使用，並包含完全限定的功能變數名稱（FQDN）。</p></td>
<td><p>Lync Server 2010 的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-描述（已過時）</p></td>
<td><p>這個單一值的 UNICODE 字串屬性包含此手機路由或正常化規則的助記描述。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DomainData</p></td>
<td><p>這個屬性已保留供日後使用。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-功能變數名稱</p></td>
<td><p>這個屬性代表為註冊機構設定的網域。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EdgeProxyData</p></td>
<td><p>這個屬性已保留供日後使用。</p></td>
<td><p>即時通訊伺服器2005中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxyFQDN</p></td>
<td><p>這個屬性會指定執行存取邊緣服務之伺服器的 FQDN。</p>
<p>每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</p></td>
<td><p>即時通訊伺服器2005中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnableBestEffortNotify （已過時）</p></td>
<td><p>這個屬性控制伺服器是否會產生最佳努力通知（BENOTIFY）要求，而不是通知要求，以回應來自用戶端的訂閱要求。 BENOTIFY 是伺服器產生 BENOTIFY 要求而不是一般通知要求的 [訂閱通知握手] 延伸的效能。 效能好處是 BENOTIFY 要求不需要用戶端的 200 OK 回應，就像是通知要求。</p>
<p>有效值為<strong>TRUE</strong>或<strong>FALSE</strong>。</p>
<div>

> [!NOTE]  
> [即時通訊伺服器] 2003 不支援 BENOTIFY 要求。 若要與在即時通訊2005伺服器上執行的即時通訊伺服器2003伺服器 API （以及協力廠商伺服器）所撰寫的伺服器應用程式交互操作，可以透過將 BENOTIFY 要求設定為<STRONG>FALSE</STRONG>來加以停用。 BENOTIFY 目前不是 IETF （網際網路工程工作強制） SIP 標準化處理常式的一部分。


</div></td>
<td><p>即時通訊伺服器2005中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnableFederation （已過時）</p></td>
<td><p>這個屬性是一個全域開關，IT 系統管理員會使用它來設定是否允許使用者與其他組織的使用者通訊。 它可讓系統管理員覆寫個別使用者的<strong>FederationEnabled</strong>屬性。 此屬性可讓您協助保護內部網路，避免受到公司的蠕蟲、病毒或目標攻擊所造成的網際網路攻擊。</p>
<p>有效值（以及相關聯的位位置）如下所示：</p>
<ul>
<li><p>1：啟用公用 IM 連線（位位置0）</p></li>
<li><p>2：保留（bit 位置1）</p></li>
<li><p>4：保留（bit 位置2）</p></li>
<li><p>8：保留（bit 位置3）</p></li>
<li><p>16：已啟用遠端呼叫控制 [電話] （位位置4）</p></li>
<li><p>64： AllowOrganizeMeetingWithAnonymousParticipants （允許使用者邀請匿名使用者加入會議（位位置6）</p></li>
<li><p>128： UCEnabled （可讓使用者進行整合通訊）（位位置7）</p></li>
<li><p>256： EnabledForEnhancedPresence （可讓使用者使用公用 IM 連線）（bit 位置8）</p></li>
<li><p>512： RemoteCallControlDualMode （bit 位置9）</p></li>
</ul></td>
<td><p>即時通訊伺服器2005中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServices</p></td>
<td><p>這個屬性會指出是否要在指定的伺服器上載入企業服務。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ExtensionData</p></td>
<td><p>這個屬性已保留供日後使用。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ExternalAccessCode</p></td>
<td><p>這個屬性包含外部存取的撥號程式碼。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-FederationEnabled</p></td>
<td><p>這個屬性控制是否針對單一使用者啟用同盟。 它是由 [企業服務] 層強制執行。 它標示為供全域編目複製。</p>
<p>有效值為<strong>TRUE</strong>或<strong>FALSE</strong>。</p></td>
<td><p>即時通訊伺服器2005中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-FrontEndServers</p></td>
<td><p>這個屬性是一個多重值清單，其中包含與某個池關聯的所有企業版伺服器的功能變數名稱。</p>
<p>返回連結：<strong>連結識別碼 11023</strong></p>
<p>此返回連結的相對前連結是<strong>msRTCSIP-PoolAddress</strong>。</p></td>
<td><p>即時通訊伺服器2005中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-閘道（已過時）</p></td>
<td><p>這個多重值字串屬性包含閘道和埠的清單（每個閘道）。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalSettingsData （已過時）</p></td>
<td><p>這個屬性會儲存 [名稱：值] 對。 已定義的名稱：值對適用于 [<strong>允許輪詢目前狀態</strong>] 設定。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GroupingID</p></td>
<td><p>這個屬性是用來群組通訊錄專案之群組的唯一識別碼。</p></td>
<td><p>Lync Server 2010 的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeServer （已過時）</p></td>
<td><p>-</p></td>
<td><p>即時通訊伺服器2003中的新功能（不使用）。</p>
<p>在即時通訊伺服器2005中過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-HomeServerString （已過時）</p></td>
<td><p>-</p></td>
<td><p>即時通訊伺服器2003中的新功能。</p>
<p>在即時通訊伺服器2005中過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeUsers （已過時）</p></td>
<td><p>-</p></td>
<td><p>即時通訊伺服器2003中的新功能（不使用）。</p>
<p>在即時通訊伺服器2005中過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-InternetAccessEnabled</p></td>
<td><p>這個屬性控制是否已針對外部使用者存取啟用單一使用者。 它是由 [企業服務] 層強制執行。 它標示為供全域編目複製。</p>
<p>有效值為<strong>TRUE</strong>或<strong>FALSE</strong>。</p></td>
<td><p>即時通訊伺服器2005中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-IsMaster （已過時）</p></td>
<td><p>-</p></td>
<td><p>即時通訊伺服器2003中的新功能</p>
<p>在即時通訊伺服器2005中過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP 線</p></td>
<td><p>這個單一值屬性包含 Lync for 電話語音所使用的裝置識別碼（SIP URI 或使用者控制項電話的電話 URI）。 這個屬性標示為供全域編目複製，且已編制索引。 如果使用者已啟用企業語音，此屬性會儲存以164標準形式的使用者電話號碼。</p></td>
<td><p>Microsoft Office Live 通訊伺服器2005中的新功能（含 SP1）</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LineServer</p></td>
<td><p>這個單值屬性包含 CSTA-SIP 閘道伺服器的 SIP URI。 這個屬性標示為 [全域編目複製]，但未編制索引。</p></td>
<td><p>Microsoft Office Live 通訊伺服器2005中的新功能（含 SP1）</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationData （已過時）</p></td>
<td><p>這個屬性已保留供日後使用。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalizationLinks （已過時）</p></td>
<td><p>這個多重值屬性包含與此位置設定檔相關聯的局部正常化可分辨名稱（DN）清單。 這個屬性的類型是 DN 二進位。 位置設定檔與局部正常化規則之間有一對多的關聯性。 局部正常化 DNs 清單的排序必須依管理員指定的順序進行維護。 順序保留是由 DN 二進位的二進位部分所維護，它會指定訂單索引。</p>
<p>轉寄連結：<strong>連結識別碼 11034</strong></p>
<p>與此轉寄連結屬性相對應的 back 連結是<strong>msRTCSIP-LocationProfileBL</strong>。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationOptions</p></td>
<td><p>這個屬性包含正常化規則選項的清單。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationName （已過時）</p></td>
<td><p>這個單一值屬性包含位置設定檔的易記名稱，指出此設定檔代表的位置。 因為可能有多個位置設定檔，所以管理員需要一種方式來區分不同的設定檔。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-locationProfileBL （已過時）</p></td>
<td><p>這個多重值屬性包含位置設定檔辨識名稱的清單。 這個屬性會指定一個或多個位置設定檔的上一頁連結。</p>
<p>返回連結：<strong>連結識別碼 11035</strong></p>
<p>這個屬性會對應到轉寄連結<strong>msRTCSIP-LocalNormalizationLinks</strong>。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfileData （已過時）</p></td>
<td><p>這個屬性已保留供日後使用。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfileOptions</p></td>
<td><p>這個屬性包含位置設定檔的選項。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MappingContact</p></td>
<td><p>這個多重值屬性會保留應用程式連絡人清單。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MappingLocation</p></td>
<td><p>這個多重值屬性會保留位置設定檔的清單。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxNumOutstandingSearchPerServer （已過時）</p></td>
<td><p>這個屬性代表每個伺服器上未處理的搜尋要求數目上限。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxNumSubscriptionsPerUser （已過時）</p></td>
<td><p>屬性代表每個使用者的訂閱數上限。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxPresenceSubscriptionTimeout （已過時）</p></td>
<td><p>這個屬性代表 [訂閱超時] 視窗的最大值。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxRegistrationsTimeout （已過時）</p></td>
<td><p>這個屬性代表 [最大註冊超時] 視窗。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxRoamingDataSubscriptionTimeout （已過時）</p></td>
<td><p>這個屬性代表最大的 [漫遊資料訂閱超時] 視窗。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUData</p></td>
<td><p>這個屬性已保留供日後使用。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryAddress</p></td>
<td><p>這個屬性是電腦類別下的服務控制點屬性，可指定連結回到它所屬的 multipoint 控制項單元（MCU）工廠。 針對每個 Microsoft MCU，都會建立此服務控制點和屬性。 每個 Microsoft MCU 都必須找到它所屬之池的後端伺服器，才能從它取得池層級設定。</p>
<p>這個屬性的值是 MCU 工廠的辨識名稱（DN）。 這是單值屬性，並標示為供全域編目複製。</p>
<p>轉寄連結：<strong>連結識別碼 11026</strong></p>
<p>與此轉寄連結屬性相對應的 back 連結是<strong>msRTCSIP-MCUServers</strong>。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryData</p></td>
<td><p>這是多重字串保留屬性。 儲存在這個屬性中的設定會以名稱 = 值對表示。 目前定義的名稱 = 值對：</p>
<ul>
<li><p>FactoryURL = &lt;URL&gt;</p></li>
</ul></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryPath</p></td>
<td><p>這個單一值屬性包含與某個池相關聯的單一 MCU 工廠的辨識名稱（DN）。</p>
<p>轉寄連結：<strong>連結識別碼 11024</strong></p>
<p>與此轉寄連結屬性相對應的 back 連結是<strong>msRTCSIP-PoolAddresses</strong>。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryProviderID</p></td>
<td><p>這個屬性是一個指定 MCU 工廠提供者的 GUID 的單一值字串。 根據 GUID 值，MCU factory 進程會判斷是否要為此 MCU 類型服務。 如果 GUID 值是<strong>{F0810510-424F-46ef-84FE-6CC720DF1791}</strong>，則 MCU factory 程式（在 Lync Server 中則預設提供）會處理它。 對於任何其他 GUID 值，MCU factory 進程將不會為 MCU 類型提供服務。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUServers</p></td>
<td><p>這個屬性是一個多重值清單，可分辨名稱（DN）。 這個屬性包含與此 MCU 工廠相關聯之相同類型和廠商的所有 MCU 伺服器清單。 每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</p>
<p>返回連結：連結識別碼11027</p>
<p>此返回連結的相對前連結是<strong>msRTCSIP-MCUFactoryAddress</strong>。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUType</p></td>
<td><p>這個屬性是單一值字串，它指定了 MCU 可以處理的媒介。</p>
<p>支援的有效類型包括：</p>
<ul>
<li><p>要求</p></li>
<li><p>音訊-影片</p></li>
<li><p>交流</p></li>
<li><p>電話會議</p></li>
</ul></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUVendor</p></td>
<td><p>這個屬性是指定 MCU 廠商名稱的單一值字串。 所有 Microsoft MCUs 都會將這個屬性指定為<strong>Microsoft Corporation</strong>。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MeetingFlags （已過時）</p></td>
<td><p>這個屬性會定義不同的會議選項，這些選項會針對所有使用者或連絡人物件全域啟用。 這個屬性是整數類型的位元遮罩值。</p>
<p>有效值（以及相關聯的位位置）如下所示：</p>
<ul>
<li><p>0： AllowOrganizeMeetingWithAnonymousParticipants 為 None （不允許使用者邀請匿名使用者加入會議）（未設定位）</p></li>
<li><p>4： AllowOrganizeMeetingWithAnonymousParticipants 為 [所有人] （允許所有使用者邀請匿名使用者加入會議）（位位置2）</p></li>
<li><p>8： AllowOrganizeMeetingWithAnonymousParticipants 是 UsePerUserSetting （允許使用者根據每個使用者設定邀請匿名使用者加入會議）（位位置3）</p></li>
<li><p>16： UserPerUserMeetingPolicy （會議原則是針對每位使用者定義）（bit 位置4）</p></li>
</ul></td>
<td><p>Office 通訊伺服器2007中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MeetingPolicy （已過時）</p></td>
<td><p>這個屬性會指定管理員指派給此使用者做為單一值屬性之原則的辨識名稱（DN）。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinPresenceSubscriptionTimeout （已過時）</p></td>
<td><p>這個屬性代表最小的目前狀態訂閱超時視窗。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MinRegistrationTimeout （已過時）</p></td>
<td><p>這個屬性代表最小的註冊超時視窗。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinRoamingDataSubscriptionTimeout （已過時）</p></td>
<td><p>這個屬性代表最小的 [漫遊資料訂閱超時] 視窗。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>這個屬性是用來儲存前端池所使用的鏡像 SQL Server 後端。</p></td>
<td><p>Lync Server 2013 的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MobilityFlags</p></td>
<td><p>這個屬性包含定義行動設定的選項和標誌。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MobilityPolicy</p></td>
<td><p>這個屬性包含行動策略物件的 DN。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-NumDevicesPerUser （已過時）</p></td>
<td><p>這個屬性代表允許使用者註冊 SIP 通訊及訂閱目前狀態的裝置數量。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OptionFlags</p></td>
<td><p>這個屬性會指定為使用者或連絡人物件啟用的選項。 這個屬性是 integer 類型的位元遮罩值。 每個選項都是由一個位來表示。 這個屬性標示為供全域編目複製。</p>
<p>有效值（以及相關聯的位位置）如下所示：</p>
<ul>
<li><p>1：啟用公用立即訊息（IM）連線（位位置0）</p></li>
<li><p>2：保留（bit 位置1）</p></li>
<li><p>4：保留（bit 位置2）</p></li>
<li><p>8：保留（bit 位置3）</p></li>
<li><p>16：已啟用遠端呼叫控制 [電話] （位位置4）</p></li>
<li><p>64： AllowOrganizeMeetingWithAnonymousParticipants （允許使用者邀請匿名使用者加入會議（位位置6）</p></li>
<li><p>128： UCEnabled （啟用 UC 的使用者）（位位置7）</p></li>
<li><p>256： EnabledForEnhancedPresence （可讓使用者使用公用 IM 連線）（bit 位置8）</p></li>
<li><p>512： RemoteCallControlDualMode （bit 位置9）</p></li>
</ul></td>
<td><p>即時通訊伺服器2005中的新功能（含 SP1）。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-OriginatorSID</p></td>
<td><p>這個屬性是在資源與中央林拓撲中使用，可在從 Windows NT 伺服器主體帳戶將使用者的 ObjectSID 複製到資源或中央林中的對應使用者或連絡人物件的這個屬性時，啟用單一登入。 Communicator Web Access 會使用這個屬性或使用者的 ObjectSID，在 AD DS 中搜尋使用者。 這個屬性標示為供全域編目複製。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OwnerUrn</p></td>
<td><p>這個屬性是應用程式連絡人擁有者的統一資源名稱（URN）。</p></td>
<td><p>Lync Server 2010 的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-模式（已過時）</p></td>
<td><p>這個單值字串屬性包含一個模式，用於將撥號號碼與 E. 164 格式搭配使用。 如果撥號號碼符合這個模式，就會將轉換套用到撥號號碼。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteBL （已過時）</p></td>
<td><p>這個多重值屬性包含一份電話路線可分辨名稱（DN）清單。 這個屬性指定了一或多個電話路由的上一頁連結。</p>
<p>返回連結：<strong>連結識別碼 11033</strong></p>
<p>這個屬性會對應到轉寄連結<strong>msRTCSIP-RouteUsageLinks</strong>。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRouteData （已過時）</p></td>
<td><p>這個屬性已保留供日後使用。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteName （已過時）</p></td>
<td><p>這個單一值 UNICODE 字串屬性會指定電話路線的易記名稱，所以系統管理員可以輕鬆地參考它。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneUsageData （已過時）</p></td>
<td><p>這個屬性已保留供日後使用。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyContent （已過時）</p></td>
<td><p>這個屬性是單一值的 Unicode 字串。 這個字串屬性包含 XML 格式的原則定義。 XML 架構定義在不同的原則類型中是通用的，只有每個原則類型的設定都是不同的。</p>
<p>XML 架構定義（XSD）的定義如下所示：</p>
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
<td><p>Office 通訊伺服器2007中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PolicyData （已過時）</p></td>
<td><p>這個屬性已保留供日後使用。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyType （已過時）</p></td>
<td><p>這個單一值的 Unicode 字串屬性包含原則類型。 有效的原則類型如下：</p>
<ul>
<li><p>要求</p></li>
<li><p>$</p></li>
</ul></td>
<td><p>Office 通訊伺服器2007中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolAddress</p></td>
<td><p>這個屬性會指定回到電腦所屬之池的連結。 無論電腦執行的是標準版或企業版的 Lync Server，都要設定此屬性。 這個屬性標示為供全域編目複製。</p>
<p>有效值為 pool 的功能變數名稱。</p>
<p>轉寄連結：<strong>連結識別碼 11022</strong></p>
<p>與此轉寄連結屬性相對應的 back 連結是<strong>msRTCSIP-FrontEndServers</strong>。</p></td>
<td><p>即時通訊伺服器2005中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolAddresses</p></td>
<td><p>這是一個多重值屬性，其中包含與 MCU 工廠相關聯之 pool 的辨別名稱（DN）清單。</p>
<p>返回連結：<strong>連結識別碼 11025</strong></p>
<p>此返回連結的相對前連結是<strong>msRTCSIP-MCUFactoryPath</strong>。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolData</p></td>
<td><p>這個屬性已保留供日後使用。</p></td>
<td><p>即時通訊伺服器2005中的新功能（含 SP1）。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolDisplayName</p></td>
<td><p>這個屬性會指定管理主控台所顯示之池的任意名稱。 系統管理員可以變更此名稱。</p>
<p>有效的值是代表某個池名稱的字串。</p></td>
<td><p>即時通訊伺服器2005中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolDomainFQDN</p></td>
<td><p>這個屬性是單一值的字串值。 此屬性的值（如果有的話）代表池的網域 FQDN （如果系統管理員想要使用不符合在其中建立頂層端池之 Active Directory 網域結構的 FQDN）來建立該前端池（例如，SIP從 Domain Name System （DNS）命名空間中移除命名空間。</p>
<p>我們建議您將前端池網域 FQDN 對應至功能變數名稱部分，將其放在該池所在的 Active Directory 網域中。 因此，如果此屬性中沒有值，則 [前端] 池 FQDN 將預設為 Active Directory 功能變數名稱結構（由<strong>dnsHostName</strong>屬性工作表示）。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolFunctionality</p></td>
<td><p>多值清單，其中列出與某個池關聯的所有 Lync Server、企業版伺服器的功能變數名稱。 此整數類型的這個屬性會定義該池是否具備立即訊息（IM）與目前狀態及會議。</p>
<p>可能的有效值類型如下所示：</p>
<ul>
<li><p>未定義： IM 和目前狀態服務（即時通訊伺服器2005和2003）</p></li>
<li><p>1： IM 和目前狀態服務（Lync Server）</p></li>
<li><p>2： IM 和目前狀態與會議服務（Lync Server）</p></li>
</ul></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolType</p></td>
<td><p>這個屬性指定伺服器池是否正在執行標準版 server 或 Enterprise Edition 伺服器。 這個屬性是 integer 類型的位元遮罩值。 每個選項都是由一個位來表示。</p>
<p>有效值（以及相關聯的位位置）如下所示：</p>
<ul>
<li><p>1：標準版伺服器、主機使用者（位位置0）</p></li>
<li><p>2：企業版 server、主機使用者（位位置1）</p></li>
<li><p>4：標準版伺服器、主機應用程式（位位置2）</p></li>
<li><p>8：企業版 server、主機應用程式（位位置3）</p></li>
</ul>
<p>因為 Lync Server 不支援僅限託管應用程式的池，所以唯一有效的值如下所示：</p>
<ul>
<li><p>5：標準版 server、主機使用者和應用程式（bit 位置0和2）</p></li>
<li><p>10：企業版 server、主機使用者和應用程式（bit 位置1和3）</p></li>
</ul></td>
<td><p>即時通訊伺服器2005中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolVersion</p></td>
<td><p>這個屬性會定義池子版本。 它是每個主要產品發行增加的整數類型。</p>
<p>可能的有效值類型如下所示：</p>
<ul>
<li><p>0：即時通訊伺服器2003</p></li>
<li><p>1：即時通訊伺服器2005</p></li>
<li><p>2：即時通訊伺服器2005與 SP1</p></li>
<li><p>3： Office 通訊伺服器2007</p></li>
<li><p>4： Office 通訊伺服器 2007 R2</p></li>
<li><p>5： Lync Server 2010</p></li>
</ul></td>
<td><p>即時通訊伺服器2005（含 SP1）。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PresenceFlags</p></td>
<td><p>這個屬性包含定義目前狀態設定的選項和標誌。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PresencePolicy</p></td>
<td><p>這個屬性包含目前狀態原則物件的 DN。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrimaryHomeServer</p></td>
<td><p>此屬性可讓使用者或連絡人進行 SIP 訊息。 因為在中央目錄林拓撲中，連絡人物件（而非使用者物件）是 SIP 啟用的，所以會將它加入連絡人類別。</p>
<p>有效值為使用者所駐留之標準版 server 或 Enterprise Edition 前端池的 DN。</p></td>
<td><p>即時通訊伺服器2005中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>這個屬性包含指定使用者的 SIP 位址。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrivateLine</p></td>
<td><p>這個屬性包含專用線路裝置的裝置識別碼。</p></td>
<td><p>Lync Server 2010 的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP 路由</p></td>
<td><p>這個屬性是一個布林值屬性，用來判斷 Lync Server 是否有授權使用其 GRUU 位址路由至此服務。 如果此值設定為<strong>TRUE</strong>，則 Lync Server 有權路由至此服務。 如果此值設定為<strong>FALSE</strong>，則 Lync Server 無權路由至此服務。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsageAttribute （已過時）</p></td>
<td><p>這個單一值的 UNICODE 字串屬性會定義一個限定手機路線用法的屬性。 手機路線的選取是根據兩個元素來決定：指派給手機路線的使用方式屬性，以及來電者的允許原則使用屬性。 已選取與本機號碼的使用方式屬性相符的第一個電話路線。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsageLinks （已過時）</p></td>
<td><p>這個多重值的辨別名稱（DN）屬性包含路由使用的可分辨名稱清單。</p>
<p>轉寄連結：<strong>連結識別碼 11032</strong></p>
<p>這個屬性是相對應的 back 連結<strong>msRTCSIP-PhoneRouteBL</strong>的轉寄連結。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RoutingPoolDN</p></td>
<td><p>這個屬性包含指向您針對此 MCU 或受信任的服務所傳送之所有 SIP 流量必須經過的該池的 DN。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RuleName （已過時）</p></td>
<td><p>這個單一值的 UNICODE 字串屬性會指定正常化規則的易記名稱，所以系統管理員可以輕鬆地參考它。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SchemaVersion</p></td>
<td><p>這個屬性代表目前部署在組織中的架構版本。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SearchMaxRequests （已過時）</p></td>
<td><p>這個屬性會限制使用者使用 Communicator 搜尋連絡人時，從目錄搜尋傳回的搜尋結果數目。 這個屬性會覆寫用戶端提供的值。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SearchMaxResults （已過時）</p></td>
<td><p>這個屬性會限制傳回的搜尋要求數目。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerBL</p></td>
<td><p>這個多重值屬性是一個包含辨識名稱（DN）清單的返回連結。 這些 DNs 指向一個 pool 或<strong>TrustedService</strong>物件。</p>
<p>這個屬性會對應到轉寄連結<strong>msRTCSIP-TrustedServiceLinks</strong>。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerData</p></td>
<td><p>這個屬性已保留供日後使用。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerReferenceBL （已過時）</p></td>
<td><p>這個多重值屬性包含辨識名稱的清單。 這些辨識名稱會傳回參照可指派預設位置設定檔之其他伺服器物件的連結。</p>
<p>返回連結：<strong>連結識別碼 11037</strong></p>
<p>此返回連結的相對前連結是<strong>msRTCSIP-DefaultLocationProfileLink</strong>。</p>
<p>這個返回連結屬性只會參照池和轉送伺服器。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerVersion</p></td>
<td><p>這個屬性會定義伺服器的版本資訊。 此版本號碼適用于所有伺服器角色。 它是一種 monotonously 增加的整數，會隨著每個正式產品發行而增加。</p>
<p>可能的有效值如下：</p>
<ul>
<li><p>未定義：即時通訊伺服器2003</p>
<p>                 [即時通訊伺服器] 2005</p>
<p>                 使用 SP1 進行即時通訊伺服器2005</p></li>
<li><p>3： Office 通訊伺服器2007</p></li>
<li><p>4： Office 通訊伺服器 2007 R2</p></li>
<li><p>5： Lync Server 2010</p></li>
<li><p>6： Lync Server 2013</p></li>
</ul></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SourceObjectType</p></td>
<td><p>整數類型的這個單值屬性會指定<strong>SourceObjectDN</strong>指向的物件類型，如下所示：</p>
<ul>
<li><p>null |0x00000001：代表不同林中的 Windows NT 伺服器主體使用者物件</p></li>
<li><p>下列屬性代表通訊群組延伸的不同樹林中的群組類型：</p>
<ul>
<li><p>0x00000002： ADS_GROUP_TYPE_GLOBAL_GROUP</p></li>
<li><p>0x00000004： ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</p></li>
<li><p>0x00000004： ADS_GROUP_TYPE_LOCAL_GROUP</p></li>
<li><p>0x00000008： ADS_GROUP_TYPE_UNIVERSAL_GROUP</p></li>
<li><p>0x80000000： ADS_GROUP_TYPE_SECURITY_ENABLED</p></li>
<li><p>0x90000000：代表來自同一個目錄林或不同林中的自動助理或訂閱者存取物件</p></li>
</ul></li>
</ul></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SubscriptionAuthRequired （已過時）</p></td>
<td><p>-</p></td>
<td><p>即時通訊伺服器2003中的新功能。</p>
<p>在即時通訊伺服器2005中過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetHomeServer</p></td>
<td><p>這個屬性可讓您將使用者或連絡人物件從一個 Lync 伺服器池移至另一個。 這個屬性會新增至 contact 類別，因為在中央目錄林拓撲中，連絡人物件（而非使用者物件）是 SIP 啟用的。</p>
<p>有效值是要將使用者移至其中的目的地標準版伺服器或前端池之 DN。</p></td>
<td><p>即時通訊伺服器2005中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TargetPhoneNumber （已過時）</p></td>
<td><p>這個單值字串屬性包含電話號碼模式或範圍，以路由至在<strong>msRTCSIP-閘道</strong>中定義的指定閘道。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetUserPolicies</p></td>
<td><p>這個屬性會儲存 Lync Server 使用者之目標原則的名稱/值對。</p></td>
<td><p>Lync Server 2010 的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TenantId</p></td>
<td><p>這個屬性會儲存租使用者的唯一識別碼。</p></td>
<td><p>Lync Server 2010 的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-翻譯（已過時）</p></td>
<td><p>這個屬性是由 Lync Server 的語音功能所使用，而且包含要在撥打電話號碼上套用的翻譯字串（如果找到相符專案）。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCUData</p></td>
<td><p>這個屬性已保留供日後使用。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUFQDN</p></td>
<td><p>這個屬性是包含 MCU FQDN 的字串值。 這是單值屬性。 每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxyData</p></td>
<td><p>這個屬性已保留供日後使用。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxyFQDN</p></td>
<td><p>這個屬性是一個字串值，其中包含執行 Proxy 伺服器之伺服器的 FQDN。 這個屬性是單一值。 每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerData</p></td>
<td><p>這個屬性已保留供日後使用。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServerFQDN</p></td>
<td><p>這個屬性是一個代表信任伺服器 FQDN 的單一值屬性。</p></td>
<td><p>即時通訊伺服器2005中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerVersion</p></td>
<td><p>這個屬性會指定可信伺服器清單中伺服器的版本號碼。</p>
<p>可能的有效值如下：</p>
<ul>
<li><p>Null：即時通訊伺服器2003</p></li>
<li><p>2：即時通訊伺服器2005</p></li>
<li><p>3： Office 通訊伺服器2007</p></li>
<li><p>4： Office 通訊伺服器 2007 R2</p></li>
<li><p>5： Lync Server 2010</p></li>
<li><p>6： Lync Server 2013</p></li>
</ul></td>
<td><p>即時通訊伺服器2005中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServiceFlags</p></td>
<td><p>這個屬性會定義受信任服務啟用的選項。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceLinks</p></td>
<td><p>這個多重值屬性包含參照受信任的服務物件（例如媒體轉送驗證服務）的辨識名稱（DN）清單。 媒體轉送驗證服務（在執行 A/V 會議服務的邊緣伺服器上實際 collocated）必須與一個池建立關聯，才能支援遠端使用者的音訊案例。</p>
<p>與此轉寄連結屬性相對應的 back 連結是<strong>msRTCSIP-ServerBL</strong>。</p></td>
<td><p>整合通訊</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServicePort</p></td>
<td><p>這個屬性是一個整數，定義用來連接此 GRUU 服務的埠號碼。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceType</p></td>
<td><p>這個屬性是一個定義其所代表之 GRUU 服務類型的字串值。</p>
<p>有效的 GRUU 服務類型如下所示：</p>
<ul>
<li><p>MediationServer</p></li>
<li><p>關</p></li>
<li><p>媒體轉送驗證服務（MRAS）</p></li>
<li><p>QoSM</p></li>
<li><p>msRTCSIP-UserExtension CWA</p></li>
</ul></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServerData</p></td>
<td><p>這個屬性已保留供日後使用。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServerFQDN</p></td>
<td><p>這個屬性是一個字串值，其中包含執行 Lync Server Web 服務的 IIS FQDN。 這是單值屬性。 每個區段的有效值為63個字元;整個 FQDN 的有效值為255個字元。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UCFlags （已過時）</p></td>
<td><p>這個屬性定義不同的 UC 選項，這些選項會針對所有使用者或連絡人物件全域啟用。 這個屬性是整數類型的位元遮罩值。 每個選項都是由一個位所代表。</p>
<p>可能的有效值（以及相關聯的位位置）如下所示：</p>
<ul>
<li><p>4： UsePerUserUCPolicy （bit 位置2）</p></li>
</ul>
<p>如果設定了這個位數，UC 原則就會定義為 [每位使用者]。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UCPolicy （已過時）</p></td>
<td><p>這個單一值屬性包含管理員已指派給此使用者的 UC 原則的辨識名稱（DN）。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserDomainList （已過時）</p></td>
<td><p>這個屬性提供林中所有主機擁有 SIP 的使用者的網域清單。 預設值為空白清單，表示林中的所有網域都已啟用 SIP。</p>
<p>有效值為多個字串，代表個別網域的功能變數名稱。</p></td>
<td><p>即時通訊伺服器2005中的新功能。</p>
<p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserEnabled</p></td>
<td><p>這個屬性會判斷使用者目前是否已啟用 Lync Server。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserExtension</p></td>
<td><p>這個多重值屬性包含名稱 = 值格式&quot;的名稱/值對清單。&quot;這個屬性標示為供全域編目複製。</p></td>
<td><p>即時通訊伺服器2005中的新功能（含 SP1）。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserLocationProfile</p></td>
<td><p>這個屬性包含指向位置設定檔物件的辨別名稱（DN）。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserPolicies</p></td>
<td><p>這個屬性會儲存使用者原則的名稱/值對。</p></td>
<td><p>Lync Server 2010 的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserPolicy</p></td>
<td><p>這是包含辨識名稱清單的多重值屬性，二進位（DN_WITH_BINARY）指向不同類型的全域使用者原則。 二進位部分指出 DN 部分指向的原則類型。</p>
<p>有效的二進位值如下所示：</p>
<ul>
<li><p>0x00000001：會議原則</p></li>
<li><p>0x00000002： UC 原則</p></li>
<li><p>0x00000005：目前狀態原則</p></li>
</ul></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>這是 SIP 路由群組識別碼。 相同群組中的使用者會註冊到相同的前端伺服器。</p></td>
<td><p>Lync Server 2013 的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsData</p></td>
<td><p>這是多重值屬性。 這個屬性已保留供日後使用。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsPoolAddress</p></td>
<td><p>這個單一值屬性會指向網頁元件所屬的 pool 或標準版伺服器。</p>
<p>轉寄連結：<strong>連結識別碼 11028</strong></p>
<p>與此轉寄連結屬性相對應的 back 連結是<strong>msRTCSIP-WebComponentsServers</strong>。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsServers</p></td>
<td><p>這個屬性是多值的辨識名稱清單。 這個屬性包含與此 pool 關聯的所有 Web 服務器清單。</p>
<p>返回連結：<strong>連結識別碼 11029</strong></p>
<p>此返回連結的相對前連結是<strong>msRTCSIP-WebComponentsPoolAddress</strong>。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WMIInstanceId （已過時）</p></td>
<td><p>-</p></td>
<td><p>即時通訊伺服器2003中的新功能。</p>
<p>在即時通訊伺服器2005中過時。</p></td>
</tr>
<tr class="odd">
<td><p>OtherIPPhone</p></td>
<td><p>[電話語音] 會使用這個現有的 Active Directory 屬性來指定手機的備用 TCP/IP 地址清單。</p></td>
<td><p>Windows Server 2008 作業系統中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>PhoneOfficeOther</p></td>
<td><p>在 Lync Server 的語音元件中，只有連絡人物件，才會使用這個現有的 Active Directory 屬性，目的是將呼叫路由到統一訊息自動助理和訂閱者存取號碼。 無條件來電轉接位址會儲存在這個多重值屬性中。 這個帳戶是針對自動助理和訂閱者存取的特定用途而建立。 系統管理員不應該修改這個帳戶的屬性。</p></td>
<td><p>Windows 2000 作業系統中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>ProxyAddresses</p></td>
<td><p>這個現有的 Active Directory 多重值屬性是 Windows 2000 中所引進之基本 Active Directory 架構的一部分。 這個屬性包含使用者電子郵件的各種 X400、X500 及 SMTP 位址。 在 [即時通訊伺服器2003及更新版本] 中，使用者的 SIP URI 會新增至此清單&quot;（使用&quot; [SIP：] 標記）。</p>
<p>下列應用程式會從這個屬性搜尋使用者的 SIP URI：</p>
<ul>
<li><p>Microsoft Office Outlook 2003 訊息與共同作業用戶端</p></li>
<li><p>Microsoft Office SharePoint Server 2007</p></li>
</ul></td>
<td><p>Windows 2000 作業系統中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>Telephonenumber 相同</p></td>
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

