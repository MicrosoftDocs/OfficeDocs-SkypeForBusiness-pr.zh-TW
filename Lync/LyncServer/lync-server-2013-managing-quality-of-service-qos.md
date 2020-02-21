---
title: Lync Server 2013： 管理服務的品質 (QoS)
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
ms.openlocfilehash: 13d96132357e1981214961f136cf5365cf74907a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a><span data-ttu-id="0eef8-102">管理服務的品質 (QoS 在 Lync Server 2013)</span><span class="sxs-lookup"><span data-stu-id="0eef8-102">Managing Quality of Service (QoS) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0eef8-103">_**上次修改主題：** 2013年-11-07_</span><span class="sxs-lookup"><span data-stu-id="0eef8-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="0eef8-104">服務品質 (QoS) 是一種網路技術，在某些組織中用於協助提供最佳使用者經驗的音訊及視訊通訊。</span><span class="sxs-lookup"><span data-stu-id="0eef8-104">Quality of Service (QoS) is a networking technology used in some organizations to help provide an optimal end-user experience for audio and video communications.</span></span> <span data-ttu-id="0eef8-105">QoS 最常用於網路頻寬所在有限： 設立了許多網路封包競用相當少量的可用頻寬，Quality of Service 提供讓系統管理員指派給封包的較高的優先順序持有音訊或視訊資料。</span><span class="sxs-lookup"><span data-stu-id="0eef8-105">QoS is most-commonly used on networks where bandwidth is limited: with a large number of network packets competing for a relatively small amount of available bandwidth, Quality of Service provides a way for administrators to assign higher priorities to packets carrying audio or video data.</span></span> <span data-ttu-id="0eef8-106">授與這些封包優先順序較高，音訊和視訊通訊未經過可能會完成速度更快，並使用較少的中斷，比涉及之類的檔案傳輸、 網站瀏覽]，或資料庫備份的網路工作階段。</span><span class="sxs-lookup"><span data-stu-id="0eef8-106">By giving these packets a higher priority, audio and video communications are likely to complete faster, and with less interruption, than network sessions involving things like file transfers, web browsing, or database backups.</span></span> <span data-ttu-id="0eef8-107">這是因為用於檔案傳輸或資料庫備份的網路封包指派 「 最佳投入比 」 的優先順序。</span><span class="sxs-lookup"><span data-stu-id="0eef8-107">That's because network packets used for file transfers or database backups are assigned a "best effort" priority.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0eef8-108">一般而言，Quality of Service 僅適用於您的內部網路上的通訊工作階段。</span><span class="sxs-lookup"><span data-stu-id="0eef8-108">As a general rule, Quality of Service applies only to communication sessions on your internal network.</span></span> <span data-ttu-id="0eef8-109">當您實作 QoS 時，設定您的伺服器和路由器，以支援封包標示;不過，您設定這些裝置所支援封包標示以特定方式。</span><span class="sxs-lookup"><span data-stu-id="0eef8-109">When you implement QoS, you configure your servers and routers to support packet marking; however, you configure these devices to support packet marking in a particular manner.</span></span> <span data-ttu-id="0eef8-110">您不能假定其他網路或網際網路上，將支援的服務品質。</span><span class="sxs-lookup"><span data-stu-id="0eef8-110">You cannot assume that Quality of Service will be supported on the Internet or on other networks.</span></span> <span data-ttu-id="0eef8-111">即使品質服務支援其他網路上是否有不保證能 QoS 設定您網路上設定服務的方式相同。</span><span class="sxs-lookup"><span data-stu-id="0eef8-111">Even if Quality if Service is supported on other networks, there is no guarantee that QoS will be configured the same way that you configured the service on your network.</span></span>



</div>

