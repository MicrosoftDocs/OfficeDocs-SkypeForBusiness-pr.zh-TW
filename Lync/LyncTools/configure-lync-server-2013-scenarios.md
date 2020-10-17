---
title: 設定 Lync Server 2013 案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945596(v=OCS.15)
ms:contentKeyID: 51541420
ms.date: 12/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d108cc3a2c49c40eb04c9039c83689fb8c5abf4c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499940"
---
# <a name="configure-lync-server-2013-scenarios"></a><span data-ttu-id="1fa03-102">設定 Lync Server 2013 案例</span><span class="sxs-lookup"><span data-stu-id="1fa03-102">Configure Lync Server 2013 Scenarios</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fa03-103">_**主題上次修改日期：** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="1fa03-103">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="1fa03-104">若要執行 Lync Server 2013 壓力和效能工具 (LyncPerfTool) ，必須先針對將要執行的案例，設定 Lync Server 2013 拓撲。</span><span class="sxs-lookup"><span data-stu-id="1fa03-104">To run the Lync Server 2013 Stress and Performance Tool (LyncPerfTool), the Lync Server 2013 topology must first be configured for the scenarios that will be executed.</span></span> <span data-ttu-id="1fa03-105">如果未設定 Lync Server 2013 或設定不正確，則在大多數情況下負載模擬都會失敗。</span><span class="sxs-lookup"><span data-stu-id="1fa03-105">If Lync Server 2013 is not configured or is configured incorrectly, load simulation will fail in most cases.</span></span> <span data-ttu-id="1fa03-106">透過 Lync Server 2013 壓力和效能工具，我們提供了一些範例 Lync Server 管理命令介面腳本和基本資源檔案，可做為設定 Lync Server 2013 的起始點。</span><span class="sxs-lookup"><span data-stu-id="1fa03-106">With the Lync Server 2013 Stress and Performance Tool, we have provided example Lync Server Management Shell scripts and basic resource files that can be used as a starting point for configuring Lync Server 2013.</span></span> <span data-ttu-id="1fa03-107">本主題說明所提供的 Windows PowerShell 範例。</span><span class="sxs-lookup"><span data-stu-id="1fa03-107">This topic describes the Windows PowerShell examples provided.</span></span> <span data-ttu-id="1fa03-108">請注意，這不是本主題的目標，說明一般會如何設定 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="1fa03-108">Note that it is not the goal of this topic to describe how to configure Lync Server 2013 in general.</span></span> <span data-ttu-id="1fa03-109">如需在 Lync Server 2013 中使用 Windows PowerShell 的詳細資訊，請參閱 Lync Server 管理命令介面檔，網址為 <https://technet.microsoft.com/library/gg398474.aspx> 。</span><span class="sxs-lookup"><span data-stu-id="1fa03-109">For details about working with Windows PowerShell in Lync Server 2013, see the Lync Server Management Shell documentation at <https://technet.microsoft.com/library/gg398474.aspx>.</span></span>

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a><span data-ttu-id="1fa03-110">關於執行 Lync Server 管理命令介面腳本</span><span class="sxs-lookup"><span data-stu-id="1fa03-110">About Running Lync Server Management Shell Scripts</span></span>

