---
title: 在管理員主控台中使用團隊醫療保健範本
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 在管理員主控台中使用 Microsoft 團隊範本，透過提供預先定義的設定、頻道和應用程式範本，快速且輕鬆地建立小組。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 95837c4bbeb1f0624476f5066a168b09d09fd605
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308276"
---
# <a name="use-teams-healthcare-templates-in-the-admin-console"></a><span data-ttu-id="b5235-103">在管理員主控台中使用團隊醫療保健範本</span><span class="sxs-lookup"><span data-stu-id="b5235-103">Use Teams healthcare templates in the admin console</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="b5235-104">Microsoft 團隊範本可讓您透過提供預先定義的設定、頻道及預先安裝應用程式範本，快速且輕鬆地建立小組。</span><span class="sxs-lookup"><span data-stu-id="b5235-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="b5235-105">針對醫療保健組織而言，範本特別實用，因為它們為使用者提供結構，以瞭解如何有效地利用團隊。</span><span class="sxs-lookup"><span data-stu-id="b5235-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to best leverage Teams effectively.</span></span> <span data-ttu-id="b5235-106">範本也可讓系統管理員在組織中部署一致的團隊。</span><span class="sxs-lookup"><span data-stu-id="b5235-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="b5235-107">本文適用于您負責規劃、部署及管理整個醫療保健組織中的多個小組。</span><span class="sxs-lookup"><span data-stu-id="b5235-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your Healthcare organization.</span></span>

<span data-ttu-id="b5235-108">我們目前提供兩個第一方醫療保健範本，您可以在各種情況下利用。</span><span class="sxs-lookup"><span data-stu-id="b5235-108">We currently offer two first-party healthcare templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="b5235-109">若要深入瞭解小組範本的詳細資訊，請參閱 [管理主控台中的團隊範本快速入門](../../get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="b5235-109">To learn more about team templates in general, see [Get started with Teams templates in the admin console](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="collaborate-on-patient-care"></a><span data-ttu-id="b5235-110">在患者治療上共同作業</span><span class="sxs-lookup"><span data-stu-id="b5235-110">Collaborate on patient care</span></span>

 <span data-ttu-id="b5235-111">在 ward、pod 或部門中簡化醫療保健溝通與共同作業。</span><span class="sxs-lookup"><span data-stu-id="b5235-111">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="b5235-112">範本可用於協助患者管理和 ward 的操作需求。</span><span class="sxs-lookup"><span data-stu-id="b5235-112">The template can be used to facilitate patient management and operational needs of a ward.</span></span>

| <span data-ttu-id="b5235-113">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="b5235-113">Base template type</span></span> |<span data-ttu-id="b5235-114">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="b5235-114">baseTemplateId</span></span>| <span data-ttu-id="b5235-115">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="b5235-115">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="b5235-116">在患者治療上共同作業</span><span class="sxs-lookup"><span data-stu-id="b5235-116">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="b5235-117">管道</span><span class="sxs-lookup"><span data-stu-id="b5235-117">Channels:</span></span><ul><li><span data-ttu-id="b5235-118">一般</span><span class="sxs-lookup"><span data-stu-id="b5235-118">General</span></span></li><li><span data-ttu-id="b5235-119">公告</span><span class="sxs-lookup"><span data-stu-id="b5235-119">Announcements</span></span></li><li><span data-ttu-id="b5235-120">Huddles</span><span class="sxs-lookup"><span data-stu-id="b5235-120">Huddles</span></span></li><li><span data-ttu-id="b5235-121">輪</span><span class="sxs-lookup"><span data-stu-id="b5235-121">Rounds</span></span></li><li><span data-ttu-id="b5235-122">人員</span><span class="sxs-lookup"><span data-stu-id="b5235-122">Staffing</span></span></li><li><span data-ttu-id="b5235-123">訓練</span><span class="sxs-lookup"><span data-stu-id="b5235-123">Training</span></span></li></ul> <span data-ttu-id="b5235-124">應用</span><span class="sxs-lookup"><span data-stu-id="b5235-124">Apps:</span></span> <ul><li><span data-ttu-id="b5235-125">Wiki</span><span class="sxs-lookup"><span data-stu-id="b5235-125">Wiki</span></span></li>|
||||

## <a name="hospital"></a><span data-ttu-id="b5235-126">醫院</span><span class="sxs-lookup"><span data-stu-id="b5235-126">Hospital</span></span>

<span data-ttu-id="b5235-127">在醫院中的多個 wards、箱與部門之間簡化溝通與共同作業。</span><span class="sxs-lookup"><span data-stu-id="b5235-127">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="b5235-128">此範本包含一組醫院作業的基底頻道，而且可以自行延伸以納入專業、零星。</span><span class="sxs-lookup"><span data-stu-id="b5235-128">This template includes a set of base channels for hospital operations, and can be self-extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="b5235-129">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="b5235-129">Base template type</span></span> |<span data-ttu-id="b5235-130">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="b5235-130">baseTemplateId</span></span> | <span data-ttu-id="b5235-131">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="b5235-131">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="b5235-132">醫院</span><span class="sxs-lookup"><span data-stu-id="b5235-132">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="b5235-133">管道</span><span class="sxs-lookup"><span data-stu-id="b5235-133">Channels:</span></span> <ul><li><span data-ttu-id="b5235-134">一般</span><span class="sxs-lookup"><span data-stu-id="b5235-134">General</span></span><li><span data-ttu-id="b5235-135">公告</span><span class="sxs-lookup"><span data-stu-id="b5235-135">Announcements</span></span></li><li><span data-ttu-id="b5235-136">合規性</span><span class="sxs-lookup"><span data-stu-id="b5235-136">Compliance</span></span></li><li><span data-ttu-id="b5235-137">Custodial</span><span class="sxs-lookup"><span data-stu-id="b5235-137">Custodial</span></span></li><li><span data-ttu-id="b5235-138">人力資源</span><span class="sxs-lookup"><span data-stu-id="b5235-138">Human resources</span></span></li><li><span data-ttu-id="b5235-139">藥房</span><span class="sxs-lookup"><span data-stu-id="b5235-139">Pharmacy</span></span></li></ul> <span data-ttu-id="b5235-140">應用</span><span class="sxs-lookup"><span data-stu-id="b5235-140">Apps:</span></span> <ul><li><span data-ttu-id="b5235-141">Wiki</span><span class="sxs-lookup"><span data-stu-id="b5235-141">Wiki</span></span></li></ul>|
||||

## <a name="related-topics"></a><span data-ttu-id="b5235-142">相關主題</span><span class="sxs-lookup"><span data-stu-id="b5235-142">Related topics</span></span>

[<span data-ttu-id="b5235-143">開始使用 Teams 範本</span><span class="sxs-lookup"><span data-stu-id="b5235-143">Get started with Teams templates</span></span>](../../get-started-with-teams-templates-in-the-admin-console.md)
