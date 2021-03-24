---
title: 在商務用 Skype Server 中建立或修改呼叫識別碼簡報的轉譯規則
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
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 摘要：瞭解如何使用商務用 Skype Server 中的組建轉譯規則工具來定義轉譯規則。
ms.openlocfilehash: 3f4754184e69e7b574709d0272afc9989553cfe5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103639"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="74bd1-103">在商務用 Skype Server 中建立或修改呼叫識別碼簡報的轉譯規則</span><span class="sxs-lookup"><span data-stu-id="74bd1-103">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="74bd1-104">**摘要：** 瞭解如何使用商務用 Skype Server 中的組建轉譯規則工具來定義轉譯規則。</span><span class="sxs-lookup"><span data-stu-id="74bd1-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server.</span></span>

<span data-ttu-id="74bd1-105">若要定義轉譯規則，請在 [ **組建轉譯規則** ] 工具中輸入一組值，並啟用商務用 Skype Server 控制台，為您產生對應的相符模式和轉譯規則，以執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="74bd1-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="74bd1-106">或者，您可以手動寫入正則運算式，以定義符合的模式和轉譯規則。</span><span class="sxs-lookup"><span data-stu-id="74bd1-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="74bd1-107">如需詳細資訊，請參閱 [手動建立或修改轉譯規則](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-translation-rule-manually)。</span><span class="sxs-lookup"><span data-stu-id="74bd1-107">For details, see [Create or Modify a Translation Rule Manually](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-translation-rule-manually).</span></span>

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="74bd1-108">使用組建轉譯規則工具定義規則</span><span class="sxs-lookup"><span data-stu-id="74bd1-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="74bd1-109">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="74bd1-109">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="74bd1-110">若要開始定義轉譯規則，請依照在商務 [用 Skype server 中設定具有媒體旁路](configure-trunk-with-media-bypass.md) 功能的主幹中的步驟，或透過步驟9在 [商務用 Skype server 中設定沒有媒體旁路的主幹](configure-trunk-without-media-bypass.md) 。</span><span class="sxs-lookup"><span data-stu-id="74bd1-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="74bd1-111">在 [**新增轉譯規則**] 或 [**編輯轉譯規則**] 頁面的 [**名稱**] 下，輸入描述所轉譯之號碼模式的名稱。</span><span class="sxs-lookup"><span data-stu-id="74bd1-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="74bd1-112"> (選用) 在 [ **描述**] 底下，輸入轉譯規則的描述，例如美國國際長途撥號。</span><span class="sxs-lookup"><span data-stu-id="74bd1-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="74bd1-113">在對話方塊的 [ **組建轉譯規則** ] 區段中，于下欄欄位中輸入值：</span><span class="sxs-lookup"><span data-stu-id="74bd1-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>

   - <span data-ttu-id="74bd1-114">**開始位數**： (選用) 指定您想要模式比對的數位前置位數。</span><span class="sxs-lookup"><span data-stu-id="74bd1-114">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="74bd1-115">例如，在此欄位中輸入 [+]，以比對以 +) 開頭的 (164 格式的數位。</span><span class="sxs-lookup"><span data-stu-id="74bd1-115">For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>

   - <span data-ttu-id="74bd1-116">**Length**：指定比對模式中的位數，並選取是否要讓模式比對此長度的數位完全一致、至少此長度或任何長度。</span><span class="sxs-lookup"><span data-stu-id="74bd1-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="74bd1-117">例如，在下拉式清單中輸入11和 selectAt，以比對長度至少為11位數的數位。</span><span class="sxs-lookup"><span data-stu-id="74bd1-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>

   - <span data-ttu-id="74bd1-118">**要移除的位數**： (選用) 指定要移除的開始數位的數目。</span><span class="sxs-lookup"><span data-stu-id="74bd1-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="74bd1-119">例如，輸入1以從號碼的開頭去掉 +。</span><span class="sxs-lookup"><span data-stu-id="74bd1-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>

   - <span data-ttu-id="74bd1-120">**要新增的位數**： (選用) 指定要預先編號為已轉譯之數位的位數。</span><span class="sxs-lookup"><span data-stu-id="74bd1-120">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="74bd1-121">例如，如果您希望在套用規則時，將011預先加入翻譯的編號，請輸入011。</span><span class="sxs-lookup"><span data-stu-id="74bd1-121">For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>

     <span data-ttu-id="74bd1-122">您在這些欄位中輸入的值，會反映在 [ **要搭配的模式** ] 和 [ **轉譯規則** ] 欄位中。</span><span class="sxs-lookup"><span data-stu-id="74bd1-122">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields.</span></span> <span data-ttu-id="74bd1-123">例如，如果您指定前面的範例值，就會在 [ **要搭配的模式** ] 欄位中產生正則運算式：</span><span class="sxs-lookup"><span data-stu-id="74bd1-123">For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>

     <span data-ttu-id="74bd1-124">^\+ ( \d {9} \d +) $</span><span class="sxs-lookup"><span data-stu-id="74bd1-124">^\+(\d{9}\d+)$</span></span>

     <span data-ttu-id="74bd1-125">**轉譯規則** 欄位會指定轉譯後的數位格式的模式。</span><span class="sxs-lookup"><span data-stu-id="74bd1-125">The **Translation rule** field specifies a pattern for the format of translated numbers.</span></span> <span data-ttu-id="74bd1-126">這種模式分為兩個部分：</span><span class="sxs-lookup"><span data-stu-id="74bd1-126">This pattern has two parts:</span></span>

   - <span data-ttu-id="74bd1-127">值 (例如，$1) ，代表比對模式中的數位數目</span><span class="sxs-lookup"><span data-stu-id="74bd1-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>

   - <span data-ttu-id="74bd1-128"> (選用) 您可以在 [ **要加入的數位** ] 欄位中輸入值，以進行前置計算</span><span class="sxs-lookup"><span data-stu-id="74bd1-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>

     <span data-ttu-id="74bd1-129">使用上述範例值，011 $ 1 會出現在 **轉譯規則** 欄位中。</span><span class="sxs-lookup"><span data-stu-id="74bd1-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>

     <span data-ttu-id="74bd1-130">套用此轉譯規則時，+ 441235551010 會變成011441235551010。</span><span class="sxs-lookup"><span data-stu-id="74bd1-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

6. <span data-ttu-id="74bd1-131">按一下 **[確定]** 儲存轉譯規則。</span><span class="sxs-lookup"><span data-stu-id="74bd1-131">Click **OK** to save the translation rule.</span></span>

7. <span data-ttu-id="74bd1-132">按一下 **[確定]** 儲存主幹組態。</span><span class="sxs-lookup"><span data-stu-id="74bd1-132">Click **OK** to save the trunk configuration.</span></span>

8. <span data-ttu-id="74bd1-133">在 **[主幹組態]** 頁面上，按一下 **[認可]**，再按一下 **[全部認可]**。</span><span class="sxs-lookup"><span data-stu-id="74bd1-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="74bd1-134">當您建立或修改轉譯規則時，您都必須執行 [全部認可] 命令才能發行組態變更。</span><span class="sxs-lookup"><span data-stu-id="74bd1-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="74bd1-135">如需詳細資訊，請參閱 Operations 檔中的在 [商務用 Skype 中發佈待定的變更至語音路由](voice-route-config-changes.md) 設定。</span><span class="sxs-lookup"><span data-stu-id="74bd1-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="74bd1-136">若要手動定義轉譯規則</span><span class="sxs-lookup"><span data-stu-id="74bd1-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="74bd1-137">開啟商務用 Skype Server 控制台</span><span class="sxs-lookup"><span data-stu-id="74bd1-137">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="74bd1-138">若要開始定義轉譯規則，請依照在商務 [用 Skype server 中設定具有媒體旁路](configure-trunk-with-media-bypass.md) 功能的主幹中的步驟，或透過步驟9在 [商務用 Skype server 中設定沒有媒體旁路的主幹](configure-trunk-without-media-bypass.md) 。</span><span class="sxs-lookup"><span data-stu-id="74bd1-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="74bd1-139">在 **[新增轉譯規則]** 或 **[編輯轉譯規則]** 頁面的 **[名稱]** 欄位中，輸入可描述所轉譯號碼模式的名稱。</span><span class="sxs-lookup"><span data-stu-id="74bd1-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="74bd1-140"> (選用) 在 [ **描述**] 中，輸入轉譯規則的描述，例如美國國際長途撥號。</span><span class="sxs-lookup"><span data-stu-id="74bd1-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="74bd1-141">按一下 **[建置轉譯規則]** 區段底部的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="74bd1-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

6. <span data-ttu-id="74bd1-142">在 [輸入規則運算式] 中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="74bd1-142">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="74bd1-143">在 [符合此模式] 中，指定用來比對要轉譯之號碼的模式。</span><span class="sxs-lookup"><span data-stu-id="74bd1-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>

   - <span data-ttu-id="74bd1-144">在 [轉譯規則] 中，指定轉譯號碼的格式模式。</span><span class="sxs-lookup"><span data-stu-id="74bd1-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>

     <span data-ttu-id="74bd1-145">例如，如果您輸入 ^ \+ ( \d {9} \d +) $ In 符合 **轉譯規則** 中的 **此模式** and011 $ 1，則規則會將 + 441235551010 轉譯為011441235551010。</span><span class="sxs-lookup"><span data-stu-id="74bd1-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

7. <span data-ttu-id="74bd1-146">按一下 **[確定]** 儲存轉譯規則。</span><span class="sxs-lookup"><span data-stu-id="74bd1-146">Click **OK** to save the translation rule.</span></span>

8. <span data-ttu-id="74bd1-147">按一下 **[確定]** 儲存主幹組態。</span><span class="sxs-lookup"><span data-stu-id="74bd1-147">Click **OK** to save the trunk configuration.</span></span>

9. <span data-ttu-id="74bd1-148">在 **[主幹組態]** 頁面上，按一下 **[認可]**，再按一下 **[全部認可]**。</span><span class="sxs-lookup"><span data-stu-id="74bd1-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="74bd1-149">當您建立或修改轉譯規則時，您都必須執行 [全部認可] 命令才能發行組態變更。</span><span class="sxs-lookup"><span data-stu-id="74bd1-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="74bd1-150">如需詳細資訊，請參閱 Operations 檔中的在 [商務用 Skype 中發佈待定的變更至語音路由](voice-route-config-changes.md) 設定。</span><span class="sxs-lookup"><span data-stu-id="74bd1-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="74bd1-151">另請參閱</span><span class="sxs-lookup"><span data-stu-id="74bd1-151">See also</span></span>

[<span data-ttu-id="74bd1-152">在商務用 Skype Server 中設定含媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="74bd1-152">Configure a trunk with media bypass in Skype for Business Server</span></span>](configure-trunk-with-media-bypass.md)

[<span data-ttu-id="74bd1-153">在商務用 Skype Server 中設定無媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="74bd1-153">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="74bd1-154">在商務用 Skype 中將擱置的變更發佈至語音路由設定</span><span class="sxs-lookup"><span data-stu-id="74bd1-154">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="74bd1-155">在商務用 Skype Server 中部署媒體旁路</span><span class="sxs-lookup"><span data-stu-id="74bd1-155">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)