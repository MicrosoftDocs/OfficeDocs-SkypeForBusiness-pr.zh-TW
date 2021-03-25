---
title: 在系統管理中心開始使用 Teams 製造範本
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
description: 瞭解如何使用。 使用系統管理中心提供預先定義的設定、頻道和預先安裝的 App，以建立專為製造需求設計的小組結構。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f5439cd8fdd053ab8444a1016eac94064638605
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120554"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-center"></a><span data-ttu-id="e1050-104">在系統管理中心使用 Teams 製造範本</span><span class="sxs-lookup"><span data-stu-id="e1050-104">Use Teams manufacturing templates in the admin center</span></span>

<span data-ttu-id="e1050-105">Teams 範本提供預先定義的設定、頻道和預先安裝應用程式範本，讓您快速且輕鬆地建立團隊。</span><span class="sxs-lookup"><span data-stu-id="e1050-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="e1050-106">Teams 範本有預先建立的團隊結構定義，專為製造需求所設計。</span><span class="sxs-lookup"><span data-stu-id="e1050-106">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="e1050-107">您也可以擴充 Teams 範本，以建立專為您特定組織需求量身打造的團隊。</span><span class="sxs-lookup"><span data-stu-id="e1050-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="e1050-108">本文介紹每個 Teams 範本，並建議如何使用這些範本。</span><span class="sxs-lookup"><span data-stu-id="e1050-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="e1050-109">如果您負責規劃、部署及管理整個製造組織的多個團隊，本文適合您閱讀。</span><span class="sxs-lookup"><span data-stu-id="e1050-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="e1050-110">您已在組織中部署 Teams 服務。</span><span class="sxs-lookup"><span data-stu-id="e1050-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="e1050-111">如果您尚未推出 Teams，請先閱讀[如何推出 Microsoft Teams](./deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e1050-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="e1050-112">如需深入了解一般 Teams 範本，請參閱 [Teams 範本入門](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="e1050-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="e1050-113">品質和安全性</span><span class="sxs-lookup"><span data-stu-id="e1050-113">Quality and safety</span></span>

<span data-ttu-id="e1050-114">與製造工廠小組集中通訊、存取資源，以及工廠作業。</span><span class="sxs-lookup"><span data-stu-id="e1050-114">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="e1050-115">包含政策與程式檔、訓練影片、安全注意事項、移轉程式。</span><span class="sxs-lookup"><span data-stu-id="e1050-115">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="e1050-116">基本範本類型</span><span class="sxs-lookup"><span data-stu-id="e1050-116">Base template type</span></span>|<span data-ttu-id="e1050-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="e1050-117">baseTemplateId</span></span>| <span data-ttu-id="e1050-118">此基本範本提供的屬性</span><span class="sxs-lookup"><span data-stu-id="e1050-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="e1050-119">品質和安全性</span><span class="sxs-lookup"><span data-stu-id="e1050-119">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="e1050-120">頻道：</span><span class="sxs-lookup"><span data-stu-id="e1050-120">Channels:</span></span> <ul><li><span data-ttu-id="e1050-121">一般</span><span class="sxs-lookup"><span data-stu-id="e1050-121">General</span></span><li><span data-ttu-id="e1050-122">公告</span><span class="sxs-lookup"><span data-stu-id="e1050-122">Announcements</span></span></li><li><span data-ttu-id="e1050-123">第 1 行</span><span class="sxs-lookup"><span data-stu-id="e1050-123">Line 1</span></span></li><li><span data-ttu-id="e1050-124">第 2 行</span><span class="sxs-lookup"><span data-stu-id="e1050-124">Line 2</span></span></li><li><span data-ttu-id="e1050-125">第 3 行</span><span class="sxs-lookup"><span data-stu-id="e1050-125">Line 3</span></span></li><li><span data-ttu-id="e1050-126">安全</span><span class="sxs-lookup"><span data-stu-id="e1050-126">Safety</span></span></li><li><span data-ttu-id="e1050-127">訓練</span><span class="sxs-lookup"><span data-stu-id="e1050-127">Training</span></span></li><li><span data-ttu-id="e1050-128">維護</span><span class="sxs-lookup"><span data-stu-id="e1050-128">Maintenance</span></span></li><li><span data-ttu-id="e1050-129">有趣的專案</span><span class="sxs-lookup"><span data-stu-id="e1050-129">Fun stuff</span></span></li></ul> <span data-ttu-id="e1050-130">應用程式：</span><span class="sxs-lookup"><span data-stu-id="e1050-130">Apps:</span></span> <ul><li><span data-ttu-id="e1050-131">Wiki</span><span class="sxs-lookup"><span data-stu-id="e1050-131">Wiki</span></span></li><li><span data-ttu-id="e1050-132">Planner</span><span class="sxs-lookup"><span data-stu-id="e1050-132">Planner</span></span></li></ul>|
||||