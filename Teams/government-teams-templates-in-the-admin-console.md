---
title: 在管理員主控台中使用團隊政府範本
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
description: 瞭解如何使用 [團隊範本]，透過使用管理主控台提供預先定義的設定、通道及預先安裝的應用程式，來建立專為政府需求設計的小組結構。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: aa83d8122475ee22c2d0bdd69c8d69f916499d46
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/19/2020
ms.locfileid: "48136005"
---
# <a name="use-teams-government-templates-in-the-admin-console"></a><span data-ttu-id="9d3de-103">在管理員主控台中使用團隊政府範本</span><span class="sxs-lookup"><span data-stu-id="9d3de-103">Use Teams government templates in the admin console</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="9d3de-104">團隊範本可讓您透過提供預先定義的設定、通道及預先安裝應用程式範本，快速且輕鬆地建立團隊。</span><span class="sxs-lookup"><span data-stu-id="9d3de-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="9d3de-105">團隊範本有預先建立的小組結構定義，專為政府需求而設計。</span><span class="sxs-lookup"><span data-stu-id="9d3de-105">Teams templates have pre-built definitions of team structures designed around governmental needs.</span></span> <span data-ttu-id="9d3de-106">您也可以延伸團隊範本，建立專為您特定組織需求量身定制的小組。</span><span class="sxs-lookup"><span data-stu-id="9d3de-106">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="9d3de-107">在本文中，我們將介紹每個團隊範本，以及我們建議使用這些範本的方式。</span><span class="sxs-lookup"><span data-stu-id="9d3de-107">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="9d3de-108">本文適用于您負責規劃、部署及管理政府組織中的多個小組。</span><span class="sxs-lookup"><span data-stu-id="9d3de-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your governmental organization.</span></span> <span data-ttu-id="9d3de-109">我們假設您已在貴組織中已部署團隊服務。</span><span class="sxs-lookup"><span data-stu-id="9d3de-109">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="9d3de-110">如果您還沒有推出小組，請先閱讀 [如何推出 Microsoft 團隊](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="9d3de-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="9d3de-111">若要深入瞭解小組範本的整體資訊，請參閱 [開始使用團隊範本](get-started-with-teams-templates-in-the-admin-console.md)。</span><span class="sxs-lookup"><span data-stu-id="9d3de-111">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="coordinate-incident-response"></a><span data-ttu-id="9d3de-112">協調事件回應</span><span class="sxs-lookup"><span data-stu-id="9d3de-112">Coordinate incident response</span></span>

<span data-ttu-id="9d3de-113">針對危機管理或事件回應小組集中溝通與重要資源。</span><span class="sxs-lookup"><span data-stu-id="9d3de-113">Centralize communication and critical resources for your crisis management or incident response team.</span></span> <span data-ttu-id="9d3de-114">在這個小組中，您可以加入許多不同類型的檔案，協助您為所有檔建立一個集中位置。</span><span class="sxs-lookup"><span data-stu-id="9d3de-114">Within this team you can include many different types of files to help create a central place for all your documents.</span></span> <span data-ttu-id="9d3de-115">使用線上會議來改善資訊流與形勢感知。</span><span class="sxs-lookup"><span data-stu-id="9d3de-115">Use online meetings to improve information flow and situational awareness.</span></span>

| <span data-ttu-id="9d3de-116">基底範本類型</span><span class="sxs-lookup"><span data-stu-id="9d3de-116">Base template type</span></span> | | <span data-ttu-id="9d3de-117">此基礎範本隨附的屬性</span><span class="sxs-lookup"><span data-stu-id="9d3de-117">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="9d3de-118">協調事件回應</span><span class="sxs-lookup"><span data-stu-id="9d3de-118">Coordinate incident response</span></span>|`com.microsoft.teams.template.CoordinateIncidentResponse` |<span data-ttu-id="9d3de-119">管道</span><span class="sxs-lookup"><span data-stu-id="9d3de-119">Channels:</span></span> <ul><li><span data-ttu-id="9d3de-120">一般</span><span class="sxs-lookup"><span data-stu-id="9d3de-120">General</span></span><li><span data-ttu-id="9d3de-121">公告</span><span class="sxs-lookup"><span data-stu-id="9d3de-121">Announcements</span></span></li><li><span data-ttu-id="9d3de-122">物流</span><span class="sxs-lookup"><span data-stu-id="9d3de-122">Logistics</span></span></li><li><span data-ttu-id="9d3de-123">規劃</span><span class="sxs-lookup"><span data-stu-id="9d3de-123">Planning</span></span></li><li><span data-ttu-id="9d3de-124">修復</span><span class="sxs-lookup"><span data-stu-id="9d3de-124">Recovery</span></span></li><li><span data-ttu-id="9d3de-125">非常</span><span class="sxs-lookup"><span data-stu-id="9d3de-125">Urgent</span></span></li></ul> <span data-ttu-id="9d3de-126">應用</span><span class="sxs-lookup"><span data-stu-id="9d3de-126">Apps:</span></span> <ul><li><span data-ttu-id="9d3de-127">Wiki</span><span class="sxs-lookup"><span data-stu-id="9d3de-127">Wiki</span></span></li><li><span data-ttu-id="9d3de-128">Excel</span><span class="sxs-lookup"><span data-stu-id="9d3de-128">Excel</span></span></li><li><span data-ttu-id="9d3de-129">OneNote</span><span class="sxs-lookup"><span data-stu-id="9d3de-129">OneNote</span></span></li><li><span data-ttu-id="9d3de-130">SharePoint</span><span class="sxs-lookup"><span data-stu-id="9d3de-130">SharePoint</span></span></li><li><span data-ttu-id="9d3de-131">Planner</span><span class="sxs-lookup"><span data-stu-id="9d3de-131">Planner</span></span></li></ul>|
||||