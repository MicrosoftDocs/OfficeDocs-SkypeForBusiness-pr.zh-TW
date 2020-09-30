---
title: 在系統管理主控台中開始使用小組製造範本
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
description: 瞭解如何使用。 團隊範本可透過使用管理主控台提供預先定義的設定、通道及預先安裝的應用程式，來建立專為製造業需求設計的小組結構。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb7769a193e95f31db8ffb02b6120babfa05c661
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308396"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-console"></a><span data-ttu-id="4b1be-104">在管理員主控台中使用小組製造範本</span><span class="sxs-lookup"><span data-stu-id="4b1be-104">Use Teams manufacturing templates in the admin console</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="4b1be-105">團隊範本可讓您透過提供預先定義的設定、通道及預先安裝應用程式範本，快速且輕鬆地建立團隊。</span><span class="sxs-lookup"><span data-stu-id="4b1be-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="4b1be-106">團隊範本有預先建立的小組結構定義，專門圍繞車間需求而設計。</span><span class="sxs-lookup"><span data-stu-id="4b1be-106">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="4b1be-107">您也可以延伸團隊範本，建立專為您特定組織需求量身定制的小組。</span><span class="sxs-lookup"><span data-stu-id="4b1be-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="4b1be-108">在本文中，我們將介紹每個團隊範本，並建議如何使用它們。</span><span class="sxs-lookup"><span data-stu-id="4b1be-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="4b1be-109">如果您負責規劃、部署及管理多個生產組織中的多個小組，本文適用于您。</span><span class="sxs-lookup"><span data-stu-id="4b1be-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="4b1be-110">您已在組織中部署團隊服務。</span><span class="sxs-lookup"><span data-stu-id="4b1be-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="4b1be-111">如果您還沒有推出小組，請先閱讀 [如何推出 Microsoft 團隊](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="4b1be-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="4b1be-112">若要深入瞭解小組範本的整體資訊，請參閱 [開始使用團隊範本](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="4b1be-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="4b1be-113">品質與安全性</span><span class="sxs-lookup"><span data-stu-id="4b1be-113">Quality and safety</span></span>

<span data-ttu-id="4b1be-114">使用製造業車間作業團隊集中溝通、存取資源和車間作業。</span><span class="sxs-lookup"><span data-stu-id="4b1be-114">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="4b1be-115">包括原則與程式檔、訓練影片、安全通知、班次移交程式。</span><span class="sxs-lookup"><span data-stu-id="4b1be-115">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="4b1be-116">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="4b1be-116">Base template type</span></span>|<span data-ttu-id="4b1be-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="4b1be-117">baseTemplateId</span></span> | <span data-ttu-id="4b1be-118">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="4b1be-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="4b1be-119">品質與安全性</span><span class="sxs-lookup"><span data-stu-id="4b1be-119">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="4b1be-120">管道</span><span class="sxs-lookup"><span data-stu-id="4b1be-120">Channels:</span></span> <ul><li><span data-ttu-id="4b1be-121">一般</span><span class="sxs-lookup"><span data-stu-id="4b1be-121">General</span></span><li><span data-ttu-id="4b1be-122">公告</span><span class="sxs-lookup"><span data-stu-id="4b1be-122">Announcements</span></span></li><li><span data-ttu-id="4b1be-123">行1</span><span class="sxs-lookup"><span data-stu-id="4b1be-123">Line 1</span></span></li><li><span data-ttu-id="4b1be-124">第2行</span><span class="sxs-lookup"><span data-stu-id="4b1be-124">Line 2</span></span></li><li><span data-ttu-id="4b1be-125">第3行</span><span class="sxs-lookup"><span data-stu-id="4b1be-125">Line 3</span></span></li><li><span data-ttu-id="4b1be-126">安全</span><span class="sxs-lookup"><span data-stu-id="4b1be-126">Safety</span></span></li><li><span data-ttu-id="4b1be-127">訓練</span><span class="sxs-lookup"><span data-stu-id="4b1be-127">Training</span></span></li><li><span data-ttu-id="4b1be-128">保養</span><span class="sxs-lookup"><span data-stu-id="4b1be-128">Maintenance</span></span></li><li><span data-ttu-id="4b1be-129">有趣的內容</span><span class="sxs-lookup"><span data-stu-id="4b1be-129">Fun stuff</span></span></li></ul> <span data-ttu-id="4b1be-130">應用</span><span class="sxs-lookup"><span data-stu-id="4b1be-130">Apps:</span></span> <ul><li><span data-ttu-id="4b1be-131">Wiki</span><span class="sxs-lookup"><span data-stu-id="4b1be-131">Wiki</span></span></li></ul>|
||||
