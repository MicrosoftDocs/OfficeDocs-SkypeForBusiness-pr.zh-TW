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
ms.openlocfilehash: f428a40e5a9adf4a53d4b2e12064b90b4ceebe43
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2020
ms.locfileid: "46657094"
---
# <a name="manage-microsoft-teams-device-tags"></a><span data-ttu-id="9c123-103">管理 Microsoft 團隊裝置標記</span><span class="sxs-lookup"><span data-stu-id="9c123-103">Manage Microsoft Teams device tags</span></span>

> [!NOTE]
> <span data-ttu-id="9c123-104">在波形中將標籤新增至 Microsoft 團隊客戶的功能。</span><span class="sxs-lookup"><span data-stu-id="9c123-104">The ability to add tags to devices is being made available to Microsoft Teams customers in waves.</span></span> <span data-ttu-id="9c123-105">如果您在 [團隊系統管理中心] 中沒有看到 [管理標籤] 的選項，則尚未在您的租使用者上啟用裝置標記。</span><span class="sxs-lookup"><span data-stu-id="9c123-105">If you don't see the option to manage tags in the Teams admin center, device tags haven't been enabled on your tenant yet.</span></span> <span data-ttu-id="9c123-106">稍後再次查看。</span><span class="sxs-lookup"><span data-stu-id="9c123-106">Check back again at a later date.</span></span>

<span data-ttu-id="9c123-107">Microsoft 團隊中的裝置標記可讓您群組、組織及更輕鬆地管理您在組織中部署的裝置。</span><span class="sxs-lookup"><span data-stu-id="9c123-107">Device tags in Microsoft Teams let you group, organize, and more easily manage the devices you've deployed in your organization.</span></span> <span data-ttu-id="9c123-108">透過 Microsoft 團隊系統管理中心，您可以在裝置中新增一或多個標籤，使用篩選來查看符合您所指定之標記的裝置，然後執行含有該標籤的裝置的動作。</span><span class="sxs-lookup"><span data-stu-id="9c123-108">With the Microsoft Teams admin center, you can add one or more tags to devices, use filters to view devices that match the tag you specify, and then perform actions the devices that have that tag.</span></span>

<span data-ttu-id="9c123-109">您可以將裝置標籤新增至多種裝置類型。</span><span class="sxs-lookup"><span data-stu-id="9c123-109">You can add a device tag to more than one device type.</span></span> <span data-ttu-id="9c123-110">不過，當您在系統管理中心開啟裝置窗格時，只會傳回該類型的裝置。</span><span class="sxs-lookup"><span data-stu-id="9c123-110">However, when you open a device pane in the admin center, only the devices of that type are returned.</span></span> <span data-ttu-id="9c123-111">例如，您可以將 "公司" 標記指派給手機和團隊會議室裝置。</span><span class="sxs-lookup"><span data-stu-id="9c123-111">For example, you can assign the "Corporate" tag to both phones and Teams Rooms devices.</span></span> <span data-ttu-id="9c123-112">如果您在**裝置**手機中搜尋「公司」標籤  >  \*\* \*\*，則只會傳回手機。</span><span class="sxs-lookup"><span data-stu-id="9c123-112">If you search for the "Corporate" tag while in **Devices** > **Phones**, only phones are returned.</span></span> <span data-ttu-id="9c123-113">同樣地，如果您在 [**裝置**] 團隊聊天室中搜尋「公司」標籤  >  \*\* \*\*，則只會傳回團隊機房裝置。</span><span class="sxs-lookup"><span data-stu-id="9c123-113">Similarly, if you search for the "Corporate" tag in **Devices** > **Teams Rooms**, only Teams Rooms devices are returned.</span></span>

<span data-ttu-id="9c123-114">若要管理裝置標記，您必須是全域系統管理員或團隊服務系統管理員。</span><span class="sxs-lookup"><span data-stu-id="9c123-114">To manage device tags, you need to be either a Global admin or a Teams service admin.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9c123-115">裝置標記會指派給登入裝置的資源帳戶。</span><span class="sxs-lookup"><span data-stu-id="9c123-115">Device tags are assigned to the resource account that's logged into a device.</span></span> <span data-ttu-id="9c123-116">如果您將資源帳戶簽出一個裝置，然後使用它來登入另一個裝置，則會將裝置標記套用至新裝置。</span><span class="sxs-lookup"><span data-stu-id="9c123-116">If you sign a resource account out of one device and then use it to sign into another devices, the device tags are applied to new device.</span></span>

