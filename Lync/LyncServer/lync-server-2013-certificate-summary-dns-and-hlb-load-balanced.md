---
title: Lync Server 2013：憑證摘要 - DNS 與 HLB 負載平衡
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - DNS and HLB load balanced
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48184676
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8cd6d86844629544b54670eb07c3433d19f99f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="8250e-102">Lync Server 2013 中的憑證摘要 - DNS 與 HLB 負載平衡</span><span class="sxs-lookup"><span data-stu-id="8250e-102">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8250e-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="8250e-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="8250e-104">具有 DNS 負載平衡的主管及硬體負載平衡器的憑證需求將會使用預設憑證，該憑證有一個消費者名稱和消費者替代名稱來提供控制器可以接收的服務。</span><span class="sxs-lookup"><span data-stu-id="8250e-104">Certificate requirements for a Director with DNS load balancing and a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="8250e-105">針對池中的每個主管要求憑證。</span><span class="sxs-lookup"><span data-stu-id="8250e-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="8250e-106">請務必記住，硬體負載平衡器只有從反向 proxy 的流量進行負載平衡。</span><span class="sxs-lookup"><span data-stu-id="8250e-106">It is important to remember that the hardware load balancer is load balancing only the traffic from the reverse proxy.</span></span> <span data-ttu-id="8250e-107">此外，在每個伺服器上安裝的伺服器到伺服器驗證目的都有一個 OAuth 權杖憑證。</span><span class="sxs-lookup"><span data-stu-id="8250e-107">Additionally, there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="8250e-108">主管的憑證</span><span class="sxs-lookup"><span data-stu-id="8250e-108">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8250e-109">元件</span><span class="sxs-lookup"><span data-stu-id="8250e-109">Component</span></span></th>
<th><span data-ttu-id="8250e-110">消費者名稱（SN）</span><span class="sxs-lookup"><span data-stu-id="8250e-110">Subject name (SN)</span></span></th>
<th><span data-ttu-id="8250e-111">消費者備用名稱（SAN）</span><span class="sxs-lookup"><span data-stu-id="8250e-111">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="8250e-112">批註</span><span class="sxs-lookup"><span data-stu-id="8250e-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8250e-113">設置</span><span class="sxs-lookup"><span data-stu-id="8250e-113">Default</span></span></p></td>
<td><p><span data-ttu-id="8250e-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="8250e-114">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="8250e-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="8250e-115">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="8250e-116">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="8250e-116">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="8250e-117">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8250e-117">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="8250e-118">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8250e-118">meet.contoso.com</span></span></p>
<p><span data-ttu-id="8250e-119">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8250e-119">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="8250e-120">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8250e-120">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="8250e-121">（選擇性） \*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="8250e-121">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8250e-122">您可以從內部管理的憑證授權單位（CA）或公用 CA 來要求控制器證書。</span><span class="sxs-lookup"><span data-stu-id="8250e-122">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="8250e-123">控制器會回應來自週邊或從邊緣伺服器的反向 proxy 要求。</span><span class="sxs-lookup"><span data-stu-id="8250e-123">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="8250e-124">內部用戶端不會使用控制器。</span><span class="sxs-lookup"><span data-stu-id="8250e-124">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="8250e-125">或者，簡單 Url 的萬用字元專案</span><span class="sxs-lookup"><span data-stu-id="8250e-125">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8250e-126">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="8250e-126">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="8250e-127">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="8250e-127">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="8250e-128">無專案</span><span class="sxs-lookup"><span data-stu-id="8250e-128">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="8250e-129">請注意，最小金鑰長度是1024，但是您可能會收到「建議」金鑰長度最小的警告（2048位）。</span><span class="sxs-lookup"><span data-stu-id="8250e-129">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="8250e-130">OAuthTokenIssuer 憑證是單一用途的憑證，目的在於驗證大型環境中的伺服器，而且可以從內部 CA 或公用 CA 進行申請。</span><span class="sxs-lookup"><span data-stu-id="8250e-130">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA.</span></span> <span data-ttu-id="8250e-131">需要證書。</span><span class="sxs-lookup"><span data-stu-id="8250e-131">The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

