---
title: Lync Server 2013：使用者活動報告
description: Lync Server 2013：使用者活動報告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Activity Report
ms:assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558638(v=OCS.15)
ms:contentKeyID: 48183862
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e959020e6ace6c72ecd570039d30a9ecc174c82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569829"
---
# <a name="user-activity-report-in-lync-server-2013"></a>Lync Server 2013 中的使用者活動報告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-02-27_

「使用者活動報告」提供了指定期間內使用者執行之對等及會議工作階段的詳細清單。不同於多數「監控報告」，「使用者活動報告」將每通通話牽繫到個別使用者。例如，對等工作階段會指定發話者 (來源使用者) 及受話者 (目標使用者) 的 SIP URI。如展開關於會議的資訊，則會顯示所有會議參與者及其在該會議中所扮演角色的清單。

「使用者活動報告」有時稱為「服務台」報告。這是因為此報告常被服務台人員用來擷取特定使用者的工作階段資訊。在 [使用者 URI 首碼] 方塊中輸入使用者的 SIP URI，即可篩選個別使用者所接收或發出的通話。

如果您這麼做，使用者活動報告會傳回其 SIP URI 以指定字串開頭的任何使用者資訊。 例如，如果您在 [URI] 方塊中輸入 **ken** ，使用者活動報告就會找到 **ken**。Myer@litwareinc.com。 不過，它也會找到下列使用者：

  - **ken**azi@litwareinc.com

  - **ken**burg@litwareinc.com

  - **Ken**。Sanchez@litwareinc.com

  - **Ken**nedy@litwareinc.com

為了確保只會傳回 Ken Myer 的資訊，請在搜尋方塊中輸入他的完整 URI (Ken.Myer@litwareinc.com) 或至少有足夠類型的 Ken URI，以唯一地區分開他與組織中的其他使用者。 例如：

Ken.my

<div>

## <a name="to-access-the-user-activity-report"></a>存取使用者活動報告

從「監控報告」首頁可存取「使用者活動報告」。 您也可以在 [ [Lync Server 2013] 的 [IP 電話清查] 報告](lync-server-2013-ip-phone-inventory-report.md)上，按一下 [使用者] URI 度量，以到達 [使用者活動] 報告。 從「使用者活動報告」中，按一下 [會議 URI] (針對會議) 會移至「會議詳細資料報告」。 同樣地，按一下對等通話的詳細資料度量，會帶您前往 [Lync Server 2013 中的 Peer-to-Peer 會話詳細資料包告](lync-server-2013-peer-to-peer-session-detail-report.md)。

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a>充分運用使用者活動報告

雖然「使用者活動報告」中有許多有用的資訊，但是有時候很難找到所需的資訊。 例如，在指定期間內，組織中發生的所有使用者活動都會包含在使用者活動報告中;這表示在報表內，會有一些使用者實際使用 Microsoft Lync Server 2013 的相關資訊。

<div>


> [!WARNING]  
> 從技術上而言，有些使用者活動可能會 unrecorded：雖然 Lync Server 盡力保留所有電話通話的資訊，但只要該呼叫的相關資訊未寫入資料庫中，就可以進行通話。 Lync Server 的設計目的是要提供極好的準確性，但不一定要瞭解如何使用 Lync Server 2013。  (不保證所有通話呼叫的100% 的事實，說明為何 Lync Server monitoring 不應該當作帳單系統使用。 ) <BR>第二，「監控報告」中的報告最多僅可顯示 1,000 筆記錄。所以，取決於使用者活動的多寡及工作期間，您的查詢可能不會傳回資料庫中所有實際儲存的資料。



</div>

  - 在此期間內哪些使用者確實使用系統？

  - 在此期間內我的哪些使用者最為活躍？

  - 通話最多的使用者也是參與最多立即訊息工作階段的使用者嗎？

