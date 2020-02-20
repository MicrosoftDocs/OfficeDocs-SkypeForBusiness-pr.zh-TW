---
title: 'Lync Server 2013: Registration 表格'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d56f08db69fab4dfbf8da0c09d5d693bccf76bf2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a>Lync Server 2013 中的 registration 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-28_

每筆記錄都代表一個使用者註冊事件。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>欄</th>
<th>資料類型</th>
<th>主索引鍵 /</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主要、外部</p></td>
<td><p>工作階段要求的時間。 其會與 <strong>SessionIdSeq</strong> 搭配使用，專門用於識別工作階段。 <a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主要，外部</p></td>
<td><p>用來識別工作階段的識別碼。 會與 <strong>SessionIdTime</strong> 搭配使用，專門用於識別工作階段。 <a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>使用者識別碼。 請參閱如需詳細資訊，<a href="lync-server-2013-users-table.md">使用者在 Lync Server 2013 中的表格</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>EndpointId</strong></p></td>
<td><p>唯一</p></td>
<td></td>
<td><p>識別註冊端點的 GUID。通常，來自相同使用者電腦的註冊事件會具備相同的端點識別碼，不同的機器則會有不同的端點識別碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndpointEra</strong></p></td>
<td><p>唯一</p></td>
<td></td>
<td><p>用於區分相同使用者和相同端點相關之登錄的識別碼。</p>
<p>Microsoft Lync Server 2013 中已採用此欄位。</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>目前使用者的用戶端版本。 請參閱<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a>如需詳細資訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegistrarId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>登錄伺服器用於登錄的識別碼。 請參閱<a href="lync-server-2013-servers-table.md">Lync Server 2013 中的伺服器表格</a>如需詳細資訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>擷取工作階段所在集區的識別碼。 請參閱如需詳細資訊，<a href="lync-server-2013-pools-table.md">在 Lync Server 2013 中的集區資料表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>登錄通過的 Edge Server。 請參閱<a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表格</a>如需詳細資訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsInternal</strong></p></td>
<td><p>位元</p></td>
<td></td>
<td><p>使用者是否從內部登入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>位元</p></td>
<td></td>
<td><p>UserService 是否可供使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>位元</p></td>
<td></td>
<td><p>是否登錄至主要登錄器。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrarCentral</strong></p></td>
<td><p>位元</p></td>
<td></td>
<td><p>表示是否使用 Survivable Branch Appliance 登錄使用者。</p>
<p>Microsoft Lync Server 2013 中已採用此欄位。</p></td>
</tr>
<tr class="even">
<td><p><strong>RegisterTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>登錄時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>解除登錄時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>登錄要求的回應碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>登錄要求的診斷識別碼。這會指出診斷資訊類型。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>登錄要求的來源裝置。 請參閱<a href="lync-server-2013-devices-table.md">Lync Server 2013 中的裝置表</a>如需詳細資訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Foreign</p></td>
<td><p>解除登錄的原因，例如「由用戶端起始」、「註冊到期」或「用戶端失敗」等。 請參閱<a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 中的 DeRegisterType 表格</a>如需詳細資訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddress</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>使用者登錄所使用的端點 IP 位址。 可以是 IPv4 位址或 IPv6 位址。</p>
<p>Microsoft Lync Server 2013 中已採用此欄位。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

