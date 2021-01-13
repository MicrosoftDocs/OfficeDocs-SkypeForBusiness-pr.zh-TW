---
title: 在商務用 Skype Server 中規劃回應群組應用程式
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6cc333e7-4029-4372-86b2-016040c415fb
description: 在商務用 Skype Server Enterprise Voice 中規劃回應群組，可讓您設定使用者群組的呼叫路由。 包括音訊檔需求。
ms.openlocfilehash: 5abf043531079e8eef707b8cdfc4efe70f8be4bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813473"
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server"></a><span data-ttu-id="1ed8e-104">在商務用 Skype Server 中規劃回應群組應用程式</span><span class="sxs-lookup"><span data-stu-id="1ed8e-104">Plan for the Response Group application in Skype for Business Server</span></span>

<span data-ttu-id="1ed8e-105">在商務用 Skype Server Enterprise Voice 中規劃回應群組，可讓您設定使用者群組的呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-105">Planning for response groups in Skype for Business Server Enterprise Voice, which enables you to set up call routing to groups of users.</span></span> <span data-ttu-id="1ed8e-106">包括音訊檔需求。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-106">Includes audio file requirements.</span></span>

<span data-ttu-id="1ed8e-107">如果您的組織擁有接聽和管理特定通話類型的人員群組，例如，針對客戶服務、內部服務台或部門的一般電話支援，您可以部署回應群組應用程式來管理這些通話類型。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-107">If your organization has groups of people who answer and manage certain types of calls, such as for customer service, an internal help desk, or general telephone support for a department, you can deploy the Response Group application to manage these types of calls.</span></span> <span data-ttu-id="1ed8e-108">回應群組應用程式會將來電路由和佇列傳送給指定的人員（稱為代理人）。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-108">The Response Group application routes and queues incoming calls to designated persons, who are known as agents.</span></span> <span data-ttu-id="1ed8e-109">藉由使用回應群組，您可以增加電話支援服務的使用頻率，並減少為執行這些服務所產生的負荷。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-109">You can increase the use of telephone support services and reduce the overhead of running these services by using response groups.</span></span>

<span data-ttu-id="1ed8e-110">來電者與回應群組通話時，該通話會根據群組搜尋或來電者對互動語音回應 (IVR) 問題的回答，路由傳送給代理人。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-110">When a caller calls a response group, the call is routed to an agent based on a hunt group or the caller's answers to interactive voice response (IVR) questions.</span></span> <span data-ttu-id="1ed8e-111">回應群組應用程式會使用標準回應群組路由方法，將通話路由傳送至下一個可用的代理程式。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-111">The Response Group application uses standard response group routing methods to route the call to the next available agent.</span></span> <span data-ttu-id="1ed8e-112">支援的呼叫路由方法包括串列、最長閒置、平行、迴圈和接聽路由 (也就是說，不論其目前狀態為何，所有的代理程式都會同時呼叫給每一個來電) 。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-112">Supported call routing methods include serial, longest-idle, parallel, round robin, and Attendant routing (that is, all agents are called at the same time for every incoming call, regardless of their current presence).</span></span>

<span data-ttu-id="1ed8e-113">如果沒有代理人有空，則會將通話保留在佇列中，直到某位代理人有空。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-113">If no agents are available, the call is held in a queue until an agent is available.</span></span> <span data-ttu-id="1ed8e-114">通話保留在佇列時，來電者會聽到音樂，直到某位有空的代理人受理該通話。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-114">While in the queue, the caller hears music until an available agent accepts the call.</span></span> <span data-ttu-id="1ed8e-115">若佇列已滿，或是佇列中的呼叫超時，來電者可能會聽到訊息，然後中斷連線或轉接至不同的目的地，例如不同的電話號碼或語音信箱。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-115">If the queue is full, or if the call times out while in the queue, the caller might hear a message and then is either disconnected or transferred to a different destination, such as a different phone number or voicemail.</span></span> <span data-ttu-id="1ed8e-116">依系統管理員設定回應群組的方式不同，代理人受理通話時，來電者不一定會看到代理人的身分識別。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-116">When an agent accepts the call, the caller might or might not be able to see the agent's identity, depending on how the administrator configures the response group.</span></span> <span data-ttu-id="1ed8e-117">代理人得以正式方式受理通話 (表示他們必須先登入群組，才能受理路由傳送給群組的通話)，或以非正式方式受理通話 (表示他們未登入及登出群組就受理通話)。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-117">Agents can either be formal, which means that they must sign in to the group before they can accept calls routed to the group, or informal, which means that they do not sign into and out of the group to accept calls.</span></span>

> [!NOTE]
> <span data-ttu-id="1ed8e-p106">只有內部部署的使用者可以成為代理人。如果將代理人從內部部署移至線上，回應群組電話將無法路由傳送給該代理人。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-p106">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>

