---
title: 在 Microsoft 團隊中管理您的裝置
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1keywords:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: 瞭解如何管理與組織中的小組搭配使用的裝置。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 871a066644aaca3b899d1c7f8b3c3c55f6a516a5
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483822"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="cead5-103">在 Microsoft 團隊中管理您的裝置</span><span class="sxs-lookup"><span data-stu-id="cead5-103">Manage your devices in Microsoft Teams</span></span>

::: zone target="docs"
<span data-ttu-id="cead5-104">做為管理員, 您可以從 Microsoft 團隊 & 商務用 Skype 系統管理中心, 管理與組織中的小組搭配使用的所有裝置。</span><span class="sxs-lookup"><span data-stu-id="cead5-104">As an admin, you manage all devices used with Teams in your organization from the Microsoft Teams & Skype for Business admin center.</span></span> <span data-ttu-id="cead5-105">您可以查看及管理貴組織的裝置庫存, 以及執行更新、重新開機及監視裝置診斷的工作。</span><span class="sxs-lookup"><span data-stu-id="cead5-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="cead5-106">您也可以建立設定檔並將其指派給裝置或裝置群組。</span><span class="sxs-lookup"><span data-stu-id="cead5-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="cead5-107">您可以管理哪些裝置？</span><span class="sxs-lookup"><span data-stu-id="cead5-107">What devices can you manage?</span></span>
<span data-ttu-id="cead5-108">裝置必須經過認證, 才能供小組使用, 並已在小組中註冊。</span><span class="sxs-lookup"><span data-stu-id="cead5-108">Devices must be certified for Teams and enrolled in Teams.</span></span> <span data-ttu-id="cead5-109">在使用者第一次登入裝置上的小組時, 裝置會自動註冊。</span><span class="sxs-lookup"><span data-stu-id="cead5-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> <span data-ttu-id="cead5-110">如需可管理的認證裝置清單, 請參閱[電話會議](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16)與[手機](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34)。</span><span class="sxs-lookup"><span data-stu-id="cead5-110">For a list of certified devices that can be managed, see [Conference phones](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16) and [Desk phones](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34).</span></span>

> [!NOTE]
> <span data-ttu-id="cead5-111">如果您有 Microsoft Intune, 裝置會自動在 Intune 中註冊。</span><span class="sxs-lookup"><span data-stu-id="cead5-111">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="cead5-112">裝置註冊之後, 系統會確認裝置合規性, 並將條件式存取原則套用到裝置上。</span><span class="sxs-lookup"><span data-stu-id="cead5-112">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span> 

## <a name="manage-devices-in-teams"></a><span data-ttu-id="cead5-113">管理團隊中的裝置</span><span class="sxs-lookup"><span data-stu-id="cead5-113">Manage devices in Teams</span></span>

