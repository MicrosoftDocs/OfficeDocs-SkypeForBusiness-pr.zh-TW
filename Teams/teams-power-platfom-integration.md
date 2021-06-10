---
title: Teams與 Microsoft Power Platform 的整合
author: cichur
ms.author: v-cichur
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
description: 瞭解如何Teams Microsoft Power Platform 工具的整合，包括 Power BI、Power App、Power 自動化Power Virtual Agents。
ms.openlocfilehash: c6442cd654dd8da6e26de048d50b7c80ef95cf26
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111039"
---
# <a name="teams-integration-with-microsoft-power-platform"></a><span data-ttu-id="8d0aa-103">Teams與 Microsoft Power Platform 的整合</span><span class="sxs-lookup"><span data-stu-id="8d0aa-103">Teams integration with Microsoft Power Platform</span></span>

<span data-ttu-id="8d0aa-104">Microsoft Power Platform 可協助使用者使用低程式碼工具加速開發，以使用 **Power BI** 分析資料、使用 Power Apps 建立自訂應用程式、使用 **Power Automate** 自動化程式，以及使用 Power Virtual Agents更快速地建立智慧型 bot。 </span><span class="sxs-lookup"><span data-stu-id="8d0aa-104">Microsoft Power Platform helps users accelerate their development with low-code tools to analyze data using **Power BI**, build custom apps using **Power Apps**, automate processes using **Power Automate**, and create intelligent bots using **Power Virtual Agents** more quickly than ever.</span></span> <span data-ttu-id="8d0aa-105">隨著遠端和混合式工作的轉移，Microsoft Teams讓世界各地的人員能夠繼續建立、共同作業及通訊。</span><span class="sxs-lookup"><span data-stu-id="8d0aa-105">With the shift to remote and hybrid work, Microsoft Teams has enabled people around the world to continue to create, collaborate, and communicate.</span></span> <span data-ttu-id="8d0aa-106">每天使用中使用者超過 7，500 萬Teams，這是人們完成工作的一個有效專案。</span><span class="sxs-lookup"><span data-stu-id="8d0aa-106">With more than 75 million daily active users, Teams is how people are getting work done.</span></span>

:::image type="content" source="media/teams-power-platform-integration.png" alt-text="Microsoft Power Platform Teams圖像摘要":::

<span data-ttu-id="8d0aa-108">Microsoft Power Platform 提供許多與 Teams 的整合功能，您可以在 **Teams** 工作區中內嵌 Power BI 報表、內嵌使用 **Power Apps** 建立的應用程式做為定位字元或個人應用程式、觸發任何訊息的 Power Automate 流程或使用介面卡，以及新增使用 **Power Virtual Agents** 建立 bot 到 Teams，讓貴組織的其他成員互動。</span><span class="sxs-lookup"><span data-stu-id="8d0aa-108">Microsoft Power Platform provides many integration capabilities with Teams where you can embed **Power BI** reports in the Teams workspace, embed apps created using **Power Apps** as a tab or personal app, trigger a **Power Automate** flow from any message or use adaptive cards, and add your bot created using **Power Virtual Agents** to Teams for other members of your organization to interact with.</span></span>

<span data-ttu-id="8d0aa-109">從 2020 年 9 月開始，與 Microsoft Power Platform 的整合已改善，讓使用者無需離開 Teams *介面即可執行下列操作*：</span><span class="sxs-lookup"><span data-stu-id="8d0aa-109">Starting September 2020, integration with Microsoft Power Platform has improved to let users do the following *without ever leaving the Teams interface*:</span></span>

- <span data-ttu-id="8d0aa-110">使用應用程式建立及共用儀表板、報表 **Power BI，以** 做出資料導向決策。</span><span class="sxs-lookup"><span data-stu-id="8d0aa-110">Create and share dashboards, reports, and apps using **Power BI** to make data-driven decisions.</span></span>
- <span data-ttu-id="8d0aa-111">使用整合 **式 Power Apps** 工作室建立及共用低程式碼、用途型應用程式，透過連接器連接至儲存在新基礎資料平臺 (Microsoft Dataverse Teams) 、Microsoft 365 或其他資料來源中的商務資料。</span><span class="sxs-lookup"><span data-stu-id="8d0aa-111">Create and share low-code, purpose-built apps using an integrated **Power Apps** studio by connecting to your business data stored either in the new underlying data platform (Microsoft Dataverse for Teams), Microsoft 365, or in other data sources through connectors.</span></span>
- <span data-ttu-id="8d0aa-112">在應用程式和服務之間建立自動化工作流程，以同步處理檔案、取得通知、**收集資料**，以及使用 Power Automate。</span><span class="sxs-lookup"><span data-stu-id="8d0aa-112">Create automated workflows between your apps and services to synchronize files, get notifications, collect data, and more using **Power Automate**.</span></span>
- <span data-ttu-id="8d0aa-113">使用引導式無程式碼圖形介面Power Virtual Agents建立 bot，輕鬆地在 Teams 中建立數位助理，並可供同事聊天。</span><span class="sxs-lookup"><span data-stu-id="8d0aa-113">Build bots using a guided, no-code graphical interface using **Power Virtual Agents** to easily create digital assistants within Teams and make them available to your colleagues to chat with.</span></span>

