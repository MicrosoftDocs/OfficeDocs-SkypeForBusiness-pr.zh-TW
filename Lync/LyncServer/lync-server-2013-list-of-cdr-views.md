---
title: Lync Server 2013： CDR views 清單
description: Lync Server 2013： CDR views 清單。
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
ms.openlocfilehash: 8f1c29560851c0e4466dbf4316bf0b1335906d4e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550079"
---
# <a name="list-of-cdr-views-in-lync-server-2013"></a>Lync Server 2013 中 CDR 視圖的清單

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

檢視讓您可以輕鬆取得從 CDR 資料庫傳回資料時最常見情況的資訊。 建議您使用 [視圖] 來建立自訂報表，而不是使用實際的 CDR 資料庫資料表;這是因為資料庫檢視更可能與未來的 Lync Server 版本保持向後相容性。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>檢視名稱</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-view.md">Lync Server 2013 中的 ClientVersions 視圖</a></p></td>
<td><p>傳回通訊工作階段中使用的用戶端軟體/裝置資訊。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencemessagecount-view.md">Lync Server 2013 中的 ConferenceMessageCount 視圖</a></p></td>
<td><p>傳回會議中使用者傳送的訊息數量資訊。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-view.md">Lync Server 2013 中的會議視圖</a></p></td>
<td><p>傳回會議資訊，包含開始時間、結束時間以及唯一會議召集人。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-view.md">Lync Server 2013 中的 ConferenceSessionDetails 視圖</a></p></td>
<td><p>傳回所有會議工作階段的工作階段詳細資料，包含開始及結束時間、使用者 ID、回應碼及診斷 ID。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conferenceuris-view.md">Lync Server 2013 中的 ConferenceUris 視圖</a></p></td>
<td><p>傳回會議中使用的會議 URI 資訊</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errorreport-view.md">Lync Server 2013 中的 ErrorReport 視圖</a></p></td>
<td><p>傳回工作階段期間發生之錯誤的資訊。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-filetransfers-view.md">Lync Server 2013 中的 FileTransfers 視圖</a></p></td>
<td><p>傳回檔案傳輸工作階段的資訊，包含檔案名稱以及是否接受、拒絕或取消傳輸。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-focusjoinsandleaves-view.md">Lync Server 2013 中的 FocusJoinsAndLeaves 視圖</a></p></td>
<td><p>傳回會議加入及會議離開活動的資訊</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mcujoinsandleaves-view.md">Lync Server 2013 中的 McuJoinsAndLeaves 視圖</a></p></td>
<td><p>傳回會議加入及會議離開活動的合併資訊 (每次會議加入均有對應的會議離開作為搭配)。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-view.md">Lync Server 2013 中的 Mcus 視圖</a></p></td>
<td><p>傳回會議伺服器的資訊。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-view.md">Lync Server 2013 中的媒體視圖</a></p></td>
<td><p>傳回對等通訊工作階段中使用的媒體類型資訊。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-view.md">Lync Server 2013 中的 ProgressReport 視圖</a></p></td>
<td><p>傳回已完成之工作階段的資訊。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-registration-view.md">Lync Server 2013 中的註冊視圖</a></p></td>
<td><p>傳回 Lync Server 註冊的相關資訊。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 中的 SessionDetails 視圖</a></p></td>
<td><p>傳回對等工作階段的資訊，包含 VoIP 對 VoIP 電話、雙方 IM 工作階段，或其他對等通訊工作階段。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-user-view.md">Lync Server 2013 中的使用者視圖</a></p></td>
<td><p>傳回已加入通訊工作階段之使用者的資訊。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-voipdetails-view.md">Lync Server 2013 中的 VoIPDetails 視圖</a></p></td>
<td><p>傳回至少包含一位 VoIP 使用者之對等工作階段的資訊。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

