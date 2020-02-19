---
title: Lync Server 2013： 的常設聊天室伺服器的 DNS 需求
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
ms.openlocfilehash: 31ea713c05dbfa3e9dca2a326f228831f189ca22
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137031"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-persistent-chat-servers-in-lync-server-2013"></a><span data-ttu-id="510bc-102">在 Lync Server 2013 常設聊天室伺服器的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="510bc-102">DNS requirements for Persistent Chat Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="510bc-103">_**主題上次修改日期：** 2012年-06-28_</span><span class="sxs-lookup"><span data-stu-id="510bc-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="510bc-104">本節說明 Persistent Chat Server 的部署所需的網域名稱系統 (DNS) 記錄。</span><span class="sxs-lookup"><span data-stu-id="510bc-104">This section describes the Domain Name System (DNS) records that are required for deployment of Persistent Chat Servers.</span></span>

<div>

## <a name="dns-records-for-persistent-chat-servers"></a><span data-ttu-id="510bc-105">常設聊天室伺服器的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="510bc-105">DNS Records for Persistent Chat Servers</span></span>

<span data-ttu-id="510bc-106">下表指定 Persistent Chat Server 部署的 DNS 需求。</span><span class="sxs-lookup"><span data-stu-id="510bc-106">The following table specifies DNS requirements for Persistent Chat Server deployment.</span></span>

### <a name="dns-requirements-for-a-persistent-chat-server"></a><span data-ttu-id="510bc-107">Persistent Chat Server 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="510bc-107">DNS Requirements for a Persistent Chat Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="510bc-108">部署案例</span><span class="sxs-lookup"><span data-stu-id="510bc-108">Deployment scenario</span></span></th>
<th><span data-ttu-id="510bc-109">DNS 需求</span><span class="sxs-lookup"><span data-stu-id="510bc-109">DNS requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="510bc-110">一部常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="510bc-110">One Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="510bc-111">一筆內部 A 記錄，用來將伺服器的完整網域名稱 (FQDN) 解析為 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="510bc-111">An internal A record that resolves the fully qualified domain name (FQDN) of the server to its IP address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="510bc-112">常設聊天室集區</span><span class="sxs-lookup"><span data-stu-id="510bc-112">Persistent Chat pool</span></span></p></td>
<td><p><span data-ttu-id="510bc-113">一筆內部 A 記錄，解析為 IP 位址的伺服器的完整的網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="510bc-113">An internal A record that resolves the fully qualified domain name (FQDN) of the servers to its IP address.</span></span></p>
<p><span data-ttu-id="510bc-114"><strong>範例</strong></span><span class="sxs-lookup"><span data-stu-id="510bc-114"><strong>Example</strong></span></span></p>
<p><span data-ttu-id="510bc-115">PersistentChatServer01.contoso.com 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="510bc-115">PersistentChatServer01.contoso.com     10.10.10.1</span></span></p>
<p><span data-ttu-id="510bc-116">PersistentChatServer02.contoso.com 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="510bc-116">PersistentChatServer02.contoso.com     10.10.10.2</span></span></p>
<p><span data-ttu-id="510bc-117">一筆內部 A 記錄，解析為 IP 位址的伺服器的完整的網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="510bc-117">An internal A record that resolves the fully qualified domain name (FQDN) of the servers to its IP address.</span></span></p>
<p><span data-ttu-id="510bc-118"><strong>範例</strong></span><span class="sxs-lookup"><span data-stu-id="510bc-118"><strong>Example</strong></span></span></p>
<p><span data-ttu-id="510bc-119">PersistentChatPool.contoso.com 10.10.10.1</span><span class="sxs-lookup"><span data-stu-id="510bc-119">PersistentChatPool.contoso.com    10.10.10.1</span></span></p>
<p><span data-ttu-id="510bc-120">PersistentChatPool.contoso.com 10.10.10.2</span><span class="sxs-lookup"><span data-stu-id="510bc-120">PersistentChatPool.contoso.com    10.10.10.2</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

