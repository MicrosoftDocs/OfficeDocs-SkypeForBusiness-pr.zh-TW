---
title: Lync Server 2013：憑證摘要 - 反向 Proxy
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42e52fa8522de53404fee3f3b5798f159361dbf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="7fc51-102">Lync Server 2013 中的憑證摘要 - 反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="7fc51-102">Certificate summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fc51-103">_**主題上次修改日期：** 2012-11-14_</span><span class="sxs-lookup"><span data-stu-id="7fc51-103">_**Topic Last Modified:** 2012-11-14_</span></span>

<span data-ttu-id="7fc51-104">反向 proxy 的憑證需求比邊緣伺服器更簡單。</span><span class="sxs-lookup"><span data-stu-id="7fc51-104">Certificate requirements for the reverse proxy are much simpler than that for the Edge Servers.</span></span> <span data-ttu-id="7fc51-105">提供的流程圖提供必要的需求。</span><span class="sxs-lookup"><span data-stu-id="7fc51-105">The provided flowchart presents the requirements necessary.</span></span> <span data-ttu-id="7fc51-106">隨附的表格針對我們在 Edge 伺服器討論中審查的案例，提供典型的憑證受領人名稱和消費者替換名稱。</span><span class="sxs-lookup"><span data-stu-id="7fc51-106">The accompanying table presents typical certificate subject name and subject alternative names in relation to the scenarios that we have been reviewed in the Edge Server discussions.</span></span> <span data-ttu-id="7fc51-107">如需有關 Edge 伺服器案例的詳細資訊，請參閱[Lync server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="7fc51-107">For more details on the Edge Server scenarios, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="7fc51-108">**反向 Proxy 的憑證流程圖**</span><span class="sxs-lookup"><span data-stu-id="7fc51-108">**Certificates Flow Chart for Reverse Proxy**</span></span>

<span data-ttu-id="7fc51-109">![Edge Server 的憑證流程圖](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Edge Server 的憑證流程圖")</span><span class="sxs-lookup"><span data-stu-id="7fc51-109">![Certificates Flow Chart for Edge Server](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Certificates Flow Chart for Edge Server")</span></span>

### <a name="reverse-proxy-external-interface"></a><span data-ttu-id="7fc51-110">反向 Proxy：外部介面</span><span class="sxs-lookup"><span data-stu-id="7fc51-110">Reverse Proxy: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7fc51-111">元件</span><span class="sxs-lookup"><span data-stu-id="7fc51-111">Component</span></span></th>
<th><span data-ttu-id="7fc51-112">消費者名稱</span><span class="sxs-lookup"><span data-stu-id="7fc51-112">Subject name</span></span></th>
<th><span data-ttu-id="7fc51-113">Subject 備用名稱（SAN）/Order</span><span class="sxs-lookup"><span data-stu-id="7fc51-113">Subject alternative name (SAN)/Order</span></span></th>
<th><span data-ttu-id="7fc51-114">批註</span><span class="sxs-lookup"><span data-stu-id="7fc51-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7fc51-115">反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="7fc51-115">Reverse Proxy</span></span></p></td>
<td><p><span data-ttu-id="7fc51-116">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7fc51-116">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7fc51-117">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7fc51-117">webext.contoso.com</span></span></p>
<p><span data-ttu-id="7fc51-118">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7fc51-118">webdirext.contoso.com</span></span></p>
<p><span data-ttu-id="7fc51-119">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7fc51-119">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="7fc51-120">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7fc51-120">meet.contoso.com</span></span></p>
<p><span data-ttu-id="7fc51-121">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7fc51-121">officewebapps01.contoso.com</span></span></p>
<p><span data-ttu-id="7fc51-122">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7fc51-122">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="7fc51-123">（選擇性）:\*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="7fc51-123">(Optional):\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="7fc51-124">證書必須由公用 CA 以及伺服器 EKU 所頒發。</span><span class="sxs-lookup"><span data-stu-id="7fc51-124">Certificate must be issued by a public CA and with the server EKU.</span></span> <span data-ttu-id="7fc51-125">服務包括通訊錄服務、通訊群組擴充會議的 Office Web Apps，以及 Lync IP 裝置發佈規則。</span><span class="sxs-lookup"><span data-stu-id="7fc51-125">Services include Address Book Service, distribution group expansion Office Web Apps for conferencing, and Lync IP Device publishing rules.</span></span> <span data-ttu-id="7fc51-126">消費者備用名稱包括：</span><span class="sxs-lookup"><span data-stu-id="7fc51-126">Subject alternative name includes:</span></span></p>
<ul>
<li><p><span data-ttu-id="7fc51-127">前端伺服器或頂層端池的外部 Web 服務 FQDN</span><span class="sxs-lookup"><span data-stu-id="7fc51-127">External Web Services FQDN for Front End Server or Front End pool</span></span></p></li>
<li><p><span data-ttu-id="7fc51-128">主管或主管池的外部 Web 服務 FQDN</span><span class="sxs-lookup"><span data-stu-id="7fc51-128">External Web Services FQDN for Director or Director pool</span></span></p></li>
<li><p><span data-ttu-id="7fc51-129">電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="7fc51-129">Dial-in conferencing</span></span></p></li>
<li><p><span data-ttu-id="7fc51-130">線上會議發佈規則</span><span class="sxs-lookup"><span data-stu-id="7fc51-130">Online meeting publishing rule</span></span></p></li>
<li><p><span data-ttu-id="7fc51-131">適用于會議的 Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="7fc51-131">Office Web Apps for conferencing</span></span></p></li>
<li><p><span data-ttu-id="7fc51-132">Lyncdiscover （自動探索）</span><span class="sxs-lookup"><span data-stu-id="7fc51-132">Lyncdiscover (Autodiscover)</span></span></p></li>
</ul>
<p><span data-ttu-id="7fc51-133">選用的萬用字元會取代 [開會] 和 [撥入] SAN</span><span class="sxs-lookup"><span data-stu-id="7fc51-133">The optional wildcard replaces both meet and dialin SAN</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

