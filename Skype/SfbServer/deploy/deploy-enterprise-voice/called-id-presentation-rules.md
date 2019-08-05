---
title: 在商務用 Skype Server 中建立或修改呼叫 ID 簡報的翻譯規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: '摘要: 瞭解如何使用商務用 Skype Server 中的 [建立翻譯規則] 工具來定義翻譯規則。'
ms.openlocfilehash: 13e89fd836c971085a3a1fc40b7e60793e10eb68
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187432"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="565dc-103">在商務用 Skype Server 中建立或修改呼叫 ID 簡報的翻譯規則</span><span class="sxs-lookup"><span data-stu-id="565dc-103">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="565dc-104">**摘要:** 瞭解如何使用商務用 Skype Server 中的 [建立翻譯規則] 工具來定義翻譯規則。</span><span class="sxs-lookup"><span data-stu-id="565dc-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server.</span></span>

<span data-ttu-id="565dc-105">如果您想要定義翻譯規則, 請在 [**建立翻譯規則**] 工具中輸入一組值, 並啟用商務用 Skype Server [控制台], 為您產生對應的相符模式與翻譯規則, 以執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="565dc-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="565dc-106">或者, 您也可以手動寫入正則運算式, 以定義相符的模式和轉換規則。</span><span class="sxs-lookup"><span data-stu-id="565dc-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="565dc-107">如需詳細資訊, 請參閱[手動建立或修改翻譯規則](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx)。</span><span class="sxs-lookup"><span data-stu-id="565dc-107">For details, see [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span></span>

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="565dc-108">使用 [建立翻譯規則] 工具定義規則</span><span class="sxs-lookup"><span data-stu-id="565dc-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="565dc-109">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="565dc-109">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="565dc-110">若要開始定義翻譯規則, 請遵循在[商務用 Skype server 中的 [透過媒體旁路媒體來設定主幹](configure-trunk-with-media-bypass.md)] 中的步驟, 或在 [商務用 skype 伺服器] 中的 [透過步驟 9][設定主幹, 不需媒體旁路](configure-trunk-without-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="565dc-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="565dc-111">在 [**新增翻譯規則**] 或 [**編輯翻譯規則**] 頁面上的 [**名稱**] 底下, 輸入描述所翻譯之數位模式的名稱。</span><span class="sxs-lookup"><span data-stu-id="565dc-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="565dc-112">可選在 [**描述**] 底下, 輸入翻譯規則的描述, 例如美國國際長途撥號。</span><span class="sxs-lookup"><span data-stu-id="565dc-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="565dc-113">在對話方塊的 [**建立翻譯規則**] 區段中, 于下欄欄位中輸入值:</span><span class="sxs-lookup"><span data-stu-id="565dc-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>

   - <span data-ttu-id="565dc-114">**起始位數**: (選擇性) 指定您想要模式符合的前置數位數位。</span><span class="sxs-lookup"><span data-stu-id="565dc-114">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="565dc-115">例如, 在這個欄位中輸入 [+], 就會以 E. 164 格式 (開頭為 +) 來相符數位。</span><span class="sxs-lookup"><span data-stu-id="565dc-115">For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>

   - <span data-ttu-id="565dc-116">**長度**: 指定 [相符] 模式中的位數, 並選取您想要模式與此長度完全相同、至少為此長度或任何長度。</span><span class="sxs-lookup"><span data-stu-id="565dc-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="565dc-117">例如, 在下拉式清單中輸入11及 selectAt, 以符合長度至少為11位數的數位。</span><span class="sxs-lookup"><span data-stu-id="565dc-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>

   - <span data-ttu-id="565dc-118">**要移除的位數**: (選用) 指定要移除的起始位數數。</span><span class="sxs-lookup"><span data-stu-id="565dc-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="565dc-119">例如, 輸入1來去掉數位開頭的 +。</span><span class="sxs-lookup"><span data-stu-id="565dc-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>

   - <span data-ttu-id="565dc-120">**要加上的位數**: (選擇性) 指定要在已翻譯數位前加上的數位。</span><span class="sxs-lookup"><span data-stu-id="565dc-120">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="565dc-121">例如, 如果您想要在套用規則時將011附加到已翻譯的編號中, 請輸入011。</span><span class="sxs-lookup"><span data-stu-id="565dc-121">For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>

     <span data-ttu-id="565dc-122">您在這些欄位中輸入的值會反映在 [相符] 與 [**翻譯規則**] 欄位的**模式**中。</span><span class="sxs-lookup"><span data-stu-id="565dc-122">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields.</span></span> <span data-ttu-id="565dc-123">例如, 如果您指定前面的範例值, 則在 [模式] 中產生的正則運算式會與 field**相符**:</span><span class="sxs-lookup"><span data-stu-id="565dc-123">For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>

     <span data-ttu-id="565dc-124">^\+(\d{9}\d +) $</span><span class="sxs-lookup"><span data-stu-id="565dc-124">^\+(\d{9}\d+)$</span></span>

     <span data-ttu-id="565dc-125">[**翻譯規則**] 欄位會指定已翻譯數位格式的模式。</span><span class="sxs-lookup"><span data-stu-id="565dc-125">The **Translation rule** field specifies a pattern for the format of translated numbers.</span></span> <span data-ttu-id="565dc-126">此模式有兩個部分:</span><span class="sxs-lookup"><span data-stu-id="565dc-126">This pattern has two parts:</span></span>

   - <span data-ttu-id="565dc-127">代表 [相符] 模式中之位數的值 (例如, $1)</span><span class="sxs-lookup"><span data-stu-id="565dc-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>

   - <span data-ttu-id="565dc-128">可選您可以在 [**要新增的數位**] 欄位中輸入的值。</span><span class="sxs-lookup"><span data-stu-id="565dc-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>

     <span data-ttu-id="565dc-129">使用上述範例值, 011 $ 1 會出現在 [**翻譯規則**] 欄位中。</span><span class="sxs-lookup"><span data-stu-id="565dc-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>

     <span data-ttu-id="565dc-130">套用此翻譯規則時, + 441235551010 會變成011441235551010。</span><span class="sxs-lookup"><span data-stu-id="565dc-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

6. <span data-ttu-id="565dc-131">按一下 **[確定]** 儲存翻譯規則。</span><span class="sxs-lookup"><span data-stu-id="565dc-131">Click **OK** to save the translation rule.</span></span>

7. <span data-ttu-id="565dc-132">按一下 **[確定]** 以儲存幹線設定。</span><span class="sxs-lookup"><span data-stu-id="565dc-132">Click **OK** to save the trunk configuration.</span></span>

8. <span data-ttu-id="565dc-133">在 [**幹線**設定] 頁面上, 按一下 [**認可**], 然後按一下 [**全部確認**]。</span><span class="sxs-lookup"><span data-stu-id="565dc-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="565dc-134">每當您建立或修改翻譯規則時, 您必須執行 [**全部提交**] 命令才能發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="565dc-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="565dc-135">如需詳細資訊, 請參閱在作業檔中[發佈商務用 Skype 中的語音路由設定的待處理變更](voice-route-config-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="565dc-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="565dc-136">手動定義翻譯規則</span><span class="sxs-lookup"><span data-stu-id="565dc-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="565dc-137">開啟商務用 Skype Server 的 [控制台]</span><span class="sxs-lookup"><span data-stu-id="565dc-137">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="565dc-138">若要開始定義翻譯規則, 請遵循在[商務用 Skype server 中的 [透過媒體旁路媒體來設定主幹](configure-trunk-with-media-bypass.md)] 中的步驟, 或在 [商務用 skype 伺服器] 中的 [透過步驟 9][設定主幹, 不需媒體旁路](configure-trunk-without-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="565dc-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="565dc-139">在 [**新增翻譯規則**] 或 [**編輯翻譯規則**] 頁面上的 [**名稱**] 欄位中, 輸入描述所翻譯之數位模式的名稱。</span><span class="sxs-lookup"><span data-stu-id="565dc-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="565dc-140">可選在 [**描述**] 中, 輸入翻譯規則的描述, 例如美國國際長途撥號。</span><span class="sxs-lookup"><span data-stu-id="565dc-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="565dc-141">按一下 [**組建翻譯規則**] 區段底部的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="565dc-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

6. <span data-ttu-id="565dc-142">在 [輸入**正則運算式**] 中輸入下列內容:</span><span class="sxs-lookup"><span data-stu-id="565dc-142">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="565dc-143">在 [**符合這個模式**] 中, 指定將用來符合要翻譯之數位的模式。</span><span class="sxs-lookup"><span data-stu-id="565dc-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>

   - <span data-ttu-id="565dc-144">在**翻譯規則**中, 指定翻譯數位格式的模式。</span><span class="sxs-lookup"><span data-stu-id="565dc-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>

     <span data-ttu-id="565dc-145">例如,\+如果您在**翻譯規則**中輸入{9}^ (\d \d +) $**與此模式**and011 $ 1, 規則會將 + 441235551010 轉換為011441235551010。</span><span class="sxs-lookup"><span data-stu-id="565dc-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

7. <span data-ttu-id="565dc-146">按一下 **[確定]** 儲存翻譯規則。</span><span class="sxs-lookup"><span data-stu-id="565dc-146">Click **OK** to save the translation rule.</span></span>

8. <span data-ttu-id="565dc-147">按一下 **[確定]** 以儲存幹線設定。</span><span class="sxs-lookup"><span data-stu-id="565dc-147">Click **OK** to save the trunk configuration.</span></span>

9. <span data-ttu-id="565dc-148">在 [**幹線**設定] 頁面上, 按一下 [**認可**], 然後按一下 [**全部確認**]。</span><span class="sxs-lookup"><span data-stu-id="565dc-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="565dc-149">每當您建立或修改翻譯規則時, 您必須執行 [**全部提交**] 命令才能發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="565dc-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="565dc-150">如需詳細資訊, 請參閱在作業檔中[發佈商務用 Skype 中的語音路由設定的待處理變更](voice-route-config-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="565dc-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="565dc-151">另請參閱</span><span class="sxs-lookup"><span data-stu-id="565dc-151">See also</span></span>

<span data-ttu-id="565dc-152">[在商務用 Skype Server 中使用 [旁路媒體] 設定主幹](configure-trunk-with-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="565dc-152">[Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md)</span></span>

[<span data-ttu-id="565dc-153">在商務用 Skype Server 中設定不使用媒體的主幹</span><span class="sxs-lookup"><span data-stu-id="565dc-153">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

<span data-ttu-id="565dc-154">[在商務用 Skype 中發佈 [語音路由設定] 的擱置變更](voice-route-config-changes.md)</span><span class="sxs-lookup"><span data-stu-id="565dc-154">[Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md)</span></span>

[<span data-ttu-id="565dc-155">在商務用 Skype Server 中部署媒體旁路</span><span class="sxs-lookup"><span data-stu-id="565dc-155">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

