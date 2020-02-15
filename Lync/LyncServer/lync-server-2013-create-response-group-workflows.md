---
title: Lync Server 2013： 建立回應群組工作流程
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
ms.openlocfilehash: 3b93b63ffbb551c7e5d9d6998a5f25f86eb6fb0b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-response-group-workflows-in-lync-server-2013"></a><span data-ttu-id="328c5-102">Lync Server 2013 中建立回應群組工作流程</span><span class="sxs-lookup"><span data-stu-id="328c5-102">Create Response Group workflows in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="328c5-103">_**主題上次修改日期：** 2012年-09-12_</span><span class="sxs-lookup"><span data-stu-id="328c5-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="328c5-p101">工作流程會定義從電話鈴聲開始響起到有人接聽該通電話這段時間的呼叫行為。工作流程指定了用於保留通話的佇列，並指定用於群組搜尋的路由方法，或讓互動回應群組使用的問題和回答。工作流程也定義歡迎訊息、等候音樂、上班時間和假日之類的設定值。</span><span class="sxs-lookup"><span data-stu-id="328c5-p101">A workflow defines the behavior of a call from the time that the phone rings to the time that someone answers the call. The workflow specifies the queue to use for holding the call, and specifies the routing method to use for hunt groups or the questions and answers to use for interactive response groups. A workflow also defines settings such as a welcome message, music on hold, business hours, and holidays.</span></span>

<span data-ttu-id="328c5-107">您可以用於回應群組組態工具建立工作流程。</span><span class="sxs-lookup"><span data-stu-id="328c5-107">You use the Response Group Configuration Tool to create workflows.</span></span> <span data-ttu-id="328c5-108">您可以從 Lync Server 控制台的 [回應群組] 頁面存取回應群組組態工具。</span><span class="sxs-lookup"><span data-stu-id="328c5-108">You can access the Response Group Configuration Tool from the Response Group page of Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="328c5-109">您必須先建立代理群組和佇列，再建立使用這些項目的工作流程。</span><span class="sxs-lookup"><span data-stu-id="328c5-109">You must create agent groups and queues before you create a workflow that uses them.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="328c5-110">本章節內容</span><span class="sxs-lookup"><span data-stu-id="328c5-110">In This Section</span></span>

  - [<span data-ttu-id="328c5-111">建立或修改群組搜尋工作流程在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="328c5-111">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)

  - [<span data-ttu-id="328c5-112">Lync Server 2013 中設計互動式語音回應通話流程</span><span class="sxs-lookup"><span data-stu-id="328c5-112">Design interactive voice response call flows in Lync Server 2013</span></span>](lync-server-2013-design-interactive-voice-response-call-flows.md)

  - [<span data-ttu-id="328c5-113">建立或修改互動工作流程在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="328c5-113">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="328c5-114">相關各節</span><span class="sxs-lookup"><span data-stu-id="328c5-114">Related Sections</span></span>

  - [<span data-ttu-id="328c5-115">建立回應群組代理群組 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="328c5-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="328c5-116">Lync Server 2013 中建立回應群組佇列</span><span class="sxs-lookup"><span data-stu-id="328c5-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

