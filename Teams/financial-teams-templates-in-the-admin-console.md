---
title: 使用系統管理主控台快速開始使用團隊財務範本
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
description: 瞭解如何使用 [團隊範本]，透過使用管理主控台提供預先定義的設定、通道及預先安裝應用程式，來建立專為財務需求而設計的小組結構。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 270e03d58a89cf35132f254d2dd1af55d894e8d0
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/19/2020
ms.locfileid: "48136013"
---
# <a name="use-teams-financial-templates-in-the-admin-console"></a><span data-ttu-id="8c54c-103">在管理員主控台中使用團隊財務範本</span><span class="sxs-lookup"><span data-stu-id="8c54c-103">Use Teams financial templates in the admin console</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="8c54c-104">團隊範本可讓您透過提供預先定義的設定、通道及預先安裝應用程式範本，快速且輕鬆地建立團隊。</span><span class="sxs-lookup"><span data-stu-id="8c54c-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="8c54c-105">團隊範本有預先建立的小組結構定義，專為圍繞財務需求而設計。</span><span class="sxs-lookup"><span data-stu-id="8c54c-105">Teams templates have pre-built definitions of team structures designed around financial needs.</span></span> <span data-ttu-id="8c54c-106">您也可以延伸團隊範本，建立專為您特定組織需求量身定制的小組。</span><span class="sxs-lookup"><span data-stu-id="8c54c-106">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="8c54c-107">在本文中，我們將介紹每個團隊範本，以及我們建議使用這些範本的方式。</span><span class="sxs-lookup"><span data-stu-id="8c54c-107">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="8c54c-108">如果您負責規劃、部署及管理整個財務組織中的多個小組，本文將適合您。</span><span class="sxs-lookup"><span data-stu-id="8c54c-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your financial organization.</span></span> <span data-ttu-id="8c54c-109">我們假設您已在貴組織中已部署團隊服務。</span><span class="sxs-lookup"><span data-stu-id="8c54c-109">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="8c54c-110">如果您還沒有推出小組，請先閱讀 [如何推出 Microsoft 團隊](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="8c54c-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="8c54c-111">若要深入瞭解小組範本的整體資訊，請參閱 [開始使用團隊範本](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="8c54c-111">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="global-crisis-or-event"></a><span data-ttu-id="8c54c-112">全球危機或活動</span><span class="sxs-lookup"><span data-stu-id="8c54c-112">Global crisis or event</span></span>

<span data-ttu-id="8c54c-113">針對您的危機小組集中共同作業，協助建立業務連續性方案、共用遠端工作秘訣、追蹤客戶通訊，以及使用宣告和新聞讓每個人都保持在迴圈中。</span><span class="sxs-lookup"><span data-stu-id="8c54c-113">Centralize collaboration for your crisis team across business units and help create business continuity plans, share remote working tips, track customer communications, and keep everyone in the loop with announcements and news.</span></span>

