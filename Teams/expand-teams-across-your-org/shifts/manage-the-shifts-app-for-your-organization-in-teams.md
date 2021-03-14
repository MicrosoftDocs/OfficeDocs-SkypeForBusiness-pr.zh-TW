---
title: 管理組織的 [班次] 應用程式
author: cichur
ms.author: v-cichur
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 了解如何在組織的前線員工在 Teams 中設定及管理班次應用程式。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 218b041d83cde91a23201ab864160ce3b8b7cb6e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909087"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="101c2-103">在 Microsoft Teams 中管理貴組織的 [班次] 應用程式</span><span class="sxs-lookup"><span data-stu-id="101c2-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="101c2-104">自 2020 年 6 月 30 起，已終止對 Microsoft StaffHub 的支援。</span><span class="sxs-lookup"><span data-stu-id="101c2-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="101c2-105">我們正在將 StaffHub 功能建入 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="101c2-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="101c2-106">今天，Teams 包含用於排程管理的班次應用程式，並且會陸續推出其他功能。</span><span class="sxs-lookup"><span data-stu-id="101c2-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="101c2-107">所有使用者自 2020 年 6 月 30 日起皆無法再使用 StaffHub。</span><span class="sxs-lookup"><span data-stu-id="101c2-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="101c2-108">任何嘗試開啟 StaffHub 的人，都會看到一則訊息，指示他們下載 Teams。</span><span class="sxs-lookup"><span data-stu-id="101c2-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="101c2-109">如需深入了解，請參閱[已終止對 Microsoft StaffHub 的支援](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="101c2-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="101c2-110">班次概觀</span><span class="sxs-lookup"><span data-stu-id="101c2-110">Overview of Shifts</span></span>

<span data-ttu-id="101c2-111">Microsoft Teams 中的班次應用程式讓前線員工保持聯繫並同步。它以行動裝置為導向，專門為快速且有效的團隊時間管理和通訊而打造。</span><span class="sxs-lookup"><span data-stu-id="101c2-111">The Shifts app in Microsoft Teams keeps Frontline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="101c2-112">班次可讓前線工作者及其主管使用行動裝置來管理排程，以及保持聯繫。</span><span class="sxs-lookup"><span data-stu-id="101c2-112">Shifts lets Frontline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="101c2-113">主管建立、更新及管理團隊的排班表。</span><span class="sxs-lookup"><span data-stu-id="101c2-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="101c2-114">主管也可以傳送訊息給單一個人 (「地板上有打翻的液體」) 或整個團隊 (「區域總經理將於 20 分鐘後抵達」)。</span><span class="sxs-lookup"><span data-stu-id="101c2-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="101c2-115">主管還可以傳送原則文件、新訊佈告欄或影片。</span><span class="sxs-lookup"><span data-stu-id="101c2-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="101c2-116">員工可查看預排的班次、查看當天還有誰已排班、要求調班或調班，以及要求請假。</span><span class="sxs-lookup"><span data-stu-id="101c2-116">Employees view their upcoming shifts, see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="101c2-117">請注意，班次目前不支援來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="101c2-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="101c2-118">這表示在 Teams 中開啟來賓存取時，團隊中的來賓無法新增或使用班次排程。</span><span class="sxs-lookup"><span data-stu-id="101c2-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

