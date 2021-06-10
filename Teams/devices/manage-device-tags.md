---
title: 管理及篩選Microsoft Teams標記
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
description: 瞭解如何在裝置上管理及篩選Microsoft Teams標記。
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1a4f8ac718a965834678098a8960347278d13aa3
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874993"
---
# <a name="manage-microsoft-teams-device-tags"></a><span data-ttu-id="b20b4-103">管理Microsoft Teams標記</span><span class="sxs-lookup"><span data-stu-id="b20b4-103">Manage Microsoft Teams device tags</span></span>

<span data-ttu-id="b20b4-104">您Microsoft Teams裝置標記，讓您分組、整理及更輕鬆地管理您部署在貴組織中之裝置。</span><span class="sxs-lookup"><span data-stu-id="b20b4-104">Device tags in Microsoft Teams let you group, organize, and more easily manage the devices you've deployed in your organization.</span></span> <span data-ttu-id="b20b4-105">有了 Microsoft Teams中心，您可以在裝置中新增一或多個標記、使用篩選來查看符合您指定標記的裝置，然後在具有該標記的裝置上執行動作。</span><span class="sxs-lookup"><span data-stu-id="b20b4-105">With the Microsoft Teams admin center, you can add one or more tags to devices, use filters to view devices that match the tag you specify, and then perform actions on the devices that have that tag.</span></span>

<span data-ttu-id="b20b4-106">您可以將裝置標記新增到多個裝置類型。</span><span class="sxs-lookup"><span data-stu-id="b20b4-106">You can add a device tag to more than one device type.</span></span> <span data-ttu-id="b20b4-107">不過，當您在系統管理中心開啟裝置窗格時，只會退回該類型的裝置。</span><span class="sxs-lookup"><span data-stu-id="b20b4-107">However, when you open a device pane in the admin center, only the devices of that type are returned.</span></span> <span data-ttu-id="b20b4-108">例如，您可以將「公司」標記指派給手機和Teams 會議室裝置。</span><span class="sxs-lookup"><span data-stu-id="b20b4-108">For example, you can assign the "Corporate" tag to both phones and Teams Rooms devices.</span></span> <span data-ttu-id="b20b4-109">如果您在裝置電話中搜尋「公司」標記，\*\*\*\*  >  則只會退回電話。</span><span class="sxs-lookup"><span data-stu-id="b20b4-109">If you search for the "Corporate" tag while in **Devices** > **Phones**, only phones are returned.</span></span> <span data-ttu-id="b20b4-110">同樣地，如果您在裝置或裝置中搜尋「公司」Teams 會議室，只會Teams 會議室  >  裝置。</span><span class="sxs-lookup"><span data-stu-id="b20b4-110">Similarly, if you search for the "Corporate" tag in **Devices** > **Teams Rooms**, only Teams Rooms devices are returned.</span></span>

