---
title: Lync Server 2013： 回應群組通話清單報告
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
ms.openlocfilehash: 0b9ec44aa0b4c6063dd6c0a3cf1ae9e5b0c10356
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-call-list-report-in-lync-server-2013"></a>Lync Server 2013 中的回應群組通話清單報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-22_

回應群組應用程式提供方法讓 Microsoft Lync Server 2013 來接聽和路由電話上所撥打的號碼，並選擇性地在一系列的問題的發話者的回覆。 系統通常不會將回應群組通話路由傳送給個人，而是將通話路由傳送給稱為代理群組的一組人員。 例如，如果某人撥打的電話號碼為您的服務台，Lync Server 2013 可以自動路由傳送該呼叫的第一個可用的說明 desk 代理程式。 或者，Lync Server 可能會要求一系列的問題 (「 按下 1 如果您有硬體問題。 軟體問題請按 2。 按 3 如果您有網路問題 」）。然後將呼叫路由至最適當說明支援工程師的代理程式根據這些問題的答案。

回應群組通話清單報告代表一群通話所做的一段時間的時間與指定類型的呼叫。 回應群組使用量報告 （其必須先開啟之前您可以開啟回應群組通話清單報告） 可辨識下列通話類型：

  - **接收的通話**。 回應群組應用程式的所有執行個體接收的通話總數。

  - **成功的通話**。 已收取的回應群組應用程式的通話總數。

  - **提供的通話**。轉接至回應群組代理程式的通話總數。

  - **接聽的通話**。回應群組代理程式實際接聽的通話總數。

  - 放棄的通話百分比。 回應群組應用程式已接收，但代理從未接聽的通話百分比。 這是從接收的通話減掉接聽的通話，再除以接收的通話數，所計算出來的值。 例如，如果您接收到 10 次通話，並接聽 7 次，就要從 10 減掉 7，剩下 3 次未接聽的通話。 該值再除以 10，則得到的放棄通話百分比為 30%。

  - **轉接的通話**。 因為佇列逾時或佇列溢位而轉接的回應群組通話總數。

<div>

## <a name="accessing-the-response-group-call-list-report"></a>存取回應群組通話清單報告

按一下 [ [Lync Server 2013 中的回應群組使用量報告](lync-server-2013-response-group-usage-report.md)上找到下列計量之一只可以存取回應群組通話清單報告：

  - 接收的通話

  - 成功的通話

  - 提供的通話

  - 接聽的通話

  - 轉接的通話

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a>最大效用的回應群組通話清單報告

回應群組通話清單報告可讓您限制對通話牽涉到特定的回應群組工作流程顯示的資料。 若要這樣做，您需要在 [工作流程 URI] 方塊中輸入工作流程 （工作流程的 SIP 位址） 的 URI。 您可以這麼做之前，不過，您必須實際能夠看到工作流程 URI] 方塊中。 若要顯示回應群組通話清單報告的篩選選項，請按一下 [報表] 視窗的左上左邊部分中的 [顯示/隱藏參數] 按鈕。

請注意，回應群組通話清單不會顯示資訊的回應碼或診斷識別碼是否您將滑鼠停留在這些計量之一。 如果您需要的詳細資訊，您可能會記下的回應碼及/或診斷識別碼，並且然後搜尋[Lync Server 2013 中的最大失敗報告](lync-server-2013-top-failures-report.md)中的這些值。

像這樣的問題: 「 哪一個個別的工作流程接收最多通話？ 」，您可以執行下列動作：

1.  在回應群組使用量報告中，設定所需的時間期間，然後按一下已接收通話計量。 如此會開啟回應群組通話清單報告。

2.  匯出的回應群組通話清單報告上顯示的資料。 例如，您可能會匯出 Microsoft Excel 格式的資料，並再將該資料轉換成逗點分隔值檔案使用 Excel。

3.  執行分析使用 Windows PowerShell。

例如，如果您將資料儲存至檔案，名為 c:\\資料\\回應\_群組\_呼叫\_清單\_Report.csv，您可以再使用下列命令來傳回每個工作流程報告中所列的已接收通話總數：

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

會將類似的資訊：

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

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 下表列出您可以使用回應群組通話清單報告的篩選器。

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
<p>2012/7/7</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>2012/7/3</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>2012/7/7</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>2012/7/3</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>工作流程 URI</strong></p></td>
<td><p>可讓您將傳回的資料限定在指定的回應群組工作流程。若要使用此篩選，請輸入工作流程 SIP 位址。例如：</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
<tr class="even">
<td><p><strong>通話</strong></p></td>
<td><p>您可以選取下列其中一個下列通話類型：</p>
<ul>
<li><p>接收的通話</p></li>
<li><p>成功的通話</p></li>
<li><p>提供的通話</p></li>
<li><p>接聽的通話</p></li>
<li><p>轉接的通話</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>計量

下表列出回應群組應用程式所接收的每個呼叫的回應群組通話清單報告內所提供的資訊。

### <a name="response-group-call-list-report-metrics"></a>回應群組通話清單報告計量

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
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
<td><p>日期和時間通話的開始。</p></td>
</tr>
<tr class="even">
<td><p><strong>結束時間</strong></p></td>
<td><p>否</p></td>
<td><p>日期和時間通話的結束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>回應碼</strong></p></td>
<td><p>否</p></td>
<td><p>SIP 工作階段失敗時傳送的回應碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>否</p></td>
<td><p>唯一識別項 （以毫秒診斷標頭的形式） 附加在 SIP 訊息通常提供在疑難排解錯誤很有用的資訊。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

