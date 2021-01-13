---
title: 在商務用 Skype 中建立或修改正規化規則
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 摘要：瞭解如何在商務用 Skype Server 中定義、建立及修改正常化規則。
ms.openlocfilehash: 6f8619304e9d3d801dfa430e6addb5105a2b82a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830763"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a><span data-ttu-id="e65eb-103">在商務用 Skype 中建立或修改正規化規則</span><span class="sxs-lookup"><span data-stu-id="e65eb-103">Create or modify a normalization rule in Skype for Business</span></span>

<span data-ttu-id="e65eb-104">**摘要：** 瞭解如何在商務用 Skype Server 中定義、建立及修改正規化規則。</span><span class="sxs-lookup"><span data-stu-id="e65eb-104">**Summary:** Learn how to define, create, and modify a normalization rule in Skype for Business Server.</span></span>

<span data-ttu-id="e65eb-105">在商務用 Skype Server 中定義、建立及修改正規化規則。</span><span class="sxs-lookup"><span data-stu-id="e65eb-105">Define, create, and modify normalization rules in Skype for Business Server.</span></span>

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="e65eb-106">使用組建正常化規則定義正規化規則</span><span class="sxs-lookup"><span data-stu-id="e65eb-106">To define a normalization rule by using Build a Normalization Rule</span></span>

1. <span data-ttu-id="e65eb-107">開啟商務用 Skype Server 控制台</span><span class="sxs-lookup"><span data-stu-id="e65eb-107">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="e65eb-108"> (選用) 請遵循下列步驟，以在 [商務用 Skype Server 中建立或修改撥號對應表中](dial-plans.md) 的步驟11或修改透過步驟 10 [的撥號](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) 對應表。</span><span class="sxs-lookup"><span data-stu-id="e65eb-108">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) through step 11 or [Modify a Dial Plan](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) through step 10.</span></span>

3. <span data-ttu-id="e65eb-109">在 [ **新增正規化規則** ] 或 [編輯正規化 **規則**] 中，輸入描述 [ **名稱** ] 中正規化的號碼模式的名稱 (例如，5DigitExtension) 。</span><span class="sxs-lookup"><span data-stu-id="e65eb-109">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example,5DigitExtension).</span></span>

