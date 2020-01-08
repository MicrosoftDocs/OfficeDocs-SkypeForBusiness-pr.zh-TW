---
title: 設定 Lync Server 2013 案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945596(v=OCS.15)
ms:contentKeyID: 51541420
ms.date: 12/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93ad7a3be8b69c956b1cca0f1d1554a5fa288f17
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-scenarios"></a><span data-ttu-id="97a99-102">設定 Lync Server 2013 案例</span><span class="sxs-lookup"><span data-stu-id="97a99-102">Configure Lync Server 2013 Scenarios</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97a99-103">_**主題上次修改日期：** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="97a99-103">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="97a99-104">若要執行 Lync Server 2013 應力和效能工具（LyncPerfTool），必須先針對要執行的案例設定 Lync Server 2013 拓撲。</span><span class="sxs-lookup"><span data-stu-id="97a99-104">To run the Lync Server 2013 Stress and Performance Tool (LyncPerfTool), the Lync Server 2013 topology must first be configured for the scenarios that will be executed.</span></span> <span data-ttu-id="97a99-105">如果未設定 Lync Server 2013 或未正確設定，則在大多數情況下，負載模擬將會失敗。</span><span class="sxs-lookup"><span data-stu-id="97a99-105">If Lync Server 2013 is not configured or is configured incorrectly, load simulation will fail in most cases.</span></span> <span data-ttu-id="97a99-106">使用 Lync Server 2013 應力和效能工具，我們提供了範例 Lync Server 管理命令介面腳本和基本資源檔案，可做為開始進行 Lync Server 2013 的起點。</span><span class="sxs-lookup"><span data-stu-id="97a99-106">With the Lync Server 2013 Stress and Performance Tool, we have provided example Lync Server Management Shell scripts and basic resource files that can be used as a starting point for configuring Lync Server 2013.</span></span> <span data-ttu-id="97a99-107">本主題描述提供的 Windows PowerShell 範例。</span><span class="sxs-lookup"><span data-stu-id="97a99-107">This topic describes the Windows PowerShell examples provided.</span></span> <span data-ttu-id="97a99-108">請注意，這不是本主題的目標，說明如何在一般情況下設定 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="97a99-108">Note that it is not the goal of this topic to describe how to configure Lync Server 2013 in general.</span></span> <span data-ttu-id="97a99-109">如需在 Lync Server 2013 中使用 Windows PowerShell 的詳細資料，請參閱 Lync Server 管理命令<https://technet.microsoft.com/en-us/library/gg398474.aspx>介面檔，網址為。</span><span class="sxs-lookup"><span data-stu-id="97a99-109">For details about working with Windows PowerShell in Lync Server 2013, see the Lync Server Management Shell documentation at <https://technet.microsoft.com/en-us/library/gg398474.aspx>.</span></span>

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a><span data-ttu-id="97a99-110">關於執行 Lync Server 管理命令介面腳本</span><span class="sxs-lookup"><span data-stu-id="97a99-110">About Running Lync Server Management Shell Scripts</span></span>

<span data-ttu-id="97a99-111">我們已提供可用於準備執行負載模擬的 Lync Server 管理命令介面腳本範例。</span><span class="sxs-lookup"><span data-stu-id="97a99-111">We have provided example Lync Server Management Shell scripts that may be used in preparation for running load simulation.</span></span> <span data-ttu-id="97a99-112">因為腳本是用來進行負載模擬，所以它們很簡單且便於使用，因此可能不適合生產。</span><span class="sxs-lookup"><span data-stu-id="97a99-112">Because the scripts are intended for load simulation, they are simple and permissive, and therefore may not be appropriate for production.</span></span> <span data-ttu-id="97a99-113">所有腳本都是範例，而且在某些情況下，您必須經過修改，才能反映您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="97a99-113">All scripts are examples and must be reviewed, and, in some cases, modified to reflect your topology.</span></span> <span data-ttu-id="97a99-114">至少，我們預期需要修改回應群組服務（RGS）案例，以指定指派給代理群組的代理程式。</span><span class="sxs-lookup"><span data-stu-id="97a99-114">At a minimum, we expect that the Response Group Service (RGS) scenario would need to be modified to specify the agents that are assigned to the agent groups.</span></span> <span data-ttu-id="97a99-115">不過，您可以選擇不要模擬這項載入。</span><span class="sxs-lookup"><span data-stu-id="97a99-115">However, you have the option to not simulate this load.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="97a99-116">在審查及瞭解所提供的範例時請小心。</span><span class="sxs-lookup"><span data-stu-id="97a99-116">Take care in reviewing and understanding the examples provided.</span></span> <span data-ttu-id="97a99-117">腳本會覆寫拓撲中任何現有的設定。</span><span class="sxs-lookup"><span data-stu-id="97a99-117">Scripts will overwrite any existing settings in the topology.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="97a99-118">如需使用 Windows PowerShell 和 Lync Server 管理命令介面的詳細資訊，請參閱 Lync Server 2013 的 Windows <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>PowerShell 博客。</span><span class="sxs-lookup"><span data-stu-id="97a99-118">For details about using Windows PowerShell and the Lync Server Management Shell, see the Lync Server 2013 Windows PowerShell Blog at <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>.</span></span>



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a><span data-ttu-id="97a99-119">壓力與效能工具用戶端版本名字物件</span><span class="sxs-lookup"><span data-stu-id="97a99-119">Stress and Performance Tool Client Version Monikers</span></span>

<span data-ttu-id="97a99-120">如果您已變更預設值的設定，您可能需要設定用戶端版本檢查原則。</span><span class="sxs-lookup"><span data-stu-id="97a99-120">You may need to configure the Client Version Check policy if you have changed the settings from the default values.</span></span> <span data-ttu-id="97a99-121">如需詳細資訊，請參閱「配置支援的<https://technet.microsoft.com/en-us/library/gg412832(v=ocs.15).aspx>用戶端版本」。</span><span class="sxs-lookup"><span data-stu-id="97a99-121">For details, see “Configuring supported client versions” at <https://technet.microsoft.com/en-us/library/gg412832(v=ocs.15).aspx>.</span></span> <span data-ttu-id="97a99-122">Lync Server 2013 的應力和效能工具預設會在與 Lync Server 2013 通訊時使用下列使用者代理版本：</span><span class="sxs-lookup"><span data-stu-id="97a99-122">The Lync Server 2013 Stress and Performance Tool uses the following User Agent Versions by default when communicating with Lync Server 2013:</span></span>

  - <span data-ttu-id="97a99-123">LSPT/15.0.0.0 （Lync Server 2013 應力和效能工具）</span><span class="sxs-lookup"><span data-stu-id="97a99-123">LSPT/15.0.0.0 (Lync Server 2013 Stress and Performance Tool)</span></span>

  - <span data-ttu-id="97a99-124">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="97a99-124">OCPHONE/.0.522</span></span>

<span data-ttu-id="97a99-125">這些適用于 LyncPerfTool 中的行動（UCWA）用戶端：</span><span class="sxs-lookup"><span data-stu-id="97a99-125">These are for the Mobility (UCWA) client in LyncPerfTool:</span></span>

  - <span data-ttu-id="97a99-126">Ucwa Perf 工具/Web 會議</span><span class="sxs-lookup"><span data-stu-id="97a99-126">Ucwa Perf Tool/Web Conference</span></span>

  - <span data-ttu-id="97a99-127">Ucwa Perf 工具/行動裝置</span><span class="sxs-lookup"><span data-stu-id="97a99-127">Ucwa Perf Tool/Mobile</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

