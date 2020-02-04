---
title: Lync Server 2013： CDR 視圖清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR views
ms:assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688009(v=OCS.15)
ms:contentKeyID: 49733598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fe2620175c2a706bfb2c48fe7fb380d5fae4c09
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-views-in-lync-server-2013"></a>Lync Server 2013 中的 CDR 視圖清單

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

[視圖] 提供一種簡單的方式，可存取從 CDR 資料庫傳回資料最常見的案例資訊。 建議您使用 [視圖] 來建立自訂報表，而不是使用實際的 CDR 資料庫資料表;這是因為資料庫檢視很可能會與未來的 Lync Server 版本保持向後相容性。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>[視圖名稱]</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-view.md">Lync Server 2013 中的 [ClientVersions] 視圖</a></p></td>
<td><p>傳回通訊會話中使用之用戶端軟體/裝置的相關資訊。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencemessagecount-view.md">Lync Server 2013 中的 [ConferenceMessageCount] 視圖</a></p></td>
<td><p>傳回會議中使用者傳送的訊息數的相關資訊。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-view.md">Lync Server 2013 中的會議視圖</a></p></td>
<td><p>傳回會議資訊，包括 [開始時間]、[結束時間] 和 [會議召集人]。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-view.md">Lync Server 2013 中的 [ConferenceSessionDetails] 視圖</a></p></td>
<td><p>傳回所有會議會話的會話詳細資料，包括開始和結束時間、使用者識別碼、回應代碼，以及診斷 Id。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferenceuris-view.md">Lync Server 2013 中的 [ConferenceUris] 視圖</a></p></td>
<td><p>傳回會議中使用之會議 Uri 的相關資訊</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errorreport-view.md">Lync Server 2013 中的 [ErrorReport] 視圖</a></p></td>
<td><p>傳回在會話期間發生之錯誤的相關資訊。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-filetransfers-view.md">Lync Server 2013 中的 [FileTransfers] 視圖</a></p></td>
<td><p>傳回檔案傳輸會話的相關資訊，包括檔案名，以及傳輸被接受、拒絕或取消。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-focusjoinsandleaves-view.md">Lync Server 2013 中的 [FocusJoinsAndLeaves] 視圖</a></p></td>
<td><p>傳回會議加入與離開活動的相關資訊。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mcujoinsandleaves-view.md">Lync Server 2013 中的 [McuJoinsAndLeaves] 視圖</a></p></td>
<td><p>傳回會議加入與離開活動的綜合資訊（每個會議加入都與對應的會議休假成對出現）。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-view.md">Lync Server 2013 中的 [Mcus] 視圖</a></p></td>
<td><p>傳回會議服務器的相關資訊。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-view.md">Lync Server 2013 中的媒體視圖</a></p></td>
<td><p>傳回對等通訊會話中所使用之媒體類型的相關資訊。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-view.md">Lync Server 2013 中的 [ProgressReport] 視圖</a></p></td>
<td><p>傳回已完成會話的相關資訊。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-registration-view.md">Lync Server 2013 中的 [註冊] 視圖</a></p></td>
<td><p>傳回有關 Lync Server 註冊的資訊。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 中的 [SessionDetails] 視圖</a></p></td>
<td><p>傳回點對點工作階段的相關資訊，包括 VoIP VoIP 電話、兩方 IM 會話，或其他對等通訊會話。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-user-view.md">Lync Server 2013 中的使用者視圖</a></p></td>
<td><p>傳回參與通訊會話之使用者的相關資訊。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-voipdetails-view.md">Lync Server 2013 中的 [VoIPDetails] 視圖</a></p></td>
<td><p>傳回至少包含一個 VoIP （在 IO 上）使用者的點對點工作階段的資訊。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

