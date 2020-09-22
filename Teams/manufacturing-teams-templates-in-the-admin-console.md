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
description: 瞭解如何使用 [團隊範本]，透過使用管理主控台提供預先定義的設定、通道及預先安裝的應用程式，來建立專為製造業需求設計的小組結構。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 919bfc1bc3e13985ac90484cd203bf93201babd2
ms.sourcegitcommit: af9f96010460f9323db84912fe143aa0750ac798
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171027"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-console"></a><span data-ttu-id="ce47e-103">在管理員主控台中使用小組製造範本</span><span class="sxs-lookup"><span data-stu-id="ce47e-103">Use Teams manufacturing templates in the admin console</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="ce47e-104">團隊範本可讓您透過提供預先定義的設定、通道及預先安裝應用程式範本，快速且輕鬆地建立團隊。</span><span class="sxs-lookup"><span data-stu-id="ce47e-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="ce47e-105">團隊範本有預先建立的小組結構定義，專門圍繞車間需求而設計。</span><span class="sxs-lookup"><span data-stu-id="ce47e-105">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="ce47e-106">您也可以延伸團隊範本，建立專為您特定組織需求量身定制的小組。</span><span class="sxs-lookup"><span data-stu-id="ce47e-106">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="ce47e-107">在本文中，我們將介紹每個團隊範本，以及我們建議使用這些範本的方式。</span><span class="sxs-lookup"><span data-stu-id="ce47e-107">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="ce47e-108">如果您負責規劃、部署及管理多個生產組織中的多個小組，本文適用于您。</span><span class="sxs-lookup"><span data-stu-id="ce47e-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="ce47e-109">我們假設您已在貴組織中已部署團隊服務。</span><span class="sxs-lookup"><span data-stu-id="ce47e-109">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="ce47e-110">如果您還沒有推出小組，請先閱讀 [如何推出 Microsoft 團隊](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="ce47e-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="ce47e-111">若要深入瞭解小組範本的整體資訊，請參閱 [開始使用團隊範本](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="ce47e-111">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="ce47e-112">品質與安全性</span><span class="sxs-lookup"><span data-stu-id="ce47e-112">Quality and safety</span></span>

<span data-ttu-id="ce47e-113">使用製造業車間作業團隊集中溝通、存取資源和車間作業。</span><span class="sxs-lookup"><span data-stu-id="ce47e-113">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="ce47e-114">包括原則與程式檔、訓練影片、安全通知、班次移交程式。</span><span class="sxs-lookup"><span data-stu-id="ce47e-114">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="ce47e-115">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="ce47e-115">Base template type</span></span>|<span data-ttu-id="ce47e-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="ce47e-116">baseTemplateId</span></span> | <span data-ttu-id="ce47e-117">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="ce47e-117">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="ce47e-118">品質與安全性</span><span class="sxs-lookup"><span data-stu-id="ce47e-118">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="ce47e-119">管道</span><span class="sxs-lookup"><span data-stu-id="ce47e-119">Channels:</span></span> <ul><li><span data-ttu-id="ce47e-120">一般</span><span class="sxs-lookup"><span data-stu-id="ce47e-120">General</span></span><li><span data-ttu-id="ce47e-121">公告</span><span class="sxs-lookup"><span data-stu-id="ce47e-121">Announcements</span></span></li><li><span data-ttu-id="ce47e-122">行1</span><span class="sxs-lookup"><span data-stu-id="ce47e-122">Line 1</span></span></li><li><span data-ttu-id="ce47e-123">第2行</span><span class="sxs-lookup"><span data-stu-id="ce47e-123">Line 2</span></span></li><li><span data-ttu-id="ce47e-124">第3行</span><span class="sxs-lookup"><span data-stu-id="ce47e-124">Line 3</span></span></li><li><span data-ttu-id="ce47e-125">安全</span><span class="sxs-lookup"><span data-stu-id="ce47e-125">Safety</span></span></li><li><span data-ttu-id="ce47e-126">訓練</span><span class="sxs-lookup"><span data-stu-id="ce47e-126">Training</span></span></li><li><span data-ttu-id="ce47e-127">保養</span><span class="sxs-lookup"><span data-stu-id="ce47e-127">Maintenance</span></span></li><li><span data-ttu-id="ce47e-128">有趣的內容</span><span class="sxs-lookup"><span data-stu-id="ce47e-128">Fun stuff</span></span></li></ul> <span data-ttu-id="ce47e-129">應用</span><span class="sxs-lookup"><span data-stu-id="ce47e-129">Apps:</span></span> <ul><li><span data-ttu-id="ce47e-130">Wiki</span><span class="sxs-lookup"><span data-stu-id="ce47e-130">Wiki</span></span></li></ul>|
||||
