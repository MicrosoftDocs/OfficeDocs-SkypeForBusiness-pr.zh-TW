---
title: 在商務用 Skype 中建立或修改語音路由
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
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: 摘要：瞭解如何使用商務用 Skype Server 控制台建立或修改商務用 Skype Server 中的語音路由。
ms.openlocfilehash: c6f1e50971551866cfa6cb12eb6a259ac2f932f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105839"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a><span data-ttu-id="f8882-103">在商務用 Skype 中建立或修改語音路由</span><span class="sxs-lookup"><span data-stu-id="f8882-103">Create or modify a voice route in Skype for Business</span></span>
 
<span data-ttu-id="f8882-104">**摘要：** 瞭解如何使用商務用 Skype Server 控制台建立或修改商務用 Skype Server 中的語音路由。</span><span class="sxs-lookup"><span data-stu-id="f8882-104">**Summary:** Learn how to create or modify a voice route in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a><span data-ttu-id="f8882-105">使用商務用 Skype Server 控制台建立語音路由</span><span class="sxs-lookup"><span data-stu-id="f8882-105">To create a voice route by using the Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f8882-106">以 RTCUniversalServerAdmins 群組成員的身分，或是 **CsVoiceAdministrator**、 **CsServerAdministrator** 或 **CsAdministrator** 系統管理角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="f8882-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="f8882-107">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="f8882-107">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f8882-108">在左導覽列中，按一下 **[語音路由]**。</span><span class="sxs-lookup"><span data-stu-id="f8882-108">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="f8882-109">按一下 **[路由]**。</span><span class="sxs-lookup"><span data-stu-id="f8882-109">Click **Route**.</span></span>
    
5. <span data-ttu-id="f8882-110">按一下 [ **新增** ] 顯示 [ **新增語音路由** ] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="f8882-110">Click **New** to display the **New Voice Route** dialog box.</span></span>
    
6. <span data-ttu-id="f8882-111">在 [ **名稱**] 中，輸入語音路由的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="f8882-111">In **Name**, type a descriptive name for the voice route.</span></span>
    
7. <span data-ttu-id="f8882-112"> (選用) 在 [ **描述**] 中，輸入語音路由的其他描述性資訊。</span><span class="sxs-lookup"><span data-stu-id="f8882-112">(Optional) In **Description**, type additional descriptive information for the voice route.</span></span>
    
8. <span data-ttu-id="f8882-113">若要指定您想要此路由容納的模式，您可以使用 **Build a pattern to match** tool 以產生正則運算式，或是手動寫入正則運算式。</span><span class="sxs-lookup"><span data-stu-id="f8882-113">To specify the patterns that you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
   - <span data-ttu-id="f8882-114">若要使用 **Build a pattern to match** tool 以產生正則運算式，請輸入下列的值。</span><span class="sxs-lookup"><span data-stu-id="f8882-114">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows.</span></span> <span data-ttu-id="f8882-115">您可以指定兩種類型的模式對應：</span><span class="sxs-lookup"><span data-stu-id="f8882-115">You can specify two types of pattern matching:</span></span>
    
   - <span data-ttu-id="f8882-116">**您想要允許的數位的開始位數**：輸入此路由必須滿足的首碼值 (包括前置 + （如果需要）) 。</span><span class="sxs-lookup"><span data-stu-id="f8882-116">**Starting digits for numbers that you want to allow**: Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="f8882-117">例如，輸入 + 425，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="f8882-117">For example, type +425, and then click **Add**.</span></span> <span data-ttu-id="f8882-118">針對您想要包含在路由中的每個前置詞值，重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="f8882-118">Repeat this for each prefix value that you want to include in the route.</span></span>
    
   - <span data-ttu-id="f8882-119">**例外** 狀況：如果您想要為前置詞值指定一或多個例外狀況，請反白顯示首碼，然後按一下 [ **例外** 狀況]。</span><span class="sxs-lookup"><span data-stu-id="f8882-119">**Exceptions**: If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="f8882-120">針對您  *不*  想要此路由容納的相符模式輸入一個或多個值。</span><span class="sxs-lookup"><span data-stu-id="f8882-120">Type in one or more values for the matching patterns that you do  *not*  want this route to accommodate.</span></span> <span data-ttu-id="f8882-121">例如，若要從路由中排除從 + 425237 開始的數位，請在 [ **例外日期** ] 欄位中輸入 [+ 425237] 的值，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f8882-121">For example, to exclude numbers starting with +425237 from the route, enter a value of+425237 in the **Exceptions** field, and then click **OK**.</span></span>
    
   - <span data-ttu-id="f8882-122">若要手動定義相符的模式，請按一下 [**組建要搭配的模式**] 中的 [**編輯**]，然後輸入 .net Framework 正則運算式，以指定要套用路由之目的地電話號碼的相符模式。</span><span class="sxs-lookup"><span data-stu-id="f8882-122">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="f8882-123">如需如何撰寫正則運算式的詳細資訊，請參閱「 [.Net Framework 正則運算式](/dotnet/standard/base-types/regular-expressions)」。</span><span class="sxs-lookup"><span data-stu-id="f8882-123">For details about how to write regular expressions, see [".NET Framework Regular Expressions"](/dotnet/standard/base-types/regular-expressions).</span></span> 
    
