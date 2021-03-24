---
title: Microsoft Teams 中應用程式的系統管理設定
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag, rarang
description: 瞭解您可以在 Microsoft Teams 中管理貴組織應用程式時可以使用哪些策略和設定。
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.adminsettings
- ms.teamsadmincenter.apppermspolicies.orgwideapps.thirdpartyapps
- ms.teamsadmincenter.apppolicies.adminsettings
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0594317c21f3ef2a30d1772959458f33bef393eb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094379"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="70e37-103">Microsoft Teams 中應用程式的系統管理設定</span><span class="sxs-lookup"><span data-stu-id="70e37-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="70e37-104">應用程式提供您組織的開箱即用工具，以取得 Teams 的更多功能。</span><span class="sxs-lookup"><span data-stu-id="70e37-104">Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="70e37-105">這些應用程式結合由 Microsoft、協力廠商或貴組織的開發人員提供的定位停駐點、訊息擴充功能、連接器和 Bot 功能。</span><span class="sxs-lookup"><span data-stu-id="70e37-105">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="70e37-106">您可以在系統管理中心的 Teams **App** 中管理貴組織的應用程式。</span><span class="sxs-lookup"><span data-stu-id="70e37-106">You manage apps for your organization in **Teams apps** in the admin center.</span></span> <span data-ttu-id="70e37-107"> (請參閱使用 Teams 系統管理員角色來管理 [Teams，](./using-admin-roles.md) 以閱讀取得系統管理員角色和許可權的資訊。) 例如，您可以允許或封鎖組織層級的應用程式、設定策略以控制 Teams 使用者可以使用的應用程式，以及釘上使用者最重要的應用程式來自訂 Teams。</span><span class="sxs-lookup"><span data-stu-id="70e37-107">(See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.) For example, you can allow or block apps at the org level, set policies to control what apps are available to Teams users, and customize Teams by pinning the apps that are most important for your users.</span></span>

<span data-ttu-id="70e37-108">我們會持續改善 Teams 中的應用程式體驗，並新增功能與功能。</span><span class="sxs-lookup"><span data-stu-id="70e37-108">We're continually improving the app experience in Teams and adding features and functionality.</span></span> <span data-ttu-id="70e37-109">一段時間之後，我們會建立額外的應用程式管理功能，因此請回來查看應用程式政策上最新的資訊。</span><span class="sxs-lookup"><span data-stu-id="70e37-109">Over time, we'll be building additional app management capabilities, so check back for the most up-to-date information on app policies.</span></span>

## <a name="manage-apps"></a><span data-ttu-id="70e37-110">管理應用程式</span><span class="sxs-lookup"><span data-stu-id="70e37-110">Manage apps</span></span>

<span data-ttu-id="70e37-111">使用管理 **應用程式頁面** 來查看及管理貴組織應用程式目錄中的所有 Teams 應用程式。</span><span class="sxs-lookup"><span data-stu-id="70e37-111">Use the **Manage apps** page to view and manage all Teams apps in your organization's app catalog.</span></span> <span data-ttu-id="70e37-112">您可以查看應用程式的組織層級狀態和屬性、封鎖或允許組織層級的應用程式、將新的自訂應用程式上傳到租使用者目錄，以及管理整個組織的應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="70e37-112">You can see the org-level status and properties of apps, block or allow apps at the org level, upload new custom apps to your tenant catalog, and manage org-wide app settings.</span></span>

