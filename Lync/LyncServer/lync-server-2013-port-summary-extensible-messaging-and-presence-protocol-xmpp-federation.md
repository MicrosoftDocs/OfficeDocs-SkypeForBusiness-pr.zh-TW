---
title: 連接埠摘要-可延伸訊息與顯示狀態通訊協定 (XMPP) 同盟
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
ms.openlocfilehash: ebb2eb7695cfcc3b1ed6166f7768128dc48fb8ac
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="9c3a9-102">連接埠摘要-可延伸訊息與顯示狀態通訊協定 (XMPP) 同盟 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="9c3a9-102">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c3a9-103">_**主題上次修改日期：** 2012年-10-20 個_</span><span class="sxs-lookup"><span data-stu-id="9c3a9-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="9c3a9-104">連接埠和通訊協定可延伸訊息與顯示狀態通訊協定 (XMPP) proxy 部署 Edge Server 上定義允許的 XMPP 同盟協力廠商的通訊的 Edge server，並以 XMPP 也允許來自您的 Edge Server 的通訊同盟協力廠商。</span><span class="sxs-lookup"><span data-stu-id="9c3a9-104">The ports and protocols defined for the extensible messaging and presence protocol (XMPP) proxy deployed on the Edge Server allow communications from the XMPP federated partner to the Edge Server, and also allows communication from your Edge Server to the XMPP federated partner.</span></span> <span data-ttu-id="9c3a9-105">內部向防火牆從前端伺服器或前端集區到 Edge Server 或 Edge 集區上也定義規則。</span><span class="sxs-lookup"><span data-stu-id="9c3a9-105">A rule is also defined on the internal-facing firewall from the Front End Server or Front End pool to the Edge Server or Edge pool.</span></span>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="9c3a9-106">Extensible Messaging and Presence Protocol 的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="9c3a9-106">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c3a9-107">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="9c3a9-107">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9c3a9-108">來源 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="9c3a9-108">Source (IP address)</span></span></th>
<th><span data-ttu-id="9c3a9-109">目的地 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="9c3a9-109">Destination (IP address)</span></span></th>
<th><span data-ttu-id="9c3a9-110">註解</span><span class="sxs-lookup"><span data-stu-id="9c3a9-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c3a9-111">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="9c3a9-111">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="9c3a9-112">任何</span><span class="sxs-lookup"><span data-stu-id="9c3a9-112">Any</span></span></p></td>
<td><p><span data-ttu-id="9c3a9-113">Access Edge service 介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="9c3a9-113">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="9c3a9-114">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="9c3a9-114">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="9c3a9-115">允許從同盟 XMPP 協力廠商通訊的 Edge Server XMPP proxy</span><span class="sxs-lookup"><span data-stu-id="9c3a9-115">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c3a9-116">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="9c3a9-116">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="9c3a9-117">Access Edge service 介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="9c3a9-117">Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="9c3a9-118">任何</span><span class="sxs-lookup"><span data-stu-id="9c3a9-118">Any</span></span></p></td>
<td><p><span data-ttu-id="9c3a9-119">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="9c3a9-119">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="9c3a9-120">可從 Edge Server XMPP proxy 的通訊，讓同盟 XMPP 協力廠商</span><span class="sxs-lookup"><span data-stu-id="9c3a9-120">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c3a9-121">XMPP/MTLS/23456</span><span class="sxs-lookup"><span data-stu-id="9c3a9-121">XMPP/MTLS/23456</span></span></p></td>
<td><p><span data-ttu-id="9c3a9-122">任何</span><span class="sxs-lookup"><span data-stu-id="9c3a9-122">Any</span></span></p></td>
<td><p><span data-ttu-id="9c3a9-123">內部 Edge Server 介面 IP</span><span class="sxs-lookup"><span data-stu-id="9c3a9-123">Internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="9c3a9-124">內部 XMPP 流量從前端伺服器或前端集區上的 XMPP 閘道至 Edge Server</span><span class="sxs-lookup"><span data-stu-id="9c3a9-124">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9c3a9-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9c3a9-125">See Also</span></span>


[<span data-ttu-id="9c3a9-126">Lync Server 2013 – 與 Google Talk 的 XMPP 同盟中 XMPP 設定範例</span><span class="sxs-lookup"><span data-stu-id="9c3a9-126">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="9c3a9-127">管理 Lync Server 2013 中的 XMPP 同盟協力廠商</span><span class="sxs-lookup"><span data-stu-id="9c3a9-127">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

