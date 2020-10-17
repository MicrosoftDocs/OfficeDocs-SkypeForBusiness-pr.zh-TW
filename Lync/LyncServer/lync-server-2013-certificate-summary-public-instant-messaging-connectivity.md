---
title: Lync Server 2013：憑證摘要-公用立即訊息連線
description: Lync Server 2013：憑證摘要-公用立即訊息連線能力。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abf5a01bdeb03da158e221c623417a1b42cc82f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572329"
---
# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="d8988-103">Lync Server 2013 中的憑證摘要-公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="d8988-103">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8988-104">_**主題上次修改日期：** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="d8988-104">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="d8988-105">若要設定公用立即訊息連線的憑證，您應該先注意到其他 SIP 同盟類型或甚至是標準 Edge Server 憑證沒有任何不同之處，但北美線上 (AOL) 需要唯一的憑證設定。</span><span class="sxs-lookup"><span data-stu-id="d8988-105">To configure certificates for public Instant Messaging connectivity, you should first notice that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a unique certificate configuration.</span></span> <span data-ttu-id="d8988-106">除了一般的 server 增強金鑰使用方式外 (EKU) ，北美線上) Edge 集區的情況也需要憑證或憑證 (也包含用戶端 EKU。</span><span class="sxs-lookup"><span data-stu-id="d8988-106">In addition to the usual server enhanced key usage (EKU), America Online requires the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="d8988-107">用戶端 EKU 是憑證的新增，也是指派給 Edge Server 的外部公用憑證的一部分。</span><span class="sxs-lookup"><span data-stu-id="d8988-107">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="d8988-108">憑證摘要 - 公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="d8988-108">Certificate Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8988-109">元件</span><span class="sxs-lookup"><span data-stu-id="d8988-109">Component</span></span></th>
<th><span data-ttu-id="d8988-110">主體名稱</span><span class="sxs-lookup"><span data-stu-id="d8988-110">Subject name</span></span></th>
<th><span data-ttu-id="d8988-111">主體替代名稱 (SAN)/順序</span><span class="sxs-lookup"><span data-stu-id="d8988-111">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="d8988-112">註解</span><span class="sxs-lookup"><span data-stu-id="d8988-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8988-113">外部/Access Edge</span><span class="sxs-lookup"><span data-stu-id="d8988-113">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="d8988-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d8988-114">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d8988-115">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d8988-115">sip.contoso.com</span></span></p>
<p><span data-ttu-id="d8988-116">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d8988-116">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="d8988-117">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d8988-117">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="d8988-118">憑證必須來自公用 CA，而且若要部署與 AOL 的公用 IM 連線，則必須具有伺服器 EKU 和用戶端 EKU。</span><span class="sxs-lookup"><span data-stu-id="d8988-118">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="d8988-119">此憑證會指派給下列專案的外部 Edge Server 介面：</span><span class="sxs-lookup"><span data-stu-id="d8988-119">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="d8988-120">Access Edge Service</span><span class="sxs-lookup"><span data-stu-id="d8988-120">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="d8988-121">Web Conferencing Edge service</span><span class="sxs-lookup"><span data-stu-id="d8988-121">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="d8988-122">A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="d8988-122">A/V Edge service</span></span></p></li>
</ul>
<p><span data-ttu-id="d8988-p103">請注意，系統會根據您在拓撲產生器中的定義，將 SAN 自動新增至憑證。您可以視需要為其他 SIP 網域新增 SAN 項目，或新增其他必須支援的項目。SAN 中的主體名稱會複寫，且必須存在才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="d8988-p103">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder. You add SAN entries as needed for additional SIP domains and other entries that you need to support. The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d8988-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d8988-126">See Also</span></span>


[<span data-ttu-id="d8988-127">Lync Server 2013 中的外部使用者存取案例</span><span class="sxs-lookup"><span data-stu-id="d8988-127">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

