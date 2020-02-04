---
title: Lync Server 2013：回應群組應用程式的概覽
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b01181296a42f786a4739b5ec59d775212baaf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a><span data-ttu-id="af518-102">Lync Server 2013 中的回應群組應用程式概覽</span><span class="sxs-lookup"><span data-stu-id="af518-102">Overview of the Response Group application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af518-103">_**主題上次修改日期：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="af518-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="af518-104">當來電者呼叫回應群組時，通話會根據查尋群組或來電者對互動式語音回應（IVR）問題的答案來傳送給代理程式。</span><span class="sxs-lookup"><span data-stu-id="af518-104">When a caller calls a response group, the call is routed to an agent based on a hunt group or the caller's answers to interactive voice response (IVR) questions.</span></span> <span data-ttu-id="af518-105">回應群組應用程式會使用標準的回應群組路由方法，將呼叫路由至下一個可用的代理程式。</span><span class="sxs-lookup"><span data-stu-id="af518-105">The Response Group application uses standard response group routing methods to route the call to the next available agent.</span></span> <span data-ttu-id="af518-106">呼叫路由方法包括串列、最長閒置、並行、迴圈，以及助理路由（也就是，所有的代理程式都是在每次撥入通話時呼叫，不論其目前的狀態為何）。</span><span class="sxs-lookup"><span data-stu-id="af518-106">Call routing methods include serial, longest-idle, parallel, round robin, and Attendant routing (that is, all agents are called at the same time for every incoming call, regardless of their current presence).</span></span> <span data-ttu-id="af518-107">如果沒有可用的代理，通話會一直保留在佇列中，直到有可用的代理程式。</span><span class="sxs-lookup"><span data-stu-id="af518-107">If no agents are available, the call is held in a queue until an agent is available.</span></span> <span data-ttu-id="af518-108">在佇列中，來電者會聽到音樂，直到可用的代理程式接受通話。</span><span class="sxs-lookup"><span data-stu-id="af518-108">While in the queue, the caller hears music until an available agent accepts the call.</span></span> <span data-ttu-id="af518-109">如果佇列已滿，或通話在佇列中超時，來電者可能會聽到訊息，然後中斷連線或傳送到不同的目的地。</span><span class="sxs-lookup"><span data-stu-id="af518-109">If the queue is full, or if the call times out while in the queue, the caller might hear a message and then is either disconnected or transferred to a different destination.</span></span> <span data-ttu-id="af518-110">當代理程式接受來電時，呼叫者可能也可能無法看到代理人的身分識別，視系統管理員設定回應群組的方式而定。</span><span class="sxs-lookup"><span data-stu-id="af518-110">When an agent accepts the call, the caller might or might not be able to see the agent's identity, depending on how the administrator configures the response group.</span></span> <span data-ttu-id="af518-111">Agent 可以是正式的，這表示他們必須先登入群組，才能接受路由到群組的呼叫，或者是非正式的，這表示它們不會登入和登出群組以接受通話。</span><span class="sxs-lookup"><span data-stu-id="af518-111">Agents can either be formal, which means that they must sign in to the group before they can accept calls routed to the group, or informal, which means that they do not sign into and out of the group to accept calls.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="af518-112">只有內部部署使用者可以使用代理程式。</span><span class="sxs-lookup"><span data-stu-id="af518-112">Only on-premises users can be agents.</span></span> <span data-ttu-id="af518-113">如果代理程式是從內部部署移至線上，回應群組呼叫將不會路由至該代理程式。</span><span class="sxs-lookup"><span data-stu-id="af518-113">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="af518-114">回應群組應用程式使用名為 [相符] 的內部服務來排隊通話，並尋找可用的代理程式。</span><span class="sxs-lookup"><span data-stu-id="af518-114">The Response Group application uses an internal service, called Match Making, to queue calls and find available agents.</span></span> <span data-ttu-id="af518-115">每個執行回應群組應用程式的電腦都會執行相符的服務，但一次只能有一個相符的服務是作用中的每個 Lync Server pool; 其他是被動的。</span><span class="sxs-lookup"><span data-stu-id="af518-115">Each computer that runs the Response Group application runs the Match Making service, but only one Match Making service per Lync Server pool is active at a time--the others are passive.</span></span> <span data-ttu-id="af518-116">如果在未計畫的停機期間，使用中的 [相符] 使服務變為無法使用，其中一個被動的相符，就會變成作用中。</span><span class="sxs-lookup"><span data-stu-id="af518-116">If the active Match Making service becomes unavailable during an unplanned outage, one of the passive Match Making services becomes active.</span></span> <span data-ttu-id="af518-117">回應群組應用程式最能確保呼叫路由和佇列繼續不間斷地進行。</span><span class="sxs-lookup"><span data-stu-id="af518-117">The Response Group application does its best to make sure that call routing and queuing continues uninterrupted.</span></span> <span data-ttu-id="af518-118">不過，當相符的服務轉換發生時，任何在該時間傳輸的呼叫都會遺失。</span><span class="sxs-lookup"><span data-stu-id="af518-118">However, when a Match Making service transition occurs, any calls that are in transfer at the time are lost.</span></span> <span data-ttu-id="af518-119">例如，如果您的轉換是由於前端伺服器即將停機而引起，則目前由作用中的 Match 所處理的任何呼叫都會在該前端伺服器上執行的服務也會遺失。</span><span class="sxs-lookup"><span data-stu-id="af518-119">For example, if the transition is due to the Front End Server going down, any calls currently being handled by the active Match Making service on that Front End Server are also lost.</span></span>



