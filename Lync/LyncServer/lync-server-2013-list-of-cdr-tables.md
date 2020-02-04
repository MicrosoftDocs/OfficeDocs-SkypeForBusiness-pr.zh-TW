---
title: Lync Server 2013：CDR 表格清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0c620eaf6b54a89604071a18f445d20816178bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a>Lync Server 2013 中的 CDR 表格清單

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

[通話詳細資料錄製（CDR）] 資料庫架構由下清單格組成。

<div>

## <a name="static-tables"></a>靜態資料表


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 中的 CallPriorities 表格</a></p></td>
<td><p>儲存可能的通話優先順序清單，例如緊急、緊急、正常、非緊急及其他。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencejointimethresholds-table.md">Lync Server 2013 中的 ConferenceJoinTimeThresholds 表格</a></p></td>
<td><p>儲存 [會議加入時間摘要] 報告所使用的分類界限。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 中的 DeRegisterType 表格</a></p></td>
<td><p>儲存可能的使用者取消&quot;註冊原因（例如用戶端啟動、&quot; &quot;註冊到期、&quot; &quot;用戶端損毀&quot;等）清單。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialist-table.md">Lync Server 2013 中的 MediaList 表格</a></p></td>
<td><p>儲存可在資料庫中產生專案的媒體類型清單（例如，IM、音訊、影片和檔案傳輸）。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table.md">Lync Server 2013 中的 PurgeSettings 表格</a></p></td>
<td><p>儲存資訊，指定是否要從 CDR 資料庫自動刪除過時的呼叫詳細資料記錄（以及時間）。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-roles-table.md">Lync Server 2013 中的 Roles 表格</a></p></td>
<td><p>儲存可能的會議角色清單（例如，出席者與簡報者）。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-sipresponsemetadata-table.md">Lync Server 2013 中的 SIPResponseMetaData 表格</a></p></td>
<td><p>儲存 SIP 回應代碼清單，以及每個代碼的分類與定義。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a>支援表格


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a></p></td>
<td><p>儲存與在此資料庫中捕獲之資訊之通話所涉及之每個用戶端的用戶端（用戶端類型和版本號碼）。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表格</a></p></td>
<td><p>儲存在會議相關通話中使用的 ConferenceURIs 清單。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中的 ContentTypes 表格</a></p></td>
<td><p>儲存在對等通話和電話會議中使用的會話初始通訊協定（SIP）內容類型清單。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devices-table.md">Lync Server 2013 中的 Devices 表格</a></p></td>
<td><p>儲存裝置清單，包括其製造商、硬體版本及 MAC 位址。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的 Dialogs 表格</a></p></td>
<td><p>儲存資料庫中每個會話之對話方塊識別碼的相關資訊。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表格</a></p></td>
<td><p>儲存用於外部呼叫的邊緣伺服器清單。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的 Gateways 表格</a></p></td>
<td><p>儲存用於語音透過網際網路通訊協定（VoIP）通話的閘道清單。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中的 HardwareVersions 表格</a></p></td>
<td><p>儲存裝置的硬體版本清單（電話）。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中的 Manufacturers 表格</a></p></td>
<td><p>儲存裝置的製造商清單（電話）。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-table.md">Lync Server 2013 中的 Mcus 表格</a></p></td>
<td><p>儲存各種 A/V 會議伺服器及其 Uri 的相關資訊。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表格</a></p></td>
<td><p>儲存用於 VoIP 通話的中繼伺服器清單。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-phones-table.md">Lync Server 2013 中的 Phones 表格</a></p></td>
<td><p>儲存已歸檔或通話詳細資料之 VoIP 通話中所用的所有電話號碼。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 Pools 表格</a></p></td>
<td><p>儲存要捕獲 IM 訊息的 [池] 的名稱。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 表格</a></p></td>
<td><p>儲存通話中所涉及的伺服器名稱。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的 Tenants 表格</a></p></td>
<td><p>儲存目前部署所支援的租使用者。 企業使用者、同盟使用者、公用 IM 連線使用者和匿名使用者都有一些組建內部的租使用者。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表格</a></p></td>
<td><p>將使用者代理程式識別碼對應至代理程式的描述性名稱。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a></p></td>
<td><p>儲存參與此資料庫中記錄或封存之會話之使用者的使用者 Uri。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-userstatistics-table.md">Lync Server 2013 中的 UserStatistics 表格</a></p></td>
<td><p>儲存個別使用者使用系統的相關資訊。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a>適用于會議 CDR 記錄的表格


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-table.md">Lync Server 2013 中的 Conferences 表格</a></p></td>
<td><p>儲存已封存或記錄其詳細資料之所有會議的相關資訊，包括 ConferenceURI、開始和結束時間。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-table.md">Lync Server 2013 中的 ConferenceSessionDetails 表格</a></p></td>
<td><p>儲存每個 SIP 會議會話的相關資訊，包括開始和結束時間、使用者識別碼、回應代碼，以及每個會話的診斷 ID。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-focusjoinsandleaves-table.md">Lync Server 2013 中的 FocusJoinsAndLeaves 表格</a></p></td>
<td><p>儲存會議加入和離開的相關資訊，包括使用者的角色與用戶端版本。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcujoinsandleaves-table.md">Lync Server 2013 中的 McuJoinsAndLeaves 表格</a></p></td>
<td><p>儲存參與會議與使用者加入並離開時間的 A/V 會議伺服器資訊。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a>IM 會議中的訊息表格


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferencemessagecount-table.md">Lync Server 2013 中的 ConferenceMessageCount 表格</a></p></td>
<td><p>針對每個 IM 會議，儲存每位使用者所傳送的訊息數目。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-imreportsummary-table.md">Lync Server 2013 中的 IMReportSummary 表格</a></p></td>
<td><p>提供組織中的立即訊息會話的整體報告。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a>點對點工作階段的資料表


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 表格</a></p></td>
<td><p>儲存每個點對點工作階段的相關資訊，包括開始和結束時間、使用者識別碼、回應代碼，以及每個使用者的郵件數目。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-filetransfers-table.md">Lync Server 2013 中的 FileTransfers 表格</a></p></td>
<td><p>儲存檔案傳輸會話的相關資訊，包括檔案名與結果（接受、拒絕或取消）。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-table.md">Lync Server 2013 中的媒體資料表格</a></p></td>
<td><p>儲存點對點工作階段中所涉及之不同媒體類型的相關資訊。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a>VoIP 通話詳細資料的表格


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-voipdetails-table.md">Lync Server 2013 中的 VoipDetails 表格</a></p></td>
<td><p>針對每個雙方的 VoIP/PSTN 通話，儲存有關通話的資訊，例如 VoIP 電話的電話 ID、使用的閘道，以及哪個方已中斷連線。 參照<a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 資料表</a>取得呼叫開始/結束時間及回應碼。</p>
<div>

