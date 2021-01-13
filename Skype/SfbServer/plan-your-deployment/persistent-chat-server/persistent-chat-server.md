---
title: 在商務用 Skype Server 2015 中規劃 Persistent Chat Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: 摘要：閱讀此主題以瞭解如何在商務用 Skype Server 2015 中規劃 Persistent Chat Server。
ms.openlocfilehash: 9195c149744b9aab9927f0b2a6e490442cff6573
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813663"
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="90efe-103">在商務用 Skype Server 2015 中規劃 Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="90efe-103">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="90efe-104">**摘要：** 閱讀此主題以瞭解如何在商務用 Skype Server 2015 中規劃 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="90efe-104">**Summary:** Read this topic to learn how to plan for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="90efe-105">Persistent Chat Server 是一種選用角色，可讓您組織中的多位使用者參與隨時間持續的聊天室交談。</span><span class="sxs-lookup"><span data-stu-id="90efe-105">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="90efe-106">雖然使用者可以在聊天會話中即時通訊，但每個會話的內容（包括文字、連結及檔案）都是持續性的，這表示使用者可以隨時查看及搜尋會話的所有內容。</span><span class="sxs-lookup"><span data-stu-id="90efe-106">Although users can communicate in real time during a chat session, the content of each session--including text, links, and files--is persistent, which means users can view and search all content of the session at any time.</span></span>
  
<span data-ttu-id="90efe-107">Persistent Chat Server 可以協助改善組織內的通訊：</span><span class="sxs-lookup"><span data-stu-id="90efe-107">Persistent Chat Server can help improve communication within your organization by:</span></span>
  
- <span data-ttu-id="90efe-108">拓寬整個組織的資訊意識和參與</span><span class="sxs-lookup"><span data-stu-id="90efe-108">Broadening information awareness and participation throughout the organization</span></span>
    
- <span data-ttu-id="90efe-109">啟用有效的資訊共用</span><span class="sxs-lookup"><span data-stu-id="90efe-109">Enabling efficient information sharing</span></span> 
    
- <span data-ttu-id="90efe-110">改善小組之間的通訊，包括地理位置分散及跨職能團隊</span><span class="sxs-lookup"><span data-stu-id="90efe-110">Improving communication between teams, including geographically dispersed and cross-functional teams</span></span>
    
- <span data-ttu-id="90efe-111">減少資訊超載</span><span class="sxs-lookup"><span data-stu-id="90efe-111">Reducing information overload</span></span>
    
- <span data-ttu-id="90efe-112">依照選用方式部署 Persistent Chat 合規性服務，遵循相容性法規</span><span class="sxs-lookup"><span data-stu-id="90efe-112">Following compliance regulations by optionally deploying the Persistent Chat Compliance service</span></span>

> [!NOTE] 
> <span data-ttu-id="90efe-113">商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="90efe-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="90efe-114">小組中提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="90efe-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="90efe-115">如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="90efe-115">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="90efe-116">如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="90efe-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
    
## <a name="persistent-chat-server-high-level-architecture"></a><span data-ttu-id="90efe-117">Persistent Chat Server 高層級架構</span><span class="sxs-lookup"><span data-stu-id="90efe-117">Persistent Chat Server high-level architecture</span></span>

<span data-ttu-id="90efe-118">下圖顯示 Persistent Chat Server 架構的高層級視圖。</span><span class="sxs-lookup"><span data-stu-id="90efe-118">The following diagram shows a high-level view of the Persistent Chat Server architecture.</span></span> 
  
