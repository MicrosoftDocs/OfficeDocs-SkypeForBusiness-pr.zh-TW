---
title: 設定詳細通話記錄及經驗品質設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring call detail recording and Quality of Experience settings
ms:assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204621(v=OCS.15)
ms:contentKeyID: 48183223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 504c2221e9f8a3ef32e2cebbb792f5e03aef15c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-call-detail-recording-and-quality-of-experience-settings-in-lync-server-2013"></a>在 Lync Server 2013 中設定通話詳細資料錄製和體驗品質設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-17_

在您將監視存放區與前端池關聯之後，請設定監視存放區，然後安裝和設定 SQL Server Reporting Services 及監視報告，您可以管理呼叫詳細資料錄製（CDR）及體驗品質（QoE）使用 Lync Server 管理命令介面進行監視。 Lync Server 管理命令介面 Cmdlet 可讓您針對特定網站或整個 Lync Server 部署啟用及停用 CDR 及/或 QoE 監視;如此一來，您就可以使用簡單的命令完成下列作業：

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

當您安裝 Microsoft Lync Server 2013 時，您也會針對 CDR 和 QoE 安裝預先定義的全域配置設定集合。 [通話詳細資料錄製] 使用的一些常用設定的預設值如下表所示：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Property</th>
<th>說明</th>
<th>預設值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnableCDR</p></td>
<td><p>指出是否已啟用 CDR。 如果為 True，則會收集所有 CDR 記錄，並將其寫入監視資料庫。</p></td>
<td><p>滿足</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>指出 CDR 記錄是否會定期從資料庫中刪除。 如果為 True，則在屬性 KeepCallDetailForDays （適用于 CDR 記錄）和 KeepErrorReportForDays （針對 CDR 錯誤）指定的時段之後，將會刪除記錄。 如果是 False，則會無限期維護 CDR 記錄。</p></td>
<td><p>滿足</p></td>
</tr>
<tr class="odd">
<td><p>KeepCallDetailForDays</p></td>
<td><p>指出 CDR 記錄將保留在資料庫中的天數;任何超過指定天數的記錄都會自動刪除。 不過，這只會在已啟用清除的情況下發生。</p>
<p>KeepCallDetailForDays 可以設定為1到2562天之間（大約7年）的任何整數值。</p></td>
<td><p>60 天</p></td>
</tr>
<tr class="even">
<td><p>KeepErrorReportForDays</p></td>
<td><p>指出 CDR 錯誤報表的保留天數;任何超過指定天數的報告都會自動刪除。 CDR 錯誤報表是由用戶端應用程式（例如 Microsoft Lync 2013）上傳的診斷報告。</p>
<p>您可以將此屬性設定為1到2562天之間的任何整數值。</p></td>
<td><p>60 天</p></td>
</tr>
</tbody>
</table>


同樣地，此表格會顯示所選 QoE 設定的預設值：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Property</th>
<th>說明</th>
<th>預設值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnableQoE</p></td>
<td><p>指出是否已啟用 QoE 監視。 如果為 True，則會收集所有 QoE 記錄並寫入監視資料庫。</p></td>
<td><p>滿足</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>指出 QoE 記錄是否會定期從資料庫中刪除。 如果為 True，則會在 KeepQoEDataForDays 屬性指定的時段之後刪除記錄。 如果是 False，QoE 記錄將會無限期維護。</p></td>
<td><p>滿足</p></td>
</tr>
<tr class="odd">
<td><p>KeepQoEDataForDays</p></td>
<td><p>指出 QoE 記錄將保留在資料庫中的天數;任何超過指定天數的記錄都會自動刪除。 不過，這只會在已啟用清除的情況下發生。</p>
<p>KeepCallDetailForDays 可以設定為1到2562天之間的任何整數值。</p></td>
<td><p>60 天</p></td>
</tr>
</tbody>
</table>


如果您需要修改這些全域設定，您可以使用 CsCdrConfiguration 和 CsQoEConfiguration Cmdlet 來執行此動作。 例如，此命令（在 Lync Server 管理命令介面內執行）會停用全域範圍中的 CDR 監視;這是透過將 EnableCDR 屬性設定為 False （$False）來完成：

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

請注意，停用監視並不會解除與 [前端] 池的關聯，也不會卸載或以其他方式影響後端監視資料庫。 當您使用 Lync Server 管理命令介面來停用 CDR 或 QoE 監視時，您實際所做的全部動作就是暫時停止 Lync Server 收集及封存監視資料。 如果您想要繼續，在這種情況下，您只需將 EnableCDR 屬性設回 True （$True），就可以開始收集及歸檔 CDR 資料：

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

同樣地，這個命令會停用全域範圍的 QoE 記錄清除：

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

除了全域設定，還可以將 CDR 及 QoE 設定設定指派給網站範圍。 這在監視時提供額外的管理靈活性;例如，管理員可以為雷德蒙的網站啟用 CDR 監視，但停用用於都柏林網站的 CDR 監視。 若要在網站範圍中建立新的 CDR 配置設定，請使用類似以下的命令：

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

請記住，在網站範圍設定的設定會優先于在全域範圍中設定的設定。 例如，假設在全域範圍中啟用 CDR 監視，但在網站範圍停用（針對雷德蒙的網站）。 如此一來，就不會針對雷德蒙者網站上的使用者封存通話詳細資料記錄資訊。 不過，其他網站中的使用者（也就是由全域設定所管理的使用者，而不是雷德蒙網站設定）會將通話詳細記錄資訊存檔。

您可以使用如下的命令，在網站範圍建立新的 QoE 配置設定：

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

如需詳細資訊，請在 Lync Server 管理命令介面中輸入下列命令：

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

</div>

<span> </span>

</div>

</div>

</div>

