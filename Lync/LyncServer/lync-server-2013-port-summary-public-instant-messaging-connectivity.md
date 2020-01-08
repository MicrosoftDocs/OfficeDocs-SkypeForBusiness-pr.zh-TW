---
title: Lync Server 2013：埠摘要-公用立即訊息連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Public instant messaging connectivity
ms:assetid: f46756ec-1401-4ca2-a4a4-5cd28bcfdc7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618376(v=OCS.15)
ms:contentKeyID: 49105663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bb6b8d0d9277b7d77440519596da76585b9d91b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a><span data-ttu-id="e7db6-102">埠摘要-Lync Server 2013 中的公用立即訊息連線能力</span><span class="sxs-lookup"><span data-stu-id="e7db6-102">Port summary - Public instant messaging connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7db6-103">_**主題上次修改日期：** 2013-02-16_</span><span class="sxs-lookup"><span data-stu-id="e7db6-103">_**Topic Last Modified:** 2013-02-16_</span></span>

<span data-ttu-id="e7db6-104">若要針對支援公用立即訊息連線的埠和通訊協定設定您的防火牆，請先注意，SIP/MTLS/TCP 5061 是雙向的，以將公用 IM 提供者的連絡人連線到 Lync 用戶端，或是 Lync 與公用 IM 連絡人聯繫。</span><span class="sxs-lookup"><span data-stu-id="e7db6-104">To configure your firewall for ports and protocols necessary to support public instant messaging connectivity, first note that SIP/MTLS/TCP 5061 is bidirectional to account for the ability of contacts in the public IM provider to contact Lync clients, or for Lync to contact public IM contacts.</span></span>

<span data-ttu-id="e7db6-105">Windows Live Messenger 可以使用 Lync 用戶端參與音訊/視頻通訊。</span><span class="sxs-lookup"><span data-stu-id="e7db6-105">Windows Live Messenger can participate in audio/video communications with Lync clients.</span></span> <span data-ttu-id="e7db6-106">這個帳戶是您在防火牆上通常會有的類似防火牆埠和通訊協定設定，以支援 Lync 用戶端作為外部使用者。</span><span class="sxs-lookup"><span data-stu-id="e7db6-106">This accounts for the very similar firewall port and protocol configuration that you would typically have on the firewall to support Lync clients as external users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e7db6-107">Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。</span><span class="sxs-lookup"><span data-stu-id="e7db6-107">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="e7db6-108">與 Windows Live Messenger 的同盟不需要在 Lync 標準用戶端存取授權（CAL）之外的其他使用者/裝置授權。</span><span class="sxs-lookup"><span data-stu-id="e7db6-108">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard Client Access License (CAL).</span></span> <span data-ttu-id="e7db6-109">您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="e7db6-109">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span><BR><span data-ttu-id="e7db6-110">與 Messenger 用戶端連絡人的同盟將于2013年3月15日正式結束，除了中國大陸以外。</span><span class="sxs-lookup"><span data-stu-id="e7db6-110">Federation with Messenger client contacts will officially end on March 15, 2013, except for mainland China.</span></span> <span data-ttu-id="e7db6-111">Skype 將成為先前使用 Messenger 之聯盟使用者的同盟用戶端。</span><span class="sxs-lookup"><span data-stu-id="e7db6-111">Skype will become the federation client for federated users who previously used Messenger.</span></span>



</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="e7db6-112">防火牆摘要–公用立即訊息連線能力</span><span class="sxs-lookup"><span data-stu-id="e7db6-112">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e7db6-113">角色/通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="e7db6-113">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e7db6-114">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e7db6-114">Source IP address</span></span></th>
<th><span data-ttu-id="e7db6-115">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e7db6-115">Destination IP address</span></span></th>
<th><span data-ttu-id="e7db6-116">筆記</span><span class="sxs-lookup"><span data-stu-id="e7db6-116">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7db6-117">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e7db6-117">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e7db6-118">公用 IM 連線性合作夥伴</span><span class="sxs-lookup"><span data-stu-id="e7db6-118">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="e7db6-119">Edge 伺服器存取介面</span><span class="sxs-lookup"><span data-stu-id="e7db6-119">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="e7db6-120">針對使用 SIP 的同盟與公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="e7db6-120">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db6-121">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e7db6-121">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e7db6-122">Edge 伺服器存取介面</span><span class="sxs-lookup"><span data-stu-id="e7db6-122">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="e7db6-123">公用 IM 連線性合作夥伴</span><span class="sxs-lookup"><span data-stu-id="e7db6-123">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="e7db6-124">針對使用 SIP 的同盟與公用 IM 連線。</span><span class="sxs-lookup"><span data-stu-id="e7db6-124">For federated and public IM connectivity that use SIP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db6-125">Access/SIP （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e7db6-125">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e7db6-126">台</span><span class="sxs-lookup"><span data-stu-id="e7db6-126">Clients</span></span></p></td>
<td><p><span data-ttu-id="e7db6-127">Edge 伺服器存取介面</span><span class="sxs-lookup"><span data-stu-id="e7db6-127">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="e7db6-128">供外部使用者存取的用戶端到伺服器 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="e7db6-128">Client-to-server SIP traffic for external user access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db6-129">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="e7db6-129">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e7db6-130">Edge 伺服器存取介面</span><span class="sxs-lookup"><span data-stu-id="e7db6-130">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="e7db6-131">即時 Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="e7db6-131">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="e7db6-132">在已設定公用 IM 連線的情況中，使用 Windows Live Messenger 進行 A/V 會話。</span><span class="sxs-lookup"><span data-stu-id="e7db6-132">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7db6-133">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e7db6-133">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e7db6-134">Edge 伺服器存取介面</span><span class="sxs-lookup"><span data-stu-id="e7db6-134">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="e7db6-135">即時 Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="e7db6-135">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="e7db6-136">對於使用 Windows Live Messenger 的公用 IM 連線是必要的。</span><span class="sxs-lookup"><span data-stu-id="e7db6-136">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7db6-137">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e7db6-137">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e7db6-138">即時 Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="e7db6-138">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="e7db6-139">Edge 伺服器存取介面</span><span class="sxs-lookup"><span data-stu-id="e7db6-139">Edge Server Access interface</span></span></p></td>
<td><p><span data-ttu-id="e7db6-140">對於使用 Windows Live Messenger 的公用 IM 連線是必要的。</span><span class="sxs-lookup"><span data-stu-id="e7db6-140">Required for public IM connectivity with Windows Live Messenger.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e7db6-141">請參閱</span><span class="sxs-lookup"><span data-stu-id="e7db6-141">See Also</span></span>


[<span data-ttu-id="e7db6-142">Lync Server 2013 中的外部使用者存取案例</span><span class="sxs-lookup"><span data-stu-id="e7db6-142">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="e7db6-143">決定 Lync Server 2013 的外部 A/V 防火牆和連接埠需求</span><span class="sxs-lookup"><span data-stu-id="e7db6-143">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

