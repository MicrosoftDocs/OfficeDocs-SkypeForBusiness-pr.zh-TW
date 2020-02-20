---
title: Lync Server 2013： 從另一個應用程式啟動 Lync
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
ms.openlocfilehash: 75e7a48645301b6c822eed52ea31e6d4b46019bd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a>從另一個應用程式啟動 Lync

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-20 個_

您可以使用命令列參數，以快速開始 Lync 2013。 例如，如果使用者按一下 [其他應用程式中的電話號碼，應用程式可以啟動 Lync 2013 的執行個體，並啟動該號碼。

Lync 2013 還能辨識分號分隔的連絡人名稱清單以便進行多方會議。

若 Lync 2013 設為自動啟動時，登入，然後以命令列參數啟動 Lync 2013 將會開啟在 Lync 主視窗。 如果 Lync 未設定成在啟動時，會自動登入，登入視窗隨即開啟。

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
<th>副檔名</th>
<th>資料格式</th>
<th>動作</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>tel:</p></td>
<td><p>tel URI</p></td>
<td><p>開啟音訊通話的 [交談] 視窗，但不會撥打指定的號碼。</p></td>
</tr>
<tr class="even">
<td><p>callto:</p></td>
<td><p>tel:，sip:，或可輸入的 tel URI</p></td>
<td><p>開啟音訊通話的 [交談] 視窗，但不會撥打指定的號碼。</p></td>
</tr>
<tr class="odd">
<td><p>sip:</p></td>
<td><p>SIP URI</p></td>
<td><p>開啟 「 交談 」 視窗與指定之 SIP 統一資源識別元 (URI) 在參與者清單中。</p></td>
</tr>
<tr class="even">
<td><p>Sips:</p></td>
<td><p>SIP URI</p></td>
<td><p>如果 Lync 2013 設定為使用傳輸層安全性 (TLS) 通訊協定，函式完全像 sip:。 如果未使用 TLS，會顯示對話方塊，告知使用者的安全性層級必要。</p></td>
</tr>
<tr class="odd">
<td><p>conf:</p></td>
<td><p>SIP URI 的會議加入</p></td>
<td><p>如果 self URI，具現化焦點，並會帶出名冊僅限檢視。 否則，會帶出名冊檢視，但不會傳送邀請。</p></td>
</tr>
<tr class="even">
<td><p>im:</p></td>
<td><p>SIP URI</p></td>
<td><p>會顯示 [立即訊息 (IM)-僅交談視窗與 SIP URI。 可接受多個 SIP Uri 指定內角括弧 (&lt;&gt;) 不含任何分隔符號。</p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


下表提供上述命令列參數範例。

### <a name="command-line-parameter-examples"></a>命令列參數範例

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>執行個體</th>
<th>結果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tel: 14255550101</p></td>
<td><p>會開啟 14255550101 的僅限電話檢視。</p></td>
</tr>
<tr class="even">
<td><p>Callto:tel: + 14255550101</p></td>
<td><p>會開啟 14255550101 的僅限電話檢視。</p></td>
</tr>
<tr class="odd">
<td><p>Callto:sip:kazuto@litwareinc.com</p></td>
<td><p>開啟內含 kazuto@litwareinc.com 的僅限電話檢視。</p></td>
</tr>
<tr class="even">
<td><p>sip:kazuto@litwareinc.com</p></td>
<td><p>開啟內含 kazuto@litwareinc.com 的交談視窗。</p></td>
</tr>
<tr class="odd">
<td><p>conf:sip:https://meet.contoso.com/kazuto/7322994</p></td>
<td><p>開啟的交談視窗並顯示會議音訊加入選項。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

