---
title: 在商務用 Skype 中建立或修改正常化規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: c206bd20c02053f4e3775f32b1ba61000bb59a63
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767086"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a><span data-ttu-id="cebaa-103">在商務用 Skype 中建立或修改正常化規則</span><span class="sxs-lookup"><span data-stu-id="cebaa-103">Create or modify a normalization rule in Skype for Business</span></span>

<span data-ttu-id="cebaa-104">**摘要：** 瞭解如何在商務用 Skype Server 中定義、建立及修改正常化規則。</span><span class="sxs-lookup"><span data-stu-id="cebaa-104">**Summary:** Learn how to define, create, and modify a normalization rule in Skype for Business Server.</span></span>

<span data-ttu-id="cebaa-105">在商務用 Skype Server 中定義、建立及修改正常化規則。</span><span class="sxs-lookup"><span data-stu-id="cebaa-105">Define, create, and modify normalization rules in Skype for Business Server.</span></span>

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="cebaa-106">使用組建正常化規則定義正常化規則</span><span class="sxs-lookup"><span data-stu-id="cebaa-106">To define a normalization rule by using Build a Normalization Rule</span></span>

1. <span data-ttu-id="cebaa-107">開啟商務用 Skype Server 的 [控制台]</span><span class="sxs-lookup"><span data-stu-id="cebaa-107">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="cebaa-108">可選請依照步驟11中的[商務用 Skype Server 建立或修改撥號方案](dial-plans.md)中的步驟操作，或透過步驟 10[修改撥號計畫](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx)。</span><span class="sxs-lookup"><span data-stu-id="cebaa-108">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) through step 11 or [Modify a Dial Plan](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) through step 10.</span></span>

3. <span data-ttu-id="cebaa-109">在**新的 [正常化規則**] 或 [**編輯正常化規則**] 中，輸入一個名稱，以在**名稱**中描述正常化的數位模式（例如，5DigitExtension）。</span><span class="sxs-lookup"><span data-stu-id="cebaa-109">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example,5DigitExtension).</span></span>

