---
title: 回應群組應用程式的 Lync Server 2013： 概觀
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
ms.openlocfilehash: df3bb7b9260e85326718bf388da977833c6e87ea
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a><span data-ttu-id="b229c-102">Lync Server 2013 中的回應群組應用程式概觀</span><span class="sxs-lookup"><span data-stu-id="b229c-102">Overview of the Response Group application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b229c-103">_**主題上次修改日期：** 2012年-09-11_</span><span class="sxs-lookup"><span data-stu-id="b229c-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="b229c-104">來電者與回應群組通話時，該通話會根據群組搜尋或來電者對互動語音回應 (IVR) 問題的回答，路由傳送給代理人。</span><span class="sxs-lookup"><span data-stu-id="b229c-104">When a caller calls a response group, the call is routed to an agent based on a hunt group or the caller's answers to interactive voice response (IVR) questions.</span></span> <span data-ttu-id="b229c-105">回應群組應用程式使用的標準回應群組路由方法，將呼叫路由至下一個線上專員。</span><span class="sxs-lookup"><span data-stu-id="b229c-105">The Response Group application uses standard response group routing methods to route the call to the next available agent.</span></span> <span data-ttu-id="b229c-106">通話路由方法包括序列、最長閒置時間、平行、循環配置資源及應答路由 (也就是說，所有代理人都會同時接獲每一通來電，不論他們目前是否有空)。</span><span class="sxs-lookup"><span data-stu-id="b229c-106">Call routing methods include serial, longest-idle, parallel, round robin, and Attendant routing (that is, all agents are called at the same time for every incoming call, regardless of their current presence).</span></span> <span data-ttu-id="b229c-107">如果沒有代理人有空，則會將通話保留在佇列中，直到某位代理人有空。</span><span class="sxs-lookup"><span data-stu-id="b229c-107">If no agents are available, the call is held in a queue until an agent is available.</span></span> <span data-ttu-id="b229c-108">通話保留在佇列時，來電者會聽到音樂，直到某位有空的代理人受理該通話。</span><span class="sxs-lookup"><span data-stu-id="b229c-108">While in the queue, the caller hears music until an available agent accepts the call.</span></span> <span data-ttu-id="b229c-109">如果佇列已滿，或通話在佇列中逾時，則來電者可能會聽到訊息，然後便中斷通話或將通話轉接至不同的目的地。</span><span class="sxs-lookup"><span data-stu-id="b229c-109">If the queue is full, or if the call times out while in the queue, the caller might hear a message and then is either disconnected or transferred to a different destination.</span></span> <span data-ttu-id="b229c-110">依系統管理員設定回應群組的方式不同，代理人受理通話時，來電者不一定會看到代理人的身分識別。</span><span class="sxs-lookup"><span data-stu-id="b229c-110">When an agent accepts the call, the caller might or might not be able to see the agent's identity, depending on how the administrator configures the response group.</span></span> <span data-ttu-id="b229c-111">代理人得以正式方式受理通話 (表示他們必須先登入群組，才能受理路由傳送給群組的通話)，或以非正式方式受理通話 (表示他們未登入及登出群組就受理通話)。</span><span class="sxs-lookup"><span data-stu-id="b229c-111">Agents can either be formal, which means that they must sign in to the group before they can accept calls routed to the group, or informal, which means that they do not sign into and out of the group to accept calls.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b229c-p102">只有內部部署的使用者可以成為代理人。如果將代理人從內部部署移至線上，回應群組電話將無法路由傳送給該代理人。</span><span class="sxs-lookup"><span data-stu-id="b229c-p102">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b229c-114">回應群組應用程式會使用稱為配對，內部服務佇列通話，然後尋找可用的代理程式。</span><span class="sxs-lookup"><span data-stu-id="b229c-114">The Response Group application uses an internal service, called Match Making, to queue calls and find available agents.</span></span> <span data-ttu-id="b229c-115">每一部執行回應群組應用程式的電腦執行配對服務，但只有一個符合項目進行的服務，每個 Lync 伺服器集區為作用中一次-其他是被動。</span><span class="sxs-lookup"><span data-stu-id="b229c-115">Each computer that runs the Response Group application runs the Match Making service, but only one Match Making service per Lync Server pool is active at a time--the others are passive.</span></span> <span data-ttu-id="b229c-116">如果主動配對服務在意外中斷服務期間無法使用，則被動配對服務其中之一會變成主動配對服務。</span><span class="sxs-lookup"><span data-stu-id="b229c-116">If the active Match Making service becomes unavailable during an unplanned outage, one of the passive Match Making services becomes active.</span></span> <span data-ttu-id="b229c-117">回應群組應用程式達到最佳若要確定該通話路由傳送並佇列會繼續執行不會中斷。</span><span class="sxs-lookup"><span data-stu-id="b229c-117">The Response Group application does its best to make sure that call routing and queuing continues uninterrupted.</span></span> <span data-ttu-id="b229c-118">但是在轉換配對服務時，所有轉接中的通話都會中斷。</span><span class="sxs-lookup"><span data-stu-id="b229c-118">However, when a Match Making service transition occurs, any calls that are in transfer at the time are lost.</span></span> <span data-ttu-id="b229c-119">例如，如果轉換是因為前端伺服器下降目前所處理的作用中配對服務，任何呼叫前端伺服器也是遺失。</span><span class="sxs-lookup"><span data-stu-id="b229c-119">For example, if the transition is due to the Front End Server going down, any calls currently being handled by the active Match Making service on that Front End Server are also lost.</span></span>



