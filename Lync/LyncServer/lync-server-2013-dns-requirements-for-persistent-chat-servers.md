---
title: Lync Server 2013：持久聊天伺服器的 DNS 需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Persistent Chat Servers
ms:assetid: f7531374-d7ed-4b63-ae81-02294cb4496a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205391(v=OCS.15)
ms:contentKeyID: 48185857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b97d3238c64173cb5f9bfcfc12dce40f987da123
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-persistent-chat-servers-in-lync-server-2013"></a>Lync Server 2013 中持續聊天伺服器的 DNS 需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-28_

本節說明部署持久聊天伺服器時所需的網域名稱系統（DNS）記錄。

<div>

## <a name="dns-records-for-persistent-chat-servers"></a>持久聊天伺服器的 DNS 記錄

下表指定持續聊天伺服器部署的 DNS 需求。

### <a name="dns-requirements-for-a-persistent-chat-server"></a>持久聊天伺服器的 DNS 需求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>部署案例</th>
<th>DNS 需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>一個持續聊天伺服器</p></td>
<td><p>將伺服器的完整功能變數名稱（FQDN）解析成其 IP 位址的內部 A 記錄。</p></td>
</tr>
<tr class="even">
<td><p>持續聊天池</p></td>
<td><p>將伺服器的完整功能變數名稱（FQDN）解析成其 IP 位址的內部 A 記錄。</p>
<p><strong>範例</strong></p>
<p>PersistentChatServer01.contoso.com 10.10.10。1</p>
<p>PersistentChatServer02.contoso.com 10.10.10。2</p>
<p>將伺服器的完整功能變數名稱（FQDN）解析成其 IP 位址的內部 A 記錄。</p>
<p><strong>範例</strong></p>
<p>PersistentChatPool.contoso.com 10.10.10。1</p>
<p>PersistentChatPool.contoso.com 10.10.10。2</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

