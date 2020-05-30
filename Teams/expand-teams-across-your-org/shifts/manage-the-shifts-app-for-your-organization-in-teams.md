---
title: 為您的組織管理倒班應用程式
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
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
ms.openlocfilehash: c2ca24f2176547f83efb6bdce591ac71d516dca9
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416883"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="3dfaf-103">在 Microsoft 團隊中為您的組織管理倒班應用程式</span><span class="sxs-lookup"><span data-stu-id="3dfaf-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3dfaf-104">2020年6月30日生效，Microsoft StaffHub 將停用。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-104">Effective June 30, 2020, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="3dfaf-105">我們正在將 StaffHub 功能組建至 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="3dfaf-106">今天，小組包含針對排程管理的倒班應用程式，而其他功能則會隨著時間推移而推出。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="3dfaf-107">StaffHub 將會針對2020年6月30日的所有使用者停止運作。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-107">StaffHub will stop working for all users on June 30, 2020.</span></span> <span data-ttu-id="3dfaf-108">任何試圖開啟 StaffHub 的人，都會顯示一則訊息，讓他們下載小組。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="3dfaf-109">若要深入瞭解，請參閱[Microsoft StaffHub 停用](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="3dfaf-110">班次的概覽</span><span class="sxs-lookup"><span data-stu-id="3dfaf-110">Overview of Shifts</span></span>

<span data-ttu-id="3dfaf-111">Microsoft 團隊中的 [倒班] 應用程式會讓第一線員工工作人員保持連線並同步處理。它會先建立行動裝置，以快速且有效地管理和溝通小組的時間。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="3dfaf-112">[倒班] 讓第一線員工工作者及其主管使用行動裝置管理排程，並保持聯繫。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="3dfaf-113">管理員建立、更新及管理團隊的倒班排程。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="3dfaf-114">他們可以將訊息傳送給一個人（「在地面有溢出）」或整個小組（「地區 GM 已在20分鐘內抵達」）。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="3dfaf-115">他們也可以傳送原則檔、新聞佈告及影片。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="3dfaf-116">員工要查看他們的後續班次，可以查看當天排程的人員、要求交換或提供倒班，以及要求下班時間。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="3dfaf-117">我們必須知道，倒班目前不支援來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="3dfaf-118">這表示當您在小組中開啟來賓存取功能時，小組中的來賓不能加入或使用倒班排程。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="3dfaf-119">倒班的可用性</span><span class="sxs-lookup"><span data-stu-id="3dfaf-119">Availability of Shifts</span></span>

<span data-ttu-id="3dfaf-120">在可使用團隊的所有企業 Sku 中，都提供倒班。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-120">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="3dfaf-121">倒班資料的位置</span><span class="sxs-lookup"><span data-stu-id="3dfaf-121">Location of Shifts data</span></span>

