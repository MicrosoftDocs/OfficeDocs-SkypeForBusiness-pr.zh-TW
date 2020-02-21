---
title: Lync Server 2013： 支援虛擬化技術和已知的限制
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
ms.openlocfilehash: c81b56fd8d0922b011840aa2b3133ce05d32ad13
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a><span data-ttu-id="d6ea3-102">支援的虛擬化技術和 Lync Server 2013 中的已知的限制</span><span class="sxs-lookup"><span data-stu-id="d6ea3-102">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6ea3-103">_**主題上次修改日期：** 2017年-02-06_</span><span class="sxs-lookup"><span data-stu-id="d6ea3-103">_**Topic Last Modified:** 2017-02-06_</span></span>

<span data-ttu-id="d6ea3-104">Lync VDI 外掛程式可讓音訊和視訊通話支援的虛擬化技術。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-104">The Lync VDI plug-in allows audio and video calling for supported virtualization technologies.</span></span> <span data-ttu-id="d6ea3-105">此擴充[Microsoft Lync 2010 中的用戶端虛擬化](https://go.microsoft.com/fwlink/?linkid=330447)本白皮書中所述的 Microsoft Lync Server 2010 功能。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-105">This extends the functionality outlined for Microsoft Lync Server 2010 in the [Client Virtualization in Microsoft Lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) white paper.</span></span> <span data-ttu-id="d6ea3-106">符合標準電話法規、 規範支援 E911 是也包含在內。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-106">In compliance with standard telephone regulations, support for E911 is also included.</span></span> <span data-ttu-id="d6ea3-107">下列各節說明 Lync VDI 外掛程式已知的功能會受到限制所支援的虛擬化技術。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-107">The following sections describe the virtualization technologies that are supported by the Lync VDI plug-in and the known feature limitations.</span></span>

<div>

## <a name="support-for-virtualization-technologies"></a><span data-ttu-id="d6ea3-108">對虛擬化技術的支援</span><span class="sxs-lookup"><span data-stu-id="d6ea3-108">Support for Virtualization Technologies</span></span>