</div>

<span data-ttu-id="b229c-120">在 Lync Server 2013 中，有兩個管理角色可供管理回應群組： 回應群組管理員及回應群組管理員。</span><span class="sxs-lookup"><span data-stu-id="b229c-120">In Lync Server 2013, two management roles are available for managing response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="b229c-121">回應群組管理員可以管理任何回應群組的任何層面。</span><span class="sxs-lookup"><span data-stu-id="b229c-121">Response Group Administrators can manage any aspect of any response group.</span></span> <span data-ttu-id="b229c-122">回應群組管理員可管理特定層面，並僅用於回應群組，其所擁有。</span><span class="sxs-lookup"><span data-stu-id="b229c-122">Response Group Managers can manage only certain aspects, and only for the response groups that they own.</span></span> <span data-ttu-id="b229c-123">新的 「 管理員 」 角色可以協助減少管理成本，因為您可以將委派有限的責任對於特定的回應群組，已啟用 Enterprise Voice 的任何使用者。</span><span class="sxs-lookup"><span data-stu-id="b229c-123">The new Manager role can help reduce administration costs, because you can delegate limited responsibilities for specific response groups to any user who is enabled for Enterprise Voice.</span></span>

<span data-ttu-id="b229c-124">若要容納新的 「 管理員 」 角色，Lync Server 2013 回應群組應用程式會介紹受管理或未受管理的**工作流程類型**。</span><span class="sxs-lookup"><span data-stu-id="b229c-124">To accommodate the new Manager role, Lync Server 2013 Response Group application introduces a **Workflow Type** of Managed or Unmanaged.</span></span> <span data-ttu-id="b229c-125">下表描述「已受管理」與「未受管理」回應群組內容。</span><span class="sxs-lookup"><span data-stu-id="b229c-125">The following table describes Managed and Unmanaged response groups.</span></span>

