---
title: 'Lync Server 2013: DNS 摘要-單一 Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44bcd52c2e7d13ef57e96e4ae5dc8841a58bc3d9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="498dc-102">DNS 摘要-Lync Server 2013 中的單一 Director</span><span class="sxs-lookup"><span data-stu-id="498dc-102">DNS summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="498dc-103">_**主題上次修改日期：** 2012年-10-20 個_</span><span class="sxs-lookup"><span data-stu-id="498dc-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="498dc-104">下表包含支援單一 Director 所需的 DNS 記錄摘要。</span><span class="sxs-lookup"><span data-stu-id="498dc-104">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="498dc-105">Director 角色為前端伺服器需要類似的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="498dc-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="498dc-106">Director 憑證上所需的主體替代名稱會反映所需的記錄筆數。</span><span class="sxs-lookup"><span data-stu-id="498dc-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="498dc-107">不同於前端伺服器，Director 不會主控使用者帳戶或裝載行動服務。</span><span class="sxs-lookup"><span data-stu-id="498dc-107">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="498dc-108">Director 的必要的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="498dc-108">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="498dc-109">位置/類型/連接埠</span><span class="sxs-lookup"><span data-stu-id="498dc-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="498dc-110">FQDN/DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="498dc-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="498dc-111">IP 位址/FQDN</span><span class="sxs-lookup"><span data-stu-id="498dc-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="498dc-112">對應至/註解</span><span class="sxs-lookup"><span data-stu-id="498dc-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="498dc-113">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="498dc-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="498dc-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="498dc-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="498dc-115">Director</span><span class="sxs-lookup"><span data-stu-id="498dc-115">Director</span></span></p></td>
<td><p><span data-ttu-id="498dc-116">用於複寫及伺服器對伺服器的 director 主機記錄</span><span class="sxs-lookup"><span data-stu-id="498dc-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="498dc-117">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="498dc-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="498dc-118">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="498dc-118">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="498dc-119">Director</span><span class="sxs-lookup"><span data-stu-id="498dc-119">Director</span></span></p></td>
<td><p><span data-ttu-id="498dc-120">輸入工作階段初始通訊協定 (SIP) 從 Edge Server 的內部 Edge 介面</span><span class="sxs-lookup"><span data-stu-id="498dc-120">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="498dc-121">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="498dc-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="498dc-122">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="498dc-122">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="498dc-123">Director</span><span class="sxs-lookup"><span data-stu-id="498dc-123">Director</span></span></p></td>
<td><p><span data-ttu-id="498dc-124">從反向 Proxy 發行的 Dialin Web 服務</span><span class="sxs-lookup"><span data-stu-id="498dc-124">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="498dc-125">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="498dc-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="498dc-126">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="498dc-126">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="498dc-127">Director</span><span class="sxs-lookup"><span data-stu-id="498dc-127">Director</span></span></p></td>
<td><p><span data-ttu-id="498dc-128">從反向 Proxy 發行的會議 Web 服務</span><span class="sxs-lookup"><span data-stu-id="498dc-128">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="498dc-129">內部 DNS/A</span><span class="sxs-lookup"><span data-stu-id="498dc-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="498dc-130">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="498dc-130">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="498dc-131">Director</span><span class="sxs-lookup"><span data-stu-id="498dc-131">Director</span></span></p></td>
<td><p><span data-ttu-id="498dc-132">發行和定義反向 proxy Web 票證外部 web 服務的 Director</span><span class="sxs-lookup"><span data-stu-id="498dc-132">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