> [!NOTE]
> <span data-ttu-id="1ed8e-120">回應群組應用程式使用稱為「符合」的內部服務，以佇列通話並尋找可用的代理程式。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-120">The Response Group application uses an internal service, called Match Making, to queue calls and find available agents.</span></span> <span data-ttu-id="1ed8e-121">每一部執行回應群組應用程式的電腦都會執行相符服務，但是一次只能有一個符合每個集區的服務--另一個是被動。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-121">Each computer that runs the Response Group application runs the Match Making service, but only one Match Making service per pool is active at a time--the others are passive.</span></span> <span data-ttu-id="1ed8e-122">如果主動配對服務在意外中斷服務期間無法使用，則被動配對服務其中之一會變成主動配對服務。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-122">If the active Match Making service becomes unavailable during an unplanned outage, one of the passive Match Making services becomes active.</span></span> <span data-ttu-id="1ed8e-123">回應群組應用程式會盡力確保通話路由和佇列繼續不間斷地繼續進行。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-123">The Response Group application does its best to make sure that call routing and queuing continues uninterrupted.</span></span> <span data-ttu-id="1ed8e-124">但是在轉換配對服務時，所有轉接中的通話都會中斷。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-124">However, when a Match Making service transition occurs, any calls that are in transfer at the time are lost.</span></span> <span data-ttu-id="1ed8e-125">例如，如果轉換是由於前端伺服器即將停機，則目前正由使用中的相符服務所處理的所有呼叫都會遺失該前端伺服器上的服務。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-125">For example, if the transition is due to the Front End Server going down, any calls currently being handled by the active Match Making service on that Front End Server are also lost.</span></span>

## <a name="response-group-workflows"></a><span data-ttu-id="1ed8e-126">回應群組工作流程</span><span class="sxs-lookup"><span data-stu-id="1ed8e-126">Response group workflows</span></span>

<span data-ttu-id="1ed8e-p108">工作流程會定義從電話鈴聲開始響起到有人接聽該通電話這段時間的呼叫行為。工作流程指定了用於保留通話的佇列，並指定用於群組搜尋的路由方法，或讓互動回應群組使用的問題和回答。工作流程也定義歡迎訊息、等候音樂、上班時間和假日之類的設定值。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-p108">A workflow defines the behavior of a call from the time that the phone rings to the time that someone answers the call. The workflow specifies the queue to use for holding the call, and specifies the routing method to use for hunt groups or the questions and answers to use for interactive response groups. A workflow also defines settings such as a welcome message, music on hold, business hours, and holidays.</span></span>

> [!NOTE]
> <span data-ttu-id="1ed8e-130">您必須先建立代理群組和佇列，再建立使用這些項目的工作流程。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-130">You must create agent groups and queues before you create a workflow that uses them.</span></span>

## <a name="management-of-response-groups"></a><span data-ttu-id="1ed8e-131">管理回應群組</span><span class="sxs-lookup"><span data-stu-id="1ed8e-131">Management of response groups</span></span>

<span data-ttu-id="1ed8e-132">在商務用 Skype Server 中，有兩個管理角色可用於管理回應群組：回應群組管理員和回應群組管理員。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-132">In Skype for Business Server, two management roles are available for managing response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="1ed8e-133">回應群組管理員可以管理任何回應群組的任何方面。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-133">Response Group Administrators can manage any aspect of any response group.</span></span> <span data-ttu-id="1ed8e-134">回應群組管理員只可管理特定的部分，而且只可管理其擁有的回應群組。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-134">Response Group Managers can manage only certain aspects, and only for the response groups that they own.</span></span> <span data-ttu-id="1ed8e-135">管理員角色可協助您降低管理成本，因為您可以將特定回應群組的有限責任委派給已啟用 Enterprise Voice 的任何使用者。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-135">The Manager role can help you reduce your administration costs, because you can delegate limited responsibilities for specific response groups to any user who is enabled for Enterprise Voice.</span></span> <span data-ttu-id="1ed8e-136">請注意，使用者可以是回應群組管理員和回應群組管理員。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-136">Note that a user can be both a Response Group Manager and a Response Group Administrator.</span></span>

<span data-ttu-id="1ed8e-137">為了容納管理員角色，回應群組應用程式使用 Managed 或未受管理的 **工作流程類型** 。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-137">To accommodate the Manager role, Response Group application uses a **Workflow Type** of Managed or Unmanaged.</span></span> <span data-ttu-id="1ed8e-138">下表描述「已受管理」與「未受管理」回應群組內容。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-138">The following table describes Managed and Unmanaged response groups.</span></span>

<span data-ttu-id="1ed8e-139">**受管理與未受管理回應群組**</span><span class="sxs-lookup"><span data-stu-id="1ed8e-139">**Managed and Unmanaged Response Groups**</span></span>

