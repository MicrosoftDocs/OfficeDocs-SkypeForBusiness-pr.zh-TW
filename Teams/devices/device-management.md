---
title: 在 Microsoft 團隊中管理您的裝置
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: 瞭解如何管理與組織中的小組搭配使用的裝置。
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ac6c0b503266a83033a72940ea6572feeaffaf5
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2020
ms.locfileid: "47964805"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="322fe-103">在 Microsoft 團隊中管理您的裝置</span><span class="sxs-lookup"><span data-stu-id="322fe-103">Manage your devices in Microsoft Teams</span></span>

<span data-ttu-id="322fe-104">您可以從 Microsoft 團隊系統管理中心管理組織中 Microsoft 團隊使用的裝置。</span><span class="sxs-lookup"><span data-stu-id="322fe-104">You can manage devices used with Microsoft Teams in your organization from the Microsoft Teams admin center.</span></span> <span data-ttu-id="322fe-105">您可以查看及管理貴組織的裝置庫存，以及執行更新、重新開機及監視裝置診斷的工作。</span><span class="sxs-lookup"><span data-stu-id="322fe-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="322fe-106">您也可以建立設定檔並將其指派給裝置或裝置群組。</span><span class="sxs-lookup"><span data-stu-id="322fe-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span>

<span data-ttu-id="322fe-107">若要管理裝置，例如變更裝置設定、重新開機裝置、管理更新，或查看裝置和外設健康情況，您必須指派下列其中一個 Microsoft 365 管理員角色：</span><span class="sxs-lookup"><span data-stu-id="322fe-107">To manage devices, such as changing device configuration, restarting devices, managing updates, or viewing device and peripheral health, you need to be assigned one of the following Microsoft 365 admin roles:</span></span>

- <span data-ttu-id="322fe-108">Microsoft 365 全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="322fe-108">Microsoft 365 Global admin</span></span>
- <span data-ttu-id="322fe-109">團隊服務管理員</span><span class="sxs-lookup"><span data-stu-id="322fe-109">Teams Service admin</span></span>
- <span data-ttu-id="322fe-110">團隊裝置管理員</span><span class="sxs-lookup"><span data-stu-id="322fe-110">Teams Device admin</span></span>