4. <span data-ttu-id="cebaa-110">可選在 [**描述**] 中，輸入正常化規則的描述（例如，"轉譯5位數的延伸"）。</span><span class="sxs-lookup"><span data-stu-id="cebaa-110">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="cebaa-111">在 [**建立正常化規則**] 中，于下欄欄位中輸入值：</span><span class="sxs-lookup"><span data-stu-id="cebaa-111">In **Build a Normalization Rule**, enter values in the following fields:</span></span>

   - <span data-ttu-id="cebaa-112">**起始位數**（選用）指定您想要模式符合的撥號號碼的前導位數。</span><span class="sxs-lookup"><span data-stu-id="cebaa-112">**Starting digits** (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="cebaa-113">例如，如果您想要讓模式搭配從425開始的撥入號碼相符，請 type425。</span><span class="sxs-lookup"><span data-stu-id="cebaa-113">For example, type425 if you want the pattern to match dialed numbers beginning with 425.</span></span>

   - <span data-ttu-id="cebaa-114">**長度**在 [相符] 模式中指定位數，然後選取您想要模式完全符合這個長度、與至少有此長度的撥入號碼相符，或與任何長度的撥入號碼相符。</span><span class="sxs-lookup"><span data-stu-id="cebaa-114">**Length** Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>

   - <span data-ttu-id="cebaa-115">**要移除的數位**（選擇性）指定要從撥打的號碼中移除的起始位數，您想要讓模式符合該數位。</span><span class="sxs-lookup"><span data-stu-id="cebaa-115">**Digits to remove** (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>

   - <span data-ttu-id="cebaa-116">**要加**上的位數（選擇性）指定要在撥打的號碼中加上您想要模式相符的數位。</span><span class="sxs-lookup"><span data-stu-id="cebaa-116">**Digits to add** (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>

     <span data-ttu-id="cebaa-117">您在這些欄位中輸入的值會反映在模式中，**以符合**與**翻譯規則**。</span><span class="sxs-lookup"><span data-stu-id="cebaa-117">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="cebaa-118">例如，如果您保留的**起始位數**為空白，請 type7 到 [**長度**] 欄位中，然後選取 [**完全**]，並指定**要移除**的 [0]，結果是**要與之相符**的正則運算式如下所示：</span><span class="sxs-lookup"><span data-stu-id="cebaa-118">For example, if you leave **Starting digits** empty, type7 into the **Length** field and select **Exactly**, and specify 0 in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>

     <span data-ttu-id="cebaa-119">^ （\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="cebaa-119">^(\d{7})$</span></span>

6. <span data-ttu-id="cebaa-120">在**翻譯規則**中，指定翻譯的 e. 164 電話號碼格式的模式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cebaa-120">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>

   - <span data-ttu-id="cebaa-121">代表 [相符] 模式中指定之位數的值。</span><span class="sxs-lookup"><span data-stu-id="cebaa-121">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="cebaa-122">例如，如果相符的模式是 ^ （\d{7}） $，則翻譯規則中的 $ 1 則代表7位數的撥入號碼。</span><span class="sxs-lookup"><span data-stu-id="cebaa-122">For example, if the matching pattern is ^(\d{7})$ then$1 in the translation rule represents 7-digit dialed numbers.</span></span>

   - <span data-ttu-id="cebaa-123">可選在 [位數] 中輸入一個值，以指定要在已翻譯數位前**加**上的位數（例如 + 1425）。</span><span class="sxs-lookup"><span data-stu-id="cebaa-123">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example,+1425).</span></span>

     <span data-ttu-id="cebaa-124">例如，如果**要搭配的模式**包含 ^ （\d{7}） $ 做為撥入號碼和**翻譯規則**的模式，包含 + 1425 $ 1 做為 e.i 電話號碼的模式，規則會將5550100標準化至 + 14255550100。</span><span class="sxs-lookup"><span data-stu-id="cebaa-124">For example, if **Pattern to match** contains^(\d{7})$ as the pattern for dialed numbers and **Translation rule** contains+1425$1 as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="cebaa-125">可選如果正常化規則所產生的是貴組織內部的電話號碼，請選取 [**內部擴充**]。</span><span class="sxs-lookup"><span data-stu-id="cebaa-125">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="cebaa-126">可選輸入數位以測試正常化規則，**然後按一下 [** 執行]。</span><span class="sxs-lookup"><span data-stu-id="cebaa-126">(Optional) Enter a number to test the normalization rule, and then click **Go**.</span></span> <span data-ttu-id="cebaa-127">測試結果會顯示在 [**輸入要測試的號碼**] 下。</span><span class="sxs-lookup"><span data-stu-id="cebaa-127">The test results are displayed under **Enter a number to test**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cebaa-128">您可以儲存尚未經過測試的正常化規則，稍後再重新設定。</span><span class="sxs-lookup"><span data-stu-id="cebaa-128">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="cebaa-129">如需詳細資訊，請參閱[測試語音路由](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="cebaa-129">For details, see [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span>

9. <span data-ttu-id="cebaa-130">按一下 **[確定]** 以儲存正常化規則。</span><span class="sxs-lookup"><span data-stu-id="cebaa-130">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="cebaa-131">按一下 **[確定]** 儲存撥號計畫。</span><span class="sxs-lookup"><span data-stu-id="cebaa-131">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="cebaa-132">在 [**撥號方案**] 頁面上，按一下 [**認可**]，然後按一下 [**全部提交**]。</span><span class="sxs-lookup"><span data-stu-id="cebaa-132">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cebaa-133">每當您建立或變更正常化規則時，您必須執行 [**全部提交**] 命令才能發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="cebaa-133">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="cebaa-134">如需詳細資訊，請參閱在作業檔中[發佈商務用 Skype 中的語音路由設定的待處理變更](voice-route-config-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="cebaa-134">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="cebaa-135">手動定義正常化規則</span><span class="sxs-lookup"><span data-stu-id="cebaa-135">To define a normalization rule manually</span></span>

1. <span data-ttu-id="cebaa-136">開啟商務用 Skype Server 的 [控制台]</span><span class="sxs-lookup"><span data-stu-id="cebaa-136">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="cebaa-137">可選遵循在商務用[Skype Server 中建立或修改撥號計畫](dial-plans.md)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="cebaa-137">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md).</span></span>

3. <span data-ttu-id="cebaa-138">在 [**新增正常化規則**] 或 [**編輯正常化規則**] 中，輸入描述**名稱**中要正常化之數位模式的名稱（例如，將正常化 rule5DigitExtension 命名）。</span><span class="sxs-lookup"><span data-stu-id="cebaa-138">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule5DigitExtension).</span></span>

