---
title: Lync Server 2013： PurgeSettings 表格
description: Lync Server 2013： PurgeSettings 表格。
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
ms.openlocfilehash: 1ec2d1508d8362988bddbab2fe7303a23a8ee2d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559179"
---
# <a name="purgesettings-table-in-lync-server-2013"></a>Lync Server 2013 中的 PurgeSettings 表格

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

PurgeSettings 表包含的資訊可指定是否 (和何時會自動從 CDR 資料庫中刪除) 過期的詳細通話記錄。 請注意，您也可以在 Microsoft Lync Server 2013 管理命令介面中執行下列命令，以取得清除相關資訊：

    Get-CsCdrConfiguration

管理員應該將 PurgeSettings 表格視為唯讀：只有在使用 [新的-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) 或 [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) Cmdlet 時，才應進行通話詳細資料清除設定的變更。

此表格已引進 Microsoft Lync Server 2013。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>欄</th>
<th>資料類型</th>
<th>索引鍵/索引</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Id</strong></p></td>
<td><p>int</p></td>
<td><p>主要</p></td>
<td><p>CDR 清除設定集合的唯一識別碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>位</p></td>
<td></td>
<td><p>設為 True 時 (1) Microsoft Lync Server 2013 會定期從 CDR 資料庫清除過時的記錄。 清除動作會每天在 PurgeHour 設定中指定的時間加以執行。 若設為 False (0)，就不會從資料庫自動清除記錄。 預設值為 True。</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepCallDetailForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>會指定要從資料庫中清除之 CDR 記錄的保留天數)  (：如果啟用清除，則舊于此值以上的 CDR 記錄會從資料庫中移除。 預設值為 60 天。</p></td>
</tr>
<tr class="even">
<td><p><strong>KeepErrorReportForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>指定要從資料庫中清除的錯誤報表記錄 (天數) ：若啟用清除功能，則會從資料庫中移除比此值還舊的錯誤報表記錄。 預設值為 60 天。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>指定要執行資料庫清除的時間。 時間是以 24 小時制指定，0 代表午夜 (上午 12:00)，而 23 則代表下午 11:00。 請注意，您僅能指定時間的時數：允許將值設為 10 (代表上午 10:00)，但不允許設為 10:30 的 10.5 (代表上午 10:30)。 預設值為 2 (2:00 AM)。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

