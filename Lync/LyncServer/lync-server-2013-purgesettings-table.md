---
title: Lync Server 2013： PurgeSettings 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205121(v=OCS.15)
ms:contentKeyID: 48184932
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56ea95d0ba54a34eaa315ff345efb45cd563700c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a>Lync Server 2013 中的 PurgeSettings 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

PurgeSettings 資料表包含的資訊可指定是否會自動從 CDR 資料庫中刪除過時的呼叫詳細資料記錄。 請注意，您也可以透過執行下列命令，在 Microsoft Lync Server 2013 管理命令介面中取得清除相關資訊：

    Get-CsCdrConfiguration

系統管理員應該將 PurgeSettings 資料表視為唯讀：只有使用[新的-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration)或[Set CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) Cmdlet，才能對通話詳細資料清除設定進行變更。

此表格是在 Microsoft Lync Server 2013 中推出。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>左欄</th>
<th>資料類型</th>
<th>索引鍵/索引</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>標識號</strong></p></td>
<td><p>int</p></td>
<td><p>首選</p></td>
<td><p>CDR 清除設定集合的唯一識別碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>稍微</p></td>
<td></td>
<td><p>當設定為 True （1）時，Microsoft Lync Server 2013 會定期從 CDR 資料庫清除過時的記錄。 [清除] 會在每天的 PurgeHour 設定所指定的聖多美上進行。 如果設定為 False （0），則不會自動從資料庫清除記錄。 預設值為 True。</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepCallDetailForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>指定將從資料庫清除的 CDR 記錄（天數）的存留期：如果已啟用清除，則早于此值的 CDR 記錄將會從資料庫中移除。 預設值為60天。</p></td>
</tr>
<tr class="even">
<td><p><strong>KeepErrorReportForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>指定將從資料庫清除的錯誤報表記錄（天數）的存留期：如果已啟用清除，則超過此值的錯誤報表記錄將會從資料庫中移除。 預設值為60天。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>指定要在進行資料庫清除時的當地時間。 時間是以 24 小時制指定，0 代表午夜 (12:00 AM)，而 23 則代表 11:00 PM。 請注意，您只能指定一天中的小時數：值為10（表示 10:00 AM），但不允許值為 10:30 of 10.5 （表示 10:30 AM）。 預設值為 2 (2:00 AM)。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

