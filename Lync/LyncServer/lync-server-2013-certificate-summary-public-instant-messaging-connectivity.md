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
ms.openlocfilehash: 5c93e79eed643d608ac9ab04516222227fc7c1f6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="00f0d-102">證書摘要-Lync Server 2013 中的公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="00f0d-102">Certificate summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00f0d-103">_**主題上次修改日期：** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="00f0d-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="00f0d-104">若要設定公用立即訊息連線的憑證，您應該先注意到其他 SIP 同盟類型或甚至是標準邊緣伺服器憑證沒有什麼不同，只是北美 Online （AOL）需要唯一證書配置。</span><span class="sxs-lookup"><span data-stu-id="00f0d-104">To configure certificates for public Instant Messaging connectivity, you should first notice that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a unique certificate configuration.</span></span> <span data-ttu-id="00f0d-105">除了一般的伺服器增強型金鑰用法（EKU）之外，美洲線上還需要證書或憑證（在邊緣池而言），也包含用戶端 EKU。</span><span class="sxs-lookup"><span data-stu-id="00f0d-105">In addition to the usual server enhanced key usage (EKU), America Online requires the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="00f0d-106">用戶端 EKU 是憑證的補充，而且是指派給 Edge 伺服器的外部公用憑證的一部分。</span><span class="sxs-lookup"><span data-stu-id="00f0d-106">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="00f0d-107">證書摘要–公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="00f0d-107">Certificate Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00f0d-108">元件</span><span class="sxs-lookup"><span data-stu-id="00f0d-108">Component</span></span></th>
<th><span data-ttu-id="00f0d-109">消費者名稱</span><span class="sxs-lookup"><span data-stu-id="00f0d-109">Subject name</span></span></th>
<th><span data-ttu-id="00f0d-110">Subject 替代名稱（SAN）/Order</span><span class="sxs-lookup"><span data-stu-id="00f0d-110">Subject alternative names (SAN)/Order</span></span></th>
<th><span data-ttu-id="00f0d-111">批註</span><span class="sxs-lookup"><span data-stu-id="00f0d-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00f0d-112">外部/存取邊緣</span><span class="sxs-lookup"><span data-stu-id="00f0d-112">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="00f0d-113">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="00f0d-113">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="00f0d-114">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="00f0d-114">sip.contoso.com</span></span></p>
<p><span data-ttu-id="00f0d-115">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="00f0d-115">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="00f0d-116">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="00f0d-116">sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="00f0d-117">證書必須來自公用 CA，而且如果要部署與 AOL 的公用 IM 連線，則必須擁有伺服器 EKU 和用戶端 EKU。</span><span class="sxs-lookup"><span data-stu-id="00f0d-117">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="00f0d-118">已將證書指派給外部邊緣伺服器介面，以進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="00f0d-118">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="00f0d-119">存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="00f0d-119">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="00f0d-120">網路會議 Edge 服務</span><span class="sxs-lookup"><span data-stu-id="00f0d-120">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="00f0d-121">A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="00f0d-121">A/V Edge service</span></span></p></li>
</ul>
<p><span data-ttu-id="00f0d-122">請注意，San 會根據您在拓撲建立器中的定義，自動新增到憑證中。</span><span class="sxs-lookup"><span data-stu-id="00f0d-122">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder.</span></span> <span data-ttu-id="00f0d-123">您可以視需要為其他 SIP 網域以及其他所需支援的專案新增 SAN 專案。</span><span class="sxs-lookup"><span data-stu-id="00f0d-123">You add SAN entries as needed for additional SIP domains and other entries that you need to support.</span></span> <span data-ttu-id="00f0d-124">Subject 名稱是在 SAN 中複製，而且必須存在，才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="00f0d-124">The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="00f0d-125">請參閱</span><span class="sxs-lookup"><span data-stu-id="00f0d-125">See Also</span></span>


[<span data-ttu-id="00f0d-126">Lync Server 2013 中的外部使用者存取案例</span><span class="sxs-lookup"><span data-stu-id="00f0d-126">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

