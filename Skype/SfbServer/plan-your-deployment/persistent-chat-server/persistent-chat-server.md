---
title: 在商務用 Skype Server 2015 中規劃常設聊天室伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: '摘要: 請閱讀本主題, 以瞭解如何在商務用 Skype Server 2015 中規劃持續聊天伺服器。'
ms.openlocfilehash: 3e485f938d2bd48dad5f1b9f0baa96d7f3f537d0
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2019
ms.locfileid: "36194017"
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="759ec-103">在商務用 Skype Server 2015 中規劃常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="759ec-103">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="759ec-104">**摘要:** 若要瞭解如何在商務用 Skype Server 2015 中規劃持續聊天伺服器, 請閱讀本主題。</span><span class="sxs-lookup"><span data-stu-id="759ec-104">**Summary:** Read this topic to learn how to plan for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="759ec-105">持續聊天伺服器是一個可讓貴組織中的多位使用者參與在一段時間內保留的聊天室交談的選擇性角色。</span><span class="sxs-lookup"><span data-stu-id="759ec-105">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="759ec-106">雖然使用者可以在聊天會話中即時進行通訊, 但每個會話的內容 (包括文字、連結和檔案) 都是永久性的, 這表示使用者隨時都可以查看及搜尋會話的所有內容。</span><span class="sxs-lookup"><span data-stu-id="759ec-106">Although users can communicate in real time during a chat session, the content of each session--including text, links, and files--is persistent, which means users can view and search all content of the session at any time.</span></span>
  
<span data-ttu-id="759ec-107">持續聊天伺服器可協助改善貴組織內的通訊:</span><span class="sxs-lookup"><span data-stu-id="759ec-107">Persistent Chat Server can help improve communication within your organization by:</span></span>
  
- <span data-ttu-id="759ec-108">拓寬資訊的知名度並參與整個組織</span><span class="sxs-lookup"><span data-stu-id="759ec-108">Broadening information awareness and participation throughout the organization</span></span>
    
- <span data-ttu-id="759ec-109">啟用高效的資訊共用</span><span class="sxs-lookup"><span data-stu-id="759ec-109">Enabling efficient information sharing</span></span> 
    
- <span data-ttu-id="759ec-110">改善團隊間的溝通, 包括地理位置分散且跨職能的團隊</span><span class="sxs-lookup"><span data-stu-id="759ec-110">Improving communication between teams, including geographically dispersed and cross-functional teams</span></span>
    
- <span data-ttu-id="759ec-111">減少資訊超載</span><span class="sxs-lookup"><span data-stu-id="759ec-111">Reducing information overload</span></span>
    
- <span data-ttu-id="759ec-112">依選擇性地部署持續性聊天合規性服務來遵循規範規範</span><span class="sxs-lookup"><span data-stu-id="759ec-112">Following compliance regulations by optionally deploying the Persistent Chat Compliance service</span></span>

> [!NOTE] 
> <span data-ttu-id="759ec-113">商務用 Skype Server 2015 提供持續聊天, 但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="759ec-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="759ec-114">團隊中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="759ec-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="759ec-115">如需詳細資訊, 請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="759ec-115">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="759ec-116">如果您需要使用持續聊天, 您可以選擇將需要此功能的使用者遷移至小組, 或繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="759ec-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
    
## <a name="persistent-chat-server-high-level-architecture"></a><span data-ttu-id="759ec-117">持續聊天伺服器的高層次架構</span><span class="sxs-lookup"><span data-stu-id="759ec-117">Persistent Chat Server high-level architecture</span></span>

<span data-ttu-id="759ec-118">下圖顯示持久聊天伺服器架構的高層視圖。</span><span class="sxs-lookup"><span data-stu-id="759ec-118">The following diagram shows a high-level view of the Persistent Chat Server architecture.</span></span> 
  
