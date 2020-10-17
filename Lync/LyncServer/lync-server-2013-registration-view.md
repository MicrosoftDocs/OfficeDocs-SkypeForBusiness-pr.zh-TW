---
title: Lync Server 2013：註冊視圖
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdf0e0edd69685af866905fea08144de327c446c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536580"
---
# <a name="registration-view-in-lync-server-2013"></a>Lync Server 2013 中的註冊視圖

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

[註冊] 視圖會儲存使用者註冊的相關資訊。 此視圖已引進 Lync Server 2013。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>欄</th>
<th>資料類型</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>工作階段要求的時間。 與 SessionIdSeq 搭配使用，以唯一識別工作階段。 如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>識別工作階段的 ID 號碼。 與 SessionIdTime 搭配使用，以唯一識別工作階段。 如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegisterTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>發生註冊的時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUri</strong></p></td>
<td><p>Nvarchar (450) </p></td>
<td><p>註冊之使用者的 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUriType</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>註冊之使用者的 URI 類型。 如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserTenant</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>註冊的使用者租使用者。 如需詳細資訊，請參閱 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的承租人資料表</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndpointId</strong></p></td>
<td><p>唯一</p></td>
<td><p>使用者已註冊之端點的唯一識別碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>EndpointEra</strong></p></td>
<td><p>唯一</p></td>
<td><p>唯一識別碼，用來區分包含相同使用者和相同端點的註冊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterType</strong></p></td>
<td><p>datetime</p></td>
<td><p>發生取消註冊的時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeRegisterReason</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>取消註冊的原因。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft.rtc.management.writableconfig.policy.clientversion.rule</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>註冊的使用者所使用的用戶端版本。</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>註冊的使用者所使用的用戶端。 如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>Nvarchar (64) </p></td>
<td><p>註冊的使用者所使用的用戶端類別。</p></td>
</tr>
<tr class="even">
<td><p><strong>址</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>使用者註冊的 IP 位址。 這可以是 IPv4 或 IPv6 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring (775) </p></td>
<td><p>SIP 對話方塊識別碼。 格式為：</p>
<p>dialog; 從-標籤; to-標記</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>工作階段邀請的 SIP 回應碼。此欄位通常會使用從工作階段之初始 INVITE 訊息中產生的資料來填入。如果沒有 INVITE 訊息，則會使用第一個相關的 SIP 訊息 (BYE、CANCEL、MESSAGE 或 INFO) 的日期與時間來填入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p>從 SIP 標頭擷取而來的診斷識別碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>處長</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>註冊機的 FQDN。</p></td>
</tr>
<tr class="odd">
<td><p><strong>集區</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>擷取工作階段適用之資料的集區 FQDN。</p></td>
</tr>
<tr class="even">
<td><p><strong>Edgeserver atl-edge</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>註冊之使用者所使用的 Edge Server FQDN。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsInternal</strong></p></td>
<td><p>位</p></td>
<td><p>指出使用者是否會從內部網路登入。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>位</p></td>
<td><p>會指出註冊時是否可使用 UserService。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>位</p></td>
<td><p>會指出註冊是否與主要註冊機。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceMacAddress</strong></p></td>
<td><p>Bigint</p></td>
<td><p>已登錄裝置的 MAC 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceManufacturer</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>已登錄裝置的製造商。 如需詳細資訊，請參閱 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中的製造商表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHardwareVersion</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>已登錄裝置的硬體版本。 如需詳細資訊，請參閱 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中的 HardwareVersions 表格</a> 。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