<span data-ttu-id="b20b4-111">若要管理裝置標記，您必須是全域系統管理員、Teams系統管理員，或Teams系統管理員。有關系統管理員角色的資訊，請參閱使用 Microsoft Teams[系統管理員角色來管理Teams。](../using-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="b20b4-111">To manage device tags, you need to be a Global admin, Teams Service admin, or Teams Device admin. For more information about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b20b4-112">裝置標記會指派給登入裝置的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="b20b4-112">Device tags are assigned to the resource account that's logged into a device.</span></span> <span data-ttu-id="b20b4-113">如果您從一個裝置登出資源帳戶，然後使用它來登錄另一個裝置，則裝置標記會新裝置。</span><span class="sxs-lookup"><span data-stu-id="b20b4-113">If you sign a resource account out of one device and then use it to sign in to another device, the device tags are applied to the new device.</span></span>

## <a name="create-remove-or-rename-device-tags"></a><span data-ttu-id="b20b4-114">建立、移除或重新命名裝置標記</span><span class="sxs-lookup"><span data-stu-id="b20b4-114">Create, remove, or rename device tags</span></span>

<span data-ttu-id="b20b4-115">您可以使用裝置標記管理面板：</span><span class="sxs-lookup"><span data-stu-id="b20b4-115">Using the device tag management panel, you can:</span></span>

- <span data-ttu-id="b20b4-116">查看所有裝置標記。</span><span class="sxs-lookup"><span data-stu-id="b20b4-116">See all your device tags.</span></span>
- <span data-ttu-id="b20b4-117">輕鬆建立多個裝置標記，稍後再指派給裝置。</span><span class="sxs-lookup"><span data-stu-id="b20b4-117">Create multiple device tags easily and then assign them to devices at a later time.</span></span> <span data-ttu-id="b20b4-118">標記最多 25 個字元。</span><span class="sxs-lookup"><span data-stu-id="b20b4-118">Tags can be up to 25 characters.</span></span>
- <span data-ttu-id="b20b4-119">移除不再需要的裝置標記。</span><span class="sxs-lookup"><span data-stu-id="b20b4-119">Remove device tags that are no longer needed.</span></span> <span data-ttu-id="b20b4-120">在移除裝置標記之前，您必須將其從所有已新增的裝置移除。</span><span class="sxs-lookup"><span data-stu-id="b20b4-120">Before you can remove a device tag, you'll need to remove it from all of the devices it has been added to.</span></span>
- <span data-ttu-id="b20b4-121">重新命名裝置標記。</span><span class="sxs-lookup"><span data-stu-id="b20b4-121">Rename device tags.</span></span> <span data-ttu-id="b20b4-122">重新命名裝置標記時，該變更會反映在新增到的所有裝置上。</span><span class="sxs-lookup"><span data-stu-id="b20b4-122">When you rename a device tag, that change is reflected on all the devices it's been added to.</span></span> <span data-ttu-id="b20b4-123">標記最多 25 個字元。</span><span class="sxs-lookup"><span data-stu-id="b20b4-123">Tags can be up to 25 characters.</span></span>

1. <span data-ttu-id="b20b4-124">請流覽 以Microsoft Teams系統管理中心 https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="b20b4-124">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="b20b4-125">流覽至 **裝置** ，然後選擇任何裝置窗格，例如 **電話**。</span><span class="sxs-lookup"><span data-stu-id="b20b4-125">Navigate to **Devices** and then choose any device pane, such as **Phones**.</span></span>
3. <span data-ttu-id="b20b4-126">選取 **頁面** 右上角的動作，然後選取所有 **裝置標記**。</span><span class="sxs-lookup"><span data-stu-id="b20b4-126">Select **Actions** in the upper-right corner of the page and select **All device tags**.</span></span>
4. <span data-ttu-id="b20b4-127">若要建立裝置標記，請選取 **+新增**，為裝置標記提供值，然後 **選取儲存圖示** 。</span><span class="sxs-lookup"><span data-stu-id="b20b4-127">To create a device tag, select **+ Add**, provide a value for the device tag, and select the **Save** icon.</span></span>
5. <span data-ttu-id="b20b4-128">若要移除裝置標記，請選取要移除之裝置標記旁的省略號 **...，** 然後選取 **刪除**。</span><span class="sxs-lookup"><span data-stu-id="b20b4-128">To remove a device tag, select the ellipsis **...** next to the device tag you want to remove, and select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="b20b4-129">如果您嘗試移除已新增到裝置中的裝置標記，您會收到一則訊息，詢問您是否要從所有裝置移除該標記。</span><span class="sxs-lookup"><span data-stu-id="b20b4-129">If you try to remove a device tag that's been added to devices, you'll receive a message asking if you want to remove it from all devices.</span></span> <span data-ttu-id="b20b4-130">如果您想要這麼做並繼續移除裝置標記，請選取取消 **標記裝置**。</span><span class="sxs-lookup"><span data-stu-id="b20b4-130">If you want to do this and continue to remove the device tag, select **Untag devices**.</span></span>
6. <span data-ttu-id="b20b4-131">若要重新命名裝置標記，請選取要重新命名之裝置標記旁的省略號 **，** 然後 **選取編輯**。</span><span class="sxs-lookup"><span data-stu-id="b20b4-131">To rename a device tag, select the ellipsis **...** next to the device tag you want to rename, and select **Edit**.</span></span> <span data-ttu-id="b20b4-132">為裝置標記提供新值，然後 **選取儲存圖示** 。</span><span class="sxs-lookup"><span data-stu-id="b20b4-132">Provide a new value for the device tag and select the **Save** icon.</span></span>

## <a name="add-or-remove-tags-on-a-single-device"></a><span data-ttu-id="b20b4-133">在單一裝置上新增或移除標記</span><span class="sxs-lookup"><span data-stu-id="b20b4-133">Add or remove tags on a single device</span></span>

<span data-ttu-id="b20b4-134">當您新增標記至裝置時，您可以選取現有的標記或建立新標記。</span><span class="sxs-lookup"><span data-stu-id="b20b4-134">When you add tags to a device, you can either select an existing tag or create a new one.</span></span> <span data-ttu-id="b20b4-135">標記最多 25 個字元。</span><span class="sxs-lookup"><span data-stu-id="b20b4-135">Tags can be up to 25 characters.</span></span>

1. <span data-ttu-id="b20b4-136">請流覽 以Microsoft Teams系統管理中心 https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="b20b4-136">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="b20b4-137">流覽 **至裝置，** 然後選擇包含要新增或移除標記之裝置之裝置窗格。</span><span class="sxs-lookup"><span data-stu-id="b20b4-137">Navigate to **Devices** and then choose the device pane that contains the device you want to add or remove tags on.</span></span>
3. <span data-ttu-id="b20b4-138">在您想要新增或移除標記的裝置旁邊放置一個核取方塊，然後選取管理 **標記**。</span><span class="sxs-lookup"><span data-stu-id="b20b4-138">Place a check mark next to the device you want to add or remove tags on and select **Manage tags**.</span></span>
4. <span data-ttu-id="b20b4-139">如果您想要新增標記：</span><span class="sxs-lookup"><span data-stu-id="b20b4-139">If you want to add a tag:</span></span>
    1. <span data-ttu-id="b20b4-140">開始輸入要新增的標記名稱。</span><span class="sxs-lookup"><span data-stu-id="b20b4-140">Start typing the tag name you want to add.</span></span>
    2. <span data-ttu-id="b20b4-141">如果標記已存在，請從所退回的標記清單中選取它。</span><span class="sxs-lookup"><span data-stu-id="b20b4-141">If the tag already exists, select it from the list of tags that are returned.</span></span>
    3. <span data-ttu-id="b20b4-142">如果標記不存在，請選取新增 **" \<tag name> 做為新標記**。</span><span class="sxs-lookup"><span data-stu-id="b20b4-142">If the tag doesn't exist, select **Add "\<tag name>" as a new tag**.</span></span> <span data-ttu-id="b20b4-143">標記最多 25 個字元。</span><span class="sxs-lookup"><span data-stu-id="b20b4-143">Tags can be up to 25 characters.</span></span>
5. <span data-ttu-id="b20b4-144">如果您想要移除標記，請選取 **要** 移除之標記旁的 X。</span><span class="sxs-lookup"><span data-stu-id="b20b4-144">If you want to remove a tag, select **X** next to the tag you want to remove.</span></span>
6. <span data-ttu-id="b20b4-145">如果您想要新增或移除更多標記，請重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="b20b4-145">Repeat the steps above if you want to add or remove more tags.</span></span>
7. <span data-ttu-id="b20b4-146">選取 **Apply**。</span><span class="sxs-lookup"><span data-stu-id="b20b4-146">Select **Apply**.</span></span>

## <a name="add-or-remove-tags-on-multiple-devices"></a><span data-ttu-id="b20b4-147">在多個裝置上新增或移除標記</span><span class="sxs-lookup"><span data-stu-id="b20b4-147">Add or remove tags on multiple devices</span></span>

<span data-ttu-id="b20b4-148">當您新增標記至裝置時，您可以選取現有的標記或建立新標記。</span><span class="sxs-lookup"><span data-stu-id="b20b4-148">When you add tags to a device, you can either select an existing tag or create a new one.</span></span> <span data-ttu-id="b20b4-149">標記最多 25 個字元。</span><span class="sxs-lookup"><span data-stu-id="b20b4-149">Tags can be up to 25 characters.</span></span> <span data-ttu-id="b20b4-150">如果您想要從多個裝置移除標記，您必須選取與Teams相關聯的使用者，然後從使用者移除標記。</span><span class="sxs-lookup"><span data-stu-id="b20b4-150">If you want to remove a tag from multiple devices, you need to select the Teams user that's associated with the device and remove the tag from the user.</span></span>

1. <span data-ttu-id="b20b4-151">請流覽 以Microsoft Teams系統管理中心 https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="b20b4-151">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="b20b4-152">流覽 **至裝置** ，然後選擇包含要新增或移除標記之裝置之裝置窗格。</span><span class="sxs-lookup"><span data-stu-id="b20b4-152">Navigate to **Devices** and then choose the device pane that contains the devices you want to add or remove tags on.</span></span>
3. <span data-ttu-id="b20b4-153">在您想要新增或移除標記的裝置旁邊放置一個核取方塊，然後選取管理 **標記**。</span><span class="sxs-lookup"><span data-stu-id="b20b4-153">Place a check mark next to the devices you want to add or remove tags on and select **Manage tags**.</span></span>
4. <span data-ttu-id="b20b4-154">如果您想要新增標記：</span><span class="sxs-lookup"><span data-stu-id="b20b4-154">If you want to add a tag:</span></span>
    1. <span data-ttu-id="b20b4-155">開始在管理使用者所有裝置上的標記中輸入Teams **名稱**。</span><span class="sxs-lookup"><span data-stu-id="b20b4-155">Start typing the tag name you want to add in **Manage tags for all devices of Teams users**.</span></span>
    2. <span data-ttu-id="b20b4-156">如果標記已存在，請從所退回的標記清單中選取它。</span><span class="sxs-lookup"><span data-stu-id="b20b4-156">If the tag already exists, select it from the list of tags that are returned.</span></span>
    3. <span data-ttu-id="b20b4-157">如果標記不存在，請選取新增 **" \<tag name> 做為新標記**。</span><span class="sxs-lookup"><span data-stu-id="b20b4-157">If the tag doesn't exist, select **Add "\<tag name>" as a new tag**.</span></span>
5. <span data-ttu-id="b20b4-158">如果您想要移除標記：</span><span class="sxs-lookup"><span data-stu-id="b20b4-158">If you want to remove a tag:</span></span>
    1. <span data-ttu-id="b20b4-159">展開 **選取 Teams 使用者**。</span><span class="sxs-lookup"><span data-stu-id="b20b4-159">Expand **Select Teams users**.</span></span>
    2. <span data-ttu-id="b20b4-160">展開 **\<x> 要** 移除Teams使用者名稱下的標記。</span><span class="sxs-lookup"><span data-stu-id="b20b4-160">Expand **\<x> tags** under the name of the Teams user you want to remove tags from.</span></span>
    3. <span data-ttu-id="b20b4-161">選取 **要** 移除之標記旁的 X。</span><span class="sxs-lookup"><span data-stu-id="b20b4-161">Select **X** next to the tag you want to remove.</span></span>
6. <span data-ttu-id="b20b4-162">如果您想要新增或移除更多標記，請重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="b20b4-162">Repeat the steps above if you want to add or remove more tags.</span></span>
7. <span data-ttu-id="b20b4-163">選取 **Apply**。</span><span class="sxs-lookup"><span data-stu-id="b20b4-163">Select **Apply**.</span></span>

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a><span data-ttu-id="b20b4-164">使用篩選來退回具有特定標記的裝置</span><span class="sxs-lookup"><span data-stu-id="b20b4-164">Use filters to return devices with a specific tag</span></span>

<span data-ttu-id="b20b4-165">如果您已經將裝置標記新增到您的裝置，您可以使用它們來篩選裝置清單，只返回已新增指定標記的裝置。</span><span class="sxs-lookup"><span data-stu-id="b20b4-165">If you've added device tags to your devices, you can use them to filter the device list to return only the devices that have had a specified tag added to them.</span></span> <span data-ttu-id="b20b4-166">如果您只想查看特定聊天室的所有裝置、特定類型的所有裝置，或是新增標記時所使用的任何其他準則，這項功能會很有説明。</span><span class="sxs-lookup"><span data-stu-id="b20b4-166">This can be helpful if you just want to view all the devices in a specific room, all the devices of a certain type, or any other criteria you used when adding your tags.</span></span> <span data-ttu-id="b20b4-167">您也可以在退回的裝置上執行大量動作，例如，在波浪中應用更新，或根據使用裝置標記識別的裝置群組來設定不同的設定原則。</span><span class="sxs-lookup"><span data-stu-id="b20b4-167">You can also perform bulk actions on returned devices, such as applying updates in waves, or setting different configuration policies depending on the groups of devices identified using device tags.</span></span>

1. <span data-ttu-id="b20b4-168">請流覽 以Microsoft Teams系統管理中心 https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="b20b4-168">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="b20b4-169">流覽 **至裝置** ，然後選擇包含要篩選之裝置窗格。</span><span class="sxs-lookup"><span data-stu-id="b20b4-169">Navigate to **Devices** and then choose the device pane that contains the devices you want to filter.</span></span>
3. <span data-ttu-id="b20b4-170">選取篩選 **圖示** 。</span><span class="sxs-lookup"><span data-stu-id="b20b4-170">Select the **Filter** icon.</span></span>
4. <span data-ttu-id="b20b4-171">如果您只想指定單一標記，或想要尋找具有您指定所有標記的裝置，請選取符合 **所有這些條件**。</span><span class="sxs-lookup"><span data-stu-id="b20b4-171">If you only want to specify a single tag, or if you want to find devices that have all the tags you specify, select **Match all of these conditions**.</span></span>
5. <span data-ttu-id="b20b4-172">如果您想要尋找符合一或多個裝置標記的裝置，請選取符合 **上述任一條件**。</span><span class="sxs-lookup"><span data-stu-id="b20b4-172">If you want to find devices that match one or more device tags, select **Match any one of these conditions**.</span></span>
6. <span data-ttu-id="b20b4-173">選取標記 **欄位** ，然後在輸入值欄位中 **指定裝置標記** 名稱。</span><span class="sxs-lookup"><span data-stu-id="b20b4-173">Select the **Tag** field and then specify a device tag name in the **Enter a value** field.</span></span>
7. <span data-ttu-id="b20b4-174">如果您想要新增更多裝置標記， **請針對要** 新增的每個標記選取新增更多標記，然後重複步驟 6。</span><span class="sxs-lookup"><span data-stu-id="b20b4-174">If you want to add more device tags, select **Add more** and repeat step 6 for each tag you want to add.</span></span>
8. <span data-ttu-id="b20b4-175">選取 **Apply**。</span><span class="sxs-lookup"><span data-stu-id="b20b4-175">Select **Apply**.</span></span>

<span data-ttu-id="b20b4-176">篩選裝置清單中的裝置之後，您可以像平常一樣對裝置執行動作。</span><span class="sxs-lookup"><span data-stu-id="b20b4-176">After you've filtered the devices in your device list, you can perform actions on them as you normally would.</span></span> <span data-ttu-id="b20b4-177">例如，您可以選取這些設定，然後指派設定、編輯 (，Teams 會議室裝置) 等等。</span><span class="sxs-lookup"><span data-stu-id="b20b4-177">For example, you can select them and then assign configurations, edit their settings (if they're Teams Rooms devices), and so on.</span></span> <span data-ttu-id="b20b4-178">完成後，您可以選取標記篩選項目旁的 **X，** 或選取清單右側的所有清除，以移除篩選。 </span><span class="sxs-lookup"><span data-stu-id="b20b4-178">When you're done, you can remove the filter by selecting the **X**  next to the **Tag** filter entry or by selecting **Clear all** on the right side of the list.</span></span>
