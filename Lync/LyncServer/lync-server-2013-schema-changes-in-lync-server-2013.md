---
title: Lync Server 2013： Lync Server 2013 中的架構變更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bbe1c08b7d03042be2c03511103bfa4e43d39d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a>Lync Server 2013 中的架構變更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

在您部署並操作 Lync Server 2013 之前，您必須透過延伸架構來準備 Active Directory 網域服務。 架構延伸會新增 Lync Server 2013 所需的類別和屬性。

Lync Server 2013 需要幾個新的類別和屬性，並修改一些現有的類別和屬性。 此外，Lync Server 2013 的許多配置資訊會儲存在中央管理儲存區中，而不是在 AD DS 中，就像在舊版中一樣。 下列資訊仍會儲存在 Lync Server 2013 的 AD DS 中：

  - **架構擴充**：
    
      - 使用者物件延伸
    
      - Office 通訊伺服器2007與 Office 通訊伺服器 2007 R2 類別的擴充功能，可維持與支援的早期版本的向後相容性

<!-- end list -->

  - **資料**（儲存在 Lync Server 擴展架構和現有的架構類別中）：
    
      - 使用者 SIP 統一資源識別項（URI）及其他使用者設定
    
      - 回應群組和會議助理等應用程式的連絡人物件
    
      - 指向中央管理存放區的指標
    
      - Kerberos 驗證帳戶（選擇性電腦物件）

本主題說明 Lync Server 2013 所需的 Active Directory 架構變更。 它不會說明舊版 Office 通訊伺服器所引入的架構變更。 如需類別及其描述的清單，請參閱[Lync Server 2013 中的架構類別與說明](lync-server-2013-schema-classes-and-descriptions.md)。 如需屬性及其描述的清單，請參閱[Lync Server 2013 中的架構屬性及描述](lync-server-2013-schema-attributes-and-descriptions.md)。 如需具有它們可能包含之屬性的類別清單，請參閱[Lync Server 2013 中的類別的架構屬性](lync-server-2013-schema-attributes-by-class.md)。

MsRTCSIP 首碼會識別 Lync Server 專用的類別和屬性。

<div>

## <a name="new-active-directory-attributes"></a>新的 Active Directory 屬性

下表說明 Lync Server 2013 新增的 Active Directory 屬性。

### <a name="attributes-added-by-lync-server-2013"></a>Lync Server 2013 新增的屬性

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attribute</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>這個多重值屬性包含適用于使用者的保留原則的識別碼。 保留原則在保留期間保留使用者的信箱專案。 這個屬性是與 Exchange 2013 共用的。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>這是 SIP 路由群組識別碼。 相同群組中的使用者會註冊到相同的前端伺服器。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>這個屬性是用來儲存前端池所使用的鏡像 SQL Server 後端。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a>已修改的 Active Directory 類別

下表說明 Lync Server 2013 修改的 Active Directory 類別。

### <a name="classes-modified-by-lync-server-2013"></a>Lync Server 2013 修改的類別

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>靜態類</th>
<th>切換</th>
<th>類別或屬性</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>使用者</p></td>
<td><p>新增： mayContain</p>
<p>新增： mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="even">
<td><p>資訊</p></td>
<td><p>新增： mayContain</p>
<p>新增： mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="odd">
<td><p>郵件-收件者</p></td>
<td><p>新增： mayContain</p></td>
<td><p>msExchUserHoldPolicies</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>新增： mayContain</p></td>
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

