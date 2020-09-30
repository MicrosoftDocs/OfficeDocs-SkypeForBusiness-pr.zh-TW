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
ms.openlocfilehash: 77411e734ebbcfaea4d3e2a0454f48e43a8b8a7d
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308326"
---
# <a name="use-teams-retail-templates-in-the-admin-console"></a><span data-ttu-id="24813-103">在管理員主控台中使用團隊零售範本</span><span class="sxs-lookup"><span data-stu-id="24813-103">Use Teams retail templates in the admin console</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="24813-104">團隊範本可讓您透過提供預先定義的設定、通道及預先安裝應用程式範本，快速且輕鬆地建立團隊。</span><span class="sxs-lookup"><span data-stu-id="24813-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="24813-105">團隊範本擁有圍繞零售商需求設計之小組結構的預先建立的定義。</span><span class="sxs-lookup"><span data-stu-id="24813-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="24813-106">您可以使用團隊範本快速建立適用于零售商的團隊類型，並在整個組織中進行部署。</span><span class="sxs-lookup"><span data-stu-id="24813-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="24813-107">您也可以延伸團隊範本，建立專為您特定組織需求量身定制的小組。</span><span class="sxs-lookup"><span data-stu-id="24813-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="24813-108">在本文中，我們將介紹每個團隊範本，以及我們建議使用這些範本的方式。</span><span class="sxs-lookup"><span data-stu-id="24813-108">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="24813-109">如果您負責規劃、部署及管理多個零售組織中的多個小組，本文適用于您。</span><span class="sxs-lookup"><span data-stu-id="24813-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="24813-110">我們假設您已在貴組織中已部署團隊服務。</span><span class="sxs-lookup"><span data-stu-id="24813-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="24813-111">如果您還沒有推出小組，請先閱讀 [如何推出 Microsoft 團隊](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="24813-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="24813-112">若要深入瞭解小組範本的整體資訊，請參閱 [開始使用團隊範本](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="24813-112">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="organize-a-store"></a><span data-ttu-id="24813-113">整理商店</span><span class="sxs-lookup"><span data-stu-id="24813-113">Organize a store</span></span>

<span data-ttu-id="24813-114">將您的零售員工集中在一個集中體驗中，以管理工作、共用文件並解決客戶問題。</span><span class="sxs-lookup"><span data-stu-id="24813-114">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="24813-115">整合其他應用程式，以簡化倒班開始 & 結束程式。</span><span class="sxs-lookup"><span data-stu-id="24813-115">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="24813-116">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="24813-116">Base template type</span></span> |<span data-ttu-id="24813-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="24813-117">baseTemplateId</span></span> | <span data-ttu-id="24813-118">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="24813-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="24813-119">整理商店</span><span class="sxs-lookup"><span data-stu-id="24813-119">Organize a store</span></span>| `retailStore`|<span data-ttu-id="24813-120">管道</span><span class="sxs-lookup"><span data-stu-id="24813-120">Channels:</span></span> <ul><li><span data-ttu-id="24813-121">一般</span><span class="sxs-lookup"><span data-stu-id="24813-121">General</span></span><li><span data-ttu-id="24813-122">倒班切換</span><span class="sxs-lookup"><span data-stu-id="24813-122">Shift handoff</span></span></li><li><span data-ttu-id="24813-123">教學</span><span class="sxs-lookup"><span data-stu-id="24813-123">Learning</span></span></li></ul> <span data-ttu-id="24813-124">應用</span><span class="sxs-lookup"><span data-stu-id="24813-124">Apps:</span></span> <ul><li><span data-ttu-id="24813-125">Wiki</span><span class="sxs-lookup"><span data-stu-id="24813-125">Wiki</span></span></li></ul>|
||||

## <a name="manager-collaboration"></a><span data-ttu-id="24813-126">Manager 共同作業</span><span class="sxs-lookup"><span data-stu-id="24813-126">Manager Collaboration</span></span>

<span data-ttu-id="24813-127">Manager 共同工作範本適用于為一組主管建立小組，以便在商店/地區等共同作業。例如，如果您的組織有地區，您可以為加利福尼亞地區建立經理共同作業小組，並包含該地區的所有書店管理員，以及該地區的地區經理。</span><span class="sxs-lookup"><span data-stu-id="24813-127">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="24813-128">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="24813-128">Base template type</span></span>| <span data-ttu-id="24813-129">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="24813-129">baseTemplateId</span></span> | <span data-ttu-id="24813-130">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="24813-130">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="24813-131">零售經理共同作業</span><span class="sxs-lookup"><span data-stu-id="24813-131">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="24813-132">管道</span><span class="sxs-lookup"><span data-stu-id="24813-132">Channels:</span></span> <ul><li><span data-ttu-id="24813-133">一般</span><span class="sxs-lookup"><span data-stu-id="24813-133">General</span></span><li><span data-ttu-id="24813-134">營運</span><span class="sxs-lookup"><span data-stu-id="24813-134">Operations</span></span></li><li><span data-ttu-id="24813-135">教學</span><span class="sxs-lookup"><span data-stu-id="24813-135">Learning</span></span></li></ul> <span data-ttu-id="24813-136">應用</span><span class="sxs-lookup"><span data-stu-id="24813-136">Apps:</span></span> <ul><li><span data-ttu-id="24813-137">Wiki</span><span class="sxs-lookup"><span data-stu-id="24813-137">Wiki</span></span></li></ul>|
||||