9. <span data-ttu-id="f8882-124">如果您不想讓撥出電話的電話號碼對來電收件者顯示，請選取 [ **抑制來電者識別碼** ]。</span><span class="sxs-lookup"><span data-stu-id="f8882-124">Select **Suppress caller ID** if you do not want the ID of the phone making the outbound call to appear to the call recipient.</span></span> <span data-ttu-id="f8882-125">如果您選取此選項，則必須指定要在收件者的來電者 ID 顯示上顯示的 **替代來電者識別碼** 。</span><span class="sxs-lookup"><span data-stu-id="f8882-125">If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient's caller ID display.</span></span>
    
10. <span data-ttu-id="f8882-126">若要將一或多個主幹與語音路由產生關聯，請按一下 [ **新增** ]，然後從清單中選取一個主幹。</span><span class="sxs-lookup"><span data-stu-id="f8882-126">To associate one or more trunks with the voice route, click **Add** and then select a trunk from the list.</span></span>
    
11. <span data-ttu-id="f8882-127">若要將一或多個公用交換電話網路 (PSTN) 使用方式與語音路由產生關聯，請按一下 [ **選取** ]，然後從為您的 Enterprise voice 部署定義的 PSTN 使用方式記錄清單中，選擇記錄。</span><span class="sxs-lookup"><span data-stu-id="f8882-127">To associate one or more Public Switched Telephone Network (PSTN) usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f8882-128">若要查看每個可用 PSTN 使用方式記錄的屬性，請參閱 [在商務用 Skype 中查看 PSTN 使用方式記錄](view-pstn-usage-records.md)。</span><span class="sxs-lookup"><span data-stu-id="f8882-128">To view the properties of each of the available PSTN usage records, see [View PSTN usage records in Skype for Business](view-pstn-usage-records.md).</span></span> <span data-ttu-id="f8882-129">> 若要建立或編輯 PSTN 使用方式記錄，請參閱 [在商務用 Skype 中建立或修改語音原則和設定 pstn 使用方式記錄](voice-policy-and-pstn-usage-records.md)</span><span class="sxs-lookup"><span data-stu-id="f8882-129">> To create or edit PSTN usage records, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business](voice-policy-and-pstn-usage-records.md)</span></span>
  
