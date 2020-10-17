---
title: 'Lync Server 2013：管理服務品質 (QoS) '
description: Lync Server 2013：管理服務品質 (QoS) 。
ms.reviewer: ''
f1.keywords:
- NOCSH
TOCTitle: Managing Quality of Service (QoS)
author: lanachin
ms.author: v-lanac
ms.manager: serdars
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df0e84389cc030cd63fe04c46929bd981a074aec
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552719"
---
# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a><span data-ttu-id="cc3c6-103">在 Lync Server 2013 中管理服務品質 (QoS) </span><span class="sxs-lookup"><span data-stu-id="cc3c6-103">Managing Quality of Service (QoS) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc3c6-104">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="cc3c6-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="cc3c6-105">服務品質 (QoS) 是某些組織所用的網路技術，可協助提供最佳的音訊和視頻通訊使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-105">Quality of Service (QoS) is a networking technology used in some organizations to help provide an optimal end-user experience for audio and video communications.</span></span> <span data-ttu-id="cc3c6-106">QoS 最常用於頻寬有限的網路：有大量網路資料包會爭用相對的可用頻寬量，服務品質可為系統管理員提供一種方法，讓系統管理員可以將較高優先順序指派給攜帶音訊或視頻資料的封包。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-106">QoS is most-commonly used on networks where bandwidth is limited: with a large number of network packets competing for a relatively small amount of available bandwidth, Quality of Service provides a way for administrators to assign higher priorities to packets carrying audio or video data.</span></span> <span data-ttu-id="cc3c6-107">透過將這些封包以較高優先順序傳送，音訊和影片通訊的速度可能會更快，且中斷較低，其方式就是檔案傳輸、網頁流覽或資料庫備份等相關的網路會話。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-107">By giving these packets a higher priority, audio and video communications are likely to complete faster, and with less interruption, than network sessions involving things like file transfers, web browsing, or database backups.</span></span> <span data-ttu-id="cc3c6-108">這是因為用於進行檔案傳輸或資料庫備份的網路封包是以「最大努力」優先順序指派。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-108">That's because network packets used for file transfers or database backups are assigned a "best effort" priority.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cc3c6-109">一般來說，服務品質只適用于內部網路上的通訊會話。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-109">As a general rule, Quality of Service applies only to communication sessions on your internal network.</span></span> <span data-ttu-id="cc3c6-110">當您執行 QoS 時，會設定您的伺服器和路由器以支援封包標記;不過，您可以設定這些裝置以特定方式支援封包標記。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-110">When you implement QoS, you configure your servers and routers to support packet marking; however, you configure these devices to support packet marking in a particular manner.</span></span> <span data-ttu-id="cc3c6-111">您無法假定在網際網路或其他網路上都支援服務品質。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-111">You cannot assume that Quality of Service will be supported on the Internet or on other networks.</span></span> <span data-ttu-id="cc3c6-112">即使其他網路上支援品質的服務，也無法保證 QoS 會以您在網路上設定服務的相同方式來設定。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-112">Even if Quality if Service is supported on other networks, there is no guarantee that QoS will be configured the same way that you configured the service on your network.</span></span>



</div>

<span data-ttu-id="cc3c6-113">Microsoft Lync Server 2013 不需要服務品質;如果您目前未使用 QoS 您不需要在安裝 Lync Server 2013 之前安裝服務。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-113">Microsoft Lync Server 2013 does not require Quality of Service; if you do not currently use QoS there is no requirement that you install the service before installing Lync Server 2013.</span></span> <span data-ttu-id="cc3c6-114">如果您的網路上有大量的封包遺失，建議的方法是緩解此問題，以增加額外的頻寬。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-114">If you experience a considerable amount of packet loss on your network the recommended way to alleviate this problem is to add additional bandwidth.</span></span> <span data-ttu-id="cc3c6-115">如果無法新增更多的頻寬，您可能想要改為執行服務品質。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-115">If adding more bandwidth is not possible, then you might want to implement Quality of Service instead.</span></span>

