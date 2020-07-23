---
title: Microsoft 團隊中應用程式的系統管理設定
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag, rarang
description: 瞭解您可以用來在 Microsoft 團隊中管理組織相關應用程式的原則與設定。
localization_priority: Normal
ms.custom:
- ms.teamsadmincenter.apppermspolicies.adminsettings
- ms.teamsadmincenter.apppermspolicies.orgwideapps.thirdpartyapps
- ms.teamsadmincenter.apppolicies.adminsettings
f1.keywords:
- CSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ae1776cf57368ea0f18cb6b0e46e5a11dffe447
ms.sourcegitcommit: 863347fb6e5916d8d936adc4ddcebb2e32a91d1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/22/2020
ms.locfileid: "45228899"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="90b8b-103">Microsoft 團隊中應用程式的系統管理設定</span><span class="sxs-lookup"><span data-stu-id="90b8b-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="90b8b-104">App 提供現成的工具供貴組織用來充分發揮團隊的效用。</span><span class="sxs-lookup"><span data-stu-id="90b8b-104">Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="90b8b-105">這些 app 結合由 Microsoft （由協力廠商或由貴組織的開發人員建立）所提供的索引標籤、訊息擴充、連接器和 bot 功能。</span><span class="sxs-lookup"><span data-stu-id="90b8b-105">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="90b8b-106">您可以在系統管理中心的 [**團隊 app** ] 中管理貴組織的應用程式。</span><span class="sxs-lookup"><span data-stu-id="90b8b-106">You manage apps for your organization in **Teams apps** in the admin center.</span></span> <span data-ttu-id="90b8b-107">（請參閱[使用團隊管理員角色管理團隊](https://docs.microsoft.com/microsoftteams/using-admin-roles)，以瞭解取得管理員角色和許可權的相關資訊。）例如，您可以允許或封鎖組織階層的 app、設定原則以控制團隊使用者可以使用哪些應用程式，以及將最重要的 app 釘選到您的使用者，來自訂團隊。</span><span class="sxs-lookup"><span data-stu-id="90b8b-107">(See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.) For example, you can allow or block apps at the org level, set policies to control what apps are available to Teams users, and customize Teams by pinning the apps that are most important for your users.</span></span>

<span data-ttu-id="90b8b-108">我們會持續改善團隊中的應用程式體驗，以及新增功能和功能。</span><span class="sxs-lookup"><span data-stu-id="90b8b-108">We're continually improving the app experience in Teams and adding features and functionality.</span></span> <span data-ttu-id="90b8b-109">隨著時間的推移，我們將會建立其他 app 管理功能，因此請返回有關 app 原則的最新資訊。</span><span class="sxs-lookup"><span data-stu-id="90b8b-109">Over time, we'll be building additional app management capabilities, so check back for the most up-to-date information on app policies.</span></span>

## <a name="manage-apps"></a><span data-ttu-id="90b8b-110">管理 app</span><span class="sxs-lookup"><span data-stu-id="90b8b-110">Manage apps</span></span>

<span data-ttu-id="90b8b-111">使用 [**管理應用程式**] 頁面來查看及管理貴組織的 [應用程式目錄] 中的所有團隊 app。</span><span class="sxs-lookup"><span data-stu-id="90b8b-111">Use the **Manage apps** page to view and manage all Teams apps in your organization's app catalog.</span></span> <span data-ttu-id="90b8b-112">您可以查看應用程式的組織層級狀態和屬性、封鎖或允許組織階層的 app、將新的自訂應用程式上傳到租使用者目錄，以及管理整個組織的應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="90b8b-112">You can see the org-level status and properties of apps, block or allow apps at the org level, upload new custom apps to your tenant catalog, and manage org-wide app settings.</span></span>

