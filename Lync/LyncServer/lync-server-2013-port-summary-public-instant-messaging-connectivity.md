---
title: Lync Server 2013：埠摘要-公用立即訊息連線
description: Lync Server 2013：埠摘要-公用立即訊息連線能力。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4137b5f92e043dc15dc9aa1f0b9593b4d9f7c2ca
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543059"
---
# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="0e141-103">Lync Server 2013 中的埠摘要-公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="0e141-103">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e141-104">_**主題上次修改日期：** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="0e141-104">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="0e141-105">若要為您的防火牆設定支援公用立即訊息連線所需的埠和通訊協定，請先注意 SIP/MTLS/TCP 5061 是雙向的，可讓公用 IM 提供者中的連絡人能夠聯繫 Lync 用戶端，或與 Lync 聯繫以取得公用 IM 連絡人。</span><span class="sxs-lookup"><span data-stu-id="0e141-105">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="0e141-106">Windows Live Messenger 可以與 Lync 用戶端參與音訊/視頻通訊。</span><span class="sxs-lookup"><span data-stu-id="0e141-106">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="0e141-107">這會針對一般具有防火牆的防火牆埠和通訊協定設定，以支援 Lync 用戶端的外部使用者使用。</span><span class="sxs-lookup"><span data-stu-id="0e141-107">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0e141-108">Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。</span><span class="sxs-lookup"><span data-stu-id="0e141-108">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="0e141-109">與 Windows Live Messenger 的同盟除了 Lync Standard Client Access License (CAL) 之外，不需要額外的使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="0e141-109">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="0e141-110">隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</span><span class="sxs-lookup"><span data-stu-id="0e141-110">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="0e141-111">與 Messenger 用戶端連絡人的同盟會在2013年3月15日（中國大陸除外）正式結束。</span><span class="sxs-lookup"><span data-stu-id="0e141-111">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="0e141-112">Skype 會成為先前使用信使的同盟使用者的同盟用戶端。</span><span class="sxs-lookup"><span data-stu-id="0e141-112">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="0e141-113">防火牆摘要 - 公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="0e141-113">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e141-114">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="0e141-114">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="0e141-115">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0e141-115">Source IP address</span></span></th>
<th><span data-ttu-id="0e141-116">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0e141-116">Destination IP address</span></span></th>
<th><span data-ttu-id="0e141-117">注意事項</span><span class="sxs-lookup"><span data-stu-id="0e141-117">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e141-118">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="0e141-118">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="0e141-119">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="0e141-119">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="0e141-120">Edge Server Access 介面</span><span class="sxs-lookup"><span data-stu-id="0e141-120">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="0e141-121">適用于使用 SIP 的同盟與公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="0e141-121">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e141-122">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="0e141-122">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="0e141-123">Edge Server Access 介面</span><span class="sxs-lookup"><span data-stu-id="0e141-123">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="0e141-124">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="0e141-124">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="0e141-125">適用于使用 SIP 的同盟與公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="0e141-125">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e141-126">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="0e141-126">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="0e141-127">用戶端</span><span class="sxs-lookup"><span data-stu-id="0e141-127">Clients</span></span></p></td>
<td><p><span data-ttu-id="0e141-128">Edge Server Access 介面</span><span class="sxs-lookup"><span data-stu-id="0e141-128">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="0e141-129">外部使用者存取的用戶端對伺服器 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="0e141-129">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e141-130">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="0e141-130">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="0e141-131">Edge Server Access 介面</span><span class="sxs-lookup"><span data-stu-id="0e141-131">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="0e141-132">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="0e141-132">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="0e141-133">如果有設定 IM 連線，可與 Windows Live Messenger 用於 A/V 工作階段</span><span class="sxs-lookup"><span data-stu-id="0e141-133">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e141-134">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="0e141-134">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="0e141-135">Edge Server Access 介面</span><span class="sxs-lookup"><span data-stu-id="0e141-135">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="0e141-136">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="0e141-136">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="0e141-137">使用 Windows Live Messenger 進行公用 IM 連線時必須使用。</span><span class="sxs-lookup"><span data-stu-id="0e141-137">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e141-138">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="0e141-138">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="0e141-139">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="0e141-139">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="0e141-140">Edge Server Access 介面</span><span class="sxs-lookup"><span data-stu-id="0e141-140">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="0e141-141">使用 Windows Live Messenger 進行公用 IM 連線時必須使用。</span><span class="sxs-lookup"><span data-stu-id="0e141-141">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0e141-142">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0e141-142">See Also</span></span>


[<span data-ttu-id="0e141-143">Lync Server 2013 中的外部使用者存取案例</span><span class="sxs-lookup"><span data-stu-id="0e141-143">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="0e141-144">決定 Lync Server 2013 的外部 A/V 防火牆和埠需求</span><span class="sxs-lookup"><span data-stu-id="0e141-144">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

