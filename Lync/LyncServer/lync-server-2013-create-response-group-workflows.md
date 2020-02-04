---
title: Lync Server 2013：建立回應群組工作流程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group workflows
ms:assetid: 41272258-728d-42bd-b4d4-2a499734c720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425918(v=OCS.15)
ms:contentKeyID: 48183954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9aa76d218564e04048a07db7592ffc5ea4046a71
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-response-group-workflows-in-lync-server-2013"></a><span data-ttu-id="bf4af-102">在 Lync Server 2013 中建立回應群組工作流程</span><span class="sxs-lookup"><span data-stu-id="bf4af-102">Create Response Group workflows in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf4af-103">_**主題上次修改日期：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="bf4af-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="bf4af-104">工作流程會定義撥打電話到某人接聽來電之時間的通話行為。</span><span class="sxs-lookup"><span data-stu-id="bf4af-104">A workflow defines the behavior of a call from the time that the phone rings to the time that someone answers the call.</span></span> <span data-ttu-id="bf4af-105">工作流程會指定要用來進行通話的佇列，並指定用來進行查尋群組的傳送方法，或是用於互動式回應群組的問題與解答。</span><span class="sxs-lookup"><span data-stu-id="bf4af-105">The workflow specifies the queue to use for holding the call, and specifies the routing method to use for hunt groups or the questions and answers to use for interactive response groups.</span></span> <span data-ttu-id="bf4af-106">工作流程也會定義設定，例如 [歡迎] 訊息、[等候音樂]、[上班時間] 和 [假日]。</span><span class="sxs-lookup"><span data-stu-id="bf4af-106">A workflow also defines settings such as a welcome message, music on hold, business hours, and holidays.</span></span>

<span data-ttu-id="bf4af-107">您可以使用 [回應群組設定] 工具來建立工作流程。</span><span class="sxs-lookup"><span data-stu-id="bf4af-107">You use the Response Group Configuration Tool to create workflows.</span></span> <span data-ttu-id="bf4af-108">您可以從 Lync Server [控制台] 的 [回應群組] 頁面存取 [回應群組設定] 工具。</span><span class="sxs-lookup"><span data-stu-id="bf4af-108">You can access the Response Group Configuration Tool from the Response Group page of Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bf4af-109">您必須先建立代理群組和佇列，才能建立使用它們的工作流程。</span><span class="sxs-lookup"><span data-stu-id="bf4af-109">You must create agent groups and queues before you create a workflow that uses them.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bf4af-110">本節內容</span><span class="sxs-lookup"><span data-stu-id="bf4af-110">In This Section</span></span>

  - [<span data-ttu-id="bf4af-111">在 Lync Server 2013 中建立或修改查尋群組工作流程</span><span class="sxs-lookup"><span data-stu-id="bf4af-111">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)

  - [<span data-ttu-id="bf4af-112">在 Lync Server 2013 中設計互動語音回應系統通話流程</span><span class="sxs-lookup"><span data-stu-id="bf4af-112">Design interactive voice response call flows in Lync Server 2013</span></span>](lync-server-2013-design-interactive-voice-response-call-flows.md)

  - [<span data-ttu-id="bf4af-113">在 Lync Server 2013 中建立或修改互動式工作流程</span><span class="sxs-lookup"><span data-stu-id="bf4af-113">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="bf4af-114">相關各節</span><span class="sxs-lookup"><span data-stu-id="bf4af-114">Related Sections</span></span>

  - [<span data-ttu-id="bf4af-115">在 Lync Server 2013 中建立回應群組代理群組</span><span class="sxs-lookup"><span data-stu-id="bf4af-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="bf4af-116">在 Lync Server 2013 中建立回應群組佇列</span><span class="sxs-lookup"><span data-stu-id="bf4af-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