<span data-ttu-id="1fa03-111">我們已提供範例 Lync Server 管理命令介面腳本，可用於準備執行負載模擬。</span><span class="sxs-lookup"><span data-stu-id="1fa03-111">We have provided example Lync Server Management Shell scripts that may be used in preparation for running load simulation.</span></span> <span data-ttu-id="1fa03-112">因為這些腳本是用來進行負載模擬，所以它們很簡單且可供進行，因此可能不適合實際執行。</span><span class="sxs-lookup"><span data-stu-id="1fa03-112">Because the scripts are intended for load simulation, they are simple and permissive, and therefore may not be appropriate for production.</span></span> <span data-ttu-id="1fa03-113">所有腳本都是範例，必須先加以檢查，而且在某些情況下，修改後才能反映您的拓撲。</span><span class="sxs-lookup"><span data-stu-id="1fa03-113">All scripts are examples and must be reviewed, and, in some cases, modified to reflect your topology.</span></span> <span data-ttu-id="1fa03-114">在最低限度下，我們預計必須修改回應群組服務 (RGS) 案例，以指定指派給代理人群組的代理程式。</span><span class="sxs-lookup"><span data-stu-id="1fa03-114">At a minimum, we expect that the Response Group Service (RGS) scenario would need to be modified to specify the agents that are assigned to the agent groups.</span></span> <span data-ttu-id="1fa03-115">不過，您可以選擇不要模擬此負載。</span><span class="sxs-lookup"><span data-stu-id="1fa03-115">However, you have the option to not simulate this load.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="1fa03-116">請小心檢查和瞭解所提供的範例。</span><span class="sxs-lookup"><span data-stu-id="1fa03-116">Take care in reviewing and understanding the examples provided.</span></span> <span data-ttu-id="1fa03-117">腳本會覆寫拓撲中的任何現有設定。</span><span class="sxs-lookup"><span data-stu-id="1fa03-117">Scripts will overwrite any existing settings in the topology.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1fa03-118">如需使用 Windows PowerShell 和 Lync Server 管理命令介面的詳細資訊，請參閱 Lync Server 2013 Windows PowerShell 博客，網址為 <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A> 。</span><span class="sxs-lookup"><span data-stu-id="1fa03-118">For details about using Windows PowerShell and the Lync Server Management Shell, see the Lync Server 2013 Windows PowerShell Blog at <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>.</span></span>



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a><span data-ttu-id="1fa03-119">應力和效能工具用戶端版本名字物件</span><span class="sxs-lookup"><span data-stu-id="1fa03-119">Stress and Performance Tool Client Version Monikers</span></span>

<span data-ttu-id="1fa03-120">如果您已變更預設值的設定，您可能需要設定用戶端版本檢查原則。</span><span class="sxs-lookup"><span data-stu-id="1fa03-120">You may need to configure the Client Version Check policy if you have changed the settings from the default values.</span></span> <span data-ttu-id="1fa03-121">如需詳細資訊，請參閱《設定支援的用戶端版本》 <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx> 。</span><span class="sxs-lookup"><span data-stu-id="1fa03-121">For details, see “Configuring supported client versions” at <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx>.</span></span> <span data-ttu-id="1fa03-122">Lync Server 2013 應力和效能工具預設會使用下列使用者代理程式版本與 Lync Server 2013 通訊：</span><span class="sxs-lookup"><span data-stu-id="1fa03-122">The Lync Server 2013 Stress and Performance Tool uses the following User Agent Versions by default when communicating with Lync Server 2013:</span></span>

  - <span data-ttu-id="1fa03-123">LSPT/15.0.0.0 (Lync Server 2013 壓力和效能工具) </span><span class="sxs-lookup"><span data-stu-id="1fa03-123">LSPT/15.0.0.0 (Lync Server 2013 Stress and Performance Tool)</span></span>

  - <span data-ttu-id="1fa03-124">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="1fa03-124">OCPHONE/.0.522</span></span>

<span data-ttu-id="1fa03-125">以下是 LyncPerfTool 中 (UCWA) 用戶端的行動性：</span><span class="sxs-lookup"><span data-stu-id="1fa03-125">These are for the Mobility (UCWA) client in LyncPerfTool:</span></span>

  - <span data-ttu-id="1fa03-126">Ucwa Perf 工具/Web 會議</span><span class="sxs-lookup"><span data-stu-id="1fa03-126">Ucwa Perf Tool/Web Conference</span></span>

  - <span data-ttu-id="1fa03-127">Ucwa Perf 工具/行動裝置</span><span class="sxs-lookup"><span data-stu-id="1fa03-127">Ucwa Perf Tool/Mobile</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

