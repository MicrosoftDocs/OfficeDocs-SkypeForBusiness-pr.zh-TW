---
title: 規劃商務用 Skype Server 中的回應群組應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6cc333e7-4029-4372-86b2-016040c415fb
description: 規劃商務用 Skype Server Enterprise Voice 中的回應群組, 可讓您設定呼叫路由至使用者群組。 包括音訊檔需求。
ms.openlocfilehash: b1c8a2ab1a7dc42fd290df4bdc1ccf69b52db43a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187567"
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server"></a><span data-ttu-id="10e25-104">規劃商務用 Skype Server 中的回應群組應用程式</span><span class="sxs-lookup"><span data-stu-id="10e25-104">Plan for the Response Group application in Skype for Business Server</span></span>

<span data-ttu-id="10e25-105">規劃商務用 Skype Server Enterprise Voice 中的回應群組, 可讓您設定呼叫路由至使用者群組。</span><span class="sxs-lookup"><span data-stu-id="10e25-105">Planning for response groups in Skype for Business Server Enterprise Voice, which enables you to set up call routing to groups of users.</span></span> <span data-ttu-id="10e25-106">包括音訊檔需求。</span><span class="sxs-lookup"><span data-stu-id="10e25-106">Includes audio file requirements.</span></span>

<span data-ttu-id="10e25-107">如果您的組織有一組人接聽並管理特定類型的通話 (例如客戶服務、內部說明服務台或部門的一般電話支援), 您可以部署回應群組應用程式來管理這些呼叫類型。</span><span class="sxs-lookup"><span data-stu-id="10e25-107">If your organization has groups of people who answer and manage certain types of calls, such as for customer service, an internal help desk, or general telephone support for a department, you can deploy the Response Group application to manage these types of calls.</span></span> <span data-ttu-id="10e25-108">回應群組應用程式會將來電路由並列隊給指定的人員 (稱為代理者)。</span><span class="sxs-lookup"><span data-stu-id="10e25-108">The Response Group application routes and queues incoming calls to designated persons, who are known as agents.</span></span> <span data-ttu-id="10e25-109">您可以增加電話支援服務的使用, 並使用回應群組來減少執行這些服務的額外負荷。</span><span class="sxs-lookup"><span data-stu-id="10e25-109">You can increase the use of telephone support services and reduce the overhead of running these services by using response groups.</span></span>

<span data-ttu-id="10e25-110">當來電者呼叫回應群組時, 通話會根據查尋群組或來電者對互動式語音回應 (IVR) 問題的答案來傳送給代理程式。</span><span class="sxs-lookup"><span data-stu-id="10e25-110">When a caller calls a response group, the call is routed to an agent based on a hunt group or the caller's answers to interactive voice response (IVR) questions.</span></span> <span data-ttu-id="10e25-111">回應群組應用程式會使用標準的回應群組路由方法, 將呼叫路由至下一個可用的代理程式。</span><span class="sxs-lookup"><span data-stu-id="10e25-111">The Response Group application uses standard response group routing methods to route the call to the next available agent.</span></span> <span data-ttu-id="10e25-112">支援的呼叫路由方法包括串列、最長閒置、並行、迴圈和傳送路線 (也就是, 所有的代理程式都是在每次撥入通話時呼叫, 不論其目前的狀態為何)。</span><span class="sxs-lookup"><span data-stu-id="10e25-112">Supported call routing methods include serial, longest-idle, parallel, round robin, and Attendant routing (that is, all agents are called at the same time for every incoming call, regardless of their current presence).</span></span>

<span data-ttu-id="10e25-113">如果沒有可用的代理, 通話會一直保留在佇列中, 直到有可用的代理程式。</span><span class="sxs-lookup"><span data-stu-id="10e25-113">If no agents are available, the call is held in a queue until an agent is available.</span></span> <span data-ttu-id="10e25-114">在佇列中, 來電者會聽到音樂, 直到可用的代理程式接受通話。</span><span class="sxs-lookup"><span data-stu-id="10e25-114">While in the queue, the caller hears music until an available agent accepts the call.</span></span> <span data-ttu-id="10e25-115">如果佇列已滿, 或通話在佇列中超時, 來電者可能會聽到訊息, 然後中斷連線或傳送到不同的目的地, 例如不同的電話號碼或語音信箱。</span><span class="sxs-lookup"><span data-stu-id="10e25-115">If the queue is full, or if the call times out while in the queue, the caller might hear a message and then is either disconnected or transferred to a different destination, such as a different phone number or voicemail.</span></span> <span data-ttu-id="10e25-116">當代理程式接受來電時, 呼叫者可能也可能無法看到代理人的身分識別, 視系統管理員設定回應群組的方式而定。</span><span class="sxs-lookup"><span data-stu-id="10e25-116">When an agent accepts the call, the caller might or might not be able to see the agent's identity, depending on how the administrator configures the response group.</span></span> <span data-ttu-id="10e25-117">Agent 可以是正式的, 這表示他們必須先登入群組, 才能接受路由到群組的呼叫, 或者是非正式的, 這表示它們不會登入和登出群組以接受通話。</span><span class="sxs-lookup"><span data-stu-id="10e25-117">Agents can either be formal, which means that they must sign in to the group before they can accept calls routed to the group, or informal, which means that they do not sign into and out of the group to accept calls.</span></span>

> [!NOTE]
> <span data-ttu-id="10e25-118">只有內部部署使用者可以使用代理程式。</span><span class="sxs-lookup"><span data-stu-id="10e25-118">Only on-premises users can be agents.</span></span> <span data-ttu-id="10e25-119">如果代理程式是從內部部署移至線上, 回應群組呼叫將不會路由至該代理程式。</span><span class="sxs-lookup"><span data-stu-id="10e25-119">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>

