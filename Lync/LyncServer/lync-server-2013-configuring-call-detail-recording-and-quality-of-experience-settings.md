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
ms.openlocfilehash: a6f39bf16a9d0ecf57a5617774395af477a67c2d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502130"
---
# <a name="configuring-call-detail-recording-and-quality-of-experience-settings-in-lync-server-2013"></a>在 Lync Server 2013 中設定詳細通話記錄及經驗品質設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-17_

在您將監視存放區與前端集區相關聯之後，請先設定監視儲存體，然後安裝及設定 SQL Server Reporting Services 與監視報告，以使用 Lync Server 管理命令介面來管理詳細通話記錄 (CDR) 和經驗品質 (QoE) 監視。 Lync Server 管理命令介面 Cmdlet 可讓您啟用及停用特定網站或整個 Lync Server 部署的 CDR 和/或 QoE 監視;您可以使用下列方式做為簡單的命令：

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

當您安裝 Microsoft Lync Server 2013 時，也會為 CDR 和 QoE 同時安裝全域設定設定的預先定義集合。 下表顯示詳細通話記錄較常用的一些設定的預設值：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>屬性	</th>
<th>描述</th>
<th>預設值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnableCDR</p></td>
<td><p>表示是否啟用 CDR。若為 True，則會收集所有 CDR 記錄並寫入監控資料庫。</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>表示是否要從資料庫定期刪除 CDR 記錄。若為 True，則會在過了 KeepCallDetailForDays (適用於 CDR 記錄) 和 KeepErrorReportForDays (適用於 CDR 錯誤) 屬性指定的期間之後刪除記錄。若為 False，則會無限期保留 CDR 記錄。</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>KeepCallDetailForDays</p></td>
<td><p>表示在資料庫保留 CDR 記錄的天數；任何超過指定天數的記錄都將自動刪除。但是，只有在啟用清除功能時，才會發生此情況。</p>
<p>您可以將 KeepCallDetailForDays 設為 1 到 2562 天 (大約 7 年) 之間的任何整數值。</p></td>
<td><p>60 天</p></td>
</tr>
<tr class="even">
<td><p>KeepErrorReportForDays</p></td>
<td><p>表示保留 CDR 錯誤報告的天數；任何超過指定天數的報告都將自動刪除。 CDR 錯誤報表是由用戶端應用程式（例如 Microsoft Lync 2013）上傳的診斷報告。</p>
<p>您可以將此屬性設為 1 到 2562 天之間的任何整數值。</p></td>
<td><p>60 天</p></td>
</tr>
</tbody>
</table>


同樣地，下表顯示所選 QoE 設定的預設值：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>屬性	</th>
<th>描述</th>
<th>預設值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnableQoE</p></td>
<td><p>表示是否啟用 QoE 監控。若為 True，則會收集所有 QoE 記錄並寫入監控資料庫。</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>EnablePurging</p></td>
<td><p>表示是否要從資料庫定期刪除 QoE 記錄。若為 True，則會在過了 KeepQoEDataForDays 屬性指定的期間之後刪除記錄。若為 False，則會無限期保留 QoE 記錄。</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>KeepQoEDataForDays</p></td>
<td><p>表示在資料庫保留 QoE 記錄的天數；任何超過指定天數的記錄都將自動刪除。但是，只有在啟用清除功能時，才會發生此情況。</p>
<p>您可以將 KeepCallDetailForDays 設為 1 到 2562 天之間的任何整數值。</p></td>
<td><p>60 天</p></td>
</tr>
</tbody>
</table>


如果您需要修改這些全域設定，可以使用 Set-CsCdrConfiguration 和 Set-CsQoEConfiguration Cmdlet 執行這項操作。例如，從 Lync Server 管理命令介面執行此命令可在全域範圍停用 CDR 監控；作法是將 EnableCDR 屬性設為 False ($False)：

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

請注意，停用監控並不會解除監控儲存區與前端集區的關聯，也不會解除安裝或影響後端監控資料庫。 當您使用 Lync Server 管理命令介面停用 CDR 或 QoE 監視時，您實際執行的工作會暫時停止 Lync Server 收集和封存監控資料。 在此情況下，如果您想繼續收集及封存 CDR 資料，只需要將 EnableCDR 屬性設回 True ($True) 即可：

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

同樣地，此命令會在全域範圍停止清除 QoE 記錄：

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

除了全域設定之外，也可以對網站範圍指派 CDR 和 QoE 組態設定。這會提供監控作業額外的管理彈性；例如，系統管理員可以啟用 Redmond 網站的 CDR 監控，但停用 Dublin 網站的 CDR 監控。若要在網站範圍建立新的 CDR 組態設定，請使用類似如下的命令：

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

請注意，在網站範圍進行的設定優先順序高於在全域範圍進行的設定。例如，假設在全域範圍啟用 CDR 監控，但在網站範圍 (Redmond 網站) 停用 CDR 監控。這表示不會封存 Redmond 網站使用者的詳細通話記錄資訊，但是會封存其他網站使用者 (亦即全域設定 (而非 Redmond 網站設定) 所管理的使用者) 的詳細通話記錄資訊。

您可以使用類似如下的命令，在網站範圍建立新的 QoE 組態設定：

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