> [!Note]
> <span data-ttu-id="101c2-119">如需有關不同平台上班次功能的詳細資訊，請參閱[依平台的 Teams 功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。</span><span class="sxs-lookup"><span data-stu-id="101c2-119">For details about Shifts capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="availability-of-shifts"></a><span data-ttu-id="101c2-120">班次的可用性</span><span class="sxs-lookup"><span data-stu-id="101c2-120">Availability of Shifts</span></span>

<span data-ttu-id="101c2-121">班次可在可用 Teams 的所有企業 SKUS 中使用。</span><span class="sxs-lookup"><span data-stu-id="101c2-121">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="101c2-122">班次資料的位置</span><span class="sxs-lookup"><span data-stu-id="101c2-122">Location of Shifts data</span></span>

<span data-ttu-id="101c2-123">班次資料目前儲存在位於北美洲、西歐和亞太地區資料中心的 Azure 中。</span><span class="sxs-lookup"><span data-stu-id="101c2-123">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="101c2-124">如需有關資料儲存位置的詳細資訊，請參閱[我的資料在哪裡](http://o365datacentermap.azurewebsites.net/)？</span><span class="sxs-lookup"><span data-stu-id="101c2-124">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="101c2-125">設定班次</span><span class="sxs-lookup"><span data-stu-id="101c2-125">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="101c2-126">啟用或停用組織中的 [班次]</span><span class="sxs-lookup"><span data-stu-id="101c2-126">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="101c2-127">您的組織中的所有 Teams 使用者預設會啟用 [班次]。</span><span class="sxs-lookup"><span data-stu-id="101c2-127">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="101c2-128">您可以在 Microsoft Teams 系統管理中心的[管理應用程式](../../manage-apps.md)頁面上關閉或開啟組織層級的應用程式。</span><span class="sxs-lookup"><span data-stu-id="101c2-128">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="101c2-129">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 **Teams 應用程式** > **管理應用程式**。</span><span class="sxs-lookup"><span data-stu-id="101c2-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="101c2-130">在應用程式清單中，執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="101c2-130">In the list of apps, do one of the following actions:</span></span>

    - <span data-ttu-id="101c2-131">若要關閉貴組織的 [班次]，請搜尋 [班次] 應用程式，加以選取，然後選取 **封鎖**。</span><span class="sxs-lookup"><span data-stu-id="101c2-131">To turn off Shifts for your organization, search for the Shifts app, select it, and then select **Block**.</span></span>
    - <span data-ttu-id="101c2-132">若要開啟貴組織的 [班次]，請搜尋 [班次] 應用程式，加以選取，然後選取 **允許**。</span><span class="sxs-lookup"><span data-stu-id="101c2-132">To turn on Shifts for your organization, search for the Shifts app, select it, and then select **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="101c2-133">啟用或停用組織中特定使用者的 [班次]</span><span class="sxs-lookup"><span data-stu-id="101c2-133">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="101c2-134">若要允許或封鎖貴組織中的特定使用者使用 [班次]，請確定您的組織在[管理應用程式](../../manage-apps.md)頁面上已開啟 [班次]，然後建立自訂應用程式權限原則，並將其指派給這些使用者。</span><span class="sxs-lookup"><span data-stu-id="101c2-134">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="101c2-135">如需深入了解，請參閱[管理 Teams 中的應用程式權限原則](../../teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="101c2-135">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="101c2-136">使用 FrontlineWorker 應用程式設定原則將班次釘選至 Teams</span><span class="sxs-lookup"><span data-stu-id="101c2-136">Use the FrontlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="101c2-137">應用程式設定原則可讓您自訂 Teams，以醒目提示對貴組織中使用者最重要的應用程式。</span><span class="sxs-lookup"><span data-stu-id="101c2-137">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="101c2-138">您在原則中設定的應用程式會釘選到應用程式列&mdash;位於 Teams 桌面版用戶端側邊列，以及位於 Teams 行動版用戶端底部&mdash;，可讓使用者快速且輕鬆地存取。</span><span class="sxs-lookup"><span data-stu-id="101c2-138">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span>
 
<span data-ttu-id="101c2-139">Teams 包含內建的 FrontlineWorker 應用程式設定原則，您可以指派給貴組織的前線員工。</span><span class="sxs-lookup"><span data-stu-id="101c2-139">Teams includes a built-in FrontlineWorker app setup policy that you can assign to Frontline Workers in your organization.</span></span> <span data-ttu-id="101c2-140">根據預設，此策略包含活動、班次、聊天和通話應用程式。</span><span class="sxs-lookup"><span data-stu-id="101c2-140">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="101c2-141">如需檢視 FrontlineWorker 原則，請前往 Microsoft Teams 系統管理中心左側瀏覽的 **Teams 應用程式** > **應用程式設原則**。</span><span class="sxs-lookup"><span data-stu-id="101c2-141">To view the FrontlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="101c2-142">![FrontlineWorker 應用程式設定原則的螢幕擷取畫面](../../media/firstline-worker-app-setup-policy.png "Microsoft Teams 系統管理中心的 FrontlineWorker 應用程式設定原則螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="101c2-142">![Screenshot of the FrontlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FrontlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a><span data-ttu-id="101c2-143">將 FrontlineWorker 應用程式設定原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="101c2-143">Assign the FrontlineWorker app setup policy to users</span></span>

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="101c2-144">搜尋班次活動的稽核記錄檔</span><span class="sxs-lookup"><span data-stu-id="101c2-144">Search the audit log for Shifts events</span></span>

<span data-ttu-id="101c2-145">**(預覽)**</span><span class="sxs-lookup"><span data-stu-id="101c2-145">**(in preview)**</span></span>

<span data-ttu-id="101c2-146">您可以搜尋稽核記錄來查看貴組織的班次活動。</span><span class="sxs-lookup"><span data-stu-id="101c2-146">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="101c2-147">如需深入了解如何搜尋稽核記錄，以及查看稽核記錄中記錄的[班次活動](../../audit-log-events.md#shifts-in-teams-activities)清單，請參閱 [在 Teams 中搜尋活動的稽核記錄](../../audit-log-events.md)。</span><span class="sxs-lookup"><span data-stu-id="101c2-147">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="101c2-148">在您可以搜尋稽核記錄檔之前，您必須先在[安全性與合規性中心](https://protection.office.com)中開啟稽核。</span><span class="sxs-lookup"><span data-stu-id="101c2-148">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="101c2-149">如需深入了解，請參閱[開啟或關閉稽核記錄](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。</span><span class="sxs-lookup"><span data-stu-id="101c2-149">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="101c2-150">請記住，只有當您開啟稽核時，才能使用稽核資料。</span><span class="sxs-lookup"><span data-stu-id="101c2-150">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="101c2-151">相關主題</span><span class="sxs-lookup"><span data-stu-id="101c2-151">Related topics</span></span>

- [<span data-ttu-id="101c2-152">前線員工班次說明</span><span class="sxs-lookup"><span data-stu-id="101c2-152">Shifts Help for Frontline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="101c2-153">將原則指派給 Teams 中的使用者</span><span class="sxs-lookup"><span data-stu-id="101c2-153">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
