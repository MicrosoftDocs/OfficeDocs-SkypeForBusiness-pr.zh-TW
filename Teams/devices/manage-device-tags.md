---
title: 管理和篩選 Microsoft 團隊的裝置標記
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
description: 瞭解如何管理及篩選 Microsoft 團隊裝置上的標籤。
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: d29bc28de39c8d145914d3bddab4ed949ad0a338
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962894"
---
# <a name="manage-microsoft-teams-device-tags"></a><span data-ttu-id="74e11-103">管理 Microsoft 團隊裝置標記</span><span class="sxs-lookup"><span data-stu-id="74e11-103">Manage Microsoft Teams device tags</span></span>

<span data-ttu-id="74e11-104">Microsoft 團隊中的裝置標記可讓您群組、組織及更輕鬆地管理您在組織中部署的裝置。</span><span class="sxs-lookup"><span data-stu-id="74e11-104">Device tags in Microsoft Teams let you group, organize, and more easily manage the devices you've deployed in your organization.</span></span> <span data-ttu-id="74e11-105">透過 Microsoft 團隊系統管理中心，您可以在裝置中新增一或多個標籤，使用篩選來查看符合您所指定之標記的裝置，然後執行含有該標籤的裝置的動作。</span><span class="sxs-lookup"><span data-stu-id="74e11-105">With the Microsoft Teams admin center, you can add one or more tags to devices, use filters to view devices that match the tag you specify, and then perform actions the devices that have that tag.</span></span>

<span data-ttu-id="74e11-106">您可以將裝置標籤新增至多種裝置類型。</span><span class="sxs-lookup"><span data-stu-id="74e11-106">You can add a device tag to more than one device type.</span></span> <span data-ttu-id="74e11-107">不過，當您在系統管理中心開啟裝置窗格時，只會傳回該類型的裝置。</span><span class="sxs-lookup"><span data-stu-id="74e11-107">However, when you open a device pane in the admin center, only the devices of that type are returned.</span></span> <span data-ttu-id="74e11-108">例如，您可以將 "公司" 標記指派給手機和團隊會議室裝置。</span><span class="sxs-lookup"><span data-stu-id="74e11-108">For example, you can assign the "Corporate" tag to both phones and Teams Rooms devices.</span></span> <span data-ttu-id="74e11-109">如果您在**裝置**手機中搜尋「公司」標籤  >  \*\* \*\*，則只會傳回手機。</span><span class="sxs-lookup"><span data-stu-id="74e11-109">If you search for the "Corporate" tag while in **Devices** > **Phones**, only phones are returned.</span></span> <span data-ttu-id="74e11-110">同樣地，如果您在 [**裝置**] 團隊聊天室中搜尋「公司」標籤  >  \*\* \*\*，則只會傳回團隊機房裝置。</span><span class="sxs-lookup"><span data-stu-id="74e11-110">Similarly, if you search for the "Corporate" tag in **Devices** > **Teams Rooms**, only Teams Rooms devices are returned.</span></span>