<span data-ttu-id="cc3c6-116">Lync Server 2013 為服務品質提供完整支援：這表示已使用 QoS 的組織可以輕鬆地將 Lync Server 整合至現有的網路基礎結構。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-116">Lync Server 2013 offers full support for Quality of Service: that means that organizations that are already using QoS can easily integrate Lync Server into their existing network infrastructure.</span></span> <span data-ttu-id="cc3c6-117">為了達到此目的，您必須執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="cc3c6-117">In order to do this you must perform the following tasks:</span></span>

  - <span data-ttu-id="cc3c6-118">[為不是以 Windows 為基礎的裝置啟用 Lync Server 2013 中的 QoS](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md)。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-118">[Enabling QoS in Lync Server 2013 for devices that are not based on Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span></span> <span data-ttu-id="cc3c6-119">根據預設，系統會停用電腦及其他裝置的 QoS，例如執行其他作業系統的 Iphone) 等 (。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-119">By default, QoS is disabled for computers and other devices (such as iPhones) that run other operating systems.</span></span> <span data-ttu-id="cc3c6-120">雖然您可以使用 Lync Server 來啟用及停用裝置的服務品質，但通常無法使用產品修改這些裝置所使用的 DSCP 代碼。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-120">Although you can use Lync Server to enable and disable Quality of Service for devices, you typically cannot use the product to modify the DSCP codes used by these devices.</span></span>

  - <span data-ttu-id="cc3c6-121">[針對會議、應用程式及轉送伺服器，在 Lync Server 2013 中設定埠範圍](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-121">[Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="cc3c6-122">您必須為不同的封包類型（如音訊和影片）預約一組獨特的埠。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-122">You must reserve a unique set of ports for different packet types, such as audio and video.</span></span> <span data-ttu-id="cc3c6-123">透過 Lync Server 2013，您未啟用或停用服務品質，例如，將屬性值設定為 True 或 False。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-123">With Lync Server 2013 you do not enable or disable Quality of Service by, say, setting a property value to True or to False.</span></span> <span data-ttu-id="cc3c6-124">相反地，您可以設定埠範圍，然後建立及套用群組原則，以啟用服務品質。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-124">Instead, you enable Quality of Service by configuring port ranges and then creating and applying Group Policy.</span></span> <span data-ttu-id="cc3c6-125">如果您稍後決定不使用 QoS 您只要移除適當的群組原則物件，就可以「停用」服務品質。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-125">If you later decide not to use QoS you can “disable” Quality of Service simply by removing the appropriate Group Policy objects.</span></span>

  - <span data-ttu-id="cc3c6-126">[在 Lync Server 2013 中設定 Edge server 的埠範圍](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-126">[Configuring port ranges for your Edge Servers in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md).</span></span> <span data-ttu-id="cc3c6-127">您可以將 Edge server 設定成使用與其他伺服器相同的埠範圍，但這不是必要的。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-127">Although not required, you can configure your Edge servers to use the same port ranges as your other servers.</span></span>

  - <span data-ttu-id="cc3c6-128">[在 Lync Server 2013 中設定 Microsoft Lync 用戶端的埠範圍](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-128">[Configuring port ranges for your Microsoft Lync clients in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md).</span></span> <span data-ttu-id="cc3c6-129">這些埠範圍只適用于用戶端電腦，通常與伺服器上設定的埠範圍不同。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-129">These port ranges apply only to client computers and are typically not the same as the port ranges configured on your servers.</span></span>

  - <span data-ttu-id="cc3c6-130">[針對會議、應用程式及轉送伺服器，在 Lync Server 2013 中設定服務品質原則](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-130">[Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="cc3c6-131">這些原則決定適用于不同的資料包類型的 DSCP 代碼。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-131">These policies determine the DSCP codes that are applied to different packet types.</span></span>

  - <span data-ttu-id="cc3c6-132">[在 Lync Server 2013 中為您的 A/V Edge server 設定品質服務原則](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-132">[Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md).</span></span> <span data-ttu-id="cc3c6-133">這只應該針對 Edge server 的內部端進行。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-133">This should only be done for the internal side of your Edge servers.</span></span> <span data-ttu-id="cc3c6-134">這是因為服務品質已設計為用於內部網路，而不是在網際網路上。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-134">That's because Quality of Service is designed for use on your internal network and not on the Internet.</span></span>

  - <span data-ttu-id="cc3c6-135">[針對在 windows 7 或 windows 8 上執行的用戶端，在 Lync Server 2013 中設定服務品質原則](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md)。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-135">[Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md).</span></span> <span data-ttu-id="cc3c6-136">請注意，Microsoft Lync Server 2013 不支援其他 Windows 作業系統（如 Windows Vista 或 Windows XP）的 QoS。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-136">Note that Microsoft Lync Server 2013 does not support QoS for other Windows operating systems, such as Windows Vista or Windows XP.</span></span>

  - <span data-ttu-id="cc3c6-137">[在 Lync Server 2013 中設定 Microsoft Lync Phone Edition 裝置上的服務品質](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-137">[Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md).</span></span> <span data-ttu-id="cc3c6-138">根據預設，Lync Phone Edition 裝置會啟用 QoS。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-138">By default, QoS is enabled for Lync Phone Edition devices.</span></span> <span data-ttu-id="cc3c6-139">不過，您可能會想要變更預設 DSCP 值，以確保組織中的所有音訊封包都使用相同的 DSCP 碼。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-139">However, you might want to change the default DSCP value in order to ensure that all audio packets in your organization use the same DSCP code.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cc3c6-140">如果您使用的是 Microsoft Windows Server 2012 或 Windows Server 2012 R2，您可能會對一組新的 Windows PowerShell Cmdlet 感興趣，以在該平臺上管理服務品質。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-140">If you are using Microsoft Windows Server 2012 or Windows Server 2012 R2 you might be interested in the new set of Windows PowerShell cmdlets available for managing Quality of Service on that platform.</span></span> <span data-ttu-id="cc3c6-141">如需詳細資訊，請參閱 Windows PowerShell 中的網路服務指令程式品質 Cmdlet [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps) 。</span><span class="sxs-lookup"><span data-stu-id="cc3c6-141">For more information, see Network Quality of Service Cmdlets in Windows PowerShell at [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

