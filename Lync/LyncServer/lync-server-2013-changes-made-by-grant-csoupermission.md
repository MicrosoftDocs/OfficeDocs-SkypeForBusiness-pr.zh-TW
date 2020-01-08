---
title: Lync Server 2013：由授與授權所做的變更 CsOUPermission
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ce6b16dff48afeeec848024d763655695905008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a>在 Lync Server 2013 中由 Grant CsOUPermission 所做的變更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-20_

若要委派 Lync Server 2013 管理，您可以在指定的組織單位（Ou）中新增許可權，以便由林準備建立的 RTC 通用群組成員可以存取 Ou，而不是網域管理員群組的成員。

**Grant CsOuPermission** Cmdlet 會根據下表中的指定，將許可權授與指定 OU 中的物件。

<div>

## <a name="granting-permission-for-user-objects"></a>授與使用者物件的許可權

當您針對 OU 中的使用者物件執行**Grant CsOuPermission** Cmdlet 時，系統會授與群組的許可權，如下表所示。

### <a name="permissions-granted-for-user-objects"></a>授與使用者物件的許可權

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>群組</th>
<th>拒絕</th>
<th>適用于</th>
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
<td><p>閱讀 RTCUserSearchPropertySet</p>
<p>閱讀 RTCUserProvisioningPropertySet</p>
<p>閱讀 RTCPropertySet</p>
<p>閱讀公用資訊</p>
<p>閱讀一般資訊</p>
<p>閱讀使用者-帳戶限制</p></td>
<td><p>後代使用者物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>撰寫 RTCUserSearchPropertySet</p>
<p>撰寫 msExchUCVoiceMailSettings</p>
<p>撰寫 RTCUserProvisioningPropertySet</p>
<p>撰寫 RTCPropertySet</p>
<p>撰寫 proxyAddresses</p></td>
<td><p>後代使用者物件</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a>授與電腦物件的許可權

當您針對 OU 中的電腦物件執行**Grant CsOuPermission** Cmdlet 時，系統會授與群組的許可權，如下表所示。

### <a name="permissions-granted-for-computer-objects"></a>授與電腦物件的許可權

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>群組</th>
<th>拒絕</th>
<th>適用于</th>
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
<td><p>閱讀公用資訊</p>
<p>已驗證閱讀-DNS 主機名稱</p></td>
<td><p>後代電腦物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>閱讀公用資訊</p>
<p>已驗證閱讀-DNS 主機名稱</p></td>
<td><p>後代電腦物件</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a>授予連絡人或 AppContact 物件的許可權

當您在 OU 上執行連絡人物件或 AppContact 物件的**Grant CsOuPermission** Cmdlet 時，系統會授與群組的許可權，如下表所示。

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
<th>拒絕</th>
<th>適用于</th>
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
<td><p>閱讀 RTCUserSearchPropertySet</p>
<p>閱讀 RTCUserProvisioningPropertySet</p>
<p>閱讀 RTCPropertySet</p>
<p>閱讀公用資訊</p>
<p>閱讀一般資訊</p>
<p>閱讀個人資訊</p>
<p>閱讀使用者-帳戶限制</p></td>
<td><p>子代連絡人物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>撰寫 RTCUserSearchPropertySet</p>
<p>撰寫 otherIpPhone</p>
<p>寫入 displayName</p>
<p>撰寫描述</p>
<p>撰寫 Telephonenumber 相同</p>
<p>撰寫 msExchUCVoiceMailSettings</p>
<p>撰寫 RTCUserProvisioningPropertySet</p>
<p>撰寫 RTCPropertySet</p>
<p>撰寫 proxyAddresses</p></td>
<td><p>子代連絡人物件</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a>為裝置物件授與許可權

當您針對 OU 中的裝置物件執行**Grant CsOuPermission** Cmdlet 時，系統會授與群組的許可權，如下表所示。

### <a name="permissions-granted-for-device-objects"></a>針對裝置物件所授的許可權

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>群組</th>
<th>拒絕</th>
<th>適用于</th>
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
<td><p>閱讀 RTCUserSearchPropertySet</p>
<p>閱讀 RTCUserProvisioningPropertySet</p>
<p>閱讀 RTCPropertySet</p>
<p>閱讀公用資訊</p>
<p>閱讀個人資訊</p>
<p>閱讀一般資訊</p>
<p>閱讀使用者-帳戶限制</p></td>
<td><p>子代連絡人物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>建立子系</p>
<p>刪除子系</p>
<p>刪除樹</p></td>
<td><p>資訊</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>寫入 displayName</p>
<p>撰寫描述</p>
<p>撰寫 Telephonenumber 相同</p></td>
<td><p>後代使用者物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>撰寫 RTCUserSearchPropertySet</p>
<p>撰寫 otherIpPhone</p>
<p>寫入 displayName</p>
<p>撰寫描述</p>
<p>撰寫 Telephonenumber 相同</p>
<p>撰寫 msExchUCVoiceMailSettings</p>
<p>撰寫 RTCUserProvisioningPropertySet</p>
<p>撰寫 RTCPropertySet</p>
<p>撰寫 proxyAddresses</p></td>
<td><p>子代連絡人物件</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a>授予 InetOrgPerson 物件的許可權

當您針對 OU 上的 InetOrgPerson 物件執行**Grant CsOuPermission** Cmdlet 時，系統會授與群組的許可權，如下表所示。

### <a name="permissions-granted-for-inetorgperson-objects"></a>授與 InetOrgPerson 物件的許可權

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>群組</th>
<th>拒絕</th>
<th>適用于</th>
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
<td><p>閱讀 RTCUserSearchPropertySet</p>
<p>閱讀 RTCUserProvisioningPropertySet</p>
<p>閱讀 RTCPropertySet</p>
<p>閱讀個人資訊</p>
<p>閱讀公用資訊</p>
<p>閱讀一般資訊</p>
<p>閱讀使用者-帳戶限制</p></td>
<td><p>子代 inetOrgPerson 物件</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>撰寫 RTCUserSearchPropertySet</p>
<p>撰寫 RTCUserProvisioningPropertySet</p>
<p>撰寫 RTCPropertySet</p>
<p>撰寫 proxyAddresses</p></td>
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

