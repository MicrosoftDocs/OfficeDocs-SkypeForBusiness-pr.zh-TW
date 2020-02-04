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
ms.openlocfilehash: 4ec15b826614afcca970989b6436d3ad94d7941f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a>在 Lync Server 2013 中指派每個使用者的目前狀態原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-11_

目前狀態原則是一組會影響目前狀態的限制與限制。 下表說明 Lync Server 2013 中的目前狀態原則設定。

### <a name="presence-policy-settings"></a>目前狀態原則設定

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
<th>說明</th>
<th>類型</th>
<th>值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CategorySubscriptions</p></td>
<td><p>最大訂閱者類別訂閱數</p></td>
<td><p>限制訂閱者類別訂閱的數目。 例如，當 Communicator 訂閱使用者的目前狀態時，它會針對每一個連絡人卡片、行事歷數據、記事、服務和狀態類別，取得類別訂閱。</p>
<p>設定為0表示使用者或連絡人物件不能由其他人訂閱。</p>
<div>

> [!NOTE]  
> 此設定會對效能產生很大的影響（如果它設定為高數位），而一般使用者有大量的使用者訂閱自己的目前狀態。


</div></td>
<td><p>整</p></td>
<td><p>0-3000</p></td>
</tr>
<tr class="even">
<td><p>PromptedSubscribers</p></td>
<td><p>已排隊的目前狀態訂閱通知數量上限</p></td>
<td><p>限制提示訂閱者資料表中的專案數。 這個設定決定了指定使用者可以列隊的最大提示數。 例如，當使用者 A 訂閱使用者 B 的目前狀態時，使用者 B 會收到提示：使用者 A 現在已訂閱使用者 B，而使用者 B 的提示訂閱者資料表中則會建立確認提示。 當使用者 B 接受或確認訂閱之後，就會從使用者 B 的提示訂閱者資料表中移除確認提示。</p>
<p>設定為0表示某人訂閱自己的目前狀態時，系統不會提示使用者。</p></td>
<td><p>整型或標記</p></td>
<td><p>0-500</p></td>
</tr>
</tbody>
</table>


根據預設**原則**和服務，當您部署 Lync Server 時，就會安裝 [**中**目前狀態] 原則。 下表說明這兩種目前狀態原則的特定設定。

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
<th>說明</th>
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
<td><p>服務：中型</p></td>
<td><p>需要更多使用者才能訂閱物件目前狀態的應用程式原則。</p></td>
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