如果您需要回答此類問題，可以將「監控報告」擷取的資料匯出到 Excel 試算表。 然後使用該試算表及 (或) 逗點分隔值檔案，以「使用者活動報告」無法做到的方式來分析資料。 例如，假設您已將報告資料匯出到 Excel，再儲存為逗點分隔值檔案。 在該點，您可以匯入資料。CSV 檔案至 Windows PowerShell，其使用類似如下的命令：

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

在匯入資料後，您就可以使用簡易的 Windows PowerShell 命令，協助您回答問題。 例如，以下命令會傳回至少在一個工作階段中擔任「來源使用者」的唯一使用者清單：

    $x | Group-Object "From user" | Select Name | Sort-Object Name

換句話說：

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

此命令會列出唯一使用者 (根據他們參與的工作階段總數)：

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

這會傳回如下的資訊：

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

此命令會將報告的工作階段限制為包含音訊形式的工作階段：

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

如果將滑鼠停留在報告上顯示的任何 [診斷識別碼] 上，說明該識別碼的工具提示就會顯示。

</div>

<div>

## <a name="filters"></a>篩選

篩選可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。例如，使用者活動報告可讓您依據活動類型之類的項目 (也就是，對等工作階段或會議工作階段)，或是依使用者的 SIP 位址 (可讓您檢視一位使用者的活動)，篩選傳回的資料。您也可以選擇資料的分組方式。在這種情況下，使用量會按照小時、日、星期或月加以分組。

下表列出您可以用於使用者活動報告的篩選。

### <a name="user-activity-report-filters"></a>使用者活動報告篩選

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>From</strong></p></td>
<td><p>時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/17/12012 1:00 PM</p>
<p>如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>7/17/12012</p>
<p>若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</p>
<p>7/13/2012</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/17/12012 1:00 PM</p>
<p>如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>7/17/12012</p>
<p>若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</p>
<p>7/13/2012</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>活動類型</strong></p></td>
<td><p>活動的類型。請選取下列其中一項：</p>
<ul>
<li><p>一切</p></li>
<li><p>對等</p></li>
<li><p>會議</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>形態</strong></p></td>
<td><p>您可以使用的模態視選取活動類型而定。 如果活動類型為 Peer-to-Peer，您可以選取 [IM];檔案傳輸;應用程式共用;口音或像是模態的影片。</p>
<p>如果活動類型為 [會議]，您可以選取 [IM 電話] 會議;Web 會議;應用程式共用;語音/視訊會議;或電話語音會議。</p></td>
</tr>
<tr class="odd">
<td><p><strong>工作階段類別</strong></p></td>
<td><p>指出有疑問的活動為成功或失敗。請選取下列其中一項：</p>
<ul>
<li><p>一切</p></li>
<li><p>成功</p></li>
<li><p>預期的失敗</p></li>
<li><p>未預期的失敗</p></li>
</ul>
<p>&quot;預期的失敗 &quot; 是預期會發生的失敗; 例如，如果使用者已將其狀態設為 [請勿打擾]，則您預期該使用者的任何呼叫都會失敗。 未 &quot; 預期的失敗 &quot; 是指出現在其他狀況良好之系統上的失敗。 例如，當發話者處於保留狀態時，不應掛斷通話。 當發生此狀況時，會將其標幟為未預期的失敗。</p></td>
</tr>
<tr class="even">
<td><p><strong>使用者 URI 字首</strong></p></td>
<td><p>使用者的 SIP 位址。如果只要檢視使用者 Ken Myer 的記錄，則需要輸入 Ken Myer 的 SIP 位址。例如：</p>
<p>sip:kenmyer@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>對等工作階段的計量

下表列出使用者活動報告中提供的對等工作階段資訊 (也就是只有兩個參與者的工作階段)。

