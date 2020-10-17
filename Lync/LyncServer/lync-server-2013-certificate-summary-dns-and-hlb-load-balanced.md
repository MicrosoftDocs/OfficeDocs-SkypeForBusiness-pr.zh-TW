---
title: Lync Server 2013：憑證摘要-DNS 與 HLB 負載平衡
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
ms.openlocfilehash: 743818f81f5083e9c5d3a7877d2518d05176a5e7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499290"
---
# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="ff890-102">Lync Server 2013 的憑證摘要-DNS 與 HLB 負載平衡</span><span class="sxs-lookup"><span data-stu-id="ff890-102">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff890-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="ff890-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="ff890-104">使用 DNS 負載平衡與硬體負載平衡器之 Director 的憑證需求，會針對 Director 可接收的服務，使用具有主體名稱和主體替代名稱的預設憑證。</span><span class="sxs-lookup"><span data-stu-id="ff890-104">Certificate requirements for a Director with DNS load balancing and a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="ff890-105">集區中的每個 Director 要求憑證。</span><span class="sxs-lookup"><span data-stu-id="ff890-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="ff890-106">必須注意的是，硬體負載平衡器僅對於來自反向 Proxy 的流量進行負載平衡。</span><span class="sxs-lookup"><span data-stu-id="ff890-106">It is important to remember that the hardware load balancer is load balancing only the traffic from the reverse proxy.</span></span> <span data-ttu-id="ff890-107">此外，各個伺服器上安裝的 OAuth 語彙基元憑證可用於伺服器對伺服器驗證用途。</span><span class="sxs-lookup"><span data-stu-id="ff890-107">Additionally, there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="ff890-108">Director 憑證</span><span class="sxs-lookup"><span data-stu-id="ff890-108">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff890-109">元件</span><span class="sxs-lookup"><span data-stu-id="ff890-109">Component</span></span></th>
<th><span data-ttu-id="ff890-110">主體名稱 (SN)</span><span class="sxs-lookup"><span data-stu-id="ff890-110">Subject name (SN)</span></span></th>
<th><span data-ttu-id="ff890-111">主體替代名稱 (SAN)</span><span class="sxs-lookup"><span data-stu-id="ff890-111">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="ff890-112">註解</span><span class="sxs-lookup"><span data-stu-id="ff890-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff890-113">預設</span><span class="sxs-lookup"><span data-stu-id="ff890-113">Default</span></span></p></td>
<td><p><span data-ttu-id="ff890-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="ff890-114">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="ff890-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="ff890-115">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="ff890-116">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="ff890-116">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="ff890-117">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ff890-117">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="ff890-118">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ff890-118">meet.contoso.com</span></span></p>
<p><span data-ttu-id="ff890-119">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ff890-119">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="ff890-120">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ff890-120">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="ff890-121">(選用) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ff890-121">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ff890-122">Director 憑證可以從內部管理的憑證授權單位單位 (CA) 或公用 CA 要求。</span><span class="sxs-lookup"><span data-stu-id="ff890-122">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="ff890-123">Director 會從周邊或 Edge Server 的反向 proxy 回應要求。</span><span class="sxs-lookup"><span data-stu-id="ff890-123">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="ff890-124">內部用戶端將不會使用 Director。</span><span class="sxs-lookup"><span data-stu-id="ff890-124">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="ff890-125">或是簡單 URL 的萬用字元項目</span><span class="sxs-lookup"><span data-stu-id="ff890-125">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff890-126">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="ff890-126">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="ff890-127">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="ff890-127">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="ff890-128">無項目</span><span class="sxs-lookup"><span data-stu-id="ff890-128">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="ff890-129">請注意，雖然最小金鑰長度是 1024，但是您可能會收到警告表示建議最小金鑰長度為 2048 位元。</span><span class="sxs-lookup"><span data-stu-id="ff890-129">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="ff890-p103">OAuthTokenIssuer 憑證是單一目的憑證，用於驗證大規模環境中的伺服器，且可向內部 CA 或公用 CA 要求。此憑證為必要。</span><span class="sxs-lookup"><span data-stu-id="ff890-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