![持續聊天伺服器的高層次架構](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
<span data-ttu-id="759ec-120">持續聊天是由提供持續性聊天服務以及後端 SQL 資料庫元件的前端伺服器角色所組成。</span><span class="sxs-lookup"><span data-stu-id="759ec-120">Persistent Chat consists of a front-end server role that provides the Persistent Chat services as well as a back-end SQL database component.</span></span> <span data-ttu-id="759ec-121">前端和後端元件都包含在專用的持久性聊天池中。</span><span class="sxs-lookup"><span data-stu-id="759ec-121">Both front-end and back-end components are included in a dedicated Persistent Chat pool.</span></span> <span data-ttu-id="759ec-122">每個主持持久聊天伺服器的電腦都必須有權存取現有的商務用 Skype Server 2015 拓撲。</span><span class="sxs-lookup"><span data-stu-id="759ec-122">Each computer that hosts Persistent Chat Server must have access to an existing Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="759ec-123">在此圖表中, 有一個持續式聊天伺服器池 (A), 它依賴于商務用 Skype Server Pool A 來傳送郵件給它。</span><span class="sxs-lookup"><span data-stu-id="759ec-123">In this diagram, there is one Persistent Chat Server pool (A), which is dependent on Skype for Business Server Pool A for routing messages to it.</span></span>
  
<span data-ttu-id="759ec-124">您可以部署一或多個持續聊天伺服器池, 每個都有最多四個可支援80K 併發使用者的活躍持久聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="759ec-124">You can deploy one or more Persistent Chat Server pools, each with up to four active Persistent Chat Servers supporting up to 80K concurrent users.</span></span>
  
<span data-ttu-id="759ec-125">商務用 Skype Server 2015 會使用用於登錄的會話初始通訊協定 (SIP) 及透過 SIP 通訊協定 (XCCOS) 上的 [線上] 進行聊天, 與持續聊天服務進行通訊。</span><span class="sxs-lookup"><span data-stu-id="759ec-125">Skype for Business Server 2015 communicates with the Persistent Chat service using the Session Initiation Protocol (SIP) for registration and the Extensible Chat Communication Over SIP protocol (XCCOS) for chat.</span></span> 
  
## <a name="persistent-chat-services"></a><span data-ttu-id="759ec-126">持續聊天服務</span><span class="sxs-lookup"><span data-stu-id="759ec-126">Persistent Chat services</span></span>

<span data-ttu-id="759ec-127">下圖顯示持久的聊天伺服器前端服務, 以及這些服務如何與後端資料庫元件進行通訊。</span><span class="sxs-lookup"><span data-stu-id="759ec-127">The following diagram shows the Persistent Chat Server front-end services, and how these services communicate with the back-end database components.</span></span> <span data-ttu-id="759ec-128">前端元件包括持久聊天服務和合規性服務。</span><span class="sxs-lookup"><span data-stu-id="759ec-128">The front-end components include the Persistent Chat services and the Compliance service.</span></span> <span data-ttu-id="759ec-129">後端元件包括 [永久聊天] 存放區和持續性聊天規範存放區。</span><span class="sxs-lookup"><span data-stu-id="759ec-129">The back-end components include the Persistent Chat store and the Persistent Chat compliance store.</span></span>
  
![持續聊天伺服器高層級服務](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a><span data-ttu-id="759ec-131">聊天服務</span><span class="sxs-lookup"><span data-stu-id="759ec-131">Chat service</span></span>

<span data-ttu-id="759ec-132">聊天服務 (也稱為通道服務) 是負責持久聊天伺服器的核心服務。</span><span class="sxs-lookup"><span data-stu-id="759ec-132">The Chat service, also called the Channel service, is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="759ec-133">聊天服務提供下列功能:</span><span class="sxs-lookup"><span data-stu-id="759ec-133">The Chat service provides the following functions:</span></span>
  
- <span data-ttu-id="759ec-134">接受接收的郵件</span><span class="sxs-lookup"><span data-stu-id="759ec-134">Accepts incoming messages</span></span>
    
- <span data-ttu-id="759ec-135">在持續聊天室中註冊並列出線上參與者</span><span class="sxs-lookup"><span data-stu-id="759ec-135">Registers and lists online participants within a Persistent Chat room</span></span>
    
- <span data-ttu-id="759ec-136">將郵件重新傳送至其他通道訂閱者</span><span class="sxs-lookup"><span data-stu-id="759ec-136">Retransmits messages to other channel subscribers</span></span>
    
- <span data-ttu-id="759ec-137">針對通道管理、聊天室邀請、搜尋及新內容通知的實現邏輯</span><span class="sxs-lookup"><span data-stu-id="759ec-137">Implements logic for channel management, chat room invitations, search and new content notifications</span></span>
    
<span data-ttu-id="759ec-138">Persistent 聊天服務會使用 [永久聊天] 存放區, 儲存及存取聊天室內容和其他系統中繼資料 (授權規則等)。</span><span class="sxs-lookup"><span data-stu-id="759ec-138">The Persistent Chat service stores and accesses chat room content and other system metadata (authorization rules and so on) by using the Persistent Chat store.</span></span> <span data-ttu-id="759ec-139">此服務會將上傳到聊天室中的檔案儲存在永久聊天檔案存放區中。</span><span class="sxs-lookup"><span data-stu-id="759ec-139">The service stores files that are uploaded into chat rooms in the Persistent Chat file store.</span></span>
  
### <a name="compliance-service"></a><span data-ttu-id="759ec-140">合規性服務</span><span class="sxs-lookup"><span data-stu-id="759ec-140">Compliance service</span></span>

<span data-ttu-id="759ec-141">如果您的組織有需要永久聊天活動進行封存的規章, 您可以部署選用的持續聊天合規性服務。</span><span class="sxs-lookup"><span data-stu-id="759ec-141">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="759ec-142">合規性服務負責將聊天內容和事件 (例如加入與離開會議室) 儲存在持續聊天相容性檔案存放區中。</span><span class="sxs-lookup"><span data-stu-id="759ec-142">The Compliance service is responsible for archiving chat content and events, such as joining and leaving rooms, to the Persistent Chat Compliance file store.</span></span> <span data-ttu-id="759ec-143">相容性服務已安裝在持續聊天池中的每個持續聊天伺服器上。</span><span class="sxs-lookup"><span data-stu-id="759ec-143">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> 
  
### <a name="web-services"></a><span data-ttu-id="759ec-144">Web 服務</span><span class="sxs-lookup"><span data-stu-id="759ec-144">Web services</span></span>

<span data-ttu-id="759ec-145">在商務用 Skype 前端伺服器上執行永久性聊天 web 服務。</span><span class="sxs-lookup"><span data-stu-id="759ec-145">The Persistent Chat web services run on the Skype for Business Front End Servers.</span></span> <span data-ttu-id="759ec-146">Web 服務依賴于網際網路資訊服務 (IIS), 並以網頁元件的形式實現:</span><span class="sxs-lookup"><span data-stu-id="759ec-146">The web services depend on Internet Information Services (IIS), and are implemented as web components:</span></span>
  
- <span data-ttu-id="759ec-147">檔案上傳和下載的持續聊天 web 服務負責從聊天室張貼及檢索檔案。</span><span class="sxs-lookup"><span data-stu-id="759ec-147">Persistent Chat web services for file upload and download are responsible for posting and retrieving files from chat rooms.</span></span>
    
- <span data-ttu-id="759ec-148">聊天室管理的持續聊天 web 服務負責提供使用者管理其聊天室的功能, 並建立新的聊天室。</span><span class="sxs-lookup"><span data-stu-id="759ec-148">Persistent Chat web services for chat room management are responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>
    
## <a name="defining-requirements-for-your-organization"></a><span data-ttu-id="759ec-149">定義貴組織的需求</span><span class="sxs-lookup"><span data-stu-id="759ec-149">Defining requirements for your organization</span></span>

<span data-ttu-id="759ec-150">如果您決定要部署持久聊天伺服器, 您必須判斷貴組織的業務需求, 然後定義拓撲、基礎結構及技術需求, 以支援您的業務需求。</span><span class="sxs-lookup"><span data-stu-id="759ec-150">If you decide to deploy Persistent Chat Server, you'll need to determine your organization's business requirements, then define the topology, infrastructure, and technical requirements to support your business needs.</span></span> <span data-ttu-id="759ec-151">若要優化您的部署, 您必須回答下列問題:</span><span class="sxs-lookup"><span data-stu-id="759ec-151">To optimize your deployment, you'll need to answer the following questions:</span></span>
  
- <span data-ttu-id="759ec-152">您是從舊版的群組聊天伺服器或舊版本的持久性聊天伺服器進行遷移嗎？還是第一次部署持久聊天伺服器？</span><span class="sxs-lookup"><span data-stu-id="759ec-152">Are you migrating from a previous version of Group Chat Server, or a previous version of Persistent Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>
    
- <span data-ttu-id="759ec-153">誰可以使用持續聊天伺服器？</span><span class="sxs-lookup"><span data-stu-id="759ec-153">Who can use Persistent Chat Server?</span></span> <span data-ttu-id="759ec-154">您可以指定持續聊天原則, 以決定全域、網站或使用者層級的使用者存取權。</span><span class="sxs-lookup"><span data-stu-id="759ec-154">You specify Persistent Chat policies to determine user access at the global, site, or user level.</span></span>
    
- <span data-ttu-id="759ec-155">需要多少使用者才能存取持久聊天伺服器？</span><span class="sxs-lookup"><span data-stu-id="759ec-155">How many users will require access to Persistent Chat Server?</span></span> <span data-ttu-id="759ec-156">持續聊天伺服器支援150000預配的使用者 (由原則啟用), 以及最多80000個併發使用者。</span><span class="sxs-lookup"><span data-stu-id="759ec-156">Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users.</span></span> <span data-ttu-id="759ec-157">單一持久聊天伺服器可支援20000連線的使用者, 且單一持續式聊天伺服器池最多可以有4個作用中的伺服器, 共80000個同時連接的使用者。</span><span class="sxs-lookup"><span data-stu-id="759ec-157">A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>
    
- <span data-ttu-id="759ec-158">您要如何控制範圍、道德界限及存取權？</span><span class="sxs-lookup"><span data-stu-id="759ec-158">How do you want to control scopes, ethical boundaries, and access?</span></span> <span data-ttu-id="759ec-159">您可以定義類別來隔離這些界限, 並選擇每個類別中所能建立的人員在會議室中。</span><span class="sxs-lookup"><span data-stu-id="759ec-159">You can define categories to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>
    
- <span data-ttu-id="759ec-160">您想要如何控制誰可以建立聊天室？</span><span class="sxs-lookup"><span data-stu-id="759ec-160">How do you want to control who can create rooms?</span></span> <span data-ttu-id="759ec-161">您可以定義可建立聊天室的建立者。</span><span class="sxs-lookup"><span data-stu-id="759ec-161">You can define creators who can create rooms.</span></span> <span data-ttu-id="759ec-162">創意者可以指派其他成員做為聊天室管理員, 以便持續管理會議室。</span><span class="sxs-lookup"><span data-stu-id="759ec-162">Creators can assign other members as chat room managers for ongoing management of the rooms.</span></span>
    
- <span data-ttu-id="759ec-163">您想要如何建立聊天室？</span><span class="sxs-lookup"><span data-stu-id="759ec-163">How do you want to create rooms?</span></span> <span data-ttu-id="759ec-164">持續聊天伺服器提供建立及管理會議室所用的網路功能。</span><span class="sxs-lookup"><span data-stu-id="759ec-164">Persistent Chat Server provides a web-based feature for creating and managing rooms.</span></span> <span data-ttu-id="759ec-165">您可以從商務用 Skype 用戶端啟動此程式。</span><span class="sxs-lookup"><span data-stu-id="759ec-165">This can be launched from the Skype for Business client.</span></span> <span data-ttu-id="759ec-166">您可以選擇定義實施您的業務需求與工作流程的客戶解決方案, 並設定持續聊天伺服器以將使用者引導至您的自訂方案。</span><span class="sxs-lookup"><span data-stu-id="759ec-166">You can choose to define a customer solution that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>
    
- <span data-ttu-id="759ec-167">您想要提供哪種增益集？</span><span class="sxs-lookup"><span data-stu-id="759ec-167">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="759ec-168">增益集可利用商務用 Skype 用戶端中的 [擴充性] 窗格, 以提供與聊天室相關的內容, 以增強會議室體驗。</span><span class="sxs-lookup"><span data-stu-id="759ec-168">Add-ins enhance the in-room experience by leveraging the extensibility pane in the Skype for Business client to provide context that is relevant to the room.</span></span> <span data-ttu-id="759ec-169">您可以選擇一般的增益集最實用 (例如, 您的公司網站、內部共同作業檔等等)。</span><span class="sxs-lookup"><span data-stu-id="759ec-169">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="759ec-170">聊天室管理員可以選擇其中一個已註冊的增益集, 並視需要將其與聊天室產生關聯。</span><span class="sxs-lookup"><span data-stu-id="759ec-170">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span> 
    
- <span data-ttu-id="759ec-171">您擁有哪種類型的高可用性和災害復原需求？</span><span class="sxs-lookup"><span data-stu-id="759ec-171">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="759ec-172">持久聊天伺服器支援 SQL Server 鏡像與 SQL Server 群集, 以提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="759ec-172">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability.</span></span> <span data-ttu-id="759ec-173">針對災難復原, 持續性聊天伺服器可在具有 SQL Server 記錄傳送的延伸池中支援最多8個伺服器 (4 個作用中和4個備用)。</span><span class="sxs-lookup"><span data-stu-id="759ec-173">For disaster recovery, Persistent Chat Server supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping.</span></span> 
    
- <span data-ttu-id="759ec-174">是否有法規要求？</span><span class="sxs-lookup"><span data-stu-id="759ec-174">Are there regulatory requirements?</span></span> <span data-ttu-id="759ec-175">如果您的公司所在的國家或地區中需要將資料保留在全國, 您可能需要將多個持續聊天伺服器池, 分別部署到特定地理位置。</span><span class="sxs-lookup"><span data-stu-id="759ec-175">If your company is in a country or region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="759ec-176">[會議室]、[類別] 或 [增益集] 不會跨越資源庫, 只屬於一個持續聊天伺服器池。</span><span class="sxs-lookup"><span data-stu-id="759ec-176">A room, category, or add-in does not span pools--it belongs to only one Persistent Chat Server pool.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="759ec-177">擁有多個持續聊天伺服器池並不能提供更多規模 (您仍可在所有持久聊天伺服器池中使用80000並行使用者)。</span><span class="sxs-lookup"><span data-stu-id="759ec-177">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrent users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="759ec-178">支援多個持續聊天伺服器池的主要原因是要支援法規問題。</span><span class="sxs-lookup"><span data-stu-id="759ec-178">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="759ec-179">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="759ec-179">For more information</span></span>

<span data-ttu-id="759ec-180">如需安裝及設定持久聊天伺服器的詳細資訊, 請參閱下列主題:</span><span class="sxs-lookup"><span data-stu-id="759ec-180">For more information about installing and configuring Persistent Chat Server, see the following topics:</span></span>
  
- <span data-ttu-id="759ec-181">如需有關如何部署持久聊天伺服器的詳細資訊, 請參閱[在商務用 Skype server 2015 中部署持久聊天伺服器](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="759ec-181">For details about how to deploy Persistent Chat Server, see [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md).</span></span> 
    
- <span data-ttu-id="759ec-182">如需有關如何在持續聊天伺服器部署上設定設定的詳細資訊, 請參閱[在商務用 Skype server 2015 中管理持久聊天伺服器](../../manage/persistent-chat/persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="759ec-182">For details about how to configure settings on your Persistent Chat Server deployment, see [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
    

