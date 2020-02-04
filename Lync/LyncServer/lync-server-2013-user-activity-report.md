---
title: Lync Server 2013：使用者活動報告
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
ms.openlocfilehash: 583c647ac3cdab290f1833539abbbd033ea89410
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-activity-report-in-lync-server-2013"></a>Lync Server 2013 中的使用者活動報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-02-27_

[使用者活動] 報告提供您在指定時段內由使用者執行之對等與會議會話的詳細清單。 與許多監視報表不同，使用者活動報告會將每個呼叫與個別使用者相互結合。 例如，點對點工作階段會指定啟動通話的人員的 SIP Uri （來自使用者）及呼叫者（To 使用者）。 如果您展開會議的資訊，您會看到所有會議參與者的清單，以及他們為該會議所擔任的角色。

使用者活動報告有時稱為「問訊台」報告。 這是因為技術支援人員經常會使用報告來取得特定使用者的會話資訊。 您只要在 [使用者 URI 首碼] 方塊中輸入使用者的 SIP URI，就可以篩選給個別使用者所撥或進行的通話。

如果您這樣做，使用者活動報告會會傳回其 SIP URI 以指定字串開頭的任何使用者資訊。 例如，如果您在 [URI] 方塊中輸入**ken** ，使用者活動報告會會找到**ken**。Myer@litwareinc.com。 不過，它也會尋找這些使用者：

  - **ken**azi@litwareinc.com

  - **ken**burg@litwareinc.com

  - **Ken**。Sanchez@litwareinc.com

  - **Ken**nedy@litwareinc.com

若要確保傳回 Ken Myer 的資訊，請在 [搜尋] 方塊中輸入他的完整 URI （Ken.Myer@litwareinc.com），或是至少要將其與您組織中的其他使用者區分開來。 例如：

Ken.my

<div>

## <a name="to-access-the-user-activity-report"></a>存取使用者活動報告

使用者活動報告是從 [監控報告] 首頁存取。 您也可以按一下 [ [Lync Server 2013] 的 [IP 電話清點] 報告中](lync-server-2013-ip-phone-inventory-report.md)的使用者 URI 躍點數，以取得使用者活動報告。 在 [使用者活動] 報告中，按一下會議 URI （適用于會議）會將您帶到會議詳細資料包告。 同樣地，按一下對等通話的詳細資料規格會將您帶到[Lync Server 2013 的點對點工作階段詳細資料包告](lync-server-2013-peer-to-peer-session-detail-report.md)。

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a>充分運用使用者活動報告

雖然使用者活動報告中有許多有用的資訊，但有時可能難以找出該資訊。 例如，在指定期間內，您組織中發生的所有使用者活動，都會包含在使用者活動報告中;也就是說，在報表中，[隱藏] 是哪些使用者以某種方式實際使用 Microsoft Lync Server 2013 的相關資訊。

<div>


> [!WARNING]  
> 從技術角度來看，有些使用者的活動可能會 unrecorded：當 Lync Server 努力保留所有電話通話的相關資訊時，就可以進行通話，而不需要將該通話寫入資料庫的相關資訊。 Lync Server 的設計目的是提供極其精確的功能，但不一定能完全瞭解 Lync Server 2013 的使用方式。 （不保證所有通話的100% 都已記錄，說明為什麼 Lync Server monitoring 不應該用來做為帳單系統）。<BR>第二，監視報告報告最多隻能顯示1000記錄。 根據您所擁有的使用者活動數量而定，這表示您的查詢可能不會傳回實際儲存在資料庫中的所有資料。



</div>

  - 在此期間實際使用系統的使用者是哪一種？

  - 在此期間，哪些使用者是最活躍的？

  - 使用者是否也能撥打電話至最常接聽的訊息？

如果您需要回答如下所示的問題，您可以將監控報告所檢索的資料匯出至 Excel 試算表。 接著，您可以使用該試算表和/或逗號分隔值檔案，以使用者活動報告的方式來分析資料。 例如，假設您已將報表資料匯出至 Excel，然後匯出為逗號分隔值檔案。 在該位置，您可以匯入資料。在 Windows PowerShell 中使用類似以下的命令來執行 CSV 檔案：

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

