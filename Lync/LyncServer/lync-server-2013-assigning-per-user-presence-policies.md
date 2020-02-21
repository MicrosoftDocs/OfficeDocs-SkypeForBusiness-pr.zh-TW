---
title: Lync Server 2013： 指派每位使用者的顯示狀態原則
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
ms.openlocfilehash: c169c6995ca49cc89742bd026b18dc254430cb9d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a>指派每位使用者在 Lync Server 2013 中的目前狀態原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-11_

目前狀態原則是一組的限制與限制會影響目前狀態。 下表說明適用於 Lync Server 2013 的目前狀態原則設定。

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
<th>辨別名稱 (DN)</th>
<th>描述</th>
<th>Type</th>
<th>值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CategorySubscriptions</p></td>
<td><p>訂閱者類別目錄訂閱數目上限</p></td>
<td><p>限制訂閱者類別目錄訂閱的數目。 例如，當 Communicator 訂閱使用者的目前狀態，它會取得類別訂用帳戶為每個連絡人卡片、 行事曆資料、 備忘稿、 服務和狀態類別。</p>
<p>如果設定為 0 表示使用者或連絡人物件無法由其他使用者訂閱。</p>
<div>

> [!NOTE]  
> 此設定可以對效能造成重大影響，如果它設定為較高的數字，而且一般使用者會有大量使用者訂閱他/她的目前狀態。


</div></td>
<td><p>整數</p></td>
<td><p>0 – 3000</p></td>
</tr>
<tr class="even">
<td><p>PromptedSubscribers</p></td>
<td><p>已排入佇列的目前狀態訂閱警示數目上限</p></td>
<td><p>限制提示 「 訂閱者 」 表格中的項目數。 此設定會決定可以排入佇列的指定使用者的提示的最大數目。 例如，當使用者的訂閱使用者 B 的目前狀態，使用者 B 會收到提示的現在訂閱給使用者 B，該使用者而認可提示字元中建立使用者 B 的提示 「 訂閱者 」 表格。 使用者 B 接受，或認可，訂閱之後, 的確認提示會移除使用者 B 的提示 「 訂閱者 」 表格。</p>
<p>當某人訂閱使用者的目前狀態時，系統提示您設定為 0 表示使用者不是。</p></td>
<td><p>整數或 Token</p></td>
<td><p>0-500</p></td>
</tr>
</tbody>
</table>


根據預設，**預設原則**和**服務： 中型**當您部署 Lync Server 時，會安裝目前狀態原則。 下表說明兩個的目前狀態原則的特定設定。

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
<td><p>服務： 中等</p></td>
<td><p>需要更多使用者訂閱物件的目前狀態的應用程式的原則。</p></td>
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