<span data-ttu-id="8d0aa-114">Teams、Teams 版[Dataverse](/powerapps/teams/overview-data-platform)的新內建、低程式碼資料平臺支援建立應用程式、Bot 和工作流程的新功能，提供關聯式資料儲存、豐富的資料類型、企業級管理，以及單鍵解決方案部署。</span><span class="sxs-lookup"><span data-stu-id="8d0aa-114">The new capabilities to create apps, bots, and workflows are backed by the new built-in, low-code data platform for Teams, [Dataverse for Teams](/powerapps/teams/overview-data-platform), which provides relational data storage, rich data types, enterprise grade governance, and one-click solution deployment.</span></span> <span data-ttu-id="8d0aa-115">適用于 Teams 的 Dataverse 是建置在[Microsoft Dataverse 的頂端](/powerapps/maker/common-data-service/data-platform-intro)。</span><span class="sxs-lookup"><span data-stu-id="8d0aa-115">Dataverse for Teams is built on top of [Microsoft Dataverse](/powerapps/maker/common-data-service/data-platform-intro).</span></span> <span data-ttu-id="8d0aa-116">有了 Dataverse for Teams，Teams使用者可以從展示跨產業常見案例的 Teams App Store 中尋找並安裝自訂且現成使用的解決方案。</span><span class="sxs-lookup"><span data-stu-id="8d0aa-116">With Dataverse for Teams, Teams users can find and install custom, ready-to-use solutions from the Teams app store that showcase common scenarios across industries.</span></span> <span data-ttu-id="8d0aa-117">您可以自訂和延伸這些自訂解決方案，以調整組織的品牌和需求。</span><span class="sxs-lookup"><span data-stu-id="8d0aa-117">You can customize and extend these custom solutions to adapt to your organization's branding and requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="8d0aa-118">授權</span><span class="sxs-lookup"><span data-stu-id="8d0aa-118">Licensing</span></span>

<span data-ttu-id="8d0aa-119">新功能可供選取訂閱Microsoft 365使用。</span><span class="sxs-lookup"><span data-stu-id="8d0aa-119">The new capabilities are available to the select Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="8d0aa-120">如要進一Power Apps、Power Automate、Power Virtual Agents和 Dataverse Teams授權需求，請參閱[授權](/power-platform/admin/about-teams-environment)。</span><span class="sxs-lookup"><span data-stu-id="8d0aa-120">For more information about licensing requirements for Power Apps, Power Automate, Power Virtual Agents, and Dataverse for Teams, see [Licensing](/power-platform/admin/about-teams-environment).</span></span>
- <span data-ttu-id="8d0aa-121">如想進一Power BI授權需求，請參閱[需求](/power-bi/collaborate-share/service-collaborate-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="8d0aa-121">For more information about licensing requirements for Power BI, see [Requirements](/power-bi/collaborate-share/service-collaborate-microsoft-teams).</span></span>
 
## <a name="how-do-i-get-started"></a><span data-ttu-id="8d0aa-122">如何開始使用？</span><span class="sxs-lookup"><span data-stu-id="8d0aa-122">How do I get started?</span></span>

- [<span data-ttu-id="8d0aa-123">Power BI和Teams</span><span class="sxs-lookup"><span data-stu-id="8d0aa-123">Power BI and Teams</span></span>](/power-bi/collaborate-share/service-collaborate-microsoft-teams)
- [<span data-ttu-id="8d0aa-124">Power Apps和Teams</span><span class="sxs-lookup"><span data-stu-id="8d0aa-124">Power Apps and Teams</span></span>](/powerapps/teams/overview)
- [<span data-ttu-id="8d0aa-125">Power Automate Teams</span><span class="sxs-lookup"><span data-stu-id="8d0aa-125">Power Automate and Teams</span></span>](/power-automate/teams/overview)
- [<span data-ttu-id="8d0aa-126">Power Virtual Agents Teams</span><span class="sxs-lookup"><span data-stu-id="8d0aa-126">Power Virtual Agents and Teams</span></span>](/power-virtual-agents/teams/fundamentals-what-is-power-virtual-agents-teams)