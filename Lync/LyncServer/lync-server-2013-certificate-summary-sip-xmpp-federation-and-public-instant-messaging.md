---
title: 憑證摘要-SIP、XMPP 同盟和公用立即訊息
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
ms.openlocfilehash: 284a633a2c5ce820009c6672058837bbecb7ecd6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517870"
---
# <a name="certificate-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="384c3-102">Lync Server 2013 中的憑證摘要-SIP、XMPP 同盟和公用立即訊息</span><span class="sxs-lookup"><span data-stu-id="384c3-102">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="384c3-103">_**主題上次修改日期：** 2013-03-15_</span><span class="sxs-lookup"><span data-stu-id="384c3-103">_**Topic Last Modified:** 2013-03-15_</span></span>

<span data-ttu-id="384c3-104">您所需要的憑證是與 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通訊伺服器進行同盟，通常是由您設定、要求並指派給 Edge Server 的憑證所滿足。</span><span class="sxs-lookup"><span data-stu-id="384c3-104">The certificates that you need for federating with Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server will typically be met by the certificates that you configure, request and assign to your Edge Server.</span></span>

<span data-ttu-id="384c3-105">使用可延伸訊息和顯示狀態通訊協定來啟用及建立通訊的憑證需求 (XMPP) 合作夥伴需要加入 XMPP 網域的專案。</span><span class="sxs-lookup"><span data-stu-id="384c3-105">Certificate requirements for enabling and establishing communications with extensible messaging and presence protocol (XMPP) partners require addition of entries for your XMPP domains.</span></span> <span data-ttu-id="384c3-106"> (SAN) 中包含在憑證上的記錄，都是可參與 XMPP 通訊的網域。</span><span class="sxs-lookup"><span data-stu-id="384c3-106">The record that is included on the certificate as a subject alternative name (SAN) will be the domain that can participate in XMPP communications.</span></span> <span data-ttu-id="384c3-107">網域可以是根層級網域 (例如) ，如果您想要對整個網域啟用 XMPP，或可以選取子域 (例如，corp.contoso.com、finance.contoso.com) （如果您為使用者的子集啟用 XMPP）。</span><span class="sxs-lookup"><span data-stu-id="384c3-107">The domain can be the root-level domain (for example, contoso.com) if you want to enable XMPP for your entire domain, or can be selected child domains (for example, corp.contoso.com, finance.contoso.com) if you are enabling XMPP for a subset of users.</span></span>

<span data-ttu-id="384c3-108">若要設定公用立即訊息連線的憑證，請注意，除了北美線上 (AOL) 需要憑證或憑證 (的憑證或憑證，) 也包含用戶端 EKU 時，與其他 SIP 同盟類型或甚至標準 Edge Server 憑證沒有任何不同之處。</span><span class="sxs-lookup"><span data-stu-id="384c3-108">To configure certificates for public Instant Messaging connectivity, note that there is nothing different from other SIP federation types or even standard Edge Server certificates, except that America Online (AOL) requires a the certificate or certificates (in the case of an Edge pool) to also contain the client EKU.</span></span> <span data-ttu-id="384c3-109">用戶端 EKU 是憑證的新增，也是指派給 Edge Server 的外部公用憑證的一部分。</span><span class="sxs-lookup"><span data-stu-id="384c3-109">The client EKU is an addition to the certificate, and is part of the external public certificate that is assigned to your Edge Server.</span></span>

<span data-ttu-id="384c3-110">若要確認您是否符合 Edge Server 部署的正確憑證需求，請參閱一節中所列的主題，如 **另**列所列。</span><span class="sxs-lookup"><span data-stu-id="384c3-110">To confirm that you have met the correct certificate requirements for your Edge Server deployment, review the topics listed in the section titled **See Also**.</span></span>

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
<th><span data-ttu-id="384c3-111">元件</span><span class="sxs-lookup"><span data-stu-id="384c3-111">Component</span></span></th>
<th><span data-ttu-id="384c3-112">主體名稱</span><span class="sxs-lookup"><span data-stu-id="384c3-112">Subject name</span></span></th>
<th><span data-ttu-id="384c3-113">主體替代名稱 (SAN)</span><span class="sxs-lookup"><span data-stu-id="384c3-113">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="384c3-114">註解</span><span class="sxs-lookup"><span data-stu-id="384c3-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="384c3-115">外部/Access Edge</span><span class="sxs-lookup"><span data-stu-id="384c3-115">External/Access Edge</span></span></p></td>
<td><p><span data-ttu-id="384c3-116">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="384c3-116">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="384c3-117">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="384c3-117">sip.contoso.com</span></span></p>
<p><span data-ttu-id="384c3-118">webcon.contoso.com</span><span class="sxs-lookup"><span data-stu-id="384c3-118">webcon.contoso.com</span></span></p>
<p><span data-ttu-id="384c3-119">contoso.com</span><span class="sxs-lookup"><span data-stu-id="384c3-119">contoso.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="384c3-120">若要支援 contoso.com XMPP 命名空間</span><span class="sxs-lookup"><span data-stu-id="384c3-120">To support the contoso.com XMPP namespace</span></span>


