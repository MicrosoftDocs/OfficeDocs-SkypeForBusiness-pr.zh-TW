---
title: 'Lync Server 2013: Grant-csoupermission 所做的變更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfad0cf4b8b863cd19d4d4113241477de1a50aaf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a>Grant-csoupermission Lync Server 2013 中所做的變更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-06-20 個_

若要委派 Lync Server 2013 管理，您可以指定組織單位 (Ou) 來新增權限，使樹系準備所建立的 RTC 萬用群組的成員能夠存取 Ou 不需要以 Domain Admins 群組的成員。

**Grant-csoupermission** cmdlet 授與權限給所指定的下列表格中所指定 OU 中的物件。

<div>

## <a name="granting-permission-for-user-objects"></a>授與使用者物件的權限

當您針對 OU 執行**Grant-csoupermission** cmdlet 的使用者物件時，群組會授與權限，如下表所示。

### <a name="permissions-granted-for-user-objects"></a>使用者物件的授與的權限

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
<th>權限</th>
<th>適用於</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>「 複寫目錄變更</p></td>
<td><p>只有此物件</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>列出內容</p>
<p>讀取所有內容</p>
<p>讀取權限</p></td>
<td><p>只有此物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>列出內容</p>
<p>讀取所有內容</p>
<p>讀取權限</p></td>
<td><p>只有此物件</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>讀取 RTCUserSearchPropertySet</p>
<p>讀取 RTCUserProvisioningPropertySet</p>
<p>讀取 RTCPropertySet</p>
<p>讀取 Public-information</p>
<p>讀取 General-information</p>
<p>讀取使用者帳戶限制</p></td>
<td><p>子系 User 物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>寫入 RTCUserSearchPropertySet</p>
<p>寫入 msExchUCVoiceMailSettings</p>
<p>寫入 RTCUserProvisioningPropertySet</p>
<p>寫入 RTCPropertySet</p>
<p>寫入 proxyAddresses</p></td>
<td><p>子系 User 物件</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a>授與 Computer 物件的權限

當您針對 OU 執行**Grant-csoupermission** cmdlet 的電腦物件時，群組會授與權限，如下表所示。

### <a name="permissions-granted-for-computer-objects"></a>電腦物件的授與的權限

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
<th>權限</th>
<th>適用於</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>「 複寫目錄變更</p></td>
<td><p>只有此物件</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>列出內容</p>
<p>讀取所有內容</p>
<p>讀取權限</p></td>
<td><p>只有此物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>列出內容</p>
<p>讀取所有內容</p>
<p>讀取權限</p></td>
<td><p>只有此物件</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>讀取 Public-information</p>
<p>讀取驗證型 DNS 主機的名稱</p></td>
<td><p>子系 Computer 物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>讀取 Public-information</p>
<p>讀取驗證型 DNS 主機的名稱</p></td>
<td><p>子系 Computer 物件</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a>授與 Contact 或 AppContact 物件的權限

當您針對 OU 執行**Grant-csoupermission** cmdlet 的 Contact 或 AppContact 物件時，會授與群組的權限，如下表所示。

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a>Contact 或 AppContact 物件的授與的權限

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
<th>權限</th>
<th>適用於</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>「 複寫目錄變更</p></td>
<td><p>只有此物件</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>列出內容</p>
<p>讀取所有內容</p>
<p>讀取權限</p></td>
<td><p>只有此物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>列出內容</p>
<p>讀取所有內容</p>
<p>讀取權限</p></td>
<td><p>只有此物件</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>讀取 RTCUserSearchPropertySet</p>
<p>讀取 RTCUserProvisioningPropertySet</p>
<p>讀取 RTCPropertySet</p>
<p>讀取 Public-information</p>
<p>讀取 General-information</p>
<p>讀取 Personal-information</p>
<p>讀取使用者帳戶限制</p></td>
<td><p>子系 Contact 物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>寫入 RTCUserSearchPropertySet</p>
<p>寫入 otherIpPhone</p>
<p>寫入 displayName</p>
<p>寫入 description</p>
<p>寫入 telephoneNumber</p>
<p>寫入 msExchUCVoiceMailSettings</p>
<p>寫入 RTCUserProvisioningPropertySet</p>
<p>寫入 RTCPropertySet</p>
<p>寫入 proxyAddresses</p></td>
<td><p>子系 Contact 物件</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a>授與 Device 物件的權限

當您執行**Grant-csoupermission** cmdlet Device 物件的 OU 上時，群組會授與權限，如下表所示。

### <a name="permissions-granted-for-device-objects"></a>裝置物件的授與的權限

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
<th>權限</th>
<th>適用於</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>「 複寫目錄變更</p></td>
<td><p>只有此物件</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>列出內容</p>
<p>讀取所有內容</p>
<p>讀取權限</p></td>
<td><p>只有此物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>列出內容</p>
<p>讀取所有內容</p>
<p>讀取權限</p></td>
<td><p>只有此物件</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>讀取 RTCUserSearchPropertySet</p>
<p>讀取 RTCUserProvisioningPropertySet</p>
<p>讀取 RTCPropertySet</p>
<p>讀取 Public-information</p>
<p>讀取 Personal-information</p>
<p>讀取 General-information</p>
<p>讀取使用者帳戶限制</p></td>
<td><p>子系 Contact 物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>建立子項</p>
<p>刪除子項</p>
<p>刪除樹狀目錄</p></td>
<td><p>連絡人</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>寫入 displayName</p>
<p>寫入 description</p>
<p>寫入 telephoneNumber</p></td>
<td><p>子系 User 物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>寫入 RTCUserSearchPropertySet</p>
<p>寫入 otherIpPhone</p>
<p>寫入 displayName</p>
<p>寫入 description</p>
<p>寫入 telephoneNumber</p>
<p>寫入 msExchUCVoiceMailSettings</p>
<p>寫入 RTCUserProvisioningPropertySet</p>
<p>寫入 RTCPropertySet</p>
<p>寫入 proxyAddresses</p></td>
<td><p>子系 Contact 物件</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a>授與 InetOrgPerson 物件的權限

當您執行**Grant-csoupermission** cmdlet InetOrgPerson 物件的 OU 上時，群組會授與權限，如下表所示。

### <a name="permissions-granted-for-inetorgperson-objects"></a>InetOrgPerson 物件的授與的權限

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Group</th>
<th>權限</th>
<th>適用於</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>「 複寫目錄變更</p></td>
<td><p>只有此物件</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>列出內容</p>
<p>讀取所有內容</p>
<p>讀取權限</p></td>
<td><p>只有此物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>列出內容</p>
<p>讀取所有內容</p>
<p>讀取權限</p></td>
<td><p>只有此物件</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>讀取 RTCUserSearchPropertySet</p>
<p>讀取 RTCUserProvisioningPropertySet</p>
<p>讀取 RTCPropertySet</p>
<p>讀取 Personal-information</p>
<p>讀取 Public-information</p>
<p>讀取 General-information</p>
<p>讀取使用者帳戶限制</p></td>
<td><p>子系 inetOrgPerson 物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>寫入 RTCUserSearchPropertySet</p>
<p>寫入 RTCUserProvisioningPropertySet</p>
<p>寫入 RTCPropertySet</p>
<p>寫入 proxyAddresses</p></td>
<td><p>子系 inetOrgPerson 物件</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

