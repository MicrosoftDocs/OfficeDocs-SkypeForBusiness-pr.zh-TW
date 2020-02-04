---
title: 埠摘要-可擴展的訊息和目前狀態通訊協定（XMPP）同盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary -  Extensible messaging and presence protocol (XMPP) federation
ms:assetid: 62e98fab-7add-4983-a3fa-dbe74e1c3849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618371(v=OCS.15)
ms:contentKeyID: 49105658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a18129fce98b3bb9bc613f4fc752daadfb6c5ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="56752-102">在 Lync Server 2013 中的埠摘要-可擴展的訊息和目前狀態通訊協定（XMPP）同盟</span><span class="sxs-lookup"><span data-stu-id="56752-102">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56752-103">_**主題上次修改日期：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="56752-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="56752-104">針對在 Edge 伺服器部署的可擴展訊息和目前狀態通訊協定（XMPP） proxy 所定義的埠和通訊協定，允許從 XMPP 聯盟夥伴傳送到 Edge 伺服器，也可讓您從邊緣伺服器與 XMPP 進行通訊。聯盟合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="56752-104">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="56752-105">您也可以在內部防火牆上，從前端伺服器或頂層端池中，在邊緣伺服器或 Edge 池中定義規則。</span><span class="sxs-lookup"><span data-stu-id="56752-105">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="56752-106">可擴展訊息和目前狀態通訊協定的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="56752-106">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56752-107">通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="56752-107">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="56752-108">來源（IP 位址）</span><span class="sxs-lookup"><span data-stu-id="56752-108">Source (IP address)</span></span></th>
<th><span data-ttu-id="56752-109">目的地（IP 位址）</span><span class="sxs-lookup"><span data-stu-id="56752-109">Destination (IP address)</span></span></th>
<th><span data-ttu-id="56752-110">批註</span><span class="sxs-lookup"><span data-stu-id="56752-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56752-111">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="56752-111">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="56752-112">每</span><span class="sxs-lookup"><span data-stu-id="56752-112">Any</span></span></p></td>
<td><p><span data-ttu-id="56752-113">Access Edge 服務介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="56752-113">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="56752-114">XMPP 的標準伺服器與伺服器通訊埠。</span><span class="sxs-lookup"><span data-stu-id="56752-114">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="56752-115">允許從聯盟 XMPP 合作夥伴與 Edge 伺服器 XMPP proxy 進行通訊</span><span class="sxs-lookup"><span data-stu-id="56752-115">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56752-116">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="56752-116">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="56752-117">Access Edge 服務介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="56752-117">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="56752-118">每</span><span class="sxs-lookup"><span data-stu-id="56752-118">Any</span></span></p></td>
<td><p><span data-ttu-id="56752-119">XMPP 的標準伺服器與伺服器通訊埠。</span><span class="sxs-lookup"><span data-stu-id="56752-119">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="56752-120">允許從 Edge 伺服器 XMPP proxy 到聯盟 XMPP 合作夥伴的通訊</span><span class="sxs-lookup"><span data-stu-id="56752-120">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56752-121">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="56752-121">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="56752-122">每</span><span class="sxs-lookup"><span data-stu-id="56752-122">Any</span></span></p></td>
<td><p><span data-ttu-id="56752-123">內部邊緣伺服器介面 IP</span><span class="sxs-lookup"><span data-stu-id="56752-123">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="56752-124">從前端伺服器或頂層池的 XMPP 閘道到 Edge 伺服器的內部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="56752-124">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="56752-125">請參閱</span><span class="sxs-lookup"><span data-stu-id="56752-125">See Also</span></span>


[<span data-ttu-id="56752-126">Lync Server 2013 中的範例 XMPP 設定 – XMPP 與 Google Talk 的同盟</span><span class="sxs-lookup"><span data-stu-id="56752-126">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="56752-127">在 Lync Server 2013 中管理 XMPP 同盟夥伴</span><span class="sxs-lookup"><span data-stu-id="56752-127">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

