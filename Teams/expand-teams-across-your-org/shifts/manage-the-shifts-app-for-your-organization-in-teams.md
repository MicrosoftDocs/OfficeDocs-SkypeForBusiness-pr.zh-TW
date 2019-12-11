---
title: 在 Microsoft 團隊中為您的組織管理倒班應用程式
author: kenwith
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何針對貴組織中的第一線員工工作人員，在小組中設定和管理倒班 app。
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6bd65376be278a3d07e5a7a8c4ba69ccd5408090
ms.sourcegitcommit: a23f45ab3a2cb7b5c279356edddf61c4030c41bd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2019
ms.locfileid: "39961608"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="e8cb4-103">在 Microsoft 團隊中為您的組織管理倒班應用程式</span><span class="sxs-lookup"><span data-stu-id="e8cb4-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e8cb4-104">2019年12月31日生效，Microsoft StaffHub 將停用。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="e8cb4-105">我們正在將 StaffHub 功能組建至 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="e8cb4-106">今天，小組包含針對排程管理的倒班應用程式，而其他功能則會隨著時間推移而推出。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="e8cb4-107">StaffHub 將會停止針對2019年12月31日的所有使用者使用。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="e8cb4-108">任何試圖開啟 StaffHub 的人，都會顯示一則訊息，讓他們下載小組。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="e8cb4-109">若要深入瞭解，請參閱[Microsoft StaffHub 停用](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="e8cb4-110">班次的概覽</span><span class="sxs-lookup"><span data-stu-id="e8cb4-110">Overview of Shifts</span></span>
<span data-ttu-id="e8cb4-111">Microsoft 團隊中的 [倒班] 應用程式會讓第一線員工工作人員保持連線並同步處理。它會先建立行動裝置，以快速且有效地管理和溝通小組的時間。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="e8cb4-112">[倒班] 讓第一線員工工作者及其主管使用行動裝置管理排程，並保持聯繫。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span> 

- <span data-ttu-id="e8cb4-113">管理員建立、更新及管理團隊的倒班排程。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="e8cb4-114">他們可以將訊息傳送給一個人（「在地面有溢出）」或整個小組（「地區 GM 已在20分鐘內抵達」）。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="e8cb4-115">他們也可以傳送原則檔、新聞佈告及影片。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="e8cb4-116">員工要查看他們的後續班次，可以查看當天排程的人員、要求交換或提供倒班，以及要求下班時間。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="e8cb4-117">我們必須知道，倒班目前不支援來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="e8cb4-118">這表示當您在小組中開啟來賓存取功能時，小組中的來賓不能加入或使用倒班排程。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="e8cb4-119">倒班的可用性</span><span class="sxs-lookup"><span data-stu-id="e8cb4-119">Availability of Shifts</span></span>

<span data-ttu-id="e8cb4-120">在可使用團隊的所有企業 Sku 中，都提供倒班。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-120">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="e8cb4-121">倒班資料的位置</span><span class="sxs-lookup"><span data-stu-id="e8cb4-121">Location of Shifts data</span></span>

<span data-ttu-id="e8cb4-122">倒班資料目前儲存在北美、西歐及亞太地區資料中心的 Azure 中。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-122">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="e8cb4-123">如需有關資料儲存位置的詳細資訊，請參閱[我的資料在哪裡](http://o365datacentermap.azurewebsites.net/)？</span><span class="sxs-lookup"><span data-stu-id="e8cb4-123">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="e8cb4-124">設定倒班</span><span class="sxs-lookup"><span data-stu-id="e8cb4-124">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="e8cb4-125">在組織中啟用或停用倒班</span><span class="sxs-lookup"><span data-stu-id="e8cb4-125">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="e8cb4-126">預設會針對貴組織中的所有團隊使用者啟用班次。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-126">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="e8cb4-127">您可以在 Microsoft 團隊系統管理中心的 app 許可權原則中使用全組織性設定，來關閉或開啟應用程式的整個組織結構。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-127">You can turn off or turn on the app org-wide by using org-wide settings in app permission policies in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="e8cb4-128">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊 app** > ]**許可權原則**。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-128">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies** .</span></span>
2. <span data-ttu-id="e8cb4-129">按一下 [**整個組織的設定**]。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-129">Click **Org-wide settings**.</span></span>
3. <span data-ttu-id="e8cb4-130">在**組織範圍**的 [設定] 面板中，在 [**封鎖的 app**] 底下，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="e8cb4-130">In the **Org-wide settings** panel, under **Blocked apps**, do one of the following:</span></span>

    - <span data-ttu-id="e8cb4-131">若要關閉貴組織的倒班，請搜尋 [倒班] 應用程式，然後按一下 [**新增**]，將其新增到 [封鎖的應用程式] 清單。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-131">To turn off Shifts for your organization, search for the Shifts app, and click **Add** to add it to the blocked apps list.</span></span>
    - <span data-ttu-id="e8cb4-132">若要為您的組織開啟倒班，請從 [封鎖的 app] 清單中移除 [倒班] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-132">To turn on Shifts for your organization, remove the Shifts app from the blocked apps list.</span></span>
4. <span data-ttu-id="e8cb4-133">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-133">Click **Save**.</span></span> 

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="e8cb4-134">針對貴組織中的特定使用者啟用或停用班次</span><span class="sxs-lookup"><span data-stu-id="e8cb4-134">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="e8cb4-135">若要允許或封鎖貴組織中的特定使用者使用倒班，請確定您的組織已在組織內設定中開啟了 [倒班]，然後建立自訂應用程式許可權原則，並將其指派給那些使用者。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-135">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization in org-wide settings, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="e8cb4-136">若要深入瞭解，請參閱[在團隊中管理 app 許可權原則](../../teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-136">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="e8cb4-137">使用 FirstlineWorker 應用程式設定原則釘選到團隊</span><span class="sxs-lookup"><span data-stu-id="e8cb4-137">Use the FirstlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="e8cb4-138">App 設定原則可讓您自訂小組，以醒目提示貴組織中的使用者最重要的 app。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-138">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="e8cb4-139">原則中設定的應用程式會釘選到應用程式&mdash;行，以及小組行動客戶&mdash;端的右側列，使用者可以快速且輕鬆地存取。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-139">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="e8cb4-140">團隊包含內建的 FirstlineWorker 應用程式設定原則，您可以將它指派給貴組織中的第一線員工工作人員。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-140">Teams includes a built-in FirstlineWorker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="e8cb4-141">根據預設，原則包含活動、班次、聊天及呼叫 app。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-141">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="e8cb4-142">若要查看 FirstlineWorker 原則，請在 Microsoft 團隊系統管理中心的左導覽中，移至 [**小組 app** > **應用程式] 設定原則**。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-142">To view the FirstlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="e8cb4-143">![FirstlineWorker 應用程式設定原則的螢幕擷取畫面](../../media/firstline-worker-app-setup-policy.png "Microsoft 團隊系統管理中心的 FirstlineWorker 應用程式設定原則的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="e8cb4-143">![Screenshot of the FirstlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FirstlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a><span data-ttu-id="e8cb4-144">將 FirstlineWorker 原則指派給個別使用者</span><span class="sxs-lookup"><span data-stu-id="e8cb4-144">Assign the FirstlineWorker policy to individual users</span></span>

1. <span data-ttu-id="e8cb4-145">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**使用者**]，然後按一下使用者。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-145">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="e8cb4-146">在 [**指派的原則**] 旁，選擇 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-146">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="e8cb4-147">在 [**團隊 App 設定原則**] 底下，選取 [ **FirstlineWorker**]，然後選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-147">Under **Teams App Setup policy**, select **FirstlineWorker**, and then choose **Save**.</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="e8cb4-148">將 FirstlineWorker 應用程式設定原則指派給群組中的使用者</span><span class="sxs-lookup"><span data-stu-id="e8cb4-148">Assign the FirstlineWorker app setup policy to users in a group</span></span>

<span data-ttu-id="e8cb4-149">您可以將 FirstlineWorker 應用程式設定原則指派給群組中的使用者（例如安全性群組），方法是連線到 Azure Active Directory PowerShell for Graph 模組及商務用 Skype PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-149">You can assign the FirstlineWorker app setup policy to users in a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="e8cb4-150">如需有關使用 PowerShell 來管理團隊的詳細資訊，請參閱[團隊 PowerShell 概覽](../../teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-150">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](../../teams-powershell-overview.md).</span></span>

<span data-ttu-id="e8cb4-151">在這個範例中，我們會將 FirstlineWorker 應用程式設定原則指派給 Contoso 第一線員工小組群組中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-151">In this example, we assign the FirstlineWorker app setup policy to all users in the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="e8cb4-152">請依照在[單一 Windows PowerShell 視窗中連線至 [所有 Office 365 服務]](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步驟，確認您首先連線至 [圖形模組] 和 [商務用 Skype] powershell 模組的 [Azure Active Directory PowerShell]。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-152">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="e8cb4-153">取得特定群組的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-153">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="e8cb4-154">取得指定群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-154">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="e8cb4-155">將群組中的所有使用者指派至 FirstlineWorker 應用程式設定原則。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-155">Assign all users in the group to the FirstlineWorker app setup policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="e8cb4-156">根據群組中的成員數目而定，此命令可能需要幾分鐘的時間執行。</span><span class="sxs-lookup"><span data-stu-id="e8cb4-156">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e8cb4-157">相關主題</span><span class="sxs-lookup"><span data-stu-id="e8cb4-157">Related topics</span></span>
- [<span data-ttu-id="e8cb4-158">倒班第一線員工工作者的協助</span><span class="sxs-lookup"><span data-stu-id="e8cb4-158">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
