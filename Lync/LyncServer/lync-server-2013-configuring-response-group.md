---
title: Lync Server 2013：設定回應群組
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Response Group
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205249(v=OCS.15)
ms:contentKeyID: 48185359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4d12d1ee21cfa5e480dea52a0de9f89b250715c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-response-group-in-lync-server-2013"></a><span data-ttu-id="e507b-102">在 Lync Server 2013 中設定回應群組</span><span class="sxs-lookup"><span data-stu-id="e507b-102">Configuring Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e507b-103">_**主題上次修改日期：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="e507b-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="e507b-104">[回應] 群組是一個企業語音功能，可將來電路由並列隊給一組人員（例如服務台或客戶*服務台）。*</span><span class="sxs-lookup"><span data-stu-id="e507b-104">Response Group is an Enterprise Voice feature that routes and queues incoming calls to groups of people, called *agents*, such as a help desk or a customer service desk.</span></span>

<span data-ttu-id="e507b-105">當您部署企業語音時，會在前端伺服器或標準版伺服器上自動安裝及啟用回應群組所需的元件。</span><span class="sxs-lookup"><span data-stu-id="e507b-105">The components that Response Group requires are installed and enabled automatically on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="e507b-106">若要讓使用者使用 [回應群組]，您必須先設定 [代理群組]、[佇列]，然後再設定 [工作流程]。</span><span class="sxs-lookup"><span data-stu-id="e507b-106">To make Response Group available to users, you must configure agent groups, then queues, and then workflows.</span></span> <span data-ttu-id="e507b-107">此外，回應群組管理員可以將現有工作流程的設定委派給回應群組管理員，然後可以修改及重新設定工作流程及其關聯的代理群組和佇列。</span><span class="sxs-lookup"><span data-stu-id="e507b-107">Additionally, a Response Group Administrator can delegate configuration of an existing workflow to a Response Group Manager, who can then modify and reconfigure the workflow and its associated agent groups and queues.</span></span>

<span data-ttu-id="e507b-108">本節將引導您完成 Lync Server 2013 回應群組的設定。</span><span class="sxs-lookup"><span data-stu-id="e507b-108">This section guides you through the configuration of Lync Server 2013 Response Group.</span></span> <span data-ttu-id="e507b-109">它假設您已閱讀與回應群組相關的規劃區段，並已部署企業版伺服器或使用企業語音的標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="e507b-109">It assumes that you have already read the planning sections related to Response Group and have deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="e507b-110">如需使用 Lync Server 管理命令介面（包括範例腳本）建立回應群組的詳細資料，請參閱使用 Lync Server 管理命令介面的「建立您的<A href="http://go.microsoft.com/fwlink/p/?linkid=204108">http://go.microsoft.com/fwlink/p/?linkId=204108</A>第一個回應群組」。</span><span class="sxs-lookup"><span data-stu-id="e507b-110">For details about creating a Response Group by using Lync Server Management Shell, including a sample script, see "Creating Your First Response Group Using Lync Server Management Shell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=204108">http://go.microsoft.com/fwlink/p/?linkId=204108</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e507b-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="e507b-111">In This Section</span></span>

  - [<span data-ttu-id="e507b-112">Lync Server 2013 中的回應群組設定權限和先決條件</span><span class="sxs-lookup"><span data-stu-id="e507b-112">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [<span data-ttu-id="e507b-113">Lync Server 2013 中的回應群組部署程式</span><span class="sxs-lookup"><span data-stu-id="e507b-113">Deployment process for Response Group in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-response-group.md)

  - [<span data-ttu-id="e507b-114">在 Lync Server 2013 中建立工作流程的案例概觀</span><span class="sxs-lookup"><span data-stu-id="e507b-114">Overview of workflow creation scenarios in Lync Server 2013</span></span>](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [<span data-ttu-id="e507b-115">在 Lync Server 2013 中建立回應群組代理群組</span><span class="sxs-lookup"><span data-stu-id="e507b-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="e507b-116">在 Lync Server 2013 中建立回應群組佇列</span><span class="sxs-lookup"><span data-stu-id="e507b-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

  - [<span data-ttu-id="e507b-117">可選在 Lync Server 2013 中定義回應群組的上班時間</span><span class="sxs-lookup"><span data-stu-id="e507b-117">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)

  - [<span data-ttu-id="e507b-118">可選在 Lync Server 2013 中定義回應群組假日集</span><span class="sxs-lookup"><span data-stu-id="e507b-118">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [<span data-ttu-id="e507b-119">在 Lync Server 2013 中建立回應群組工作流程</span><span class="sxs-lookup"><span data-stu-id="e507b-119">Create Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-create-response-group-workflows.md)

  - [<span data-ttu-id="e507b-120">可選在 Lync Server 2013 中驗證回應群組部署</span><span class="sxs-lookup"><span data-stu-id="e507b-120">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e507b-121">請參閱</span><span class="sxs-lookup"><span data-stu-id="e507b-121">See Also</span></span>


[<span data-ttu-id="e507b-122">規劃 Lync Server 2013 中的通話管理功能</span><span class="sxs-lookup"><span data-stu-id="e507b-122">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