<span data-ttu-id="d6ea3-109">Lync VDI 外掛程式可支援完整桌面 remoting 在個人虛擬桌面案例中，但不是在遠端桌面工作階段的案例。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-109">The Lync VDI plug-in supports full desktop remoting in the personal virtual desktop scenario, but not in the remote desktop session scenario.</span></span> <span data-ttu-id="d6ea3-110">這些案例說明如下：</span><span class="sxs-lookup"><span data-stu-id="d6ea3-110">These scenarios can be described as follows:</span></span>

  - <span data-ttu-id="d6ea3-111">**支援： 個人化的虛擬桌面或虛擬桌面基礎結構 (VDI)。**   在此案例中，每位使用者登入可自訂的虛擬桌面，而且能夠儲存在桌面上會保存跨工作階段的檔案。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-111">**Supported: Personalized Virtual Desktops or Virtual Desktop Infrastructure (VDI).**   In this scenario, each user logs on to a customizable virtual desktop and is able to save files on the desktop that persist across sessions.</span></span> <span data-ttu-id="d6ea3-112">Microsoft 遠端桌面服務、 VMware 水平線檢視，以及 Citrix XenDesktop 是經過測試與 Lync 搭配使用的實作。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-112">Microsoft Remote Desktop Services, VMware Horizon View, and Citrix XenDesktop are implementations that have been tested for use with Lync.</span></span> <span data-ttu-id="d6ea3-113">供應商特有 VDI 環境和 microsoft 經過測試的用戶端硬體的相關資訊，請參閱[Microsoft lync 合格基礎結構](https://go.microsoft.com/fwlink/?linkid=313435)。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-113">For information about vendor-specific VDI environments and client hardware that have been tested by Microsoft, see [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span></span>

  - <span data-ttu-id="d6ea3-114">**不支援： 遠端桌面工作階段。**   在此案例中，每個使用者用來登入的一般虛擬桌面工作階段無法自訂。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-114">**Not supported: Remote Desktop Sessions.**   In this scenario, each user logs on to a generic virtual desktop session that cannot be customized.</span></span> <span data-ttu-id="d6ea3-115">範例實作包括 Microsoft 遠端桌面工作階段 (RDSH)，以及 Citrix XenApp 結合 Citrix 收件者。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-115">Example implementations include Microsoft Remote Desktop Sessions (RDSH) and Citrix XenApp combined with Citrix Receiver.</span></span>

<span data-ttu-id="d6ea3-116">Lync VDI 外掛程式不支援其他虛擬化技術，例如應用程式虛擬化，而不需要安裝完整的應用程式在本機上允許使用應用程式。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-116">The Lync VDI plug-in does not support other virtualization technologies, such as application virtualization, which allows the use of an application without requiring installation of the full application locally.</span></span> <span data-ttu-id="d6ea3-117">範例實作包含 Citrix XenApp 和 Microsoft Application Virtualization (APP-V)。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-117">Example implementations include Citrix XenApp and Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="d6ea3-118">不支援應用程式資料流、 應用程式遠端處理和混合式虛擬化模式 （例如，應用程式遠端處理的完整桌面的遠端處理）。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-118">Application streaming, application remoting, and mixed virtualization modes (for example, application remoting in full desktop remoting) are not supported.</span></span>

<span data-ttu-id="d6ea3-119">若要允許擴充性，Lync VDI 外掛程式的設計目的在於使用獨立平台的 Api 呼叫動態虛擬通道 (DVCs)。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-119">To allow extensibility, the Lync VDI plug-in was designed to use platform-independent APIs called Dynamic Virtual Channels (DVCs).</span></span> <span data-ttu-id="d6ea3-120">Lync 不明確支援的案例，請參閱支援從 VDI 解決方案提供者的陳述式。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-120">For scenarios that are not explicitly supported by Lync, refer to support statements from the VDI solution provider.</span></span>

</div>

<div>

## <a name="known-feature-limitations"></a><span data-ttu-id="d6ea3-121">已知的功能會受到限制</span><span class="sxs-lookup"><span data-stu-id="d6ea3-121">Known Feature Limitations</span></span>

<span data-ttu-id="d6ea3-122">下面是已知限制在 VDI 環境中使用 Lync 2013 時：</span><span class="sxs-lookup"><span data-stu-id="d6ea3-122">The following are known limitations when you use Lync 2013 in a VDI environment:</span></span>

  - <span data-ttu-id="d6ea3-123">沒有有限的支援通話委派與回應群組代理人匿名功能。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-123">There is limited support for Call Delegation and Response Group Agent Anonymization features.</span></span>

  - <span data-ttu-id="d6ea3-124">不支援以下功能：</span><span class="sxs-lookup"><span data-stu-id="d6ea3-124">There is no support for the following features:</span></span>
    
      - <span data-ttu-id="d6ea3-125">整合式音訊裝置及視訊裝置調整頁面。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-125">Integrated Audio Device and Video Device tuning pages.</span></span>
    
      - <span data-ttu-id="d6ea3-126">多重檢視視訊。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-126">Multiple-view video.</span></span>
    
      - <span data-ttu-id="d6ea3-127">錄製交談。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-127">Recording of conversations.</span></span>
    
      - <span data-ttu-id="d6ea3-128">遠端桌面服務 (RDS)。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-128">Remote Desktop Services (RDS).</span></span>
    
      - <span data-ttu-id="d6ea3-129">加入會議匿名 （也就加入與您的組織不同盟的組織所主控的 Lync 會議）。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-129">Joining meetings anonymously (that is, joining Lync meetings hosted by an organization that does not federate with your organization).</span></span>
    
      - <span data-ttu-id="d6ea3-130">使用 Lync VDI 外掛程式以及 Lync Phone Edition 裝置。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-130">Using the Lync VDI plug-in along with a Lync Phone Edition device.</span></span>
    
      - <span data-ttu-id="d6ea3-131">在網路中斷連線的情況下延續通話。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-131">Call continuity in case of a network outage.</span></span>
    
      - <span data-ttu-id="d6ea3-132">自訂等候鈴聲及音樂上保留功能。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-132">Customized ringtones and music-on-hold features.</span></span>

  - <span data-ttu-id="d6ea3-133">在 Office 365 環境中不支援 Lync VDI 外掛程式。</span><span class="sxs-lookup"><span data-stu-id="d6ea3-133">The Lync VDI plug-in is not supported in an Office 365 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

