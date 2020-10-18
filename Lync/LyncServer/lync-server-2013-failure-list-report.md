---
title: Lync Server 2013：失敗清單報告
description: Lync Server 2013：失敗清單報告。
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
ms.openlocfilehash: 7467144fe207ab61fd086cd35aac74779fd4f771
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575049"
---
# <a name="failure-list-report-in-lync-server-2013"></a>Lync Server 2013 的失敗清單報告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-07-02_

「失敗清單報告」會提供參與「對等」或「會議」會話失敗之人員的相關資訊。 此資訊包含發生問題之使用者的 URI，以及與失敗相關聯的 SIP 回應碼和診斷識別碼。

<div>

## <a name="accessing-the-failure-list-report"></a>存取失敗清單報告

若要存取失敗清單報告，請在 [ [Lync Server 2013] 中的 [失敗] 散佈報告](lync-server-2013-failure-distribution-report.md)上，按一下下列任一度量值：

  - 前幾名診斷原因 (工作階段)

  - 最常見形式 (工作階段)

  - 最常見集區 (工作階段)

  - 最常見來源 (工作階段)

  - 最常見元件 (工作階段)

  - 最常見來源使用者 (工作階段)

  - 最常見目標使用者 (工作階段)

  - 最常見來源使用者代理程式 (工作階段)

在 [失敗清單] 報告中，您可以按一下點對點工作階段的會話詳細資料計量， [以在 Lync Server 2013 中存取 Peer-to-Peer 會話詳細資料包告](lync-server-2013-peer-to-peer-session-detail-report.md) 。 您也可以按一下會議的會議度量來存取會議詳細資料包告。

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a>讓 [失敗清單] 報告的最佳用法

在 [失敗清單] 報告中，只要將滑鼠停留在該值上，您就可以查看每個回應代碼或每個診斷識別碼的描述。 例如，如果您將滑鼠停留在診斷 ID 7025 上，您會看到工具提示中顯示下列內容：

為使用者建立媒體時發生內部伺服器錯誤。

請務必注意，失敗清單報告並未提供直接找回至少參與一則失敗之會話之所有使用者的清單，也不會提供一種方法來判斷失敗的會話中最常參與的使用者。  (一件事，失敗清單報告沒有篩選功能。 ) 不過，如果您匯出資料，然後將其轉換成逗號分隔值檔案，您可以使用 Windows PowerShell 尋找類似問題的答案。 例如，假設您將資料儲存到。名為 C： \\ 資料 \\ 失敗 \_List.csv 的 CSV 檔案。 根據儲存在該檔案中的資料，此命令會列出至少包含一個失敗會話的所有使用者：

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

該命令會傳回類似以下的清單：

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

這兩個命令傳回每位使用者參與的失敗會話總數：

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

該命令將傳回類似下列的資料：

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a>篩選

無。 您無法篩選失敗清單報告。

</div>

<div>

## <a name="metrics"></a>指標

下表列出每個失敗通話的失敗清單報告中提供的資訊。

### <a name="failure-list-report-metrics"></a>失敗清單報告計量

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
<td><p><strong>報告時間</strong></p></td>
<td><p>否</p></td>
<td><p>報告的記錄日期與時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>請求</strong></p></td>
<td><p>否</p></td>
<td><p>失敗的 SIP 要求類型。 例如，INVITE 或再見。</p></td>
</tr>
<tr class="odd">
<td><p><strong>回應碼</strong></p></td>
<td><p>否</p></td>
<td><p>會議失敗時所傳送的 SIP 回應碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>否</p></td>
<td><p>附加至 SIP 郵件（通常會在疑難排解錯誤中提供有用資訊) ）的表單中的唯一識別碼 (。</p></td>
</tr>
<tr class="odd">
<td><p><strong>加入成本時間 (毫秒) </strong></p></td>
<td><p>否</p></td>
<td><p>使用者加入會議所需的時間長度 (（毫秒）) 。</p></td>
</tr>
<tr class="even">
<td><p><strong>來源使用者</strong></p></td>
<td><p>否</p></td>
<td><p>撥打通話之使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>從使用者代理程式</strong></p></td>
<td><p>否</p></td>
<td><p>起始通話之使用者端點所使用的軟體。</p></td>
</tr>
<tr class="even">
<td><p><strong>目標使用者</strong></p></td>
<td><p>否</p></td>
<td><p>呼叫之使用者的 SIP 位址。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

