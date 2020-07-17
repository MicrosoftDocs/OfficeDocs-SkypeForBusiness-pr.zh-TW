---
title: 為您的組織管理倒班應用程式
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何針對貴組織中的第一線員工工作人員，在小組中設定和管理倒班 app。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ecc64c105bb9171942dfac912ccea4f2fa1442aa
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938352"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="0b392-103">在 Microsoft 團隊中為您的組織管理倒班應用程式</span><span class="sxs-lookup"><span data-stu-id="0b392-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0b392-104">2020年6月30日生效，Microsoft StaffHub 已停用。</span><span class="sxs-lookup"><span data-stu-id="0b392-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="0b392-105">我們正在將 StaffHub 功能組建至 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="0b392-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="0b392-106">今天，小組包含針對排程管理的倒班應用程式，而其他功能則會隨著時間推移而推出。</span><span class="sxs-lookup"><span data-stu-id="0b392-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="0b392-107">StaffHub 已停止針對2020年6月30日的所有使用者使用。</span><span class="sxs-lookup"><span data-stu-id="0b392-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="0b392-108">任何試圖開啟 StaffHub 的人都會顯示一則訊息，讓他們下載團隊。</span><span class="sxs-lookup"><span data-stu-id="0b392-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="0b392-109">若要深入瞭解，請參閱[Microsoft StaffHub 已停](microsoft-staffhub-to-be-retired.md)用。</span><span class="sxs-lookup"><span data-stu-id="0b392-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="0b392-110">班次的概覽</span><span class="sxs-lookup"><span data-stu-id="0b392-110">Overview of Shifts</span></span>

<span data-ttu-id="0b392-111">Microsoft 團隊中的 [倒班] 應用程式會讓第一線員工工作人員保持連線並同步處理。它會先建立行動裝置，以快速且有效地管理和溝通小組的時間。</span><span class="sxs-lookup"><span data-stu-id="0b392-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="0b392-112">[倒班] 讓第一線員工工作者及其主管使用行動裝置管理排程，並保持聯繫。</span><span class="sxs-lookup"><span data-stu-id="0b392-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="0b392-113">管理員建立、更新及管理團隊的倒班排程。</span><span class="sxs-lookup"><span data-stu-id="0b392-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="0b392-114">他們可以將訊息傳送給一個人（「在地面有溢出）」或整個小組（「地區 GM 已在20分鐘內抵達」）。</span><span class="sxs-lookup"><span data-stu-id="0b392-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="0b392-115">他們也可以傳送原則檔、新聞佈告及影片。</span><span class="sxs-lookup"><span data-stu-id="0b392-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="0b392-116">員工要查看他們的後續班次，可以查看當天排程的人員、要求交換或提供倒班，以及要求下班時間。</span><span class="sxs-lookup"><span data-stu-id="0b392-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="0b392-117">我們必須知道，倒班目前不支援來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="0b392-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="0b392-118">這表示當您在小組中開啟來賓存取功能時，小組中的來賓不能加入或使用倒班排程。</span><span class="sxs-lookup"><span data-stu-id="0b392-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="0b392-119">倒班的可用性</span><span class="sxs-lookup"><span data-stu-id="0b392-119">Availability of Shifts</span></span>

<span data-ttu-id="0b392-120">在可使用團隊的所有企業 Sku 中，都提供倒班。</span><span class="sxs-lookup"><span data-stu-id="0b392-120">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="0b392-121">倒班資料的位置</span><span class="sxs-lookup"><span data-stu-id="0b392-121">Location of Shifts data</span></span>

