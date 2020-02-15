---
title: Lync Server 2013： 憑證摘要-DNS 與 HLB 負載平衡
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
ms.openlocfilehash: 44b89f1b305b99d86fd1843ac61625083a5fb51b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="eac60-102">憑證摘要-DNS 與 HLB 負載平衡 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="eac60-102">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eac60-103">_**主題上次修改日期：** 2012年-10-22_</span><span class="sxs-lookup"><span data-stu-id="eac60-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="eac60-104">搭配 DNS Director 的憑證需求的負載平衡與硬體負載平衡器會使用預設的憑證具有主旨名稱和主體替代名稱 Director 可接收的服務。</span><span class="sxs-lookup"><span data-stu-id="eac60-104">Certificate requirements for a Director with DNS load balancing and a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="eac60-105">憑證要求的每個 Director 集區中。</span><span class="sxs-lookup"><span data-stu-id="eac60-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="eac60-106">必須注意的是，硬體負載平衡器僅對於來自反向 Proxy 的流量進行負載平衡。</span><span class="sxs-lookup"><span data-stu-id="eac60-106">It is important to remember that the hardware load balancer is load balancing only the traffic from the reverse proxy.</span></span> <span data-ttu-id="eac60-107">此外，各個伺服器上安裝的 OAuth 語彙基元憑證可用於伺服器對伺服器驗證用途。</span><span class="sxs-lookup"><span data-stu-id="eac60-107">Additionally, there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="eac60-108">Director 憑證</span><span class="sxs-lookup"><span data-stu-id="eac60-108">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eac60-109">元件</span><span class="sxs-lookup"><span data-stu-id="eac60-109">Component</span></span></th>
<th><span data-ttu-id="eac60-110">主體名稱 (SN)</span><span class="sxs-lookup"><span data-stu-id="eac60-110">Subject name (SN)</span></span></th>
<th><span data-ttu-id="eac60-111">主體替代名稱 (SAN)</span><span class="sxs-lookup"><span data-stu-id="eac60-111">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="eac60-112">註解</span><span class="sxs-lookup"><span data-stu-id="eac60-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eac60-113">預設</span><span class="sxs-lookup"><span data-stu-id="eac60-113">Default</span></span></p></td>
<td><p><span data-ttu-id="eac60-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="eac60-114">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="eac60-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="eac60-115">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="eac60-116">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="eac60-116">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="eac60-117">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eac60-117">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="eac60-118">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eac60-118">meet.contoso.com</span></span></p>
<p><span data-ttu-id="eac60-119">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eac60-119">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="eac60-120">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eac60-120">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="eac60-121">(選用) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eac60-121">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="eac60-122">可向內部管理的憑證授權單位 (CA) 或公用 ca 要求 director 的憑證。</span><span class="sxs-lookup"><span data-stu-id="eac60-122">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="eac60-123">Director 回應要求從周邊網路中的反向 proxy 或 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="eac60-123">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="eac60-124">內部用戶端不會使用 Director。</span><span class="sxs-lookup"><span data-stu-id="eac60-124">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="eac60-125">或是簡單 URL 的萬用字元項目</span><span class="sxs-lookup"><span data-stu-id="eac60-125">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eac60-126">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="eac60-126">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="eac60-127">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="eac60-127">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="eac60-128">無項目</span><span class="sxs-lookup"><span data-stu-id="eac60-128">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="eac60-129">請注意，雖然最小金鑰長度是 1024，但是您可能會收到警告表示建議最小金鑰長度為 2048 位元。</span><span class="sxs-lookup"><span data-stu-id="eac60-129">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="eac60-p103">OAuthTokenIssuer 憑證是單一目的憑證，用於驗證大規模環境中的伺服器，且可向內部 CA 或公用 CA 要求。此憑證為必要。</span><span class="sxs-lookup"><span data-stu-id="eac60-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