|<span data-ttu-id="1ed8e-140">**回應群組類型**</span><span class="sxs-lookup"><span data-stu-id="1ed8e-140">**Response group type**</span></span>|<span data-ttu-id="1ed8e-141">**描述**</span><span class="sxs-lookup"><span data-stu-id="1ed8e-141">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1ed8e-142">非 託管</span><span class="sxs-lookup"><span data-stu-id="1ed8e-142">Unmanaged</span></span>  <br/> | <span data-ttu-id="1ed8e-143">未受管理的回應群組沒有指定的管理員。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-143">Unmanaged response groups have no assigned Managers.</span></span> <span data-ttu-id="1ed8e-144">只有回應群組管理員可以設定這些回應群組。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-144">Only the Response Group Administrator can configure these response groups.</span></span> <br/>  <span data-ttu-id="1ed8e-145">多個未受管理回應群組可共用一個佇列或代理人群組。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-145">Multiple unmanaged response groups can share a queue or agent group.</span></span> <br/>  <span data-ttu-id="1ed8e-146">當您從先前版本向商務用 Skype Server 遷移回應群組時，該類型會設定為 [未管理]。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-146">When you migrate response groups from a prior version to Skype for Business Server, the type is set to Unmanaged.</span></span> <br/> |
|<span data-ttu-id="1ed8e-147">受管理</span><span class="sxs-lookup"><span data-stu-id="1ed8e-147">Managed</span></span>  <br/> | <span data-ttu-id="1ed8e-148">回應群組管理員可以設定受管理回應群組的任何方面。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-148">Response Group Administrators can configure any aspect of managed response groups.</span></span> <br/>  <span data-ttu-id="1ed8e-149">回應群組管理員無法查看或修改未明確指派給他們的回應群組。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-149">Response Group Managers cannot view or modify response groups that are not explicitly assigned to them.</span></span> <br/>  <span data-ttu-id="1ed8e-150">回應群組管理員可以只為明確指派給他們的回應群組設定部分設定。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-150">Response Group Managers can configure only some settings for the response groups that are explicitly assigned to them.</span></span> <br/>  <span data-ttu-id="1ed8e-151">受管理的回應群組無法與其他任何受管理或未受管理的回應群組共用任何佇列或代理人群組。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-151">Managed response groups can't share any queues or agent groups with any other response group, managed or unmanaged.</span></span> <br/> |

<span data-ttu-id="1ed8e-152">下表說明回應群組管理員可對指派給他們的回應群組執行和無法執行的動作。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-152">The following table describes the actions that Response Group Managers can and cannot perform for the response groups assigned to them.</span></span>

<span data-ttu-id="1ed8e-153">**回應群組管理員功能**</span><span class="sxs-lookup"><span data-stu-id="1ed8e-153">**Response Group Manager Capabilities**</span></span>

|<span data-ttu-id="1ed8e-154">**可設定：**</span><span class="sxs-lookup"><span data-stu-id="1ed8e-154">**Can configure:**</span></span>|<span data-ttu-id="1ed8e-155">**可建立、刪除或設定：**</span><span class="sxs-lookup"><span data-stu-id="1ed8e-155">**Can create, delete, or configure:**</span></span>|<span data-ttu-id="1ed8e-156">**不能：**</span><span class="sxs-lookup"><span data-stu-id="1ed8e-156">**Cannot:**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="1ed8e-157">Agents</span><span class="sxs-lookup"><span data-stu-id="1ed8e-157">Agents</span></span> <br/>  <span data-ttu-id="1ed8e-158">歡迎訊息</span><span class="sxs-lookup"><span data-stu-id="1ed8e-158">Welcome message</span></span> <br/>  <span data-ttu-id="1ed8e-159">回應群組名稱</span><span class="sxs-lookup"><span data-stu-id="1ed8e-159">Response Group name</span></span> <br/>  <span data-ttu-id="1ed8e-160">描述</span><span class="sxs-lookup"><span data-stu-id="1ed8e-160">Description</span></span> <br/>  <span data-ttu-id="1ed8e-161">顯示號碼</span><span class="sxs-lookup"><span data-stu-id="1ed8e-161">Display number</span></span> <br/>  <span data-ttu-id="1ed8e-162">營業時間</span><span class="sxs-lookup"><span data-stu-id="1ed8e-162">Business hours</span></span> <br/>  <span data-ttu-id="1ed8e-163">保留音樂</span><span class="sxs-lookup"><span data-stu-id="1ed8e-163">Music on hold</span></span> <br/>  <span data-ttu-id="1ed8e-164">狀態 (使用中/非使用中)</span><span class="sxs-lookup"><span data-stu-id="1ed8e-164">Status (active/inactive)</span></span> <br/>  <span data-ttu-id="1ed8e-165">群組搜尋工作流程或互動語音回應 (IVR) 工作流程</span><span class="sxs-lookup"><span data-stu-id="1ed8e-165">Hunt group workflows or Interactive voice response (IVR) workflows</span></span> <br/> | <span data-ttu-id="1ed8e-166">代理人群組</span><span class="sxs-lookup"><span data-stu-id="1ed8e-166">Agent Groups</span></span> <br/>  <span data-ttu-id="1ed8e-167">佇列</span><span class="sxs-lookup"><span data-stu-id="1ed8e-167">Queues</span></span> <br/>  <span data-ttu-id="1ed8e-168">假日集</span><span class="sxs-lookup"><span data-stu-id="1ed8e-168">Holiday sets</span></span> <br/> | <span data-ttu-id="1ed8e-169">建立或刪除任何工作流程類型</span><span class="sxs-lookup"><span data-stu-id="1ed8e-169">Create or delete any type of workflow</span></span> <br/>  <span data-ttu-id="1ed8e-170">修改核心回應群組設定，例如：**[SIP URI]**、**[電話號碼]** 或 **[工作流程類型]**。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-170">Modify core response group settings, such as: **SIP URI**, **Telephone Number**, or **Workflow Type**.</span></span>  <br/> |

<span data-ttu-id="1ed8e-171">回應群組管理員可使用下列工具來管理其指定的回應群組。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-171">Response Group Managers can use the following tools to manage their designated response groups.</span></span>

