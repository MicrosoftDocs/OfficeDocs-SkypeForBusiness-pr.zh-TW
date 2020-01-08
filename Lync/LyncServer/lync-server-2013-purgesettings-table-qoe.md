---
title: Lync Server 2013： PurgeSettings table （QoE）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PurgeSettings table (QoE)
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204788(v=OCS.15)
ms:contentKeyID: 48183777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3cc227d11ee723acb5a49c50d5b8d4d7e819062
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-qoe-in-lync-server-2013"></a>Lync Server 2013 中的 PurgeSettings table （QoE）

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

PurgeSettings 資料表包含的資訊會指定是否（以及時間）系統會自動將過時的體驗記錄品質從 QoE 資料庫中刪除。 請注意，您也可以透過執行下列命令，在 Microsoft Lync Server 2013 管理命令介面中取得清除相關資訊：

    Get-CsQoEConfiguration

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
<th><strong>左欄</strong></th>
<th><strong>資料類型</strong></th>
<th><strong>索引鍵/索引</strong></th>
<th><strong>詳細資料</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>標識號</strong></p></td>
<td><p>int</p></td>
<td><p>首選</p></td>
<td><p>QoE 清除設定集合的唯一識別碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>EnablePurge</strong></p></td>
<td><p>稍微</p></td>
<td></td>
<td><p>當設定為 True （1）時，Microsoft Lync Server 2013 會定期從 QoE 資料庫清除過時的記錄。 [清除] 會在每天的 PurgeHour 設定所指定的聖多美上進行。 如果設定為 False （0），則不會自動從資料庫清除記錄。 預設值為 True。</p></td>
</tr>
<tr class="odd">
<td><p><strong>KeepQoEDataForDays</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>指定將從資料庫清除的 QoE 記錄（天）期限：如果已啟用清除，則會從資料庫中移除超過此值的 QoE 記錄。 預設值為60天。</p></td>
</tr>
<tr class="even">
<td><p><strong>PurgeHour</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>指定要在進行資料庫清除時的當地時間。 時間是以 24 小時制指定，0 代表午夜 (12:00 AM)，而 23 則代表 11:00 PM。 請注意，您只能指定一天中的小時數：值為10（表示 10:00 AM），但不允許值為 10:30 of 10.5 （表示 10:30 AM）。 預設值為1（1:00 AM）。 指定要在進行資料庫清除時的當地時間。 時間是以 24 小時制指定，0 代表午夜 (12:00 AM)，而 23 則代表 11:00 PM。 請注意，您只能指定一天中的小時數：值為10（表示 10:00 AM），但不允許值為 10:30 of 10.5 （表示 10:30 AM）。 預設值為1（1:00 AM）。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