12. <span data-ttu-id="f8882-130">排列 PSTN 使用方式記錄，以獲得最佳效能。</span><span class="sxs-lookup"><span data-stu-id="f8882-130">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="f8882-131">若要變更記錄在清單中的位置，請反白顯示記錄名稱，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="f8882-131">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f8882-132">與語音原則不同的是，列出 PSTN 使用方式記錄的順序很重要，因此語音路由中列出 PSTN 使用方式記錄的順序是沒有意義的。</span><span class="sxs-lookup"><span data-stu-id="f8882-132">In contrast to a voice policy, where the order in which PSTN usage records are listed is important, the order in which PSTN usage records are listed in the voice route is insignificant.</span></span> <span data-ttu-id="f8882-133">不過，我們建議您依使用頻率來組織清單。</span><span class="sxs-lookup"><span data-stu-id="f8882-133">However, we recommend that you organize the list by frequency of use.</span></span> <span data-ttu-id="f8882-134">例如： RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="f8882-134">For example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="f8882-135"> (商務用 Skype 伺服器從左上開始遍歷清單。 ) </span><span class="sxs-lookup"><span data-stu-id="f8882-135">(Skype for Business Server traverses the list from the top down.)</span></span> 
  
13. <span data-ttu-id="f8882-136"> (選用) 在 [ **輸入要測試的轉譯的號碼** ] 欄位中輸入值，然後按一下 [ **移至**]。</span><span class="sxs-lookup"><span data-stu-id="f8882-136">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**.</span></span> <span data-ttu-id="f8882-137">測試結果會顯示在欄位底下。</span><span class="sxs-lookup"><span data-stu-id="f8882-137">The test results are displayed under the field.</span></span>
    
14. <span data-ttu-id="f8882-138">按一下 **[確定]** 以儲存語音路由。</span><span class="sxs-lookup"><span data-stu-id="f8882-138">Click **OK** to save the voice route.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f8882-139">每當您建立語音路由時，都必須執行「 **認可全部** 」命令來發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="f8882-139">Whenever you create a voice route, you must run the **Commit All** command to publish the configuration change.</span></span> <span data-ttu-id="f8882-140">如需詳細資訊，請參閱 [在商務用 Skype 中發佈擱置的變更至語音路由](voice-route-config-changes.md)設定。</span><span class="sxs-lookup"><span data-stu-id="f8882-140">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md).</span></span> 
  
### <a name="to-modify-a-voice-route"></a><span data-ttu-id="f8882-141">修改語音路由</span><span class="sxs-lookup"><span data-stu-id="f8882-141">To modify a voice route</span></span>

1. <span data-ttu-id="f8882-142">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="f8882-142">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="f8882-143">在左導覽列中，按一下 [ **語音路由**]，然後按一下 [ **路由**]。</span><span class="sxs-lookup"><span data-stu-id="f8882-143">In the left navigation bar, click **Voice Routing**, and then click **Route**.</span></span>
    
3. <span data-ttu-id="f8882-144">在 [ **路由** ] 頁面上，使用下列其中一種方法來修改語音路由：</span><span class="sxs-lookup"><span data-stu-id="f8882-144">On the **Route** page, use either of the following methods to modify a voice route:</span></span>
    
   - <span data-ttu-id="f8882-145">按一下 voice route 名稱，按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="f8882-145">Click a voice route name, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="f8882-146">依序按一下 voice route 名稱、[ **編輯**] 和 [ **複製**]，然後按一下 [ **貼** 上]。</span><span class="sxs-lookup"><span data-stu-id="f8882-146">Click a voice route name, click **Edit**, click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="f8882-147">按一下您剛建立之語音路由的新複本，按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="f8882-147">Click the new copy of the voice route that you just created, click **Edit**, and then click **Show details**.</span></span>
    
4. <span data-ttu-id="f8882-148">在 [**編輯語音路由**] 頁面上的 [**名稱**] 欄位中，輸入語音路由的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="f8882-148">In the **Name** field on the **Edit Voice Route** page, type a descriptive name for the voice route.</span></span>
    
5. <span data-ttu-id="f8882-149"> (選用) 在 [ **描述** ] 欄位中，輸入語音路由的其他描述性資訊。</span><span class="sxs-lookup"><span data-stu-id="f8882-149">(Optional) In the **Description** field, type in additional descriptive information for the voice route.</span></span>
    