</div>

<span data-ttu-id="af518-120">在 Lync Server 2013 中，有兩個管理角色可用來管理回應群組： [回應群組管理員] 和 [回應群組管理員]。</span><span class="sxs-lookup"><span data-stu-id="af518-120">In Lync Server 2013, two management roles are available for managing response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="af518-121">回應群組管理員可以管理任何回應群組的任何方面。</span><span class="sxs-lookup"><span data-stu-id="af518-121">Response Group Administrators can manage any aspect of any response group.</span></span> <span data-ttu-id="af518-122">回應群組管理員只能管理特定的部分，而且只能管理自己擁有的回應群組。</span><span class="sxs-lookup"><span data-stu-id="af518-122">Response Group Managers can manage only certain aspects, and only for the response groups that they own.</span></span> <span data-ttu-id="af518-123">新的管理員角色可協助降低管理成本，因為您可以將特定回應群組的有限職責委派給任何已啟用企業語音的使用者。</span><span class="sxs-lookup"><span data-stu-id="af518-123">The new Manager role can help reduce administration costs, because you can delegate limited responsibilities for specific response groups to any user who is enabled for Enterprise Voice.</span></span>

<span data-ttu-id="af518-124">為了適應新的管理員角色，Lync Server 2013 回應群組應用程式引入了託管或非託管的**工作流程類型**。</span><span class="sxs-lookup"><span data-stu-id="af518-124">To accommodate the new Manager role, Lync Server 2013 Response Group application introduces a **Workflow Type** of Managed or Unmanaged.</span></span> <span data-ttu-id="af518-125">下表說明受管理和未受管理的回應群組。</span><span class="sxs-lookup"><span data-stu-id="af518-125">The following table describes Managed and Unmanaged response groups.</span></span>

