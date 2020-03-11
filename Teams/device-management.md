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
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef6412ff40d71a21f619b08ee5e334819d5470ca
ms.sourcegitcommit: a597b1572f1eca095144288446a2c038e5daa5f7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2020
ms.locfileid: "42587312"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="08140-103">在 Microsoft 團隊中管理您的裝置</span><span class="sxs-lookup"><span data-stu-id="08140-103">Manage your devices in Microsoft Teams</span></span>

<span data-ttu-id="08140-104">做為管理員，您可以從 Microsoft 團隊系統管理中心管理與組織中的小組搭配使用的裝置。</span><span class="sxs-lookup"><span data-stu-id="08140-104">As an admin, you can manage devices used with Teams in your organization from the Microsoft Teams admin center.</span></span> <span data-ttu-id="08140-105">您可以查看及管理貴組織的裝置庫存，以及執行更新、重新開機及監視裝置診斷的工作。</span><span class="sxs-lookup"><span data-stu-id="08140-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="08140-106">您也可以建立設定檔並將其指派給裝置或裝置群組。</span><span class="sxs-lookup"><span data-stu-id="08140-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="08140-107">您可以管理哪些裝置？</span><span class="sxs-lookup"><span data-stu-id="08140-107">What devices can you manage?</span></span>
<span data-ttu-id="08140-108">您可以管理任何已認證的裝置，以及已註冊的小組。</span><span class="sxs-lookup"><span data-stu-id="08140-108">You can manage any device that's certified for, and enrolled in, Teams.</span></span> <span data-ttu-id="08140-109">在使用者第一次登入裝置上的小組時，裝置會自動註冊。</span><span class="sxs-lookup"><span data-stu-id="08140-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> <span data-ttu-id="08140-110">如需可管理的認證裝置清單，請參閱：</span><span class="sxs-lookup"><span data-stu-id="08140-110">For a list of certified devices that can be managed, see:</span></span>

