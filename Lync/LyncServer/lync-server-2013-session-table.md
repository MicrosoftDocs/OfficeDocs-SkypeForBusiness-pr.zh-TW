---
title: Lync Server 2013： 工作階段表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 554491ebdc09789a2704835dc0dce3ddc34f8b0b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a>Lync Server 2013 中的工作階段表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-09-09_

每筆記錄代表一個包括音訊或音訊和視訊工作階段。 它包含整體工作階段的相關資訊。 工作階段被指兩個端點之間的音訊或視訊工作階段初始通訊協定 (SIP) 對話方塊。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>欄</strong></th>
<th><strong>資料類型</strong></th>
<th><strong>主索引鍵 /</strong></th>
<th><strong>詳細資料</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主要</p></td>
<td><p>參考來源： <a href="lync-server-2013-dialog-table.md">Lync Server 2013 中的 Dialog 表格</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主要</p></td>
<td><p>參考來源： <a href="lync-server-2013-dialog-table.md">Lync Server 2013 中的 Dialog 表格</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>會議索引鍵。 參考來源： <a href="lync-server-2013-conference-table.md">Lync Server 2013 中的會議表格</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>相互關聯索引鍵。 參考來源： <a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 中的 SessionCorrelation 表格</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogCategory</strong></p></td>
<td><p>位元</p></td>
<td><p> </p></td>
<td><p>對話類別;0 是 Lync Server 中繼伺服器 leg;1 是中繼伺服器到 PSTN 閘道計量。</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServerBypassFlag</strong></p></td>
<td><p>位元</p></td>
<td></td>
<td><p>指出通話略過如果旗標。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaBypassWarningFlag</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>此欄位 (若有) 指出即使旁路識別碼相符，通話為何未經旁路處理。 Lync Server 的定義只能有一個值。</p>
<p>0x0001 – 預設網路介面卡未知的旁路 ID。</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>通話開始時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>通話結束時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPool</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>發話者的集區。 參考來源： <a href="lync-server-2013-pool-table.md">Lync Server 2013 中的集區資料表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePool</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>受話者集區。 參考來源： <a href="lync-server-2013-pool-table.md">Lync Server 2013 中的集區資料表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleePAI</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>在 [SIP p 聲稱的身分識別 (PAI) 接收方端點的 SIP URI。 參考來源：<a href="lync-server-2013-user-table.md">使用者在 Lync Server 2013 中的表格</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerURI</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>發話者的 URI。 參考來源：<a href="lync-server-2013-user-table.md">使用者在 Lync Server 2013 中的表格</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>發話者端點。 參考來源： <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的端點資料表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerUserAgent</strong></p></td>
<td><p>位元</p></td>
<td><p>Foreign</p></td>
<td><p>發話者的使用者代理程式。 參考來源： <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>此通話的優先順序。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>位元</p></td>
<td></td>
<td><p>此資料行已經被取代，並不適用於 Microsoft Lync Server 2013。 相反地，這項資訊會報告上的每個媒體行基底。 請參閱<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a> ，如需詳細資訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPAI</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>P-聲稱的身分識別打電話的使用者。 P 聲稱的識別 (PAI) 用來傳達使用者打電話，則為 true 身分識別。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>接到電話的端點。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeUserAgent</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>使用者代理程式採用使用者已收到通話。 使用者代理程式代表的用戶端端點裝置。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeUri</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>接到電話之使用者的 SIP URI。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

