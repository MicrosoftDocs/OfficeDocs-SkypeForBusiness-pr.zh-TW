---
title: Lync Server 2013：指派每個使用者的目前狀態原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c4f561189b72cf19fad28879711e3a1da0da8fb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527120"
---
# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a>在 Lync Server 2013 中指派每一使用者的目前狀態原則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-11_

目前狀態原則是一組影響顯示狀態的限制和限制。 下表說明 Lync Server 2013 中可用的目前狀態原則設定。

### <a name="presence-policy-settings"></a>顯示狀態原則設定

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>XML 名稱</th>
<th>顯示名稱</th>
<th>描述</th>
<th>Type</th>
<th>值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CategorySubscriptions</p></td>
<td><p>訂閱者類別訂閱數目上限</p></td>
<td><p>限制使用者類別訂閱數目。 例如，當 Communicator 訂閱使用者的目前狀態時，它會取得每個連絡人卡片、行事歷數據、記事、服務和狀態類別的類別訂閱。</p>
<p>設定為0表示使用者或連絡人物件無法由其他人訂閱。</p>
<div>

> [!NOTE]  
> 此設定在效能設定為高值時，對效能的影響很大，而且平均使用者有大量使用者訂閱其目前狀態。


</div></td>
<td><p>整數</p></td>
<td><p>0-3000</p></td>
</tr>
<tr class="even">
<td><p>PromptedSubscribers</p></td>
<td><p>佇列顯示訂閱警示的數目上限</p></td>
<td><p>限制提示的訂戶表格中的專案數。 此設定會決定指定使用者可以列隊的提示數目上限。 例如，當使用者 A 訂閱使用者 B 的狀態時，使用者 B 會收到提示，指出使用者 A 現在已訂閱使用者 B，而且會在使用者 B 的提示訂閱者表格中建立認可提示。 在使用者 B 接受（或承認）訂閱後，會從使用者 B 的提示訂閱者表格中移除確認提示。</p>
<p>設定為0時，表示當有人訂閱他或她的目前狀態時，不會提示使用者。</p></td>
<td><p>整數或標記</p></td>
<td><p>0-500</p></td>
</tr>
</tbody>
</table>


根據預設，當您部署 Lync Server 時，會安裝 **預設原則** 及 **服務：「中** 狀態」原則。 下表說明兩種目前狀態原則的特定設定。

### <a name="presence-policies"></a>目前狀態原則

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>原則名稱</th>
<th>描述</th>
<th>CategorySubscriptions</th>
<th>PromptedSubscribers</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>預設原則</p></td>
<td><p>一般使用者的原則。 這是預設的目前狀態原則。</p></td>
<td><p>1000</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>服務：中速</p></td>
<td><p>需要更多使用者訂閱物件目前狀態的應用程式的原則。</p></td>
<td><p>1000</p></td>
<td><p>0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

