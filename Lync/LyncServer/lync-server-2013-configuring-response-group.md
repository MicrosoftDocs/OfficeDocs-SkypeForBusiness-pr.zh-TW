---
title: Lync Server 2013：設定回應群組
description: Lync Server 2013：設定回應群組。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Response Group
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205249(v=OCS.15)
ms:contentKeyID: 48185359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92674bb971ec5216051d75d788dc58b9c7ca641c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547929"
---
# <a name="configuring-response-group-in-lync-server-2013"></a><span data-ttu-id="7d8cc-103">在 Lync Server 2013 中設定回應群組</span><span class="sxs-lookup"><span data-stu-id="7d8cc-103">Configuring Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d8cc-104">_**主題上次修改日期：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="7d8cc-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="7d8cc-105">回應群組是一種企業語音功能，可將來電路由及列隊給一組人 *（稱為「* 服務台」，例如「服務台」或「客戶服務台」）。</span><span class="sxs-lookup"><span data-stu-id="7d8cc-105">Response Group is an Enterprise Voice feature that routes and queues incoming calls to groups of people, called *agents*, such as a help desk or a customer service desk.</span></span>

<span data-ttu-id="7d8cc-106">「回應群組」所需的元件，會在您部署企業語音時自動安裝於前端伺服器或 Standard Edition Server 上並啟用。</span><span class="sxs-lookup"><span data-stu-id="7d8cc-106">The components that Response Group requires are installed and enabled automatically on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="7d8cc-107">若要讓使用者能夠使用「回應群組」，您必須依序設定專員群組、佇列和工作流程。</span><span class="sxs-lookup"><span data-stu-id="7d8cc-107">To make Response Group available to users, you must configure agent groups, then queues, and then workflows.</span></span> <span data-ttu-id="7d8cc-108">此外，回應群組管理員可以將現有工作流程的設定委派給回應群組管理員，然後該管理員可以修改及重新設定工作流程及其相關聯的代理人群組和佇列。</span><span class="sxs-lookup"><span data-stu-id="7d8cc-108">Additionally, a Response Group Administrator can delegate configuration of an existing workflow to a Response Group Manager, who can then modify and reconfigure the workflow and its associated agent groups and queues.</span></span>

<span data-ttu-id="7d8cc-109">本節會引導您完成 Lync Server 2013 回應群組的設定。</span><span class="sxs-lookup"><span data-stu-id="7d8cc-109">This section guides you through the configuration of Lync Server 2013 Response Group.</span></span> <span data-ttu-id="7d8cc-110">它假設您已閱讀與回應群組相關的規劃區段，並已部署 Enterprise Edition server 或 Standard Edition server 與 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="7d8cc-110">It assumes that you have already read the planning sections related to Response Group and have deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="7d8cc-111">如需使用 Lync Server 管理命令介面（包括範例腳本）建立回應群組的詳細資訊，請參閱「使用 Lync Server 管理命令介面建立第一個回應群組」 <A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A> 。</span><span class="sxs-lookup"><span data-stu-id="7d8cc-111">For details about creating a Response Group by using Lync Server Management Shell, including a sample script, see "Creating Your First Response Group Using Lync Server Management Shell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7d8cc-112">本章節內容</span><span class="sxs-lookup"><span data-stu-id="7d8cc-112">In This Section</span></span>

  - [<span data-ttu-id="7d8cc-113">Lync Server 2013 的回應群組設定許可權和必要條件</span><span class="sxs-lookup"><span data-stu-id="7d8cc-113">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [<span data-ttu-id="7d8cc-114">Lync Server 2013 中回應群組的部署程式</span><span class="sxs-lookup"><span data-stu-id="7d8cc-114">Deployment process for Response Group in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-response-group.md)

  - [<span data-ttu-id="7d8cc-115">Lync Server 2013 中的工作流程建立案例概述</span><span class="sxs-lookup"><span data-stu-id="7d8cc-115">Overview of workflow creation scenarios in Lync Server 2013</span></span>](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [<span data-ttu-id="7d8cc-116">建立回應群組代理群組 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d8cc-116">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="7d8cc-117">在 Lync Server 2013 中建立回應群組佇列</span><span class="sxs-lookup"><span data-stu-id="7d8cc-117">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

  - [<span data-ttu-id="7d8cc-118"> (選用) 在 Lync Server 2013 中定義回應群組上班時間</span><span class="sxs-lookup"><span data-stu-id="7d8cc-118">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)

  - [<span data-ttu-id="7d8cc-119"> (選用) 在 Lync Server 2013 中定義回應群組假日集</span><span class="sxs-lookup"><span data-stu-id="7d8cc-119">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [<span data-ttu-id="7d8cc-120">在 Lync Server 2013 中建立回應群組工作流程</span><span class="sxs-lookup"><span data-stu-id="7d8cc-120">Create Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-create-response-group-workflows.md)

  - [<span data-ttu-id="7d8cc-121"> 在 Lync Server 2013 中 (選用) 驗證回應群組部署</span><span class="sxs-lookup"><span data-stu-id="7d8cc-121">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7d8cc-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7d8cc-122">See Also</span></span>


[<span data-ttu-id="7d8cc-123">在 Lync Server 2013 中規劃通話管理功能</span><span class="sxs-lookup"><span data-stu-id="7d8cc-123">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

