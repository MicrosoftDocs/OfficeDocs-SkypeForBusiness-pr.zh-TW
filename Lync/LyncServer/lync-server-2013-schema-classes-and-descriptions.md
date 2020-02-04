---
title: Lync Server 2013：架構類別和描述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema classes and descriptions
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48184612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5080af0977457f5c4a75d2f121e75560b0f24524
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a>Lync Server 2013 中的架構類別和描述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-30_

本節將說明 Lync Server 2013 使用的所有架構類別。

<div>

## <a name="schema-classes-and-descriptions"></a>架構類別和描述


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>靜態類</th>
<th>說明</th>
<th>批註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>郵件-收件者</p></td>
<td><p>Exchange 整合通訊（UM）電子郵件收件者。</p></td>
<td><p>這個輔助類別是與 Exchange UM 共用。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationContacts</p></td>
<td><p>這個類別是多個應用程式連絡人的容器，且不包含任何屬性本身。</p></td>
<td><p>Microsoft Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServer</p></td>
<td><p>這個類別會保留針對整合通訊應用程式服務（UCAS）實例之服務控制點的專案。</p></td>
<td><p>Office 通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerService</p></td>
<td><p>這個類別提供從特定的池中到其應用程式服務的關聯。</p></td>
<td><p>通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerSettings</p></td>
<td><p>此輔助類別可 msRTCSIP-ApplicationServer 保留代表應用程式服務實例之設定的屬性。</p></td>
<td><p>通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP 封存（已過時）</p></td>
<td><p>此輔助類別可 msRTCSIP-GlobalContainer 保留與封存相關的所有設定。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServer （已過時）</p></td>
<td><p>這個類別代表單一立即訊息存檔伺服器。 當電腦啟動為立即訊息存檔伺服器（例如已安裝立即訊息存檔服務的電腦）時，就會建立這個類別的實例。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectories</p></td>
<td><p>這個類別是多個會議目錄實例的容器，且不包含任何屬性本身。</p></td>
<td><p>通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectory</p></td>
<td><p>這個類別會保留代表特定會議目錄設定的屬性。</p></td>
<td><p>通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConnectionPoint</p></td>
<td><p>一般服務控制點（SCP），將電腦指定為執行 Lync Server 的伺服器。</p></td>
<td><p>Lync 2010 的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWABank</p></td>
<td><p>這個輔助類別會保留 Microsoft Lync Web App 銀行的設定。</p></td>
<td><p>通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-網域</p></td>
<td><p>這個類別會保留定義 SIP 註冊機構的已設定網域的屬性。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxy</p></td>
<td><p>這個類別容器代表單一存取邊緣服務。 因為 Access Edge 服務是在周邊網路中部署，而且客戶通常不允許從周邊網路存取 Active Directory 網域服務，所以 Access Edge 服務的實例不會加入內部網路的 Active Directory 網路。 因此，Access proxy 不會自動在 AD DS 中註冊。 系統管理員必須在 AD DS 中手動設定每個 Access Edge 服務實例的存在。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseMCUSettings</p></td>
<td><p>這個輔助類別至 msRTCSIP-MCU 保留代表會議服務器設定的屬性。</p></td>
<td><p>Microsoft Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnterpriseMediationServerSettings</p></td>
<td><p>此輔助類別可 msRTCSIP-MediationServer 保留代表對轉送伺服器的設定的屬性。</p></td>
<td><p>Office 通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServerSettings</p></td>
<td><p>此輔助類別可 msRTCSIP-Server 封存屬性代表 SIP 伺服器的設定。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-同盟</p></td>
<td><p>此輔助類別至 msRTCSIP-GlobalContainer 會保留與同盟相關的所有設定。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalContainer</p></td>
<td><p>這個類別會保留所有適用于 Lync Server 部署的設定。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalUserPolicy （已過時）</p></td>
<td><p>這個類別代表單一的 Office 通訊伺服器會議原則。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>本機全域拓撲設定物件。</p></td>
<td><p>Lync Server 2010 的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalTopologySettings</p></td>
<td><p>容納全域拓撲設定物件的容器。</p></td>
<td><p>Lync Server 2010 的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalization</p></td>
<td><p>這個類別是一個代表位置正常化規則實例的容器。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationContactMapping</p></td>
<td><p>這個類別是由會議助理應用程式所建立，並保留用於依地區分類會議電話號碼的屬性。</p></td>
<td><p>通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationContactMappings</p></td>
<td><p>這個類別是多個位置連絡人對應的實例容器，且不包含任何屬性本身。</p></td>
<td><p>通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfile</p></td>
<td><p>這個類別是代表特定位置設定檔的容器。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfiles （已過時）</p></td>
<td><p>這個類別是多個位置設定檔的容器，且不包含任何屬性本身。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizations （已過時）</p></td>
<td><p>這個類別是多個局部正常化規則的容器，且不包含任何屬性本身。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCU</p></td>
<td><p>這個類別代表單一的會議服務器。</p></td>
<td><p>通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactories</p></td>
<td><p>這個類別會保留多個 msRTCSIP MCUFactory 類別，而且沒有屬性本身。</p></td>
<td><p>通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactory</p></td>
<td><p>這個類別是一個代表單一中型類型會議服務器工廠的容器。 此類別的實例會在啟用此特定類型和供應商的第一個會議服務器時建立。</p></td>
<td><p>通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryService</p></td>
<td><p>這個類別提供從特定的池中到它的會議服務器工廠的關聯。</p></td>
<td><p>通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MediationServer</p></td>
<td><p>這個類別會儲存轉送伺服器的服務控制點專案。</p></td>
<td><p>通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-會議（已過時）</p></td>
<td><p>此輔助類別可 msRTCSIP-GlobalContainer 保留代表可設定會議設定的屬性。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-行動性</p></td>
<td><p>儲存全域行動設定的容器。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MonitoringServer</p></td>
<td><p>這個類別會保留代表單一監視伺服器設定的屬性。</p></td>
<td><p>通訊伺服器 2007 R2 中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRoute （已過時）</p></td>
<td><p>這個類別是代表閘道或閘道組之最小成本路線實例的容器。 此資訊是由執行標準版的所有企業池或伺服器所使用，以最經濟划算的方式將撥出電話路由到公用交換電話網絡（PSTN）。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRoutes （已過時）</p></td>
<td><p>這個類別是多個最低成本路由的容器，而且不包含任何屬性本身。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-原則（已過時）</p></td>
<td><p>這個類別會保留多個 Lync 伺服器原則類別，而且沒有任何屬性本身。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Pool</p></td>
<td><p>這個類別代表單一的 Lync 伺服器池。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Pool</p></td>
<td><p>這個類別會保留多個 Lync 伺服器池，而且沒有任何屬性本身。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolService</p></td>
<td><p>這個類別代表一個池子的服務控制 pointservice 控點。 主機上託管的使用者會將其 msRTCSIP-PrimaryHomeServer 屬性指向這個類別的實例。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-目前狀態</p></td>
<td><p>儲存全域目前狀態設定的容器。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-註冊機構</p></td>
<td><p>此輔助類別可 msRTCSIP-GlobalContainer 保留代表 SIP 註冊機構所維護之使用者設定的屬性。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsage （已過時）</p></td>
<td><p>這個類別是代表手機路線使用量的實例的容器。 電話路線使用類別由屬性欄位和描述欄位組成。 屬性欄位會定義用法類型。 [描述] 欄位可讓系統管理員描述手機路線中這個屬性的使用方式。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsages （已過時）</p></td>
<td><p>這個類別會保留 msRTCSIP-RouteUsage 類別的多個實例，且不具備任何屬性本身。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-搜尋</p></td>
<td><p>這個輔助類別至 msRTCSIP-GlobalContainer 保留限制及控制搜尋結果範圍的屬性。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-伺服器</p></td>
<td><p>這個類別代表一台執行 Lync Server 的伺服器。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-服務</p></td>
<td><p>這個類別會保留全域設定容器與 msRTCSIP 網域物件。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCU</p></td>
<td><p>這個類別會保留代表受信任的會議服務器設定的屬性。</p></td>
<td><p>通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUs</p></td>
<td><p>這個類別會保留 msRTCSIP-TrustedMCU 類別的多個實例，且不具備任何屬性本身。</p></td>
<td><p>通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxies</p></td>
<td><p>這個類別會保留多個 msRTCSIP TrustedProxy 類別，且不包含任何屬性本身。</p></td>
<td><p>通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxy</p></td>
<td><p>這個類別是一個代表執行 Proxy 伺服器的伺服器容器。 當您在已加入 AD DS 的電腦上啟用新的 Proxy 伺服器時，就會建立這個類別的實例。</p></td>
<td><p>通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServer</p></td>
<td><p>這個類別會保留代表信任伺服器設定的屬性。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedService</p></td>
<td><p>這個類別是一個代表可透過全域路由使用者代理程式 URI （GRUU）位址路由的信任服務的容器。 當啟用 Lync Server 信任的新伺服器時，就會建立這個類別的實例。 這個受信任的伺服器必須加入 Active Directory 網域。</p></td>
<td><p>通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServices</p></td>
<td><p>這個類別是多個 GRUU 伺服器的容器，且不包含任何屬性本身。</p></td>
<td><p>通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServer</p></td>
<td><p>這個類別會保留代表信任網頁元件設定的屬性。</p></td>
<td><p>通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServers</p></td>
<td><p>這個類別會保留 msRTCSIP-TrustedWebComponentServer 類別的多個實例，且不具備任何屬性本身。</p></td>
<td><p>通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UnifiedCommunications （已過時）</p></td>
<td><p>此輔助類別可 msRTCSIP-GlobalContainer 保留與整合通訊相關的屬性。</p></td>
<td><p>在 Lync Server 2010 中已過時。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponents</p></td>
<td><p>這個類別會保留網際網路 information Server （IIS）的服務控制 pointservice 控制點。 它會將伺服器識別為網頁元件伺服器。</p></td>
<td><p>通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsService</p></td>
<td><p>這個類別提供從特定的池中到該池將使用之網頁元件的關聯。</p></td>
<td><p>通訊伺服器2007中的新功能。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentSettings</p></td>
<td><p>此輔助類別可 msRTCSIP-WebComponents 保留代表網頁元件設定的屬性。</p></td>
<td><p>通訊伺服器2007中的新功能。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