<span data-ttu-id="0b392-122">倒班資料目前儲存在北美、西歐及亞太地區資料中心的 Azure 中。</span><span class="sxs-lookup"><span data-stu-id="0b392-122">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="0b392-123">如需有關資料儲存位置的詳細資訊，請參閱[我的資料在哪裡](http://o365datacentermap.azurewebsites.net/)？</span><span class="sxs-lookup"><span data-stu-id="0b392-123">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="0b392-124">設定倒班</span><span class="sxs-lookup"><span data-stu-id="0b392-124">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="0b392-125">在組織中啟用或停用倒班</span><span class="sxs-lookup"><span data-stu-id="0b392-125">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="0b392-126">預設會針對貴組織中的所有團隊使用者啟用班次。</span><span class="sxs-lookup"><span data-stu-id="0b392-126">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="0b392-127">您可以在 Microsoft 團隊系統管理中心的 [[管理應用程式](../../manage-apps.md)] 頁面上關閉或開啟組織階層的 app。</span><span class="sxs-lookup"><span data-stu-id="0b392-127">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="0b392-128">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **管理應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="0b392-128">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps** .</span></span>
2. <span data-ttu-id="0b392-129">在應用程式清單中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="0b392-129">In the list of apps, do one of the following:</span></span>

    - <span data-ttu-id="0b392-130">若要關閉貴組織的倒班，請搜尋 [倒班] app，選取它，然後按一下 [**封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="0b392-130">To turn off Shifts for your organization, search for the Shifts app, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="0b392-131">若要為您的組織開啟倒班，請搜尋 [倒班] app，選取它，然後按一下 [**允許**]。</span><span class="sxs-lookup"><span data-stu-id="0b392-131">To turn on Shifts for your organization, search for the Shifts app, select it, and then click **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="0b392-132">針對貴組織中的特定使用者啟用或停用班次</span><span class="sxs-lookup"><span data-stu-id="0b392-132">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="0b392-133">若要允許或封鎖貴組織中的特定使用者使用倒班，請確定您的組織已開啟 [[管理應用程式](../../manage-apps.md)] 頁面上的 [倒班]，然後建立自訂應用程式許可權原則，並將其指派給那些使用者。</span><span class="sxs-lookup"><span data-stu-id="0b392-133">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="0b392-134">若要深入瞭解，請參閱[在團隊中管理 app 許可權原則](../../teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0b392-134">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="0b392-135">使用 FirstlineWorker 應用程式設定原則釘選到團隊</span><span class="sxs-lookup"><span data-stu-id="0b392-135">Use the FirstlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="0b392-136">App 設定原則可讓您自訂小組，以醒目提示貴組織中的使用者最重要的 app。</span><span class="sxs-lookup"><span data-stu-id="0b392-136">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="0b392-137">原則中設定的應用程式會釘選到應用程式行， &mdash; 以及小組行動用戶端的右側列， &mdash; 使用者可以快速且輕鬆地存取。</span><span class="sxs-lookup"><span data-stu-id="0b392-137">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span>
 
<span data-ttu-id="0b392-138">團隊包含內建的 FirstlineWorker 應用程式設定原則，您可以將它指派給貴組織中的第一線員工工作人員。</span><span class="sxs-lookup"><span data-stu-id="0b392-138">Teams includes a built-in FirstlineWorker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="0b392-139">根據預設，原則包含活動、班次、聊天及呼叫 app。</span><span class="sxs-lookup"><span data-stu-id="0b392-139">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="0b392-140">若要查看 FirstlineWorker 原則，請在 Microsoft 團隊系統管理中心的左導覽中，移至 [**小組 app**  >  **應用程式] 設定原則**。</span><span class="sxs-lookup"><span data-stu-id="0b392-140">To view the FirstlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="0b392-141">![FirstlineWorker 應用程式設定原則的螢幕擷取畫面](../../media/firstline-worker-app-setup-policy.png "Microsoft 團隊系統管理中心的 FirstlineWorker 應用程式設定原則的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="0b392-141">![Screenshot of the FirstlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FirstlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="0b392-142">將 FirstlineWorker 應用程式設定原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="0b392-142">Assign the FirstlineWorker app setup policy to users</span></span>

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="0b392-143">搜尋審核記錄，以取得倒班事件</span><span class="sxs-lookup"><span data-stu-id="0b392-143">Search the audit log for Shifts events</span></span>

<span data-ttu-id="0b392-144">**(預覽)**</span><span class="sxs-lookup"><span data-stu-id="0b392-144">**(in preview)**</span></span>

<span data-ttu-id="0b392-145">您可以搜尋 [審核記錄]，在您的組織中查看倒班活動。</span><span class="sxs-lookup"><span data-stu-id="0b392-145">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="0b392-146">若要深入瞭解如何搜尋審核記錄，以及查看已記錄在審核記錄中的[倒班活動](../../audit-log-events.md#shifts-in-teams-activities)清單，請參閱[搜尋小組中事件的審核記錄](../../audit-log-events.md)。</span><span class="sxs-lookup"><span data-stu-id="0b392-146">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="0b392-147">在您可以搜尋審核記錄之前，您必須先在[安全性 & 合規性中心](https://protection.office.com)開啟審核。</span><span class="sxs-lookup"><span data-stu-id="0b392-147">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="0b392-148">若要深入瞭解，請參閱[開啟或關閉審核記錄搜尋](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。</span><span class="sxs-lookup"><span data-stu-id="0b392-148">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="0b392-149">請記住，審核資料只能從您開啟審核的位置取得。</span><span class="sxs-lookup"><span data-stu-id="0b392-149">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0b392-150">相關主題</span><span class="sxs-lookup"><span data-stu-id="0b392-150">Related topics</span></span>

- [<span data-ttu-id="0b392-151">倒班第一線員工工作者的協助</span><span class="sxs-lookup"><span data-stu-id="0b392-151">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="0b392-152">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="0b392-152">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
