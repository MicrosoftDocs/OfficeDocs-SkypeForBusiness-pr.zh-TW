---
title: Lync Server 2013：受支援的虛擬化技術與已知限制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b5c99151be45f70d1d95fa0a89835ebb6f7d352
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a><span data-ttu-id="cd45b-102">Lync Server 2013 中受支援的虛擬化技術與已知限制</span><span class="sxs-lookup"><span data-stu-id="cd45b-102">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd45b-103">_**主題上次修改日期：** 2017-02-06_</span><span class="sxs-lookup"><span data-stu-id="cd45b-103">_**Topic Last Modified:** 2017-02-06_</span></span>

<span data-ttu-id="cd45b-104">Lync VDI 外掛程式可支援音訊及視頻通話（支援的虛擬化技術）。</span><span class="sxs-lookup"><span data-stu-id="cd45b-104">The Lync VDI plug-in allows audio and video calling for supported virtualization technologies.</span></span> <span data-ttu-id="cd45b-105">這會在[Microsoft lync 2010 白皮書的用戶端虛擬化](https://go.microsoft.com/fwlink/?linkid=330447)中擴充 Microsoft lync Server 2010 所列的功能。</span><span class="sxs-lookup"><span data-stu-id="cd45b-105">This extends the functionality outlined for Microsoft Lync Server 2010 in the [Client Virtualization in Microsoft Lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) white paper.</span></span> <span data-ttu-id="cd45b-106">在遵守標準電話規章的情況下，也包含對 E911 的支援。</span><span class="sxs-lookup"><span data-stu-id="cd45b-106">In compliance with standard telephone regulations, support for E911 is also included.</span></span> <span data-ttu-id="cd45b-107">下列各節說明 Lync VDI 外掛程式所支援的虛擬化技術和已知的功能限制。</span><span class="sxs-lookup"><span data-stu-id="cd45b-107">The following sections describe the virtualization technologies that are supported by the Lync VDI plug-in and the known feature limitations.</span></span>

<div>

## <a name="support-for-virtualization-technologies"></a><span data-ttu-id="cd45b-108">對虛擬化技術的支援</span><span class="sxs-lookup"><span data-stu-id="cd45b-108">Support for Virtualization Technologies</span></span>

<span data-ttu-id="cd45b-109">Lync VDI 外掛程式支援個人虛擬桌面案例中的完整桌面遠端作業，但在遠端桌面會話案例中則不支援。</span><span class="sxs-lookup"><span data-stu-id="cd45b-109">The Lync VDI plug-in supports full desktop remoting in the personal virtual desktop scenario, but not in the remote desktop session scenario.</span></span> <span data-ttu-id="cd45b-110">這些案例的描述如下：</span><span class="sxs-lookup"><span data-stu-id="cd45b-110">These scenarios can be described as follows:</span></span>

  - <span data-ttu-id="cd45b-111">**支援：個人化的虛擬桌面或虛擬桌面基礎結構（VDI）。**   在這種情況下，每個使用者都會登入可自訂的虛擬桌面電腦，並能夠在桌上型電腦上儲存跨會話的檔案。</span><span class="sxs-lookup"><span data-stu-id="cd45b-111">**Supported: Personalized Virtual Desktops or Virtual Desktop Infrastructure (VDI).**   In this scenario, each user logs on to a customizable virtual desktop and is able to save files on the desktop that persist across sessions.</span></span> <span data-ttu-id="cd45b-112">Microsoft 遠端桌面服務、VMware 地平線視圖和 Citrix XenDesktop 是已經過測試，可搭配 Lync 使用的實現。</span><span class="sxs-lookup"><span data-stu-id="cd45b-112">Microsoft Remote Desktop Services, VMware Horizon View, and Citrix XenDesktop are implementations that have been tested for use with Lync.</span></span> <span data-ttu-id="cd45b-113">如需有關已由 Microsoft 測試的供應商專用 VDI 環境及用戶端硬體的相關資訊，請參閱[Microsoft Lync 合格的基礎結構](https://go.microsoft.com/fwlink/?linkid=313435)。</span><span class="sxs-lookup"><span data-stu-id="cd45b-113">For information about vendor-specific VDI environments and client hardware that have been tested by Microsoft, see [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span></span>

  - <span data-ttu-id="cd45b-114">**不支援： [遠端桌面會話]。**   在這種情況下，每個使用者都會登入不能自訂的一般虛擬桌面會話。</span><span class="sxs-lookup"><span data-stu-id="cd45b-114">**Not supported: Remote Desktop Sessions.**   In this scenario, each user logs on to a generic virtual desktop session that cannot be customized.</span></span> <span data-ttu-id="cd45b-115">實作範例包括 Microsoft 遠端桌面工作階段 (RDSH) 和結合 Citrix 接收器的 Citrix XenApp。</span><span class="sxs-lookup"><span data-stu-id="cd45b-115">Example implementations include Microsoft Remote Desktop Sessions (RDSH) and Citrix XenApp combined with Citrix Receiver.</span></span>

<span data-ttu-id="cd45b-116">Lync VDI 外掛程式不支援其他虛擬化技術（例如應用程式虛擬化），可讓您使用應用程式，而不需要在本機安裝完整的應用程式。</span><span class="sxs-lookup"><span data-stu-id="cd45b-116">The Lync VDI plug-in does not support other virtualization technologies, such as application virtualization, which allows the use of an application without requiring installation of the full application locally.</span></span> <span data-ttu-id="cd45b-117">範例實現包括 Citrix XenApp 和 Microsoft Application Virtualization （App-v）。</span><span class="sxs-lookup"><span data-stu-id="cd45b-117">Example implementations include Citrix XenApp and Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="cd45b-118">不支援應用程式流式處理、應用程式遠端處理及混合式虛擬化模式（例如，完整桌面遠端處理中的應用程式遠端處理）。</span><span class="sxs-lookup"><span data-stu-id="cd45b-118">Application streaming, application remoting, and mixed virtualization modes (for example, application remoting in full desktop remoting) are not supported.</span></span>

<span data-ttu-id="cd45b-119">若要允許擴充性，Lync VDI 外掛程式的設計目的是使用稱為「動態虛擬通道」（DVCs）的平臺無關 Api。</span><span class="sxs-lookup"><span data-stu-id="cd45b-119">To allow extensibility, the Lync VDI plug-in was designed to use platform-independent APIs called Dynamic Virtual Channels (DVCs).</span></span> <span data-ttu-id="cd45b-120">針對 Lync 未明確支援的案例，請參閱來自 VDI 解決方案提供者的支援聲明。</span><span class="sxs-lookup"><span data-stu-id="cd45b-120">For scenarios that are not explicitly supported by Lync, refer to support statements from the VDI solution provider.</span></span>

</div>

<div>

## <a name="known-feature-limitations"></a><span data-ttu-id="cd45b-121">已知的功能限制</span><span class="sxs-lookup"><span data-stu-id="cd45b-121">Known Feature Limitations</span></span>

<span data-ttu-id="cd45b-122">當您在 VDI 環境中使用 Lync 2013 時，以下是已知的限制：</span><span class="sxs-lookup"><span data-stu-id="cd45b-122">The following are known limitations when you use Lync 2013 in a VDI environment:</span></span>

  - <span data-ttu-id="cd45b-123">通話委派與回應群組代理匿名功能的支援有限。</span><span class="sxs-lookup"><span data-stu-id="cd45b-123">There is limited support for Call Delegation and Response Group Agent Anonymization features.</span></span>

  - <span data-ttu-id="cd45b-124">不支援以下功能：</span><span class="sxs-lookup"><span data-stu-id="cd45b-124">There is no support for the following features:</span></span>
    
      - <span data-ttu-id="cd45b-125">整合式音訊裝置及視訊裝置調整頁面。</span><span class="sxs-lookup"><span data-stu-id="cd45b-125">Integrated Audio Device and Video Device tuning pages.</span></span>
    
      - <span data-ttu-id="cd45b-126">多重檢視視訊。</span><span class="sxs-lookup"><span data-stu-id="cd45b-126">Multiple-view video.</span></span>
    
      - <span data-ttu-id="cd45b-127">錄製交談。</span><span class="sxs-lookup"><span data-stu-id="cd45b-127">Recording of conversations.</span></span>
    
      - <span data-ttu-id="cd45b-128">遠端桌面服務（RDS）。</span><span class="sxs-lookup"><span data-stu-id="cd45b-128">Remote Desktop Services (RDS).</span></span>
    
      - <span data-ttu-id="cd45b-129">匿名加入會議（也就是加入不與您的組織聯盟之組織託管的 Lync 會議）。</span><span class="sxs-lookup"><span data-stu-id="cd45b-129">Joining meetings anonymously (that is, joining Lync meetings hosted by an organization that does not federate with your organization).</span></span>
    
      - <span data-ttu-id="cd45b-130">將 Lync VDI 外掛程式與 Lync Phone Edition 裝置搭配使用。</span><span class="sxs-lookup"><span data-stu-id="cd45b-130">Using the Lync VDI plug-in along with a Lync Phone Edition device.</span></span>
    
      - <span data-ttu-id="cd45b-131">在網路中斷連線的情況下延續通話。</span><span class="sxs-lookup"><span data-stu-id="cd45b-131">Call continuity in case of a network outage.</span></span>
    
      - <span data-ttu-id="cd45b-132">自訂鈴聲及通話保留音樂功能。</span><span class="sxs-lookup"><span data-stu-id="cd45b-132">Customized ringtones and music-on-hold features.</span></span>

  - <span data-ttu-id="cd45b-133">在 Office 365 環境中不支援 Lync VDI 外掛程式。</span><span class="sxs-lookup"><span data-stu-id="cd45b-133">The Lync VDI plug-in is not supported in an Office 365 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

