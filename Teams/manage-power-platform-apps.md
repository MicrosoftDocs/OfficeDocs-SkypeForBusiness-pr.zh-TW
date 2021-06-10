---
title: 在系統管理中心Microsoft Teams Microsoft Power Platform 應用程式
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: joglocke
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何管理系統管理中心內建于 Microsoft Power Platform Microsoft Teams應用程式的存取權。
ms.openlocfilehash: 03940d402bd2259287e1e69f844e6560424f15e2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096157"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="a7ee5-103">在系統管理中心Microsoft Teams Microsoft Power Platform 應用程式</span><span class="sxs-lookup"><span data-stu-id="a7ee5-103">Manage Microsoft Power Platform apps in the Microsoft Teams admin center</span></span>

## <a name="microsoft-power-platform-apps-in-teams"></a><span data-ttu-id="a7ee5-104">Microsoft Power Platform 應用程式Teams</span><span class="sxs-lookup"><span data-stu-id="a7ee5-104">Microsoft Power Platform apps in Teams</span></span>

<span data-ttu-id="a7ee5-105">本文提供如何在系統管理中心管理 Microsoft [Power Platform](https://powerplatform.microsoft.com/)應用程式Microsoft Teams概觀。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-105">This article gives you an overview of how to manage [Microsoft Power Platform](https://powerplatform.microsoft.com/) apps in the Microsoft Teams admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="a7ee5-106">本文適用于由貴組織建立者使用或Power Apps建立Power Virtual Agents。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-106">This article applies to custom apps created by makers in your organization using Power Apps or Power Virtual Agents.</span></span> <span data-ttu-id="a7ee5-107">這些自訂應用程式會自動新Teams。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-107">These custom apps are automatically added to Teams.</span></span> <span data-ttu-id="a7ee5-108">本文不適用於從應用程式頁面Power Apps或Power Virtual Agents透過應用程式設定原則釘Teams的 App 或應用程式。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-108">This article doesn't apply to the Power Apps app or Power Virtual Agents app that are installed from the Apps page or pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="a7ee5-109">您可以使用應用程式權限原則和應用程式設定政策，像管理應用程式頁面上任何其他[](manage-apps.md)應用程式一樣管理[這些應用程式](teams-app-setup-policies.md)。 [](teams-app-permission-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a7ee5-109">You manage those apps as you would for any other app on the [Manage apps](manage-apps.md) page, using [app permission policies](teams-app-permission-policies.md), and [app setup policies](teams-app-setup-policies.md).</span></span>

<span data-ttu-id="a7ee5-110">[Power Apps](https://powerapps.microsoft.com)是低程式碼/無代碼的應用程式開發環境，貴組織的製造商可以使用這個環境來建立可連接到您商務資料的自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-110">[Power Apps](https://powerapps.microsoft.com) is a low-code/no-code application development environment that makers in your organization can use to build custom apps that connect to your business data.</span></span> <span data-ttu-id="a7ee5-111">[Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents)是一個無程式碼的 Bot 建立環境，讓製造商能夠建立功能強大的 Bot。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-111">[Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents) is a no-code bot building environment for makers to create powerful bots.</span></span> <span data-ttu-id="a7ee5-112">隨著 Microsoft Power Platform 應用程式與 Teams 整合，組織可以簡化商務程式、更快速地回應變更的業務需求，以推動更大的共同作業，以及建立及共用自訂解決方案，以提升生產力。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-112">With the integration of Microsoft Power Platform apps into Teams, organizations can streamline business processes, respond to changing business needs more rapidly to drive greater collaboration, and create and share custom solutions to be more productive.</span></span>  

<span data-ttu-id="a7ee5-113">由貴組織廠商所建立之 Microsoft Power Platform 應用程式會自動新Teams。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-113">Microsoft Power Platform apps created by makers in your organization are automatically added to Teams.</span></span> <span data-ttu-id="a7ee5-114">製作人可以使用應用程式中的共用功能，[以及](/powerapps/maker/canvas-apps/share-app)Power Apps 中的共用功能來控制誰可以存取[Power Virtual Agents。](/power-virtual-agents/admin-share-bots)</span><span class="sxs-lookup"><span data-stu-id="a7ee5-114">Makers can control who can access their app by using the [sharing feature in Power Apps](/powerapps/maker/canvas-apps/share-app) and the [sharing feature in Power Virtual Agents](/power-virtual-agents/admin-share-bots).</span></span>

<span data-ttu-id="a7ee5-115">建立或共用 Microsoft Power Platform App 時，使用者可以在應用程式頁面上查看並安裝，請流覽 \*\*\*\* 至由同事建立的組織名稱  >  \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-115">When a Microsoft Power Platform app is created or shared, users can view and install it on the Apps page by going to **Built for *Your Organization Name*** > **Built by your colleagues**.</span></span> <span data-ttu-id="a7ee5-116"> (建立或共用應用程式後，可能需要幾分鐘的時間，應用程式才能在這裡顯示。) </span><span class="sxs-lookup"><span data-stu-id="a7ee5-116">(It might take a few minutes after an app is created or shared for the app to appear here.)</span></span>

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="應用程式頁面的螢幕擷取畫面，顯示同事在建立中所列的 Microsoft Power Platform 應用程式":::

<span data-ttu-id="a7ee5-118">如果應用程式符合下列其中一個條件，使用者會看到同事在內建的應用程式。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-118">A user will see an app in **Built by your colleagues** if the app meets one of the following conditions.</span></span>

|<span data-ttu-id="a7ee5-119">Power Apps</span><span class="sxs-lookup"><span data-stu-id="a7ee5-119">Power Apps</span></span> |<span data-ttu-id="a7ee5-120">Power Virtual Agents</span><span class="sxs-lookup"><span data-stu-id="a7ee5-120">Power Virtual Agents</span></span>  |
|---------|---------|
|<ul><li><span data-ttu-id="a7ee5-121">使用者建立了應用程式。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-121">The user created the app.</span></span></li><li><span data-ttu-id="a7ee5-122">應用程式已直接與使用者共用。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-122">The app was shared directly with the user.</span></span></li><li><span data-ttu-id="a7ee5-123">使用者最近使用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-123">The user recently used the app.</span></span> </li></ul>| <ul><li><span data-ttu-id="a7ee5-124">使用者建立了 Bot。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-124">The user created the bot.</span></span></li><li><span data-ttu-id="a7ee5-125">Bot 是由使用者所屬團隊所擁有。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-125">The bot is owned by a team the user is a member of.</span></span> </li></ul>        |

<span data-ttu-id="a7ee5-126">使用者安裝 Microsoft Power Platform App 的方式，與安裝任何其他應用程式Teams相同。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-126">Users install Microsoft Power Platform apps in the same way they install any other Teams app.</span></span> <span data-ttu-id="a7ee5-127">請記住，使用者只能將應用程式安裝到他們有權使用的背景，例如他們擁有的團隊、他們屬於的聊天，或是他們的個人範圍。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-127">Keep in mind that users can only install  apps to the context to which they have permissions, for example, a team they own, a chat that they're a part of, or their personal scope.</span></span>

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="a7ee5-128">在系統管理中心管理 Microsoft Power Platform Microsoft Teams存取權</span><span class="sxs-lookup"><span data-stu-id="a7ee5-128">Manage access to Microsoft Power Platform apps in the Microsoft Teams admin center</span></span>

<span data-ttu-id="a7ee5-129">做為系統管理員，您可以控制 Microsoft Power Platform 應用程式是否列在您同事在 Teams 的 App 頁面上的建Teams。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-129">As an admin, you can control whether Microsoft Power Platform apps are listed in **Built by your colleagues** on the Apps page in Teams.</span></span> <span data-ttu-id="a7ee5-130">您可以共同封鎖或允許在 Power Apps 中建立的所有應用程式，或是在組織層級的 Power Virtual Agents 中建立的所有應用程式，或針對使用[](manage-apps.md)應用程式權限原則的特定[使用者。](teams-app-permission-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a7ee5-130">You can collectively block or allow all apps created in Power Apps or all apps created in Power Virtual Agents at the org level on the [Manage apps](manage-apps.md) page or for specific users using [app permission policies](teams-app-permission-policies.md).</span></span>

<span data-ttu-id="a7ee5-131">貴 **Power Apps** App Store 中的共用應用程式與 **共用 Power Virtual Agent App** 應用程式代表該特定平臺上建立的所有應用程式。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-131">The **Shared Power Apps** and **Shared Power Virtual Agent Apps** apps in your organization's app store represent all apps created on that particular platform.</span></span> <span data-ttu-id="a7ee5-132">如果您在組織層級或針對特定使用者封鎖一或兩個這些應用程式，這些使用者無法從同事建集的這些平臺上看到任何應用程式，而且無法將它們安裝在 Teams。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-132">If you block one or both these apps at the org level or for specific users, those users can't see any apps from those platforms in **Built by your colleagues** and can't install them in Teams.</span></span>  

<span data-ttu-id="a7ee5-133">請記住，您可以控制在 Power Apps 和 Power Virtual Agents 中建立的所有應用程式存取權，但無法允許或封鎖個別應用程式。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-133">Keep in mind that you can control access to all apps created in Power Apps and Power Virtual Agents but you can't allow or block individual apps.</span></span> <span data-ttu-id="a7ee5-134">製作人決定誰可以透過共用功能存取他們建立的應用程式，Power Apps Power Virtual Agents。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-134">Makers decide who can access the apps they create through the sharing feature from within Power Apps and Power Virtual Agents.</span></span> <span data-ttu-id="a7ee5-135">如果製作者與使用者在 Power Virtual Agents 中建立的應用程式共用，而您封鎖該使用者的共用 **Power Virtual Agents** App，使用者將無法在 Teams 中查看或安裝該平臺的任何應用程式。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-135">If a maker shared an app they created in Power Virtual Agents with a user and you blocked **Shared Power Virtual Agents Apps** for that user, the user won't be able to see or install any apps from that platform in Teams.</span></span>

<span data-ttu-id="a7ee5-136">如果使用者允許從 Power Apps 或 Power Virtual Agents 存取應用程式，而您接著封鎖使用者從其中一個或兩個平臺存取應用程式，則在您封鎖 App 或 App 之前，使用者仍可存取並使用他們安裝的 Microsoft Power 平臺應用程式。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-136">If a user is allowed to access apps from Power Apps or Power Virtual Agents, and you then block the user from accessing apps from one or both these platforms, the user can still access and use Microsoft Power Platforms apps that they installed before you blocked the app or apps.</span></span> <span data-ttu-id="a7ee5-137">不過，使用者無法再看到或安裝同事在內建的這些平臺上 **的任何應用程式**。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-137">However, the user can no longer see or install any apps from those platforms in **Built by your colleagues**.</span></span>

> [!NOTE]
> <span data-ttu-id="a7ee5-138">在 **管理應用程式頁面上** 的允許與自訂應用程式互動整個組織 [](manage-apps.md)App 設定會適用于貴組織中的每個人，並規範他們是否能與自訂應用程式互動。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-138">The **Allow interaction with custom apps** org-wide app setting on the [Manage apps](manage-apps.md) page applies to everyone in your organization and governs whether they can interact with custom apps.</span></span> <span data-ttu-id="a7ee5-139">全組織應用程式設定會控管所有使用者的行為，並覆寫指派給使用者的任何其他應用程式權限原則。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-139">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="a7ee5-140">此設定預設會開啟。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-140">By default, this setting is turned on.</span></span> <span data-ttu-id="a7ee5-141">如果關閉此設定，貴組織的使用者就看不到或安裝任何自訂應用程式，包括 Microsoft Power Platform App。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-141">If this setting is turned off, users in your organization can't see or install any custom apps, including Microsoft Power Platform apps.</span></span> <span data-ttu-id="a7ee5-142">若要深入瞭解，請參閱 [管理全組織的應用程式設定](manage-apps.md#manage-org-wide-app-settings)。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-142">To learn  more, see [Manage org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a><span data-ttu-id="a7ee5-143">允許或封鎖貴組織的 Microsoft Power Platform 應用程式</span><span class="sxs-lookup"><span data-stu-id="a7ee5-143">Allow or block Microsoft Power Platform apps for your organization</span></span>

<span data-ttu-id="a7ee5-144">根據預設 **，Power Apps** 組織中所有使用者都Teams共用和共用 **Power 虛擬** 代理應用程式。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-144">By default, **Shared Power Apps** and **Shared Power Virtual Agent Apps** are allowed for all Teams users in your organization.</span></span> <span data-ttu-id="a7ee5-145">您可以在系統管理中心的管理應用程式頁面上，在組織層級封鎖[](manage-apps.md)或允許Microsoft Teams應用程式。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-145">You can block or allow them at the org level on the [Manage apps](manage-apps.md) page of the Microsoft Teams admin center.</span></span>  

1. <span data-ttu-id="a7ee5-146">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-146">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="a7ee5-147">您必須是全域系統管理員或Teams系統管理員才能存取頁面。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-147">You must be a global admin or Teams service admin to access the page.</span></span>
2. <span data-ttu-id="a7ee5-148">在應用程式清單中，執行下列其中一項操作。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-148">In the list of apps, do one of the following.</span></span>

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="管理應用程式頁面的螢幕擷取畫面，顯示共用的 Microsoft Power Platform 應用程式":::

    - <span data-ttu-id="a7ee5-150">若要封鎖在 Power Apps 或 Power Virtual Agents 中為貴組織所有使用者所建立的應用程式，請搜尋 [共用 Power Apps 或 **共用 Power Virtual Agent Apps，** 選取它，然後按一下 [**封鎖**。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-150">To block apps created in Power Apps or Power Virtual Agents for all users in your organization, search for **Shared Power Apps** or **Shared Power Virtual Agent Apps**, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="a7ee5-151">若要允許在 Power Apps 或 Power Virtual Agents 中為貴組織所有使用者建立的應用程式，請搜尋 [共用Power Apps **或\*\*\*\*[共用 Power Virtual Agent Apps》，** 選取它，然後按一下 [**允許**。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-151">To allow apps created in Power Apps or Power Virtual Agents for all users in your organization, search for **Shared Power Apps** or **Shared Power Virtual Agent Apps**, select it, and then click **Allow**.</span></span>

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a><span data-ttu-id="a7ee5-152">允許或封鎖特定使用者的 Microsoft Power Platform 應用程式</span><span class="sxs-lookup"><span data-stu-id="a7ee5-152">Allow or block Microsoft Power Platform apps for specific users</span></span>

<span data-ttu-id="a7ee5-153">若要允許或封鎖貴組織中特定使用者存取在 Power Apps 或 Power Virtual Agents 中建立的應用程式，請建立並指派一或多個自訂[應用程式權限原則](teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-153">To allow or block specific users in your organization from accessing apps created in Power Apps or Power Virtual Agents, create and assign one or more custom [app permission policies](teams-app-permission-policies.md).</span></span> 

<span data-ttu-id="a7ee5-154">例如，若要封鎖特定使用者存取 Power Apps 中建立的應用程式，請建立自訂應用程式權限原則來封鎖共用 **Power Apps，然後將** 該策略指派給這些使用者。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-154">For example, to block specific users from accessing apps created in Power Apps, create a custom app permission policy to block **Shared Power Apps**, and then assign the policy to those users.</span></span>

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="已封鎖共用帳戶之自訂應用程式許可權Power Apps的螢幕擷取畫面":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a><span data-ttu-id="a7ee5-156">使用稽核記錄來調查 Microsoft Power Platform 安裝活動</span><span class="sxs-lookup"><span data-stu-id="a7ee5-156">Use audit logs to investigate Microsoft Power Platform installation activity</span></span>

<span data-ttu-id="a7ee5-157">您可以使用適用于 Teams 的稽核記錄，調查使用者從 Teams 中應用程式頁面的 "由同事建立」 區段安裝 Microsoft Power Platform 應用程式的事件。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-157">You can use audit logs for Teams to investigate events where users installed Microsoft Power Platform apps from the **Built by your colleagues** section of the Apps page in Teams.</span></span> <span data-ttu-id="a7ee5-158">若要 [這麼做，請](./audit-log-events.md)針對使用者或一組使用者Teams **App 安裝** (App 安裝) 活動的稽核記錄。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-158">To do this, [search the audit log](./audit-log-events.md) for the **Installed app** Teams event (under the **AppInstalled** operation) for a user or set of users.</span></span> <span data-ttu-id="a7ee5-159">若要尋找同事從 **建** 置安裝的應用程式，請尋找特定記錄詳細資料 **中 AppDistributionMode** 屬性中的 **TemplatedInstance** 值。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-159">To find apps installed from **Built by your colleagues**, look for the **TemplatedInstance** value in the **AppDistributionMode** property in a given record's details.</span></span> 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="AppDistributionMode 屬性中 TemplatedInstance 值的螢幕擷取畫面":::

> [!NOTE]
> <span data-ttu-id="a7ee5-161">您可以匯出 CSV 格式的稽核記錄，以便更容易篩選。</span><span class="sxs-lookup"><span data-stu-id="a7ee5-161">You can export audit records in CSV format for easier filtering.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a7ee5-162">相關主題</span><span class="sxs-lookup"><span data-stu-id="a7ee5-162">Related topics</span></span>

- [<span data-ttu-id="a7ee5-163">在應用程式中共用畫布Power Apps</span><span class="sxs-lookup"><span data-stu-id="a7ee5-163">Share a canvas app in Power Apps</span></span>](/powerapps/maker/canvas-apps/share-app)
- [<span data-ttu-id="a7ee5-164">與其他使用者共用您的 Bot</span><span class="sxs-lookup"><span data-stu-id="a7ee5-164">Share your bot with other users</span></span>](/power-virtual-agents/admin-share-bots)
- [<span data-ttu-id="a7ee5-165">在系統管理中心Microsoft Teams應用程式</span><span class="sxs-lookup"><span data-stu-id="a7ee5-165">Manage apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="a7ee5-166">在 Teams 中管理應用程式權限原則</span><span class="sxs-lookup"><span data-stu-id="a7ee5-166">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="a7ee5-167">發佈透過應用程式提交 API Teams提交的自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="a7ee5-167">Publish a custom app submitted through the Teams App Submission API</span></span>](submit-approve-custom-apps.md)