> [!NOTE]
> <span data-ttu-id="10e25-120">回應群組應用程式使用名為 [相符] 的內部服務來排隊通話, 並尋找可用的代理程式。</span><span class="sxs-lookup"><span data-stu-id="10e25-120">The Response Group application uses an internal service, called Match Making, to queue calls and find available agents.</span></span> <span data-ttu-id="10e25-121">每個執行回應群組應用程式的電腦都會執行相符的服務, 但一次只能有一個相符的服務, 而其他則是被動的。</span><span class="sxs-lookup"><span data-stu-id="10e25-121">Each computer that runs the Response Group application runs the Match Making service, but only one Match Making service per pool is active at a time--the others are passive.</span></span> <span data-ttu-id="10e25-122">如果在未計畫的停機期間, 使用中的 [相符] 使服務變為無法使用, 其中一個被動的相符, 就會變成作用中。</span><span class="sxs-lookup"><span data-stu-id="10e25-122">If the active Match Making service becomes unavailable during an unplanned outage, one of the passive Match Making services becomes active.</span></span> <span data-ttu-id="10e25-123">回應群組應用程式最能確保呼叫路由和佇列繼續不間斷地進行。</span><span class="sxs-lookup"><span data-stu-id="10e25-123">The Response Group application does its best to make sure that call routing and queuing continues uninterrupted.</span></span> <span data-ttu-id="10e25-124">不過, 當相符的服務轉換發生時, 任何在該時間傳輸的呼叫都會遺失。</span><span class="sxs-lookup"><span data-stu-id="10e25-124">However, when a Match Making service transition occurs, any calls that are in transfer at the time are lost.</span></span> <span data-ttu-id="10e25-125">例如, 如果您的轉換是由於前端伺服器即將停機而引起, 則目前由作用中的 Match 所處理的任何呼叫都會在該前端伺服器上執行的服務也會遺失。</span><span class="sxs-lookup"><span data-stu-id="10e25-125">For example, if the transition is due to the Front End Server going down, any calls currently being handled by the active Match Making service on that Front End Server are also lost.</span></span>

## <a name="response-group-workflows"></a><span data-ttu-id="10e25-126">回應群組工作流程</span><span class="sxs-lookup"><span data-stu-id="10e25-126">Response group workflows</span></span>

<span data-ttu-id="10e25-127">工作流程會定義撥打電話到某人接聽來電之時間的通話行為。</span><span class="sxs-lookup"><span data-stu-id="10e25-127">A workflow defines the behavior of a call from the time that the phone rings to the time that someone answers the call.</span></span> <span data-ttu-id="10e25-128">工作流程會指定要用來進行通話的佇列, 並指定用來進行查尋群組的傳送方法, 或是用於互動式回應群組的問題與解答。</span><span class="sxs-lookup"><span data-stu-id="10e25-128">The workflow specifies the queue to use for holding the call, and specifies the routing method to use for hunt groups or the questions and answers to use for interactive response groups.</span></span> <span data-ttu-id="10e25-129">工作流程也會定義設定, 例如 [歡迎] 訊息、[等候音樂]、[上班時間] 和 [假日]。</span><span class="sxs-lookup"><span data-stu-id="10e25-129">A workflow also defines settings such as a welcome message, music on hold, business hours, and holidays.</span></span>

> [!NOTE]
> <span data-ttu-id="10e25-130">您必須先建立代理群組和佇列, 才能建立使用它們的工作流程。</span><span class="sxs-lookup"><span data-stu-id="10e25-130">You must create agent groups and queues before you create a workflow that uses them.</span></span>

## <a name="management-of-response-groups"></a><span data-ttu-id="10e25-131">回應群組的管理</span><span class="sxs-lookup"><span data-stu-id="10e25-131">Management of response groups</span></span>

<span data-ttu-id="10e25-132">在商務用 Skype Server 中, 有兩個管理角色可供管理回應群組: [回應群組管理員] 與 [回應群組管理員]。</span><span class="sxs-lookup"><span data-stu-id="10e25-132">In Skype for Business Server, two management roles are available for managing response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="10e25-133">回應群組管理員可以管理任何回應群組的任何方面。</span><span class="sxs-lookup"><span data-stu-id="10e25-133">Response Group Administrators can manage any aspect of any response group.</span></span> <span data-ttu-id="10e25-134">回應群組管理員只能管理特定的部分, 而且只能管理自己擁有的回應群組。</span><span class="sxs-lookup"><span data-stu-id="10e25-134">Response Group Managers can manage only certain aspects, and only for the response groups that they own.</span></span> <span data-ttu-id="10e25-135">Manager 角色可協助您降低系統管理成本, 因為您可以將特定回應群組的有限責任委派給任何已啟用企業語音的使用者。</span><span class="sxs-lookup"><span data-stu-id="10e25-135">The Manager role can help you reduce your administration costs, because you can delegate limited responsibilities for specific response groups to any user who is enabled for Enterprise Voice.</span></span> <span data-ttu-id="10e25-136">請注意, 使用者可以同時是回應群組管理員與回應群組系統管理員。</span><span class="sxs-lookup"><span data-stu-id="10e25-136">Note that a user can be both a Response Group Manager and a Response Group Administrator.</span></span>

<span data-ttu-id="10e25-137">為了適應 Manager 角色, 回應群組應用程式會使用受管理或未受管理的**工作流程類型**。</span><span class="sxs-lookup"><span data-stu-id="10e25-137">To accommodate the Manager role, Response Group application uses a **Workflow Type** of Managed or Unmanaged.</span></span> <span data-ttu-id="10e25-138">下表說明受管理和未受管理的回應群組。</span><span class="sxs-lookup"><span data-stu-id="10e25-138">The following table describes Managed and Unmanaged response groups.</span></span>

