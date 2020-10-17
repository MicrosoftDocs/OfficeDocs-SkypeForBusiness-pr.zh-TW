---
title: Lync Server 2013：從其他應用程式啟動 Lync
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
ms.openlocfilehash: 0d10e70615083796baa0934c6291b377dcd18005
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519510"
---
# <a name="starting-lync-from-another-application"></a>從另一個應用程式啟動 Lync

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-20_

您可以使用命令列參數，快速地啟動 Lync 2013。 例如，如果使用者按一下另一個應用程式中的電話號碼，應用程式就可以啟動 Lync 2013 的實例，並初始化對該號碼的呼叫。

Lync 2013 也可以辨識以分號分隔的連絡人名稱清單，以供多方會議使用。

如果 Lync 2013 已設定為在開始時自動登入，則使用命令列參數啟動 Lync 2013 時，會開啟 Lync 主視窗。 若 Lync 未設定為在開始時自動登入，則會開啟登入視窗。

下表顯示可用的參數。

### <a name="lync-2013-command-line-parameters"></a>Lync 2013 Command-Line 參數

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>副檔名</th>
<th>資料格式</th>
<th>動作</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>電話：</p></td>
<td><p>電話 URI</p></td>
<td><p>會開啟語音通話的交談視窗，但不會撥打指定的號碼。</p></td>
</tr>
<tr class="even">
<td><p>callto</p></td>
<td><p>電話：、sip：或 typeable 電話 URI</p></td>
<td><p>會開啟語音通話的交談視窗，但不會撥打指定的號碼。</p></td>
</tr>
<tr class="odd">
<td><p>Sip：</p></td>
<td><p>SIP URI</p></td>
<td><p>在參與者清單中，以指定的 SIP 統一資源識別項 (URI) 開啟 [交談] 視窗。</p></td>
</tr>
<tr class="even">
<td><p>Sip</p></td>
<td><p>SIP URI</p></td>
<td><p>如果 Lync 2013 設定為使用傳輸層安全性 (TLS) 通訊協定，其功能與 sip 完全相同：。 若未使用 TLS，會顯示一個對話方塊，告知使用者需要較高的安全性層級。</p></td>
</tr>
<tr class="odd">
<td><p>會議</p></td>
<td><p>加入會議的 SIP URI</p></td>
<td><p>如果 URI 是自我，請將焦點具現化，並只顯示僅限名單的模式。 否則，會顯示名單視圖，但不會傳送邀請。</p></td>
</tr>
<tr class="even">
<td><p>我：</p></td>
<td><p>SIP URI</p></td>
<td><p>以 SIP URI 顯示立即訊息 (IM) 專用交談視窗。 接受在 &lt; &gt; 不含任何分隔符號 () 中的角括弧中指定的多個 SIP URIs。</p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


下表提供這些命令列參數的範例。

### <a name="command-line-parameter-examples"></a>Command-Line 參數範例

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Instance</th>
<th>結果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>電話： + 14255550101</p></td>
<td><p>開啟具有 + 14255550101 的僅限電話的視圖。</p></td>
</tr>
<tr class="even">
<td><p>Callto：電話： + 14255550101</p></td>
<td><p>開啟具有 + 14255550101 的僅限電話的視圖。</p></td>
</tr>
<tr class="odd">
<td><p>Callto:sip:kazuto@litwareinc.com</p></td>
<td><p>使用 kazuto@litwareinc.com 開啟僅限電話的視圖。</p></td>
</tr>
<tr class="even">
<td><p>sip:kazuto@litwareinc.com</p></td>
<td><p>使用 kazuto@litwareinc.com 開啟交談視窗。</p></td>
</tr>
<tr class="odd">
<td><p>會議： sip：https://meet.contoso.com/kazuto/7322994</p></td>
<td><p>開啟 [交談] 視窗並顯示會議音訊加入選項。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

