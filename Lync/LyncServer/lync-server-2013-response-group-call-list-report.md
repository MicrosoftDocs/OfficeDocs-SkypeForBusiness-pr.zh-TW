---
title: Lync Server 2013：回應群組通話清單報告
description: Lync Server 2013：回應群組通話清單報告。
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
ms.openlocfilehash: 5ffe4b62534d4849b4f0cdade9aeef8be5d69178
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560879"
---
# <a name="response-group-call-list-report-in-lync-server-2013"></a>Lync Server 2013 的回應群組通話清單報告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

回應群組應用程式提供一種方式，讓 Microsoft Lync Server 2013 根據撥打的號碼來接聽和路由通話，也可以在來電者對一系列問題的回應中作出通話。 系統通常不會將回應群組通話路由傳送給個人，而是將通話路由傳送給稱為代理群組的一組人員。 例如，如果有人呼叫您的技術支援人員的電話號碼，Lync Server 2013 可自動將該呼叫路由傳送至第一個可用的服務台代理。 或者，如果您有硬體問題，Lync Server 可能會詢問一系列的問題 ( "請按1。 軟體問題請按 2。 如果您有網路問題，請按3。」) ，然後根據這些問題的答案，將通話路由傳送給最適當的服務台代理程式。

回應群組通話清單報告代表指定的一段時間內和指定的通話類型所撥打的來電集合。 [回應群組使用量] 報告 (，必須先開啟此報告，才能開啟回應群組通話清單報告) 識別下列呼叫類型：

  - **接收的通話**。 回應群組應用程式的所有執行個體接收的通話總數。

  - **成功的通話**。 回應群組應用程式挑選的呼叫總數。

  - **提供的通話**。轉接至回應群組代理程式的通話總數。

  - **接聽的通話**。回應群組代理程式實際接聽的通話總數。

  - 放棄的通話百分比。 回應群組應用程式已接收，但代理從未接聽的通話百分比。 這是從接收的通話減掉接聽的通話，再除以接收的通話數，所計算出來的值。 例如，如果您接收到 10 次通話，並接聽 7 次，就要從 10 減掉 7，剩下 3 次未接聽的通話。 該值再除以 10，則得到的放棄通話百分比為 30%。

  - **轉接的通話**。 因為佇列逾時或佇列溢位而轉接的回應群組通話總數。

<div>

## <a name="accessing-the-response-group-call-list-report"></a>存取回應群組通話清單報告

按一下下列其中一個在 [Lync Server 2013 中的 [回應群組使用方式] 報告中](lync-server-2013-response-group-usage-report.md)找到的計量，即可存取回應群組通話清單報告：

  - 接收的通話

  - 成功的通話

  - 提供的通話

  - 接聽的通話

  - 轉接的通話

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a>充分利用回應群組通話清單報告

回應群組通話清單報告可讓您將顯示的資料限制為涉及特定回應群組工作流程的呼叫。 若要這麼做，您必須在 [工作流程 URI] 方塊中輸入工作流程 URI (工作流程的 SIP 位址) 。 不過，您必須確實能夠看到工作流程 URI 方塊，才能執行這項作業。 若要顯示回應群組通話清單報告的篩選選項，請在報表視窗的左上方，按一下 [顯示/隱藏參數] 按鈕。

請注意，回應群組通話清單不會顯示回應碼或診斷識別碼的資訊（如果您將滑鼠放在其中一個計量中）。 如果您需要詳細資訊，請注意回應碼和/或診斷識別碼，然後在 [Lync Server 2013 的 [最大失敗] 報告中](lync-server-2013-top-failures-report.md)搜尋這些值。

這類問題：「哪些個別工作流程接收最多通話？」，您可以執行下列作業：

1.  在 [回應群組使用量] 報告上，設定所需的時間週期，然後按一下 [接收的通話計數]。 這會開啟回應群組通話清單報告。

2.  匯出回應群組通話清單報告上顯示的資料。 例如，您可以將 Microsoft Excel 格式的資料匯出，然後使用 Excel 將該資料轉換成逗號分隔值檔案。

3.  使用 Windows PowerShell 執行分析。

例如，如果您已將資料儲存到名為 C： \\ data \\ Response \_ Group \_ Call \_ ListReport.csv 的檔案 \_ 中，您就可以使用下列命令，為報告中列出的每個工作流程傳回已接收的呼叫總數：

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

這會類似如下的資訊：

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 下表列出您可以搭配回應群組通話清單報告使用的篩選器。

### <a name="response-group-call-list-report-filters"></a>回應群組通話清單報告篩選器

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
<p>7/7/2012 1:00 PM</p>
<p>如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>7/7/2012</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>7/3/2012</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>7/7/2012</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>7/3/2012</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>工作流程 URI</strong></p></td>
<td><p>可讓您將傳回的資料限定在指定的回應群組工作流程。若要使用此篩選，請輸入工作流程 SIP 位址。例如：</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
<tr class="even">
<td><p><strong>調用</strong></p></td>
<td><p>您可以選取下列其中一種通話類型：</p>
<ul>
<li><p>接收通話</p></li>
<li><p>通話成功</p></li>
<li><p>提供通話</p></li>
<li><p>接聽的通話</p></li>
<li><p>轉接通話</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

下表列出回應群組應用程式每次呼叫的回應群組通話清單報告中提供的資訊。

### <a name="response-group-call-list-report-metrics"></a>回應群組通話清單報告計量

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
<td><p><strong>Caller</strong></p></td>
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
<td><p>通話的開始日期與時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>結束時間</strong></p></td>
<td><p>否</p></td>
<td><p>通話的結束日期和時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>回應碼</strong></p></td>
<td><p>否</p></td>
<td><p>會話失敗時傳送的 SIP 回應碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>否</p></td>
<td><p>附加至 SIP 郵件（通常會在疑難排解錯誤中提供有用資訊) ）的表單中的唯一識別碼 (。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

