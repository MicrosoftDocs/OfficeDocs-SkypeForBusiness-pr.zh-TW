---
title: Lync Server 2013： Persistent Chat Server 的 DNS 需求
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
ms.openlocfilehash: 055a55498247cdde540ceca44cc33187e2b9baca
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501380"
---
# <a name="dns-requirements-for-persistent-chat-servers-in-lync-server-2013"></a>Lync Server 2013 中 Persistent Chat Server 的 DNS 需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-28_

本節說明網域名稱系統 (DNS) 部署 Persistent Chat Server 所需的記錄。

<div>

## <a name="dns-records-for-persistent-chat-servers"></a>Persistent Chat Server 的 DNS 記錄

下表指定 Persistent Chat Server 部署的 DNS 需求。

### <a name="dns-requirements-for-a-persistent-chat-server"></a>Persistent Chat Server 的 DNS 需求

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
<td><p>一部 Persistent Chat Server</p></td>
<td><p>一筆內部 A 記錄，用來將伺服器的完整網域名稱 (FQDN) 解析為 IP 位址。</p></td>
</tr>
<tr class="even">
<td><p>Persistent Chat 集區</p></td>
<td><p>內部 A 記錄，可將伺服器的完整功能變數名稱 (FQDN) 解析為 IP 位址。</p>
<p><strong>範例</strong></p>
<p>PersistentChatServer01.contoso.com 10.10.10。1</p>
<p>PersistentChatServer02.contoso.com 10.10.10。2</p>
<p>內部 A 記錄，可將伺服器的完整功能變數名稱 (FQDN) 解析為 IP 位址。</p>
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

