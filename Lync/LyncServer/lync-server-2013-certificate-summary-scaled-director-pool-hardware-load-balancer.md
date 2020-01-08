---
title: 憑證摘要 - 調整式 Director 集區 (硬體負載平衡器)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Scaled Director pool, hardware load balancer
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48183992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21b1688641d09e00c82ea952d57bd2a9547ac0dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="80a5b-102">Lync Server 2013 中的憑證摘要 - 調整式 Director 集區 (硬體負載平衡器)</span><span class="sxs-lookup"><span data-stu-id="80a5b-102">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80a5b-103">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="80a5b-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="80a5b-104">具有硬體負載平衡器之主管的憑證需求將會使用預設認證，該預設憑證具有 [受領人名稱] 和 [消費者名稱] 的預設憑證，且可供控制器擁有者接收。</span><span class="sxs-lookup"><span data-stu-id="80a5b-104">Certificate requirements for a Director with a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director pool can receive.</span></span> <span data-ttu-id="80a5b-105">針對池中的每個主管要求憑證。</span><span class="sxs-lookup"><span data-stu-id="80a5b-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="80a5b-106">此外，在每個伺服器上安裝的伺服器到伺服器驗證目的都有 OAuth 權杖憑證。</span><span class="sxs-lookup"><span data-stu-id="80a5b-106">Additionally there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a><span data-ttu-id="80a5b-107">使用硬體負載平衡器的縮放控制器憑證</span><span class="sxs-lookup"><span data-stu-id="80a5b-107">Certificates for a Scaled Director Using a Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80a5b-108">元件</span><span class="sxs-lookup"><span data-stu-id="80a5b-108">Component</span></span></th>
<th><span data-ttu-id="80a5b-109">消費者名稱（SN）</span><span class="sxs-lookup"><span data-stu-id="80a5b-109">Subject name (SN)</span></span></th>
<th><span data-ttu-id="80a5b-110">消費者備用名稱（SAN）</span><span class="sxs-lookup"><span data-stu-id="80a5b-110">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="80a5b-111">批註</span><span class="sxs-lookup"><span data-stu-id="80a5b-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80a5b-112">設置</span><span class="sxs-lookup"><span data-stu-id="80a5b-112">Default</span></span></p></td>
<td><p><span data-ttu-id="80a5b-113">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="80a5b-113">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="80a5b-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="80a5b-114">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="80a5b-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="80a5b-115">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="80a5b-116">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="80a5b-116">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="80a5b-117">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="80a5b-117">meet.contoso.com</span></span></p>
<p><span data-ttu-id="80a5b-118">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="80a5b-118">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="80a5b-119">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="80a5b-119">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="80a5b-120">（選擇性） \*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="80a5b-120">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="80a5b-121">您可以從內部管理的憑證授權單位（CA）或公用 CA 來要求控制器證書。</span><span class="sxs-lookup"><span data-stu-id="80a5b-121">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="80a5b-122">控制器會回應來自週邊或從邊緣伺服器的反向 proxy 要求。</span><span class="sxs-lookup"><span data-stu-id="80a5b-122">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span></p>
<p><span data-ttu-id="80a5b-123">或者，簡單 Url 的萬用字元專案</span><span class="sxs-lookup"><span data-stu-id="80a5b-123">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80a5b-124">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="80a5b-124">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="80a5b-125">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="80a5b-125">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="80a5b-126">無專案</span><span class="sxs-lookup"><span data-stu-id="80a5b-126">No Entry</span></span></p></td>
<td>


> [!IMPORTANT]
> <span data-ttu-id="80a5b-127">請注意，最小金鑰長度是1024，但是您可能會收到「建議」金鑰長度最小的警告（2048位）。</span><span class="sxs-lookup"><span data-stu-id="80a5b-127">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


<p><span data-ttu-id="80a5b-128">OAuthTokenIssuer 憑證是單一用途的憑證，目的在於驗證大型環境中的伺服器，而且可以從內部 CA 或公用 CA 進行申請。</span><span class="sxs-lookup"><span data-stu-id="80a5b-128">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA.</span></span> <span data-ttu-id="80a5b-129">需要證書。</span><span class="sxs-lookup"><span data-stu-id="80a5b-129">The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