## <a name="create-remove-or-rename-device-tags"></a><span data-ttu-id="9c123-117">建立、移除或重新命名裝置標記</span><span class="sxs-lookup"><span data-stu-id="9c123-117">Create, remove, or rename device tags</span></span>

<span data-ttu-id="9c123-118">使用 [裝置標記管理] 面板，您可以：</span><span class="sxs-lookup"><span data-stu-id="9c123-118">Using the device tag management panel, you can:</span></span>

- <span data-ttu-id="9c123-119">查看所有的裝置標記。</span><span class="sxs-lookup"><span data-stu-id="9c123-119">See all your device tags.</span></span>
- <span data-ttu-id="9c123-120">輕鬆建立多個裝置標記，稍後再將它們指派給裝置。</span><span class="sxs-lookup"><span data-stu-id="9c123-120">Create multiple device tags easily and then assign them to devices at a later time.</span></span> <span data-ttu-id="9c123-121">標記最多可以有25個字元。</span><span class="sxs-lookup"><span data-stu-id="9c123-121">Tags can be up to 25 characters.</span></span>
- <span data-ttu-id="9c123-122">移除不再需要的裝置標記。</span><span class="sxs-lookup"><span data-stu-id="9c123-122">Remove device tags that are no longer needed.</span></span> <span data-ttu-id="9c123-123">您必須先將裝置標籤從已新增到其中的所有裝置中移除，才能移除裝置標記。</span><span class="sxs-lookup"><span data-stu-id="9c123-123">Before you can remove a device tag, you'll need to remove it from all of the devices it has been added to.</span></span>
- <span data-ttu-id="9c123-124">重新命名裝置標記。</span><span class="sxs-lookup"><span data-stu-id="9c123-124">Rename device tags.</span></span> <span data-ttu-id="9c123-125">當您重新命名裝置標籤時，該變更會反映在已新增的所有裝置上。</span><span class="sxs-lookup"><span data-stu-id="9c123-125">When you rename a device tag, that change is reflected on all the devices it's been added to.</span></span> <span data-ttu-id="9c123-126">標記最多可以有25個字元。</span><span class="sxs-lookup"><span data-stu-id="9c123-126">Tags can be up to 25 characters.</span></span>

1. <span data-ttu-id="9c123-127">透過造訪登入 Microsoft 團隊管理中心 https://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9c123-127">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="9c123-128">流覽至 [**裝置**]，然後選擇 [任何裝置] 窗格（例如 [**電話**]）</span><span class="sxs-lookup"><span data-stu-id="9c123-128">Navigate to **Devices** and then choose any device pane, such as **Phones**</span></span>
3. <span data-ttu-id="9c123-129">選取頁面右上角的 [**動作**]，然後選取 [**所有裝置標記**]</span><span class="sxs-lookup"><span data-stu-id="9c123-129">Select **Actions** in the upper-right corner of the page and select **All device tags**</span></span>
4. <span data-ttu-id="9c123-130">若要建立裝置標記，請選取 [ **+ 新增**]，提供 device 標記的值，然後選取 [ **儲存** ] 圖示</span><span class="sxs-lookup"><span data-stu-id="9c123-130">To create a device tag, select **+ Add**, provide a value for the device tag, and select the **Save** icon</span></span>
5. <span data-ttu-id="9c123-131">若要移除裝置標籤，請選取您要移除之裝置標記旁邊的省略號 **...** ，然後選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="9c123-131">To remove a device tag, select the ellipsis **...** next to the device tag you want to remove, and select **Delete**</span></span>
    > [!NOTE]
    > <span data-ttu-id="9c123-132">如果您嘗試移除已新增至裝置的裝置標記，您會收到一則訊息，詢問您是否要將它從所有裝置中移除。</span><span class="sxs-lookup"><span data-stu-id="9c123-132">If you try to remove a device tag that's been added to devices, you'll receive a message asking if you want to remove it from all devices.</span></span> <span data-ttu-id="9c123-133">如果您想要這樣做並繼續移除 device 標記，請選取 [ **將裝置**]。</span><span class="sxs-lookup"><span data-stu-id="9c123-133">If you want to do this and continue to remove the device tag, select **Untag devices**.</span></span>
