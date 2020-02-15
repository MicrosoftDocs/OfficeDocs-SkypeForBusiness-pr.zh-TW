---
title: Lync Server 2013： 憑證摘要-單一 Director
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
ms.openlocfilehash: abb3b1e9963d88a7876232219a8d4f2290c2c9cc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="d29b1-102">憑證摘要-Lync Server 2013 中的單一 Director</span><span class="sxs-lookup"><span data-stu-id="d29b1-102">Certificate summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d29b1-103">_**主題上次修改日期：** 2012年-09-08_</span><span class="sxs-lookup"><span data-stu-id="d29b1-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="d29b1-104">單一 Director 的憑證需求所組成的預設憑證，有一個主旨名稱和主體替代名稱 Director 可接收的服務。</span><span class="sxs-lookup"><span data-stu-id="d29b1-104">Certificate requirements for a single Director consist of a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="d29b1-105">此外，還包含用於伺服器對伺服器驗證所需的 OAuth Token 憑證。</span><span class="sxs-lookup"><span data-stu-id="d29b1-105">Additionally, there is an OAuth Token certificate for server to server authentication purposes.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="d29b1-106">Director 憑證</span><span class="sxs-lookup"><span data-stu-id="d29b1-106">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d29b1-107">元件</span><span class="sxs-lookup"><span data-stu-id="d29b1-107">Component</span></span></th>
<th><span data-ttu-id="d29b1-108">主體名稱 (SN)</span><span class="sxs-lookup"><span data-stu-id="d29b1-108">Subject name (SN)</span></span></th>
<th><span data-ttu-id="d29b1-109">主體替代名稱 (SAN)</span><span class="sxs-lookup"><span data-stu-id="d29b1-109">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="d29b1-110">註解</span><span class="sxs-lookup"><span data-stu-id="d29b1-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d29b1-111">預設</span><span class="sxs-lookup"><span data-stu-id="d29b1-111">Default</span></span></p></td>
<td><p><span data-ttu-id="d29b1-112">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="d29b1-112">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="d29b1-113">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="d29b1-113">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="d29b1-114">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d29b1-114">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="d29b1-115">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d29b1-115">meet.contoso.com</span></span></p>
<p><span data-ttu-id="d29b1-116">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d29b1-116">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="d29b1-117">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d29b1-117">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="d29b1-118">(選用) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d29b1-118">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d29b1-119">可向內部管理的憑證授權單位 (CA) 或公用 ca 要求 director 的憑證。</span><span class="sxs-lookup"><span data-stu-id="d29b1-119">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="d29b1-120">Director 回應要求從周邊網路中的反向 proxy 或 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="d29b1-120">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="d29b1-121">內部用戶端不會使用 Director。</span><span class="sxs-lookup"><span data-stu-id="d29b1-121">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="d29b1-122">或是簡單 URL 的萬用字元項目</span><span class="sxs-lookup"><span data-stu-id="d29b1-122">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d29b1-123">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="d29b1-123">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="d29b1-124">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="d29b1-124">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="d29b1-125">無項目</span><span class="sxs-lookup"><span data-stu-id="d29b1-125">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="d29b1-126">請注意，雖然最小金鑰長度是 1024，但是您可能會收到警告表示建議最小金鑰長度為 2048 位元。</span><span class="sxs-lookup"><span data-stu-id="d29b1-126">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="d29b1-p103">OAuthTokenIssuer 憑證是單一目的憑證，用於驗證大規模環境中的伺服器，且可向內部 CA 或公用 CA 要求。此憑證為必要。</span><span class="sxs-lookup"><span data-stu-id="d29b1-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