<span data-ttu-id="90b8b-113">[**管理應用程式**] 頁面可讓您查看租使用者目錄中所有可用的應用程式，為您提供所需的資訊，讓您決定要允許或封鎖整個組織的哪些應用程式。</span><span class="sxs-lookup"><span data-stu-id="90b8b-113">The **Manage apps** page gives you a view into all available apps in your tenant catalog, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="90b8b-114">接著，您可以使用[應用程式許可權原則](#app-permission-policies)、[應用程式設定原則](#app-setup-policies)，以及[自訂的 app 原則和設定](#custom-app-policies-and-settings)，為貴組織中的特定使用者設定 app 體驗。</span><span class="sxs-lookup"><span data-stu-id="90b8b-114">You can then use [app permission policies](#app-permission-policies), [app setup policies](#app-setup-policies), and [custom app policies and settings](#custom-app-policies-and-settings) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="90b8b-115">若要深入瞭解，請參閱[管理團隊中的應用程式](manage-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="90b8b-115">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

## <a name="app-permission-policies"></a><span data-ttu-id="90b8b-116">應用程式權限原則</span><span class="sxs-lookup"><span data-stu-id="90b8b-116">App permission policies</span></span>

<span data-ttu-id="90b8b-117">有了 app 許可權原則，您就可以控制貴組織中特定使用者可以使用哪些 app。</span><span class="sxs-lookup"><span data-stu-id="90b8b-117">With app permission policies, you can control what apps are available to specific users in your organization.</span></span> <span data-ttu-id="90b8b-118">您可以允許或封鎖由 Microsoft、協力廠商及貴組織發佈的所有 app 或特定應用程式。</span><span class="sxs-lookup"><span data-stu-id="90b8b-118">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="90b8b-119">例如，您可以使用應用程式許可權原則來執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="90b8b-119">For example, you can use app permission policies to:</span></span>

- <span data-ttu-id="90b8b-120">將新的協力廠商或自訂的應用程式逐漸推出給特定的使用者。</span><span class="sxs-lookup"><span data-stu-id="90b8b-120">Gradually roll out new third-party or custom built apps to specific users.</span></span>
- <span data-ttu-id="90b8b-121">簡化使用者體驗，尤其是當您開始在整個組織中推出團隊時。</span><span class="sxs-lookup"><span data-stu-id="90b8b-121">Simplify the user experience, especially when you start rolling out Teams across your organization.</span></span>

<span data-ttu-id="90b8b-122">若要深入瞭解，請參閱[管理團隊中的 app 許可權原則](teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="90b8b-122">To learn more, go to [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="app-setup-policies"></a><span data-ttu-id="90b8b-123">App 設定原則</span><span class="sxs-lookup"><span data-stu-id="90b8b-123">App setup policies</span></span>

<span data-ttu-id="90b8b-124">App 設定原則可讓您自訂使用者的 app 體驗。</span><span class="sxs-lookup"><span data-stu-id="90b8b-124">App setup policies let you customize the app experience for your users.</span></span> <span data-ttu-id="90b8b-125">您可以在 [團隊用戶端] 中，選擇您要釘選到應用程式行的應用程式，以及它們出現的順序、網頁、桌面及行動用戶端。</span><span class="sxs-lookup"><span data-stu-id="90b8b-125">You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients.</span></span>

<span data-ttu-id="90b8b-126">以下是如何使用 app 設定原則的一些範例：</span><span class="sxs-lookup"><span data-stu-id="90b8b-126">Here's some examples of how you can use app setup policies:</span></span>

- <span data-ttu-id="90b8b-127">促進核心應用程式的認識與採用。</span><span class="sxs-lookup"><span data-stu-id="90b8b-127">Drive awareness and adoption of core apps.</span></span> <span data-ttu-id="90b8b-128">例如，將自訂招聘和人才管理 app 固定在人力資源小組中的使用者。</span><span class="sxs-lookup"><span data-stu-id="90b8b-128">For example, pin a custom recruiting and talent management app for users on your HR team.</span></span>
- <span data-ttu-id="90b8b-129">選擇性地固定核心小組功能，例如聊天、團隊和通話。</span><span class="sxs-lookup"><span data-stu-id="90b8b-129">Selectively pin core Teams features, such as Chat, Teams, and Calling.</span></span> <span data-ttu-id="90b8b-130">如此一來，就能協助確保使用者參與團隊中的特定活動。</span><span class="sxs-lookup"><span data-stu-id="90b8b-130">Doing so can help ensure users are engaged in specific activities within Teams.</span></span>

<span data-ttu-id="90b8b-131">若要深入瞭解，請參閱[管理團隊中的 app 設定原則](teams-app-setup-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="90b8b-131">To learn more, check out [Manage app setup policies in Teams](teams-app-setup-policies.md).</span></span>

## <a name="custom-app-policies-and-settings"></a><span data-ttu-id="90b8b-132">自訂 app 原則與設定</span><span class="sxs-lookup"><span data-stu-id="90b8b-132">Custom app policies and settings</span></span>

<span data-ttu-id="90b8b-133">團隊可讓貴組織中的開發人員建立、測試並將自訂應用程式部署到其他使用者。</span><span class="sxs-lookup"><span data-stu-id="90b8b-133">Teams allows developers in your organization to build, test, and deploy custom apps to other users.</span></span> <span data-ttu-id="90b8b-134">您可以將自訂應用程式直接上傳至小組或個人內容，將其新增至小組。</span><span class="sxs-lookup"><span data-stu-id="90b8b-134">Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context.</span></span> <span data-ttu-id="90b8b-135">您可以使用應用程式設定原則來控制貴組織中可以上傳自訂應用程式的人員。</span><span class="sxs-lookup"><span data-stu-id="90b8b-135">You can use app setup policies to control who in your organization can upload custom apps.</span></span> <span data-ttu-id="90b8b-136">您也可以設定全組織性設定，以控制使用者是否能與特定的自訂應用程式互動。</span><span class="sxs-lookup"><span data-stu-id="90b8b-136">You can also set org-wide settings to control whether users can interact with specific custom apps.</span></span>

<span data-ttu-id="90b8b-137">若要深入瞭解，請移至[管理團隊中的自訂應用程式原則和設定](teams-custom-app-policies-and-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="90b8b-137">To learn more, go to [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>
