---
title: Lync Server 2013： Grant-CsOUPermission 所做的變更
description: Lync Server 2013： Grant-CsOUPermission 所做的變更。
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
ms.openlocfilehash: 10d3db0e9dde380628690bc016e2b4bd2ec85b54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543609"
---
# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a>Lync Server 2013 中 Grant-CsOUPermission 所做的變更

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-20_

若要委派 Lync Server 2013 管理，您可以將許可權新增至指定的組織單位 (Ou) ，以便樹系準備所建立的 RTC 通用群組成員可以存取 Ou，而不是 Domain Admins 群組的成員。

**Grant-CsOuPermission** Cmdlet 會依照下表所指定的方式，將許可權授與指定之 OU 中的物件。

<div>

## <a name="granting-permission-for-user-objects"></a>授與使用者物件的許可權

當您為 OU 上的使用者物件執行 **Grant-CsOuPermission** Cmdlet 時，會將許可權授與下表所示的許可權。

### <a name="permissions-granted-for-user-objects"></a>使用者物件的授與許可權

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>群組</th>
<th>權限</th>
<th>適用於</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>複製目錄變更</p></td>
<td><p>僅限這個物件</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>清單內容</p>
<p>讀取所有屬性</p>
<p>讀取權限</p></td>
<td><p>僅限這個物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>清單內容</p>
<p>讀取所有屬性</p>
<p>讀取權限</p></td>
<td><p>僅限這個物件</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>讀取 RTCUserSearchPropertySet</p>
<p>讀取 RTCUserProvisioningPropertySet</p>
<p>讀取 RTCPropertySet</p>
<p>讀取 Public-Information</p>
<p>讀取 General-Information</p>
<p>讀取 User-Account-Restrictions</p></td>
<td><p>子代使用者物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>寫入 RTCUserSearchPropertySet</p>
<p>寫入 msExchUCVoiceMailSettings</p>
<p>寫入 RTCUserProvisioningPropertySet</p>
<p>寫入 RTCPropertySet</p>
<p>寫入 proxyAddresses</p></td>
<td><p>子代使用者物件</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a>授與電腦物件的許可權

當您為 OU 上的電腦物件執行 **Grant-CsOuPermission** Cmdlet 時，系統會將群組授與下表所示的許可權。

### <a name="permissions-granted-for-computer-objects"></a>電腦物件的授與許可權

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>群組</th>
<th>權限</th>
<th>適用於</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>複製目錄變更</p></td>
<td><p>僅限這個物件</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>清單內容</p>
<p>讀取所有屬性</p>
<p>讀取權限</p></td>
<td><p>僅限這個物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>清單內容</p>
<p>讀取所有屬性</p>
<p>讀取權限</p></td>
<td><p>僅限這個物件</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>讀取 Public-Information</p>
<p>讀取 Validated-DNS-Host-Name</p></td>
<td><p>子代電腦物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>讀取 Public-Information</p>
<p>讀取 Validated-DNS-Host-Name</p></td>
<td><p>子代電腦物件</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a>授與連絡人或 AppContact 物件的許可權

當您對 OU 上的連絡人物件或 AppContact 物件執行 **Grant-CsOuPermission** Cmdlet 時，會授與下表所示的許可權。

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a>授與連絡人或 AppContact 物件的許可權

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>群組</th>
<th>權限</th>
<th>適用於</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>複製目錄變更</p></td>
<td><p>僅限這個物件</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>清單內容</p>
<p>讀取所有屬性</p>
<p>讀取權限</p></td>
<td><p>僅限這個物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>清單內容</p>
<p>讀取所有屬性</p>
<p>讀取權限</p></td>
<td><p>僅限這個物件</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>讀取 RTCUserSearchPropertySet</p>
<p>讀取 RTCUserProvisioningPropertySet</p>
<p>讀取 RTCPropertySet</p>
<p>讀取 Public-Information</p>
<p>讀取 General-Information</p>
<p>讀取 Personal-Information</p>
<p>讀取 User-Account-Restrictions</p></td>
<td><p>子代連絡人物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>寫入 RTCUserSearchPropertySet</p>
<p>寫入 otherIpPhone</p>
<p>寫入 displayName</p>
<p>寫入描述</p>
<p>寫入 telephoneNumber</p>
<p>寫入 msExchUCVoiceMailSettings</p>
<p>寫入 RTCUserProvisioningPropertySet</p>
<p>寫入 RTCPropertySet</p>
<p>寫入 proxyAddresses</p></td>
<td><p>子代連絡人物件</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a>授與裝置物件的許可權

當您為 OU 上的裝置物件執行 **Grant-CsOuPermission** Cmdlet 時，會將許可權授與下表所示的許可權。

### <a name="permissions-granted-for-device-objects"></a>對 Device 物件授與的許可權

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>群組</th>
<th>權限</th>
<th>適用於</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>複製目錄變更</p></td>
<td><p>僅限這個物件</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>清單內容</p>
<p>讀取所有屬性</p>
<p>讀取權限</p></td>
<td><p>僅限這個物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>清單內容</p>
<p>讀取所有屬性</p>
<p>讀取權限</p></td>
<td><p>僅限這個物件</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>讀取 RTCUserSearchPropertySet</p>
<p>讀取 RTCUserProvisioningPropertySet</p>
<p>讀取 RTCPropertySet</p>
<p>讀取 Public-Information</p>
<p>讀取 Personal-Information</p>
<p>讀取 General-Information</p>
<p>讀取 User-Account-Restrictions</p></td>
<td><p>子代連絡人物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>建立子項</p>
<p>刪除子項</p>
<p>刪除樹</p></td>
<td><p>連絡人</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>寫入 displayName</p>
<p>寫入描述</p>
<p>寫入 telephoneNumber</p></td>
<td><p>子代使用者物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>寫入 RTCUserSearchPropertySet</p>
<p>寫入 otherIpPhone</p>
<p>寫入 displayName</p>
<p>寫入描述</p>
<p>寫入 telephoneNumber</p>
<p>寫入 msExchUCVoiceMailSettings</p>
<p>寫入 RTCUserProvisioningPropertySet</p>
<p>寫入 RTCPropertySet</p>
<p>寫入 proxyAddresses</p></td>
<td><p>子代連絡人物件</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a>授與 InetOrgPerson 物件的許可權

當您為 OU 上的 InetOrgPerson 物件執行 **Grant-CsOuPermission** Cmdlet 時，會將許可權授與下表所示的許可權。

### <a name="permissions-granted-for-inetorgperson-objects"></a>InetOrgPerson 物件的授與許可權

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>群組</th>
<th>權限</th>
<th>適用於</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>複製目錄變更</p></td>
<td><p>僅限這個物件</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>清單內容</p>
<p>讀取所有屬性</p>
<p>讀取權限</p></td>
<td><p>僅限這個物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>清單內容</p>
<p>讀取所有屬性</p>
<p>讀取權限</p></td>
<td><p>僅限這個物件</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>讀取 RTCUserSearchPropertySet</p>
<p>讀取 RTCUserProvisioningPropertySet</p>
<p>讀取 RTCPropertySet</p>
<p>讀取 Personal-Information</p>
<p>讀取 Public-Information</p>
<p>讀取 General-Information</p>
<p>讀取 User-Account-Restrictions</p></td>
<td><p>子代 inetOrgPerson 物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>寫入 RTCUserSearchPropertySet</p>
<p>寫入 RTCUserProvisioningPropertySet</p>
<p>寫入 RTCPropertySet</p>
<p>寫入 proxyAddresses</p></td>
<td><p>子代 inetOrgPerson 物件</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