<span data-ttu-id="74e11-111">若要管理裝置標記，您必須是全域系統管理員、團隊服務系統管理員或團隊裝置系統管理員。如需管理員角色的詳細資訊，請參閱 [使用 Microsoft 團隊管理員角色管理團隊](../using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="74e11-111">To manage device tags, you need to be a Global admin, Teams Service admin, or Teams Device admin. For more information about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74e11-112">裝置標記會指派給登入裝置的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="74e11-112">Device tags are assigned to the resource account that's logged into a device.</span></span> <span data-ttu-id="74e11-113">如果您將資源帳戶簽出一個裝置，然後使用它來登入另一個裝置，則會將裝置標記套用至新裝置。</span><span class="sxs-lookup"><span data-stu-id="74e11-113">If you sign a resource account out of one device and then use it to sign into another devices, the device tags are applied to new device.</span></span>

## <a name="create-remove-or-rename-device-tags"></a><span data-ttu-id="74e11-114">建立、移除或重新命名裝置標記</span><span class="sxs-lookup"><span data-stu-id="74e11-114">Create, remove, or rename device tags</span></span>

<span data-ttu-id="74e11-115">使用 [裝置標記管理] 面板，您可以：</span><span class="sxs-lookup"><span data-stu-id="74e11-115">Using the device tag management panel, you can:</span></span>

- <span data-ttu-id="74e11-116">查看所有的裝置標記。</span><span class="sxs-lookup"><span data-stu-id="74e11-116">See all your device tags.</span></span>
- <span data-ttu-id="74e11-117">輕鬆建立多個裝置標記，稍後再將它們指派給裝置。</span><span class="sxs-lookup"><span data-stu-id="74e11-117">Create multiple device tags easily and then assign them to devices at a later time.</span></span> <span data-ttu-id="74e11-118">標記最多可以有25個字元。</span><span class="sxs-lookup"><span data-stu-id="74e11-118">Tags can be up to 25 characters.</span></span>
- <span data-ttu-id="74e11-119">移除不再需要的裝置標記。</span><span class="sxs-lookup"><span data-stu-id="74e11-119">Remove device tags that are no longer needed.</span></span> <span data-ttu-id="74e11-120">您必須先將裝置標籤從已新增到其中的所有裝置中移除，才能移除裝置標記。</span><span class="sxs-lookup"><span data-stu-id="74e11-120">Before you can remove a device tag, you'll need to remove it from all of the devices it has been added to.</span></span>
- <span data-ttu-id="74e11-121">重新命名裝置標記。</span><span class="sxs-lookup"><span data-stu-id="74e11-121">Rename device tags.</span></span> <span data-ttu-id="74e11-122">當您重新命名裝置標籤時，該變更會反映在已新增的所有裝置上。</span><span class="sxs-lookup"><span data-stu-id="74e11-122">When you rename a device tag, that change is reflected on all the devices it's been added to.</span></span> <span data-ttu-id="74e11-123">標記最多可以有25個字元。</span><span class="sxs-lookup"><span data-stu-id="74e11-123">Tags can be up to 25 characters.</span></span>

1. <span data-ttu-id="74e11-124">透過造訪登入 Microsoft 團隊系統管理中心 https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="74e11-124">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="74e11-125">流覽至 [ **裝置** ]，然後選擇 [任何裝置] 窗格（例如 [ **電話**]）。</span><span class="sxs-lookup"><span data-stu-id="74e11-125">Navigate to **Devices** and then choose any device pane, such as **Phones**.</span></span>
3. <span data-ttu-id="74e11-126">選取頁面右上角的 [ **動作** ]，然後選取 [ **所有裝置標記**]。</span><span class="sxs-lookup"><span data-stu-id="74e11-126">Select **Actions** in the upper-right corner of the page and select **All device tags**.</span></span>
4. <span data-ttu-id="74e11-127">若要建立裝置標記，請選取 [ **+ 新增**]，提供 device 標記的值，然後選取 [ **儲存** ] 圖示。</span><span class="sxs-lookup"><span data-stu-id="74e11-127">To create a device tag, select **+ Add**, provide a value for the device tag, and select the **Save** icon.</span></span>
5. <span data-ttu-id="74e11-128">若要移除裝置標籤，請選取您要移除之裝置標記旁邊的省略號 **...** ，然後選取 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="74e11-128">To remove a device tag, select the ellipsis **...** next to the device tag you want to remove, and select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="74e11-129">如果您嘗試移除已新增至裝置的裝置標記，您會收到一則訊息，詢問您是否要將它從所有裝置中移除。</span><span class="sxs-lookup"><span data-stu-id="74e11-129">If you try to remove a device tag that's been added to devices, you'll receive a message asking if you want to remove it from all devices.</span></span> <span data-ttu-id="74e11-130">如果您想要這樣做並繼續移除 device 標記，請選取 [ **將裝置**]。</span><span class="sxs-lookup"><span data-stu-id="74e11-130">If you want to do this and continue to remove the device tag, select **Untag devices**.</span></span>
6. <span data-ttu-id="74e11-131">若要重新命名裝置標籤，請選取您想要重新命名之裝置標記旁邊的省略號 **...** ，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="74e11-131">To rename a device tag, select the ellipsis **...** next to the device tag you want to rename, and select **Edit**.</span></span> <span data-ttu-id="74e11-132">為 [裝置] 標記提供新的值，然後選取 [ **儲存** ] 圖示。</span><span class="sxs-lookup"><span data-stu-id="74e11-132">Provide a new value for the device tag and select the **Save** icon.</span></span>

## <a name="add-or-remove-tags-on-a-single-device"></a><span data-ttu-id="74e11-133">在單一裝置上新增或移除標籤</span><span class="sxs-lookup"><span data-stu-id="74e11-133">Add or remove tags on a single device</span></span>

<span data-ttu-id="74e11-134">當您在裝置中新增標籤時，您可以選取現有的標籤或建立新的標籤。</span><span class="sxs-lookup"><span data-stu-id="74e11-134">When you add tags to a device, you can either select an existing tag or create a new one.</span></span> <span data-ttu-id="74e11-135">標記最多可以有25個字元。</span><span class="sxs-lookup"><span data-stu-id="74e11-135">Tags can be up to 25 characters.</span></span>

1. <span data-ttu-id="74e11-136">透過造訪登入 Microsoft 團隊系統管理中心 https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="74e11-136">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="74e11-137">流覽至 [ **裝置** ]，然後選擇包含您要新增或移除標籤之裝置的裝置窗格。</span><span class="sxs-lookup"><span data-stu-id="74e11-137">Navigate to **Devices** and then choose the device pane that contains the device you want to add or remove tags on.</span></span>
3. <span data-ttu-id="74e11-138">在您要新增或移除標籤的裝置旁，選取 [ **管理**標籤] 旁邊的核取記號。</span><span class="sxs-lookup"><span data-stu-id="74e11-138">Place a check mark next to the device you want to add or remove tags on and select **Manage tags**.</span></span>
4. <span data-ttu-id="74e11-139">如果您要新增標籤：</span><span class="sxs-lookup"><span data-stu-id="74e11-139">If you want to add a tag:</span></span>
    1. <span data-ttu-id="74e11-140">開始輸入您要新增的標記名稱。</span><span class="sxs-lookup"><span data-stu-id="74e11-140">Start typing the tag name you want to add.</span></span>
    2. <span data-ttu-id="74e11-141">如果標記已存在，請從傳回的標記清單中選取。</span><span class="sxs-lookup"><span data-stu-id="74e11-141">If the tag already exists, select it from the list of tags that are returned.</span></span>
    3. <span data-ttu-id="74e11-142">如果標記不存在，請選取 [ \*\* \<tag name> 新增「] 做為新的標記\*\*。</span><span class="sxs-lookup"><span data-stu-id="74e11-142">If the tag doesn't exist, select **Add "\<tag name>" as a new tag**.</span></span> <span data-ttu-id="74e11-143">標記最多可以有25個字元。</span><span class="sxs-lookup"><span data-stu-id="74e11-143">Tags can be up to 25 characters.</span></span>
5. <span data-ttu-id="74e11-144">若要移除標籤，請選取您要移除之標記旁邊的 [ **X** ]。</span><span class="sxs-lookup"><span data-stu-id="74e11-144">If you want to remove a tag, select **X** next to the tag you want to remove.</span></span>
6. <span data-ttu-id="74e11-145">如果您想要新增或移除更多標記，請重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="74e11-145">Repeat the steps above if you want to add or remove more tags.</span></span>
7. <span data-ttu-id="74e11-146">選取 **[** 套用]。</span><span class="sxs-lookup"><span data-stu-id="74e11-146">Select **Apply**.</span></span>

## <a name="add-or-remove-tags-on-multiple-devices"></a><span data-ttu-id="74e11-147">在多個裝置上新增或移除標籤</span><span class="sxs-lookup"><span data-stu-id="74e11-147">Add or remove tags on multiple devices</span></span>

<span data-ttu-id="74e11-148">當您在裝置中新增標籤時，您可以選取現有的標籤或建立新的標籤。</span><span class="sxs-lookup"><span data-stu-id="74e11-148">When you add tags to a device, you can either select an existing tag or create a new one.</span></span> <span data-ttu-id="74e11-149">標記最多可以有25個字元。</span><span class="sxs-lookup"><span data-stu-id="74e11-149">Tags can be up to 25 characters.</span></span> <span data-ttu-id="74e11-150">如果您想要移除多個裝置上的標籤，您必須選取與裝置相關聯的小組使用者，然後從使用者移除標記。</span><span class="sxs-lookup"><span data-stu-id="74e11-150">If you want to remove a tag from multiple devices, you need to select the Teams user that's associated with the device and remove the tag from the user.</span></span>

1. <span data-ttu-id="74e11-151">透過造訪登入 Microsoft 團隊系統管理中心 https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="74e11-151">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="74e11-152">流覽至 [ **裝置** ]，然後選擇包含您要新增或移除標籤之裝置的裝置窗格。</span><span class="sxs-lookup"><span data-stu-id="74e11-152">Navigate to **Devices** and then choose the device pane that contains the devices you want to add or remove tags on.</span></span>
3. <span data-ttu-id="74e11-153">在您要新增或移除標籤的裝置旁邊放置核取符號，然後選取 [ **管理**標籤]。</span><span class="sxs-lookup"><span data-stu-id="74e11-153">Place a check mark next to the devices you want to add or remove tags on and select **Manage tags**.</span></span>
4. <span data-ttu-id="74e11-154">如果您要新增標籤：</span><span class="sxs-lookup"><span data-stu-id="74e11-154">If you want to add a tag:</span></span>
    1. <span data-ttu-id="74e11-155">開始輸入您想要在 [ **管理標記] 中為 [團隊使用者] 的所有裝置**新增的標記名稱。</span><span class="sxs-lookup"><span data-stu-id="74e11-155">Start typing the tag name you want to add in **Manage tags for all devices of Teams users**.</span></span>
    2. <span data-ttu-id="74e11-156">如果標記已存在，請從傳回的標記清單中選取。</span><span class="sxs-lookup"><span data-stu-id="74e11-156">If the tag already exists, select it from the list of tags that are returned.</span></span>
    3. <span data-ttu-id="74e11-157">如果標記不存在，請選取 [ \*\* \<tag name> 新增「] 做為新的標記\*\*。</span><span class="sxs-lookup"><span data-stu-id="74e11-157">If the tag doesn't exist, select **Add "\<tag name>" as a new tag**.</span></span>
5. <span data-ttu-id="74e11-158">如果您想要移除標記：</span><span class="sxs-lookup"><span data-stu-id="74e11-158">If you want to remove a tag:</span></span>
    1. <span data-ttu-id="74e11-159">展開 [ **選取團隊使用者**]。</span><span class="sxs-lookup"><span data-stu-id="74e11-159">Expand **Select Teams users**.</span></span>
    2. <span data-ttu-id="74e11-160">展開您要從中移除標籤之小組使用者名稱下方的 [ \*\* \<x> 標記\*\*]。</span><span class="sxs-lookup"><span data-stu-id="74e11-160">Expand **\<x> tags** under the name of the Teams user you want to remove tags from.</span></span>
    3. <span data-ttu-id="74e11-161">選取您要移除之標記旁邊的 [ **X** ]。</span><span class="sxs-lookup"><span data-stu-id="74e11-161">Select **X** next to the tag you want to remove.</span></span>
6. <span data-ttu-id="74e11-162">如果您想要新增或移除更多標記，請重複上述步驟。</span><span class="sxs-lookup"><span data-stu-id="74e11-162">Repeat the steps above if you want to add or remove more tags.</span></span>
7. <span data-ttu-id="74e11-163">選取 **[** 套用]。</span><span class="sxs-lookup"><span data-stu-id="74e11-163">Select **Apply**.</span></span>

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a><span data-ttu-id="74e11-164">使用篩選來傳回具有特定標記的裝置</span><span class="sxs-lookup"><span data-stu-id="74e11-164">Use filters to return devices with a specific tag</span></span>

<span data-ttu-id="74e11-165">如果您已將裝置標籤新增到裝置，您可以使用它們來篩選裝置清單，只傳回已將指定標記新增至其中的裝置。</span><span class="sxs-lookup"><span data-stu-id="74e11-165">If you've added device tags to your devices, you can use them to filter the device list to return only the devices that have had a specified tag added to them.</span></span> <span data-ttu-id="74e11-166">如果您只想要查看特定聊天室中的所有裝置、特定類型的所有裝置，或新增標籤時所使用的任何其他準則，這會很有説明。</span><span class="sxs-lookup"><span data-stu-id="74e11-166">This can be helpful if you just want to view all the devices in a specific room, all the devices of a certain type, or any other criteria you used when adding your tags.</span></span> <span data-ttu-id="74e11-167">您也可以在傳回的裝置上執行大量動作，例如在波形中套用更新，或根據使用裝置標籤識別的裝置群組設定不同的配置原則。</span><span class="sxs-lookup"><span data-stu-id="74e11-167">You can also perform bulk actions on returned devices, such as applying updates in waves, or setting different configuration policies depending on the groups of devices identified using device tags.</span></span>

1. <span data-ttu-id="74e11-168">透過造訪登入 Microsoft 團隊系統管理中心 https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="74e11-168">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="74e11-169">流覽至 [ **裝置** ]，然後選擇包含您要篩選之裝置的裝置窗格。</span><span class="sxs-lookup"><span data-stu-id="74e11-169">Navigate to **Devices** and then choose the device pane that contains the devices you want to filter.</span></span>
3. <span data-ttu-id="74e11-170">選取 [ **篩選** ] 圖示。</span><span class="sxs-lookup"><span data-stu-id="74e11-170">Select the **Filter** icon.</span></span>
4. <span data-ttu-id="74e11-171">如果您只想要指定單一標記，或者想要尋找具有您指定之所有標記的裝置，請選取 [ **符合所有這些條件**]。</span><span class="sxs-lookup"><span data-stu-id="74e11-171">If you only want to specify a single tag, or if you want to find devices that have all the tags you specify, select **Match all of these conditions**.</span></span>
5. <span data-ttu-id="74e11-172">如果您想要尋找符合一或多個裝置標籤的裝置，請選取 [ **符合下列任何一個條件**]。</span><span class="sxs-lookup"><span data-stu-id="74e11-172">If you want to find devices that match one or more device tags, select **Match any one of these conditions**.</span></span>
6. <span data-ttu-id="74e11-173">選取 **Tag** 欄位，然後在 [ **輸入值** ] 欄位中指定裝置標記名稱。</span><span class="sxs-lookup"><span data-stu-id="74e11-173">Select the **Tag** field and then specify a device tag name in the **Enter a value** field.</span></span>
7. <span data-ttu-id="74e11-174">如果您想要新增更多裝置標記，請選取 [ **新增更多** ]，然後針對您要新增的每個標籤重複步驟6。</span><span class="sxs-lookup"><span data-stu-id="74e11-174">If you want to add more device tags, select **Add more** and repeat step 6 for each tag you want to add.</span></span>
8. <span data-ttu-id="74e11-175">選取 **[** 套用]。</span><span class="sxs-lookup"><span data-stu-id="74e11-175">Select **Apply**.</span></span>

<span data-ttu-id="74e11-176">在裝置清單中篩選出裝置之後，您就可以像平常一樣在這些裝置上執行動作。</span><span class="sxs-lookup"><span data-stu-id="74e11-176">After you've filtered the devices in your device list, you can perform actions on them as you normally would.</span></span> <span data-ttu-id="74e11-177">例如，您可以選取它們並指派設定、編輯其設定 (如果他們是 [團隊室]，請) 等等。</span><span class="sxs-lookup"><span data-stu-id="74e11-177">For example, you can select them and then assign configurations, edit their settings (if they're Teams Rooms devices), and so on.</span></span> <span data-ttu-id="74e11-178">完成後，您可以**選取 [標籤篩選]** 專案旁的**X** ，或選取清單右側的 [**全部清除**] 來移除篩選。</span><span class="sxs-lookup"><span data-stu-id="74e11-178">When you're done, you can remove the filter by selecting the **X**  next to the **Tag** filter entry or by selecting **Clear all** on the right side of the list.</span></span>