### <a name="managed-and-unmanaged-response-groups"></a><span data-ttu-id="b229c-126">受管理與未受管理回應群組</span><span class="sxs-lookup"><span data-stu-id="b229c-126">Managed and Unmanaged Response Groups</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b229c-127">回應群組類型</span><span class="sxs-lookup"><span data-stu-id="b229c-127">Response group type</span></span></th>
<th><span data-ttu-id="b229c-128">描述</span><span class="sxs-lookup"><span data-stu-id="b229c-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b229c-129">未受管理</span><span class="sxs-lookup"><span data-stu-id="b229c-129">Unmanaged</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b229c-130">未受管理的回應群組沒有指定的管理員。</span><span class="sxs-lookup"><span data-stu-id="b229c-130">Unmanaged response groups have no assigned Managers.</span></span> <span data-ttu-id="b229c-131">只有回應群組管理員可以設定這些回應群組。</span><span class="sxs-lookup"><span data-stu-id="b229c-131">Only the Response Group Administrator can configure these response groups.</span></span></p></li>
<li><p><span data-ttu-id="b229c-132">多個未受管理回應群組可共用一個佇列或代理人群組。</span><span class="sxs-lookup"><span data-stu-id="b229c-132">Multiple unmanaged response groups can share a queue or agent group.</span></span></p></li>
<li><p><span data-ttu-id="b229c-133">當您從舊版移轉回應群組至 Lync Server 2013 時，此類型設為未受管理。</span><span class="sxs-lookup"><span data-stu-id="b229c-133">When you migrate response groups from a prior version to Lync Server 2013, the type is set to Unmanaged.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b229c-134">受管理</span><span class="sxs-lookup"><span data-stu-id="b229c-134">Managed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b229c-135">回應群組管理員可以設定受管理之回應任何的群組層面。</span><span class="sxs-lookup"><span data-stu-id="b229c-135">Response Group Administrators can configure any aspect of managed response groups.</span></span></p></li>
<li><p><span data-ttu-id="b229c-136">回應群組管理員無法檢視或修改未明確指派給他們的回應群組。</span><span class="sxs-lookup"><span data-stu-id="b229c-136">Response Group Managers cannot view or modify response groups that are not explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="b229c-137">回應群組管理員可以設定僅一些明確指派給他們的回應群組設定。</span><span class="sxs-lookup"><span data-stu-id="b229c-137">Response Group Managers can configure only some settings for the response groups that are explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="b229c-138">受管理的回應群組無法與其他任何受管理或未受管理的回應群組共用任何佇列或代理人群組。</span><span class="sxs-lookup"><span data-stu-id="b229c-138">Managed response groups can't share any queues or agent groups with any other response group, managed or unmanaged.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b229c-139">下表說明回應群組經理可以和指派給他們的回應群組無法執行的動作。</span><span class="sxs-lookup"><span data-stu-id="b229c-139">The following table describes the actions that Response Group Managers can and cannot perform for the response groups assigned to them.</span></span>