<span data-ttu-id="0eef8-112">Microsoft Lync Server 2013 不需要的服務品質;如果您目前未使用 QoS，沒有安裝 Lync Server 2013 之前先安裝服務的需求。</span><span class="sxs-lookup"><span data-stu-id="0eef8-112">Microsoft Lync Server 2013 does not require Quality of Service; if you do not currently use QoS there is no requirement that you install the service before installing Lync Server 2013.</span></span> <span data-ttu-id="0eef8-113">如果您遇到相當可觀的封包遺失在您的網路以避免此問題的建議方式是將新增額外的頻寬。</span><span class="sxs-lookup"><span data-stu-id="0eef8-113">If you experience a considerable amount of packet loss on your network the recommended way to alleviate this problem is to add additional bandwidth.</span></span> <span data-ttu-id="0eef8-114">如果新增更多的頻寬不可行，您可能想要改為實作的服務品質。</span><span class="sxs-lookup"><span data-stu-id="0eef8-114">If adding more bandwidth is not possible, then you might want to implement Quality of Service instead.</span></span>

<span data-ttu-id="0eef8-115">Lync Server 2013 提供的服務品質的完整支援:，表示已經在使用 QoS 的組織可以輕鬆地將 Lync Server 整合到其現有的網路基礎結構。</span><span class="sxs-lookup"><span data-stu-id="0eef8-115">Lync Server 2013 offers full support for Quality of Service: that means that organizations that are already using QoS can easily integrate Lync Server into their existing network infrastructure.</span></span> <span data-ttu-id="0eef8-116">若要這麼做，您必須執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="0eef8-116">In order to do this you must perform the following tasks:</span></span>

  - <span data-ttu-id="0eef8-117">[裝置不採用 Windows 的 Lync Server 2013 中啟用 QoS](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md)。</span><span class="sxs-lookup"><span data-stu-id="0eef8-117">[Enabling QoS in Lync Server 2013 for devices that are not based on Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span></span> <span data-ttu-id="0eef8-118">根據預設，QoS 已停用的電腦及其他裝置 （例如 Iphone) 執行其他的作業系統。</span><span class="sxs-lookup"><span data-stu-id="0eef8-118">By default, QoS is disabled for computers and other devices (such as iPhones) that run other operating systems.</span></span> <span data-ttu-id="0eef8-119">雖然您可以使用 Lync Server 來啟用及停用裝置的服務品質，您通常無法使用產品來修改這些裝置所用的 DSCP 代碼。</span><span class="sxs-lookup"><span data-stu-id="0eef8-119">Although you can use Lync Server to enable and disable Quality of Service for devices, you typically cannot use the product to modify the DSCP codes used by these devices.</span></span>

  - <span data-ttu-id="0eef8-120">[設定會議、 應用程式及中繼伺服器的 Lync Server 2013 中的連接埠範圍](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="0eef8-120">[Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="0eef8-121">您必須保留一組唯一不同的封包類型，例如音訊和視訊的連接埠。</span><span class="sxs-lookup"><span data-stu-id="0eef8-121">You must reserve a unique set of ports for different packet types, such as audio and video.</span></span> <span data-ttu-id="0eef8-122">搭配 Lync Server 2013 您不要未啟用或停用服務品質，說，屬性值設定為 True 或 False。</span><span class="sxs-lookup"><span data-stu-id="0eef8-122">With Lync Server 2013 you do not enable or disable Quality of Service by, say, setting a property value to True or to False.</span></span> <span data-ttu-id="0eef8-123">相反地，您會藉由設定連接埠範圍然後建立並套用群組原則啟用的服務品質。</span><span class="sxs-lookup"><span data-stu-id="0eef8-123">Instead, you enable Quality of Service by configuring port ranges and then creating and applying Group Policy.</span></span> <span data-ttu-id="0eef8-124">如果您稍後決定不應使用 QoS 您可以 「 停用 「 服務品質只移除適當的群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="0eef8-124">If you later decide not to use QoS you can “disable” Quality of Service simply by removing the appropriate Group Policy objects.</span></span>

  - <span data-ttu-id="0eef8-125">[設定 Lync Server 2013 Edge Server 的連接埠範圍](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="0eef8-125">[Configuring port ranges for your Edge Servers in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md).</span></span> <span data-ttu-id="0eef8-126">雖然並非必要，您可以設定您的 Edge server 使用相同的連接埠範圍作為其他的伺服器。</span><span class="sxs-lookup"><span data-stu-id="0eef8-126">Although not required, you can configure your Edge servers to use the same port ranges as your other servers.</span></span>

  - <span data-ttu-id="0eef8-127">[設定您的 Microsoft Lync 用戶端，Lync Server 2013 中的連接埠範圍](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="0eef8-127">[Configuring port ranges for your Microsoft Lync clients in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md).</span></span> <span data-ttu-id="0eef8-128">這些連接埠範圍僅適用於用戶端電腦和通常不是在您的伺服器上設定的連接埠範圍相同。</span><span class="sxs-lookup"><span data-stu-id="0eef8-128">These port ranges apply only to client computers and are typically not the same as the port ranges configured on your servers.</span></span>

  - <span data-ttu-id="0eef8-129">[設定會議、 應用程式及中繼伺服器的 Lync Server 2013 中的服務品質原則](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="0eef8-129">[Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="0eef8-130">這些原則決定套用至不同的封包類型的 DSCP 代碼。</span><span class="sxs-lookup"><span data-stu-id="0eef8-130">These policies determine the DSCP codes that are applied to different packet types.</span></span>

  - <span data-ttu-id="0eef8-131">[設定服務品質原則的 A / V Edge Server 在 Lync Server 2013 中](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md)。</span><span class="sxs-lookup"><span data-stu-id="0eef8-131">[Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md).</span></span> <span data-ttu-id="0eef8-132">這只應為您的 Edge server 之對內端。</span><span class="sxs-lookup"><span data-stu-id="0eef8-132">This should only be done for the internal side of your Edge servers.</span></span> <span data-ttu-id="0eef8-133">這是因為 Quality of Service 設計用於您的內部網路上並不是在網際網路上。</span><span class="sxs-lookup"><span data-stu-id="0eef8-133">That's because Quality of Service is designed for use on your internal network and not on the Internet.</span></span>

  - <span data-ttu-id="0eef8-134">[在 Windows 7 或 Windows 8 上執行的用戶端的 Lync Server 2013 中設定服務品質原則](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md)。</span><span class="sxs-lookup"><span data-stu-id="0eef8-134">[Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md).</span></span> <span data-ttu-id="0eef8-135">請注意，Microsoft Lync Server 2013 不支援 QoS 適用於其他 Windows 作業系統，例如 Windows Vista 或 Windows XP。</span><span class="sxs-lookup"><span data-stu-id="0eef8-135">Note that Microsoft Lync Server 2013 does not support QoS for other Windows operating systems, such as Windows Vista or Windows XP.</span></span>

  - <span data-ttu-id="0eef8-136">[設定服務品質 Lync Server 2013 中的 Microsoft Lync Phone Edition 裝置上](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="0eef8-136">[Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md).</span></span> <span data-ttu-id="0eef8-137">根據預設，QoS 已啟用 Lync Phone Edition 裝置。</span><span class="sxs-lookup"><span data-stu-id="0eef8-137">By default, QoS is enabled for Lync Phone Edition devices.</span></span> <span data-ttu-id="0eef8-138">不過，您可能想要變更預設的 DSCP 值，以確保組織中的所有音訊封包都使用相同的 DSCP 程式碼。</span><span class="sxs-lookup"><span data-stu-id="0eef8-138">However, you might want to change the default DSCP value in order to ensure that all audio packets in your organization use the same DSCP code.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0eef8-139">如果您使用 Microsoft Windows Server 2012 或 Windows Server 2012 R2 您可能會感興趣一組新的 Windows PowerShell cmdlet 可用於管理該平台上的服務品質。</span><span class="sxs-lookup"><span data-stu-id="0eef8-139">If you are using Microsoft Windows Server 2012 or Windows Server 2012 R2 you might be interested in the new set of Windows PowerShell cmdlets available for managing Quality of Service on that platform.</span></span> <span data-ttu-id="0eef8-140">如需詳細資訊，請參閱網路品質的服務中的指令程式在 Windows PowerShell [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)。</span><span class="sxs-lookup"><span data-stu-id="0eef8-140">For more information, see Network Quality of Service Cmdlets in Windows PowerShell at [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

