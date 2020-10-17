---
title: Lync Server 2013： PSTN 使用方式記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74c9f6dda4112325d6a408cc1bbb543373e9de61
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512430"
---
# <a name="pstn-usage-records-in-lync-server-2013"></a>Lync Server 2013 中的 PSTN 使用方式記錄

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-23_

規劃 PSTN 使用方式記錄，主要是列出組織中目前強制執行的所有呼叫許可權，從 CEO 到暫存工作者、顧問和員工。 此程式也可讓您重新檢查現有的呼叫許可權並加以修正。 您只能為適用于您預期的 Enterprise Voice 使用者的呼叫許可權建立 PSTN 使用方式記錄，但較好的長方案可能是針對所有呼叫許可權建立 PSTN 使用方式記錄，而不論某些可能目前未套用到啟用 Enterprise Voice 的使用者群組。 如果新增了具有不同呼叫許可權的撥號許可權變更或新使用者，您就已建立必要的 PSTN 使用方式記錄。

下表顯示一般的 PSTN 使用方式表格。

### <a name="pstn-usage-records"></a>PSTN 使用方式記錄

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Phone 屬性</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>本機</p></td>
<td><p>本機通話</p></td>
</tr>
<tr class="even">
<td><p>Long-Distance</p></td>
<td><p>長途通話</p></td>
</tr>
<tr class="odd">
<td><p>International</p></td>
<td><p>國際通話</p></td>
</tr>
<tr class="even">
<td><p>德里</p></td>
<td><p>新德里全職員工</p></td>
</tr>
<tr class="odd">
<td><p>雷德蒙</p></td>
<td><p>雷德蒙的全職員工</p></td>
</tr>
<tr class="even">
<td><p>RedmondTemps</p></td>
<td><p>Redmond 臨時員工</p></td>
</tr>
<tr class="odd">
<td><p>蘇黎世</p></td>
<td><p>蘇黎世全職員工</p></td>
</tr>
</tbody>
</table>


PSTN 使用方式記錄本身不會執行任何動作。 為了讓他們能夠運作，您必須將它們與下列專案產生關聯：

  - 指派給使用者的語音原則。

  - 指派給電話號碼的路由。

如需語音原則和路由的詳細資訊，請參閱 lync server [2013 中的語音原則](lync-server-2013-voice-policies.md) 和 [lync server 2013 中的語音路由](lync-server-2013-voice-routes.md)。 如需如何建立及設定的詳細資訊，請參閱 [在 Lync Server 2013 中設定撥出電話的語音路由](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)。

</div>

<span> </span>

</div>

</div>

</div>

