---
title: Lync Server 2013：憑證摘要-公用立即訊息連線
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
ms.openlocfilehash: bdc4bba8064332d7fa3f90d0d6a3d4b9f6cef9e6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512780"
---
# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="8abed-102">Lync Server 2013 中的憑證摘要-公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="8abed-102">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8abed-103">_**主題上次修改日期：** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="8abed-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="8abed-104">若要設定公用立即訊息連線的憑證，您應該先注意到其他 SIP 同盟類型或甚至是標準 Edge Server 憑證沒有任何不同之處，但北美線上 (AOL) 需要唯一的憑證設定。</span><span class="sxs-lookup"><span data-stu-id="8abed-104">To configure certificates for public Instant Messaging connectivity, you should first notice that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a unique certificate configuration.</span></span> <span data-ttu-id="8abed-105">除了一般的 server 增強金鑰使用方式外 (EKU) ，北美線上) Edge 集區的情況也需要憑證或憑證 (也包含用戶端 EKU。</span><span class="sxs-lookup"><span data-stu-id="8abed-105">In addition to the usual server enhanced key usage (EKU), America Online requires the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="8abed-106">用戶端 EKU 是憑證的新增，也是指派給 Edge Server 的外部公用憑證的一部分。</span><span class="sxs-lookup"><span data-stu-id="8abed-106">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="8abed-107">憑證摘要 - 公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="8abed-107">Certificate Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8abed-108">元件</span><span class="sxs-lookup"><span data-stu-id="8abed-108">Component</span></span></th>
<th><span data-ttu-id="8abed-109">主體名稱</span><span class="sxs-lookup"><span data-stu-id="8abed-109">Subject name</span></span></th>
<th><span data-ttu-id="8abed-110">主體替代名稱 (SAN)/順序</span><span class="sxs-lookup"><span data-stu-id="8abed-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="8abed-111">註解</span><span class="sxs-lookup"><span data-stu-id="8abed-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8abed-112">外部/Access Edge</span><span class="sxs-lookup"><span data-stu-id="8abed-112">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="8abed-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8abed-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8abed-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8abed-114">sip.contoso.com</span></span></p>
<p><span data-ttu-id="8abed-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8abed-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="8abed-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="8abed-116">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="8abed-117">憑證必須來自公用 CA，而且若要部署與 AOL 的公用 IM 連線，則必須具有伺服器 EKU 和用戶端 EKU。</span><span class="sxs-lookup"><span data-stu-id="8abed-117">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="8abed-118">此憑證會指派給下列專案的外部 Edge Server 介面：</span><span class="sxs-lookup"><span data-stu-id="8abed-118">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="8abed-119">Access Edge Service</span><span class="sxs-lookup"><span data-stu-id="8abed-119">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="8abed-120">Web Conferencing Edge service</span><span class="sxs-lookup"><span data-stu-id="8abed-120">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="8abed-121">A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="8abed-121">A/V Edge service</span></span></p></li>
</ul>
<p><span data-ttu-id="8abed-p103">請注意，系統會根據您在拓撲產生器中的定義，將 SAN 自動新增至憑證。您可以視需要為其他 SIP 網域新增 SAN 項目，或新增其他必須支援的項目。SAN 中的主體名稱會複寫，且必須存在才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="8abed-p103">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder. You add SAN entries as needed for additional SIP domains and other entries that you need to support. The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8abed-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8abed-125">See Also</span></span>


[<span data-ttu-id="8abed-126">Lync Server 2013 中的外部使用者存取案例</span><span class="sxs-lookup"><span data-stu-id="8abed-126">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

