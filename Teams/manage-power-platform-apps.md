---
title: 在 Microsoft [團隊管理中心] 中管理 Power Platform 應用程式
author: lanachin
ms.author: v-lanac
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
description: 瞭解如何在 Microsoft 團隊系統管理中心中管理 Power Platform app 的存取權。
ms.openlocfilehash: 74bfabaff0ec7ed5f27c08ac86b325164d9dad10
ms.sourcegitcommit: af9f96010460f9323db84912fe143aa0750ac798
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171439"
---
# <a name="manage-power-platform-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="28960-103">在 Microsoft [團隊管理中心] 中管理 Power Platform 應用程式</span><span class="sxs-lookup"><span data-stu-id="28960-103">Manage Power Platform apps in the Microsoft Teams admin center</span></span>

## <a name="power-platform-apps-in-teams"></a><span data-ttu-id="28960-104">團隊中的 Power Platform 應用程式</span><span class="sxs-lookup"><span data-stu-id="28960-104">Power Platform apps in Teams</span></span>

<span data-ttu-id="28960-105">本文將說明如何管理新增至 Microsoft 團隊系統管理中心之小組的 [Power Platform](https://powerplatform.microsoft.com/) app。</span><span class="sxs-lookup"><span data-stu-id="28960-105">This article gives you an overview of how to manage [Power Platform](https://powerplatform.microsoft.com/) apps added to Teams in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="28960-106">[Power app](https://powerapps.microsoft.com) 是低代碼/無代碼應用程式開發環境，貴組織中的開發人員可以使用它來建立連線至您的商務資料的自訂應用程式。</span><span class="sxs-lookup"><span data-stu-id="28960-106">[Power Apps](https://powerapps.microsoft.com) is a low-code/no-code application development environment that makers in your organization can use to build custom apps that connect to your business data.</span></span> <span data-ttu-id="28960-107">[Power Virtual agent](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) 是一種無需開發人員用來建立功能強大的機器人的無程式碼 bot 組建環境。</span><span class="sxs-lookup"><span data-stu-id="28960-107">[Power Virtual Agents](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) is a no-code bot building environment for makers to create powerful bots.</span></span> <span data-ttu-id="28960-108">透過將 Power Platform app 整合成小組，組織可以簡化業務流程、回應不斷變化的業務需求，以促進更大的共同作業，並建立及共用自訂解決方案以提高生產力。</span><span class="sxs-lookup"><span data-stu-id="28960-108">With the integration of Power Platform apps into Teams, organizations can streamline business processes, respond to changing business needs more rapidly to drive greater collaboration, and create and share custom solutions to be more productive.</span></span>  

<span data-ttu-id="28960-109">貴組織中由系統製造商所建立的 Power Platform app 會自動新增至團隊。</span><span class="sxs-lookup"><span data-stu-id="28960-109">Power Platform apps created by makers in your organization are automatically added to Teams.</span></span> <span data-ttu-id="28960-110">使用 power Apps 中的 [共用功能](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) 和 [power Virtual agent 中的共用功能](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)，員工可以控制誰可以存取其應用程式。</span><span class="sxs-lookup"><span data-stu-id="28960-110">Makers can control who can access their app by using the [sharing feature in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) and the [sharing feature in Power Virtual Agents](https://docs.microsoft.com/power-virtual-agents/admin-share-bots).</span></span> 

<span data-ttu-id="28960-111">當 Power Platform 應用程式建立或共用時，使用者可以在 [應用程式] 頁面上，透過您的同事建立**的\*組織名稱**\* 來查看並安裝  >  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="28960-111">When a Power Platform app is created or shared, users can view and install it on the Apps page by going to **Built for *Your Organization Name*** > **Built by your colleagues**.</span></span> <span data-ttu-id="28960-112"> (可能需要幾分鐘的時間，才會在應用程式建立或共用之後，才會顯示應用程式。 ) </span><span class="sxs-lookup"><span data-stu-id="28960-112">(It might take a few minutes after an app is created or shared for the app to appear here.)</span></span>

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="[應用程式] 頁面的螢幕擷取畫面，顯示由您的同事建立的 Power Platform app":::

<span data-ttu-id="28960-114">如果應用程式符合下列其中一個條件，使用者就會看到 **由您同事建立** 的 Power Platform 應用程式。</span><span class="sxs-lookup"><span data-stu-id="28960-114">A user will see a Power Platform app in **Built by your colleagues** if the app meets one of the following conditions.</span></span>

|<span data-ttu-id="28960-115">Power App</span><span class="sxs-lookup"><span data-stu-id="28960-115">Power Apps</span></span> |<span data-ttu-id="28960-116">Power Virtual Agent</span><span class="sxs-lookup"><span data-stu-id="28960-116">Power Virtual Agents</span></span>  |
|---------|---------|
|<ul><li><span data-ttu-id="28960-117">使用者建立應用程式。</span><span class="sxs-lookup"><span data-stu-id="28960-117">The user created the app.</span></span></li><li><span data-ttu-id="28960-118">App 是直接與使用者共用。</span><span class="sxs-lookup"><span data-stu-id="28960-118">The app was shared directly with the user.</span></span></li><li><span data-ttu-id="28960-119">使用者最近使用過應用程式。</span><span class="sxs-lookup"><span data-stu-id="28960-119">The user recently used the app.</span></span> </li></ul>| <ul><li><span data-ttu-id="28960-120">使用者建立了 bot。</span><span class="sxs-lookup"><span data-stu-id="28960-120">The user created the bot.</span></span></li><li><span data-ttu-id="28960-121">Bot 是由使用者所屬的小組所擁有。</span><span class="sxs-lookup"><span data-stu-id="28960-121">The bot is owned by a team the user is a member of.</span></span> </li></ul>        |

<span data-ttu-id="28960-122">使用者以安裝任何其他團隊 app 的方式，安裝 Power Platform 應用程式。</span><span class="sxs-lookup"><span data-stu-id="28960-122">Users install Power Platform apps in the same way they install any other Teams app.</span></span> <span data-ttu-id="28960-123">請記住，使用者只能將 app 安裝至他們擁有許可權的內容，例如，擁有者擁有的小組、其所屬的聊天或其個人範圍。</span><span class="sxs-lookup"><span data-stu-id="28960-123">Keep in mind that users can only install  apps to the context to which they have permissions, for example, a team they own, a chat that they're a part of, or their personal scope.</span></span>

## <a name="manage-access-to-power-platform-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="28960-124">管理 Microsoft 團隊系統管理中心的 Power Platform 應用程式存取權</span><span class="sxs-lookup"><span data-stu-id="28960-124">Manage access to Power Platform apps in the Microsoft Teams admin center</span></span>

<span data-ttu-id="28960-125">身為系統管理員，您可以控制 **由您的同事** 在團隊中的 [應用程式] 頁面上所建立的 Power Platform app。</span><span class="sxs-lookup"><span data-stu-id="28960-125">As an admin, you can control whether Power Platform apps are listed in **Built by your colleagues** on the Apps page in Teams.</span></span> <span data-ttu-id="28960-126">您可以在 [ [管理應用程式](manage-apps.md) ] 頁面上的 [管理 app] 頁面上，或針對特定使用者使用 [app 許可權原則](teams-app-permission-policies.md)，綜合封鎖或允許在 power Virtual agent 中建立的所有 app。</span><span class="sxs-lookup"><span data-stu-id="28960-126">You can collectively block or allow all apps created in Power Apps or all apps created in Power Virtual Agents at the org level on the [Manage apps](manage-apps.md) page or for specific users using [app permission policies](teams-app-permission-policies.md).</span></span>

<span data-ttu-id="28960-127">貴組織 app store 中的 [ **共用電源 app** ] 和 [ **共用電源虛擬代理** ] 應用程式代表在該特定平臺上建立的所有 app。</span><span class="sxs-lookup"><span data-stu-id="28960-127">The **Shared Power Apps** and **Shared Power Virtual Agent Apps** apps in your organization's app store represent all apps created on that particular platform.</span></span> <span data-ttu-id="28960-128">如果您在組織階層或針對特定使用者封鎖其中一個或兩個應用程式，這些使用者就無法看到 **由您的同事建立** 的那些平臺中的任何應用程式，而且無法在小組中安裝它們。</span><span class="sxs-lookup"><span data-stu-id="28960-128">If you block one or both these apps at the org level or for specific users, those users can't see any apps from those platforms in **Built by your colleagues** and can't install them in Teams.</span></span>  

<span data-ttu-id="28960-129">請記住，您可以控制對 Power App 和 Power Virtual Agent 中所建立之所有 app 的存取，但您無法允許或封鎖個別的應用程式。</span><span class="sxs-lookup"><span data-stu-id="28960-129">Keep in mind that you can control access to all apps created in Power Apps and Power Virtual Agents but you can't allow or block individual apps.</span></span> <span data-ttu-id="28960-130">在 Power App 和 Power Virtual Agent 中，您可以透過共用功能來決定誰可以存取他們所建立的應用程式。</span><span class="sxs-lookup"><span data-stu-id="28960-130">Makers decide who can access the apps they create through the sharing feature from within Power Apps and Power Virtual Agents.</span></span> <span data-ttu-id="28960-131">如果您的 maker 是與使用者在 Power Virtual Agent 中建立的應用程式，而且您已封鎖該使用者的 **共用 Power Virtual Agent 應用** 程式，則使用者將無法在團隊中看到或安裝該平臺中的任何應用程式。</span><span class="sxs-lookup"><span data-stu-id="28960-131">If a maker shared an app they created in Power Virtual Agents with a user and you blocked **Shared Power Virtual Agents Apps** for that user, the user won't be able to see or install any apps from that platform in Teams.</span></span>

<span data-ttu-id="28960-132">如果允許使用者從 Power Apps 或 Power Virtual Agent 存取應用程式，然後封鎖使用者從這兩個平臺的其中一個或兩個都存取應用程式，使用者仍然可以存取及使用其在您封鎖 app 或應用程式之前所安裝的 Power 平臺應用程式。</span><span class="sxs-lookup"><span data-stu-id="28960-132">If a user is allowed to access apps from Power Apps or Power Virtual Agents, and you then block the user from accessing apps from one or both these platforms, the user can still access and use the Power Platforms apps that they installed before you blocked the app or apps.</span></span> <span data-ttu-id="28960-133">不過，使用者不能再看到或安裝來自 **您同事所建**之平臺的任何應用程式。</span><span class="sxs-lookup"><span data-stu-id="28960-133">However, the user can no longer see or install any apps from those platforms in **Built by your colleagues**.</span></span>

> [!NOTE]
> <span data-ttu-id="28960-134">[[管理應用程式](manage-apps.md)] 頁面上的 [**允許與自訂應用程式互動] 與**[管理 app] 頁面上的 [全式應用程式] 設定適用于組織中的所有人，並可控制他們是否</span><span class="sxs-lookup"><span data-stu-id="28960-134">The **Allow interaction with custom apps** org-wide app setting on the [Manage apps](manage-apps.md) page applies to everyone in your organization and governs whether they can interact with custom apps.</span></span> <span data-ttu-id="28960-135">全組織式應用程式設定會控制所有使用者的行為，並覆寫指派給使用者的任何其他應用程式許可權原則。</span><span class="sxs-lookup"><span data-stu-id="28960-135">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="28960-136">根據預設，此設定為開啟狀態。</span><span class="sxs-lookup"><span data-stu-id="28960-136">By default, this setting is turned on.</span></span> <span data-ttu-id="28960-137">如果關閉此設定，貴組織中的使用者將無法看到或安裝任何自訂應用程式，包括 Power Platform app。</span><span class="sxs-lookup"><span data-stu-id="28960-137">If this setting is turned off, users in your organization can't see or install any custom apps, including Power Platform apps.</span></span> <span data-ttu-id="28960-138">若要深入瞭解，請參閱 [管理整個組織內的應用程式設定](manage-apps.md#manage-org-wide-app-settings)。</span><span class="sxs-lookup"><span data-stu-id="28960-138">To learn  more, see [Manage org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

### <a name="allow-or-block-power-platform-apps-for-your-organization"></a><span data-ttu-id="28960-139">允許或封鎖貴組織的 Power Platform 應用程式</span><span class="sxs-lookup"><span data-stu-id="28960-139">Allow or block Power Platform apps for your organization</span></span>

<span data-ttu-id="28960-140">根據預設，您組織中的所有團隊使用者都可以使用 **共用的 Power app** 和 **共用的 Power Virtual Agent app** 。</span><span class="sxs-lookup"><span data-stu-id="28960-140">By default, **Shared Power Apps** and **Shared Power Virtual Agent Apps** are allowed for all Teams users in your organization.</span></span> <span data-ttu-id="28960-141">您可以在 Microsoft 團隊系統管理中心的 [ [管理應用程式](manage-apps.md) ] 頁面上，在組織階層封鎖或允許。</span><span class="sxs-lookup"><span data-stu-id="28960-141">You can block or allow them at the org level on the [Manage apps](manage-apps.md) page of the Microsoft Teams admin center.</span></span>  

1. <span data-ttu-id="28960-142">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **管理應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="28960-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="28960-143">您必須是全域系統管理員或團隊服務系統管理員，才能存取該頁面。</span><span class="sxs-lookup"><span data-stu-id="28960-143">You must be a global admin or Teams service admin to access the page.</span></span>
2. <span data-ttu-id="28960-144">在應用程式清單中，執行下列其中一項操作。</span><span class="sxs-lookup"><span data-stu-id="28960-144">In the list of apps, do one of the following.</span></span>

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="[管理應用程式] 頁面的螢幕擷取畫面，顯示共用的 Power Platform 應用程式":::

    - <span data-ttu-id="28960-146">若要封鎖貴組織中所有使用者在 Power App 或 Power Virtual Agent 中建立的應用程式，請搜尋 **共用的 Power app** 或 **共用的 Power Virtual agent 應用程式**，選取它，然後按一下 [ **封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="28960-146">To block apps created in Power Apps or Power Virtual Agents for all users in your organization, search for **Shared Power Apps** or **Shared Power Virtual Agent Apps**, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="28960-147">若要允許貴組織中所有使用者在 Power App 或 Power Virtual Agent 中建立的應用程式，請搜尋 **共用的 Power app** 或 **共用的 Power Virtual agent 應用程式**，選取它，然後按一下 [ **允許**]。</span><span class="sxs-lookup"><span data-stu-id="28960-147">To allow apps created in Power Apps or Power Virtual Agents for all users in your organization, search for **Shared Power Apps** or **Shared Power Virtual Agent Apps**, select it, and then click **Allow**.</span></span>

### <a name="allow-or-block-power-platform-apps-for-specific-users"></a><span data-ttu-id="28960-148">針對特定使用者允許或封鎖 Power Platform 應用程式</span><span class="sxs-lookup"><span data-stu-id="28960-148">Allow or block Power Platform apps for specific users</span></span>

<span data-ttu-id="28960-149">若要允許或封鎖貴組織中的特定使用者存取在 Power App 或 Power Virtual Agent 中建立的應用程式，請建立並指派一或多個自訂 [應用程式許可權原則](teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="28960-149">To allow or block specific users in your organization from accessing apps created in Power Apps or Power Virtual Agents, create and assign one or more custom [app permission policies](teams-app-permission-policies.md).</span></span> 

<span data-ttu-id="28960-150">例如，若要封鎖特定使用者存取在 Power 應用程式中建立的應用程式，請建立自訂應用程式許可權原則來封鎖 **共用的 Power 應用程式**，然後將原則指派給這些使用者。</span><span class="sxs-lookup"><span data-stu-id="28960-150">For example, to block specific users from accessing apps created in Power Apps, create a custom app permission policy to block **Shared Power Apps**, and then assign the policy to those users.</span></span>

:::image type="content" source="media/manage-power-platform-apps-app-permissions-policy.png" alt-text="已封鎖共用電源 app 之範例自訂應用程式許可權原則的螢幕擷取畫面":::

## <a name="related-topics"></a><span data-ttu-id="28960-152">相關主題</span><span class="sxs-lookup"><span data-stu-id="28960-152">Related topics</span></span>

- [<span data-ttu-id="28960-153">在 Power 應用程式中共用畫布 app</span><span class="sxs-lookup"><span data-stu-id="28960-153">Share a canvas app in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app)
- [<span data-ttu-id="28960-154">與其他使用者共用您的機器人</span><span class="sxs-lookup"><span data-stu-id="28960-154">Share your bot with other users</span></span>](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)
- [<span data-ttu-id="28960-155">在 Microsoft 團隊系統管理中心中管理應用程式</span><span class="sxs-lookup"><span data-stu-id="28960-155">Manage apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="28960-156">在 Teams 中管理應用程式權限原則</span><span class="sxs-lookup"><span data-stu-id="28960-156">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="28960-157">發佈透過團隊 App 提交 API 提交的自訂應用程式</span><span class="sxs-lookup"><span data-stu-id="28960-157">Publish a custom app submitted through the Teams App Submission API</span></span>](submit-approve-custom-apps.md)