6. <span data-ttu-id="f8882-150">若要指定您想要此路由容納的模式，您可以使用 **Build a pattern to match** tool 以產生正則運算式，或是手動寫入正則運算式。</span><span class="sxs-lookup"><span data-stu-id="f8882-150">To specify the patterns you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
   - <span data-ttu-id="f8882-151">若要使用 **Build a pattern to match** tool 以產生正則運算式，請輸入下列的值。</span><span class="sxs-lookup"><span data-stu-id="f8882-151">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows.</span></span> <span data-ttu-id="f8882-152">您可以指定兩種類型的模式對應：</span><span class="sxs-lookup"><span data-stu-id="f8882-152">You can specify two types of pattern matching:</span></span>
    
   - <span data-ttu-id="f8882-153">**您想要允許的數位的開始位數**：輸入此路由必須滿足的首碼值 (包括前置 + （如果需要）) 。</span><span class="sxs-lookup"><span data-stu-id="f8882-153">**Starting digits for numbers that you want to allow**: Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="f8882-154">例如，輸入 + 425，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="f8882-154">For example, type +425 and then click **Add**.</span></span> <span data-ttu-id="f8882-155">針對您想要包含在路由中的每個前置詞值，重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="f8882-155">Repeat this for each prefix value that you want to include in the route.</span></span>
    
   - <span data-ttu-id="f8882-156">**例外** 狀況：如果您想要為前置詞值指定一或多個例外狀況，請反白顯示首碼，然後按一下 [ **例外** 狀況]。</span><span class="sxs-lookup"><span data-stu-id="f8882-156">**Exceptions**: If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="f8882-157">針對您  *不*  想要此路由容納的相符模式輸入一個或多個值。</span><span class="sxs-lookup"><span data-stu-id="f8882-157">Type in one or more values for the matching patterns that you do  *not*  want this route to accommodate.</span></span> <span data-ttu-id="f8882-158">例如，若要從路由中排除從 + 425237 開始的數位，請在 [ **例外日期** ] 欄位中輸入 [+ 425237] 的值，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f8882-158">For example, to exclude numbers starting with +425237 from the route, enter a value of+425237 in the **Exceptions** field, and then click **OK**.</span></span>
    
   - <span data-ttu-id="f8882-159">若要手動定義相符的模式，請按一下 [**組建要搭配的模式**] 中的 [**編輯**]，然後輸入 .net Framework 正則運算式，以指定要套用路由之目的地電話號碼的相符模式。如需如何撰寫正則運算式的詳細資訊，請參閱「 [.Net Framework 正則運算式](/dotnet/standard/base-types/regular-expressions)」。</span><span class="sxs-lookup"><span data-stu-id="f8882-159">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.For details about how to write regular expressions, see [".NET Framework Regular Expressions"](/dotnet/standard/base-types/regular-expressions).</span></span> 
    
7. <span data-ttu-id="f8882-160">如果您不想讓撥出呼叫出現在來電收件者的電話識別碼，請選取 [ **抑制來電者識別碼** ]。</span><span class="sxs-lookup"><span data-stu-id="f8882-160">Select **Suppress caller ID** if you do not want the ID of the phone that is making the outbound call to appear to the call recipient.</span></span> <span data-ttu-id="f8882-161">如果您選取此選項，則必須指定要在收件者的來電者 ID 顯示上顯示的 **替代來電者識別碼** 。</span><span class="sxs-lookup"><span data-stu-id="f8882-161">If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient's caller ID display.</span></span>
    
8. <span data-ttu-id="f8882-162">若要將一或多個公用交換電話網路 (PSTN) 主幹與語音路由產生關聯，請按一下 [ **新增**]，然後從清單中選取一個主幹。</span><span class="sxs-lookup"><span data-stu-id="f8882-162">To associate one or more public switched telephone network (PSTN) trunks with the voice route, click **Add**, and then select a trunk from the list.</span></span>
    
