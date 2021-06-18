## <a name="integration-models-for-solution-providers"></a><span data-ttu-id="8bcde-101">解決方案提供者的整合模型</span><span class="sxs-lookup"><span data-stu-id="8bcde-101">Integration models for solution providers</span></span>

<a name="steps"></a>

<span data-ttu-id="8bcde-102">作為聯絡中心解決方案提供者，您可以選擇三種模式，將已連接的聯絡人中心解決方案整合至 Teams：</span><span class="sxs-lookup"><span data-stu-id="8bcde-102">As a contact center solution provider, there are three models to choose from to integrate your connected contact center solution into Teams:</span></span>

- <span data-ttu-id="8bcde-103">如果您想要使用認證 SBCs 和直接路由將聯絡中心解決方案連結至 Teams，請參閱 [連接模型](?tabs=connect#steps)。</span><span class="sxs-lookup"><span data-stu-id="8bcde-103">If you want to use certified SBCs and Direct Routing to connect a contact center solution to Teams, see the [Connect model](?tabs=connect#steps).</span></span>

- <span data-ttu-id="8bcde-104">如果您想要使用 Azure Bot 和 Microsoft Graph 通訊 API 來啟用解決方案提供者建立 Teams 應用程式，請參閱 [延伸模型](?tabs=extend#steps)。</span><span class="sxs-lookup"><span data-stu-id="8bcde-104">If you want to use Azure bots and the Microsoft Graph Communication APIs to enable solution providers to create Teams apps, see the [Extend model](?tabs=extend#steps).</span></span>

- <span data-ttu-id="8bcde-105">如果您想要使用可讓解決方案提供者在 App 中內安裝原生 Teams 體驗的 SDK，請參閱 [Power 模型](?tabs=power#steps)。</span><span class="sxs-lookup"><span data-stu-id="8bcde-105">If you want to use an SDK that enables solution providers to imbed native Teams experiences in their App, see the [Power model](?tabs=power#steps).</span></span> <span data-ttu-id="8bcde-106">在 2021 年底提供 SDK 時，將可以使用 Power Solutions。</span><span class="sxs-lookup"><span data-stu-id="8bcde-106">Power solutions will be possible when the SDK is available, towards the end of 2021.</span></span>

### <a name="the-connect-model"></a>[<span data-ttu-id="8bcde-107">**連接模型**</span><span class="sxs-lookup"><span data-stu-id="8bcde-107">**The Connect model**</span></span>](#tab/connect)

<span data-ttu-id="8bcde-108">Connect 模型使用 Microsoft 認證的 SBCs 和直接路由，將聯絡人中心解決方案連接到 Teams 電話系統基礎結構，啟用增強的路由、組配置和系統深入見解。</span><span class="sxs-lookup"><span data-stu-id="8bcde-108">The Connect model uses Microsoft certified SBCs and Direct Routing to connect contact center solutions to Teams phone system infrastructure, enabling enhanced routing, configuration, and system insights.</span></span>

<span data-ttu-id="8bcde-109">代理人可以設定自動化虛擬助理員和技能型路由佇列，以收集資訊，並讓客戶與主題專家聯繫。</span><span class="sxs-lookup"><span data-stu-id="8bcde-109">Agents can set up automated virtual assistants and skill-based routing queues to gather information and connect customers with subject matter experts.</span></span>

<span data-ttu-id="8bcde-110">**功能重點：**</span><span class="sxs-lookup"><span data-stu-id="8bcde-110">**Feature highlights:**</span></span>

<span data-ttu-id="8bcde-111">雖然這些功能不是此整合模型的功能全面清單，但焦點區域包括：</span><span class="sxs-lookup"><span data-stu-id="8bcde-111">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="8bcde-112">適用于代理人的 Office 365 authN，以從整合的 CCaaS 用戶端連接到其 Microsoft 租使用者</span><span class="sxs-lookup"><span data-stu-id="8bcde-112">Office 365 authN for agents to connect to their Microsoft tenant from their integrated CCaaS client</span></span> 

  - <span data-ttu-id="8bcde-113">查看 Teams 何時可以使用代理程式</span><span class="sxs-lookup"><span data-stu-id="8bcde-113">See when agents are available with Teams</span></span>

  - <span data-ttu-id="8bcde-114">Teams 的轉接和群組通話支援</span><span class="sxs-lookup"><span data-stu-id="8bcde-114">Transfers and group call support with Teams</span></span> 

  - <span data-ttu-id="8bcde-115">與 Teams 整合的 Teams Graph API 和雲端通訊 API</span><span class="sxs-lookup"><span data-stu-id="8bcde-115">Teams Graph APIs and Cloud Communication APIs for integration with Teams</span></span> 

  - <span data-ttu-id="8bcde-116">多租使用者 SIP 主幹，可支援解決方案提供者 SBC 上的多個客戶。</span><span class="sxs-lookup"><span data-stu-id="8bcde-116">Multi-tenant SIP trunking to support several customers on solution provider’s SBC.</span></span>  

  - <span data-ttu-id="8bcde-117">解決方案提供者使用 [<span class="underline">Microsoft 認證的會話邊界控制器 (SBC) </span>](../direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="8bcde-117">Solution providers to use [<span class="underline">Microsoft certified session border controller (SBC)</span>](../direct-routing-border-controllers.md)</span></span>


### <a name="the-extend-model"></a>[<span data-ttu-id="8bcde-118">**延伸模型**</span><span class="sxs-lookup"><span data-stu-id="8bcde-118">**The Extend model**</span></span>](#tab/extend)

<span data-ttu-id="8bcde-119">擴充模型會使用 Microsoft Graph 中的 [Teams](/microsoftteams/platform/overview)用戶端平臺 [、Teams Graph API](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) 和雲端通訊 API 與 [Teams 用戶端整合](/graph/api/resources/communications-api-overview?view=graph-rest-1.0)。</span><span class="sxs-lookup"><span data-stu-id="8bcde-119">The Extend model integrates with the Teams client using the [Teams client platform](/microsoftteams/platform/overview), [Teams Graph APIs](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) and [Cloud Communications API in Microsoft Graph](/graph/api/resources/communications-api-overview?view=graph-rest-1.0).</span></span> <span data-ttu-id="8bcde-120">延伸模式也會使用 Teams 電話系統，以用於所有聯絡中心通話和通話控制體驗，而聯絡中心解決方案提供者會和 Microsoft 365 一起做為電話業者。</span><span class="sxs-lookup"><span data-stu-id="8bcde-120">The Extend model also uses the Teams phone system for all contact center calls and call control experiences, and the contact center solution provider acts as a telephony carrier alongside Microsoft 365.</span></span>

<span data-ttu-id="8bcde-121">代理人可以使用 Teams 進行內部共同合作和外部通訊，而且可以在開始進行互動之前，從多個系統的資料相互關聯的動態關聯性筆記獲益，然後避免成本昂貴的上下文切換。</span><span class="sxs-lookup"><span data-stu-id="8bcde-121">Agents can use Teams for internal collaboration and external communication and can benefit from dynamic, contextual notes correlating data from multiple systems prior to starting an engagement and then avoid costly context switching.</span></span>

<span data-ttu-id="8bcde-122">組織可以向下設計工作流程和進位路由組組，並測量其系統與互動的品質。</span><span class="sxs-lookup"><span data-stu-id="8bcde-122">Organizations can design workflows and advanced routing configurations down to the individual and measure the quality of their system and interactions.</span></span>

<span data-ttu-id="8bcde-123">**功能重點：**</span><span class="sxs-lookup"><span data-stu-id="8bcde-123">**Feature highlights:**</span></span>

<span data-ttu-id="8bcde-124">雖然這些功能不是此整合模型的功能全面清單，但焦點區域包括：</span><span class="sxs-lookup"><span data-stu-id="8bcde-124">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="8bcde-125">與 Teams 整合的 Teams Graph API 和雲端通訊 API</span><span class="sxs-lookup"><span data-stu-id="8bcde-125">Teams Graph APIs and Cloud Communication APIs for integration with Teams</span></span> 

  - <span data-ttu-id="8bcde-126">適用于代理人體驗的 Teams 型應用程式</span><span class="sxs-lookup"><span data-stu-id="8bcde-126">Teams-based app for agent experiences</span></span> 

  - <span data-ttu-id="8bcde-127">Teams 是代理程式的主要通話端點</span><span class="sxs-lookup"><span data-stu-id="8bcde-127">Teams as the primary calling endpoint for the agents</span></span> 

  - <span data-ttu-id="8bcde-128">所有通話控制項的 Teams 用戶端通話</span><span class="sxs-lookup"><span data-stu-id="8bcde-128">Teams client calling for all the call controls</span></span>

  - <span data-ttu-id="8bcde-129">Teams Web 和行動用戶端的 Agent 體驗應用程式</span><span class="sxs-lookup"><span data-stu-id="8bcde-129">Agent experience app for both Teams web and mobile client</span></span>

  - <span data-ttu-id="8bcde-130">Teams 中 CCaaS 應用程式中的代理人分析、工作流程管理、角色型體驗</span><span class="sxs-lookup"><span data-stu-id="8bcde-130">Analytics, workflow management, role-based experiences for agents in the CCaaS app in Teams</span></span>

  - <span data-ttu-id="8bcde-131">與 Teams 用戶端整合的聊天和共同合作體驗</span><span class="sxs-lookup"><span data-stu-id="8bcde-131">Chat and collaboration experiences integrated with Teams clients</span></span> 

  - <span data-ttu-id="8bcde-132">在所有應用程式中保留 Teams 用戶端體驗的績效和品質</span><span class="sxs-lookup"><span data-stu-id="8bcde-132">Preserve performance and quality of Teams client experiences in all apps</span></span>  

### <a name="the-power-model"></a>[<span data-ttu-id="8bcde-133">**Power 模型**</span><span class="sxs-lookup"><span data-stu-id="8bcde-133">**The Power model**</span></span>](#tab/power)

<span data-ttu-id="8bcde-134">Power 模型可讓解決方案提供者使用 Teams 通話基礎結構和用戶端平臺建立原生 Azure 語音應用程式，以提供現代化智慧型解決方案，以用於共同操作的客戶和代理人員連接。</span><span class="sxs-lookup"><span data-stu-id="8bcde-134">The Power model enables solution providers to create native Azure-based voice applications using the Teams calling infrastructure and client platform to deliver modern, intelligent solutions for collaborative customer and agent connection.</span></span> <span data-ttu-id="8bcde-135">Power 模型的目標是提供單一應用程式、單螢幕聯絡中心體驗。</span><span class="sxs-lookup"><span data-stu-id="8bcde-135">The goal of the Power model is to provide a one-app, one-screen contact center experience.</span></span>

<span data-ttu-id="8bcde-136">**功能重點：**</span><span class="sxs-lookup"><span data-stu-id="8bcde-136">**Feature highlights:**</span></span>

<span data-ttu-id="8bcde-137">雖然這些功能不是此整合模型的功能全面清單，但焦點區域包括：</span><span class="sxs-lookup"><span data-stu-id="8bcde-137">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="8bcde-138">正式代理體驗原生啟用，透過 Teams SDK 進行全通道通訊</span><span class="sxs-lookup"><span data-stu-id="8bcde-138">Formal agent experiences natively enabled for omni-channel communication via Teams SDK</span></span> 

  - <span data-ttu-id="8bcde-139">使用 Teams 共同服務進行代理人共同合作和客戶互動</span><span class="sxs-lookup"><span data-stu-id="8bcde-139">Use Teams collaboration services for agent collaboration and customer interactions</span></span>  

  - <span data-ttu-id="8bcde-140">快速部署雲端服務，隨時隨地部署</span><span class="sxs-lookup"><span data-stu-id="8bcde-140">Rapid provisioning of cloud services, deploy anywhere</span></span> 

  - <span data-ttu-id="8bcde-141">在 Teams 交談期間直接進行交談控制及與使用者互動</span><span class="sxs-lookup"><span data-stu-id="8bcde-141">Direct conversation control and interaction with users during Teams conversations</span></span> 

>[!NOTE]
> <span data-ttu-id="8bcde-142">Power 模型將于 2021 年底提供。</span><span class="sxs-lookup"><span data-stu-id="8bcde-142">The Power model will be available towards the end of 2021.</span></span>
