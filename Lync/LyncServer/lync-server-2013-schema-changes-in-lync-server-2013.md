---
title: Lync Server 2013： Lync Server 2013 中的架構變更
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
ms.openlocfilehash: 1c3733eee90fb1ea0bb3e0a67be88243dee56aa7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510780"
---
# <a name="schema-changes-in-lync-server-2013"></a>Lync Server 2013 中的架構變更

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

在您部署及操作 Lync Server 2013 之前，您必須透過擴充架構來準備 Active Directory 網域服務。 架構擴充新增了 Lync Server 2013 所需的類別和屬性。

Lync Server 2013 需要數個新的類別和屬性，並修改一些現有的類別和屬性。 此外，Lync Server 2013 的大部分設定資訊都會儲存在中央管理存放區，而不是在 AD DS 中，就像先前的版本一樣。 下列資訊仍儲存在 Lync Server 2013 的 AD DS 中：

  - **架構擴充**：
    
      - 使用者物件擴充
    
      - Office 通訊伺服器2007和 Office 通訊伺服器 2007 R2 類別的分機，以維持與支援的舊版的回溯相容性

<!-- end list -->

  - 儲存在 Lync Server 擴充架構和現有架構類別中的**資料** () ：
    
      - 使用者 SIP 統一資源識別項 (URI) 和其他使用者設定
    
      - 回應群組和會議助理等應用程式的連絡人物件
    
      - 中央管理存放區的指標
    
      - Kerberos 驗證帳戶 (選用的電腦物件) 

本主題說明 Lync Server 2013 所需的 Active Directory 架構變更。 它不會描述先前版本的 Office 通訊伺服器所引進的架構變更。 如需類別及其描述的清單，請參閱 [Lync Server 2013 中的架構類別和描述](lync-server-2013-schema-classes-and-descriptions.md)。 如需屬性及其描述的清單，請參閱 [Lync Server 2013 中的架構屬性和描述](lync-server-2013-schema-attributes-and-descriptions.md)。 如需其屬性可能包含的類別清單，請參閱 [在 Lync Server 2013 中依類別的架構屬性](lync-server-2013-schema-attributes-by-class.md)。

MsRTCSIP 首碼可識別 Lync Server 專用的類別和屬性。

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
<th>屬性</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>此多重值屬性包含適用于使用者之保留原則的識別碼。 保留原則會在保留期間保留使用者的信箱專案。 此屬性與 Exchange 2013 共用。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP UserRoutingGroupId</p></td>
<td><p>這是 SIP 路由群組識別碼。 相同群組中的使用者會註冊到同一個前端伺服器。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP MirrorBackEndServer</p></td>
<td><p>此屬性用來儲存前端集區所使用的鏡像 SQL Server 後端。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a>修改的 Active Directory 類別

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
<p>msRTCSIP UserRoutingGroupId</p></td>
</tr>
<tr class="even">
<td><p>連絡人</p></td>
<td><p>add: mayContain</p>
<p>add: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP UserRoutingGroupId</p></td>
</tr>
<tr class="odd">
<td><p>Mail-Recipient</p></td>
<td><p>add: mayContain</p></td>
<td><p>msExchUserHoldPolicies</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP GlobalTopologySetting</p></td>
<td><p>add: mayContain</p></td>
<td><p>msRTCSIP MirrorBackEndServer</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

