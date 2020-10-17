---
title: Lync Server 2013：憑證摘要-反向 proxy
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
ms.openlocfilehash: 25e83fb5857988396c3d13d2b07078c654972c92
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515740"
---
# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="e41dd-102">Lync Server 2013 的憑證摘要-反向 proxy</span><span class="sxs-lookup"><span data-stu-id="e41dd-102">Certificate summary - Reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e41dd-103">_**主題上次修改日期：** 2012-11-14_</span><span class="sxs-lookup"><span data-stu-id="e41dd-103">_**Topic Last Modified:** 2012-11-14_</span></span>

<span data-ttu-id="e41dd-104">反向 proxy 的憑證需求比 Edge Server 的憑證需求更簡單。</span><span class="sxs-lookup"><span data-stu-id="e41dd-104">Certificate requirements for the reverse proxy are much simpler than that for the Edge Servers.</span></span> <span data-ttu-id="e41dd-105">提供的流程圖提供必要的需求。</span><span class="sxs-lookup"><span data-stu-id="e41dd-105">The provided flowchart presents the requirements necessary.</span></span> <span data-ttu-id="e41dd-106">伴隨的表格提供一般的憑證主體名稱與主體別名，與我們在 Edge Server 討論中已複習的案例有關。</span><span class="sxs-lookup"><span data-stu-id="e41dd-106">The accompanying table presents typical certificate subject name and subject alternative names in relation to the scenarios that we have been reviewed in the Edge Server discussions.</span></span> <span data-ttu-id="e41dd-107">如需 Edge Server 案例的詳細資訊，請參閱 [Lync server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="e41dd-107">For more details on the Edge Server scenarios, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="e41dd-108">**反向 Proxy 的憑證流程圖表**</span><span class="sxs-lookup"><span data-stu-id="e41dd-108">**Certificates Flow Chart for Reverse Proxy**</span></span>

<span data-ttu-id="e41dd-109">![Edge Server 的憑證流程圖表](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Edge Server 的憑證流程圖表")</span><span class="sxs-lookup"><span data-stu-id="e41dd-109">![Certificates Flow Chart for Edge Server](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Certificates Flow Chart for Edge Server")</span></span>

### <a name="reverse-proxy-external-interface"></a><span data-ttu-id="e41dd-110">反向 Proxy：外部介面</span><span class="sxs-lookup"><span data-stu-id="e41dd-110">Reverse Proxy: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e41dd-111">元件</span><span class="sxs-lookup"><span data-stu-id="e41dd-111">Component</span></span></th>
<th><span data-ttu-id="e41dd-112">主體名稱</span><span class="sxs-lookup"><span data-stu-id="e41dd-112">Subject name</span></span></th>
<th><span data-ttu-id="e41dd-113"> (SAN) /Order 的主體替代名稱</span><span class="sxs-lookup"><span data-stu-id="e41dd-113">Subject alternative name (SAN)/Order</span></span></th>
<th><span data-ttu-id="e41dd-114">註解</span><span class="sxs-lookup"><span data-stu-id="e41dd-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e41dd-115">反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="e41dd-115">Reverse Proxy</span></span></p></td>
<td><p><span data-ttu-id="e41dd-116">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e41dd-116">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e41dd-117">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e41dd-117">webext.contoso.com</span></span></p>
<p><span data-ttu-id="e41dd-118">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e41dd-118">webdirext.contoso.com</span></span></p>
<p><span data-ttu-id="e41dd-119">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e41dd-119">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="e41dd-120">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e41dd-120">meet.contoso.com</span></span></p>
<p><span data-ttu-id="e41dd-121">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e41dd-121">officewebapps01.contoso.com</span></span></p>
<p><span data-ttu-id="e41dd-122">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e41dd-122">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="e41dd-123"> (選用) \:*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="e41dd-123">(Optional):\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="e41dd-124">憑證必須由公用 CA 和伺服器 EKU 所發行。</span><span class="sxs-lookup"><span data-stu-id="e41dd-124">Certificate must be issued by a public CA and with the server EKU.</span></span> <span data-ttu-id="e41dd-125">服務包括通訊錄服務、通訊群組擴充的 Office Web Apps for 會議，以及 Lync IP 裝置發行規則。</span><span class="sxs-lookup"><span data-stu-id="e41dd-125">Services include Address Book Service, distribution group expansion Office Web Apps for conferencing, and Lync IP Device publishing rules.</span></span> <span data-ttu-id="e41dd-126">主體替代名稱包括：</span><span class="sxs-lookup"><span data-stu-id="e41dd-126">Subject alternative name includes:</span></span></p>
<ul>
<li><p><span data-ttu-id="e41dd-127">前端伺服器或前端集區的外部 Web 服務 FQDN</span><span class="sxs-lookup"><span data-stu-id="e41dd-127">External Web Services FQDN for Front End Server or Front End pool</span></span></p></li>
<li><p><span data-ttu-id="e41dd-128">Director 或 Director 集區的外部 Web 服務 FQDN</span><span class="sxs-lookup"><span data-stu-id="e41dd-128">External Web Services FQDN for Director or Director pool</span></span></p></li>
<li><p><span data-ttu-id="e41dd-129">電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="e41dd-129">Dial-in conferencing</span></span></p></li>
<li><p><span data-ttu-id="e41dd-130">線上會議發佈規則</span><span class="sxs-lookup"><span data-stu-id="e41dd-130">Online meeting publishing rule</span></span></p></li>
<li><p><span data-ttu-id="e41dd-131">適用于會議的 Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="e41dd-131">Office Web Apps for conferencing</span></span></p></li>
<li><p><span data-ttu-id="e41dd-132">Lyncdiscover (自動探索) </span><span class="sxs-lookup"><span data-stu-id="e41dd-132">Lyncdiscover (Autodiscover)</span></span></p></li>
</ul>
<p><span data-ttu-id="e41dd-133">選用的萬用字元會取代「符合和撥入 SAN</span><span class="sxs-lookup"><span data-stu-id="e41dd-133">The optional wildcard replaces both meet and dialin SAN</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