<span data-ttu-id="70e37-113">管理 **應用程式頁面** 提供您租使用者目錄中所有可用 App 的視圖，為您提供決定要允許或封鎖整個組織之應用程式所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="70e37-113">The **Manage apps** page gives you a view into all available apps in your tenant catalog, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="70e37-114">然後，您可以使用 [應用程式權限原則](#app-permission-policies)、 [應用程式設定](#app-setup-policies)策略，以及 [自訂應用程式策略和](#custom-app-policies-and-settings) 設定，為貴組織的特定使用者設定應用程式體驗。</span><span class="sxs-lookup"><span data-stu-id="70e37-114">You can then use [app permission policies](#app-permission-policies), [app setup policies](#app-setup-policies), and [custom app policies and settings](#custom-app-policies-and-settings) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="70e37-115">若要深入瞭解，請參閱 [在 Teams 中管理應用程式](manage-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="70e37-115">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

## <a name="app-permission-policies"></a><span data-ttu-id="70e37-116">應用程式權限原則</span><span class="sxs-lookup"><span data-stu-id="70e37-116">App permission policies</span></span>

<span data-ttu-id="70e37-117">使用應用程式許可權政策，您可以控制哪些應用程式可供貴組織的特定使用者使用。</span><span class="sxs-lookup"><span data-stu-id="70e37-117">With app permission policies, you can control what apps are available to specific users in your organization.</span></span> <span data-ttu-id="70e37-118">您可以允許或封鎖所有應用程式，或是由 Microsoft、第三方和您的組織發行的特定應用程式。</span><span class="sxs-lookup"><span data-stu-id="70e37-118">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="70e37-119">例如，您可以使用應用程式權限原則：</span><span class="sxs-lookup"><span data-stu-id="70e37-119">For example, you can use app permission policies to:</span></span>

- <span data-ttu-id="70e37-120">逐步推出新的協力廠商或自訂內建應用程式給特定使用者。</span><span class="sxs-lookup"><span data-stu-id="70e37-120">Gradually roll out new third-party or custom built apps to specific users.</span></span>
- <span data-ttu-id="70e37-121">簡化使用者體驗，尤其是當您開始在組織中推出 Teams 時。</span><span class="sxs-lookup"><span data-stu-id="70e37-121">Simplify the user experience, especially when you start rolling out Teams across your organization.</span></span>

<span data-ttu-id="70e37-122">若要深入瞭解，請前往 [在 Teams 中管理應用程式許可權政策](teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="70e37-122">To learn more, go to [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="app-setup-policies"></a><span data-ttu-id="70e37-123">應用程式設定政策</span><span class="sxs-lookup"><span data-stu-id="70e37-123">App setup policies</span></span>

<span data-ttu-id="70e37-124">應用程式設定政策讓您自訂使用者的應用程式體驗。</span><span class="sxs-lookup"><span data-stu-id="70e37-124">App setup policies let you customize the app experience for your users.</span></span> <span data-ttu-id="70e37-125">您可以選擇要釘選至 Teams 用戶端中的應用程式欄，以及應用程式在 Web、桌面和行動用戶端上顯示的順序。</span><span class="sxs-lookup"><span data-stu-id="70e37-125">You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients.</span></span>

<span data-ttu-id="70e37-126">以下是一些如何使用應用程式設定策略的範例：</span><span class="sxs-lookup"><span data-stu-id="70e37-126">Here's some examples of how you can use app setup policies:</span></span>

- <span data-ttu-id="70e37-127">提升核心應用程式認知度及採用度。</span><span class="sxs-lookup"><span data-stu-id="70e37-127">Drive awareness and adoption of core apps.</span></span> <span data-ttu-id="70e37-128">例如，為人力資源小組的使用者釘選自訂招募和人才管理應用程式。</span><span class="sxs-lookup"><span data-stu-id="70e37-128">For example, pin a custom recruiting and talent management app for users on your HR team.</span></span>
- <span data-ttu-id="70e37-129">選擇性地釘選核心 Teams 功能，例如聊天、Teams 和通話。</span><span class="sxs-lookup"><span data-stu-id="70e37-129">Selectively pin core Teams features, such as Chat, Teams, and Calling.</span></span> <span data-ttu-id="70e37-130">這麼做有助於確保使用者在 Teams 中參與特定活動。</span><span class="sxs-lookup"><span data-stu-id="70e37-130">Doing so can help ensure users are engaged in specific activities within Teams.</span></span>

<span data-ttu-id="70e37-131">若要深入瞭解，請查看在 Teams 中管理 [應用程式設定政策](teams-app-setup-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="70e37-131">To learn more, check out [Manage app setup policies in Teams](teams-app-setup-policies.md).</span></span>

## <a name="custom-app-policies-and-settings"></a><span data-ttu-id="70e37-132">自訂應用程式策略和設定</span><span class="sxs-lookup"><span data-stu-id="70e37-132">Custom app policies and settings</span></span>

<span data-ttu-id="70e37-133">Teams 可讓貴組織的開發人員建立、測試自訂應用程式，以及將自訂應用程式部署到其他使用者。</span><span class="sxs-lookup"><span data-stu-id="70e37-133">Teams allows developers in your organization to build, test, and deploy custom apps to other users.</span></span> <span data-ttu-id="70e37-134">您可以直接將 .zip 檔案中的應用程式套件上傳到團隊或個人環境中，將自訂應用程式新加入 Teams。</span><span class="sxs-lookup"><span data-stu-id="70e37-134">Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context.</span></span> <span data-ttu-id="70e37-135">您可以使用應用程式設定策略來控制組織中誰可以上傳自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="70e37-135">You can use app setup policies to control who in your organization can upload custom apps.</span></span> <span data-ttu-id="70e37-136">您也可以設定全組織設定，以控制使用者是否能與特定的自訂應用程式互動。</span><span class="sxs-lookup"><span data-stu-id="70e37-136">You can also set org-wide settings to control whether users can interact with specific custom apps.</span></span>

<span data-ttu-id="70e37-137">若要深入瞭解，請前往 [管理 Teams 中的自訂應用程式策略和設定](teams-custom-app-policies-and-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="70e37-137">To learn more, go to [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>