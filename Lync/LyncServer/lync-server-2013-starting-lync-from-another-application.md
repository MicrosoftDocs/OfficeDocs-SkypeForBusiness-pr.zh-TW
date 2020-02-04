---
title: Lync Server 2013：從另一個應用程式啟動 Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dafb8295d3070cd9f38e8691e654146978156d45
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a>從另一個應用程式啟動 Lync

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-20_

您可以使用命令列參數快速啟動 Lync 2013。 例如，如果使用者在其他應用程式中按一下電話號碼，應用程式可以啟動 Lync 2013 的實例，並初始化該號碼的呼叫。

Lync 2013 也可以辨識以分號分隔的多方會議連絡人名稱清單。

如果 Lync 2013 已設定為在啟動時自動登入，則使用命令列參數啟動 Lync 2013，就會開啟 Lync 主視窗。 如果 Lync 未設定為在啟動時自動登入，[登入] 視窗就會隨即開啟。

下表顯示可用的參數。

### <a name="lync-2013-command-line-parameters"></a>Lync 2013 命令列參數

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>延伸</th>
<th>資料的格式</th>
<th>動作</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>tel</p></td>
<td><p>電話 URI</p></td>
<td><p>開啟 [交談] 視窗以進行音訊通話，但不會撥打指定的電話號碼。</p></td>
</tr>
<tr class="even">
<td><p>callto</p></td>
<td><p>電話：，sip：，或 typeable 電話 URI</p></td>
<td><p>開啟 [交談] 視窗以進行音訊通話，但不會撥打指定的電話號碼。</p></td>
</tr>
<tr class="odd">
<td><p>呼吸</p></td>
<td><p>SIP URI</p></td>
<td><p>在參與者清單中，開啟含有指定 SIP 統一資源識別項（URI）的 [交談] 視窗。</p></td>
</tr>
<tr class="even">
<td><p>那些</p></td>
<td><p>SIP URI</p></td>
<td><p>如果 Lync 2013 設定為使用傳輸層安全性（TLS）通訊協定，則功能與 sip 完全一樣：。 如果沒有使用 TLS，則會顯示一個對話方塊，通知使用者需要較高的安全性等級。</p></td>
</tr>
<tr class="odd">
<td><p>會議</p></td>
<td><p>加入會議的 SIP URI</p></td>
<td><p>如果 URI 是 self，請將焦點放在一起，並顯示 [僅限名單] 視圖。 否則，會顯示 [名單] 視圖，但不會傳送邀請。</p></td>
</tr>
<tr class="even">
<td><p>傳遞</p></td>
<td><p>SIP URI</p></td>
<td><p>顯示含有 SIP URI 的立即訊息（IM）專用交談視窗。 接受在不含任何分隔符號的角括弧（&lt;&gt;）內指定的多個 SIP uri。</p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


下表提供這些命令列參數的範例。

### <a name="command-line-parameter-examples"></a>命令列參數範例

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>示例</th>
<th>這樣</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>電話： + 14255550101</p></td>
<td><p>開啟只有 [+ 14255550101] 的 [僅限手機] 視圖。</p></td>
</tr>
<tr class="even">
<td><p>Callto：電話： + 14255550101</p></td>
<td><p>開啟只有 [+ 14255550101] 的 [僅限手機] 視圖。</p></td>
</tr>
<tr class="odd">
<td><p>Callto:sip:kazuto@litwareinc.com</p></td>
<td><p>開啟 [僅限手機] 視圖，並顯示 kazuto@litwareinc.com。</p></td>
</tr>
<tr class="even">
<td><p>sip:kazuto@litwareinc.com</p></td>
<td><p>使用 kazuto@litwareinc.com 開啟交談視窗。</p></td>
</tr>
<tr class="odd">
<td><p>會議： sip：https://meet.contoso.com/kazuto/7322994</p></td>
<td><p>開啟交談視窗，並顯示會議音訊連接選項。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

