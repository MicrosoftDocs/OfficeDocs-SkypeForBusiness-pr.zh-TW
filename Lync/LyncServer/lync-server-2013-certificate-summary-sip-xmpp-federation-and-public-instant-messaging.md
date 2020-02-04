---
title: 憑證摘要-SIP、XMPP 同盟及公用立即訊息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 933d6351-cfa6-4432-b3ed-1aff3ac92065
ms:mtpsurl: https://technet.microsoft.com/library/JJ618372(v=OCS.15)
ms:contentKeyID: 49105659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fc3b7a1745d045954fb06403dbb3359fb699a29
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="eb456-102">認證摘要-Lync Server 2013 中的 SIP、XMPP 同盟及公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="eb456-102">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb456-103">_**主題上次修改日期：** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="eb456-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="eb456-104">您要用來與 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器進行聯盟所需的憑證，通常會受到您設定、要求並指派給 Edge 伺服器的憑證。</span><span class="sxs-lookup"><span data-stu-id="eb456-104">The certificates that you need for federating with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server will typically be met by the certificates that you configure, request and assign to your Edge Server.</span></span>

<span data-ttu-id="eb456-105">啟用和建立使用可擴展訊息和目前狀態通訊協定（XMPP）合作夥伴的憑證需求，您必須加入 XMPP 網域的專案。</span><span class="sxs-lookup"><span data-stu-id="eb456-105">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require addition of entries for your XMPP domains.</span></span> <span data-ttu-id="eb456-106">在證書中作為消費者備用名稱（SAN）所包含的記錄，就是可參與 XMPP 通訊的網域。</span><span class="sxs-lookup"><span data-stu-id="eb456-106">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="eb456-107">網域可以是根層級網域（例如，contoso.com），如果您想要為整個網域啟用 XMPP，或可以選取子域（例如，corp.contoso.com、finance.contoso.com），如果您要為使用者的子集啟用 XMPP。</span><span class="sxs-lookup"><span data-stu-id="eb456-107">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<span data-ttu-id="eb456-108">若要設定公用立即訊息連線的憑證，請注意，除了北美線上（AOL）需要證書或憑證之外，其他 SIP 同盟類型或甚至標準邊緣伺服器憑證沒有什麼不同（在邊緣池的大小寫）也包含用戶端 EKU。</span><span class="sxs-lookup"><span data-stu-id="eb456-108">To configure certificates for public Instant Messaging connectivity, note that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="eb456-109">用戶端 EKU 是憑證的補充，而且是指派給 Edge 伺服器的外部公用憑證的一部分。</span><span class="sxs-lookup"><span data-stu-id="eb456-109">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<span data-ttu-id="eb456-110">若要確認您已符合 Edge 伺服器部署的正確證書需求，請參閱標題為 [**另請參閱**] 區段中所列的主題。</span><span class="sxs-lookup"><span data-stu-id="eb456-110">To confirm that you have met the correct certificate requirements for your Edge Server deployment, review the topics listed in the section titled **See Also**.</span></span>

<div>



<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eb456-111">元件</span><span class="sxs-lookup"><span data-stu-id="eb456-111">Component</span></span></th>
<th><span data-ttu-id="eb456-112">消費者名稱</span><span class="sxs-lookup"><span data-stu-id="eb456-112">Subject name</span></span></th>
<th><span data-ttu-id="eb456-113">消費者備用名稱（SAN）</span><span class="sxs-lookup"><span data-stu-id="eb456-113">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="eb456-114">批註</span><span class="sxs-lookup"><span data-stu-id="eb456-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eb456-115">外部/存取邊緣</span><span class="sxs-lookup"><span data-stu-id="eb456-115">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="eb456-116">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb456-116">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="eb456-117">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb456-117">sip.contoso.com</span></span></p>
<p><span data-ttu-id="eb456-118">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb456-118">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="eb456-119">contoso.com</span><span class="sxs-lookup"><span data-stu-id="eb456-119">contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="eb456-120">支援 contoso.com XMPP 命名空間</span><span class="sxs-lookup"><span data-stu-id="eb456-120">To support the contoso.com XMPP namespace</span></span>


