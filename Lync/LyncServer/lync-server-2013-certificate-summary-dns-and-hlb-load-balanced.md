---
title: Lync Server 2013：憑證摘要-DNS 與 HLB 負載平衡
description: Lync Server 2013：憑證摘要-DNS 與 HLB 負載平衡。
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
ms.openlocfilehash: 97a89975af16b6e39625677f787d3726f00c76c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575969"
---
# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="908f2-103">Lync Server 2013 的憑證摘要-DNS 與 HLB 負載平衡</span><span class="sxs-lookup"><span data-stu-id="908f2-103">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="908f2-104">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="908f2-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="908f2-105">使用 DNS 負載平衡與硬體負載平衡器之 Director 的憑證需求，會針對 Director 可接收的服務，使用具有主體名稱和主體替代名稱的預設憑證。</span><span class="sxs-lookup"><span data-stu-id="908f2-105">Certificate requirements for a Director with DNS load balancing and a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="908f2-106">集區中的每個 Director 要求憑證。</span><span class="sxs-lookup"><span data-stu-id="908f2-106">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="908f2-107">必須注意的是，硬體負載平衡器僅對於來自反向 Proxy 的流量進行負載平衡。</span><span class="sxs-lookup"><span data-stu-id="908f2-107">It is important to remember that the hardware load balancer is load balancing only the traffic from the reverse proxy.</span></span> <span data-ttu-id="908f2-108">此外，各個伺服器上安裝的 OAuth 語彙基元憑證可用於伺服器對伺服器驗證用途。</span><span class="sxs-lookup"><span data-stu-id="908f2-108">Additionally, there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="908f2-109">Director 憑證</span><span class="sxs-lookup"><span data-stu-id="908f2-109">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="908f2-110">元件</span><span class="sxs-lookup"><span data-stu-id="908f2-110">Component</span></span></th>
<th><span data-ttu-id="908f2-111">主體名稱 (SN)</span><span class="sxs-lookup"><span data-stu-id="908f2-111">Subject name (SN)</span></span></th>
<th><span data-ttu-id="908f2-112">主體替代名稱 (SAN)</span><span class="sxs-lookup"><span data-stu-id="908f2-112">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="908f2-113">註解</span><span class="sxs-lookup"><span data-stu-id="908f2-113">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="908f2-114">預設</span><span class="sxs-lookup"><span data-stu-id="908f2-114">Default</span></span></p></td>
<td><p><span data-ttu-id="908f2-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="908f2-115">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="908f2-116">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="908f2-116">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="908f2-117">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="908f2-117">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="908f2-118">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="908f2-118">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="908f2-119">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="908f2-119">meet.contoso.com</span></span></p>
<p><span data-ttu-id="908f2-120">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="908f2-120">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="908f2-121">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="908f2-121">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="908f2-122">(選用) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="908f2-122">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="908f2-123">Director 憑證可以從內部管理的憑證授權單位單位 (CA) 或公用 CA 要求。</span><span class="sxs-lookup"><span data-stu-id="908f2-123">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="908f2-124">Director 會從周邊或 Edge Server 的反向 proxy 回應要求。</span><span class="sxs-lookup"><span data-stu-id="908f2-124">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="908f2-125">內部用戶端將不會使用 Director。</span><span class="sxs-lookup"><span data-stu-id="908f2-125">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="908f2-126">或是簡單 URL 的萬用字元項目</span><span class="sxs-lookup"><span data-stu-id="908f2-126">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="908f2-127">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="908f2-127">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="908f2-128">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="908f2-128">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="908f2-129">無項目</span><span class="sxs-lookup"><span data-stu-id="908f2-129">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="908f2-130">請注意，雖然最小金鑰長度是 1024，但是您可能會收到警告表示建議最小金鑰長度為 2048 位元。</span><span class="sxs-lookup"><span data-stu-id="908f2-130">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="908f2-p103">OAuthTokenIssuer 憑證是單一目的憑證，用於驗證大規模環境中的伺服器，且可向內部 CA 或公用 CA 要求。此憑證為必要。</span><span class="sxs-lookup"><span data-stu-id="908f2-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

