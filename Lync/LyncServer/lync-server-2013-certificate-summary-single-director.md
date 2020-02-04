---
title: Lync Server 2013：憑證摘要 - 單一 Director
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
ms.openlocfilehash: f18fcec270104be1620402ddee0c665c0f3f3a4f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="60bd3-102">Lync Server 2013 中的憑證摘要 - 單一 Director</span><span class="sxs-lookup"><span data-stu-id="60bd3-102">Certificate summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60bd3-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="60bd3-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="60bd3-104">單一控制器的憑證需求是由控制器可以接收之服務的主體名稱和消費者替代名稱所組成的預設憑證所組成。</span><span class="sxs-lookup"><span data-stu-id="60bd3-104">Certificate requirements for a single Director consist of a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="60bd3-105">此外，有一個用於伺服器驗證的 OAuth 權杖憑證。</span><span class="sxs-lookup"><span data-stu-id="60bd3-105">Additionally, there is an OAuth Token certificate for server to server authentication purposes.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="60bd3-106">主管的憑證</span><span class="sxs-lookup"><span data-stu-id="60bd3-106">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="60bd3-107">元件</span><span class="sxs-lookup"><span data-stu-id="60bd3-107">Component</span></span></th>
<th><span data-ttu-id="60bd3-108">消費者名稱（SN）</span><span class="sxs-lookup"><span data-stu-id="60bd3-108">Subject name (SN)</span></span></th>
<th><span data-ttu-id="60bd3-109">消費者備用名稱（SAN）</span><span class="sxs-lookup"><span data-stu-id="60bd3-109">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="60bd3-110">批註</span><span class="sxs-lookup"><span data-stu-id="60bd3-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60bd3-111">設置</span><span class="sxs-lookup"><span data-stu-id="60bd3-111">Default</span></span></p></td>
<td><p><span data-ttu-id="60bd3-112">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="60bd3-112">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="60bd3-113">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="60bd3-113">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="60bd3-114">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="60bd3-114">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="60bd3-115">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="60bd3-115">meet.contoso.com</span></span></p>
<p><span data-ttu-id="60bd3-116">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="60bd3-116">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="60bd3-117">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="60bd3-117">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="60bd3-118">（選擇性） \*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="60bd3-118">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="60bd3-119">您可以從內部管理的憑證授權單位（CA）或公用 CA 來要求控制器證書。</span><span class="sxs-lookup"><span data-stu-id="60bd3-119">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="60bd3-120">控制器會回應來自週邊或從邊緣伺服器的反向 proxy 要求。</span><span class="sxs-lookup"><span data-stu-id="60bd3-120">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="60bd3-121">內部用戶端不會使用控制器。</span><span class="sxs-lookup"><span data-stu-id="60bd3-121">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="60bd3-122">或者，簡單 Url 的萬用字元專案</span><span class="sxs-lookup"><span data-stu-id="60bd3-122">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60bd3-123">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="60bd3-123">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="60bd3-124">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="60bd3-124">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="60bd3-125">無專案</span><span class="sxs-lookup"><span data-stu-id="60bd3-125">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="60bd3-126">請注意，最小金鑰長度是1024，但是您可能會收到「建議」金鑰長度最小的警告（2048位）。</span><span class="sxs-lookup"><span data-stu-id="60bd3-126">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="60bd3-127">OAuthTokenIssuer 憑證是單一用途的憑證，目的在於驗證大型環境中的伺服器，而且可以從內部 CA 或公用 CA 進行申請。</span><span class="sxs-lookup"><span data-stu-id="60bd3-127">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA.</span></span> <span data-ttu-id="60bd3-128">需要證書。</span><span class="sxs-lookup"><span data-stu-id="60bd3-128">The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