### <a name="metrics-for-peer-to-peer-sessions"></a>對等工作階段的計量

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>姓名</th>
<th>可以排序這個項目嗎？</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Detail</strong></p></td>
<td><p>否</p></td>
<td><p>當您按一下此項目，報告即顯示所選取之工作階段的對等工作階段詳細資料報告。</p></td>
</tr>
<tr class="even">
<td><p><strong>來源使用者</strong></p></td>
<td><p>是</p></td>
<td><p>啟動對等工作階段之使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>目標使用者</strong></p></td>
<td><p>是</p></td>
<td><p>參與對等工作階段之使用者的 SIP 位址。</p></td>
</tr>
<tr class="even">
<td><p><strong>方式</strong></p></td>
<td><p>是</p></td>
<td><p>工作階段中所使用的通訊類型。例如 IM、音訊或檔案傳輸。</p></td>
</tr>
<tr class="odd">
<td><p><strong>邀請時間</strong></p></td>
<td><p>是</p></td>
<td><p>初始邀請加入對等工作階段時，傳送邀請的日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>回應時間</strong></p></td>
<td><p>是</p></td>
<td><p>&quot;至 &quot; 使用者接受會話邀請的日期和時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>結束時間</strong></p></td>
<td><p>是</p></td>
<td><p>對等工作階段結束的日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>是</p></td>
<td><p>附加在 SIP 訊息中的唯一識別碼 (採用 ms-diagnostics 標頭的格式)，常可以在疑難排解錯誤時提供實用的資訊。診斷標頭為選用 (也可能有 SIP 工作階段不包含這些標頭)。只有發生特定問題的工作階段才會回報診斷識別碼。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>會議工作階段的計量

下表列出使用者活動報告中提供的會議工作階段資訊 (也就是有三個以上參與者的工作階段)。

### <a name="metrics-for-conferencing-sessions"></a>會議工作階段的計量

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>姓名</th>
<th>可以排序這個項目嗎？</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>會議 URI</strong></p></td>
<td><p>是</p></td>
<td><p>唯一會議識別碼。 當您按一下此項目，報告即顯示所選取之工作階段的會議詳細資料報告。 當您展開此項目，報告會顯示會議參與者的相關資訊。 如需詳細資訊，請參閱 &quot; 本主題稍後的會議參與者的計量 &quot; 區一節。</p></td>
</tr>
<tr class="even">
<td><p><strong>召集人</strong></p></td>
<td><p>是</p></td>
<td><p>召開會議之使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>集區</strong></p></td>
<td><p>是</p></td>
<td><p>會議中使用的 Edge Server 名稱 (若有的話)。</p></td>
</tr>
<tr class="even">
<td><p><strong>開始時間</strong></p></td>
<td><p>是</p></td>
<td><p>會議開始的日期與時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>結束時間</strong></p></td>
<td><p>是</p></td>
<td><p>會議結束的日期與時間。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a>會議參與者的計量

下表列出使用者活動報告中為會議每位參與者提供的資訊。

### <a name="metrics-for-conference-participants"></a>會議參與者的計量

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>姓名</th>
<th>可以排序這個項目嗎？</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Role</strong></p></td>
<td><p>否</p></td>
<td><p>使用者的會議角色 (例如簡報者)。</p></td>
</tr>
<tr class="even">
<td><p><strong>參與者</strong></p></td>
<td><p>否</p></td>
<td><p>使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>連線能力</strong></p></td>
<td><p>否</p></td>
<td><p>網路連線類型。 例如， &quot; 來自內部連線 &quot; 或 &quot; 從 PSTN &quot; 針對撥號使用者。</p></td>
</tr>
<tr class="even">
<td><p><strong>加入時間</strong></p></td>
<td><p>否</p></td>
<td><p>使用者加入會議的日期與時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>離開時間</strong></p></td>
<td><p>否</p></td>
<td><p>使用者離開會議的日期與時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>否</p></td>
<td><p>附加在 SIP 訊息中的唯一識別碼 (採用 ms-diagnostics 標頭的格式)，常可以在疑難排解錯誤時提供實用的資訊。診斷標頭為選用 (也可能有 SIP 工作階段不包含這些標頭)。只有發生特定問題的工作階段才會回報診斷識別碼。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

