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
- NewAdminCenter_Update
f1.keywords:
- ms.teamsadmincenter.apppermspolicies.adminsettings
- ms.teamsadmincenter.apppermspolicies.orgwideapps.thirdpartyapps
- ms.teamsadmincenter.apppolicies.adminsettings
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b857d0b1c0ded68bc74831d1596c78ff1d8e5907
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695488"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="c27ad-103">Microsoft 團隊中應用程式的系統管理設定</span><span class="sxs-lookup"><span data-stu-id="c27ad-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="c27ad-104">App 提供現成的工具供貴組織用來充分發揮團隊的效用。</span><span class="sxs-lookup"><span data-stu-id="c27ad-104">Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="c27ad-105">這些 app 結合由 Microsoft （由協力廠商或由貴組織的開發人員建立）所提供的索引標籤、訊息擴充、連接器和 bot 功能。</span><span class="sxs-lookup"><span data-stu-id="c27ad-105">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="c27ad-106">在 Microsoft 團隊系統管理中心的 [**團隊 app** ] 中，您可以設定策略來管理貴組織的 app。</span><span class="sxs-lookup"><span data-stu-id="c27ad-106">In **Teams apps** in the Microsoft Teams admin center, you can set policies to manage apps for your organization.</span></span> <span data-ttu-id="c27ad-107">例如，您可以設定原則來控制團隊使用者可以使用哪些應用程式，而且您可以將最重要的 app 釘選到您的使用者，來自訂團隊。</span><span class="sxs-lookup"><span data-stu-id="c27ad-107">For example, you can set policies to control what apps are available to Teams users and you can customize Teams by pinning the apps that are most important for your users.</span></span>

<span data-ttu-id="c27ad-108">我們會持續改善團隊中的應用程式體驗，以及新增功能和功能。</span><span class="sxs-lookup"><span data-stu-id="c27ad-108">We're continually improving the app experience in Teams and adding features and functionality.</span></span> <span data-ttu-id="c27ad-109">隨著時間的推移，我們將會建立其他 app 管理功能，因此請返回有關 app 原則的最新資訊。</span><span class="sxs-lookup"><span data-stu-id="c27ad-109">Over time, we'll be building additional app management capabilities, so check back for the most up-to-date information on app policies.</span></span>

## <a name="app-permission-policies"></a><span data-ttu-id="c27ad-110">App 許可權原則</span><span class="sxs-lookup"><span data-stu-id="c27ad-110">App permission policies</span></span>

<span data-ttu-id="c27ad-111">有了 app 許可權原則，您就可以封鎖或允許應用程式（無論是組織內或特定使用者）。</span><span class="sxs-lookup"><span data-stu-id="c27ad-111">With app permission policies, you can block or allow apps, either org-wide or for specific users.</span></span>  <span data-ttu-id="c27ad-112">當您封鎖 app 時，所有與該 app 的互動都會停用，且 app 不會出現在使用者的小組中。</span><span class="sxs-lookup"><span data-stu-id="c27ad-112">When you block an app, all interactions with that app are disabled and the app doesn't appear in Teams for users.</span></span>

<span data-ttu-id="c27ad-113">例如，您可以使用應用程式許可權原則來執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="c27ad-113">For example, you can use app permission policies to:</span></span>

- <span data-ttu-id="c27ad-114">停用會對您的組織帶來許可權或資料遺失風險的 app。</span><span class="sxs-lookup"><span data-stu-id="c27ad-114">Disable an app that poses a permission or data loss risk to your organization.</span></span>
- <span data-ttu-id="c27ad-115">將新的協力廠商或自訂的應用程式逐漸推出給特定的使用者。</span><span class="sxs-lookup"><span data-stu-id="c27ad-115">Gradually roll out new third-party or custom built apps to specific users.</span></span>
- <span data-ttu-id="c27ad-116">簡化使用者體驗，尤其是當您開始在整個組織中推出團隊時。</span><span class="sxs-lookup"><span data-stu-id="c27ad-116">Simplify the user experience, especially when you start rolling out Teams across your organization.</span></span>