6. <span data-ttu-id="9c123-134">若要重新命名裝置標籤，請選取您想要重新命名之裝置標記旁邊的省略號 **...** ，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="9c123-134">To rename a device tag, select the ellipsis **...** next to the device tag you want to rename, and select **Edit**.</span></span> <span data-ttu-id="9c123-135">為 device 標記提供新的值，然後選取 [ **儲存** ] 圖示</span><span class="sxs-lookup"><span data-stu-id="9c123-135">Provide a new value for the device tag and select the **Save** icon</span></span>

## <a name="add-or-remove-tags-on-a-single-device"></a><span data-ttu-id="9c123-136">在單一裝置上新增或移除標籤</span><span class="sxs-lookup"><span data-stu-id="9c123-136">Add or remove tags on a single device</span></span>

<span data-ttu-id="9c123-137">當您在裝置中新增標籤時，您可以選取現有的標籤或建立新的標籤。</span><span class="sxs-lookup"><span data-stu-id="9c123-137">When you add tags to a device, you can either select an existing tag or create a new one.</span></span> <span data-ttu-id="9c123-138">標記最多可以有25個字元。</span><span class="sxs-lookup"><span data-stu-id="9c123-138">Tags can be up to 25 characters.</span></span>

1. <span data-ttu-id="9c123-139">透過造訪登入 Microsoft 團隊管理中心 https://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9c123-139">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="9c123-140">流覽至 [ **裝置** ]，然後選擇包含您要新增或移除標籤之裝置的裝置窗格</span><span class="sxs-lookup"><span data-stu-id="9c123-140">Navigate to **Devices** and then choose the device pane that contains the device you want to add or remove tags on</span></span>
3. <span data-ttu-id="9c123-141">在您要新增或移除標籤的裝置旁放置核取符號，然後選取 [**管理**標籤]</span><span class="sxs-lookup"><span data-stu-id="9c123-141">Place a check mark next to the device you want to add or remove tags on and select **Manage tags**</span></span>
4. <span data-ttu-id="9c123-142">如果您要新增標籤：</span><span class="sxs-lookup"><span data-stu-id="9c123-142">If you want to add a tag:</span></span>
    1. <span data-ttu-id="9c123-143">開始輸入您要新增的標記名稱</span><span class="sxs-lookup"><span data-stu-id="9c123-143">Start typing the tag name you want to add</span></span>
    2. <span data-ttu-id="9c123-144">如果標籤已存在，請從傳回的標記清單中選取該標記</span><span class="sxs-lookup"><span data-stu-id="9c123-144">If the tag already exists, select it from the list of tags that are returned</span></span>
    3. <span data-ttu-id="9c123-145">如果標記不存在，請選取 [ \*\* \<tag name> 新增「] 做為新的標記\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c123-145">If the tag doesn't exist, select **Add "\<tag name>" as a new tag**.</span></span> <span data-ttu-id="9c123-146">標記最多可以有25個字元。</span><span class="sxs-lookup"><span data-stu-id="9c123-146">Tags can be up to 25 characters.</span></span>
5. <span data-ttu-id="9c123-147">如果您想要移除標籤，請選取您要移除之標記旁邊的 [ **X** ]。</span><span class="sxs-lookup"><span data-stu-id="9c123-147">If you want to remove a tag, select **X** next to the tag you want to remove</span></span>
6. <span data-ttu-id="9c123-148">如果您想要新增或移除更多標記，請重複上述步驟</span><span class="sxs-lookup"><span data-stu-id="9c123-148">Repeat the steps above if you want to add or remove more tags</span></span>
7. <span data-ttu-id="9c123-149">選取 **[** 套用]</span><span class="sxs-lookup"><span data-stu-id="9c123-149">Select **Apply**</span></span>

## <a name="add-or-remove-tags-on-multiple-devices"></a><span data-ttu-id="9c123-150">在多個裝置上新增或移除標籤</span><span class="sxs-lookup"><span data-stu-id="9c123-150">Add or remove tags on multiple devices</span></span>