4. <span data-ttu-id="e65eb-110"> (選用) 在 [ **描述**] 中，輸入正規化規則的描述 (例如，「轉譯5位數分機」 ) 。</span><span class="sxs-lookup"><span data-stu-id="e65eb-110">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="e65eb-111">在 [ **建立正規化規則**] 中，在下欄欄位中輸入值：</span><span class="sxs-lookup"><span data-stu-id="e65eb-111">In **Build a Normalization Rule**, enter values in the following fields:</span></span>

   - <span data-ttu-id="e65eb-112">**開始數位** (選用) 指定您想要模式符合的撥號號碼的前置位數。</span><span class="sxs-lookup"><span data-stu-id="e65eb-112">**Starting digits** (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="e65eb-113">例如，如果您希望模式比對從425開始的撥號號碼，請 type425。</span><span class="sxs-lookup"><span data-stu-id="e65eb-113">For example, type425 if you want the pattern to match dialed numbers beginning with 425.</span></span>

   - <span data-ttu-id="e65eb-114">**長度** 指定比對模式中的位數，然後選取是否要讓模式完全符合此長度、比對至少一個長度的撥號號碼，或比對任何長度的撥號號碼。</span><span class="sxs-lookup"><span data-stu-id="e65eb-114">**Length** Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>

   - <span data-ttu-id="e65eb-115">**移除的位數** (選用) 指定您想要模式比對的撥號號碼中所要移除的開始數位的數目。</span><span class="sxs-lookup"><span data-stu-id="e65eb-115">**Digits to remove** (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>

   - <span data-ttu-id="e65eb-116">**要** 新增 (選用的位數) 指定要新增至撥號號碼的數位，使其符合模式。</span><span class="sxs-lookup"><span data-stu-id="e65eb-116">**Digits to add** (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>

     <span data-ttu-id="e65eb-117">您在這些欄位中輸入的值會反映在模式中， **以符合** 和 **轉譯規則**。</span><span class="sxs-lookup"><span data-stu-id="e65eb-117">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="e65eb-118">例如，如果您保留空白的 **開始位數** ，請 type7 至 [ **長度** ] 欄位並選取 [ **完全**]，並指定 **要移除的位數** 為0， **模式** 中所產生的正則運算式會比對：</span><span class="sxs-lookup"><span data-stu-id="e65eb-118">For example, if you leave **Starting digits** empty, type7 into the **Length** field and select **Exactly**, and specify 0 in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>

     <span data-ttu-id="e65eb-119">^ ( \d {7}) $</span><span class="sxs-lookup"><span data-stu-id="e65eb-119">^(\d{7})$</span></span>

6. <span data-ttu-id="e65eb-120">在 [ **轉譯規則**] 中，指定轉譯的 e.164 電話號碼格式的模式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e65eb-120">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>

   - <span data-ttu-id="e65eb-121">代表匹配模式中指定之位數的值。</span><span class="sxs-lookup"><span data-stu-id="e65eb-121">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="e65eb-122">例如，如果相符的模式是 ^ ( \d {7}) $ 之後的轉譯規則代表7位數撥打的號碼。</span><span class="sxs-lookup"><span data-stu-id="e65eb-122">For example, if the matching pattern is ^(\d{7})$ then$1 in the translation rule represents 7-digit dialed numbers.</span></span>

   - <span data-ttu-id="e65eb-123"> (選用) 在 [ **要新增的位數** ] 欄位中輸入值，以指定要附加到已轉譯之數位的位數 (例如，+ 1425) 。</span><span class="sxs-lookup"><span data-stu-id="e65eb-123">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example,+1425).</span></span>

     <span data-ttu-id="e65eb-124">例如，如果 **要比對的模式** 包含 ^ ( \d {7}) $ 做為撥打號碼和 **轉譯規則** 的模式，包含 + 1425 $ 1 做為 e.164 電話號碼的模式，規則會將5550100標準化為 + 14255550100。</span><span class="sxs-lookup"><span data-stu-id="e65eb-124">For example, if **Pattern to match** contains^(\d{7})$ as the pattern for dialed numbers and **Translation rule** contains+1425$1 as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="e65eb-125"> (選用) 如果正規化規則會產生您組織內部的電話號碼，請選取 [ **內部分機**]。</span><span class="sxs-lookup"><span data-stu-id="e65eb-125">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="e65eb-126"> (選用) 請輸入號碼以測試正規化規則，然後按一下 [ **移至**]。</span><span class="sxs-lookup"><span data-stu-id="e65eb-126">(Optional) Enter a number to test the normalization rule, and then click **Go**.</span></span> <span data-ttu-id="e65eb-127">測試結果會顯示在 [ **輸入要測試的號碼**] 底下。</span><span class="sxs-lookup"><span data-stu-id="e65eb-127">The test results are displayed under **Enter a number to test**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e65eb-128">您可以儲存尚未通過測試的正規化規則，然後稍後再加以重新設定。</span><span class="sxs-lookup"><span data-stu-id="e65eb-128">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="e65eb-129">如需詳細資訊，請參閱＜[Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx)＞。</span><span class="sxs-lookup"><span data-stu-id="e65eb-129">For details, see [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span>

9. <span data-ttu-id="e65eb-130">按一下 **[確定]** 儲存正規化規則。</span><span class="sxs-lookup"><span data-stu-id="e65eb-130">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="e65eb-131">按一下 **[確定]** 儲存撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="e65eb-131">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="e65eb-132">在 [ **撥號** 對應表] 頁面上，按一下 [ **認可**]，然後按一下 [ **全部認可**]。</span><span class="sxs-lookup"><span data-stu-id="e65eb-132">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e65eb-133">當您建立或變更正規化規則時，您必須執行 [ **全部認可** ] 命令來發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="e65eb-133">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="e65eb-134">如需詳細資訊，請參閱 Operations 檔中的在 [商務用 Skype 中發佈待定的變更至語音路由](voice-route-config-changes.md) 設定。</span><span class="sxs-lookup"><span data-stu-id="e65eb-134">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="e65eb-135">手動定義正常化規則</span><span class="sxs-lookup"><span data-stu-id="e65eb-135">To define a normalization rule manually</span></span>

1. <span data-ttu-id="e65eb-136">開啟商務用 Skype Server 控制台</span><span class="sxs-lookup"><span data-stu-id="e65eb-136">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="e65eb-137"> (選用) 依照在商務用 [Skype Server 中建立或修改撥號對應](dial-plans.md)表中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="e65eb-137">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md).</span></span>

3. <span data-ttu-id="e65eb-138">在 [ **新增正常化規則** ] 或 [ **編輯正規化規則**] 中，輸入描述 [ **名稱** ] 中正規化的號碼模式的名稱 (例如，將正規化 rule5DigitExtension) 命名為 name。</span><span class="sxs-lookup"><span data-stu-id="e65eb-138">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule5DigitExtension).</span></span>

