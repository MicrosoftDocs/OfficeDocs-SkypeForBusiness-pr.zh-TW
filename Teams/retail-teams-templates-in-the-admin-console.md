---
title: 在管理員主控台中使用團隊零售範本
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
description: 瞭解如何使用 [團隊範本]，透過使用管理主控台提供預先定義的設定、通道及預先安裝應用程式，來建立專為零售商需求而設計的小組結構。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a7cdac4b64f8a6fb10f3b36544e3361b6c413ad7
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/19/2020
ms.locfileid: "48136029"
---
# <a name="use-teams-retail-templates-in-the-admin-console"></a><span data-ttu-id="5106e-103">在管理員主控台中使用團隊零售範本</span><span class="sxs-lookup"><span data-stu-id="5106e-103">Use Teams retail templates in the admin console</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="5106e-104">團隊範本可讓您透過提供預先定義的設定、通道及預先安裝應用程式範本，快速且輕鬆地建立團隊。</span><span class="sxs-lookup"><span data-stu-id="5106e-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="5106e-105">團隊範本擁有圍繞零售商需求設計之小組結構的預先建立的定義。</span><span class="sxs-lookup"><span data-stu-id="5106e-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="5106e-106">您可以使用團隊範本快速建立適用于零售商的團隊類型，並在整個組織中進行部署。</span><span class="sxs-lookup"><span data-stu-id="5106e-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="5106e-107">您也可以延伸團隊範本，建立專為您特定組織需求量身定制的小組。</span><span class="sxs-lookup"><span data-stu-id="5106e-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="5106e-108">在本文中，我們將介紹每個團隊範本，以及我們建議使用這些範本的方式。</span><span class="sxs-lookup"><span data-stu-id="5106e-108">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="5106e-109">如果您負責規劃、部署及管理多個零售組織中的多個小組，本文適用于您。</span><span class="sxs-lookup"><span data-stu-id="5106e-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="5106e-110">我們假設您已在貴組織中已部署團隊服務。</span><span class="sxs-lookup"><span data-stu-id="5106e-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="5106e-111">如果您還沒有推出小組，請先閱讀 [如何推出 Microsoft 團隊](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="5106e-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="5106e-112">若要深入瞭解小組範本的整體資訊，請參閱 [開始使用團隊範本](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="5106e-112">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="organize-a-store"></a><span data-ttu-id="5106e-113">整理商店</span><span class="sxs-lookup"><span data-stu-id="5106e-113">Organize a store</span></span>

<span data-ttu-id="5106e-114">將您的零售員工集中在一個集中體驗中，以管理工作、共用文件並解決客戶問題。</span><span class="sxs-lookup"><span data-stu-id="5106e-114">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="5106e-115">整合其他應用程式，以簡化倒班開始 & 結束程式。</span><span class="sxs-lookup"><span data-stu-id="5106e-115">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="5106e-116">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="5106e-116">Base template type</span></span>| | <span data-ttu-id="5106e-117">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="5106e-117">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="5106e-118">整理商店</span><span class="sxs-lookup"><span data-stu-id="5106e-118">Organize a store</span></span>| `retailStore`|<span data-ttu-id="5106e-119">管道</span><span class="sxs-lookup"><span data-stu-id="5106e-119">Channels:</span></span> <ul><li><span data-ttu-id="5106e-120">一般</span><span class="sxs-lookup"><span data-stu-id="5106e-120">General</span></span><li><span data-ttu-id="5106e-121">倒班切換</span><span class="sxs-lookup"><span data-stu-id="5106e-121">Shift handoff</span></span></li><li><span data-ttu-id="5106e-122">教學</span><span class="sxs-lookup"><span data-stu-id="5106e-122">Learning</span></span></li></ul> <span data-ttu-id="5106e-123">應用</span><span class="sxs-lookup"><span data-stu-id="5106e-123">Apps:</span></span> <ul><li><span data-ttu-id="5106e-124">Wiki</span><span class="sxs-lookup"><span data-stu-id="5106e-124">Wiki</span></span></li></ul>|
||||

## <a name="manager-collaboration"></a><span data-ttu-id="5106e-125">Manager 共同作業</span><span class="sxs-lookup"><span data-stu-id="5106e-125">Manager Collaboration</span></span>

<span data-ttu-id="5106e-126">Manager 共同工作範本適用于為一組主管建立小組，以便在商店/地區等共同作業。例如，如果您的組織有地區，您可以為加利福尼亞地區建立經理共同作業小組，並包含該地區的所有書店管理員，以及該地區的地區經理。</span><span class="sxs-lookup"><span data-stu-id="5106e-126">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="5106e-127">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="5106e-127">Base template type</span></span>|  | <span data-ttu-id="5106e-128">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="5106e-128">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="5106e-129">零售經理共同作業</span><span class="sxs-lookup"><span data-stu-id="5106e-129">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="5106e-130">管道</span><span class="sxs-lookup"><span data-stu-id="5106e-130">Channels:</span></span> <ul><li><span data-ttu-id="5106e-131">一般</span><span class="sxs-lookup"><span data-stu-id="5106e-131">General</span></span><li><span data-ttu-id="5106e-132">營運</span><span class="sxs-lookup"><span data-stu-id="5106e-132">Operations</span></span></li><li><span data-ttu-id="5106e-133">教學</span><span class="sxs-lookup"><span data-stu-id="5106e-133">Learning</span></span></li></ul> <span data-ttu-id="5106e-134">應用</span><span class="sxs-lookup"><span data-stu-id="5106e-134">Apps:</span></span> <ul><li><span data-ttu-id="5106e-135">Wiki</span><span class="sxs-lookup"><span data-stu-id="5106e-135">Wiki</span></span></li></ul>|
||||