<span data-ttu-id="cead5-114">![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="cead5-114">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="cead5-115">在左側導覽中, 移至 [**裝置** > **管理裝置**]。</span><span class="sxs-lookup"><span data-stu-id="cead5-115">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="cead5-116">選取 [**所有裝置**]。</span><span class="sxs-lookup"><span data-stu-id="cead5-116">Select **All devices**.</span></span>  

::: zone-end

 <span data-ttu-id="cead5-117">您可以從這裡, 查看及管理您組織中所有已註冊團隊的裝置。</span><span class="sxs-lookup"><span data-stu-id="cead5-117">From here, you can view and manage all devices enrolled in Teams in your organization.</span></span> <span data-ttu-id="cead5-118">您會在每個裝置上看到的資訊包括裝置名稱、製造商、型號、使用者、狀態、動作、上次查看, 以及歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="cead5-118">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="cead5-119">您可以自訂 [視圖], 以顯示符合您需求的資訊。</span><span class="sxs-lookup"><span data-stu-id="cead5-119">You can customize the view to show the information that fits your needs.</span></span>

 <span data-ttu-id="cead5-120">以下是如何管理組織中的小組裝置的一些範例。</span><span class="sxs-lookup"><span data-stu-id="cead5-120">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="cead5-121">若要執行此動作 .。。</span><span class="sxs-lookup"><span data-stu-id="cead5-121">To do this...</span></span>  |<span data-ttu-id="cead5-122">執行此動作</span><span class="sxs-lookup"><span data-stu-id="cead5-122">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="cead5-123">變更裝置資訊</span><span class="sxs-lookup"><span data-stu-id="cead5-123">Change device information</span></span>   | <span data-ttu-id="cead5-124">選取 >**編輯**的裝置。</span><span class="sxs-lookup"><span data-stu-id="cead5-124">Select a device > **Edit**.</span></span> <span data-ttu-id="cead5-125">您可以編輯 [裝置名稱]、[使用者資訊]、[資產標記], 以及 [新增記事] 等詳細資料。</span><span class="sxs-lookup"><span data-stu-id="cead5-125">You can edit details such as device name, user information, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="cead5-126">管理軟體更新</span><span class="sxs-lookup"><span data-stu-id="cead5-126">Manage software updates</span></span>   |<span data-ttu-id="cead5-127">選取 >**更新**的裝置。</span><span class="sxs-lookup"><span data-stu-id="cead5-127">Select a device > **Update**.</span></span> <span data-ttu-id="cead5-128">您可以查看裝置可用的軟體和固件更新清單, 並選擇要安裝的更新。</span><span class="sxs-lookup"><span data-stu-id="cead5-128">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="cead5-129">重新開機裝置</span><span class="sxs-lookup"><span data-stu-id="cead5-129">Restart a device</span></span>   |<span data-ttu-id="cead5-130">選取 >**重新開機**的裝置。</span><span class="sxs-lookup"><span data-stu-id="cead5-130">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="cead5-131">查看裝置歷程記錄</span><span class="sxs-lookup"><span data-stu-id="cead5-131">View device history</span></span>  | <span data-ttu-id="cead5-132">選取裝置 > 歷程**記錄**]。</span><span class="sxs-lookup"><span data-stu-id="cead5-132">Select a device > **History**.</span></span> <span data-ttu-id="cead5-133">您可以查看裝置的更新歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="cead5-133">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="cead5-134">[查看] 診斷</span><span class="sxs-lookup"><span data-stu-id="cead5-134">View diagnostics</span></span>  | <span data-ttu-id="cead5-135">選取 >**診斷**的裝置。</span><span class="sxs-lookup"><span data-stu-id="cead5-135">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="cead5-136">在團隊中使用設定檔</span><span class="sxs-lookup"><span data-stu-id="cead5-136">Use configuration profiles in Teams</span></span>

<span data-ttu-id="cead5-137">使用設定檔來管理貴組織中的小組裝置設定和功能。</span><span class="sxs-lookup"><span data-stu-id="cead5-137">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="cead5-138">您可以建立或上傳設定檔, 以包含您想要啟用或停用的設定和功能, 然後將設定檔指派給裝置或裝置群組。</span><span class="sxs-lookup"><span data-stu-id="cead5-138">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="cead5-139">建立設定檔</span><span class="sxs-lookup"><span data-stu-id="cead5-139">Create a configuration profile</span></span>

::: zone target="docs"

![顯示 Microsoft [小組標誌] 的圖示](media/teams-logo-30x30.png) <span data-ttu-id="cead5-141">使用 Microsoft 團隊 & 商務用 Skype 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="cead5-141">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="cead5-142">在左側導覽中, 移至 [**裝置** > **管理裝置**]。</span><span class="sxs-lookup"><span data-stu-id="cead5-142">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>

::: zone-end

2. <span data-ttu-id="cead5-143">選取 [**設定檔**], 然後選取 [**新增設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="cead5-143">Select **Configuration profiles**, and then select **New configuration profile**.</span></span>
3. <span data-ttu-id="cead5-144">輸入設定檔的名稱, 並視需要新增易記的描述。</span><span class="sxs-lookup"><span data-stu-id="cead5-144">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="cead5-145">為設定檔指定您想要的設定, 然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="cead5-145">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="cead5-146">指派設定檔</span><span class="sxs-lookup"><span data-stu-id="cead5-146">Assign a configuration profile</span></span>

::: zone target="docs"

![顯示 Microsoft [小組標誌] 的圖示](media/teams-logo-30x30.png) <span data-ttu-id="cead5-148">使用 Microsoft 團隊 & 商務用 Skype 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="cead5-148">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="cead5-149">在左側導覽中, 移至 [**裝置** > **管理裝置**]。</span><span class="sxs-lookup"><span data-stu-id="cead5-149">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>

::: zone-end

2. <span data-ttu-id="cead5-150">選取 [**設定檔**], 然後在 [**指派給**您要指派的設定檔] 底下, 按一下連結。</span><span class="sxs-lookup"><span data-stu-id="cead5-150">Select **Configuration profile**, and then under **Assigned to** in the profile you want to assign, click the link.</span></span>  
3. <span data-ttu-id="cead5-151">在 [**將裝置指派給**設定設定檔] 窗格中, 搜尋並選取您要指派的裝置。</span><span class="sxs-lookup"><span data-stu-id="cead5-151">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="cead5-152">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="cead5-152">Click **Save**.</span></span>