### <a name="response-group-manager-capabilities"></a><span data-ttu-id="b229c-140">回應群組管理員功能</span><span class="sxs-lookup"><span data-stu-id="b229c-140">Response Group Manager Capabilities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b229c-141">可設定：</span><span class="sxs-lookup"><span data-stu-id="b229c-141">Can configure:</span></span></th>
<th><span data-ttu-id="b229c-142">可建立、刪除或設定：</span><span class="sxs-lookup"><span data-stu-id="b229c-142">Can create, delete, or configure:</span></span></th>
<th><span data-ttu-id="b229c-143">無法：</span><span class="sxs-lookup"><span data-stu-id="b229c-143">Cannot:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="b229c-144">代理程式</span><span class="sxs-lookup"><span data-stu-id="b229c-144">Agents</span></span></p></li>
<li><p><span data-ttu-id="b229c-145">歡迎訊息</span><span class="sxs-lookup"><span data-stu-id="b229c-145">Welcome message</span></span></p></li>
<li><p><span data-ttu-id="b229c-146">回應群組名稱</span><span class="sxs-lookup"><span data-stu-id="b229c-146">Response Group name</span></span></p></li>
<li><p><span data-ttu-id="b229c-147">描述</span><span class="sxs-lookup"><span data-stu-id="b229c-147">Description</span></span></p></li>
<li><p><span data-ttu-id="b229c-148">顯示號碼</span><span class="sxs-lookup"><span data-stu-id="b229c-148">Display number</span></span></p></li>
<li><p><span data-ttu-id="b229c-149">營業時間</span><span class="sxs-lookup"><span data-stu-id="b229c-149">Business hours</span></span></p></li>
<li><p><span data-ttu-id="b229c-150">保留音樂</span><span class="sxs-lookup"><span data-stu-id="b229c-150">Music on hold</span></span></p></li>
<li><p><span data-ttu-id="b229c-151">狀態 (使用中/非使用中)</span><span class="sxs-lookup"><span data-stu-id="b229c-151">Status (active/inactive)</span></span></p></li>
<li><p><span data-ttu-id="b229c-152">群組搜尋工作流程或互動語音回應 (IVR) 工作流程</span><span class="sxs-lookup"><span data-stu-id="b229c-152">Hunt group workflows or Interactive voice response (IVR) workflows</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="b229c-153">代理人群組</span><span class="sxs-lookup"><span data-stu-id="b229c-153">Agent Groups</span></span></p></li>
<li><p><span data-ttu-id="b229c-154">佇列</span><span class="sxs-lookup"><span data-stu-id="b229c-154">Queues</span></span></p></li>
<li><p><span data-ttu-id="b229c-155">假日集</span><span class="sxs-lookup"><span data-stu-id="b229c-155">Holiday sets</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="b229c-156">建立或刪除任何工作流程類型</span><span class="sxs-lookup"><span data-stu-id="b229c-156">Create or delete any type of workflow</span></span></p></li>
<li><p><span data-ttu-id="b229c-157">修改核心回應群組設定，例如：<strong>[SIP URI]</strong>、<strong>[電話號碼]</strong> 或 <strong>[工作流程類型]</strong>。</span><span class="sxs-lookup"><span data-stu-id="b229c-157">Modify core response group settings, such as: <strong>SIP URI</strong>, <strong>Telephone Number</strong>, or <strong>Workflow Type</strong>.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b229c-158">回應群組管理員可以使用下列工具來管理其指定的回應群組。</span><span class="sxs-lookup"><span data-stu-id="b229c-158">Response Group Managers can use the following tools to manage their designated response groups.</span></span>

  - <span data-ttu-id="b229c-159">Lync Server 控制台</span><span class="sxs-lookup"><span data-stu-id="b229c-159">Lync Server Control Panel</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b229c-160">回應群組管理員只能管理回應群組設定，使用此工具。</span><span class="sxs-lookup"><span data-stu-id="b229c-160">Response Group Managers can only manage Response Group settings with this tool.</span></span> <span data-ttu-id="b229c-161">其他 Lync Server 的設定不提供給主管。</span><span class="sxs-lookup"><span data-stu-id="b229c-161">Other Lync Server settings are not available to Managers.</span></span>

    
    </div>

  - <span data-ttu-id="b229c-162">回應群組設定工具</span><span class="sxs-lookup"><span data-stu-id="b229c-162">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="b229c-163">Lync Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="b229c-163">Lync Server Management Shell</span></span>

<span data-ttu-id="b229c-164">回應群組比例很適合用來部門或工作群組環境 （如需詳細資訊，請參閱[Capacity planning for Lync Server 2013 中的回應群組](lync-server-2013-capacity-planning-for-response-group.md)），並可以部署在全新電話語音安裝。</span><span class="sxs-lookup"><span data-stu-id="b229c-164">Response Group scales well to departmental or workgroup environments (for details, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) and can be deployed in entirely new telephony installations.</span></span> <span data-ttu-id="b229c-165">它支援從 Enterprise Voice 部署和本機通信業者網路的傳入呼叫。</span><span class="sxs-lookup"><span data-stu-id="b229c-165">It supports incoming calls from the Enterprise Voice deployment and from the local carrier network.</span></span> <span data-ttu-id="b229c-166">代理程式可以使用 Lync 2013、 Lync 2010、 Lync 2010 Attendant 或 Lync Phone Edition，才會路由傳送至他們的通話。</span><span class="sxs-lookup"><span data-stu-id="b229c-166">Agents can use Lync 2013, Lync 2010, Lync 2010 Attendant, or Lync Phone Edition to take the calls routed to them.</span></span>

<span data-ttu-id="b229c-167">回應群組應用程式是企業語音元件。</span><span class="sxs-lookup"><span data-stu-id="b229c-167">The Response Group application is a component of Enterprise Voice.</span></span> <span data-ttu-id="b229c-168">當您部署企業語音時，回應群組應用程式已安裝，並自動啟動。</span><span class="sxs-lookup"><span data-stu-id="b229c-168">When you deploy Enterprise Voice, the Response Group application is installed and activated automatically.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

