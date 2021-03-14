---
title: 在系統管理中心中使用 Teams 零售業範本
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用 Teams 範本，使用系統管理中心透過提供預先定義的設定、頻道和預先安裝的應用程式，以建立專為零售商需求設計的團隊結構。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b40da8fd1cc8182d0e5ad80c30f5a459f17d26f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662638"
---
# <a name="use-teams-retail-templates-in-the-admin-center"></a><span data-ttu-id="68979-103">在系統管理中心中使用 Teams 零售業範本</span><span class="sxs-lookup"><span data-stu-id="68979-103">Use Teams retail templates in the admin center</span></span>

<span data-ttu-id="68979-104">Teams 範本提供預先定義的設定、頻道和預先安裝應用程式範本，讓您快速且輕鬆地建立團隊。</span><span class="sxs-lookup"><span data-stu-id="68979-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="68979-105">Teams 範本具有專為零售商需求設計的團隊結構預先建立的定義。</span><span class="sxs-lookup"><span data-stu-id="68979-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="68979-106">您可以使用 Teams 範本快速建立適合零售商的團隊類型，並在整個組織中部署。</span><span class="sxs-lookup"><span data-stu-id="68979-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="68979-107">您也可以擴充 Teams 範本，以建立專為您特定組織需求量身打造的團隊。</span><span class="sxs-lookup"><span data-stu-id="68979-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="68979-108">本文將介紹各個 Teams 範本，並建議如何使用範本。</span><span class="sxs-lookup"><span data-stu-id="68979-108">In this article, we'll introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="68979-109">如果您負責規劃、部署和管理整個零售組織的多個團隊，本文適合您。</span><span class="sxs-lookup"><span data-stu-id="68979-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="68979-110">我們假定您已在組織中部署 Teams 服務。</span><span class="sxs-lookup"><span data-stu-id="68979-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="68979-111">如果您尚未推出 Teams，請先閱讀[如何推出 Microsoft Teams](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="68979-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="68979-112">如需深入了解一般 Teams 範本，請參閱 [Teams 範本入門](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="68979-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="organize-a-store"></a><span data-ttu-id="68979-113">組織商店</span><span class="sxs-lookup"><span data-stu-id="68979-113">Organize a store</span></span>

<span data-ttu-id="68979-114">將零售員工彙集在集中的體驗，以管理工作、共用文件及解決客戶問題。</span><span class="sxs-lookup"><span data-stu-id="68979-114">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="68979-115">整合其他應用程式，以簡化班次的開始與結束程序。</span><span class="sxs-lookup"><span data-stu-id="68979-115">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="68979-116">基本範本類型</span><span class="sxs-lookup"><span data-stu-id="68979-116">Base template type</span></span> |<span data-ttu-id="68979-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="68979-117">baseTemplateId</span></span> | <span data-ttu-id="68979-118">此基本範本提供的屬性</span><span class="sxs-lookup"><span data-stu-id="68979-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="68979-119">組織商店</span><span class="sxs-lookup"><span data-stu-id="68979-119">Organize a store</span></span>|`retailStore`|<span data-ttu-id="68979-120">頻道：</span><span class="sxs-lookup"><span data-stu-id="68979-120">Channels:</span></span> <ul><li><span data-ttu-id="68979-121">一般</span><span class="sxs-lookup"><span data-stu-id="68979-121">General</span></span><li><span data-ttu-id="68979-122">班次交班</span><span class="sxs-lookup"><span data-stu-id="68979-122">Shift handoff</span></span></li><li><span data-ttu-id="68979-123">學習</span><span class="sxs-lookup"><span data-stu-id="68979-123">Learning</span></span></li></ul> <span data-ttu-id="68979-124">應用程式：</span><span class="sxs-lookup"><span data-stu-id="68979-124">Apps:</span></span> <ul><li><span data-ttu-id="68979-125">Wiki</span><span class="sxs-lookup"><span data-stu-id="68979-125">Wiki</span></span></li></ul>|
||||

## <a name="manager-collaboration"></a><span data-ttu-id="68979-126">主管共同作業</span><span class="sxs-lookup"><span data-stu-id="68979-126">Manager Collaboration</span></span>

<span data-ttu-id="68979-127">管理員共同作業範本適合用來建立團隊，以讓一組主管跨商店及區域等進行共同作業。例如，如果您的組織有不同地區，您可以為加州地區建立主管共同作業團隊，並包含該區域的所有商店主管，以及該地區的地區主管。</span><span class="sxs-lookup"><span data-stu-id="68979-127">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="68979-128">基本範本類型</span><span class="sxs-lookup"><span data-stu-id="68979-128">Base template type</span></span>| <span data-ttu-id="68979-129">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="68979-129">baseTemplateId</span></span> | <span data-ttu-id="68979-130">此基本範本提供的屬性</span><span class="sxs-lookup"><span data-stu-id="68979-130">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="68979-131">零售 - 主管共同作業</span><span class="sxs-lookup"><span data-stu-id="68979-131">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="68979-132">頻道：</span><span class="sxs-lookup"><span data-stu-id="68979-132">Channels:</span></span> <ul><li><span data-ttu-id="68979-133">一般</span><span class="sxs-lookup"><span data-stu-id="68979-133">General</span></span><li><span data-ttu-id="68979-134">營運</span><span class="sxs-lookup"><span data-stu-id="68979-134">Operations</span></span></li><li><span data-ttu-id="68979-135">學習</span><span class="sxs-lookup"><span data-stu-id="68979-135">Learning</span></span></li></ul> <span data-ttu-id="68979-136">應用程式：</span><span class="sxs-lookup"><span data-stu-id="68979-136">Apps:</span></span> <ul><li><span data-ttu-id="68979-137">Wiki</span><span class="sxs-lookup"><span data-stu-id="68979-137">Wiki</span></span></li></ul>|
||||
