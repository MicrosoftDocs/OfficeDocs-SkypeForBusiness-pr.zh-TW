---
title: Lync Server 2013：回應群組使用方式報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Usage Report
ms:assetid: 3248b320-a552-400a-8485-6891af4eb0f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558632(v=OCS.15)
ms:contentKeyID: 48183811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 649fb55f6c7b698986c4c31057b3a0a8f1b00a76
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511620"
---
# <a name="response-group-usage-report-in-lync-server-2013"></a>Lync Server 2013 的回應群組使用方式報告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

回應群組應用程式提供一種方式，讓 Microsoft Lync Server 2013 根據撥打的號碼來接聽和路由通話，也可以在來電者對一系列問題的回應中作出通話。 系統通常不會將回應群組通話路由傳送給個人，而是將通話路由傳送給稱為代理群組的一組人員。 例如，如果有人呼叫您的技術支援人員的電話號碼，Lync Server 2013 可自動將該呼叫路由傳送至第一個可用的服務台代理。 或者，如果您有硬體問題，Lync Server 可能會詢問一系列的問題 ( "請按1。 軟體問題請按 2。 如果您有網路問題，請按3。」) ，然後根據這些問題的答案，將通話路由傳送給最適當的服務台代理程式。

回應群組使用方式報告會提供您所有回應群組工作流程所接收之通話數的詳細資訊，然後將這些通話細分為更有限的分類，例如，提供的通話、接聽的通話及放棄的通話。

使用回應群組使用方式報告的關鍵是了解所報告之通話類型間的差異：

  - **接收的通話**。回應群組應用程式的所有執行個體接收的通話總數。

  - **成功的通話**。 回應群組應用程式挑選的呼叫總數。

  - **提供的通話**。轉接至回應群組代理程式的通話總數。

  - **接聽的通話**。回應群組代理程式實際接聽的通話總數。

  - **放棄的通話百分比**。回應群組應用程式已接收，但代理從未接聽的通話百分比。這是從接收的通話減掉接聽的通話，再除以接收的通話數，所計算出來的值。例如，如果您接收到 10 次通話，並接聽 7 次，就要從 10 減掉 7，剩下 3 次未接聽的通話。該值再除以 10，則得到的放棄通話百分比為 30%。

  - **轉接的通話**。因為佇列逾時或佇列溢位而轉接的回應群組通話總數。

如果您正在查看回應群組使用方法報告且不記得這其中任一個通話類型的定義，只需在適當的通話類型標籤上方按住您的滑鼠。即會出現工具提示，提供該通話類型的簡短說明。

回應群組使用方式報告讓您能夠篩選工作流程 URI (與該工作流程相關聯的 SIP 位址)。但是，工作流程 URI 不會實際出現在報告本身上。如果您想要了解像是哪些工作流程接聽了最多通話或者哪些工作流程經歷了最多轉接通話等事項，請按一下適當的衡量標準，以開啟該特定期間的回應群組通話清單報告。該報告不會列出工作流程 URI。

<div>

## <a name="accessing-the-response-group-usage-report"></a>存取回應群組使用方式報告

您可以從 [監視報告] 首頁存取回應群組使用方式報告。 您可以按一下下列任一度量，向下流覽 [Lync Server 2013 中的回應群組通話清單報告](lync-server-2013-response-group-call-list-report.md) ：

  - 接收的通話

  - 成功的通話

  - 提供的通話

  - 接聽的通話

  - 轉接的通話

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-usage-report"></a>回應群組使用方式報告的最佳用法

回應群組使用方式報告有一個更有趣但不是相當明顯的用途：擷取單一回應群組工作流程之使用方式資訊的能力。

<div>


> [!WARNING]  
> 回應群組工作流程基本上是一組指示當使用者撥打特定電話號碼時的 Lync Server 所執行的動作。 為該結束，每個工作流程都會與電話號碼有唯一的關聯。 當某人呼叫該號碼時，工作流程會決定處理呼叫的方式。 例如，工作流程可能導致呼叫路由傳送至一系列互動語音回應 (IVR) 問題，提示來電者輸入其他資訊 ( "按1以取得硬體支援。 軟體支援請按 2。 或者，工作流程可能會造成呼叫進入佇列中，來電者保留此呼叫直到代理可接聽來電。 代理是否可接聽電話的狀態，也是由工作流程指定的：工作流程可用來設定營業時間 (一星期的哪幾天和哪些時段會有代理接聽電話) 與假日 (代理無法接聽電話的日子)。 任何時候當您撥打屬於回應群組應用程式的電話號碼時，實際上就是呼叫回應群組工作流程。



</div>

雖然工作流程 URI 不會出現在回應群組使用方式報告中，但仍能檢視單一工作流程的使用方式統計資料，此種通常非常有用的資訊。例如，假設您最近推出了新的廣告行銷活動，並且很好奇地想要了解是否有人來電詢問該產品。如果您已將回應群組工作流程關聯至廣告促銷活動中指定的電話號碼，即可輕易地進行檢查以查看有多少人撥打該號碼 (如果有的話)。

您可能也會使用類似的處理方式，來估計您內部服務台或客戶服務部門所處理的通話數。

若要檢閱特定工作流程的使用方式統計資料，請在 [工作流程 URI] 方塊中輸入工作流程 URI。 當然，如上所述，工作流程 URI (與工作流程相關聯的 SIP 位址) 不會出現在報告上。 這表示您需要尋找其他方法來決定工作流程的 URI。 使用 Windows PowerShell 和 Lync Server 管理命令介面，一種方式是使用 Windows 和 Lync Server 管理命令介面。 例如，此命令會傳回您所有回應群組工作流程的 URI：

    Get-CsRgsWorkflow | Select-Object Name, PrimaryUri

該命令將傳回類似下列的資料：

    Name                            PrimaryUri
    ----                            ----------
    Customer Support                sip:support@litwareinc.com
    Help Desk                       sip:helpdesk@litwareinc.com
    New Ad Campaign                 sip:newads@litwareinc.com

此命令會傳回單一工作流程 (名稱為「New Ad Campaign」的工作流程) 的資訊：

    Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri

</div>

<div>

## <a name="filters"></a>篩選

篩選可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 例如，回應群組使用量報告可讓您檢視所有回應群組工作流程的資料，或檢視個別工作流程的資料。您也可以選擇資料的分組方式。在這種情況下，使用量會按照小時、日、星期或月加以分組。

下表列出您可以用於回應群組使用量報告的篩選。

### <a name="response-group-usage-report-filters"></a>回應群組使用量報告篩選

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
<td><p><strong>Interval</strong></p></td>
<td><p>時間間隔。請選取下列其中一項：</p>
<ul>
<li><p>每小時 (最多可以顯示 25 個小時)</p></li>
<li><p>每日 (最多可以顯示 31 天)</p></li>
<li><p>每週 (最多可以顯示 12 週)</p></li>
<li><p>每月 (最多可以顯示 12 個月)</p></li>
</ul>
<p>若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 7/7/2012 及 2/28/2012，將只會顯示 8/7/2012 上午 12:00 至 9/7/2012 上午 12:00 這段期間的資料 (亦即只會顯示 31 天的資料)。</p></td>
</tr>
<tr class="even">
<td><p><strong>工作流程 URI</strong></p></td>
<td><p>可讓您將傳回的資料限定在指定的回應群組工作流程。若要使用此篩選，請輸入工作流程 SIP 位址。例如：</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

下表列出回應群組使用量報告提供的資訊。

### <a name="response-group-usage-report-metrics"></a>回應群組使用量報告計量

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
<td><p><strong>每小時</strong></p>
<p><strong>每日</strong></p>
<p><strong>每週</strong></p>
<p><strong>每月</strong></p></td>
<td><p>否</p></td>
<td><p>指示所選的時間間隔。在適用的情況下，只要按一下指定的時間間隔，即可檢視該間隔的詳細資訊。例如，若您使用 [每日] 間隔並按一下 7/7/2012，將會顯示該日期之使用者登錄活動的每小時明細。</p></td>
</tr>
<tr class="even">
<td><p><strong>接收的通話</strong></p></td>
<td><p>否</p></td>
<td><p>回應群組應用程式的所有執行個體接收的通話總數。當您按一下此項目，報告即顯示所選取時段的回應群組通話清單報告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>成功的通話</strong></p></td>
<td><p>否</p></td>
<td><p>回應群組應用程式接聽的通話總數。當您按一下此項目，報告即顯示所選取時段的回應群組通話清單報告。</p></td>
</tr>
<tr class="even">
<td><p><strong>提供的通話</strong></p></td>
<td><p>否</p></td>
<td><p>轉接至回應群組代理程式的通話總數。當您按一下此項目，報告即顯示所選取時段的回應群組通話清單報告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>接聽的通話</strong></p></td>
<td><p>否</p></td>
<td><p>回應群組代理程式實際接聽的通話總數。當您按一下此項目，報告即顯示所選取時段的回應群組通話清單報告。</p></td>
</tr>
<tr class="even">
<td><p><strong>放棄的通話百分比</strong></p></td>
<td><p>否</p></td>
<td><p>回應群組應用程式已接收，但代理程式從未接聽的通話總數。這是從接收的通話減掉接聽的通話，再除以接收的通話數，所計算出來的值。例如，如果您收到 10 次通話，並接聽 7 次，就要從 10 減掉 7，剩下 3 次未接聽的通話。該值再除以 10，則得到的放棄通話百分比為 30%.</p></td>
</tr>
<tr class="odd">
<td><p><strong>代理程式的平均通話分鐘數</strong></p></td>
<td><p>否</p></td>
<td><p>回應群組代理程式用在單一通話的平均時間量。</p></td>
</tr>
<tr class="even">
<td><p><strong>轉接的通話</strong></p></td>
<td><p>否</p></td>
<td><p>因為佇列逾時或佇列溢位而轉接的回應群組通話總數。當您按一下此項目，報告即顯示所選取時段的回應群組通話清單報告。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