| <span data-ttu-id="8c54c-114">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="8c54c-114">Base template type</span></span>|<span data-ttu-id="8c54c-115">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="8c54c-115">baseTemplateId</span></span> | <span data-ttu-id="8c54c-116">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="8c54c-116">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
| <span data-ttu-id="8c54c-117">在全球危機或活動上共同作業</span><span class="sxs-lookup"><span data-stu-id="8c54c-117">Collaborate on global crisis or event</span></span>|`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |<span data-ttu-id="8c54c-118">管道</span><span class="sxs-lookup"><span data-stu-id="8c54c-118">Channels:</span></span> <ul><li><span data-ttu-id="8c54c-119">一般</span><span class="sxs-lookup"><span data-stu-id="8c54c-119">General</span></span><li><span data-ttu-id="8c54c-120">公告</span><span class="sxs-lookup"><span data-stu-id="8c54c-120">Announcements</span></span></li><li><span data-ttu-id="8c54c-121">世界新聞</span><span class="sxs-lookup"><span data-stu-id="8c54c-121">World news</span></span></li><li><span data-ttu-id="8c54c-122">業務連續性</span><span class="sxs-lookup"><span data-stu-id="8c54c-122">Business continuity</span></span></li><li><span data-ttu-id="8c54c-123">遠端作業</span><span class="sxs-lookup"><span data-stu-id="8c54c-123">Remote working</span></span></li><li><span data-ttu-id="8c54c-124">內部 comms</span><span class="sxs-lookup"><span data-stu-id="8c54c-124">Internal comms</span></span></li><li><span data-ttu-id="8c54c-125">外部 comms</span><span class="sxs-lookup"><span data-stu-id="8c54c-125">External comms</span></span></li><li><span data-ttu-id="8c54c-126">客戶投訴</span><span class="sxs-lookup"><span data-stu-id="8c54c-126">Customer complaints</span></span></li><li><span data-ttu-id="8c54c-127">Kudos</span><span class="sxs-lookup"><span data-stu-id="8c54c-127">Kudos</span></span></li><li><span data-ttu-id="8c54c-128">主管更新</span><span class="sxs-lookup"><span data-stu-id="8c54c-128">Executive update</span></span></li></ul><span data-ttu-id="8c54c-129">應用</span><span class="sxs-lookup"><span data-stu-id="8c54c-129">Apps:</span></span> <ul><li><span data-ttu-id="8c54c-130">稱讚</span><span class="sxs-lookup"><span data-stu-id="8c54c-130">Praise</span></span></li><li><span data-ttu-id="8c54c-131">Wiki</span><span class="sxs-lookup"><span data-stu-id="8c54c-131">Wiki</span></span></li><li><span data-ttu-id="8c54c-132">Web</span><span class="sxs-lookup"><span data-stu-id="8c54c-132">Website</span></span></li></ul>|
||||

## <a name="collaborate-within-a-bank-branch"></a><span data-ttu-id="8c54c-133">在銀行分支機搆內共同作業</span><span class="sxs-lookup"><span data-stu-id="8c54c-133">Collaborate within a bank branch</span></span>

<span data-ttu-id="8c54c-134">在 Huddles、客戶會議、業務程式（例如貸款共同作業）集中進行您的銀行分支機搆共同作業，並讓每個人都能透過宣告和 Kudos 保持合作。</span><span class="sxs-lookup"><span data-stu-id="8c54c-134">Centralize collaboration for your bank branch employees across Huddles, Customer Meetings, Business Processes such as Mortgage Collaboration, and keep everyone in the loop with Announcements and Kudos.</span></span>

| <span data-ttu-id="8c54c-135">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="8c54c-135">Base template type</span></span> |<span data-ttu-id="8c54c-136">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="8c54c-136">baseTemplateId</span></span>| <span data-ttu-id="8c54c-137">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="8c54c-137">Properties that come with this base template</span></span> |
| ------------------ |--|----------------------------------------------------- |
|<span data-ttu-id="8c54c-138">在銀行分支機搆內共同作業</span><span class="sxs-lookup"><span data-stu-id="8c54c-138">Collaborate within a bank branch</span></span>|`com.microsoft.teams.template.CollaborateWithinABankBranch` |<span data-ttu-id="8c54c-139">管道</span><span class="sxs-lookup"><span data-stu-id="8c54c-139">Channels:</span></span> <ul><li><span data-ttu-id="8c54c-140">一般</span><span class="sxs-lookup"><span data-stu-id="8c54c-140">General</span></span><li><span data-ttu-id="8c54c-141">公告</span><span class="sxs-lookup"><span data-stu-id="8c54c-141">Announcements</span></span></li><li><span data-ttu-id="8c54c-142">Huddles</span><span class="sxs-lookup"><span data-stu-id="8c54c-142">Huddles</span></span></li><li><span data-ttu-id="8c54c-143">客戶會議</span><span class="sxs-lookup"><span data-stu-id="8c54c-143">Customer meetings</span></span></li><li><span data-ttu-id="8c54c-144">警告</span><span class="sxs-lookup"><span data-stu-id="8c54c-144">Coaching</span></span></li><li><span data-ttu-id="8c54c-145">技能開發</span><span class="sxs-lookup"><span data-stu-id="8c54c-145">Skills development</span></span></li><li><span data-ttu-id="8c54c-146">貸款處理</span><span class="sxs-lookup"><span data-stu-id="8c54c-146">Loan processing</span></span></li><li><span data-ttu-id="8c54c-147">客戶投訴</span><span class="sxs-lookup"><span data-stu-id="8c54c-147">Customer complaints</span></span></li><li><span data-ttu-id="8c54c-148">Kudos</span><span class="sxs-lookup"><span data-stu-id="8c54c-148">Kudos</span></span></li><li><span data-ttu-id="8c54c-149">有趣的內容</span><span class="sxs-lookup"><span data-stu-id="8c54c-149">Fun stuff</span></span></li><li><span data-ttu-id="8c54c-150">合規性</span><span class="sxs-lookup"><span data-stu-id="8c54c-150">Compliance</span></span></li></ul>|
||||

