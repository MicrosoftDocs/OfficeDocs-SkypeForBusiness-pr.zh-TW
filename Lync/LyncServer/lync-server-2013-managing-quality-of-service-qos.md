---
title: Lync Server 2013：管理服務品質（QoS）
ms.reviewer: ''
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
ms.openlocfilehash: 96f25d35f0d96c9e1681c6b4d2c2c3b3079aad34
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a><span data-ttu-id="479e7-102">管理 Lync Server 2013 中的服務品質（QoS）</span><span class="sxs-lookup"><span data-stu-id="479e7-102">Managing Quality of Service (QoS) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="479e7-103">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="479e7-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="479e7-104">服務品質（QoS）是一些組織所用的網路技術，可協助提供最佳的音訊和視頻通訊使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="479e7-104">Quality of Service (QoS) is a networking technology used in some organizations to help provide an optimal end-user experience for audio and video communications.</span></span> <span data-ttu-id="479e7-105">QoS 最常用於頻寬有限的網路上：有大量網路資料包爭用相對較少的可用頻寬，服務品質會提供一種方式，讓管理員指派較高優先順序至資料包攜帶音訊或視頻資料。</span><span class="sxs-lookup"><span data-stu-id="479e7-105">QoS is most-commonly used on networks where bandwidth is limited: with a large number of network packets competing for a relatively small amount of available bandwidth, Quality of Service provides a way for administrators to assign higher priorities to packets carrying audio or video data.</span></span> <span data-ttu-id="479e7-106">透過將這些資料包設為較高的優先順序，音訊與視頻通訊可能會更快且中斷較少，因為涉及檔案傳輸、網頁流覽或資料庫備份等操作的網路會話。</span><span class="sxs-lookup"><span data-stu-id="479e7-106">By giving these packets a higher priority, audio and video communications are likely to complete faster, and with less interruption, than network sessions involving things like file transfers, web browsing, or database backups.</span></span> <span data-ttu-id="479e7-107">這是因為用於檔案傳輸或資料庫備份的網路資料包已獲指派「最大努力」的優先順序。</span><span class="sxs-lookup"><span data-stu-id="479e7-107">That's because network packets used for file transfers or database backups are assigned a "best effort" priority.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="479e7-108">一般來說，服務品質只適用于內部網路上的通訊會話。</span><span class="sxs-lookup"><span data-stu-id="479e7-108">As a general rule, Quality of Service applies only to communication sessions on your internal network.</span></span> <span data-ttu-id="479e7-109">當您實現 QoS 時，請將您的伺服器和路由器設定為支援資料包標記;不過，您可以將這些裝置設定為支援以特定方式進行資料包標記。</span><span class="sxs-lookup"><span data-stu-id="479e7-109">When you implement QoS, you configure your servers and routers to support packet marking; however, you configure these devices to support packet marking in a particular manner.</span></span> <span data-ttu-id="479e7-110">您無法假設在網際網路或其他網路上不支援該服務品質。</span><span class="sxs-lookup"><span data-stu-id="479e7-110">You cannot assume that Quality of Service will be supported on the Internet or on other networks.</span></span> <span data-ttu-id="479e7-111">即使在其他網路上支援 Quality Services，也不會保證 QoS 的設定方式與您在網路上設定服務的方式相同。</span><span class="sxs-lookup"><span data-stu-id="479e7-111">Even if Quality if Service is supported on other networks, there is no guarantee that QoS will be configured the same way that you configured the service on your network.</span></span>



</div>

