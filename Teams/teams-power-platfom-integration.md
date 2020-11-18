---
title: 團隊與 Microsoft Power Platform 整合
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: kvivek
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: 瞭解團隊與 Microsoft Power Platform 工具整合的相關資訊，包括 Power BI、Power app、Power 自動化及 Power Virtual Agent。
ms.openlocfilehash: 81d673069e972f4627a8bfab18095e81803dd4b1
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085672"
---
# <a name="teams-integration-with-microsoft-power-platform"></a><span data-ttu-id="143c3-103">團隊與 Microsoft Power Platform 整合</span><span class="sxs-lookup"><span data-stu-id="143c3-103">Teams integration with Microsoft Power Platform</span></span>

<span data-ttu-id="143c3-104">Microsoft Power Platform 可協助使用者使用低代碼工具加速開發，以使用 **POWER BI** 來分析資料、使用 **power app** 建立自訂應用程式、使用 **power** Virtual 自動執行程式，以及使用 **power Virtual agent** 來更快速地建立智慧型機器人。</span><span class="sxs-lookup"><span data-stu-id="143c3-104">Microsoft Power Platform helps users accelerate their development with low-code tools to analyze data using **Power BI**, build custom apps using **Power Apps**, automate processes using **Power Automate**, and create intelligent bots using **Power Virtual Agents** more quickly than ever.</span></span> <span data-ttu-id="143c3-105">隨著行動在遠端和混合式工作上，Microsoft 團隊已讓世界各地的人員繼續建立、共同作業及溝通。</span><span class="sxs-lookup"><span data-stu-id="143c3-105">With the shift to remote and hybrid work, Microsoft Teams has enabled people around the world to continue to create, collaborate, and communicate.</span></span> <span data-ttu-id="143c3-106">使用超過75000000的每日作用中使用者，小組就是人們如何完成工作。</span><span class="sxs-lookup"><span data-stu-id="143c3-106">With more than 75 million daily active users, Teams is how people are getting work done.</span></span>

:::image type="content" source="media/teams-power-platform-integration.png" alt-text="摘要小組與 Microsoft Power Platform 的影像":::

<span data-ttu-id="143c3-108">Microsoft Power Platform 提供大量的整合功能，讓您可以將 **POWER BI** 報表內嵌于 [團隊] 工作區、使用 **power** app 做為索引標籤或個人應用程式 **建立的應用** 程式，並將使用 **power Virtual agent** 建立的 bot，新增到您組織中其他成員的小組中進行互動。</span><span class="sxs-lookup"><span data-stu-id="143c3-108">Microsoft Power Platform provides many integration capabilities with Teams where you can embed **Power BI** reports in the Teams workspace, embed apps created using **Power Apps** as a tab or personal app, trigger a **Power Automate** flow from any message or use adaptive cards, and add your bot created using **Power Virtual Agents** to Teams for other members of your organization to interact with.</span></span>

<span data-ttu-id="143c3-109">從2020年9月開始，與 Microsoft Power Platform 整合已改良，讓使用者可以執行下列動作， *而不需離開團隊介面*：</span><span class="sxs-lookup"><span data-stu-id="143c3-109">Starting September 2020, integration with Microsoft Power Platform has improved to let users do the following *without ever leaving the Teams interface*:</span></span>

- <span data-ttu-id="143c3-110">使用 **POWER BI** 建立及共用儀表板、報表及應用程式，以進行資料導向決策。</span><span class="sxs-lookup"><span data-stu-id="143c3-110">Create and share dashboards, reports, and apps using **Power BI** to make data-driven decisions.</span></span>
- <span data-ttu-id="143c3-111">您 (可以透過連接器，透過連線至團隊) 、Microsoft 365 或其他資料來源的 Microsoft Dataverse，來建立並共用低代碼、專門建立的應用程式，並使用整合的 **Power app** studio 來建立。</span><span class="sxs-lookup"><span data-stu-id="143c3-111">Create and share low-code, purpose-built apps using an integrated **Power Apps** studio by connecting to your business data stored either in the new underlying data platform (Microsoft Dataverse for Teams), Microsoft 365, or in other data sources through connectors.</span></span>
- <span data-ttu-id="143c3-112">在您的應用程式和服務之間建立自動化工作流程，以同步處理檔案、取得通知、收集資料，以及使用 **Power 自動化等功能**。</span><span class="sxs-lookup"><span data-stu-id="143c3-112">Create automated workflows between your apps and services to synchronize files, get notifications, collect data, and more using **Power Automate**.</span></span>
- <span data-ttu-id="143c3-113">使用 **Power Virtual agent** 來建立 bot，使用無程式的程式碼圖形介面，輕鬆地在團隊中建立數位助手，並讓您的同事可以與他們交談。</span><span class="sxs-lookup"><span data-stu-id="143c3-113">Build bots using a guided, no-code graphical interface using **Power Virtual Agents** to easily create digital assistants within Teams and make them available to your colleagues to chat with.</span></span>