<span data-ttu-id="9c123-151">當您在裝置中新增標籤時，您可以選取現有的標籤或建立新的標籤。</span><span class="sxs-lookup"><span data-stu-id="9c123-151">When you add tags to a device, you can either select an existing tag or create a new one.</span></span> <span data-ttu-id="9c123-152">標記最多可以有25個字元。</span><span class="sxs-lookup"><span data-stu-id="9c123-152">Tags can be up to 25 characters.</span></span> <span data-ttu-id="9c123-153">如果您想要移除多個裝置上的標籤，您必須選取與裝置相關聯的小組使用者，然後從使用者移除標記。</span><span class="sxs-lookup"><span data-stu-id="9c123-153">If you want to remove a tag from multiple devices, you need to select the Teams user that's associated with the device and remove the tag from the user.</span></span>

1. <span data-ttu-id="9c123-154">透過造訪登入 Microsoft 團隊管理中心 https://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9c123-154">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="9c123-155">流覽至 [ **裝置** ]，然後選擇包含您要新增或移除標籤之裝置的裝置窗格</span><span class="sxs-lookup"><span data-stu-id="9c123-155">Navigate to **Devices** and then choose the device pane that contains the devices you want to add or remove tags on</span></span>
3. <span data-ttu-id="9c123-156">在您要新增或移除標籤的裝置旁邊放置核取符號，然後選取 [**管理**標籤]</span><span class="sxs-lookup"><span data-stu-id="9c123-156">Place a check mark next to the devices you want to add or remove tags on and select **Manage tags**</span></span>
4. <span data-ttu-id="9c123-157">如果您要新增標籤：</span><span class="sxs-lookup"><span data-stu-id="9c123-157">If you want to add a tag:</span></span>
    1. <span data-ttu-id="9c123-158">開始輸入您想要在 [管理標籤] 中新增的標籤名稱，以**供團隊使用者的所有裝置**使用</span><span class="sxs-lookup"><span data-stu-id="9c123-158">Start typing the tag name you want to add in **Manage tags for all devices of Teams users**</span></span>
    2. <span data-ttu-id="9c123-159">如果標籤已存在，請從傳回的標記清單中選取該標記</span><span class="sxs-lookup"><span data-stu-id="9c123-159">If the tag already exists, select it from the list of tags that are returned</span></span>
    3. <span data-ttu-id="9c123-160">如果標記不存在，請選取 [ \*\* \<tag name> 新增「] 做為新的標記\*\*</span><span class="sxs-lookup"><span data-stu-id="9c123-160">If the tag doesn't exist, select **Add "\<tag name>" as a new tag**</span></span>
5. <span data-ttu-id="9c123-161">如果您想要移除標記：</span><span class="sxs-lookup"><span data-stu-id="9c123-161">If you want to remove a tag:</span></span>
    1. <span data-ttu-id="9c123-162">展開 [**選取團隊使用者**]</span><span class="sxs-lookup"><span data-stu-id="9c123-162">Expand **Select Teams users**</span></span>
    2. <span data-ttu-id="9c123-163">展開您要從中移除標籤之小組使用者名稱下方的\*\* \<x> 標記\*\*</span><span class="sxs-lookup"><span data-stu-id="9c123-163">Expand **\<x> tags** under the name of the Teams user you want to remove tags from</span></span>
    3. <span data-ttu-id="9c123-164">選取您要移除之標記旁邊的 [ **X** ]</span><span class="sxs-lookup"><span data-stu-id="9c123-164">Select **X** next to the tag you want to remove</span></span>
6. <span data-ttu-id="9c123-165">如果您想要新增或移除更多標記，請重複上述步驟</span><span class="sxs-lookup"><span data-stu-id="9c123-165">Repeat the steps above if you want to add or remove more tags</span></span>
7. <span data-ttu-id="9c123-166">選取 **[** 套用]</span><span class="sxs-lookup"><span data-stu-id="9c123-166">Select **Apply**</span></span>

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a><span data-ttu-id="9c123-167">使用篩選來傳回具有特定標記的裝置</span><span class="sxs-lookup"><span data-stu-id="9c123-167">Use filters to return devices with a specific tag</span></span>

