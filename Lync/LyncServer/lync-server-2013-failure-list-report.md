---
title: Lync Server 2013：失敗清單報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure List Report
ms:assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615446(v=OCS.15)
ms:contentKeyID: 48185194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 370008a5b33cc7eb45802fb02bdd9a873184ed5a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-list-report-in-lync-server-2013"></a>Lync Server 2013 中的 [失敗清單] 報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-07-02_

[失敗清單] 報告會提供參與對等無法進行對等或會議會話的個別參與者的相關資訊。 此資訊包含遇到問題之使用者的 URI，以及與失敗相關聯的 SIP 回應程式碼與診斷 ID。

<div>

## <a name="accessing-the-failure-list-report"></a>存取失敗清單報告

您可以在[Lync Server 2013 的 [失敗] 發佈報告中](lync-server-2013-failure-distribution-report.md)，按一下下列任何一個測量，以存取 [失敗清單] 報告：

  - 常見的診斷原因（會話）

  - 熱門形式（會話）

  - 頂層池（會話）

  - 熱門來源（會話）

  - Top 元件（會話）

  - 使用者的最上層（會話）

  - 使用者的最上層（會話）

  - 使用者代理程式（會話）的頂端

在 [失敗清單] 報告中，您可以透過按一下點對點工作階段的會話詳細資料指標，[在 Lync Server 2013 中存取點對點工作階段詳細資料包告](lync-server-2013-peer-to-peer-session-detail-report.md)。 您也可以按一下會議的會議指標，以存取會議詳細資料包告。

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a>充分利用 [失敗清單] 報告

在 [失敗清單] 報告中，您只要將滑鼠放在該值上，就能查看每個回應代碼或每個診斷 ID 的描述。 例如，如果您將滑鼠放在診斷 ID 7025 上，您會看到下列顯示在工具提示中：

為使用者建立媒體時發生內部伺服器錯誤。

請務必注意，[失敗清單] 報告不會提供直接檢索至少參與一個失敗會話之所有使用者清單的簡單方法，也不會提供判斷哪些使用者最常參與失敗的方法。課時. （一件事，失敗清單報告沒有篩選功能）。不過，如果您匯出資料，然後將它轉換成逗號分隔值檔案，您可以使用 Windows PowerShell 來尋找問題等問題的答案。 例如，假設您將資料儲存至。名為 C：\\資料\\失敗\_清單 .csv 的 CSV 檔案。 根據儲存在該檔案中的資料，此命令會列出至少有一個失敗的會話中所涉及的所有使用者：

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

該命令會傳回如下所示的清單：

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

這兩個命令會傳回每位使用者所涉及的失敗會話總數：

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

這樣會傳回如下所示的資料：

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a>濾鏡

無。 您無法篩選失敗清單報告。

</div>

<div>

## <a name="metrics"></a>指標

下表列出每個失敗的通話在失敗清單報告中所提供的資訊。

### <a name="failure-list-report-metrics"></a>失敗清單報告度量單位

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
<td><p><strong>報告時間</strong></p></td>
<td><p>否</p></td>
<td><p>記錄報告的日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>徵求</strong></p></td>
<td><p>否</p></td>
<td><p>失敗的 SIP 要求類型。 例如，[邀請] 或 [再見]。</p></td>
</tr>
<tr class="odd">
<td><p><strong>回應代碼</strong></p></td>
<td><p>否</p></td>
<td><p>在會議失敗時傳送 SIP 回應代碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>否</p></td>
<td><p>附加至 SIP 訊息的唯一識別碼（ms diagnostics 標頭形式），通常可在疑難排解錯誤中提供有用的資訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>加入成本時間（毫秒）</strong></p></td>
<td><p>否</p></td>
<td><p>使用者加入會議所需的時間長度（以毫秒為單位）。</p></td>
</tr>
<tr class="even">
<td><p><strong>從使用者</strong></p></td>
<td><p>否</p></td>
<td><p>啟動通話的使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>從使用者代理程式</strong></p></td>
<td><p>否</p></td>
<td><p>啟動通話之使用者的端點所使用的軟體。</p></td>
</tr>
<tr class="even">
<td><p><strong>給使用者</strong></p></td>
<td><p>否</p></td>
<td><p>呼叫的使用者的 SIP 位址。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