匯入資料之後，您就可以使用簡單的 Windows PowerShell 命令來協助回答您的問題。 例如，此命令會傳回至少在一個會話中作為「寄件者」的唯一使用者清單：

    $x | Group-Object "From user" | Select Name | Sort-Object Name

換句話說：

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

這個命令會列出唯一的使用者（根據其參與的會話總數）：

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

傳回如下所示的資料：

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

這個命令會將報告的會話限制為以模態形式包含的音訊：

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

如果您將滑鼠放在報表上顯示的任何診斷 ID 上，系統會顯示描述該識別碼的工具提示。

</div>

<div>

## <a name="filters"></a>濾鏡

篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。 例如，使用者活動報告可讓您根據活動類型（也就是點對點工作階段或會議會話）或使用者的 SIP 位址（可讓您查看一位使用者的活動）來篩選傳回的資料。 您也可以選擇分組資料的方式。 在這種情況下，使用方式會依小時、日、周或月分組。

下表列出可與使用者活動報告搭配使用的篩選。

### <a name="user-activity-report-filters"></a>使用者活動報表篩選

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>從</strong></p></td>
<td><p>時間範圍的開始日期/時間。 若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</p>
<p>7/17/12012 1:00 PM</p>
<p>如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。 若要依天查看資料，只需輸入日期：</p>
<p>7/17/12012</p>
<p>若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</p>
<p>7/13/2012</p>
<p>周數總是從星期日到星期六執行。</p></td>
</tr>
<tr class="even">
<td><p><strong>自</strong></p></td>
<td><p>時間範圍的結束日期/時間。 若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</p>
<p>7/17/12012 1:00 PM</p>
<p>如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。 若要依天查看資料，只需輸入日期：</p>
<p>7/17/12012</p>
<p>若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</p>
<p>7/13/2012</p>
<p>周數總是從星期日到星期六執行。</p></td>
</tr>
<tr class="odd">
<td><p><strong>活動類型</strong></p></td>
<td><p>活動類型。 選取下列其中一項：</p>
<ul>
<li><p>同時</p></li>
<li><p>對等</p></li>
<li><p>會議</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>模態</strong></p></td>
<td><p>視選取活動類型而定，您可以使用哪些模態。 如果活動類型是對等，您可以選取 [IM];檔案傳輸;應用程式共用;語音或 [影片] 做為模態。</p>
<p>如果活動類型是 [會議]，您可以選取 [IM 電話會議];Web 會議;應用程式共用;語音/視訊會議;或電話會議。</p></td>
</tr>
<tr class="odd">
<td><p><strong>會話類別</strong></p></td>
<td><p>指出問題中的活動是否已成功或失敗。 選取下列其中一項：</p>
<ul>
<li><p>同時</p></li>
<li><p>成功案例</p></li>
<li><p>預期失敗</p></li>
<li><p>意外失敗</p></li>
</ul>
<p>&quot;預期的失敗&quot;是預期發生的失敗;例如，如果使用者將自己的狀態設為 [請勿打擾]，您預期該使用者的任何呼叫都會失敗。 發生&quot;意外的&quot;失敗，就是看起來像是其他健康的系統。 例如，如果來電者停留在 [保留] 上，就不應該終止通話。 如果發生這種情況，就會將它標記為未預期的失敗。</p></td>
</tr>
<tr class="even">
<td><p><strong>使用者 URI 首碼</strong></p></td>
<td><p>使用者的 SIP 位址。 若要只針對使用者 Ken Myer 查看記錄，您必須輸入 Ken Myer 的 SIP 位址。 例如：</p>
<p>sip:kenmyer@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>點對點工作階段的度量單位

下表列出點對點工作階段的使用者活動報告中所提供的資訊（也就是只涉及兩個參與者的會話）。