> [!NOTE]  
> 如果通話中有一方是 VoIP 使用者，或者如果是在通話中參與轉送伺服器，則會在此資料表中建立記錄。 在<A href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 的 SessionDetails 資料表</A>中，不涉及有關 VoIP/VoIP 通話的資訊。


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a>E9-1-1-1 通話審核的資料表


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-locations-table.md">Lync Server 2013 中的 Locations 表格</a></p></td>
<td><p>針對每個緊急通話（例如增強型9-1-1 （E9-1-1）通話），儲存通話的位置資訊。 參照<a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 資料表</a>取得呼叫開始/結束時間及回應碼。</p>
<div>

> [!NOTE]  
> 此表格僅包含 E9-1-1 通話的位置 blob。 參照 SessionDetails 資料表，取得有關通話的其他詳細資訊。


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a>疑難排解表格


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-application-table.md">Lync Server 2013 中的應用程式表</a></p></td>
<td><p>儲存有關在路由和連線中所涉及的 Lync Server 2013 中各種處理常式的資訊。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-calltype-table.md">Lync Server 2013 中的 CallType 表格</a></p></td>
<td><p>儲存有關通話類型的資訊，例如「音訊」、「立即訊息」、「音訊及視頻」和「應用程式共用」。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorcategory-table.md">Lync Server 2013 中的 ErrorCategory 表格</a></p></td>
<td><p>儲存每個 Microsoft Lync Server 2013 診斷分類的易記名稱。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errordef-table.md">Lync Server 2013 中的 ErrorDef 表格</a></p></td>
<td><p>儲存錯誤類型和其定義的相關資訊。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表格</a></p></td>
<td><p>儲存所發生錯誤的相關資訊。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-table.md">Lync Server 2013 中的 ProgressReport 表格</a></p></td>
<td><p>儲存有關 Lync Server 2013 程式中所涉及之各個步驟之進度報告的相關資訊。</p></td>
</tr>
</tbody>
</table>


下列清單中的表格是由 Lync Server 在內部使用。 本檔未說明其詳細資料。

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a>Lync Server 供內部使用的表格


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DbConfigDateTime</strong></p></td>
<td><p>僅供內部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>DbConfigInt</strong></p></td>
<td><p>僅供內部使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DbErrorMessage</strong></p></td>
<td><p>僅供內部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>前端表格</strong></p></td>
<td><p>僅供內部使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MSMQProcessing 資料表</strong></p></td>
<td><p>僅供內部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>僅供內部使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Syndicators 資料表</strong></p></td>
<td><p>僅供內部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>SyndicatorsTenantMap 資料表</strong></p></td>
<td><p>僅供內部使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>工作表</strong></p></td>
<td><p>僅供內部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserStatistics</strong></p></td>
<td><p>僅供內部使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UsageSummary_UQ</strong></p></td>
<td><p>僅供內部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>UsageSummary</strong></p></td>
<td><p>僅供內部使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>僅供內部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>僅供內部使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>時區</strong></p></td>
<td><p>僅供內部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>FailureSummary_UQ</strong></p></td>
<td><p>僅供內部使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FailureSummary</strong></p></td>
<td><p>僅供內部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerSummary</strong></p></td>
<td><p>僅供內部使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagMetaData</strong></p></td>
<td><p>僅供內部使用。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

