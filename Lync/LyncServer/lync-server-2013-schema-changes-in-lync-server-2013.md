---
title: Lync Server 2013 中的 Lync Server 2013： 結構描述變更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 789a6a67b1794eee5f01e8672f9aeb1076646ecf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a>Lync Server 2013 中的結構描述變更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-18_

部署及操作 Lync Server 2013 之前，您必須準備 Active Directory 網域服務來擴充架構。 架構延伸模組新增的類別和 Lync Server 2013 所需的屬性。

Lync Server 2013 需要數個新的類別和屬性，並修改某些現有類別和屬性。 此外，針對 Lync Server 2013 多組態資訊而不是 AD DS 中的中央管理存放區中儲存在舊版中。 Lync Server 2013 中的 AD DS 中仍儲存下列資訊：

  - **架構延伸模組**：
    
      - 使用者物件延伸
    
      - Office Communications Server 2007 和 Office Communications Server 2007 R2 類別，以維持與支援的舊版的回溯相容性的副檔名

<!-- end list -->

  - **資料**（儲存在 Lync Server 延伸架構和現有的架構類別中）：
    
      - 使用者的 SIP 統一資源識別元 (URI) 及其他使用者設定
    
      - 回應群組與會議服務員等應用程式的連絡人物件
    
      - 中央管理存放區的指標
    
      - Kerberos 驗證帳戶 （選擇性的電腦物件）

本主題說明所需的 Lync Server 2013 的 Active Directory 架構變更。 它不會說明舊版 Office Communications Server 所引進的架構變更。 類別和及其描述的清單，請參閱[架構類別和 Lync Server 2013 中的描述](lync-server-2013-schema-classes-and-descriptions.md)。 屬性和及其描述的清單，請參閱[結構描述的屬性和 Lync Server 2013 中的描述](lync-server-2013-schema-attributes-and-descriptions.md)。 如需類別與屬性的清單它們可能包含，請參閱[結構描述由 Lync Server 2013 中的類別的屬性](lync-server-2013-schema-attributes-by-class.md)。

MsRTCSIP 前置詞會識別類別和 Lync 伺服器特有的屬性。

<div>

## <a name="new-active-directory-attributes"></a>新的 Active Directory 屬性

下表說明新增的 Lync Server 2013 的 Active Directory 屬性。

### <a name="attributes-added-by-lync-server-2013"></a>新增 Lync Server 2013 的屬性

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>屬性</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>此多重值屬性包含識別碼保留套用到使用者的原則。 保留原則的保留期間保留使用者的信箱項目。 Exchange 2013 可共用此屬性。</p></td>
</tr>
<tr class="even">
<td><p>包含 UserRoutingGroupId</p></td>
<td><p>這是 SIP 路由群組識別碼。 相同群組中的使用者將登錄至同一個前端伺服器。</p></td>
</tr>
<tr class="odd">
<td><p>包含 MirrorBackEndServer</p></td>
<td><p>此屬性用來儲存前端集區所使用的鏡像的 SQL Server 後端。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a>已修改的 Active Directory 類別

下表說明修改的 Lync Server 2013 的 Active Directory 類別。

### <a name="classes-modified-by-lync-server-2013"></a>Lync Server 2013 所修改的類別

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>類別</th>
<th>變更</th>
<th>類別或屬性</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>使用者</p></td>
<td><p>add: mayContain</p>
<p>add: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>包含 UserRoutingGroupId</p></td>
</tr>
<tr class="even">
<td><p>連絡人</p></td>
<td><p>add: mayContain</p>
<p>add: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>包含 UserRoutingGroupId</p></td>
</tr>
<tr class="odd">
<td><p>Mail-Recipient</p></td>
<td><p>add: mayContain</p></td>
<td><p>msExchUserHoldPolicies</p></td>
</tr>
<tr class="even">
<td><p>包含 GlobalTopologySetting</p></td>
<td><p>add: mayContain</p></td>
<td><p>包含 MirrorBackEndServer</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

