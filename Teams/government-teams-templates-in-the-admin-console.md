---
title: 在系統管理中心使用團隊政府範本
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
description: 瞭解如何使用。 團隊範本：使用系統管理中心提供預先定義的設定、頻道及預先安裝的 app，以建立專為政府需求設計的小組結構。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: db0d8fa4a2744f0f3c3591918230e3f569727ae7
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662198"
---
# <a name="use-teams-government-templates-in-the-admin-center"></a><span data-ttu-id="00153-104">在系統管理中心使用團隊政府範本</span><span class="sxs-lookup"><span data-stu-id="00153-104">Use Teams government templates in the admin center</span></span>

<span data-ttu-id="00153-105">團隊範本可讓您透過提供預先定義的設定、通道及預先安裝應用程式範本，快速且輕鬆地建立團隊。</span><span class="sxs-lookup"><span data-stu-id="00153-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="00153-106">團隊範本有預先建立的小組結構定義，專為政府需求而設計。</span><span class="sxs-lookup"><span data-stu-id="00153-106">Teams templates have pre-built definitions of team structures designed around governmental needs.</span></span> <span data-ttu-id="00153-107">您也可以延伸團隊範本，建立專為您特定組織需求量身定制的小組。</span><span class="sxs-lookup"><span data-stu-id="00153-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="00153-108">在本文中，我們將介紹每個團隊範本，並建議如何使用它們。</span><span class="sxs-lookup"><span data-stu-id="00153-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="00153-109">本文適用于您負責規劃、部署及管理政府組織中的多個小組。</span><span class="sxs-lookup"><span data-stu-id="00153-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your governmental organization.</span></span> <span data-ttu-id="00153-110">您已在組織中部署團隊服務。</span><span class="sxs-lookup"><span data-stu-id="00153-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="00153-111">如果您還沒有推出小組，請先閱讀 [如何推出 Microsoft 團隊](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="00153-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="00153-112">若要深入瞭解小組範本的整體資訊，請參閱 [開始使用團隊範本](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="00153-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="coordinate-incident-response"></a><span data-ttu-id="00153-113">協調事件回應</span><span class="sxs-lookup"><span data-stu-id="00153-113">Coordinate incident response</span></span>

<span data-ttu-id="00153-114">針對危機管理或事件回應小組集中溝通與重要資源。</span><span class="sxs-lookup"><span data-stu-id="00153-114">Centralize communication and critical resources for your crisis management or incident response team.</span></span> <span data-ttu-id="00153-115">在這個小組中，您可以加入許多不同類型的檔案，協助您為所有檔建立一個集中位置。</span><span class="sxs-lookup"><span data-stu-id="00153-115">Within this team, you can include many different types of files to help create a central place for all your documents.</span></span> <span data-ttu-id="00153-116">使用線上會議來改善資訊流與形勢感知。</span><span class="sxs-lookup"><span data-stu-id="00153-116">Use online meetings to improve information flow and situational awareness.</span></span>

| <span data-ttu-id="00153-117">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="00153-117">Base template type</span></span> |<span data-ttu-id="00153-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="00153-118">baseTemplateId</span></span> | <span data-ttu-id="00153-119">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="00153-119">Properties that come with this base template</span></span> |
|-------------------|-------|---------------------------------------------------------------------------|
|<span data-ttu-id="00153-120">協調事件回應</span><span class="sxs-lookup"><span data-stu-id="00153-120">Coordinate incident response</span></span>|`com.microsoft.teams.template.CoordinateIncidentResponse`|<span data-ttu-id="00153-121">管道</span><span class="sxs-lookup"><span data-stu-id="00153-121">Channels:</span></span> <ul><li><span data-ttu-id="00153-122">一般</span><span class="sxs-lookup"><span data-stu-id="00153-122">General</span></span><li><span data-ttu-id="00153-123">公告</span><span class="sxs-lookup"><span data-stu-id="00153-123">Announcements</span></span></li><li><span data-ttu-id="00153-124">物流</span><span class="sxs-lookup"><span data-stu-id="00153-124">Logistics</span></span></li><li><span data-ttu-id="00153-125">規劃</span><span class="sxs-lookup"><span data-stu-id="00153-125">Planning</span></span></li><li><span data-ttu-id="00153-126">修復</span><span class="sxs-lookup"><span data-stu-id="00153-126">Recovery</span></span></li><li><span data-ttu-id="00153-127">非常</span><span class="sxs-lookup"><span data-stu-id="00153-127">Urgent</span></span></li></ul> <span data-ttu-id="00153-128">應用</span><span class="sxs-lookup"><span data-stu-id="00153-128">Apps:</span></span> <ul><li><span data-ttu-id="00153-129">Wiki</span><span class="sxs-lookup"><span data-stu-id="00153-129">Wiki</span></span></li><li><span data-ttu-id="00153-130">Excel</span><span class="sxs-lookup"><span data-stu-id="00153-130">Excel</span></span></li><li><span data-ttu-id="00153-131">OneNote</span><span class="sxs-lookup"><span data-stu-id="00153-131">OneNote</span></span></li><li><span data-ttu-id="00153-132">SharePoint</span><span class="sxs-lookup"><span data-stu-id="00153-132">SharePoint</span></span></li><li><span data-ttu-id="00153-133">Planner</span><span class="sxs-lookup"><span data-stu-id="00153-133">Planner</span></span></li></ul>|
||||