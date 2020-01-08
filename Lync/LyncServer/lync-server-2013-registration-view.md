---
title: Lync Server 2013： [註冊] 視圖
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe1b01b748204d3d4365b6f28ae4480d3632b35a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a>Lync Server 2013 中的 [註冊] 視圖

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

[註冊] 視圖儲存使用者註冊的相關資訊。 此視圖是在 Lync Server 2013 中推出。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>左欄</th>
<th>資料類型</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>會話要求的時間。 與 SessionIdSeq 搭配使用，可唯一識別會話。 如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>識別會話的識別碼編號。 與 SessionIdTime 搭配使用，可唯一識別會話。 如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegisterTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>發生註冊的時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUri</strong></p></td>
<td><p>Nvarchar （450）</p></td>
<td><p>已登錄之使用者的 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUriType</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>已登錄之使用者的 URI 類型。 如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserTenant</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>已註冊的使用者租使用者。 如需詳細資訊，請參閱<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中</a>的 [承租人] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>已登錄之使用者之端點的唯一識別碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>EndpointEra</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>唯一識別碼，用於區分涉及相同使用者和同一個端點的登記。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterType</strong></p></td>
<td><p>datetime</p></td>
<td><p>發生取消註冊的時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeRegisterReason</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>取消註冊的原因。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>註冊的使用者所使用的用戶端版本。</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>已註冊的使用者所使用的用戶端。 如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中</a>的 [UserAgentDef] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>Nvarchar （64）</p></td>
<td><p>已註冊的使用者所使用的用戶端類別。</p></td>
</tr>
<tr class="even">
<td><p><strong>IpAddress</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>使用者註冊的 IP 位址。 這可能是 IPv4 或 IPv6 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring （775）</p></td>
<td><p>SIP 對話方塊識別碼。 的格式為：</p>
<p>對話方塊; 從標籤; 到標籤</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>SIP 回應程式碼加入會話邀請。 這個欄位通常是由會話中初始邀請郵件所產生的資料所填入。 如果沒有邀請郵件，則會使用第一個相關 SIP 訊息（再見、CANCEL、MESSAGE 或 INFO）的日期和時間來填入欄位。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p>從 SIP 標頭捕獲的診斷 ID。</p></td>
</tr>
<tr class="even">
<td><p><strong>註冊機構</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>註冊機構的 FQDN。</p></td>
</tr>
<tr class="odd">
<td><p><strong>集區</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>捕獲會話資料之池的 FQDN。</p></td>
</tr>
<tr class="even">
<td><p><strong>EdgeServer</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>已註冊的使用者所使用的邊緣伺服器 FQDN。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsInternal</strong></p></td>
<td><p>稍微</p></td>
<td><p>指示使用者是否從內部網路登入。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>稍微</p></td>
<td><p>指示在註冊時間是否可以使用 UserService。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>稍微</p></td>
<td><p>指出註冊是否與主要註冊機構一起使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceMacAddress</strong></p></td>
<td><p>Bigint</p></td>
<td><p>已註冊的裝置 MAC 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceManufacturer</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>已註冊裝置的製造商。 如需詳細資訊，請參閱<a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中</a>的 [製造商] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHardwareVersion</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>已註冊裝置的硬體版本。 如需詳細資訊，請參閱<a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中</a>的 [HardwareVersions] 資料表。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

