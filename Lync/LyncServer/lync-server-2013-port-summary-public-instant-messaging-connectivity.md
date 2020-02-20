---
title: Lync Server 2013： 連接埠摘要-公用立即訊息連線
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
ms.openlocfilehash: 5f2d9b36e3a78b70dff97fabb08784dbbef9df9b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="21a6d-102">連接埠摘要-公用立即訊息 [Lync Server 2013 中的連線能力</span><span class="sxs-lookup"><span data-stu-id="21a6d-102">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21a6d-103">_**上次修改主題：** 2013年-02-16_</span><span class="sxs-lookup"><span data-stu-id="21a6d-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="21a6d-104">若要設定防火牆連接埠和通訊協定支援公用立即訊息連線必要，請先注意 SIP/MTLS/TCP 5061 是雙向帳戶中的公用 IM 提供者的連絡人能夠連絡 Lync 用戶端，或連絡公用 IM 連絡人的 Lync。</span><span class="sxs-lookup"><span data-stu-id="21a6d-104">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="21a6d-105">Windows Live Messenger 可以參與音訊/視訊通訊與 Lync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="21a6d-105">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="21a6d-106">此帳戶，您通常會有支援外部使用者的 Lync 用戶端防火牆上非常類似防火牆連接埠和通訊協定設定。</span><span class="sxs-lookup"><span data-stu-id="21a6d-106">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="21a6d-107">多個曾經 Lync 是功能強大的工具，可將跨組織及與個人世界各地的連線。</span><span class="sxs-lookup"><span data-stu-id="21a6d-107">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="21a6d-108">與 Windows Live Messenger 同盟需要任何其他的使用者/裝置的授權超過 Lync 標準用戶端存取授權 (CAL)。</span><span class="sxs-lookup"><span data-stu-id="21a6d-108">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="21a6d-109">Skype 同盟會新增至這份清單，讓 Lync 使用者可達到數百個數百萬的人員 IM 與語音。</span><span class="sxs-lookup"><span data-stu-id="21a6d-109">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="21a6d-110">同盟與 Messenger 用戶端連絡人最終會將正式在 2013 年 3 月 15 日，但不包括在中國大陸。</span><span class="sxs-lookup"><span data-stu-id="21a6d-110">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="21a6d-111">Skype 會變成先前用信差同盟用戶端的同盟使用者。</span><span class="sxs-lookup"><span data-stu-id="21a6d-111">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="21a6d-112">防火牆摘要 - 公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="21a6d-112">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21a6d-113">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="21a6d-113">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="21a6d-114">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="21a6d-114">Source IP address</span></span></th>
<th><span data-ttu-id="21a6d-115">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="21a6d-115">Destination IP address</span></span></th>
<th><span data-ttu-id="21a6d-116">附註</span><span class="sxs-lookup"><span data-stu-id="21a6d-116">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21a6d-117">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="21a6d-117">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="21a6d-118">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="21a6d-118">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="21a6d-119">Edge Server 存取介面</span><span class="sxs-lookup"><span data-stu-id="21a6d-119">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="21a6d-120">使用 SIP 的同盟和公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="21a6d-120">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21a6d-121">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="21a6d-121">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="21a6d-122">Edge Server 存取介面</span><span class="sxs-lookup"><span data-stu-id="21a6d-122">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="21a6d-123">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="21a6d-123">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="21a6d-124">使用 SIP 的同盟和公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="21a6d-124">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21a6d-125">Access/SIP (TLS) / TCP/443</span><span class="sxs-lookup"><span data-stu-id="21a6d-125">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="21a6d-126">用戶端</span><span class="sxs-lookup"><span data-stu-id="21a6d-126">Clients</span></span></p></td>
<td><p><span data-ttu-id="21a6d-127">Edge Server 存取介面</span><span class="sxs-lookup"><span data-stu-id="21a6d-127">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="21a6d-128">外部使用者存取的用戶端對伺服器 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="21a6d-128">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21a6d-129">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="21a6d-129">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="21a6d-130">Edge Server 存取介面</span><span class="sxs-lookup"><span data-stu-id="21a6d-130">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="21a6d-131">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="21a6d-131">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="21a6d-132">如果有設定 IM 連線，可與 Windows Live Messenger 用於 A/V 工作階段</span><span class="sxs-lookup"><span data-stu-id="21a6d-132">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21a6d-133">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="21a6d-133">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="21a6d-134">Edge Server 存取介面</span><span class="sxs-lookup"><span data-stu-id="21a6d-134">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="21a6d-135">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="21a6d-135">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="21a6d-136">所需的 Windows Live Messenger 與公用 IM 進行連線。</span><span class="sxs-lookup"><span data-stu-id="21a6d-136">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21a6d-137">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="21a6d-137">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="21a6d-138">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="21a6d-138">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="21a6d-139">Edge Server 存取介面</span><span class="sxs-lookup"><span data-stu-id="21a6d-139">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="21a6d-140">所需的 Windows Live Messenger 與公用 IM 進行連線。</span><span class="sxs-lookup"><span data-stu-id="21a6d-140">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="21a6d-141">另請參閱</span><span class="sxs-lookup"><span data-stu-id="21a6d-141">See Also</span></span>


[<span data-ttu-id="21a6d-142">Lync Server 2013 中的外部使用者存取的案例</span><span class="sxs-lookup"><span data-stu-id="21a6d-142">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="21a6d-143">決定外部 A / V 防火牆和連接埠需求 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21a6d-143">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