<span data-ttu-id="479e7-112">Microsoft Lync Server 2013 不需要服務品質;如果您目前未使用 QoS，就不需要在安裝 Lync Server 2013 之前安裝該服務。</span><span class="sxs-lookup"><span data-stu-id="479e7-112">Microsoft Lync Server 2013 does not require Quality of Service; if you do not currently use QoS there is no requirement that you install the service before installing Lync Server 2013.</span></span> <span data-ttu-id="479e7-113">如果您在網路上遇到大量的資料包遺失，建議的方式就是緩解這個問題，就是要增加額外的頻寬。</span><span class="sxs-lookup"><span data-stu-id="479e7-113">If you experience a considerable amount of packet loss on your network the recommended way to alleviate this problem is to add additional bandwidth.</span></span> <span data-ttu-id="479e7-114">如果不可能增加更多頻寬，您可能會想要改為執行服務品質。</span><span class="sxs-lookup"><span data-stu-id="479e7-114">If adding more bandwidth is not possible, then you might want to implement Quality of Service instead.</span></span>

<span data-ttu-id="479e7-115">Lync Server 2013 提供完整的服務品質支援：這表示已使用 QoS 的組織可以輕鬆地將 Lync Server 整合至其現有的網路基礎結構。</span><span class="sxs-lookup"><span data-stu-id="479e7-115">Lync Server 2013 offers full support for Quality of Service: that means that organizations that are already using QoS can easily integrate Lync Server into their existing network infrastructure.</span></span> <span data-ttu-id="479e7-116">若要這樣做，您必須執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="479e7-116">In order to do this you must perform the following tasks:</span></span>

  - <span data-ttu-id="479e7-117">[在 Lync Server 2013 中針對不是以 Windows 為基礎的裝置啟用 QoS](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md)。</span><span class="sxs-lookup"><span data-stu-id="479e7-117">[Enabling QoS in Lync Server 2013 for devices that are not based on Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span></span> <span data-ttu-id="479e7-118">根據預設，系統會針對執行其他作業系統的電腦和其他裝置（例如 Iphone）停用 QoS。</span><span class="sxs-lookup"><span data-stu-id="479e7-118">By default, QoS is disabled for computers and other devices (such as iPhones) that run other operating systems.</span></span> <span data-ttu-id="479e7-119">雖然您可以使用 Lync Server 來啟用和停用裝置的服務品質，但您通常無法使用該產品來修改這些裝置所使用的 DSCP 代碼。</span><span class="sxs-lookup"><span data-stu-id="479e7-119">Although you can use Lync Server to enable and disable Quality of Service for devices, you typically cannot use the product to modify the DSCP codes used by these devices.</span></span>

  - <span data-ttu-id="479e7-120">[針對您的會議、應用程式及中繼伺服器，在 Lync Server 2013 中設定埠範圍](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="479e7-120">[Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="479e7-121">您必須為不同的資料包類型（例如音訊和影片）保留一組獨特的埠。</span><span class="sxs-lookup"><span data-stu-id="479e7-121">You must reserve a unique set of ports for different packet types, such as audio and video.</span></span> <span data-ttu-id="479e7-122">使用 Lync Server 2013，您不可以啟用或停用服務品質，比如說將屬性值設定為 True 或 False。</span><span class="sxs-lookup"><span data-stu-id="479e7-122">With Lync Server 2013 you do not enable or disable Quality of Service by, say, setting a property value to True or to False.</span></span> <span data-ttu-id="479e7-123">相反地，您必須先設定埠範圍，然後建立並套用群組原則，才能啟用服務品質。</span><span class="sxs-lookup"><span data-stu-id="479e7-123">Instead, you enable Quality of Service by configuring port ranges and then creating and applying Group Policy.</span></span> <span data-ttu-id="479e7-124">如果您稍後決定不使用 QoS，您只要移除適當的群組原則物件，就可以「停用」服務品質。</span><span class="sxs-lookup"><span data-stu-id="479e7-124">If you later decide not to use QoS you can “disable” Quality of Service simply by removing the appropriate Group Policy objects.</span></span>

  - <span data-ttu-id="479e7-125">[在 Lync Server 2013 中設定邊緣伺服器的埠範圍](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="479e7-125">[Configuring port ranges for your Edge Servers in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md).</span></span> <span data-ttu-id="479e7-126">雖然不必要，但您可以將邊緣伺服器設定為使用與其他伺服器相同的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="479e7-126">Although not required, you can configure your Edge servers to use the same port ranges as your other servers.</span></span>

  - <span data-ttu-id="479e7-127">[在 Lync Server 2013 中為您的 Microsoft Lync 用戶端設定埠範圍](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="479e7-127">[Configuring port ranges for your Microsoft Lync clients in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md).</span></span> <span data-ttu-id="479e7-128">這些埠範圍只適用于用戶端電腦，且通常與您伺服器上設定的埠範圍不同。</span><span class="sxs-lookup"><span data-stu-id="479e7-128">These port ranges apply only to client computers and are typically not the same as the port ranges configured on your servers.</span></span>

  - <span data-ttu-id="479e7-129">[針對您的會議、應用程式及中繼伺服器，在 Lync Server 2013 中設定品質服務原則](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="479e7-129">[Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="479e7-130">這些原則會判斷套用到不同資料包類型的 DSCP 代碼。</span><span class="sxs-lookup"><span data-stu-id="479e7-130">These policies determine the DSCP codes that are applied to different packet types.</span></span>

  - <span data-ttu-id="479e7-131">[在 Lync Server 2013 中設定您的 a/V 邊緣伺服器的服務品質原則](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="479e7-131">[Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md).</span></span> <span data-ttu-id="479e7-132">只能針對邊緣伺服器的內部端執行此動作。</span><span class="sxs-lookup"><span data-stu-id="479e7-132">This should only be done for the internal side of your Edge servers.</span></span> <span data-ttu-id="479e7-133">那是因為服務品質是專為在您的內部網路（而不是在網際網路）上使用而設計。</span><span class="sxs-lookup"><span data-stu-id="479e7-133">That's because Quality of Service is designed for use on your internal network and not on the Internet.</span></span>

  - <span data-ttu-id="479e7-134">[針對在 windows 7 或 windows 8 上執行的用戶端，在 Lync Server 2013 中設定服務品質原則](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md)。</span><span class="sxs-lookup"><span data-stu-id="479e7-134">[Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md).</span></span> <span data-ttu-id="479e7-135">請注意，Microsoft Lync Server 2013 不支援其他 Windows 作業系統（例如 Windows Vista 或 Windows XP）的 QoS。</span><span class="sxs-lookup"><span data-stu-id="479e7-135">Note that Microsoft Lync Server 2013 does not support QoS for other Windows operating systems, such as Windows Vista or Windows XP.</span></span>

  - <span data-ttu-id="479e7-136">[在 Lync Server 2013 中設定 Microsoft Lync Phone Edition 裝置上的服務品質](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="479e7-136">[Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md).</span></span> <span data-ttu-id="479e7-137">根據預設，Lync 手機版裝置會啟用 QoS 功能。</span><span class="sxs-lookup"><span data-stu-id="479e7-137">By default, QoS is enabled for Lync Phone Edition devices.</span></span> <span data-ttu-id="479e7-138">不過，您可能會想要變更預設 DSCP 值，以確保貴組織中的所有音訊資料包都使用相同的 DSCP 代碼。</span><span class="sxs-lookup"><span data-stu-id="479e7-138">However, you might want to change the default DSCP value in order to ensure that all audio packets in your organization use the same DSCP code.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="479e7-139">如果您使用的是 Microsoft Windows Server 2012 或 Windows Server 2012 R2，您可能會想要在該平臺上管理服務品質所用的一組新的 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="479e7-139">If you are using Microsoft Windows Server 2012 or Windows Server 2012 R2 you might be interested in the new set of Windows PowerShell cmdlets available for managing Quality of Service on that platform.</span></span> <span data-ttu-id="479e7-140">如需詳細資訊，請參閱 Windows PowerShell 中的網路服務品質[https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="479e7-140">For more information, see Network Quality of Service Cmdlets in Windows PowerShell at [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