<p><span data-ttu-id="384c3-121">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="384c3-121">sip.fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="384c3-122">若要支援 fabrikam.com SIP 命名空間</span><span class="sxs-lookup"><span data-stu-id="384c3-122">To support the fabrikam.com SIP namespace</span></span>


<p><span data-ttu-id="384c3-123">fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="384c3-123">fabrikam.com</span></span></p>



> [!NOTE]
> <span data-ttu-id="384c3-124">若要支援 fabrikam.com XMPP 命名空間</span><span class="sxs-lookup"><span data-stu-id="384c3-124">To support the fabrikam.com XMPP namespace</span></span>

</td>
<td><p><span data-ttu-id="384c3-125">憑證必須來自公用 CA，而且若要部署與 AOL 的公用 IM 連線，則必須具有伺服器 EKU 和用戶端 EKU。</span><span class="sxs-lookup"><span data-stu-id="384c3-125">The certificate must be from a Public CA, and must have the server EKU and client EKU if public IM connectivity with AOL is to be deployed.</span></span> <span data-ttu-id="384c3-126">此憑證會指派給下列專案的外部 Edge Server 介面：</span><span class="sxs-lookup"><span data-stu-id="384c3-126">The certificate is assigned to the external Edge Server interfaces for:</span></span></p>
<ul>
<li><p><span data-ttu-id="384c3-127">Access Edge Service</span><span class="sxs-lookup"><span data-stu-id="384c3-127">Access Edge service</span></span></p></li>
<li><p><span data-ttu-id="384c3-128">Web Conferencing Edge service</span><span class="sxs-lookup"><span data-stu-id="384c3-128">Web Conferencing Edge service</span></span></p></li>
<li><p><span data-ttu-id="384c3-129">A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="384c3-129">A/V Edge service</span></span></p></li>
</ul>



> [!NOTE]
> <span data-ttu-id="384c3-130">從技術上而言，憑證並未指派給 A/V Edge。</span><span class="sxs-lookup"><span data-stu-id="384c3-130">Technically, a certificate is not assigned to the A/V Edge.</span></span> <span data-ttu-id="384c3-131">安全通訊和驗證是透過媒體轉送驗證服務 (MRAS) 來管理。</span><span class="sxs-lookup"><span data-stu-id="384c3-131">Secure communication and authentication is managed by way of the Media Relay Authentication Service (MRAS).</span></span> <span data-ttu-id="384c3-132">MRAS 使用指派給 Edge Server 內部介面的憑證。</span><span class="sxs-lookup"><span data-stu-id="384c3-132">MRAS uses the certificate assigned to the Edge Server internal interface.</span></span>


<p><span data-ttu-id="384c3-p105">請注意，系統會根據您在拓撲產生器中的定義，將 SAN 自動新增至憑證。您可以視需要為其他 SIP 網域新增 SAN 項目，或新增其他必須支援的項目。SAN 中的主體名稱會複寫，且必須存在才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="384c3-p105">Note that SANs are automatically added to the certificate based on your definitions in Topology Builder. You add SAN entries as needed for additional SIP domains and other entries that you need to support. The subject name is replicated in the SAN and must be present for correct operation.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="384c3-136">另請參閱</span><span class="sxs-lookup"><span data-stu-id="384c3-136">See Also</span></span>


[<span data-ttu-id="384c3-137">Lync Server 2013 的範例 XMPP 設定– XMPP 與 Google 交談的同盟</span><span class="sxs-lookup"><span data-stu-id="384c3-137">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="384c3-138">在 Lync Server 2013 中規劃 Edge Server 憑證</span><span class="sxs-lookup"><span data-stu-id="384c3-138">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="384c3-139">Lync Server 2013 中的憑證摘要-單一合併 edge （使用 NAT 透過私人 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="384c3-139">Certificate summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)  
[<span data-ttu-id="384c3-140">Lync Server 2013 中的憑證摘要-單一合併 edge （利用公用 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="384c3-140">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)  
[<span data-ttu-id="384c3-141">Lync Server 2013 中的憑證摘要-調整式合併 edge （使用 NAT 透過私人 IP 位址進行 DNS 負載平衡）</span><span class="sxs-lookup"><span data-stu-id="384c3-141">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)  
[<span data-ttu-id="384c3-142">Lync Server 2013 中的憑證摘要-調整式合併 edge （透過公用 IP 位址進行 DNS 負載平衡）</span><span class="sxs-lookup"><span data-stu-id="384c3-142">Certificate summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)  
[<span data-ttu-id="384c3-143">Lync Server 2013 的憑證摘要-調整式合併 edge （含硬體負載平衡器）</span><span class="sxs-lookup"><span data-stu-id="384c3-143">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