- [<span data-ttu-id="08140-111">電話會議</span><span class="sxs-lookup"><span data-stu-id="08140-111">Conference phones</span></span>](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=16)
- [<span data-ttu-id="08140-112">手機</span><span class="sxs-lookup"><span data-stu-id="08140-112">Desk phones</span></span>](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- <span data-ttu-id="08140-113">共同作業條</span><span class="sxs-lookup"><span data-stu-id="08140-113">Collaboration bars</span></span>

<span data-ttu-id="08140-114">裝置會在左側導覽中的 [**裝置**] 底下的 [ [Microsoft 團隊系統管理中心](https://admin.teams.microsoft.com)] 進行管理。</span><span class="sxs-lookup"><span data-stu-id="08140-114">Devices are managed in the [Microsoft Teams admin center](https://admin.teams.microsoft.com) under **Devices** in the left navigation.</span></span>

> [!NOTE]
> <span data-ttu-id="08140-115">如果您有 Microsoft Intune，裝置會自動在 Intune 中註冊。</span><span class="sxs-lookup"><span data-stu-id="08140-115">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="08140-116">裝置註冊之後，系統會確認裝置合規性，並將條件式存取原則套用到裝置上。</span><span class="sxs-lookup"><span data-stu-id="08140-116">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span>

## <a name="manage-phones-and-collaboration-bars-in-teams"></a><span data-ttu-id="08140-117">管理團隊中的手機與共同作業橫條圖</span><span class="sxs-lookup"><span data-stu-id="08140-117">Manage phones and collaboration bars in Teams</span></span>

<span data-ttu-id="08140-118">即使手機和共同作業橫條圖在 Microsoft [團隊管理中心] 中的管理方式相同，他們在左側導覽中的 [**裝置**] 底下都有各自的區段。</span><span class="sxs-lookup"><span data-stu-id="08140-118">Even though phones and collaboration bars are managed the same in the Microsoft Teams admin center, they have their own respective sections in the left navigation under **Devices**.</span></span> <span data-ttu-id="08140-119">這可讓您分別管理每個類型的裝置。</span><span class="sxs-lookup"><span data-stu-id="08140-119">This lets you manage each type of device separately.</span></span>

<span data-ttu-id="08140-120">您可以從這裡，查看及管理您組織中的小組登記的電話和共同作業列。</span><span class="sxs-lookup"><span data-stu-id="08140-120">From here, you can view and manage phones and collaboration bars enrolled in Teams in your organization.</span></span> <span data-ttu-id="08140-121">您會在每個裝置上看到的資訊包括裝置名稱、製造商、型號、使用者、狀態、動作、上次查看，以及歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="08140-121">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="08140-122">您可以自訂 [視圖]，以顯示符合您需求的資訊。</span><span class="sxs-lookup"><span data-stu-id="08140-122">You can customize the view to show the information that fits your needs.</span></span>

<span data-ttu-id="08140-123">以下是如何管理組織中的小組裝置的一些範例。</span><span class="sxs-lookup"><span data-stu-id="08140-123">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="08140-124">若要執行此動作 .。。</span><span class="sxs-lookup"><span data-stu-id="08140-124">To do this...</span></span>  |<span data-ttu-id="08140-125">執行此動作</span><span class="sxs-lookup"><span data-stu-id="08140-125">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="08140-126">變更裝置資訊</span><span class="sxs-lookup"><span data-stu-id="08140-126">Change device information</span></span>   | <span data-ttu-id="08140-127">選取 >**編輯**的裝置。</span><span class="sxs-lookup"><span data-stu-id="08140-127">Select a device > **Edit**.</span></span> <span data-ttu-id="08140-128">您可以編輯裝置名稱、資產標記及新增筆記等詳細資料。</span><span class="sxs-lookup"><span data-stu-id="08140-128">You can edit details such as device name, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="08140-129">管理軟體更新</span><span class="sxs-lookup"><span data-stu-id="08140-129">Manage software updates</span></span>   |<span data-ttu-id="08140-130">選取 >**更新**的裝置。</span><span class="sxs-lookup"><span data-stu-id="08140-130">Select a device > **Update**.</span></span> <span data-ttu-id="08140-131">您可以查看裝置可用的軟體和固件更新清單，並選擇要安裝的更新。</span><span class="sxs-lookup"><span data-stu-id="08140-131">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="08140-132">重新開機裝置</span><span class="sxs-lookup"><span data-stu-id="08140-132">Restart a device</span></span>   |<span data-ttu-id="08140-133">選取 >**重新開機**的裝置。</span><span class="sxs-lookup"><span data-stu-id="08140-133">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="08140-134">查看裝置歷程記錄</span><span class="sxs-lookup"><span data-stu-id="08140-134">View device history</span></span>  | <span data-ttu-id="08140-135">選取裝置 > 歷程**記錄**]。</span><span class="sxs-lookup"><span data-stu-id="08140-135">Select a device > **History**.</span></span> <span data-ttu-id="08140-136">您可以查看裝置的更新歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="08140-136">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="08140-137">[查看] 診斷</span><span class="sxs-lookup"><span data-stu-id="08140-137">View diagnostics</span></span>  | <span data-ttu-id="08140-138">選取 >**診斷**的裝置。</span><span class="sxs-lookup"><span data-stu-id="08140-138">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="08140-139">在團隊中使用設定檔</span><span class="sxs-lookup"><span data-stu-id="08140-139">Use configuration profiles in Teams</span></span>

<span data-ttu-id="08140-140">使用設定檔來管理貴組織中的小組裝置設定和功能。</span><span class="sxs-lookup"><span data-stu-id="08140-140">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="08140-141">您可以建立或上傳設定檔，以包含您想要啟用或停用的設定和功能，然後將設定檔指派給裝置或裝置群組。</span><span class="sxs-lookup"><span data-stu-id="08140-141">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="08140-142">建立設定檔</span><span class="sxs-lookup"><span data-stu-id="08140-142">Create a configuration profile</span></span>

1. <span data-ttu-id="08140-143">在左側導覽中，移至 [**裝置** > **設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="08140-143">In the left navigation, go to **Devices** > **Configuration profiles**.</span></span>
2. <span data-ttu-id="08140-144">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="08140-144">Click **Add**.</span></span>
3. <span data-ttu-id="08140-145">輸入設定檔的名稱，並視需要新增易記的描述。</span><span class="sxs-lookup"><span data-stu-id="08140-145">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="08140-146">為設定檔指定您想要的設定，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="08140-146">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="08140-147">指派設定檔</span><span class="sxs-lookup"><span data-stu-id="08140-147">Assign a configuration profile</span></span>

1. <span data-ttu-id="08140-148">在左側導覽中，移至 [**裝置** > **設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="08140-148">In the left navigation, go to **Devices** > **Configuration profiles**.</span></span>
2. <span data-ttu-id="08140-149">選取您要指派的**設定檔**，然後按一下 [**指派給裝置**]。</span><span class="sxs-lookup"><span data-stu-id="08140-149">Select the **Configuration profile** you want to assign, and then click **Assign to device**.</span></span>  
3. <span data-ttu-id="08140-150">在 [**將裝置指派給**設定設定檔] 窗格中，搜尋並選取您要指派的裝置。</span><span class="sxs-lookup"><span data-stu-id="08140-150">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="08140-151">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="08140-151">Click **Save**.</span></span>