![Persistent Chat Server 高層架構](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
<span data-ttu-id="90efe-120">Persistent Chat 包含一種前端伺服器角色，可提供持久聊天服務及後端 SQL 資料庫元件。</span><span class="sxs-lookup"><span data-stu-id="90efe-120">Persistent Chat consists of a front-end server role that provides the Persistent Chat services as well as a back-end SQL database component.</span></span> <span data-ttu-id="90efe-121">前端和後端元件都包含在專用的持久聊天集區中。</span><span class="sxs-lookup"><span data-stu-id="90efe-121">Both front-end and back-end components are included in a dedicated Persistent Chat pool.</span></span> <span data-ttu-id="90efe-122">主控 Persistent Chat Server 的每一部電腦都必須能夠存取現有的商務用 Skype Server 2015 拓撲。</span><span class="sxs-lookup"><span data-stu-id="90efe-122">Each computer that hosts Persistent Chat Server must have access to an existing Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="90efe-123">在此圖中，有一個 Persistent Chat Server 集區 () ，該取決於商務用 Skype Server 集區 A，可將郵件路由傳送至該。</span><span class="sxs-lookup"><span data-stu-id="90efe-123">In this diagram, there is one Persistent Chat Server pool (A), which is dependent on Skype for Business Server Pool A for routing messages to it.</span></span>
  
<span data-ttu-id="90efe-124">您可以部署一或多個 Persistent Chat Server 集區，每個集區最多可支援最多四個使用中80K 並行使用者的主動持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="90efe-124">You can deploy one or more Persistent Chat Server pools, each with up to four active Persistent Chat Servers supporting up to 80K concurrent users.</span></span>
  
<span data-ttu-id="90efe-125">商務用 Skype Server 2015 可使用會話初始通訊協定 (SIP) 進行登錄和透過 SIP 通訊協定 (XCCOS) 進行聊天，以與 Persistent 聊天服務進行通訊。</span><span class="sxs-lookup"><span data-stu-id="90efe-125">Skype for Business Server 2015 communicates with the Persistent Chat service using the Session Initiation Protocol (SIP) for registration and the Extensible Chat Communication Over SIP protocol (XCCOS) for chat.</span></span> 
  
## <a name="persistent-chat-services"></a><span data-ttu-id="90efe-126">Persistent Chat service</span><span class="sxs-lookup"><span data-stu-id="90efe-126">Persistent Chat services</span></span>

<span data-ttu-id="90efe-127">下圖顯示 Persistent Chat Server 前端服務，以及這些服務如何與後端資料庫元件通訊。</span><span class="sxs-lookup"><span data-stu-id="90efe-127">The following diagram shows the Persistent Chat Server front-end services, and how these services communicate with the back-end database components.</span></span> <span data-ttu-id="90efe-128">前端元件包括持久聊天服務和規範服務。</span><span class="sxs-lookup"><span data-stu-id="90efe-128">The front-end components include the Persistent Chat services and the Compliance service.</span></span> <span data-ttu-id="90efe-129">後端元件包括 Persistent Chat store 和 Persistent Chat 規範存放區。</span><span class="sxs-lookup"><span data-stu-id="90efe-129">The back-end components include the Persistent Chat store and the Persistent Chat compliance store.</span></span>
  
![Persistent Chat Server 高層服務](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a><span data-ttu-id="90efe-131">聊天室服務</span><span class="sxs-lookup"><span data-stu-id="90efe-131">Chat service</span></span>

<span data-ttu-id="90efe-132">聊天服務也稱為通道服務，是負責 Persistent Chat Server 的核心服務。</span><span class="sxs-lookup"><span data-stu-id="90efe-132">The Chat service, also called the Channel service, is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="90efe-133">Chat service 提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="90efe-133">The Chat service provides the following functions:</span></span>
  
- <span data-ttu-id="90efe-134">接受傳入訊息</span><span class="sxs-lookup"><span data-stu-id="90efe-134">Accepts incoming messages</span></span>
    
- <span data-ttu-id="90efe-135">在持續聊天室內註冊和列出線上參與者</span><span class="sxs-lookup"><span data-stu-id="90efe-135">Registers and lists online participants within a Persistent Chat room</span></span>
    
- <span data-ttu-id="90efe-136">重新傳輸訊息給其他通道訂閱者</span><span class="sxs-lookup"><span data-stu-id="90efe-136">Retransmits messages to other channel subscribers</span></span>
    
- <span data-ttu-id="90efe-137">針對通道管理、聊天室邀請、搜尋及新內容通知的實施邏輯</span><span class="sxs-lookup"><span data-stu-id="90efe-137">Implements logic for channel management, chat room invitations, search and new content notifications</span></span>
    
<span data-ttu-id="90efe-138">Persistent Chat service 會透過使用 Persistent 聊天室存放區，儲存和存取聊天室內容及其他系統中繼資料 (授權規則等等) 。</span><span class="sxs-lookup"><span data-stu-id="90efe-138">The Persistent Chat service stores and accesses chat room content and other system metadata (authorization rules and so on) by using the Persistent Chat store.</span></span> <span data-ttu-id="90efe-139">該服務會將上傳至聊天室的檔案儲存在 Persistent Chat file store 中。</span><span class="sxs-lookup"><span data-stu-id="90efe-139">The service stores files that are uploaded into chat rooms in the Persistent Chat file store.</span></span>
  
### <a name="compliance-service"></a><span data-ttu-id="90efe-140">規範服務</span><span class="sxs-lookup"><span data-stu-id="90efe-140">Compliance service</span></span>

<span data-ttu-id="90efe-141">如果貴組織的法規要求封存持續聊天活動，您可以部署選用的持續性聊天規範服務。</span><span class="sxs-lookup"><span data-stu-id="90efe-141">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="90efe-142">規範服務負責將聊天內容和事件（例如加入和離開會議室）封存到 Persistent Chat 規範檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="90efe-142">The Compliance service is responsible for archiving chat content and events, such as joining and leaving rooms, to the Persistent Chat Compliance file store.</span></span> <span data-ttu-id="90efe-143">規範服務是安裝在 Persistent Chat 集區中的每個 Persistent Chat Server 上。</span><span class="sxs-lookup"><span data-stu-id="90efe-143">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> 
  
### <a name="web-services"></a><span data-ttu-id="90efe-144">Web 服務</span><span class="sxs-lookup"><span data-stu-id="90efe-144">Web services</span></span>

<span data-ttu-id="90efe-145">在商務用 Skype 前端伺服器上執行 Persistent Chat web 服務。</span><span class="sxs-lookup"><span data-stu-id="90efe-145">The Persistent Chat web services run on the Skype for Business Front End Servers.</span></span> <span data-ttu-id="90efe-146">Web 服務取決於網際網路資訊服務 (IIS) ，並以 web 元件的形式來執行：</span><span class="sxs-lookup"><span data-stu-id="90efe-146">The web services depend on Internet Information Services (IIS), and are implemented as web components:</span></span>
  
- <span data-ttu-id="90efe-147">檔案上傳與下載的持續性聊天 web 服務負責電子檔上傳及從聊天室中檢索檔案。</span><span class="sxs-lookup"><span data-stu-id="90efe-147">Persistent Chat web services for file upload and download are responsible for posting and retrieving files from chat rooms.</span></span>
    
- <span data-ttu-id="90efe-148">聊天室管理的 Persistent Chat web 服務負責為使用者提供管理其聊天室的能力，以及建立新的聊天室。</span><span class="sxs-lookup"><span data-stu-id="90efe-148">Persistent Chat web services for chat room management are responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>
    
## <a name="defining-requirements-for-your-organization"></a><span data-ttu-id="90efe-149">定義組織的需求</span><span class="sxs-lookup"><span data-stu-id="90efe-149">Defining requirements for your organization</span></span>

<span data-ttu-id="90efe-150">如果您決定部署 Persistent Chat Server，則必須判斷組織的業務需求，然後定義拓撲、基礎結構和技術需求，以支援您的業務需求。</span><span class="sxs-lookup"><span data-stu-id="90efe-150">If you decide to deploy Persistent Chat Server, you'll need to determine your organization's business requirements, then define the topology, infrastructure, and technical requirements to support your business needs.</span></span> <span data-ttu-id="90efe-151">若要優化您的部署，您必須回答下列問題：</span><span class="sxs-lookup"><span data-stu-id="90efe-151">To optimize your deployment, you'll need to answer the following questions:</span></span>
  
- <span data-ttu-id="90efe-152">您是從舊版的群組聊天伺服器或舊版本的 Persistent Chat Server 進行遷移，還是第一次部署 Persistent Chat Server？</span><span class="sxs-lookup"><span data-stu-id="90efe-152">Are you migrating from a previous version of Group Chat Server, or a previous version of Persistent Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>
    
- <span data-ttu-id="90efe-153">誰可以使用 Persistent Chat Server？</span><span class="sxs-lookup"><span data-stu-id="90efe-153">Who can use Persistent Chat Server?</span></span> <span data-ttu-id="90efe-154">您可以指定 Persistent 聊天原則，以決定全域、網站或使用者層級的使用者存取權。</span><span class="sxs-lookup"><span data-stu-id="90efe-154">You specify Persistent Chat policies to determine user access at the global, site, or user level.</span></span>
    
- <span data-ttu-id="90efe-155">需要有多少使用者才能存取 Persistent Chat Server？</span><span class="sxs-lookup"><span data-stu-id="90efe-155">How many users will require access to Persistent Chat Server?</span></span> <span data-ttu-id="90efe-156">Persistent Chat Server 支援150000布建使用者 (由原則) 啟用，且最多可有80000同時使用者。</span><span class="sxs-lookup"><span data-stu-id="90efe-156">Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users.</span></span> <span data-ttu-id="90efe-157">單一 Persistent Chat Server 可以支援20000連線的使用者，而單一持久聊天伺服器集區最多可以有四個作用中的伺服器，共80000個同時連線的使用者。</span><span class="sxs-lookup"><span data-stu-id="90efe-157">A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>
    
- <span data-ttu-id="90efe-158">您想要如何控制範圍、道德界限及存取？</span><span class="sxs-lookup"><span data-stu-id="90efe-158">How do you want to control scopes, ethical boundaries, and access?</span></span> <span data-ttu-id="90efe-159">您可以定義類別以隔離這些界限，並選擇可在每個類別中建立的會議室。</span><span class="sxs-lookup"><span data-stu-id="90efe-159">You can define categories to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>
    
- <span data-ttu-id="90efe-160">您想要如何控制可以建立聊天室的人員？</span><span class="sxs-lookup"><span data-stu-id="90efe-160">How do you want to control who can create rooms?</span></span> <span data-ttu-id="90efe-161">您可以定義可以建立聊天室的建立者。</span><span class="sxs-lookup"><span data-stu-id="90efe-161">You can define creators who can create rooms.</span></span> <span data-ttu-id="90efe-162">建立者可以將其他成員指派為聊天室管理員，以進行持續的管理工作室。</span><span class="sxs-lookup"><span data-stu-id="90efe-162">Creators can assign other members as chat room managers for ongoing management of the rooms.</span></span>
    
- <span data-ttu-id="90efe-163">您想要如何建立聊天室？</span><span class="sxs-lookup"><span data-stu-id="90efe-163">How do you want to create rooms?</span></span> <span data-ttu-id="90efe-164">Persistent Chat Server 提供用來建立及管理聊天室的 web 型功能。</span><span class="sxs-lookup"><span data-stu-id="90efe-164">Persistent Chat Server provides a web-based feature for creating and managing rooms.</span></span> <span data-ttu-id="90efe-165">這可以從商務用 Skype 用戶端啟動。</span><span class="sxs-lookup"><span data-stu-id="90efe-165">This can be launched from the Skype for Business client.</span></span> <span data-ttu-id="90efe-166">您可以選擇定義客戶解決方案，以執行您的業務需求和工作流程，並設定 Persistent Chat Server 將使用者導向至您的自訂解決方案。</span><span class="sxs-lookup"><span data-stu-id="90efe-166">You can choose to define a customer solution that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>
    
- <span data-ttu-id="90efe-167">您想要佈建哪些種類的增益集？</span><span class="sxs-lookup"><span data-stu-id="90efe-167">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="90efe-168">增益集利用商務用 Skype 用戶端中的擴充性窗格，以提供與會議室相關的內容，增強會議室的體驗。</span><span class="sxs-lookup"><span data-stu-id="90efe-168">Add-ins enhance the in-room experience by leveraging the extensibility pane in the Skype for Business client to provide context that is relevant to the room.</span></span> <span data-ttu-id="90efe-169">您可以選擇哪些一般增益集最有用 (例如，貴公司的網站、內部共同作業元件等)。</span><span class="sxs-lookup"><span data-stu-id="90efe-169">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="90efe-170">聊天室管理員可以選擇其中一個登錄的增益集，並視需要將它關聯至他們的聊天室。</span><span class="sxs-lookup"><span data-stu-id="90efe-170">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span> 
    
- <span data-ttu-id="90efe-171">您有哪些種類的高可用性與災害復原需求？</span><span class="sxs-lookup"><span data-stu-id="90efe-171">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="90efe-172">Persistent Chat Server 支援 SQL Server 鏡像和 SQL Server 叢集以取得高可用性。</span><span class="sxs-lookup"><span data-stu-id="90efe-172">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability.</span></span> <span data-ttu-id="90efe-173">針對嚴重損壞修復，Persistent Chat Server 最多可支援8部伺服器 (使用 SQL Server 記錄傳送的延伸集區中的4個作用中和4個待命) 。</span><span class="sxs-lookup"><span data-stu-id="90efe-173">For disaster recovery, Persistent Chat Server supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping.</span></span> 
    
- <span data-ttu-id="90efe-174">是否有法規需求？</span><span class="sxs-lookup"><span data-stu-id="90efe-174">Are there regulatory requirements?</span></span> <span data-ttu-id="90efe-175">如果貴公司所在的國家或地區中的資料必須保留在全國，您可能需要將多個 Persistent 聊天伺服器集區，部署到特定地理位置的各個地方。</span><span class="sxs-lookup"><span data-stu-id="90efe-175">If your company is in a country or region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="90efe-176">會議室、類別或增益集不會跨越集區，只隸屬于一個 Persistent Chat Server 集區。</span><span class="sxs-lookup"><span data-stu-id="90efe-176">A room, category, or add-in does not span pools--it belongs to only one Persistent Chat Server pool.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="90efe-177">具有多個 Persistent Chat Server 集區不會提供更多規模 (您仍然可以在所有持久聊天伺服器集區) 上僅有80000並行的使用者。</span><span class="sxs-lookup"><span data-stu-id="90efe-177">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrent users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="90efe-178">支援多個 Persistent Chat Server 集區的主要原因是支援法規考慮。</span><span class="sxs-lookup"><span data-stu-id="90efe-178">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="90efe-179">相關資訊</span><span class="sxs-lookup"><span data-stu-id="90efe-179">For more information</span></span>

<span data-ttu-id="90efe-180">如需安裝及設定 Persistent Chat Server 的詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="90efe-180">For more information about installing and configuring Persistent Chat Server, see the following topics:</span></span>
  
- <span data-ttu-id="90efe-181">如需如何部署 Persistent Chat Server 的詳細資訊，請參閱 [Deploy Persistent Chat server In 商務用 Skype server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="90efe-181">For details about how to deploy Persistent Chat Server, see [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md).</span></span> 
    
- <span data-ttu-id="90efe-182">如需如何設定持久聊天伺服器部署設定的詳細資訊，請參閱 [Manage Persistent Chat server In 商務用 Skype server 2015](../../manage/persistent-chat/persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="90efe-182">For details about how to configure settings on your Persistent Chat Server deployment, see [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
    