<span data-ttu-id="143c3-114">建立應用程式、機器人及工作流程的新 [功能，是](https://go.microsoft.com/fwlink/?linkid=2143541)由新的內建、低代碼資料平臺供團隊使用，可提供關聯式資料儲存、豐富資料類型、企業評分管理，以及一次按一下方案部署。</span><span class="sxs-lookup"><span data-stu-id="143c3-114">The new capabilities to create apps, bots, and workflows are backed by the new built-in, low-code data platform for Teams, [Dataverse for Teams](https://go.microsoft.com/fwlink/?linkid=2143541), which provides relational data storage, rich data types, enterprise grade governance, and one-click solution deployment.</span></span> <span data-ttu-id="143c3-115">小組的 Dataverse 是以 [Microsoft Dataverse](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)為基礎。</span><span class="sxs-lookup"><span data-stu-id="143c3-115">Dataverse for Teams is built on top of [Microsoft Dataverse](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span> <span data-ttu-id="143c3-116">透過針對團隊的 Dataverse，小組使用者可以從在各行業中展示常見案例的小組 app 商店找到並安裝自訂且可供使用的解決方案。</span><span class="sxs-lookup"><span data-stu-id="143c3-116">With Dataverse for Teams, Teams users can find and install custom, ready-to-use solutions from the Teams app store that showcase common scenarios across industries.</span></span> <span data-ttu-id="143c3-117">您可以自訂及延伸這些自訂解決方案，以適應貴組織的品牌與需求。</span><span class="sxs-lookup"><span data-stu-id="143c3-117">You can customize and extend these custom solutions to adapt to your organization's branding and requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="143c3-118">授權</span><span class="sxs-lookup"><span data-stu-id="143c3-118">Licensing</span></span>

<span data-ttu-id="143c3-119">[選取 Microsoft 365 訂閱] 可使用新功能。</span><span class="sxs-lookup"><span data-stu-id="143c3-119">The new capabilities are available to the select Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="143c3-120">如需 Power App 授權需求、Power 自動化、Power Virtual Agent 及 Dataverse for 團隊的詳細資訊，請參閱 [授權](https://go.microsoft.com/fwlink/?linkid=2143647)。</span><span class="sxs-lookup"><span data-stu-id="143c3-120">For more information about licensing requirements for Power Apps, Power Automate, Power Virtual Agents, and Dataverse for Teams, see [Licensing](https://go.microsoft.com/fwlink/?linkid=2143647).</span></span>
- <span data-ttu-id="143c3-121">如需 Power BI 授權需求的詳細資訊，請參閱 [需求](https://go.microsoft.com/fwlink/?linkid=2143490)。</span><span class="sxs-lookup"><span data-stu-id="143c3-121">For more information about licensing requirements for Power BI, see [Requirements](https://go.microsoft.com/fwlink/?linkid=2143490).</span></span>
 
## <a name="how-do-i-get-started"></a><span data-ttu-id="143c3-122">我要如何開始？</span><span class="sxs-lookup"><span data-stu-id="143c3-122">How do I get started?</span></span>

- [<span data-ttu-id="143c3-123">Power BI 與團隊</span><span class="sxs-lookup"><span data-stu-id="143c3-123">Power BI and Teams</span></span>](https://aka.ms/pbi-teams-docs)
- [<span data-ttu-id="143c3-124">Power App 與團隊</span><span class="sxs-lookup"><span data-stu-id="143c3-124">Power Apps and Teams</span></span>](https://aka.ms/pa-teams-docs)
- [<span data-ttu-id="143c3-125">電源自動化與團隊</span><span class="sxs-lookup"><span data-stu-id="143c3-125">Power Automate and Teams</span></span>](https://aka.ms/pauto-teams-docs)
- [<span data-ttu-id="143c3-126">Power Virtual Agent 與團隊</span><span class="sxs-lookup"><span data-stu-id="143c3-126">Power Virtual Agents and Teams</span></span>](https://aka.ms/pva-teams-docs)
