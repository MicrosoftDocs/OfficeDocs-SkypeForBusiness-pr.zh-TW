---
title: 'Lync Server 2013: PurgeSettings 表'
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
ms.openlocfilehash: 7cbe8543f1d26f42186654d2988258e796d7eebb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a>Lync Server 2013 中的 PurgeSettings 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-28_

PurgeSettings 表包含指定是否 （時） 的資訊從 CDR 資料庫會自動刪除過期的通話詳細記錄。 請注意，清除的相關資訊，還可以取得從 Microsoft Lync Server 2013 管理命令介面中執行下列命令：

    Get-CsCdrConfiguration

系統管理員應將 PurgeSettings 表格視為唯讀： 通話詳細資料的清除設定應該只會變更使用[New-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration)或[Set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet。

Microsoft Lync Server 2013 中已採用此表格。


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
<th>主索引鍵 /</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Id</strong></p></td>
<td><p>int</p></td>
<td><p>主要</p></td>
<td><p>唯一識別項集合的 CDR 清除設定。</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>位元</p></td>
<td></td>
<td><p>當設為 True （1) Microsoft Lync Server 2013 會定期從 CDR 資料庫清除過期的記錄。 清除動作會每天在 PurgeHour 設定中指定的時間加以執行。 若設為 False (0)，就不會從資料庫自動清除記錄。 預設值為 True。</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepCallDetailForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>指定的保留天數會從資料庫中清除的 CDR 記錄 （以天數）： 如果啟用 [清除]，將會從資料庫中移除 CDR 記錄超過此值。 預設值為 60 天。</p></td>
</tr>
<tr class="even">
<td><p><strong>KeepErrorReportForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>指定錯誤報告中的記錄 （天），將會從資料庫中清除存留期： 如果啟用 [清除]，將會從資料庫中移除錯誤報告的記錄超過此值。 預設值為 60 天。</p></td>
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

