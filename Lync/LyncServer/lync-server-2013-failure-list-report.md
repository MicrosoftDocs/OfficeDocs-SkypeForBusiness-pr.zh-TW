---
title: Lync Server 2013： 失敗清單報告
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
ms.openlocfilehash: 3fc3d74e6613f54f346e00328f1fae929f7def27
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failure-list-report-in-lync-server-2013"></a>Lync Server 2013 中的失敗清單報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-07-02_

失敗清單報告提供參與失敗對等端對端或會議工作階段之個別參與者的相關資訊。 此資訊包括遇到問題，以及 SIP 回應碼之使用者的 URI，並診斷識別碼相關聯失敗。

<div>

## <a name="accessing-the-failure-list-report"></a>存取失敗清單報告

按一下任何[失敗散佈報告在 Lync Server 2013](lync-server-2013-failure-distribution-report.md)上的下列計量來存取失敗清單報告：

  - 前幾名診斷原因 (工作階段)

  - 最常見形式 (工作階段)

  - 最常見集區 (工作階段)

  - 最常見來源 (工作階段)

  - 最常見元件 (工作階段)

  - 最常見來源使用者 (工作階段)

  - 最常見目標使用者 (工作階段)

  - 最常見來源使用者代理程式 (工作階段)

您可以從 Failure List Report]，即可工作階段詳細資料] 計量端對端工作階段存取[Lync Server 2013 中的端對端工作階段詳細資料報告](lync-server-2013-peer-to-peer-session-detail-report.md)。 您也可以藉由按一下 [會議] 計量的會議存取會議詳細資料報告。

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a>失敗清單報告的最佳用法

在失敗清單報告中，您可以檢視每個回應程式碼或每個診斷識別碼的描述，只要該值上按住滑鼠。 例如，如果將滑鼠停留診斷識別碼 7025 您會看到下列工具提示中顯示：

建立使用者的媒體的內部伺服器錯誤。

請務必注意 Failure List Report 不提供直接的方法，以直接擷取清單中的所有使用者參與至少一個與失敗工作階段，也不會提供方法來決定哪些使用者最常有關的失敗工作階段。 （第一，Failure List Report 有無篩選功能）。不過，如果您將資料匯出，然後將它轉換成逗點分隔值檔案，您可以使用 Windows PowerShell 來尋找類似這些問題的答案。 例如，假設您儲存的資料。CSV 檔名為 c:\\資料\\失敗\_List.csv。 根據儲存在該檔案中的資料，此命令會列出所有已至少一個失敗工作階段相關的使用者：

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

該命令會傳回清單類似這樣：

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

這兩個命令可回報告每位使用者遭遇的失敗工作階段總數：

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

無。 您無法篩選 Failure List Report。

</div>

<div>

## <a name="metrics"></a>計量

下表列出失敗清單報告針對每通失敗通話所提供的資訊。

### <a name="failure-list-report-metrics"></a>失敗清單報告計量

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
<td><p><strong>報告的時間</strong></p></td>
<td><p>否</p></td>
<td><p>日期和時間報告的記錄。</p></td>
</tr>
<tr class="even">
<td><p><strong>要求</strong></p></td>
<td><p>否</p></td>
<td><p>SIP 失敗的要求類型。 例如，邀請或 BYE。</p></td>
</tr>
<tr class="odd">
<td><p><strong>回應碼</strong></p></td>
<td><p>否</p></td>
<td><p>會議失敗時所傳送的 SIP 回應碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>否</p></td>
<td><p>唯一識別項 （以毫秒診斷標頭的形式） 附加在 SIP 訊息通常提供在疑難排解錯誤很有用的資訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>加入時間 （毫秒）</strong></p></td>
<td><p>否</p></td>
<td><p>量所需的使用者加入會議的時間 （以毫秒為單位）。</p></td>
</tr>
<tr class="even">
<td><p><strong>來源使用者</strong></p></td>
<td><p>否</p></td>
<td><p>撥打通話之使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>來源使用者代理程式</strong></p></td>
<td><p>否</p></td>
<td><p>撥打通話之使用者端點所用的軟體。</p></td>
</tr>
<tr class="even">
<td><p><strong>目標使用者</strong></p></td>
<td><p>否</p></td>
<td><p>要呼叫之使用者的 SIP 位址。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