<span data-ttu-id="9c123-168">如果您已將裝置標籤新增到裝置，您可以使用它們來篩選裝置清單，只傳回已將指定標記新增至其中的裝置。</span><span class="sxs-lookup"><span data-stu-id="9c123-168">If you've added device tags to your devices, you can use them to filter the device list to return only the devices that have had a specified tag added to them.</span></span> <span data-ttu-id="9c123-169">如果您只想要查看特定聊天室中的所有裝置、特定類型的所有裝置，或新增標籤時所使用的任何其他準則，這會很有説明。</span><span class="sxs-lookup"><span data-stu-id="9c123-169">This can be helpful if you just want to view all the devices in a specific room, all the devices of a certain type, or any other criteria you used when adding your tags.</span></span> <span data-ttu-id="9c123-170">您也可以在傳回的裝置上執行大量動作，例如在波形中套用更新，或根據使用裝置標籤識別的裝置群組設定不同的配置原則。</span><span class="sxs-lookup"><span data-stu-id="9c123-170">You can also perform bulk actions on returned devices, such as applying updates in waves, or setting different configuration policies depending on the groups of devices identified using device tags.</span></span>

1. <span data-ttu-id="9c123-171">透過造訪登入 Microsoft 團隊管理中心 https://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9c123-171">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="9c123-172">流覽至 [ **裝置** ]，然後選擇包含您要篩選之裝置的裝置窗格</span><span class="sxs-lookup"><span data-stu-id="9c123-172">Navigate to **Devices** and then choose the device pane that contains the devices you want to filter</span></span>
3. <span data-ttu-id="9c123-173">選取 [ **篩選** ] 圖示</span><span class="sxs-lookup"><span data-stu-id="9c123-173">Select the **Filter** icon</span></span>
4. <span data-ttu-id="9c123-174">如果您只想要指定單一標記，或者想要尋找具有您指定之所有標記的裝置，請選取 [ **符合所有這些條件**]。</span><span class="sxs-lookup"><span data-stu-id="9c123-174">If you only want to specify a single tag, or if you want to find devices that have all the tags you specify, select **Match all of these conditions**.</span></span>
5. <span data-ttu-id="9c123-175">如果您想要尋找符合一或多個裝置標籤的裝置，請選取 [**符合下列任何一個條件**]</span><span class="sxs-lookup"><span data-stu-id="9c123-175">If you want to find devices that match one or more device tags, select **Match any one of these conditions**</span></span>
6. <span data-ttu-id="9c123-176">選取 [ **Tag** ] 欄位，然後在 [ **輸入值** ] 欄位中指定裝置標記名稱</span><span class="sxs-lookup"><span data-stu-id="9c123-176">Select the **Tag** field and then specify a device tag name in the **Enter a value** field</span></span>
7. <span data-ttu-id="9c123-177">如果您想要新增更多裝置標記，請選取 [ **新增更多** ]，然後針對您要新增的每個標籤重複步驟6。</span><span class="sxs-lookup"><span data-stu-id="9c123-177">If you want to add more device tags, select **Add more** and repeat step 6 for each tag you want to add</span></span>
8. <span data-ttu-id="9c123-178">選取 **[** 套用]</span><span class="sxs-lookup"><span data-stu-id="9c123-178">Select **Apply**</span></span>

<span data-ttu-id="9c123-179">在裝置清單中篩選出裝置之後，您就可以像平常一樣在這些裝置上執行動作。</span><span class="sxs-lookup"><span data-stu-id="9c123-179">After you've filtered the devices in your device list, you can perform actions on them as you normally would.</span></span> <span data-ttu-id="9c123-180">例如，您可以選取它們並指派設定、編輯其設定 (如果他們是 [團隊室]，請) 等等。</span><span class="sxs-lookup"><span data-stu-id="9c123-180">For example, you can select them and then assign configurations, edit their settings (if they're Teams Rooms devices), and so on.</span></span> <span data-ttu-id="9c123-181">完成後，您可以**選取 [標籤篩選]** 專案旁的**X** ，或選取清單右側的 [**全部清除**] 來移除篩選。</span><span class="sxs-lookup"><span data-stu-id="9c123-181">When you're done, you can remove the filter by selecting the **X**  next to the **Tag** filter entry or by selecting **Clear all** on the right side of the list.</span></span>