4. <span data-ttu-id="cebaa-139">可選在 [**描述**] 欄位中，輸入正常化規則的描述（例如，「轉譯5位數的延伸」）。</span><span class="sxs-lookup"><span data-stu-id="cebaa-139">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="cebaa-140">在 [**建立正常化規則**] 中，按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="cebaa-140">In **Build a Normalization Rule**, click **Edit**.</span></span>

6. <span data-ttu-id="cebaa-141">在 [輸入**正則運算式**] 中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="cebaa-141">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="cebaa-142">在 [**符合這個模式**] 中，指定您要用來與撥打的電話號碼相符的模式。</span><span class="sxs-lookup"><span data-stu-id="cebaa-142">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>

   - <span data-ttu-id="cebaa-143">在 [**翻譯規則**] 中，指定翻譯的 e. （164個電話號碼）格式的模式。</span><span class="sxs-lookup"><span data-stu-id="cebaa-143">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>

     <span data-ttu-id="cebaa-144">例如，如果您在**翻譯規則**中輸入{7}^ （\d） $ 與**此模式搭配**+ 1425 $ 1，規則會將5550100標準化至 + 14255550100。</span><span class="sxs-lookup"><span data-stu-id="cebaa-144">For example, if you enter ^(\d{7})$ in **Match this pattern** and+1425$1 in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="cebaa-145">可選如果正常化規則所產生的是貴組織內部的電話號碼，請選取 [**內部擴充**]。</span><span class="sxs-lookup"><span data-stu-id="cebaa-145">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="cebaa-146">可選輸入數位以測試正常化規則，**然後按一下 [** 執行]。</span><span class="sxs-lookup"><span data-stu-id="cebaa-146">(Optional) Enter a number to test the normalization rule and then click **Go**.</span></span> <span data-ttu-id="cebaa-147">測試結果會顯示在 [**輸入要測試的號碼**] 下。</span><span class="sxs-lookup"><span data-stu-id="cebaa-147">The test results are displayed under **Enter a number to test**.</span></span>

9. <span data-ttu-id="cebaa-148">按一下 **[確定]** 以儲存正常化規則。</span><span class="sxs-lookup"><span data-stu-id="cebaa-148">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="cebaa-149">按一下 **[確定]** 儲存撥號計畫。</span><span class="sxs-lookup"><span data-stu-id="cebaa-149">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="cebaa-150">在 [**撥號方案**] 頁面上，按一下 [**認可**]，然後按一下 [**全部提交**]。</span><span class="sxs-lookup"><span data-stu-id="cebaa-150">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cebaa-151">每當您建立或變更正常化規則時，您必須執行 [**全部提交**] 命令才能發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="cebaa-151">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="cebaa-152">如需詳細資訊，請參閱在作業檔中[發佈商務用 Skype 中的語音路由設定的待處理變更](voice-route-config-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="cebaa-152">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>


