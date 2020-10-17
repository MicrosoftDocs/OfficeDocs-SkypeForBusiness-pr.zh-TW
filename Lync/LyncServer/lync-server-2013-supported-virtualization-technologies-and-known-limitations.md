---
title: Lync Server 2013：支援的虛擬化技術與已知限制
description: Lync Server 2013：支援的虛擬化技術與已知限制。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 745fa535462d29342f4c0a58674ee6487db42a6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544609"
---
# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a><span data-ttu-id="c7244-103">Lync Server 2013 中支援的虛擬化技術與已知限制</span><span class="sxs-lookup"><span data-stu-id="c7244-103">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7244-104">_**主題上次修改日期：** 2017-02-06_</span><span class="sxs-lookup"><span data-stu-id="c7244-104">_**Topic Last Modified:** 2017-02-06_</span></span>

<span data-ttu-id="c7244-105">Lync VDI 外掛程式允許音訊和視頻通話支援的虛擬化技術。</span><span class="sxs-lookup"><span data-stu-id="c7244-105">The Lync VDI plug-in allows audio and video calling for supported virtualization technologies.</span></span> <span data-ttu-id="c7244-106">這會在 [Microsoft lync 2010 白皮書的用戶端虛擬化](https://go.microsoft.com/fwlink/?linkid=330447) 中，擴充 Microsoft lync Server 2010 所列的功能。</span><span class="sxs-lookup"><span data-stu-id="c7244-106">This extends the functionality outlined for Microsoft Lync Server 2010 in the [Client Virtualization in Microsoft Lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) white paper.</span></span> <span data-ttu-id="c7244-107">在遵守標準電話規定時，也會包含對 E911 的支援。</span><span class="sxs-lookup"><span data-stu-id="c7244-107">In compliance with standard telephone regulations, support for E911 is also included.</span></span> <span data-ttu-id="c7244-108">下列各節說明 Lync VDI 外掛程式支援的虛擬化技術與已知的功能限制。</span><span class="sxs-lookup"><span data-stu-id="c7244-108">The following sections describe the virtualization technologies that are supported by the Lync VDI plug-in and the known feature limitations.</span></span>

<div>

## <a name="support-for-virtualization-technologies"></a><span data-ttu-id="c7244-109">虛擬化技術的支援</span><span class="sxs-lookup"><span data-stu-id="c7244-109">Support for Virtualization Technologies</span></span>

<span data-ttu-id="c7244-110">Lync VDI 外掛程式支援個人虛擬桌面案例中的完整桌面遠端處理，但不支援在遠端桌面會話案例中。</span><span class="sxs-lookup"><span data-stu-id="c7244-110">The Lync VDI plug-in supports full desktop remoting in the personal virtual desktop scenario, but not in the remote desktop session scenario.</span></span> <span data-ttu-id="c7244-111">您可以將這些案例描述如下：</span><span class="sxs-lookup"><span data-stu-id="c7244-111">These scenarios can be described as follows:</span></span>

  - <span data-ttu-id="c7244-112">**支援：個人化虛擬桌面或虛擬桌面基礎結構 (VDI) 。**    在此案例中，每一位使用者都登入至可自訂的虛擬桌面機，而且能夠將保留在會話中的檔案儲存在桌面機上。</span><span class="sxs-lookup"><span data-stu-id="c7244-112">**Supported: Personalized Virtual Desktops or Virtual Desktop Infrastructure (VDI).**   In this scenario, each user logs on to a customizable virtual desktop and is able to save files on the desktop that persist across sessions.</span></span> <span data-ttu-id="c7244-113">Microsoft 遠端桌面服務、VMware 地平線模式，以及 Citrix XenDesktop 是已測試為搭配 Lync 使用的實施方案。</span><span class="sxs-lookup"><span data-stu-id="c7244-113">Microsoft Remote Desktop Services, VMware Horizon View, and Citrix XenDesktop are implementations that have been tested for use with Lync.</span></span> <span data-ttu-id="c7244-114">如需廠商特有的 VDI 環境及已由 Microsoft 測試的用戶端硬體資訊，請參閱 [Microsoft Lync 的基礎結構限定](https://go.microsoft.com/fwlink/?linkid=313435)。</span><span class="sxs-lookup"><span data-stu-id="c7244-114">For information about vendor-specific VDI environments and client hardware that have been tested by Microsoft, see [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span></span>

  - <span data-ttu-id="c7244-115">**不支援：遠端桌面會話。**    在此案例中，每一位使用者都登入無法自訂的一般虛擬桌面會話。</span><span class="sxs-lookup"><span data-stu-id="c7244-115">**Not supported: Remote Desktop Sessions.**   In this scenario, each user logs on to a generic virtual desktop session that cannot be customized.</span></span> <span data-ttu-id="c7244-116">範例實施包括 Microsoft 遠端桌面會話 (RDSH) 和 Citrix XenApp 與 Citrix 接收器結合使用。</span><span class="sxs-lookup"><span data-stu-id="c7244-116">Example implementations include Microsoft Remote Desktop Sessions (RDSH) and Citrix XenApp combined with Citrix Receiver.</span></span>

<span data-ttu-id="c7244-117">Lync VDI 外掛程式不支援其他虛擬化技術（例如 application virtualization），允許使用應用程式，而不需要在本機安裝完整的應用程式。</span><span class="sxs-lookup"><span data-stu-id="c7244-117">The Lync VDI plug-in does not support other virtualization technologies, such as application virtualization, which allows the use of an application without requiring installation of the full application locally.</span></span> <span data-ttu-id="c7244-118">範例實現包括 Citrix XenApp 和 Microsoft Application Virtualization (App-V) 。</span><span class="sxs-lookup"><span data-stu-id="c7244-118">Example implementations include Citrix XenApp and Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="c7244-119">應用程式流式處理、應用程式遠端處理和混合虛擬化模式 (例如，不支援完整桌面遠端) 中的應用程式遠端處理。</span><span class="sxs-lookup"><span data-stu-id="c7244-119">Application streaming, application remoting, and mixed virtualization modes (for example, application remoting in full desktop remoting) are not supported.</span></span>

<span data-ttu-id="c7244-120">為了允許擴充，Lync VDI 外掛程式設計為使用獨立于平臺的 APIs，稱為動態虛擬通道 (Dvc) 。</span><span class="sxs-lookup"><span data-stu-id="c7244-120">To allow extensibility, the Lync VDI plug-in was designed to use platform-independent APIs called Dynamic Virtual Channels (DVCs).</span></span> <span data-ttu-id="c7244-121">如果是 Lync 未明確支援的案例，請參閱 VDI 解決方案提供者的支援聲明。</span><span class="sxs-lookup"><span data-stu-id="c7244-121">For scenarios that are not explicitly supported by Lync, refer to support statements from the VDI solution provider.</span></span>

</div>

<div>

## <a name="known-feature-limitations"></a><span data-ttu-id="c7244-122">已知的功能限制</span><span class="sxs-lookup"><span data-stu-id="c7244-122">Known Feature Limitations</span></span>

<span data-ttu-id="c7244-123">當您在 VDI 環境中使用 Lync 2013 時，已知的限制如下：</span><span class="sxs-lookup"><span data-stu-id="c7244-123">The following are known limitations when you use Lync 2013 in a VDI environment:</span></span>

  - <span data-ttu-id="c7244-124">「呼叫委派」和「回應群組代理程式」匿名功能的支援有限。</span><span class="sxs-lookup"><span data-stu-id="c7244-124">There is limited support for Call Delegation and Response Group Agent Anonymization features.</span></span>

  - <span data-ttu-id="c7244-125">不支援以下功能：</span><span class="sxs-lookup"><span data-stu-id="c7244-125">There is no support for the following features:</span></span>
    
      - <span data-ttu-id="c7244-126">整合式音訊裝置及視訊裝置調整頁面。</span><span class="sxs-lookup"><span data-stu-id="c7244-126">Integrated Audio Device and Video Device tuning pages.</span></span>
    
      - <span data-ttu-id="c7244-127">多 view 影片。</span><span class="sxs-lookup"><span data-stu-id="c7244-127">Multiple-view video.</span></span>
    
      - <span data-ttu-id="c7244-128">錄製交談。</span><span class="sxs-lookup"><span data-stu-id="c7244-128">Recording of conversations.</span></span>
    
      - <span data-ttu-id="c7244-129">遠端桌面服務 (RDS) 。</span><span class="sxs-lookup"><span data-stu-id="c7244-129">Remote Desktop Services (RDS).</span></span>
    
      - <span data-ttu-id="c7244-130">以匿名方式加入會議 (也就是說，加入由未與您) 組織建立同盟之組織所主控的 Lync 會議。</span><span class="sxs-lookup"><span data-stu-id="c7244-130">Joining meetings anonymously (that is, joining Lync meetings hosted by an organization that does not federate with your organization).</span></span>
    
      - <span data-ttu-id="c7244-131">使用 Lync VDI 外掛程式和 Lync Phone Edition 裝置。</span><span class="sxs-lookup"><span data-stu-id="c7244-131">Using the Lync VDI plug-in along with a Lync Phone Edition device.</span></span>
    
      - <span data-ttu-id="c7244-132">在網路中斷連線的情況下延續通話。</span><span class="sxs-lookup"><span data-stu-id="c7244-132">Call continuity in case of a network outage.</span></span>
    
      - <span data-ttu-id="c7244-133">自訂鈴聲和暫止的音樂功能。</span><span class="sxs-lookup"><span data-stu-id="c7244-133">Customized ringtones and music-on-hold features.</span></span>

  - <span data-ttu-id="c7244-134">在 Microsoft 365 或 Office 365 環境中不支援 Lync VDI 外掛程式。</span><span class="sxs-lookup"><span data-stu-id="c7244-134">The Lync VDI plug-in is not supported in a Microsoft 365 or Office 365 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

