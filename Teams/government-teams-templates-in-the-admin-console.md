---
title: 在系統管理中心使用 Teams 政府範本
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
description: 瞭解如何使用。 使用系統管理中心提供預先定義的設定、頻道和預先安裝的 App，以建立專為政府需求設計的小組結構。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: db22de142b9e7f2bead93e607dd01c9dd362ddba
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092211"
---
# <a name="use-teams-government-templates-in-the-admin-center"></a><span data-ttu-id="8be3b-104">在系統管理中心使用 Teams 政府範本</span><span class="sxs-lookup"><span data-stu-id="8be3b-104">Use Teams government templates in the admin center</span></span>

<span data-ttu-id="8be3b-105">Teams 範本提供預先定義的設定、頻道和預先安裝應用程式範本，讓您快速且輕鬆地建立團隊。</span><span class="sxs-lookup"><span data-stu-id="8be3b-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="8be3b-106">Teams 範本有預先建立的團隊結構定義，專為政府需求所設計。</span><span class="sxs-lookup"><span data-stu-id="8be3b-106">Teams templates have pre-built definitions of team structures designed around governmental needs.</span></span> <span data-ttu-id="8be3b-107">您也可以擴充 Teams 範本，以建立專為您特定組織需求量身打造的團隊。</span><span class="sxs-lookup"><span data-stu-id="8be3b-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="8be3b-108">本文介紹每個 Teams 範本，並建議如何使用這些範本。</span><span class="sxs-lookup"><span data-stu-id="8be3b-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="8be3b-109">如果您負責規劃、部署及管理整個政府組織的多個團隊，本文適合您閱讀。</span><span class="sxs-lookup"><span data-stu-id="8be3b-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your governmental organization.</span></span> <span data-ttu-id="8be3b-110">您已在組織中部署 Teams 服務。</span><span class="sxs-lookup"><span data-stu-id="8be3b-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="8be3b-111">如果您尚未推出 Teams，請先閱讀[如何推出 Microsoft Teams](./deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="8be3b-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="8be3b-112">如需深入了解一般 Teams 範本，請參閱 [Teams 範本入門](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="8be3b-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="coordinate-incident-response"></a><span data-ttu-id="8be3b-113">協調事件回應</span><span class="sxs-lookup"><span data-stu-id="8be3b-113">Coordinate incident response</span></span>

<span data-ttu-id="8be3b-114">集中溝通和重要資源，以管理您的緊急事件或事件回應小組。</span><span class="sxs-lookup"><span data-stu-id="8be3b-114">Centralize communication and critical resources for your crisis management or incident response team.</span></span> <span data-ttu-id="8be3b-115">在這個小組中，您可以包含許多不同類型的檔案，協助建立所有檔的中央位置。</span><span class="sxs-lookup"><span data-stu-id="8be3b-115">Within this team, you can include many different types of files to help create a central place for all your documents.</span></span> <span data-ttu-id="8be3b-116">使用線上會議改善資訊流程及情境認知度。</span><span class="sxs-lookup"><span data-stu-id="8be3b-116">Use online meetings to improve information flow and situational awareness.</span></span>

| <span data-ttu-id="8be3b-117">基本範本類型</span><span class="sxs-lookup"><span data-stu-id="8be3b-117">Base template type</span></span> |<span data-ttu-id="8be3b-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="8be3b-118">baseTemplateId</span></span> | <span data-ttu-id="8be3b-119">此基本範本提供的屬性</span><span class="sxs-lookup"><span data-stu-id="8be3b-119">Properties that come with this base template</span></span> |
|-------------------|-------|---------------------------------------------------------------------------|
|<span data-ttu-id="8be3b-120">協調事件回應</span><span class="sxs-lookup"><span data-stu-id="8be3b-120">Coordinate incident response</span></span>|`com.microsoft.teams.template.CoordinateIncidentResponse`|<span data-ttu-id="8be3b-121">頻道：</span><span class="sxs-lookup"><span data-stu-id="8be3b-121">Channels:</span></span> <ul><li><span data-ttu-id="8be3b-122">一般</span><span class="sxs-lookup"><span data-stu-id="8be3b-122">General</span></span><li><span data-ttu-id="8be3b-123">公告</span><span class="sxs-lookup"><span data-stu-id="8be3b-123">Announcements</span></span></li><li><span data-ttu-id="8be3b-124">物流</span><span class="sxs-lookup"><span data-stu-id="8be3b-124">Logistics</span></span></li><li><span data-ttu-id="8be3b-125">規劃</span><span class="sxs-lookup"><span data-stu-id="8be3b-125">Planning</span></span></li><li><span data-ttu-id="8be3b-126">恢復</span><span class="sxs-lookup"><span data-stu-id="8be3b-126">Recovery</span></span></li><li><span data-ttu-id="8be3b-127">緊急</span><span class="sxs-lookup"><span data-stu-id="8be3b-127">Urgent</span></span></li></ul> <span data-ttu-id="8be3b-128">應用程式：</span><span class="sxs-lookup"><span data-stu-id="8be3b-128">Apps:</span></span> <ul><li><span data-ttu-id="8be3b-129">Wiki</span><span class="sxs-lookup"><span data-stu-id="8be3b-129">Wiki</span></span></li><li><span data-ttu-id="8be3b-130">Excel</span><span class="sxs-lookup"><span data-stu-id="8be3b-130">Excel</span></span></li><li><span data-ttu-id="8be3b-131">OneNote</span><span class="sxs-lookup"><span data-stu-id="8be3b-131">OneNote</span></span></li><li><span data-ttu-id="8be3b-132">Sharepoint</span><span class="sxs-lookup"><span data-stu-id="8be3b-132">SharePoint</span></span></li><li><span data-ttu-id="8be3b-133">Planner</span><span class="sxs-lookup"><span data-stu-id="8be3b-133">Planner</span></span></li></ul>|
||||