- <span data-ttu-id="1ed8e-172">商務用 Skype Server 控制台</span><span class="sxs-lookup"><span data-stu-id="1ed8e-172">Skype for Business Server Control Panel</span></span>

    > [!NOTE]
    > <span data-ttu-id="1ed8e-173">回應群組管理員只能使用此工具來管理回應群組設定。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-173">Response Group Managers can only manage Response Group settings with this tool.</span></span> <span data-ttu-id="1ed8e-174">管理員無法使用其他商務用 Skype Server 設定。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-174">Other Skype for Business Server settings are not available to Managers.</span></span>

- <span data-ttu-id="1ed8e-175">回應群組設定工具</span><span class="sxs-lookup"><span data-stu-id="1ed8e-175">Response Group Configuration Tool</span></span>

- <span data-ttu-id="1ed8e-176">商務用 Skype Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="1ed8e-176">Skype for Business Server Management Shell</span></span>

<span data-ttu-id="1ed8e-177">回應群組可非常適合部門或工作組環境 (如需詳細資訊，請參閱 [容量規劃，以進行回應群組](https://technet.microsoft.com/library/a2459a69-1f45-4f2f-bca5-d4f442708e44.aspx)) ，而且可以部署于全新的電話語音安裝中。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-177">Response Group scales well to departmental or workgroup environments (for details, see [Capacity Planning for Response Group](https://technet.microsoft.com/library/a2459a69-1f45-4f2f-bca5-d4f442708e44.aspx)) and can be deployed in entirely new telephony installations.</span></span> <span data-ttu-id="1ed8e-178">它支援來自 Enterprise Voice 部署和本機電信公司網路的撥入電話。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-178">It supports incoming calls from the Enterprise Voice deployment and from the local carrier network.</span></span> <span data-ttu-id="1ed8e-179">代理程式可以使用商務用 Skype、Lync 2013、Lync 2010、Lync 2010 語音應答或 Lync Phone Edition，將通話路由傳送給他們。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-179">Agents can use Skype for Business, Lync 2013, Lync 2010, Lync 2010 Attendant, or Lync Phone Edition to take the calls routed to them.</span></span>

## <a name="deployment-and-requirements"></a><span data-ttu-id="1ed8e-180">部署和需求</span><span class="sxs-lookup"><span data-stu-id="1ed8e-180">Deployment and requirements</span></span>

<span data-ttu-id="1ed8e-181">當您部署企業語音時，回應群組應用程式會自動啟用。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-181">The Response Group application is automatically enabled when you deploy Enterprise Voice.</span></span>

### <a name="hardware-and-software-requirements"></a><span data-ttu-id="1ed8e-182">硬體及軟體需求</span><span class="sxs-lookup"><span data-stu-id="1ed8e-182">Hardware and software requirements</span></span>

<span data-ttu-id="1ed8e-183">回應群組應用程式與前端伺服器具有相同的硬體需求、作業系統需求和軟體必要條件。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-183">The Response Group application has the same hardware requirements, operating system requirements and software prerequisites as Front End Servers.</span></span>

<span data-ttu-id="1ed8e-184">如果您使用 Windows Media Audio () 的回應群組音樂和宣告的檔案，所有執行回應群組應用程式的前端伺服器或 Standard Edition 伺服器，都必須針對執行 windows server 2008 R2 的伺服器及 Microsoft Media Foundation （執行 Windows Server 2012 或 Windows Server 2012 R2 的伺服器）安裝 Windows Media Format Runtime。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-184">If you use Windows Media Audio (.wma) files for Response Group music and announcements, all Front End Servers or Standard Editions servers that run the Response Group application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="1ed8e-185">若為 Windows Server 2008 R2，Windows Media Format Runtime 會安裝為 Windows 桌面體驗的一部分。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-185">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span>

<span data-ttu-id="1ed8e-186">回應群組使用 **語言套件** 來支援文字語音語音及語音辨識。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-186">Response Group uses **Language packs** to support text-to-speech and speech recognition.</span></span> <span data-ttu-id="1ed8e-187">在您設定訊息 (如歡迎訊息與其他提示) 以及互動式語音回應 (IVR) 的問題與回答時，都會用到這些語音技術。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-187">These speech technologies are used when you configure messages, such as the welcome message and other prompts, and interactive voice response (IVR) questions and answers.</span></span> <span data-ttu-id="1ed8e-188">根據預設，當您部署商務用 Skype Server 時，會安裝26個支援的語言套件。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-188">By default, the 26 supported language packs are installed when you deploy Skype for Business Server.</span></span>

### <a name="port-requirements"></a><span data-ttu-id="1ed8e-189">連接埠需求</span><span class="sxs-lookup"><span data-stu-id="1ed8e-189">Port Requirements</span></span>

<span data-ttu-id="1ed8e-190">回應群組應用程式使用下列埠：</span><span class="sxs-lookup"><span data-stu-id="1ed8e-190">The Response Group application uses the following ports:</span></span>

- <span data-ttu-id="1ed8e-191">用於 SIP 聆聽要求的 **埠 5071**</span><span class="sxs-lookup"><span data-stu-id="1ed8e-191">**Port 5071**   for SIP listening requests</span></span>

- <span data-ttu-id="1ed8e-192">用於伺服器間通訊的 **埠 8404**</span><span class="sxs-lookup"><span data-stu-id="1ed8e-192">**Port 8404**   for interserver communications</span></span>

    > [!NOTE]
    > <span data-ttu-id="1ed8e-193">此埠用於配對服務，且在具有多部前端伺服器的集區中部署回應群組應用程式時是必要的。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-193">This port is used for the Match Making service and is required when the Response Group application is deployed in a pool that has more than one Front End Server.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1ed8e-194">這些連接埠為預設設定，可使用 **Set-CsApplicationServer** Cmdlet 予以變更。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-194">These ports are default settings that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="1ed8e-195">如需此 Cmdlet 的詳細資訊，請參閱商務用 Skype Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-195">For details about this cmdlet, see the Skype for Business Server Management Shell documentation.</span></span>

### <a name="audio-file-requirements"></a><span data-ttu-id="1ed8e-196">音訊檔案需求</span><span class="sxs-lookup"><span data-stu-id="1ed8e-196">Audio File Requirements</span></span>

<span data-ttu-id="1ed8e-197">回應群組應用程式支援波形 ( wav) 檔案格式和 Windows Media 音訊 ( 回應群組訊息、等候音樂或互動語音回應的檔案格式) 。 (IVR) 問題。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-197">The Response Group application supports wave (.wav) file format and Windows Media audio (.wma) file format for Response Group messages, on-hold music, or interactive voice response (IVR) questions.</span></span>

<span data-ttu-id="1ed8e-198">Windows Media 音訊檔案格式要求 Windows Media Format Runtime 已安裝在執行 Windows Server 2008 R2 和 Windows Server 2008 的前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-198">The Windows Media audio file format requires that the Windows Media Format Runtime is installed on Front End Servers running Windows Server 2008 R2 and Windows Server 2008.</span></span> <span data-ttu-id="1ed8e-199">如需詳細資訊，請參閱本節稍早的＜軟體需求＞。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-199">For more details, see "Software Requirements" earlier in this section.</span></span>

#### <a name="supported-wave-file-formats"></a><span data-ttu-id="1ed8e-200">支援的 Wave 檔案格式</span><span class="sxs-lookup"><span data-stu-id="1ed8e-200">Supported Wave File Formats</span></span>

<span data-ttu-id="1ed8e-201">所有 Wave 檔案必須符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="1ed8e-201">All wave files must meet the following requirements:</span></span>

- <span data-ttu-id="1ed8e-202">8 位元或 16 位元檔案</span><span class="sxs-lookup"><span data-stu-id="1ed8e-202">8-bit or 16-bit file</span></span>

- <span data-ttu-id="1ed8e-203">線性脈衝代碼調變 (LPCM)，A-Law 或 mu-Law 格式</span><span class="sxs-lookup"><span data-stu-id="1ed8e-203">Linear pulse code modulation (LPCM), A-Law, or mu-Law format</span></span>

- <span data-ttu-id="1ed8e-204">單音或立體聲</span><span class="sxs-lookup"><span data-stu-id="1ed8e-204">Mono or stereo</span></span>

- <span data-ttu-id="1ed8e-205">4MB 以下</span><span class="sxs-lookup"><span data-stu-id="1ed8e-205">4MB or less</span></span>

<span data-ttu-id="1ed8e-206">為使 Wave 檔案有最佳表現，建議使用 16 kHz 單音的 16 位元 Wave 檔案。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-206">For the best performance of wave files, a 16 kHz, mono, 16-bit Wave file is recommended.</span></span>

#### <a name="supported-windows-media-audio-file-formats"></a><span data-ttu-id="1ed8e-207">支援的 Windows Media 音訊檔案格式</span><span class="sxs-lookup"><span data-stu-id="1ed8e-207">Supported Windows Media Audio File Formats</span></span>

<span data-ttu-id="1ed8e-208">如果您使用 Windows Media 音訊檔案，請考慮使用低位元速率，並驗證系統承受負載時的效能。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-208">If you use a Windows Media audio file, consider using low bit rates, and verify the performance of your system under load.</span></span>

<span data-ttu-id="1ed8e-209">您可以使用 Microsoft Expression Encoder 4 將檔案轉換成 Windows Media Audio 格式。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-209">You can use the Microsoft Expression Encoder 4 to convert a file to the Windows Media Audio format.</span></span> <span data-ttu-id="1ed8e-210">若要下載運算式編碼器4，請參閱 [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843) 。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-210">To download Expression Encoder 4, see [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843).</span></span>

### <a name="response-group-configuration-tool-requirements"></a><span data-ttu-id="1ed8e-211">回應群組設定工具需求</span><span class="sxs-lookup"><span data-stu-id="1ed8e-211">Response Group Configuration Tool Requirements</span></span>

<span data-ttu-id="1ed8e-212">回應群組設定工具支援下表所述之作業系統和網頁瀏覽器的組合。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-212">The Response Group Configuration Tool supports the combinations of operating systems and web browsers described in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="1ed8e-213">支援 32 位元或 64 位元版本的作業系統。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-213">32-bit or 64-bit versions of the operating systems are supported.</span></span> <span data-ttu-id="1ed8e-214">只支援 32 位元版本的 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-214">Only 32-bit versions of Internet Explorer are supported.</span></span>

<span data-ttu-id="1ed8e-215">**支援的作業系統和網頁瀏覽器**</span><span class="sxs-lookup"><span data-stu-id="1ed8e-215">**Supported Operating Systems and Web Browsers**</span></span>

|<span data-ttu-id="1ed8e-216">**作業系統**</span><span class="sxs-lookup"><span data-stu-id="1ed8e-216">**Operating system**</span></span>|<span data-ttu-id="1ed8e-217">**網頁瀏覽器**</span><span class="sxs-lookup"><span data-stu-id="1ed8e-217">**Web browser**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1ed8e-218">Windows Vista Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="1ed8e-218">Windows Vista with Service Pack (SP) 2</span></span>  <br/> |<span data-ttu-id="1ed8e-219">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="1ed8e-219">Internet Explorer 7</span></span>  <br/> <span data-ttu-id="1ed8e-220">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="1ed8e-220">Internet Explorer 8 (native mode)</span></span>  <br/> <span data-ttu-id="1ed8e-221">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="1ed8e-221">Internet Explorer 9 (native mode)</span></span>  <br/> |
|<span data-ttu-id="1ed8e-222">Windows 7</span><span class="sxs-lookup"><span data-stu-id="1ed8e-222">Windows 7</span></span>  <br/> <span data-ttu-id="1ed8e-223">Windows 7 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="1ed8e-223">Windows 7 with Service Pack 1</span></span>  <br/> |<span data-ttu-id="1ed8e-224">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="1ed8e-224">Internet Explorer 8 (native mode)</span></span>  <br/> <span data-ttu-id="1ed8e-225">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="1ed8e-225">Internet Explorer 9 (native mode)</span></span>  <br/> |
|<span data-ttu-id="1ed8e-226">Windows Server 2008 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="1ed8e-226">Windows Server 2008 with Service Pack 2</span></span>  <br/> |<span data-ttu-id="1ed8e-227">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="1ed8e-227">Internet Explorer 7</span></span>  <br/> <span data-ttu-id="1ed8e-228">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="1ed8e-228">Internet Explorer 8 (native mode)</span></span>  <br/> <span data-ttu-id="1ed8e-229">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="1ed8e-229">Internet Explorer 9 (native mode)</span></span>  <br/> |
|<span data-ttu-id="1ed8e-230">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="1ed8e-230">Windows Server 2008 R2</span></span>  <br/> <span data-ttu-id="1ed8e-231">Windows Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="1ed8e-231">Windows Server 2008 R2 with Service Pack 1</span></span>  <br/> |<span data-ttu-id="1ed8e-232">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="1ed8e-232">Internet Explorer 8 (native mode)</span></span>  <br/> <span data-ttu-id="1ed8e-233">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="1ed8e-233">Internet Explorer 9 (native mode)</span></span>  <br/> |
|<span data-ttu-id="1ed8e-234">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="1ed8e-234">Windows Server 2012</span></span>  <br/> ||
|<span data-ttu-id="1ed8e-235">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="1ed8e-235">Windows Server 2012 R2</span></span>  <br/> ||

### <a name="response-group-agent-console"></a><span data-ttu-id="1ed8e-236">回應群組代理程式主控台</span><span class="sxs-lookup"><span data-stu-id="1ed8e-236">Response Group Agent Console</span></span>

<span data-ttu-id="1ed8e-237">代理程式主控台支援下表中所述之作業系統和網頁瀏覽器的組合。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-237">The agent console supports the combinations of operating systems and web browsers described in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="1ed8e-p120">支援 32 位元或 64 位元版本的作業系統。只支援 32 位元版本的 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-p120">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>

<span data-ttu-id="1ed8e-240">**支援的作業系統和網頁瀏覽器**</span><span class="sxs-lookup"><span data-stu-id="1ed8e-240">**Supported Operating Systems and Web Browsers**</span></span>

|<span data-ttu-id="1ed8e-241">**作業系統**</span><span class="sxs-lookup"><span data-stu-id="1ed8e-241">**Operating system**</span></span>|<span data-ttu-id="1ed8e-242">**網頁瀏覽器**</span><span class="sxs-lookup"><span data-stu-id="1ed8e-242">**Web browser**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1ed8e-243">Windows Vista Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="1ed8e-243">Windows Vista with Service Pack (SP) 2</span></span>  <br/> |<span data-ttu-id="1ed8e-244">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="1ed8e-244">Internet Explorer 7</span></span>  <br/> <span data-ttu-id="1ed8e-245">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="1ed8e-245">Internet Explorer 8 (native mode)</span></span>  <br/> <span data-ttu-id="1ed8e-246">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="1ed8e-246">Internet Explorer 9 (native mode)</span></span>  <br/> |
|<span data-ttu-id="1ed8e-247">Windows 7</span><span class="sxs-lookup"><span data-stu-id="1ed8e-247">Windows 7</span></span>  <br/> <span data-ttu-id="1ed8e-248">Windows 7 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="1ed8e-248">Windows 7 with Service Pack 1</span></span>  <br/> |<span data-ttu-id="1ed8e-249">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="1ed8e-249">Internet Explorer 8 (native mode)</span></span>  <br/> <span data-ttu-id="1ed8e-250">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="1ed8e-250">Internet Explorer 9 (native mode)</span></span>  <br/> <span data-ttu-id="1ed8e-251">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="1ed8e-251">Firefox 10.0</span></span>  <br/> <span data-ttu-id="1ed8e-252">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="1ed8e-252">Chrome 18.0</span></span>  <br/> |
|<span data-ttu-id="1ed8e-253">Windows Server 2008 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="1ed8e-253">Windows Server 2008 with Service Pack 2</span></span>  <br/> |<span data-ttu-id="1ed8e-254">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="1ed8e-254">Internet Explorer 7</span></span>  <br/> <span data-ttu-id="1ed8e-255">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="1ed8e-255">Internet Explorer 8 (native mode)</span></span>  <br/> <span data-ttu-id="1ed8e-256">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="1ed8e-256">Internet Explorer 9 (native mode)</span></span>  <br/> |
|<span data-ttu-id="1ed8e-257">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="1ed8e-257">Windows Server 2008 R2</span></span>  <br/> <span data-ttu-id="1ed8e-258">Windows Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="1ed8e-258">Windows Server 2008 R2 with Service Pack 1</span></span>  <br/> |<span data-ttu-id="1ed8e-259">Internet Explorer 8 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="1ed8e-259">Internet Explorer 8 (native mode)</span></span>  <br/> <span data-ttu-id="1ed8e-260">Internet Explorer 9 (原生模式)</span><span class="sxs-lookup"><span data-stu-id="1ed8e-260">Internet Explorer 9 (native mode)</span></span>  <br/> <span data-ttu-id="1ed8e-261">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="1ed8e-261">Firefox 10.0</span></span>  <br/> <span data-ttu-id="1ed8e-262">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="1ed8e-262">Chrome 18.0</span></span>  <br/> |
|<span data-ttu-id="1ed8e-263">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="1ed8e-263">Windows Server 2012</span></span>  <br/> |
|<span data-ttu-id="1ed8e-264">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="1ed8e-264">Windows Server 2012 R2</span></span>  <br/> |

## <a name="client-support"></a><span data-ttu-id="1ed8e-265">用戶端支援</span><span class="sxs-lookup"><span data-stu-id="1ed8e-265">Client support</span></span>

<span data-ttu-id="1ed8e-266">回應群組應用程式支援下列用戶端：</span><span class="sxs-lookup"><span data-stu-id="1ed8e-266">The Response Group application supports the following clients:</span></span>

- <span data-ttu-id="1ed8e-267">商務用 Skype 桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="1ed8e-267">Skype for Business desktop client</span></span>

- <span data-ttu-id="1ed8e-268">Lync 2013 桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="1ed8e-268">Lync 2013 desktop client</span></span>

- <span data-ttu-id="1ed8e-269">Lync 2010 桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="1ed8e-269">Lync 2010 desktop client</span></span>

- <span data-ttu-id="1ed8e-270">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="1ed8e-270">Lync 2010 Attendant</span></span>

- <span data-ttu-id="1ed8e-271">Office 通訊伺服器 2007 R2 語音應答</span><span class="sxs-lookup"><span data-stu-id="1ed8e-271">Office Communications Server 2007 R2 Attendant</span></span>

- <span data-ttu-id="1ed8e-272">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="1ed8e-272">Lync Phone Edition</span></span>

> [!NOTE]
> <span data-ttu-id="1ed8e-273">Lync mobile 用戶端不支援回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-273">The Response Group application is not supported on Lync mobile clients.</span></span>

<span data-ttu-id="1ed8e-274">您可以使用的特定用戶端取決於您所使用的回應群組使用者類型：</span><span class="sxs-lookup"><span data-stu-id="1ed8e-274">The specific client that you can use depends on the type of Response Group user that you are:</span></span>

- <span data-ttu-id="1ed8e-275">來電 **者可以使用** 之前所列的任何用戶端，以及透過公用交換電話網路 (PSTN) 中的標準電話，撥打回應群組。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-275">**Callers** can call a response group by using any of the clients listed previously, and by using a standard telephone over the public switched telephone network (PSTN).</span></span>

- <span data-ttu-id="1ed8e-276">不會登入和登出其群組以接受來電的 **非正式代理** (，) 可以使用語音應答、Lync 或 Lync Phone Edition 接受通話。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-276">**Informal agents** (agents who do not sign into and out of their groups to accept calls) can accept calls by using Attendant, Lync, or Lync Phone Edition.</span></span> <span data-ttu-id="1ed8e-277">非正式代理程式會在使用者使用其中一位用戶端登入商務用 Skype Server 時，自動登入他們的群組。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-277">Informal agents are automatically signed into their groups when they sign in to Skype for Business Server by using one of these clients.</span></span>

- <span data-ttu-id="1ed8e-278">必須用來登入和登出其群組的 **正式代理** (，以接受來電) 可以使用商務用 Skype 來接受通話，並從功能表項目存取代理程式主控台，或是使用語音應答直接從 Internet Explorer 存取代理程式主控台。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-278">**Formal agents** (agents who must sign into and out of their groups to accept calls) can accept calls by using Skype for Business and accessing the agent console from the menu item, or by using Attendant and accessing the agent console directly from Internet Explorer.</span></span>

## <a name="capacity-planning"></a><span data-ttu-id="1ed8e-279">容量規劃</span><span class="sxs-lookup"><span data-stu-id="1ed8e-279">Capacity planning</span></span>

<span data-ttu-id="1ed8e-280">下表說明您可以用來作為容量規劃需求之基礎的回應群組使用者模型。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-280">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="1ed8e-281">下表中的數位是假設您使用 16 kHz、mono、16位 ( 波形) 所有回應群組音訊檔案的檔案。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-281">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files.</span></span> <span data-ttu-id="1ed8e-282">如果您使用其他檔案格式，例如 Windows Media Audio ( .wma) ，這些數位可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-282">If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ed8e-283">請記住，針對嚴重損壞修復容量規劃，配對集區的每個集區都應該可以處理兩個集區中所有回應群組的工作量。</span><span class="sxs-lookup"><span data-stu-id="1ed8e-283">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>

<span data-ttu-id="1ed8e-284">**回應群組使用者模型**</span><span class="sxs-lookup"><span data-stu-id="1ed8e-284">**Response Group User Model**</span></span>

|<span data-ttu-id="1ed8e-285">**計量**</span><span class="sxs-lookup"><span data-stu-id="1ed8e-285">**Metric**</span></span>|<span data-ttu-id="1ed8e-286">**每個 Enterprise Edition 集區  <br/> (，含8部前端伺服器)**</span><span class="sxs-lookup"><span data-stu-id="1ed8e-286">**Per Enterprise Edition pool  <br/> (With 8 Front End Servers)**</span></span>|<span data-ttu-id="1ed8e-287">**每個 Standard Edition server**</span><span class="sxs-lookup"><span data-stu-id="1ed8e-287">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1ed8e-288">每秒來電數</span><span class="sxs-lookup"><span data-stu-id="1ed8e-288">Incoming calls per second</span></span>  <br/> |<span data-ttu-id="1ed8e-289">16 </span><span class="sxs-lookup"><span data-stu-id="1ed8e-289">16</span></span>  <br/> |<span data-ttu-id="1ed8e-290">2 </span><span class="sxs-lookup"><span data-stu-id="1ed8e-290">2</span></span>  <br/> |
|<span data-ttu-id="1ed8e-291">連線至 IVR 或 MoH 的並行通話</span><span class="sxs-lookup"><span data-stu-id="1ed8e-291">Concurrent calls connected to IVR or MoH</span></span>  <br/> |<span data-ttu-id="1ed8e-292">480</span><span class="sxs-lookup"><span data-stu-id="1ed8e-292">480</span></span>  <br/> |<span data-ttu-id="1ed8e-293">60</span><span class="sxs-lookup"><span data-stu-id="1ed8e-293">60</span></span>  <br/> |
|<span data-ttu-id="1ed8e-294"> (沒有 IM) 的併發匿名會話</span><span class="sxs-lookup"><span data-stu-id="1ed8e-294">Concurrent anonymous sessions (without IM)</span></span>  <br/> |<span data-ttu-id="1ed8e-295">224</span><span class="sxs-lookup"><span data-stu-id="1ed8e-295">224</span></span>  <br/> |<span data-ttu-id="1ed8e-296">日</span><span class="sxs-lookup"><span data-stu-id="1ed8e-296">28</span></span>  <br/> |
|<span data-ttu-id="1ed8e-297">使用 IM)  (同時匿名會話</span><span class="sxs-lookup"><span data-stu-id="1ed8e-297">Concurrent anonymous sessions (with IM)</span></span>  <br/> |<span data-ttu-id="1ed8e-298">64</span><span class="sxs-lookup"><span data-stu-id="1ed8e-298">64</span></span>  <br/> |<span data-ttu-id="1ed8e-299">8 </span><span class="sxs-lookup"><span data-stu-id="1ed8e-299">8</span></span>  <br/> |
|<span data-ttu-id="1ed8e-300">主動代理 (正式和非正式) </span><span class="sxs-lookup"><span data-stu-id="1ed8e-300">Active agents (formal and informal)</span></span>  <br/> |<span data-ttu-id="1ed8e-301">2400</span><span class="sxs-lookup"><span data-stu-id="1ed8e-301">2400</span></span>  <br/> |<span data-ttu-id="1ed8e-302">2400</span><span class="sxs-lookup"><span data-stu-id="1ed8e-302">2400</span></span>  <br/> |
|<span data-ttu-id="1ed8e-303">群組搜尋數目</span><span class="sxs-lookup"><span data-stu-id="1ed8e-303">Number of hunt groups</span></span>  <br/> |<span data-ttu-id="1ed8e-304">800</span><span class="sxs-lookup"><span data-stu-id="1ed8e-304">800</span></span>  <br/> |<span data-ttu-id="1ed8e-305">800</span><span class="sxs-lookup"><span data-stu-id="1ed8e-305">800</span></span>  <br/> |
|<span data-ttu-id="1ed8e-306">IVR 群組 (使用語音辨識的數目) </span><span class="sxs-lookup"><span data-stu-id="1ed8e-306">Number of IVR groups (use speech recognition)</span></span>  <br/> |<span data-ttu-id="1ed8e-307">400</span><span class="sxs-lookup"><span data-stu-id="1ed8e-307">400</span></span>  <br/> |<span data-ttu-id="1ed8e-308">400</span><span class="sxs-lookup"><span data-stu-id="1ed8e-308">400</span></span>  <br/> |


