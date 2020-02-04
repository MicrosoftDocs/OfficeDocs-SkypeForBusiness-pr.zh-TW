---
title: Lync Server 2013：回應群組通話清單報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Call List Report
ms:assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615443(v=OCS.15)
ms:contentKeyID: 48184954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94c06e2029ca1a22a0a9f73249cff3251e2fcbc2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-call-list-report-in-lync-server-2013"></a>Lync Server 2013 中的 [回應群組通話清單] 報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

回應群組應用程式提供一種方式，讓 Microsoft Lync Server 2013 根據所撥打的號碼，以及在來電者對一系列問題的回應，來應答並傳送電話撥打電話。 通常，回應群組通話不會傳送給個別人，而是傳送給稱為「代理人」群組的人員小組。 例如，如果某人撥打電話號碼給您的技術支援人員，Lync Server 2013 可以自動將該呼叫路由到第一個可用的技術支援人員代理程式。 或者，如果您遇到硬體問題，Lync Server 可能會提出一系列問題（「按1）。 如果您遇到軟體問題，請按2。 如果您有網路問題，請按3。）然後根據這些問題的答案，將呼叫路由到最合適的技術支援人員。

[回應群組通話清單] 報告代表在指定的一段時間內，以及針對特定通話類型進行通話的集合。 回應群組使用方式報告（必須先開啟，才能開啟 [回應群組通話清單] 報告）可識別下列通話類型：

  - **已接收來電**。 所有回應群組應用程式實例接收到的呼叫總數。

  - **成功的通話**。 回應群組應用程式所挑選的通話總數目。

  - 已**提供來電**。 傳送給回應群組代理程式的呼叫總數。

  - 已**接聽通話**。 已由回應群組代理程式實際接聽的通話總數目。

  - 已放棄通話的百分比。 回應群組應用程式接收，但沒有由代理程式接聽的通話百分比。 此值的計算方法是從收到的電話減去接聽的通話，然後根據收到的通話數來除以該值。 例如，如果您收到10個通話，且已接聽7個，您會從10減去7，然後離開3個未回復的通話。 這個值將除以10，從而讓您放棄通話百分比30%。

  - **轉接來電**。 由於佇列超時或佇列溢出而轉移之回應群組通話的總數。

<div>

## <a name="accessing-the-response-group-call-list-report"></a>存取回應群組通話清單報告

只有在[Lync Server 2013 的 [回應群組使用方式] 報告中](lync-server-2013-response-group-usage-report.md)，按一下下列其中一個度量，才能存取 [回應] 群組通話清單報告：

  - 已接聽通話

  - 成功的通話

  - 已提供通話

  - 已接聽通話

  - 已轉移通話

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a>充分利用 [回應群組通話清單] 報告

[回應群組通話清單] 報告可讓您將顯示的資料限制在涉及特定回應群組工作流程的通話中。 若要這樣做，您必須在 [工作流程 URI] 方塊中輸入工作流程 URI （工作流程的 SIP 位址）。 不過，您必須能夠看到 [工作流程 URI] 方塊，才能執行這項作業。 若要顯示 [回應群組通話清單] 報告的篩選選項，請按一下報表視窗左上角的 [顯示/隱藏參數] 按鈕。

請注意，如果您將滑鼠放在其中一個指標中，回應群組通話清單不會顯示回應代碼或診斷 ID 的相關資訊。 如果您需要更多相關資訊，您可以記下回應代碼和/或診斷 ID，然後在[Lync Server 2013 的 [熱門失敗] 報告](lync-server-2013-top-failures-report.md)中搜尋這些值。

這個問題就像這樣：「哪個個別工作流程收到了最多通話？」，您可以執行下列動作：

1.  在 [回應群組使用方式] 報告中，設定所需的時間週期，然後按一下 [接收的通話統計]。 這會開啟 [回應群組通話清單] 報告。

2.  匯出 [回應群組通話清單] 報告上顯示的資料。 例如，您可能會將資料匯出為 Microsoft Excel 格式，然後使用 Excel 將這些資料轉換成逗號分隔值檔案。

3.  使用 Windows PowerShell 執行分析。

例如，如果您已將資料儲存到名為\\C：資料\\回應\_群組\_通話\_清單\_的檔案 .csv，您就可以使用下列命令，為報告中列出的每個工作流程傳回已接收的通話總數：

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

這將會像這樣的資訊：

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

</div>

<div>

## <a name="filters"></a>濾鏡

篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。 下表列出可與 [回應群組通話清單] 報告搭配使用的篩選。

### <a name="response-group-call-list-report-filters"></a>回應群組通話清單報表篩選

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
<p>7/7/2012 1:00 PM</p>
<p>如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。 若要依天查看資料，只需輸入日期：</p>
<p>7/7/2012</p>
<p>若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>周數總是從星期日到星期六執行。</p></td>
</tr>
<tr class="even">
<td><p><strong>自</strong></p></td>
<td><p>時間範圍的結束日期/時間。 若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。 若要依天查看資料，只需輸入日期：</p>
<p>7/7/2012</p>
<p>若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>周數總是從星期日到星期六執行。</p></td>
</tr>
<tr class="odd">
<td><p><strong>工作流程 URI</strong></p></td>
<td><p>可讓您將傳回的資料限制在指定的回應群組工作流程中。 若要使用這個篩選器，請輸入工作流程 SIP 位址。 例如：</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
<tr class="even">
<td><p><strong>撥</strong></p></td>
<td><p>您可以選取下列其中一種通話類型：</p>
<ul>
<li><p>已接聽通話</p></li>
<li><p>成功的通話</p></li>
<li><p>已提供通話</p></li>
<li><p>已接聽通話</p></li>
<li><p>已轉移通話</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

下表列出回應群組應用程式接收之每個通話的回應群組通話清單報告中所提供的資訊。

### <a name="response-group-call-list-report-metrics"></a>回應群組通話清單報告度量單位

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
<td><p><strong>呼叫</strong></p></td>
<td><p>否</p></td>
<td><p>來電者的 SIP 位址。</p></td>
</tr>
<tr class="even">
<td><p><strong>工作流程</strong></p></td>
<td><p>否</p></td>
<td><p>回應群組工作流程的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>開始時間</strong></p></td>
<td><p>否</p></td>
<td><p>通話開始的日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>結束時間</strong></p></td>
<td><p>否</p></td>
<td><p>通話結束的日期和時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>回應代碼</strong></p></td>
<td><p>否</p></td>
<td><p>在會話失敗時傳送 SIP 回應代碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>否</p></td>
<td><p>附加至 SIP 訊息的唯一識別碼（ms diagnostics 標頭形式），通常可在疑難排解錯誤中提供有用的資訊。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