<span data-ttu-id="3dfaf-122">倒班資料目前儲存在北美、西歐及亞太地區資料中心的 Azure 中。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-122">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="3dfaf-123">如需有關資料儲存位置的詳細資訊，請參閱[我的資料在哪裡](http://o365datacentermap.azurewebsites.net/)？</span><span class="sxs-lookup"><span data-stu-id="3dfaf-123">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="3dfaf-124">設定倒班</span><span class="sxs-lookup"><span data-stu-id="3dfaf-124">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="3dfaf-125">在組織中啟用或停用倒班</span><span class="sxs-lookup"><span data-stu-id="3dfaf-125">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="3dfaf-126">預設會針對貴組織中的所有團隊使用者啟用班次。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-126">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="3dfaf-127">您可以在 Microsoft 團隊系統管理中心的 [[管理應用程式](../../manage-apps.md)] 頁面上關閉或開啟組織階層的 app。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-127">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="3dfaf-128">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **管理應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-128">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps** .</span></span>
2. <span data-ttu-id="3dfaf-129">在應用程式清單中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="3dfaf-129">In the list of apps, do one of the following:</span></span>

    - <span data-ttu-id="3dfaf-130">若要關閉貴組織的倒班，請搜尋 [倒班] app，選取它，然後按一下 [**封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-130">To turn off Shifts for your organization, search for the Shifts app, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="3dfaf-131">若要為您的組織開啟倒班，請搜尋 [倒班] app，選取它，然後按一下 [**允許**]。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-131">To turn on Shifts for your organization, search for the Shifts app, select it, and then click **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="3dfaf-132">針對貴組織中的特定使用者啟用或停用班次</span><span class="sxs-lookup"><span data-stu-id="3dfaf-132">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="3dfaf-133">若要允許或封鎖貴組織中的特定使用者使用倒班，請確定您的組織已開啟 [[管理應用程式](../../manage-apps.md)] 頁面上的 [倒班]，然後建立自訂應用程式許可權原則，並將其指派給那些使用者。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-133">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="3dfaf-134">若要深入瞭解，請參閱[在團隊中管理 app 許可權原則](../../teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-134">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="3dfaf-135">使用 FirstlineWorker 應用程式設定原則釘選到團隊</span><span class="sxs-lookup"><span data-stu-id="3dfaf-135">Use the FirstlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="3dfaf-136">App 設定原則可讓您自訂小組，以醒目提示貴組織中的使用者最重要的 app。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-136">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="3dfaf-137">原則中設定的應用程式會釘選到應用程式行， &mdash; 以及小組行動用戶端的右側列， &mdash; 使用者可以快速且輕鬆地存取。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-137">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="3dfaf-138">團隊包含內建的 FirstlineWorker 應用程式設定原則，您可以將它指派給貴組織中的第一線員工工作人員。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-138">Teams includes a built-in FirstlineWorker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="3dfaf-139">根據預設，原則包含活動、班次、聊天及呼叫 app。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-139">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="3dfaf-140">若要查看 FirstlineWorker 原則，請在 Microsoft 團隊系統管理中心的左導覽中，移至 [**小組 app**  >  **應用程式] 設定原則**。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-140">To view the FirstlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="3dfaf-141">![FirstlineWorker 應用程式設定原則的螢幕擷取畫面](../../media/firstline-worker-app-setup-policy.png "Microsoft 團隊系統管理中心的 FirstlineWorker 應用程式設定原則的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="3dfaf-141">![Screenshot of the FirstlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FirstlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-policy-to-users"></a><span data-ttu-id="3dfaf-142">指派 FirstlineWorker 原則給使用者</span><span class="sxs-lookup"><span data-stu-id="3dfaf-142">Assign the FirstlineWorker policy to users</span></span>

<span data-ttu-id="3dfaf-143">若要將 FirstlineWorker 應用程式設定原則指派給一個使用者：</span><span class="sxs-lookup"><span data-stu-id="3dfaf-143">To assign the FirstlineWorker app setup policy to one user:</span></span>

1. <span data-ttu-id="3dfaf-144">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]\*\*\*\*，然後按一下該使用者。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-144">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="3dfaf-145">按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-145">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="3dfaf-146">在 [**應用程式設定原則**] 底下，選取 [ **FirstlineWorker**]，**然後按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-146">Under **App setup policy**, select **FirstlineWorker**, and then click **Apply**.</span></span>

<span data-ttu-id="3dfaf-147">若要一次將原則指派給多位使用者：</span><span class="sxs-lookup"><span data-stu-id="3dfaf-147">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="3dfaf-148">在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 [使用者]\*\*\*\*，然後搜尋使用者或篩選檢視畫面，以顯示您想要的使用者。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-148">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="3dfaf-149">在 [&#x2713;]\*\*\*\* (核取方塊) 欄中，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-149">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="3dfaf-150">若要選取 [所有使用者]，請按一下表格頂端的 [&#x2713;] (核取方塊)。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-150">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="3dfaf-151">按一下 [**編輯設定**]，然後在 [**應用程式設定原則**] 底下選取 [ **FirstlineWorker**]，**然後按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-151">Click **Edit settings**, under **App setup policy**, select **FirstlineWorker**, and then click **Apply**.</span></span>  

<span data-ttu-id="3dfaf-152">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3dfaf-152">Or, you can also do the following:</span></span>

1. <span data-ttu-id="3dfaf-153">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app**  >  **設定原則**]。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-153">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="3dfaf-154">按一下原則名稱左邊的，以選取 FirstlineWorker 原則。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-154">Select the FirstlineWorker policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="3dfaf-155">選取 [管理使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-155">Select **Manage users**.</span></span>
4. <span data-ttu-id="3dfaf-156">在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-156">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="3dfaf-157">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-157">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="3dfaf-158">完成新增使用者後，**請選取 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-158">After you finish adding users, select **Apply**.</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-user-members-of-a-group"></a><span data-ttu-id="3dfaf-159">將 FirstlineWorker 應用程式設定原則指派給群組的使用者成員</span><span class="sxs-lookup"><span data-stu-id="3dfaf-159">Assign the FirstlineWorker app setup policy to user members of a group</span></span>

<span data-ttu-id="3dfaf-160">您可以將 FirstlineWorker 應用程式設定原則指派給群組的使用者成員（例如安全性群組），方法是連線到 Azure Active Directory PowerShell for Graph 模組及商務用 Skype PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-160">You can assign the FirstlineWorker app setup policy to user members of a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="3dfaf-161">如需有關使用 PowerShell 來管理團隊的詳細資訊，請參閱[團隊 PowerShell 概覽](../../teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-161">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](../../teams-powershell-overview.md).</span></span>

<span data-ttu-id="3dfaf-162">在這個範例中，我們會將 FirstlineWorker 應用程式設定原則指派給 Contoso 第一線員工小組群組的所有使用者成員。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-162">In this example, we assign the FirstlineWorker app setup policy to all user members of the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="3dfaf-163">請依照在[單一 Windows PowerShell 視窗中連線至 [所有 Office 365 服務]](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步驟，確認您首先連線至 [圖形模組] 和 [商務用 Skype] powershell 模組的 [Azure Active Directory PowerShell]。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-163">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="3dfaf-164">取得特定群組的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-164">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="3dfaf-165">取得指定群組的成員。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-165">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="3dfaf-166">將 FirstlineWorker 應用程式設定原則指派給群組的所有使用者成員。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-166">Assign the FirstlineWorker app setup policy to all user members of the group.</span></span>
```PowerShell
$members | ForEach-Object {Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="3dfaf-167">根據群組中的成員數目而定，此命令可能需要幾分鐘的時間執行。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-167">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="search-the-audit-log-for-shifts-events"></a><span data-ttu-id="3dfaf-168">搜尋審核記錄，以取得倒班事件</span><span class="sxs-lookup"><span data-stu-id="3dfaf-168">Search the audit log for Shifts events</span></span>

<span data-ttu-id="3dfaf-169">**(預覽)**</span><span class="sxs-lookup"><span data-stu-id="3dfaf-169">**(in preview)**</span></span>

<span data-ttu-id="3dfaf-170">您可以搜尋 [審核記錄]，在您的組織中查看倒班活動。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-170">You can search the audit log to view Shifts activity in your organization.</span></span>  <span data-ttu-id="3dfaf-171">若要深入瞭解如何搜尋審核記錄，以及查看已記錄在審核記錄中的[倒班活動](../../audit-log-events.md#shifts-in-teams-activities)清單，請參閱[搜尋小組中事件的審核記錄](../../audit-log-events.md)。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-171">To learn more about how to search the audit log and to see a list of [Shifts activities](../../audit-log-events.md#shifts-in-teams-activities) that are logged in the audit log, see [Search the audit log for events in Teams](../../audit-log-events.md).</span></span>

<span data-ttu-id="3dfaf-172">在您可以搜尋審核記錄之前，您必須先在[安全性 & 合規性中心](https://protection.office.com)開啟審核。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-172">Before you can search the audit log, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="3dfaf-173">若要深入瞭解，請參閱[開啟或關閉審核記錄搜尋](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-173">To learn more, see [Turn audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span> <span data-ttu-id="3dfaf-174">請記住，審核資料只能從您開啟審核的位置取得。</span><span class="sxs-lookup"><span data-stu-id="3dfaf-174">Keep in mind that audit data is only available from the point at which you turned on auditing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3dfaf-175">相關主題</span><span class="sxs-lookup"><span data-stu-id="3dfaf-175">Related topics</span></span>

- [<span data-ttu-id="3dfaf-176">倒班第一線員工工作者的協助</span><span class="sxs-lookup"><span data-stu-id="3dfaf-176">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [<span data-ttu-id="3dfaf-177">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="3dfaf-177">Assign policies to your users in Teams</span></span>](../../assign-policies.md)