<p><span data-ttu-id="eb456-121">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="eb456-121">sip.fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="eb456-122">支援 fabrikam.com SIP 命名空間</span><span class="sxs-lookup"><span data-stu-id="eb456-122">To support the fabrikam.com SIP namespace</span></span>


<p><span data-ttu-id="eb456-123">fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="eb456-123">fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="eb456-124">支援 fabrikam.com XMPP 命名空間</span><span class="sxs-lookup"><span data-stu-id="eb456-124">To support the fabrikam.com XMPP namespace</span></span>

</td>
<td><p><span data-ttu-id="eb456-125">證書必須來自公用 CA，而且如果要部署與 AOL 的公用 IM 連線，則必須擁有伺服器 EKU 和用戶端 EKU。</span><span class="sxs-lookup"><span data-stu-id="eb456-125">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="eb456-126">已將證書指派給外部邊緣伺服器介面，以進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="eb456-126">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="eb456-127">存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="eb456-127">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="eb456-128">網路會議 Edge 服務</span><span class="sxs-lookup"><span data-stu-id="eb456-128">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="eb456-129">A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="eb456-129">A/V Edge service</span></span></p></li>
</ul>



> [!NOTE]
> <span data-ttu-id="eb456-130">從技術角度來看，憑證沒有指派給 A/V 邊緣。</span><span class="sxs-lookup"><span data-stu-id="eb456-130">Technically, a certificate is not assigned to the A/V Edge.</span></span> <span data-ttu-id="eb456-131">安全通訊與驗證是透過媒體轉送驗證服務（MRAS）的方式來管理。</span><span class="sxs-lookup"><span data-stu-id="eb456-131">Secure communication and authentication is managed by way of the Media Relay Authentication Service (MRAS).</span></span> <span data-ttu-id="eb456-132">MRAS 使用指派給 Edge 伺服器內部介面的憑證。</span><span class="sxs-lookup"><span data-stu-id="eb456-132">MRAS uses the certificate assigned to the Edge Server internal interface.</span></span>


<p><span data-ttu-id="eb456-133">請注意，San 會根據您在拓撲建立器中的定義，自動新增到憑證中。</span><span class="sxs-lookup"><span data-stu-id="eb456-133">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder.</span></span> <span data-ttu-id="eb456-134">您可以視需要為其他 SIP 網域以及其他所需支援的專案新增 SAN 專案。</span><span class="sxs-lookup"><span data-stu-id="eb456-134">You add SAN entries as needed for additional SIP domains and other entries that you need to support.</span></span> <span data-ttu-id="eb456-135">Subject 名稱是在 SAN 中複製，而且必須存在，才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="eb456-135">The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eb456-136">請參閱</span><span class="sxs-lookup"><span data-stu-id="eb456-136">See Also</span></span>


[<span data-ttu-id="eb456-137">Lync Server 2013 中的範例 XMPP 設定 – XMPP 與 Google Talk 的同盟</span><span class="sxs-lookup"><span data-stu-id="eb456-137">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="eb456-138">在 Lync Server 2013 中規劃 Edge Server 憑證</span><span class="sxs-lookup"><span data-stu-id="eb456-138">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="eb456-139">Lync Server 2013 中的憑證摘要 - 單一合併 Edge (使用 NAT 透過私人 IP 位址)</span><span class="sxs-lookup"><span data-stu-id="eb456-139">Certificate summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[<span data-ttu-id="eb456-140">Lync Server 2013 中的憑證摘要 - 含公用 IP 位址的單一合併 Edge</span><span class="sxs-lookup"><span data-stu-id="eb456-140">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[<span data-ttu-id="eb456-141">Lync Server 2013 中的憑證摘要 - 調整式合併 Edge (使用 NAT 透過私人 IP 位址進行 DNS 負載平衡)</span><span class="sxs-lookup"><span data-stu-id="eb456-141">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[<span data-ttu-id="eb456-142">Lync Server 2013 中的憑證摘要 - 調整式合併 Edge (利用公用 IP 位址進行 DNS 負載平衡)</span><span class="sxs-lookup"><span data-stu-id="eb456-142">Certificate summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[<span data-ttu-id="eb456-143">Lync Server 2013 中的憑證摘要 - 調整式合併 Edge (利用硬體負載平衡器)</span><span class="sxs-lookup"><span data-stu-id="eb456-143">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