### <a name="metrics-for-peer-to-peer-sessions"></a>點對點工作階段的度量單位

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>您可以針對此專案進行排序嗎？</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>具體</strong></p></td>
<td><p>否</p></td>
<td><p>當您按一下此專案時，報告會顯示所選會話的點對點工作階段詳細資料包告。</p></td>
</tr>
<tr class="even">
<td><p><strong>從使用者</strong></p></td>
<td><p>是</p></td>
<td><p>啟動點對點工作階段之使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>給使用者</strong></p></td>
<td><p>是</p></td>
<td><p>加入點對點工作階段之使用者的 SIP 位址。</p></td>
</tr>
<tr class="even">
<td><p><strong>形式</strong></p></td>
<td><p>是</p></td>
<td><p>會話中使用的通訊類型。 例如，IM、音訊或檔案傳輸。</p></td>
</tr>
<tr class="odd">
<td><p><strong>邀請時間</strong></p></td>
<td><p>是</p></td>
<td><p>開始加入點對點工作階段的初始邀請的日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>回應時間</strong></p></td>
<td><p>是</p></td>
<td><p>使用者接受會話邀請的日期和時間&quot; &quot;</p></td>
</tr>
<tr class="odd">
<td><p><strong>結束時間</strong></p></td>
<td><p>是</p></td>
<td><p>點對點工作階段結束的日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>是</p></td>
<td><p>附加至 SIP 訊息的唯一識別碼（ms diagnostics 標頭形式），通常可在疑難排解錯誤中提供有用的資訊。 診斷標頭是可選項（有可能是不包含這些標頭的 SIP 會話），而且只會針對遇到某種問題的會話報告診斷 Id。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>會議會話的度量單位

下表列出會議會話的使用者活動報告中所提供的資訊（也就是與三個或更多參與者相關的會話）。

### <a name="metrics-for-conferencing-sessions"></a>會議會話的度量單位

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>您可以針對此專案進行排序嗎？</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>會議 URI</strong></p></td>
<td><p>是</p></td>
<td><p>唯一的會議識別碼。 當您按一下此專案時，報告會顯示所選會話的會議詳細資料包告。 展開此專案時，報告會顯示會議參與者的相關資訊。 如需詳細資訊， &quot;請參閱本主題&quot;稍後的會議參與者的度量資料一節。</p></td>
</tr>
<tr class="even">
<td><p><strong>召集人</strong></p></td>
<td><p>是</p></td>
<td><p>組織會議的使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>集區</strong></p></td>
<td><p>是</p></td>
<td><p>在會議中使用的邊緣伺服器（如果有的話）的名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>開始時間</strong></p></td>
<td><p>是</p></td>
<td><p>會議開始的日期和時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>結束時間</strong></p></td>
<td><p>是</p></td>
<td><p>會議結束的日期和時間。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a>會議參與者的度量單位

下表列出使用者活動報告中提供的資訊，提供給會議中的每個參與者。

### <a name="metrics-for-conference-participants"></a>會議參與者的度量單位

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>您可以針對此專案進行排序嗎？</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>角色</strong></p></td>
<td><p>否</p></td>
<td><p>使用者的會議角色（例如，簡報者）。</p></td>
</tr>
<tr class="even">
<td><p><strong>參加</strong></p></td>
<td><p>否</p></td>
<td><p>使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>連通</strong></p></td>
<td><p>否</p></td>
<td><p>網路連線類型。 例如&quot;，內部連線&quot;的內部或&quot;撥入使用者&quot;的 PSTN。</p></td>
</tr>
<tr class="even">
<td><p><strong>加入時間</strong></p></td>
<td><p>否</p></td>
<td><p>使用者加入會議的日期和時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>休假時間</strong></p></td>
<td><p>否</p></td>
<td><p>使用者離開會議的日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>否</p></td>
<td><p>附加至 SIP 訊息的唯一識別碼（ms diagnostics 標頭形式），通常可在疑難排解錯誤中提供有用的資訊。 診斷標頭是可選項（有可能是不包含這些標頭的 SIP 會話），而且只會針對遇到某種問題的會話報告診斷 Id。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

