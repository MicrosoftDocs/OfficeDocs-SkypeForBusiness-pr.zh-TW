---
title: 憑證摘要-調整式 Director 集區、 硬體負載平衡器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Scaled Director pool, hardware load balancer
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48183992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33fed49b1174260e29f6badc4a3f994f888c1a4b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="f9f34-102">憑證摘要-調整式 Director 集區、 Lync Server 2013 中的硬體負載平衡器</span><span class="sxs-lookup"><span data-stu-id="f9f34-102">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9f34-103">_**主題上次修改日期：** 2012年-10-20 個_</span><span class="sxs-lookup"><span data-stu-id="f9f34-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="f9f34-104">硬體負載平衡器與 Director 的憑證需求會使用預設的憑證具有主旨名稱和主體替代名稱，可接收的 Director 集區的服務。</span><span class="sxs-lookup"><span data-stu-id="f9f34-104">Certificate requirements for a Director with a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director pool can receive.</span></span> <span data-ttu-id="f9f34-105">憑證要求的每個 Director 集區中。</span><span class="sxs-lookup"><span data-stu-id="f9f34-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="f9f34-106">此外，每部伺服器上還會安裝針對伺服器對伺服器驗證使用的 OAuth Token 憑證。</span><span class="sxs-lookup"><span data-stu-id="f9f34-106">Additionally there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a><span data-ttu-id="f9f34-107">使用硬體負載平衡器的調整式 Director 的憑證</span><span class="sxs-lookup"><span data-stu-id="f9f34-107">Certificates for a Scaled Director Using a Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9f34-108">元件</span><span class="sxs-lookup"><span data-stu-id="f9f34-108">Component</span></span></th>
<th><span data-ttu-id="f9f34-109">主體名稱 (SN)</span><span class="sxs-lookup"><span data-stu-id="f9f34-109">Subject name (SN)</span></span></th>
<th><span data-ttu-id="f9f34-110">主體替代名稱 (SAN)</span><span class="sxs-lookup"><span data-stu-id="f9f34-110">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="f9f34-111">註解</span><span class="sxs-lookup"><span data-stu-id="f9f34-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9f34-112">預設</span><span class="sxs-lookup"><span data-stu-id="f9f34-112">Default</span></span></p></td>
<td><p><span data-ttu-id="f9f34-113">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f9f34-113">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f9f34-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f9f34-114">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="f9f34-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f9f34-115">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="f9f34-116">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9f34-116">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="f9f34-117">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9f34-117">meet.contoso.com</span></span></p>
<p><span data-ttu-id="f9f34-118">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9f34-118">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="f9f34-119">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9f34-119">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="f9f34-120">(選用) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f9f34-120">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="f9f34-121">可向內部管理的憑證授權單位 (CA) 或公用 ca 要求 director 的憑證。</span><span class="sxs-lookup"><span data-stu-id="f9f34-121">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="f9f34-122">Director 回應要求從周邊網路中的反向 proxy 或 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="f9f34-122">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span></p>
<p><span data-ttu-id="f9f34-123">或是簡單 URL 的萬用字元項目</span><span class="sxs-lookup"><span data-stu-id="f9f34-123">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9f34-124">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="f9f34-124">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="f9f34-125">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f9f34-125">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="f9f34-126">無項目</span><span class="sxs-lookup"><span data-stu-id="f9f34-126">No Entry</span></span></p></td>
<td>


> [!IMPORTANT]
> <span data-ttu-id="f9f34-127">請注意，雖然最小金鑰長度是 1024，但是您可能會收到警告表示建議最小金鑰長度為 2048 位元。</span><span class="sxs-lookup"><span data-stu-id="f9f34-127">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


<p><span data-ttu-id="f9f34-p102">OAuthTokenIssuer 憑證是單一目的憑證，用於驗證大規模環境中的伺服器，且可向內部 CA 或公用 CA 要求。此憑證為必要。</span><span class="sxs-lookup"><span data-stu-id="f9f34-p102">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