<span data-ttu-id="c27ad-117">若要深入瞭解，請參閱[管理團隊中的 app 許可權原則](teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c27ad-117">To learn more, go to [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="app-setup-policies"></a><span data-ttu-id="c27ad-118">App 設定原則</span><span class="sxs-lookup"><span data-stu-id="c27ad-118">App setup policies</span></span>

<span data-ttu-id="c27ad-119">App 設定原則可讓您自訂使用者的 app 體驗。</span><span class="sxs-lookup"><span data-stu-id="c27ad-119">App setup policies let you customize the app experience for your users.</span></span> <span data-ttu-id="c27ad-120">您可以在 [團隊用戶端] 中，選擇您要釘選到應用程式行的應用程式，以及它們出現的順序、網頁、桌面及行動用戶端。</span><span class="sxs-lookup"><span data-stu-id="c27ad-120">You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients.</span></span>

<span data-ttu-id="c27ad-121">以下是如何使用 app 設定原則的一些範例：</span><span class="sxs-lookup"><span data-stu-id="c27ad-121">Here's some examples of how you can use app setup policies:</span></span>
- <span data-ttu-id="c27ad-122">促進核心應用程式的認識與採用。</span><span class="sxs-lookup"><span data-stu-id="c27ad-122">Drive awareness and adoption of core apps.</span></span> <span data-ttu-id="c27ad-123">例如，將自訂招聘和人才管理 app 固定在人力資源小組中的使用者。</span><span class="sxs-lookup"><span data-stu-id="c27ad-123">For example, pin a custom recruiting and talent management app for users on your HR team.</span></span>
- <span data-ttu-id="c27ad-124">選擇性地固定核心小組功能，例如聊天、團隊和通話。</span><span class="sxs-lookup"><span data-stu-id="c27ad-124">Selectively pin core Teams features, such as Chat, Teams, and Calling.</span></span> <span data-ttu-id="c27ad-125">如此一來，就能協助確保使用者參與團隊中的特定活動。</span><span class="sxs-lookup"><span data-stu-id="c27ad-125">Doing so can help ensure users are engaged in specific activities within Teams.</span></span>

<span data-ttu-id="c27ad-126">若要深入瞭解，請參閱[管理團隊中的 app 設定原則](teams-app-setup-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c27ad-126">To learn more, check out [Manage app setup policies in Teams](teams-app-setup-policies.md).</span></span>

## <a name="custom-app-policies-and-settings"></a><span data-ttu-id="c27ad-127">自訂 app 原則與設定</span><span class="sxs-lookup"><span data-stu-id="c27ad-127">Custom app policies and settings</span></span>

<span data-ttu-id="c27ad-128">團隊可讓貴組織中的開發人員建立、測試並將自訂應用程式部署到其他使用者。</span><span class="sxs-lookup"><span data-stu-id="c27ad-128">Teams allows developers in your organization to build, test, and deploy custom apps to other users.</span></span> <span data-ttu-id="c27ad-129">您可以將自訂應用程式直接上傳至小組或個人內容，將其新增至小組。</span><span class="sxs-lookup"><span data-stu-id="c27ad-129">Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context.</span></span> <span data-ttu-id="c27ad-130">您可以使用應用程式設定原則來控制貴組織中可以上傳自訂應用程式的人員。</span><span class="sxs-lookup"><span data-stu-id="c27ad-130">You can use app setup policies to control who in your organization can upload custom apps.</span></span> <span data-ttu-id="c27ad-131">您也可以設定全組織性設定，以控制使用者是否能與特定的自訂應用程式互動。</span><span class="sxs-lookup"><span data-stu-id="c27ad-131">You can also set org-wide settings to control whether users can interact with specific custom  apps.</span></span>

<span data-ttu-id="c27ad-132">若要深入瞭解，請移至[管理團隊中的自訂應用程式原則和設定](teams-custom-app-policies-and-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="c27ad-132">To learn more, go to [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>