4. <span data-ttu-id="e65eb-139"> (選用) 在 [ **描述** ] 欄位中，輸入正規化規則的描述 (例如，「轉譯5位數分機」 ) 。</span><span class="sxs-lookup"><span data-stu-id="e65eb-139">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="e65eb-140">在 [ **建立正常化規則**] 中，按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="e65eb-140">In **Build a Normalization Rule**, click **Edit**.</span></span>

6. <span data-ttu-id="e65eb-141">在 [輸入規則運算式] 中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="e65eb-141">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="e65eb-142">在 [ **符合此模式**] 中，指定您要用來比對撥號電話號碼的模式。</span><span class="sxs-lookup"><span data-stu-id="e65eb-142">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>

   - <span data-ttu-id="e65eb-143">在 [ **轉譯規則**] 中，指定轉譯的 e.164 電話號碼格式的模式。</span><span class="sxs-lookup"><span data-stu-id="e65eb-143">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>

     <span data-ttu-id="e65eb-144">例如，如果您輸入 ^ ( \d {7}) $ In **符合此模式** ，並在 **轉譯規則** 中的 + 1425 $ 1，則此規則會將5550100標準化為 + 14255550100。</span><span class="sxs-lookup"><span data-stu-id="e65eb-144">For example, if you enter ^(\d{7})$ in **Match this pattern** and+1425$1 in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="e65eb-145"> (選用) 如果正規化規則會產生您組織內部的電話號碼，請選取 [ **內部分機**]。</span><span class="sxs-lookup"><span data-stu-id="e65eb-145">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="e65eb-146"> (選用) 請輸入數位以測試正規化規則，然後按一下 [ **移至**]。</span><span class="sxs-lookup"><span data-stu-id="e65eb-146">(Optional) Enter a number to test the normalization rule and then click **Go**.</span></span> <span data-ttu-id="e65eb-147">測試結果會顯示在 [ **輸入要測試的號碼**] 底下。</span><span class="sxs-lookup"><span data-stu-id="e65eb-147">The test results are displayed under **Enter a number to test**.</span></span>

9. <span data-ttu-id="e65eb-148">按一下 **[確定]** 儲存正規化規則。</span><span class="sxs-lookup"><span data-stu-id="e65eb-148">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="e65eb-149">按一下 **[確定]** 儲存撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="e65eb-149">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="e65eb-150">在 [ **撥號** 對應表] 頁面上，按一下 [ **認可**]，然後按一下 [ **全部認可**]。</span><span class="sxs-lookup"><span data-stu-id="e65eb-150">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e65eb-151">當您建立或變更正規化規則時，您必須執行 [ **全部認可** ] 命令來發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="e65eb-151">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="e65eb-152">如需詳細資訊，請參閱 Operations 檔中的在 [商務用 Skype 中發佈待定的變更至語音路由](voice-route-config-changes.md) 設定。</span><span class="sxs-lookup"><span data-stu-id="e65eb-152">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>


