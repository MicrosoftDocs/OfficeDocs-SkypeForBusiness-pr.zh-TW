---
title: Lync Server 2013：PSTN 使用方式記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e32000f1664591a3e054d058ced4f996a98f27cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-usage-records-in-lync-server-2013"></a>Lync Server 2013 中的 PSTN 使用方式記錄

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-23_

規劃 PSTN 使用記錄主要包含在您的組織中，從 CEO 到臨時性員工、顧問及臨時員工，列出目前正在進行中的所有呼叫許可權。 此程式也提供重新檢查現有通話許可權及修正它們的機會。 您只能為適用于您預期企業語音使用者的呼叫許可權建立 PSTN 使用記錄，但較好的方案可能是針對所有的呼叫許可權建立 PSTN 使用記錄，不論是否有可能目前已套用至要啟用企業語音的使用者群組。 如果您已新增撥號許可權變更或具有不同呼叫許可權的新使用者，就表示您已經建立所需的 PSTN 使用記錄。

下表顯示典型的 PSTN 用法資料表。

### <a name="pstn-usage-records"></a>PSTN 使用記錄

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>[電話] 屬性</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>局部</p></td>
<td><p>當地電話</p></td>
</tr>
<tr class="even">
<td><p>遠距離</p></td>
<td><p>長途電話</p></td>
</tr>
<tr class="odd">
<td><p>國際</p></td>
<td><p>國際通話</p></td>
</tr>
<tr class="even">
<td><p>新德里</p></td>
<td><p>新德里全職員工</p></td>
</tr>
<tr class="odd">
<td><p>Redmond</p></td>
<td><p>雷德蒙全職員工</p></td>
</tr>
<tr class="even">
<td><p>RedmondTemps</p></td>
<td><p>雷蒙德暫時員工</p></td>
</tr>
<tr class="odd">
<td><p>蘇黎世</p></td>
<td><p>蘇黎世全職員工</p></td>
</tr>
</tbody>
</table>


PSTN 使用量記錄本身不會執行任何動作。 若要讓他們正常運作，您必須將它們與下列專案建立關聯：

  - 指派給使用者的語音原則。

  - 指派給電話號碼的工藝路線。

如需語音原則與路線的詳細資料，請參閱 lync server [2013 中的語音原則](lync-server-2013-voice-policies.md)和[lync server 2013 中的語音路由](lync-server-2013-voice-routes.md)。 如需如何建立和設定它們的詳細資料，請參閱[在 Lync Server 2013 中設定出站通話的語音路由](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)。

</div>

<span> </span>

</div>

</div>

</div>

