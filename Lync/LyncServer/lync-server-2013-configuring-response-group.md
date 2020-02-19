---
title: Lync Server 2013： 若要設定回應群組
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
ms.openlocfilehash: 60c224e83bc3d86dca647258540aee2551656d05
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-response-group-in-lync-server-2013"></a><span data-ttu-id="bdb3f-102">在 Lync Server 2013 中設定回應群組</span><span class="sxs-lookup"><span data-stu-id="bdb3f-102">Configuring Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdb3f-103">_**主題上次修改日期：** 2012年-10-30_</span><span class="sxs-lookup"><span data-stu-id="bdb3f-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="bdb3f-104">回應群組是人員的路由和佇列來電給群組，稱為 「*代理程式*，例如服務台或客戶服務人員 Enterprise Voice 功能。</span><span class="sxs-lookup"><span data-stu-id="bdb3f-104">Response Group is an Enterprise Voice feature that routes and queues incoming calls to groups of people, called *agents*, such as a help desk or a customer service desk.</span></span>

<span data-ttu-id="bdb3f-105">「回應群組」所需的元件，會在您部署企業語音時自動安裝於前端伺服器或 Standard Edition Server 上並啟用。</span><span class="sxs-lookup"><span data-stu-id="bdb3f-105">The components that Response Group requires are installed and enabled automatically on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="bdb3f-106">若要讓使用者能夠使用「回應群組」，您必須依序設定專員群組、佇列和工作流程。</span><span class="sxs-lookup"><span data-stu-id="bdb3f-106">To make Response Group available to users, you must configure agent groups, then queues, and then workflows.</span></span> <span data-ttu-id="bdb3f-107">此外，回應群組管理員可委派給現有的工作流程至回應群組管理員，可以再修改及重新設定工作流程和其相關聯的代理群組和佇列的組態。</span><span class="sxs-lookup"><span data-stu-id="bdb3f-107">Additionally, a Response Group Administrator can delegate configuration of an existing workflow to a Response Group Manager, who can then modify and reconfigure the workflow and its associated agent groups and queues.</span></span>

<span data-ttu-id="bdb3f-108">本節會引導您完成的 Lync Server 2013 回應群組組態。</span><span class="sxs-lookup"><span data-stu-id="bdb3f-108">This section guides you through the configuration of Lync Server 2013 Response Group.</span></span> <span data-ttu-id="bdb3f-109">假設您已經閱讀規劃章節與回應群組，並且已部署 Enterprise Edition 伺服器或 Standard Edition 伺服器與 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="bdb3f-109">It assumes that you have already read the planning sections related to Response Group and have deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="bdb3f-110">如需使用 Lync Server 管理命令介面，包括範例指令碼建立回應群組的詳細資訊，請參閱 「 建立您第一個回應群組使用 Lync Server 管理命令介面 」 在<A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A>。</span><span class="sxs-lookup"><span data-stu-id="bdb3f-110">For details about creating a Response Group by using Lync Server Management Shell, including a sample script, see "Creating Your First Response Group Using Lync Server Management Shell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bdb3f-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="bdb3f-111">In This Section</span></span>

  - [<span data-ttu-id="bdb3f-112">回應群組設定權限和 Lync Server 2013 中的必要條件</span><span class="sxs-lookup"><span data-stu-id="bdb3f-112">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [<span data-ttu-id="bdb3f-113">Lync Server 2013 中的回應群組部署程序</span><span class="sxs-lookup"><span data-stu-id="bdb3f-113">Deployment process for Response Group in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-response-group.md)

  - [<span data-ttu-id="bdb3f-114">Lync Server 2013 中的工作流程建立案例概觀</span><span class="sxs-lookup"><span data-stu-id="bdb3f-114">Overview of workflow creation scenarios in Lync Server 2013</span></span>](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [<span data-ttu-id="bdb3f-115">建立回應群組代理群組 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdb3f-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="bdb3f-116">Lync Server 2013 中建立回應群組佇列</span><span class="sxs-lookup"><span data-stu-id="bdb3f-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

  - [<span data-ttu-id="bdb3f-117">（選用）Lync Server 2013 中的定義回應群組營業時間</span><span class="sxs-lookup"><span data-stu-id="bdb3f-117">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)

  - [<span data-ttu-id="bdb3f-118">（選用）Lync Server 2013 中的定義回應群組假日集</span><span class="sxs-lookup"><span data-stu-id="bdb3f-118">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [<span data-ttu-id="bdb3f-119">Lync Server 2013 中建立回應群組工作流程</span><span class="sxs-lookup"><span data-stu-id="bdb3f-119">Create Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-create-response-group-workflows.md)

  - [<span data-ttu-id="bdb3f-120">（選用）Lync Server 2013 中驗證回應群組部署</span><span class="sxs-lookup"><span data-stu-id="bdb3f-120">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bdb3f-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bdb3f-121">See Also</span></span>


[<span data-ttu-id="bdb3f-122">規劃 Lync Server 2013 中的通話管理功能</span><span class="sxs-lookup"><span data-stu-id="bdb3f-122">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