<span data-ttu-id="322fe-111">如需有關團隊中系統管理員角色的詳細資訊，請參閱 [使用 Microsoft 團隊管理員角色管理團隊](../using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="322fe-111">For more information about admin roles in Teams, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="322fe-112">您可以管理哪些裝置？</span><span class="sxs-lookup"><span data-stu-id="322fe-112">What devices can you manage?</span></span>

<span data-ttu-id="322fe-113">您可以管理任何已認證的裝置，以及已註冊的小組。</span><span class="sxs-lookup"><span data-stu-id="322fe-113">You can manage any device that's certified for, and enrolled in, Teams.</span></span> <span data-ttu-id="322fe-114">在使用者第一次登入裝置上的小組時，裝置會自動註冊。</span><span class="sxs-lookup"><span data-stu-id="322fe-114">A device is automatically enrolled the first time a user signs into Teams on the device.</span></span> <span data-ttu-id="322fe-115">如需可管理的認證裝置清單，請參閱：</span><span class="sxs-lookup"><span data-stu-id="322fe-115">For a list of certified devices that can be managed, see:</span></span>

- [<span data-ttu-id="322fe-116">Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="322fe-116">Microsoft Teams Rooms</span></span>](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=20)
- [<span data-ttu-id="322fe-117">電話會議</span><span class="sxs-lookup"><span data-stu-id="322fe-117">Conference phones</span></span>](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73)
- [<span data-ttu-id="322fe-118">手機</span><span class="sxs-lookup"><span data-stu-id="322fe-118">Desk phones</span></span>](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- [<span data-ttu-id="322fe-119">共同作業條</span><span class="sxs-lookup"><span data-stu-id="322fe-119">Collaboration bars</span></span>](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices/devices/category?devicetype=16)

<span data-ttu-id="322fe-120">這些裝置是在 [Microsoft 團隊系統管理中心](https://admin.teams.microsoft.com) 管理，並在左側導覽中的 [ **裝置**] 底下擁有各自的區段。</span><span class="sxs-lookup"><span data-stu-id="322fe-120">These devices are managed the in the [Microsoft Teams admin center](https://admin.teams.microsoft.com) and have their own respective sections in the left navigation under **Devices**.</span></span> <span data-ttu-id="322fe-121">這可讓您分別管理每個類型的裝置。</span><span class="sxs-lookup"><span data-stu-id="322fe-121">This lets you manage each type of device separately.</span></span>

## <a name="manage-teams-rooms-devices"></a><span data-ttu-id="322fe-122">管理團隊聊天室裝置</span><span class="sxs-lookup"><span data-stu-id="322fe-122">Manage Teams Rooms devices</span></span>

<span data-ttu-id="322fe-123">您可以使用 [團隊系統管理中心]，在整個組織中查看和遠端系統管理團隊間的裝置。</span><span class="sxs-lookup"><span data-stu-id="322fe-123">You can use the Teams admin center to view and remotely manage your Teams Rooms devices across your organization.</span></span> <span data-ttu-id="322fe-124">[團隊系統管理中心] 可讓您輕鬆查看哪些裝置正常運作且需要注意，並讓您專注于特定裝置上，以查看裝置健康情況、會議效能、通話品質以及週邊設備的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="322fe-124">The Teams admin center makes it easy to see, at a glance, which devices are healthy and which need attention, and lets you focus on specific devices to see detailed information about device health, meeting performance, call quality, and peripherals.</span></span> 

<span data-ttu-id="322fe-125">以下是您可以用來管理團隊聊天室裝置的一些事項。</span><span class="sxs-lookup"><span data-stu-id="322fe-125">Here are some things you can do to manage your Teams Rooms devices.</span></span> <span data-ttu-id="322fe-126">您可以在 [**裝置**團隊聊天室] 底下的 [ [Microsoft 團隊系統管理中心](https://admin.teams.microsoft.com)] 中找到 [團隊聊天室] 裝置  >  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="322fe-126">Teams Rooms devices can be found in the [Microsoft Teams admin center](https://admin.teams.microsoft.com) under **Devices** > **Teams Rooms**.</span></span>

<span data-ttu-id="322fe-127">如需有關如何管理團隊聊天室裝置的詳細資訊，請參閱 [管理 Microsoft 團隊聊天室](../rooms/rooms-manage.md)。</span><span class="sxs-lookup"><span data-stu-id="322fe-127">For details about how to manage your Teams Rooms devices, see [Manage Microsoft Teams Rooms](../rooms/rooms-manage.md).</span></span>

| <span data-ttu-id="322fe-128">若要執行此動作 .。。</span><span class="sxs-lookup"><span data-stu-id="322fe-128">To do this...</span></span> | <span data-ttu-id="322fe-129">請這麼做</span><span class="sxs-lookup"><span data-stu-id="322fe-129">Do this</span></span>|
|---------------|--------|
| <span data-ttu-id="322fe-130">變更一或多個裝置上的設定</span><span class="sxs-lookup"><span data-stu-id="322fe-130">Change settings on one or more devices</span></span> | <span data-ttu-id="322fe-131">選取一或多個裝置 > **編輯設定**]。</span><span class="sxs-lookup"><span data-stu-id="322fe-131">Select one or more devices > **Edit settings**.</span></span> <span data-ttu-id="322fe-132">如果您選取多個裝置，您所變更的值將會取代所有選取的裝置上的值。</span><span class="sxs-lookup"><span data-stu-id="322fe-132">If you select multiple devices, the values you change will replace the values on all the selected devices.</span></span> |
| <span data-ttu-id="322fe-133">重新開機裝置</span><span class="sxs-lookup"><span data-stu-id="322fe-133">Restart devices</span></span> | <span data-ttu-id="322fe-134">選取一或多個裝置，> **重新開機**]。</span><span class="sxs-lookup"><span data-stu-id="322fe-134">Select one or more devices > **Restart**.</span></span> <span data-ttu-id="322fe-135">當您重新開機裝置時，您可以選擇是否要立即重新開機裝置，或選取 [ **排程重新開機** ]，在特定的日期和時間重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="322fe-135">When you restart a device, you can choose whether to restart the device immediately or select **Schedule restart** to restart the device at a specific date and time.</span></span> <span data-ttu-id="322fe-136">您選取的日期和時間是您在裝置重新開機的地方。</span><span class="sxs-lookup"><span data-stu-id="322fe-136">The date and time you select are local to the device being restarted.</span></span>|
| <span data-ttu-id="322fe-137">查看會議活動</span><span class="sxs-lookup"><span data-stu-id="322fe-137">View meeting activity</span></span> | <span data-ttu-id="322fe-138">選取裝置名稱，以開啟 [裝置詳細資料] > **活動**。</span><span class="sxs-lookup"><span data-stu-id="322fe-138">Select a device name to open device details > **Activity**.</span></span> <span data-ttu-id="322fe-139">當您開啟 [ **活動** ] 索引標籤時，您可以看到該裝置參與的所有會議。</span><span class="sxs-lookup"><span data-stu-id="322fe-139">When you open the **Activity** tab, you can see all the meetings that the device has participated in.</span></span> <span data-ttu-id="322fe-140">這個摘要視圖會顯示會議的開始時間、參與者的人數、其持續時間和整體通話品質。</span><span class="sxs-lookup"><span data-stu-id="322fe-140">This summary view shows the meeting start time, the number of participants, its duration, and the overall call quality.</span></span>|
| <span data-ttu-id="322fe-141">查看會議詳細資料</span><span class="sxs-lookup"><span data-stu-id="322fe-141">View meeting details</span></span> |  <span data-ttu-id="322fe-142">選取裝置名稱，以開啟 [裝置詳細資料] > **活動** > 選取會議。</span><span class="sxs-lookup"><span data-stu-id="322fe-142">Select a device name to open device details > **Activity** > select a meeting.</span></span> <span data-ttu-id="322fe-143">當您開啟會議的詳細資料時，您可以看到會議中的所有參與者、通話時長、團隊會議類型，以及個人通話品質。</span><span class="sxs-lookup"><span data-stu-id="322fe-143">When you open a meeting's details, you can see all of the participants in the meeting, how long they were in the call, the Teams session types, and their individual call quality.</span></span> <span data-ttu-id="322fe-144">如果您想要查看參與者通話的相關技術資訊，請選取參與者的通話開始時間。</span><span class="sxs-lookup"><span data-stu-id="322fe-144">If you want to see technical information about a participant's call, select the participant's call start time.</span></span>|

## <a name="manage-phones-and-collaboration-bars-in-teams"></a><span data-ttu-id="322fe-145">管理團隊中的手機與共同作業橫條圖</span><span class="sxs-lookup"><span data-stu-id="322fe-145">Manage phones and collaboration bars in Teams</span></span>

<span data-ttu-id="322fe-146">在團隊系統管理中心中，您可以查看及管理您組織中的小組登記的手機和共同作業列。</span><span class="sxs-lookup"><span data-stu-id="322fe-146">In the Teams admin center, you can view and manage phones and collaboration bars enrolled in Teams in your organization.</span></span> <span data-ttu-id="322fe-147">您會在每個裝置上看到的資訊包括裝置名稱、製造商、型號、使用者、狀態、動作、上次查看，以及歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="322fe-147">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="322fe-148">您可以自訂 [視圖]，以顯示符合您需求的資訊。</span><span class="sxs-lookup"><span data-stu-id="322fe-148">You can customize the view to show the information that fits your needs.</span></span>

<span data-ttu-id="322fe-149">如果您已註冊手機和共同作業列，就會自動在 Microsoft Intune 中註冊。</span><span class="sxs-lookup"><span data-stu-id="322fe-149">Phones and collaboration bars are automatically enrolled in Microsoft Intune, if you've signed up for it.</span></span> <span data-ttu-id="322fe-150">裝置註冊之後，系統會確認裝置合規性，並將條件式存取原則套用到裝置上。</span><span class="sxs-lookup"><span data-stu-id="322fe-150">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span>

<span data-ttu-id="322fe-151">以下是如何管理組織中的手機與共同作業條的一些範例。</span><span class="sxs-lookup"><span data-stu-id="322fe-151">Here are some examples of how you can manage phones and collaboration bars in your organization.</span></span>  

|<span data-ttu-id="322fe-152">若要執行此動作 .。。</span><span class="sxs-lookup"><span data-stu-id="322fe-152">To do this...</span></span>  |<span data-ttu-id="322fe-153">請這麼做</span><span class="sxs-lookup"><span data-stu-id="322fe-153">Do this</span></span> |
|---------|---------|
| <span data-ttu-id="322fe-154">變更裝置資訊</span><span class="sxs-lookup"><span data-stu-id="322fe-154">Change device information</span></span>               | <span data-ttu-id="322fe-155">選取 > **編輯**的裝置。</span><span class="sxs-lookup"><span data-stu-id="322fe-155">Select a device > **Edit**.</span></span> <span data-ttu-id="322fe-156">您可以編輯裝置名稱、資產標記及新增筆記等詳細資料。</span><span class="sxs-lookup"><span data-stu-id="322fe-156">You can edit details such as device name, asset tag, and add notes.</span></span>     |
| <span data-ttu-id="322fe-157">管理軟體更新</span><span class="sxs-lookup"><span data-stu-id="322fe-157">Manage software updates</span></span>                 | <span data-ttu-id="322fe-158">選取 > **更新**的裝置。</span><span class="sxs-lookup"><span data-stu-id="322fe-158">Select a device > **Update**.</span></span> <span data-ttu-id="322fe-159">您可以查看裝置可用的軟體和固件更新清單，並選擇要安裝的更新。</span><span class="sxs-lookup"><span data-stu-id="322fe-159">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span> <span data-ttu-id="322fe-160">如需更新裝置的詳細資訊，請參閱 [遠端更新 Microsoft 團隊裝置](remote-update.md)</span><span class="sxs-lookup"><span data-stu-id="322fe-160">For more information about updating devices, see [Update Microsoft Teams devices remotely](remote-update.md)</span></span>   |
| <span data-ttu-id="322fe-161">指派或變更配置原則</span><span class="sxs-lookup"><span data-stu-id="322fe-161">Assign or change configuration policies</span></span> | <span data-ttu-id="322fe-162">選取一或多個裝置 > **指派**設定]。</span><span class="sxs-lookup"><span data-stu-id="322fe-162">Select one or more devices > **Assign configuration**.</span></span>                                                                                                                                                                                                                   |
| <span data-ttu-id="322fe-163">新增或移除裝置標記</span><span class="sxs-lookup"><span data-stu-id="322fe-163">Add or remove device tags</span></span>               | <span data-ttu-id="322fe-164">選取一或多個 > **管理標記**的裝置。</span><span class="sxs-lookup"><span data-stu-id="322fe-164">Select one or more devices > **Manage tags**.</span></span> <span data-ttu-id="322fe-165">如需裝置標籤的詳細資訊，請參閱 [管理和篩選 Microsoft 團隊裝置](manage-device-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="322fe-165">For more information about device tags, see [Manage Manage and filter Microsoft Teams device](manage-device-tags.md).</span></span>                                                                                                      |
| <span data-ttu-id="322fe-166">重新開機裝置</span><span class="sxs-lookup"><span data-stu-id="322fe-166">Restart devices</span></span>                         | <span data-ttu-id="322fe-167">選取一或多個裝置，> **重新開機**]。</span><span class="sxs-lookup"><span data-stu-id="322fe-167">Select one or more devices > **Restart**.</span></span>                                                                                                                                                                                                                                |
| <span data-ttu-id="322fe-168">使用裝置標記篩選裝置</span><span class="sxs-lookup"><span data-stu-id="322fe-168">Filter devices using device tags</span></span>        | <span data-ttu-id="322fe-169">選取 [篩選] 圖示、選取 [標籤 **] 欄位、** 指定要篩選的裝置標記，然後選取 [套用 **]。**</span><span class="sxs-lookup"><span data-stu-id="322fe-169">Select the filter icon, select the **Tag** field, specify a device tag to filter on, and select **Apply**.</span></span> <span data-ttu-id="322fe-170">如需使用裝置標籤篩選裝置的詳細資訊，請參閱 [使用篩選來傳回具有特定](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag)標籤的裝置。</span><span class="sxs-lookup"><span data-stu-id="322fe-170">For more information about filtering devices using device tags, see [Use filters to return devices with a specific tag](manage-device-tags.md#use-filters-to-return-devices-with-a-specific-tag).</span></span>|
| <span data-ttu-id="322fe-171">查看裝置歷程記錄</span><span class="sxs-lookup"><span data-stu-id="322fe-171">View device history</span></span>                     | <span data-ttu-id="322fe-172">選取裝置 > 歷程 **記錄**]。</span><span class="sxs-lookup"><span data-stu-id="322fe-172">Select a device > **History**.</span></span> <span data-ttu-id="322fe-173">您可以查看裝置的更新歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="322fe-173">You can view the update history for the device.</span></span>                                                                                                                                                                                |
| <span data-ttu-id="322fe-174">[查看] 診斷</span><span class="sxs-lookup"><span data-stu-id="322fe-174">View diagnostics</span></span>                        | <span data-ttu-id="322fe-175">選取 > **診斷**的裝置。</span><span class="sxs-lookup"><span data-stu-id="322fe-175">Select a device > **Diagnostics**.</span></span>                                                                                                                                                                                                                            |


### <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="322fe-176">在團隊中使用設定檔</span><span class="sxs-lookup"><span data-stu-id="322fe-176">Use configuration profiles in Teams</span></span>

<span data-ttu-id="322fe-177">使用設定檔來管理貴組織中的小組電話與共同作業橫條圖的設定和功能。</span><span class="sxs-lookup"><span data-stu-id="322fe-177">Use configuration profiles to manage settings and features for Teams phones and collaboration bars in your organization.</span></span> <span data-ttu-id="322fe-178">您可以建立或上傳設定檔，以包含您想要啟用或停用的設定和功能，然後將設定檔指派給裝置或裝置群組。</span><span class="sxs-lookup"><span data-stu-id="322fe-178">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

#### <a name="create-a-configuration-profile"></a><span data-ttu-id="322fe-179">建立設定檔</span><span class="sxs-lookup"><span data-stu-id="322fe-179">Create a configuration profile</span></span>

1. <span data-ttu-id="322fe-180">在左側導覽中，移至 [**裝置**  >  **設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="322fe-180">In the left navigation, go to **Devices** > **Configuration profiles**.</span></span>
2. <span data-ttu-id="322fe-181">按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="322fe-181">Click **Add**.</span></span>
3. <span data-ttu-id="322fe-182">輸入設定檔的名稱，並視需要新增易記的描述。</span><span class="sxs-lookup"><span data-stu-id="322fe-182">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="322fe-183">為設定檔指定您想要的設定，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="322fe-183">Specify the settings you want for the profile, and then click **Save**.</span></span>

#### <a name="assign-a-configuration-profile"></a><span data-ttu-id="322fe-184">指派設定檔</span><span class="sxs-lookup"><span data-stu-id="322fe-184">Assign a configuration profile</span></span>

1. <span data-ttu-id="322fe-185">在左側導覽中，移至 [**裝置**  >  **設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="322fe-185">In the left navigation, go to **Devices** > **Configuration profiles**.</span></span>
2. <span data-ttu-id="322fe-186">選取您要指派的 **設定檔** ，然後按一下 [ **指派給裝置**]。</span><span class="sxs-lookup"><span data-stu-id="322fe-186">Select the **Configuration profile** you want to assign, and then click **Assign to device**.</span></span>  
3. <span data-ttu-id="322fe-187">在 [ **將裝置指派給** 設定設定檔] 窗格中，搜尋並選取您要指派的裝置。</span><span class="sxs-lookup"><span data-stu-id="322fe-187">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="322fe-188">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="322fe-188">Click **Save**.</span></span>