<span data-ttu-id="10e25-139">**受管理和未受管理的回應群組**</span><span class="sxs-lookup"><span data-stu-id="10e25-139">**Managed and Unmanaged Response Groups**</span></span>

|<span data-ttu-id="10e25-140">**回應群組類型**</span><span class="sxs-lookup"><span data-stu-id="10e25-140">**Response group type**</span></span>|<span data-ttu-id="10e25-141">**說明**</span><span class="sxs-lookup"><span data-stu-id="10e25-141">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="10e25-142">管</span><span class="sxs-lookup"><span data-stu-id="10e25-142">Unmanaged</span></span>  <br/> | <span data-ttu-id="10e25-143">未受管理的回應群組沒有已指派的管理員。</span><span class="sxs-lookup"><span data-stu-id="10e25-143">Unmanaged response groups have no assigned Managers.</span></span> <span data-ttu-id="10e25-144">只有回應群組管理員可以設定這些回應群組。</span><span class="sxs-lookup"><span data-stu-id="10e25-144">Only the Response Group Administrator can configure these response groups.</span></span> <br/>  <span data-ttu-id="10e25-145">多個未受管理的回應群組可以共用 [佇列] 或 [代理] 群組。</span><span class="sxs-lookup"><span data-stu-id="10e25-145">Multiple unmanaged response groups can share a queue or agent group.</span></span> <br/>  <span data-ttu-id="10e25-146">當您將回應群組從先前的版本遷移到商務用 Skype Server 之後, 該類型就會設定為 [未管理]。</span><span class="sxs-lookup"><span data-stu-id="10e25-146">When you migrate response groups from a prior version to Skype for Business Server, the type is set to Unmanaged.</span></span> <br/> |
|<span data-ttu-id="10e25-147">被</span><span class="sxs-lookup"><span data-stu-id="10e25-147">Managed</span></span>  <br/> | <span data-ttu-id="10e25-148">回應群組管理員可以設定受管理回應群組的任何方面。</span><span class="sxs-lookup"><span data-stu-id="10e25-148">Response Group Administrators can configure any aspect of managed response groups.</span></span> <br/>  <span data-ttu-id="10e25-149">回應群組管理員無法查看或修改未明確指派給他們的回應群組。</span><span class="sxs-lookup"><span data-stu-id="10e25-149">Response Group Managers cannot view or modify response groups that are not explicitly assigned to them.</span></span> <br/>  <span data-ttu-id="10e25-150">回應群組管理員只能針對明確指派給他們的回應群組設定部分設定。</span><span class="sxs-lookup"><span data-stu-id="10e25-150">Response Group Managers can configure only some settings for the response groups that are explicitly assigned to them.</span></span> <br/>  <span data-ttu-id="10e25-151">受管理的回應群組無法與任何其他回應群組、託管或未受管理的人共用任何佇列或代理群組。</span><span class="sxs-lookup"><span data-stu-id="10e25-151">Managed response groups can't share any queues or agent groups with any other response group, managed or unmanaged.</span></span> <br/> |

<span data-ttu-id="10e25-152">下表說明回應群組管理員可以對指派給他們的回應群組執行哪些動作。</span><span class="sxs-lookup"><span data-stu-id="10e25-152">The following table describes the actions that Response Group Managers can and cannot perform for the response groups assigned to them.</span></span>

<span data-ttu-id="10e25-153">**回應群組管理員功能**</span><span class="sxs-lookup"><span data-stu-id="10e25-153">**Response Group Manager Capabilities**</span></span>

|<span data-ttu-id="10e25-154">**可以設定:**</span><span class="sxs-lookup"><span data-stu-id="10e25-154">**Can configure:**</span></span>|<span data-ttu-id="10e25-155">**可以建立、刪除或設定:**</span><span class="sxs-lookup"><span data-stu-id="10e25-155">**Can create, delete, or configure:**</span></span>|<span data-ttu-id="10e25-156">**不**</span><span class="sxs-lookup"><span data-stu-id="10e25-156">**Cannot:**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="10e25-157">代理程式</span><span class="sxs-lookup"><span data-stu-id="10e25-157">Agents</span></span> <br/>  <span data-ttu-id="10e25-158">歡迎訊息</span><span class="sxs-lookup"><span data-stu-id="10e25-158">Welcome message</span></span> <br/>  <span data-ttu-id="10e25-159">回應群組名稱</span><span class="sxs-lookup"><span data-stu-id="10e25-159">Response Group name</span></span> <br/>  <span data-ttu-id="10e25-160">說明</span><span class="sxs-lookup"><span data-stu-id="10e25-160">Description</span></span> <br/>  <span data-ttu-id="10e25-161">顯示數位</span><span class="sxs-lookup"><span data-stu-id="10e25-161">Display number</span></span> <br/>  <span data-ttu-id="10e25-162">商務時間</span><span class="sxs-lookup"><span data-stu-id="10e25-162">Business hours</span></span> <br/>  <span data-ttu-id="10e25-163">等候音樂</span><span class="sxs-lookup"><span data-stu-id="10e25-163">Music on hold</span></span> <br/>  <span data-ttu-id="10e25-164">狀態 (有效/非使用中)</span><span class="sxs-lookup"><span data-stu-id="10e25-164">Status (active/inactive)</span></span> <br/>  <span data-ttu-id="10e25-165">查尋群組工作流程或互動式語音回應 (IVR) 工作流程</span><span class="sxs-lookup"><span data-stu-id="10e25-165">Hunt group workflows or Interactive voice response (IVR) workflows</span></span> <br/> | <span data-ttu-id="10e25-166">代理群組</span><span class="sxs-lookup"><span data-stu-id="10e25-166">Agent Groups</span></span> <br/>  <span data-ttu-id="10e25-167">佇列</span><span class="sxs-lookup"><span data-stu-id="10e25-167">Queues</span></span> <br/>  <span data-ttu-id="10e25-168">假日集</span><span class="sxs-lookup"><span data-stu-id="10e25-168">Holiday sets</span></span> <br/> | <span data-ttu-id="10e25-169">建立或刪除任何類型的工作流程</span><span class="sxs-lookup"><span data-stu-id="10e25-169">Create or delete any type of workflow</span></span> <br/>  <span data-ttu-id="10e25-170">修改核心回應群組設定, 例如: **SIP URI**、**電話號碼**或**工作流程類型**。</span><span class="sxs-lookup"><span data-stu-id="10e25-170">Modify core response group settings, such as: **SIP URI**, **Telephone Number**, or **Workflow Type**.</span></span>  <br/> |