### <a name="managed-and-unmanaged-response-groups"></a><span data-ttu-id="af518-126">受管理和未受管理的回應群組</span><span class="sxs-lookup"><span data-stu-id="af518-126">Managed and Unmanaged Response Groups</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="af518-127">回應群組類型</span><span class="sxs-lookup"><span data-stu-id="af518-127">Response group type</span></span></th>
<th><span data-ttu-id="af518-128">說明</span><span class="sxs-lookup"><span data-stu-id="af518-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af518-129">管</span><span class="sxs-lookup"><span data-stu-id="af518-129">Unmanaged</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="af518-130">未受管理的回應群組沒有已指派的管理員。</span><span class="sxs-lookup"><span data-stu-id="af518-130">Unmanaged response groups have no assigned Managers.</span></span> <span data-ttu-id="af518-131">只有回應群組管理員可以設定這些回應群組。</span><span class="sxs-lookup"><span data-stu-id="af518-131">Only the Response Group Administrator can configure these response groups.</span></span></p></li>
<li><p><span data-ttu-id="af518-132">多個未受管理的回應群組可以共用 [佇列] 或 [代理] 群組。</span><span class="sxs-lookup"><span data-stu-id="af518-132">Multiple unmanaged response groups can share a queue or agent group.</span></span></p></li>
<li><p><span data-ttu-id="af518-133">當您將回應群組從先前的版本遷移至 Lync Server 2013 時，該類型會設定為 [未管理]。</span><span class="sxs-lookup"><span data-stu-id="af518-133">When you migrate response groups from a prior version to Lync Server 2013, the type is set to Unmanaged.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af518-134">被</span><span class="sxs-lookup"><span data-stu-id="af518-134">Managed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="af518-135">回應群組管理員可以設定受管理回應群組的任何方面。</span><span class="sxs-lookup"><span data-stu-id="af518-135">Response Group Administrators can configure any aspect of managed response groups.</span></span></p></li>
<li><p><span data-ttu-id="af518-136">回應群組管理員無法查看或修改未明確指派給他們的回應群組。</span><span class="sxs-lookup"><span data-stu-id="af518-136">Response Group Managers cannot view or modify response groups that are not explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="af518-137">回應群組管理員只能針對明確指派給他們的回應群組設定部分設定。</span><span class="sxs-lookup"><span data-stu-id="af518-137">Response Group Managers can configure only some settings for the response groups that are explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="af518-138">受管理的回應群組無法與任何其他回應群組、託管或未受管理的人共用任何佇列或代理群組。</span><span class="sxs-lookup"><span data-stu-id="af518-138">Managed response groups can't share any queues or agent groups with any other response group, managed or unmanaged.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="af518-139">下表說明回應群組管理員可以對指派給他們的回應群組執行哪些動作。</span><span class="sxs-lookup"><span data-stu-id="af518-139">The following table describes the actions that Response Group Managers can and cannot perform for the response groups assigned to them.</span></span>

