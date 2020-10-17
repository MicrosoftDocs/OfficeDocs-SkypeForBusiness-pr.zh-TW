---
title: Lync Server 2013：憑證摘要-單一 Director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Single Director
ms:assetid: 1b769a76-cbf3-46e9-a955-f6cde5faff93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204720(v=OCS.15)
ms:contentKeyID: 48183546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceb2543cece60a32c733d2efad6023fc30bb2bf6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517930"
---
# <a name="certificate-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="a93d3-102">Lync Server 2013 中的憑證摘要-單一 Director</span><span class="sxs-lookup"><span data-stu-id="a93d3-102">Certificate summary - Single Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a93d3-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="a93d3-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="a93d3-104">單一 Director 的憑證需求包含預設憑證，該憑證具有 Director 可接收之服務的主體名稱和主體替代名稱。</span><span class="sxs-lookup"><span data-stu-id="a93d3-104">Certificate requirements for a single Director consist of a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="a93d3-105">此外，還包含用於伺服器對伺服器驗證所需的 OAuth Token 憑證。</span><span class="sxs-lookup"><span data-stu-id="a93d3-105">Additionally, there is an OAuth Token certificate for server to server authentication purposes.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="a93d3-106">Director 憑證</span><span class="sxs-lookup"><span data-stu-id="a93d3-106">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a93d3-107">元件</span><span class="sxs-lookup"><span data-stu-id="a93d3-107">Component</span></span></th>
<th><span data-ttu-id="a93d3-108">主體名稱 (SN)</span><span class="sxs-lookup"><span data-stu-id="a93d3-108">Subject name (SN)</span></span></th>
<th><span data-ttu-id="a93d3-109">主體替代名稱 (SAN)</span><span class="sxs-lookup"><span data-stu-id="a93d3-109">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="a93d3-110">註解</span><span class="sxs-lookup"><span data-stu-id="a93d3-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a93d3-111">預設</span><span class="sxs-lookup"><span data-stu-id="a93d3-111">Default</span></span></p></td>
<td><p><span data-ttu-id="a93d3-112">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="a93d3-112">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="a93d3-113">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="a93d3-113">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="a93d3-114">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a93d3-114">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="a93d3-115">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a93d3-115">meet.contoso.com</span></span></p>
<p><span data-ttu-id="a93d3-116">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a93d3-116">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="a93d3-117">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a93d3-117">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="a93d3-118">(選用) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a93d3-118">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a93d3-119">Director 憑證可以從內部管理的憑證授權單位單位 (CA) 或公用 CA 要求。</span><span class="sxs-lookup"><span data-stu-id="a93d3-119">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="a93d3-120">Director 會從周邊或 Edge Server 的反向 proxy 回應要求。</span><span class="sxs-lookup"><span data-stu-id="a93d3-120">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="a93d3-121">內部用戶端將不會使用 Director。</span><span class="sxs-lookup"><span data-stu-id="a93d3-121">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="a93d3-122">或是簡單 URL 的萬用字元項目</span><span class="sxs-lookup"><span data-stu-id="a93d3-122">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a93d3-123">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="a93d3-123">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="a93d3-124">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="a93d3-124">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="a93d3-125">無項目</span><span class="sxs-lookup"><span data-stu-id="a93d3-125">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="a93d3-126">請注意，雖然最小金鑰長度是 1024，但是您可能會收到警告表示建議最小金鑰長度為 2048 位元。</span><span class="sxs-lookup"><span data-stu-id="a93d3-126">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="a93d3-p103">OAuthTokenIssuer 憑證是單一目的憑證，用於驗證大規模環境中的伺服器，且可向內部 CA 或公用 CA 要求。此憑證為必要。</span><span class="sxs-lookup"><span data-stu-id="a93d3-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