<span data-ttu-id="10e25-171">回應群組管理員可以使用下列工具來管理其指定的回應群組。</span><span class="sxs-lookup"><span data-stu-id="10e25-171">Response Group Managers can use the following tools to manage their designated response groups.</span></span>

- <span data-ttu-id="10e25-172">商務用 Skype Server 的 [控制台]</span><span class="sxs-lookup"><span data-stu-id="10e25-172">Skype for Business Server Control Panel</span></span>

    > [!NOTE]
    > <span data-ttu-id="10e25-173">回應群組管理員只能使用此工具管理回應群組設定。</span><span class="sxs-lookup"><span data-stu-id="10e25-173">Response Group Managers can only manage Response Group settings with this tool.</span></span> <span data-ttu-id="10e25-174">系統管理員不提供其他商務用 Skype 伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="10e25-174">Other Skype for Business Server settings are not available to Managers.</span></span>

- <span data-ttu-id="10e25-175">回應群組設定工具</span><span class="sxs-lookup"><span data-stu-id="10e25-175">Response Group Configuration Tool</span></span>

- <span data-ttu-id="10e25-176">商務用 Skype Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="10e25-176">Skype for Business Server Management Shell</span></span>

<span data-ttu-id="10e25-177">回應群組很適合部門或工作組環境 (如需詳細資訊, 請參閱[回應群組的容量規劃](https://technet.microsoft.com/library/a2459a69-1f45-4f2f-bca5-d4f442708e44.aspx)), 而且可以在全新的電話安裝中部署。</span><span class="sxs-lookup"><span data-stu-id="10e25-177">Response Group scales well to departmental or workgroup environments (for details, see [Capacity Planning for Response Group](https://technet.microsoft.com/library/a2459a69-1f45-4f2f-bca5-d4f442708e44.aspx)) and can be deployed in entirely new telephony installations.</span></span> <span data-ttu-id="10e25-178">它支援來自企業語音部署和來自本機電信公司網路的傳入通話。</span><span class="sxs-lookup"><span data-stu-id="10e25-178">It supports incoming calls from the Enterprise Voice deployment and from the local carrier network.</span></span> <span data-ttu-id="10e25-179">代理程式可以使用商務用 Skype、Lync 2013、Lync 2010、Lync 2010 助理或 Lync Phone Edition, 進行傳送給他們的通話。</span><span class="sxs-lookup"><span data-stu-id="10e25-179">Agents can use Skype for Business, Lync 2013, Lync 2010, Lync 2010 Attendant, or Lync Phone Edition to take the calls routed to them.</span></span>

## <a name="deployment-and-requirements"></a><span data-ttu-id="10e25-180">部署與需求</span><span class="sxs-lookup"><span data-stu-id="10e25-180">Deployment and requirements</span></span>

<span data-ttu-id="10e25-181">當您部署企業語音時, 系統會自動啟用回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="10e25-181">The Response Group application is automatically enabled when you deploy Enterprise Voice.</span></span>

### <a name="hardware-and-software-requirements"></a><span data-ttu-id="10e25-182">硬體和軟體需求</span><span class="sxs-lookup"><span data-stu-id="10e25-182">Hardware and software requirements</span></span>

<span data-ttu-id="10e25-183">回應群組應用程式具有相同的硬體需求、作業系統需求和軟體先決條件 (作為前端伺服器)。</span><span class="sxs-lookup"><span data-stu-id="10e25-183">The Response Group application has the same hardware requirements, operating system requirements and software prerequisites as Front End Servers.</span></span>

<span data-ttu-id="10e25-184">如果您使用 Windows Media Audio (.wma) 檔案來取得回應群組的音樂與宣告, 所有前端伺服器或執行回應群組應用程式的標準版伺服器, 都必須針對執行 Windows 的伺服器安裝 Windows Media 格式執行時間伺服器 2008 R2 或適用于執行 Windows Server 2012 或 Windows Server 2012 R2 之伺服器的 Microsoft 媒體基礎。</span><span class="sxs-lookup"><span data-stu-id="10e25-184">If you use Windows Media Audio (.wma) files for Response Group music and announcements, all Front End Servers or Standard Editions servers that run the Response Group application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="10e25-185">針對 Windows Server 2008 R2, Windows Media 格式執行時間已安裝為 Windows 桌面體驗的一部分。</span><span class="sxs-lookup"><span data-stu-id="10e25-185">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span>

<span data-ttu-id="10e25-186">回應群組使用**語言套件**來支援文字轉換語音和語音辨識。</span><span class="sxs-lookup"><span data-stu-id="10e25-186">Response Group uses **Language packs** to support text-to-speech and speech recognition.</span></span> <span data-ttu-id="10e25-187">當您設定郵件時, 會使用這些語音技術, 例如歡迎訊息及其他提示, 以及互動式語音回應 (IVR) 問題與解答。</span><span class="sxs-lookup"><span data-stu-id="10e25-187">These speech technologies are used when you configure messages, such as the welcome message and other prompts, and interactive voice response (IVR) questions and answers.</span></span> <span data-ttu-id="10e25-188">根據預設, 在您部署商務用 Skype Server 時, 會安裝26個支援的語言套件。</span><span class="sxs-lookup"><span data-stu-id="10e25-188">By default, the 26 supported language packs are installed when you deploy Skype for Business Server.</span></span>

### <a name="port-requirements"></a><span data-ttu-id="10e25-189">埠需求</span><span class="sxs-lookup"><span data-stu-id="10e25-189">Port Requirements</span></span>

<span data-ttu-id="10e25-190">回應群組應用程式使用下列埠:</span><span class="sxs-lookup"><span data-stu-id="10e25-190">The Response Group application uses the following ports:</span></span>

- <span data-ttu-id="10e25-191">SIP 偵聽要求的**埠 5071**</span><span class="sxs-lookup"><span data-stu-id="10e25-191">**Port 5071**   for SIP listening requests</span></span>

- <span data-ttu-id="10e25-192">Interserver 通訊的**埠 8404**</span><span class="sxs-lookup"><span data-stu-id="10e25-192">**Port 8404**   for interserver communications</span></span>

    > [!NOTE]
    > <span data-ttu-id="10e25-193">這個埠是用於相符的服務, 而且當回應群組應用程式部署在擁有多個前端伺服器的池中時, 就是必要的。</span><span class="sxs-lookup"><span data-stu-id="10e25-193">This port is used for the Match Making service and is required when the Response Group application is deployed in a pool that has more than one Front End Server.</span></span>

   > [!NOTE]
   > <span data-ttu-id="10e25-194">這些埠是預設的設定, 您可以使用**CsApplicationServer** Cmdlet 變更這些設定。</span><span class="sxs-lookup"><span data-stu-id="10e25-194">These ports are default settings that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="10e25-195">如需此 Cmdlet 的詳細資訊, 請參閱商務用 Skype Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="10e25-195">For details about this cmdlet, see the Skype for Business Server Management Shell documentation.</span></span>

### <a name="audio-file-requirements"></a><span data-ttu-id="10e25-196">音訊檔需求</span><span class="sxs-lookup"><span data-stu-id="10e25-196">Audio File Requirements</span></span>

<span data-ttu-id="10e25-197">回應群組應用程式支援波形 (.wav) 檔案格式和 Windows Media 音訊 (.wma) 檔案格式, 以取得回應群組訊息、等候音樂或互動式語音回應 (IVR) 問題。</span><span class="sxs-lookup"><span data-stu-id="10e25-197">The Response Group application supports wave (.wav) file format and Windows Media audio (.wma) file format for Response Group messages, on-hold music, or interactive voice response (IVR) questions.</span></span>

<span data-ttu-id="10e25-198">Windows Media 音訊檔案格式要求 Windows Media 格式執行時間已安裝在執行 Windows Server 2008 R2 和 Windows Server 2008 的前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="10e25-198">The Windows Media audio file format requires that the Windows Media Format Runtime is installed on Front End Servers running Windows Server 2008 R2 and Windows Server 2008.</span></span> <span data-ttu-id="10e25-199">如需詳細資訊, 請參閱本節前面的「軟體需求」。</span><span class="sxs-lookup"><span data-stu-id="10e25-199">For more details, see "Software Requirements" earlier in this section.</span></span>

#### <a name="supported-wave-file-formats"></a><span data-ttu-id="10e25-200">支援的 Wave 檔案格式</span><span class="sxs-lookup"><span data-stu-id="10e25-200">Supported Wave File Formats</span></span>

<span data-ttu-id="10e25-201">所有的 wave 檔案必須符合下列需求:</span><span class="sxs-lookup"><span data-stu-id="10e25-201">All wave files must meet the following requirements:</span></span>

- <span data-ttu-id="10e25-202">8位或16位檔案</span><span class="sxs-lookup"><span data-stu-id="10e25-202">8-bit or 16-bit file</span></span>

- <span data-ttu-id="10e25-203">線性脈衝程式碼調製 (LPCM)、法律或 mu-定律格式</span><span class="sxs-lookup"><span data-stu-id="10e25-203">Linear pulse code modulation (LPCM), A-Law, or mu-Law format</span></span>

- <span data-ttu-id="10e25-204">單聲道或身歷聲</span><span class="sxs-lookup"><span data-stu-id="10e25-204">Mono or stereo</span></span>

- <span data-ttu-id="10e25-205">4MB 或更低</span><span class="sxs-lookup"><span data-stu-id="10e25-205">4MB or less</span></span>

<span data-ttu-id="10e25-206">為了獲得波形檔案的最佳效能, 建議使用 16 kHz、單聲道、16位波檔案。</span><span class="sxs-lookup"><span data-stu-id="10e25-206">For the best performance of wave files, a 16 kHz, mono, 16-bit Wave file is recommended.</span></span>

#### <a name="supported-windows-media-audio-file-formats"></a><span data-ttu-id="10e25-207">支援的 Windows Media 音訊檔案格式</span><span class="sxs-lookup"><span data-stu-id="10e25-207">Supported Windows Media Audio File Formats</span></span>

<span data-ttu-id="10e25-208">如果您使用的是 Windows Media 音訊檔, 請考慮使用低傳輸率, 並在 [載入] 底下驗證系統的效能。</span><span class="sxs-lookup"><span data-stu-id="10e25-208">If you use a Windows Media audio file, consider using low bit rates, and verify the performance of your system under load.</span></span>

<span data-ttu-id="10e25-209">您可以使用 Microsoft Expression 編碼器4將檔案轉換成 Windows Media 音訊格式。</span><span class="sxs-lookup"><span data-stu-id="10e25-209">You can use the Microsoft Expression Encoder 4 to convert a file to the Windows Media Audio format.</span></span> <span data-ttu-id="10e25-210">若要下載運算式編碼器 4, [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843)請參閱。</span><span class="sxs-lookup"><span data-stu-id="10e25-210">To download Expression Encoder 4, see [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843).</span></span>

### <a name="response-group-configuration-tool-requirements"></a><span data-ttu-id="10e25-211">回應群組設定工具需求</span><span class="sxs-lookup"><span data-stu-id="10e25-211">Response Group Configuration Tool Requirements</span></span>

<span data-ttu-id="10e25-212">[回應群組設定] 工具支援下表所述的作業系統與網頁瀏覽器混合。</span><span class="sxs-lookup"><span data-stu-id="10e25-212">The Response Group Configuration Tool supports the combinations of operating systems and web browsers described in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="10e25-213">支援32位或64位版本的作業系統。</span><span class="sxs-lookup"><span data-stu-id="10e25-213">32-bit or 64-bit versions of the operating systems are supported.</span></span> <span data-ttu-id="10e25-214">僅支援32位版本的 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="10e25-214">Only 32-bit versions of Internet Explorer are supported.</span></span>

<span data-ttu-id="10e25-215">**支援的作業系統與網頁瀏覽器**</span><span class="sxs-lookup"><span data-stu-id="10e25-215">**Supported Operating Systems and Web Browsers**</span></span>

|<span data-ttu-id="10e25-216">**作業系統**</span><span class="sxs-lookup"><span data-stu-id="10e25-216">**Operating system**</span></span>|<span data-ttu-id="10e25-217">**網頁瀏覽器**</span><span class="sxs-lookup"><span data-stu-id="10e25-217">**Web browser**</span></span>|
|:-----|:-----|
|<span data-ttu-id="10e25-218">Windows Vista (含 Service Pack (SP) 2)</span><span class="sxs-lookup"><span data-stu-id="10e25-218">Windows Vista with Service Pack (SP) 2</span></span>  <br/> |<span data-ttu-id="10e25-219">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="10e25-219">Internet Explorer 7</span></span>  <br/> <span data-ttu-id="10e25-220">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="10e25-220">Internet Explorer 8 (native mode)</span></span>  <br/> <span data-ttu-id="10e25-221">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="10e25-221">Internet Explorer 9 (native mode)</span></span>  <br/> |
|<span data-ttu-id="10e25-222">Windows 7</span><span class="sxs-lookup"><span data-stu-id="10e25-222">Windows 7</span></span>  <br/> <span data-ttu-id="10e25-223">Windows 7 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="10e25-223">Windows 7 with Service Pack 1</span></span>  <br/> |<span data-ttu-id="10e25-224">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="10e25-224">Internet Explorer 8 (native mode)</span></span>  <br/> <span data-ttu-id="10e25-225">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="10e25-225">Internet Explorer 9 (native mode)</span></span>  <br/> |
|<span data-ttu-id="10e25-226">Windows Server 2008 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="10e25-226">Windows Server 2008 with Service Pack 2</span></span>  <br/> |<span data-ttu-id="10e25-227">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="10e25-227">Internet Explorer 7</span></span>  <br/> <span data-ttu-id="10e25-228">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="10e25-228">Internet Explorer 8 (native mode)</span></span>  <br/> <span data-ttu-id="10e25-229">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="10e25-229">Internet Explorer 9 (native mode)</span></span>  <br/> |
|<span data-ttu-id="10e25-230">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="10e25-230">Windows Server 2008 R2</span></span>  <br/> <span data-ttu-id="10e25-231">Windows Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="10e25-231">Windows Server 2008 R2 with Service Pack 1</span></span>  <br/> |<span data-ttu-id="10e25-232">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="10e25-232">Internet Explorer 8 (native mode)</span></span>  <br/> <span data-ttu-id="10e25-233">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="10e25-233">Internet Explorer 9 (native mode)</span></span>  <br/> |
|<span data-ttu-id="10e25-234">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="10e25-234">Windows Server 2012</span></span>  <br/> ||
|<span data-ttu-id="10e25-235">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="10e25-235">Windows Server 2012 R2</span></span>  <br/> ||

### <a name="response-group-agent-console"></a><span data-ttu-id="10e25-236">回應群組代理程式主控台</span><span class="sxs-lookup"><span data-stu-id="10e25-236">Response Group Agent Console</span></span>

<span data-ttu-id="10e25-237">[代理程式主控台] 支援下表所述的作業系統與網頁瀏覽器混合。</span><span class="sxs-lookup"><span data-stu-id="10e25-237">The agent console supports the combinations of operating systems and web browsers described in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="10e25-238">支援32位或64位版本的作業系統。</span><span class="sxs-lookup"><span data-stu-id="10e25-238">32-bit or 64-bit versions of the operating systems are supported.</span></span> <span data-ttu-id="10e25-239">僅支援32位版本的 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="10e25-239">Only 32-bit versions of Internet Explorer are supported.</span></span>

<span data-ttu-id="10e25-240">**支援的作業系統與網頁瀏覽器**</span><span class="sxs-lookup"><span data-stu-id="10e25-240">**Supported Operating Systems and Web Browsers**</span></span>

|<span data-ttu-id="10e25-241">**作業系統**</span><span class="sxs-lookup"><span data-stu-id="10e25-241">**Operating system**</span></span>|<span data-ttu-id="10e25-242">**網頁瀏覽器**</span><span class="sxs-lookup"><span data-stu-id="10e25-242">**Web browser**</span></span>|
|:-----|:-----|
|<span data-ttu-id="10e25-243">Windows Vista (含 Service Pack (SP) 2)</span><span class="sxs-lookup"><span data-stu-id="10e25-243">Windows Vista with Service Pack (SP) 2</span></span>  <br/> |<span data-ttu-id="10e25-244">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="10e25-244">Internet Explorer 7</span></span>  <br/> <span data-ttu-id="10e25-245">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="10e25-245">Internet Explorer 8 (native mode)</span></span>  <br/> <span data-ttu-id="10e25-246">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="10e25-246">Internet Explorer 9 (native mode)</span></span>  <br/> |
|<span data-ttu-id="10e25-247">Windows 7</span><span class="sxs-lookup"><span data-stu-id="10e25-247">Windows 7</span></span>  <br/> <span data-ttu-id="10e25-248">Windows 7 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="10e25-248">Windows 7 with Service Pack 1</span></span>  <br/> |<span data-ttu-id="10e25-249">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="10e25-249">Internet Explorer 8 (native mode)</span></span>  <br/> <span data-ttu-id="10e25-250">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="10e25-250">Internet Explorer 9 (native mode)</span></span>  <br/> <span data-ttu-id="10e25-251">Firefox 10。0</span><span class="sxs-lookup"><span data-stu-id="10e25-251">Firefox 10.0</span></span>  <br/> <span data-ttu-id="10e25-252">Chrome 18。0</span><span class="sxs-lookup"><span data-stu-id="10e25-252">Chrome 18.0</span></span>  <br/> |
|<span data-ttu-id="10e25-253">Windows Server 2008 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="10e25-253">Windows Server 2008 with Service Pack 2</span></span>  <br/> |<span data-ttu-id="10e25-254">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="10e25-254">Internet Explorer 7</span></span>  <br/> <span data-ttu-id="10e25-255">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="10e25-255">Internet Explorer 8 (native mode)</span></span>  <br/> <span data-ttu-id="10e25-256">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="10e25-256">Internet Explorer 9 (native mode)</span></span>  <br/> |
|<span data-ttu-id="10e25-257">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="10e25-257">Windows Server 2008 R2</span></span>  <br/> <span data-ttu-id="10e25-258">Windows Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="10e25-258">Windows Server 2008 R2 with Service Pack 1</span></span>  <br/> |<span data-ttu-id="10e25-259">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="10e25-259">Internet Explorer 8 (native mode)</span></span>  <br/> <span data-ttu-id="10e25-260">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="10e25-260">Internet Explorer 9 (native mode)</span></span>  <br/> <span data-ttu-id="10e25-261">Firefox 10。0</span><span class="sxs-lookup"><span data-stu-id="10e25-261">Firefox 10.0</span></span>  <br/> <span data-ttu-id="10e25-262">Chrome 18。0</span><span class="sxs-lookup"><span data-stu-id="10e25-262">Chrome 18.0</span></span>  <br/> |
|<span data-ttu-id="10e25-263">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="10e25-263">Windows Server 2012</span></span>  <br/> |
|<span data-ttu-id="10e25-264">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="10e25-264">Windows Server 2012 R2</span></span>  <br/> |

## <a name="client-support"></a><span data-ttu-id="10e25-265">用戶端支援</span><span class="sxs-lookup"><span data-stu-id="10e25-265">Client support</span></span>

<span data-ttu-id="10e25-266">回應群組應用程式支援下列用戶端:</span><span class="sxs-lookup"><span data-stu-id="10e25-266">The Response Group application supports the following clients:</span></span>

- <span data-ttu-id="10e25-267">商務用 Skype 桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="10e25-267">Skype for Business desktop client</span></span>

- <span data-ttu-id="10e25-268">Lync 2013 桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="10e25-268">Lync 2013 desktop client</span></span>

- <span data-ttu-id="10e25-269">Lync 2010 桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="10e25-269">Lync 2010 desktop client</span></span>

- <span data-ttu-id="10e25-270">Lync 2010 助理</span><span class="sxs-lookup"><span data-stu-id="10e25-270">Lync 2010 Attendant</span></span>

- <span data-ttu-id="10e25-271">Office 通訊伺服器 2007 R2 助理</span><span class="sxs-lookup"><span data-stu-id="10e25-271">Office Communications Server 2007 R2 Attendant</span></span>

- <span data-ttu-id="10e25-272">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="10e25-272">Lync Phone Edition</span></span>

> [!NOTE]
> <span data-ttu-id="10e25-273">Lync 行動用戶端不支援回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="10e25-273">The Response Group application is not supported on Lync mobile clients.</span></span>

<span data-ttu-id="10e25-274">您可以使用的特定用戶端取決於您所使用的回應群組使用者類型:</span><span class="sxs-lookup"><span data-stu-id="10e25-274">The specific client that you can use depends on the type of Response Group user that you are:</span></span>

- <span data-ttu-id="10e25-275">**呼叫**者可以使用前面所列的任何用戶端呼叫回應群組, 並使用標準電話透過公用交換電話網絡 (PSTN) 撥打電話。</span><span class="sxs-lookup"><span data-stu-id="10e25-275">**Callers** can call a response group by using any of the clients listed previously, and by using a standard telephone over the public switched telephone network (PSTN).</span></span>

- <span data-ttu-id="10e25-276">**非正式代理**程式(未登入和登出其群組以接受通話的工程師) 可以使用 [障礙]、[Lync] 或 [Lync 手機版] 接受通話。</span><span class="sxs-lookup"><span data-stu-id="10e25-276">**Informal agents** (agents who do not sign into and out of their groups to accept calls) can accept calls by using Attendant, Lync, or Lync Phone Edition.</span></span> <span data-ttu-id="10e25-277">當使用者使用下列其中一個用戶端登入商務用 Skype 伺服器時, 就會自動登入他們的群組。</span><span class="sxs-lookup"><span data-stu-id="10e25-277">Informal agents are automatically signed into their groups when they sign in to Skype for Business Server by using one of these clients.</span></span>

- <span data-ttu-id="10e25-278">**正式代理**(必須登入或登出其群組才能接受呼叫), 就可以使用商務用 Skype 和從功能表項目存取代理程式主控台來接受呼叫, 或是直接從 Internet Explorer 存取代理程式主控台。</span><span class="sxs-lookup"><span data-stu-id="10e25-278">**Formal agents** (agents who must sign into and out of their groups to accept calls) can accept calls by using Skype for Business and accessing the agent console from the menu item, or by using Attendant and accessing the agent console directly from Internet Explorer.</span></span>

## <a name="capacity-planning"></a><span data-ttu-id="10e25-279">容量規劃</span><span class="sxs-lookup"><span data-stu-id="10e25-279">Capacity planning</span></span>

<span data-ttu-id="10e25-280">下表說明您可以用來做為容量規劃需求基礎的 [回應群組] 使用者模型。</span><span class="sxs-lookup"><span data-stu-id="10e25-280">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="10e25-281">下表中的數位假設您針對所有回應群組音訊檔案使用 16 kHz、單聲道、16位波 (.wav) 檔案。</span><span class="sxs-lookup"><span data-stu-id="10e25-281">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files.</span></span> <span data-ttu-id="10e25-282">如果您使用其他檔案格式 (例如, Windows Media Audio (.wma)), 這些數位可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="10e25-282">If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="10e25-283">請記住, 對於災難復原容量規劃, 配對池的每個池都應該能夠處理兩個池中所有回應群組的工作量。</span><span class="sxs-lookup"><span data-stu-id="10e25-283">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>

<span data-ttu-id="10e25-284">**回應群組使用者模型**</span><span class="sxs-lookup"><span data-stu-id="10e25-284">**Response Group User Model**</span></span>

|<span data-ttu-id="10e25-285">**衡量**</span><span class="sxs-lookup"><span data-stu-id="10e25-285">**Metric**</span></span>|<span data-ttu-id="10e25-286">**每個企業版<br/>池 (含8個前端伺服器)**</span><span class="sxs-lookup"><span data-stu-id="10e25-286">**Per Enterprise Edition pool  <br/> (With 8 Front End Servers)**</span></span>|<span data-ttu-id="10e25-287">**每個標準版 server**</span><span class="sxs-lookup"><span data-stu-id="10e25-287">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="10e25-288">每秒來電數</span><span class="sxs-lookup"><span data-stu-id="10e25-288">Incoming calls per second</span></span>  <br/> |<span data-ttu-id="10e25-289">位</span><span class="sxs-lookup"><span data-stu-id="10e25-289">16</span></span>  <br/> |<span data-ttu-id="10e25-290">pplx-2</span><span class="sxs-lookup"><span data-stu-id="10e25-290">2</span></span>  <br/> |
|<span data-ttu-id="10e25-291">連線到 IVR 或 MoH 的並行呼叫</span><span class="sxs-lookup"><span data-stu-id="10e25-291">Concurrent calls connected to IVR or MoH</span></span>  <br/> |<span data-ttu-id="10e25-292">480</span><span class="sxs-lookup"><span data-stu-id="10e25-292">480</span></span>  <br/> |<span data-ttu-id="10e25-293">60</span><span class="sxs-lookup"><span data-stu-id="10e25-293">60</span></span>  <br/> |
|<span data-ttu-id="10e25-294">並行匿名會話 (無 IM)</span><span class="sxs-lookup"><span data-stu-id="10e25-294">Concurrent anonymous sessions (without IM)</span></span>  <br/> |<span data-ttu-id="10e25-295">224</span><span class="sxs-lookup"><span data-stu-id="10e25-295">224</span></span>  <br/> |<span data-ttu-id="10e25-296">28</span><span class="sxs-lookup"><span data-stu-id="10e25-296">28</span></span>  <br/> |
|<span data-ttu-id="10e25-297">並行匿名會話 (與 IM)</span><span class="sxs-lookup"><span data-stu-id="10e25-297">Concurrent anonymous sessions (with IM)</span></span>  <br/> |<span data-ttu-id="10e25-298">64</span><span class="sxs-lookup"><span data-stu-id="10e25-298">64</span></span>  <br/> |<span data-ttu-id="10e25-299">型</span><span class="sxs-lookup"><span data-stu-id="10e25-299">8</span></span>  <br/> |
|<span data-ttu-id="10e25-300">使用中的代理程式 (正式與非正式)</span><span class="sxs-lookup"><span data-stu-id="10e25-300">Active agents (formal and informal)</span></span>  <br/> |<span data-ttu-id="10e25-301">2400</span><span class="sxs-lookup"><span data-stu-id="10e25-301">2400</span></span>  <br/> |<span data-ttu-id="10e25-302">2400</span><span class="sxs-lookup"><span data-stu-id="10e25-302">2400</span></span>  <br/> |
|<span data-ttu-id="10e25-303">查尋群組的數目</span><span class="sxs-lookup"><span data-stu-id="10e25-303">Number of hunt groups</span></span>  <br/> |<span data-ttu-id="10e25-304">800</span><span class="sxs-lookup"><span data-stu-id="10e25-304">800</span></span>  <br/> |<span data-ttu-id="10e25-305">800</span><span class="sxs-lookup"><span data-stu-id="10e25-305">800</span></span>  <br/> |
|<span data-ttu-id="10e25-306">IVR 群組數 (使用語音辨識)</span><span class="sxs-lookup"><span data-stu-id="10e25-306">Number of IVR groups (use speech recognition)</span></span>  <br/> |<span data-ttu-id="10e25-307">400</span><span class="sxs-lookup"><span data-stu-id="10e25-307">400</span></span>  <br/> |<span data-ttu-id="10e25-308">400</span><span class="sxs-lookup"><span data-stu-id="10e25-308">400</span></span>  <br/> |