### <a name="response-group-manager-capabilities"></a><span data-ttu-id="af518-140">回應群組管理員功能</span><span class="sxs-lookup"><span data-stu-id="af518-140">Response Group Manager Capabilities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="af518-141">可以設定：</span><span class="sxs-lookup"><span data-stu-id="af518-141">Can configure:</span></span></th>
<th><span data-ttu-id="af518-142">可以建立、刪除或設定：</span><span class="sxs-lookup"><span data-stu-id="af518-142">Can create, delete, or configure:</span></span></th>
<th><span data-ttu-id="af518-143">不</span><span class="sxs-lookup"><span data-stu-id="af518-143">Cannot:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="af518-144">代理程式</span><span class="sxs-lookup"><span data-stu-id="af518-144">Agents</span></span></p></li>
<li><p><span data-ttu-id="af518-145">歡迎訊息</span><span class="sxs-lookup"><span data-stu-id="af518-145">Welcome message</span></span></p></li>
<li><p><span data-ttu-id="af518-146">回應群組名稱</span><span class="sxs-lookup"><span data-stu-id="af518-146">Response Group name</span></span></p></li>
<li><p><span data-ttu-id="af518-147">說明</span><span class="sxs-lookup"><span data-stu-id="af518-147">Description</span></span></p></li>
<li><p><span data-ttu-id="af518-148">顯示數位</span><span class="sxs-lookup"><span data-stu-id="af518-148">Display number</span></span></p></li>
<li><p><span data-ttu-id="af518-149">商務時間</span><span class="sxs-lookup"><span data-stu-id="af518-149">Business hours</span></span></p></li>
<li><p><span data-ttu-id="af518-150">等候音樂</span><span class="sxs-lookup"><span data-stu-id="af518-150">Music on hold</span></span></p></li>
<li><p><span data-ttu-id="af518-151">狀態（有效/非使用中）</span><span class="sxs-lookup"><span data-stu-id="af518-151">Status (active/inactive)</span></span></p></li>
<li><p><span data-ttu-id="af518-152">查尋群組工作流程或互動式語音回應（IVR）工作流程</span><span class="sxs-lookup"><span data-stu-id="af518-152">Hunt group workflows or Interactive voice response (IVR) workflows</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="af518-153">代理群組</span><span class="sxs-lookup"><span data-stu-id="af518-153">Agent Groups</span></span></p></li>
<li><p><span data-ttu-id="af518-154">佇列</span><span class="sxs-lookup"><span data-stu-id="af518-154">Queues</span></span></p></li>
<li><p><span data-ttu-id="af518-155">假日集</span><span class="sxs-lookup"><span data-stu-id="af518-155">Holiday sets</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="af518-156">建立或刪除任何類型的工作流程</span><span class="sxs-lookup"><span data-stu-id="af518-156">Create or delete any type of workflow</span></span></p></li>
<li><p><span data-ttu-id="af518-157">修改核心回應群組設定，例如： <strong>SIP URI</strong>、<strong>電話號碼</strong>或<strong>工作流程類型</strong>。</span><span class="sxs-lookup"><span data-stu-id="af518-157">Modify core response group settings, such as: <strong>SIP URI</strong>, <strong>Telephone Number</strong>, or <strong>Workflow Type</strong>.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="af518-158">回應群組管理員可以使用下列工具來管理其指定的回應群組。</span><span class="sxs-lookup"><span data-stu-id="af518-158">Response Group Managers can use the following tools to manage their designated response groups.</span></span>

  - <span data-ttu-id="af518-159">Lync Server 控制台</span><span class="sxs-lookup"><span data-stu-id="af518-159">Lync Server Control Panel</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="af518-160">回應群組管理員只能使用此工具管理回應群組設定。</span><span class="sxs-lookup"><span data-stu-id="af518-160">Response Group Managers can only manage Response Group settings with this tool.</span></span> <span data-ttu-id="af518-161">管理員無法使用其他 Lync Server 設定。</span><span class="sxs-lookup"><span data-stu-id="af518-161">Other Lync Server settings are not available to Managers.</span></span>

    
    </div>

  - <span data-ttu-id="af518-162">回應群組設定工具</span><span class="sxs-lookup"><span data-stu-id="af518-162">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="af518-163">Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="af518-163">Lync Server Management Shell</span></span>

<span data-ttu-id="af518-164">回應群組很適合部門或工作組環境（如需詳細資訊，請參閱[Lync Server 2013 中的 [回應] 群組容量規劃](lync-server-2013-capacity-planning-for-response-group.md)），而且可以在全新的電話安裝中部署。</span><span class="sxs-lookup"><span data-stu-id="af518-164">Response Group scales well to departmental or workgroup environments (for details, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) and can be deployed in entirely new telephony installations.</span></span> <span data-ttu-id="af518-165">它支援來自企業語音部署和來自本機電信公司網路的傳入通話。</span><span class="sxs-lookup"><span data-stu-id="af518-165">It supports incoming calls from the Enterprise Voice deployment and from the local carrier network.</span></span> <span data-ttu-id="af518-166">代理程式可以使用 Lync 2013、Lync 2010、Lync 2010，或 Lync Phone Edition，讓通話傳送給他們。</span><span class="sxs-lookup"><span data-stu-id="af518-166">Agents can use Lync 2013, Lync 2010, Lync 2010 Attendant, or Lync Phone Edition to take the calls routed to them.</span></span>

<span data-ttu-id="af518-167">回應群組應用程式是企業語音的元件。</span><span class="sxs-lookup"><span data-stu-id="af518-167">The Response Group application is a component of Enterprise Voice.</span></span> <span data-ttu-id="af518-168">當您部署企業語音時，系統會自動安裝並啟用回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="af518-168">When you deploy Enterprise Voice, the Response Group application is installed and activated automatically.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