9. <span data-ttu-id="f8882-163">若要將一或多個 PSTN 使用方式與語音路由產生關聯，請按一下 [ **選取** ]，然後從為您的企業語音部署定義的 PSTN 使用方式記錄清單中，選擇記錄。</span><span class="sxs-lookup"><span data-stu-id="f8882-163">To associate one or more PSTN usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f8882-164">若要查看每個可用 PSTN 使用方式記錄的屬性，請參閱 [在商務用 Skype 中查看 PSTN 使用方式記錄](view-pstn-usage-records.md)。</span><span class="sxs-lookup"><span data-stu-id="f8882-164">To view the properties of each of the available PSTN usage records, see [View PSTN usage records in Skype for Business](view-pstn-usage-records.md).</span></span> <span data-ttu-id="f8882-165">> 若要建立或編輯 PSTN 使用方式記錄，請參閱 [在商務用 Skype 中建立或修改語音原則和設定 pstn 使用方式記錄](voice-policy-and-pstn-usage-records.md)。</span><span class="sxs-lookup"><span data-stu-id="f8882-165">> To create or edit PSTN usage records, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business](voice-policy-and-pstn-usage-records.md).</span></span> 
  
10. <span data-ttu-id="f8882-166">排列 PSTN 使用方式記錄，以獲得最佳效能。</span><span class="sxs-lookup"><span data-stu-id="f8882-166">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="f8882-167">若要變更記錄在清單中的位置，請反白顯示記錄名稱，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="f8882-167">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f8882-168">相對於語音原則，其中列出 PSTN 使用方式記錄的順序很重要，語音路由中的 PSTN 使用方式記錄的順序是無關緊要的。</span><span class="sxs-lookup"><span data-stu-id="f8882-168">In contrast to a voice policy where the order in which PSTN usage records are listed is important, the order of PSTN usage records in a voice route is insignificant.</span></span> <span data-ttu-id="f8882-169">不過，我們建議您依使用頻率來組織清單，例如： RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="f8882-169">However, we recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="f8882-170"> (商務用 Skype 伺服器從左上開始遍歷清單。 ) </span><span class="sxs-lookup"><span data-stu-id="f8882-170">(Skype for Business Server traverses the list from the top down.)</span></span> 
  
11. <span data-ttu-id="f8882-171"> (選用) 在 [ **輸入要測試的轉譯的號碼** ] 欄位中輸入值，然後按一下 [ **移至**]。</span><span class="sxs-lookup"><span data-stu-id="f8882-171">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**.</span></span> <span data-ttu-id="f8882-172">測試結果會顯示在欄位底下。</span><span class="sxs-lookup"><span data-stu-id="f8882-172">The test results are displayed under the field.</span></span>
    
12. <span data-ttu-id="f8882-173">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f8882-173">Click **OK**.</span></span>
    
13. <span data-ttu-id="f8882-174">在 [ **路由** ] 頁面上，按一下 [ **認可**]，然後按一下 [ **全部認可**]。</span><span class="sxs-lookup"><span data-stu-id="f8882-174">On the **Route** page, click **Commit**, and then click **Commit all**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f8882-175">當您建立或修改語音路由時，您必須執行「 **認可全部** 」命令來發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="f8882-175">Whenever you create or modify a voice route, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="f8882-176">如需詳細資訊，請參閱 Operations 檔中的在 [商務用 Skype 中發佈待定的變更至語音路由](voice-route-config-changes.md) 設定。</span><span class="sxs-lookup"><span data-stu-id="f8882-176">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f8882-177">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f8882-177">See also</span></span>

[<span data-ttu-id="f8882-178">在商務用 Skype 中查看 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="f8882-178">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)
  
[<span data-ttu-id="f8882-179">在商務用 Skype 中建立或修改語音原則及設定 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="f8882-179">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)
  
[<span data-ttu-id="f8882-180">在商務用 Skype 中將擱置的變更發佈至語音路由設定</span><span class="sxs-lookup"><span data-stu-id="f8882-180">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)