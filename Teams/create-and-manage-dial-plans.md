---
title: 建立和管理撥號對應表
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-apr2020
description: 瞭解如何使用系統管理中心Microsoft Teams或Windows PowerShell PSTN 撥號方案 (撥號方案) 。
ms.openlocfilehash: 59867dfe49436635f690ff9f5d56a2be36e553ec
ms.sourcegitcommit: 127f9fdf05b93ee3af4244224e1c32a45d73d3ee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/21/2021
ms.locfileid: "53046230"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="847fa-103">建立和管理撥號對應表</span><span class="sxs-lookup"><span data-stu-id="847fa-103">Create and manage dial plans</span></span>

<span data-ttu-id="847fa-104">規劃組織的撥號方案，並找出呼叫路由需要建立的所有標準化規則之後，就可以建立撥號方案了。</span><span class="sxs-lookup"><span data-stu-id="847fa-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="847fa-105">使用具有有效授權Teams系統管理員帳戶，您可以使用 Microsoft Teams或Windows PowerShell建立和管理撥號方案。</span><span class="sxs-lookup"><span data-stu-id="847fa-105">With an administrator account that has a valid Teams license, you can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="847fa-106">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="847fa-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="847fa-107">建立撥號方案</span><span class="sxs-lookup"><span data-stu-id="847fa-107">Create a dial plan</span></span>

1. <span data-ttu-id="847fa-108">在系統管理中心的左側導Microsoft Teams，請前往 **語音**  >  **撥號方案**。</span><span class="sxs-lookup"><span data-stu-id="847fa-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="847fa-109">按一下 **[新增**」，然後輸入撥號方案的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="847fa-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="847fa-110">![顯示建立撥號方案之新增頁面的螢幕擷取畫面](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="847fa-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="847fa-111">在 **撥號方案詳細資料** 下，指定外部撥號首碼，如果使用者需要撥打一或多個額外的前導 (例如 9) 以取得外部線路。</span><span class="sxs-lookup"><span data-stu-id="847fa-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="847fa-112">若要這麼做：</span><span class="sxs-lookup"><span data-stu-id="847fa-112">To do this:</span></span>
    1. <span data-ttu-id="847fa-113">在外部 **撥號首碼** 方塊中，輸入外部撥號首碼。</span><span class="sxs-lookup"><span data-stu-id="847fa-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="847fa-114">首碼最多四個字元 (#、\*和 0-9) 。</span><span class="sxs-lookup"><span data-stu-id="847fa-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="847fa-115">開啟優化 **的裝置撥號**。</span><span class="sxs-lookup"><span data-stu-id="847fa-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="847fa-116">如果您指定外部撥號首碼，您也必須開啟此設定，才能使用首碼，才能在組織外撥打電話。</span><span class="sxs-lookup"><span data-stu-id="847fa-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="847fa-117">在 **標準化規則** 下，為撥號方案設定一 [或多個標準化](what-are-dial-plans.md#normalization-rules) 規則並關聯。</span><span class="sxs-lookup"><span data-stu-id="847fa-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="847fa-118">每個撥號方案都必須至少有一個與其相關聯的標準化規則。</span><span class="sxs-lookup"><span data-stu-id="847fa-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="847fa-119">若要這麼做，請執行下列一或多個操作：</span><span class="sxs-lookup"><span data-stu-id="847fa-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="847fa-120">若要建立新常態化規則並將其與撥號方案建立關聯，請按一下 [ **新增**，然後定義規則。</span><span class="sxs-lookup"><span data-stu-id="847fa-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="847fa-121">若要編輯已與撥號方案相關聯的標準化規則，請按一下規則名稱左側以選取規則，然後按一下 [ **編輯**。</span><span class="sxs-lookup"><span data-stu-id="847fa-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="847fa-122">進行您想要的變更，然後按一下 [ **儲存**。</span><span class="sxs-lookup"><span data-stu-id="847fa-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="847fa-123">若要從撥號方案移除標準化規則，請按一下規則名稱左側以選取規則，然後按一下 [ **移除**。</span><span class="sxs-lookup"><span data-stu-id="847fa-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="847fa-124">以您想要的順序排列標準化規則。</span><span class="sxs-lookup"><span data-stu-id="847fa-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="847fa-125">按一下 **[上移** 或 **下** 移以變更規則在清單中的位置。</span><span class="sxs-lookup"><span data-stu-id="847fa-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="847fa-126">Teams由上而下，從上而下移動標準化規則清單，並使用符合撥號號碼的第一個規則。</span><span class="sxs-lookup"><span data-stu-id="847fa-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="847fa-127">如果您設定撥號方案，讓撥號號碼可以比對多個標準化規則，請確定較嚴格的規則會排序在較不嚴格的規則上方。</span><span class="sxs-lookup"><span data-stu-id="847fa-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span> <span data-ttu-id="847fa-128">如果您設定了將撥號號碼正規化的撥號方案，但不含 「+」，通話服務會嘗試使用租使用者和區域撥號方案規則再次嘗試將號碼正規化。</span><span class="sxs-lookup"><span data-stu-id="847fa-128">If you set up a dial plan that normalizes a dialed number without a "+", the calling service will attempt to normalize the number again using Tenant and regional dial plan rules.</span></span> <span data-ttu-id="847fa-129">為了避免重複常態化，建議所有標準化規則都會導致數位以"+"開始。</span><span class="sxs-lookup"><span data-stu-id="847fa-129">To avoid double normalization, it's recommended that all normalization rules result in numbers starting with a "+".</span></span> <span data-ttu-id="847fa-130">直接路由客戶可以使用 [主幹翻譯](direct-routing-translate-numbers.md) 規則來移除 「+」。如果需要的話。</span><span class="sxs-lookup"><span data-stu-id="847fa-130">Direct Routing customers can use [trunk translation](direct-routing-translate-numbers.md) rules to remove the "+" if required.</span></span> 

6. <span data-ttu-id="847fa-131">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="847fa-131">Click **Save**.</span></span>
7. <span data-ttu-id="847fa-132">如果您想要測試撥號方案，請在 [測試撥號方案> 下輸入電話號碼，然後按一下 [**測試**。</span><span class="sxs-lookup"><span data-stu-id="847fa-132">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="847fa-133">編輯撥號方案</span><span class="sxs-lookup"><span data-stu-id="847fa-133">Edit a dial plan</span></span>

1. <span data-ttu-id="847fa-134">在系統管理中心的左側導Microsoft Teams，請前往 **語音**  >  **撥號方案**。</span><span class="sxs-lookup"><span data-stu-id="847fa-134">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="847fa-135">按一下撥號方案名稱左側的撥號方案，然後按一下 [編輯」，以選取 **撥號方案**。</span><span class="sxs-lookup"><span data-stu-id="847fa-135">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="847fa-136">進行您想要的變更，然後按一下 [ **儲存**。</span><span class="sxs-lookup"><span data-stu-id="847fa-136">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-dial-plan-to-users"></a><span data-ttu-id="847fa-137">指派撥號方案給使用者</span><span class="sxs-lookup"><span data-stu-id="847fa-137">Assign a dial plan to users</span></span>

<span data-ttu-id="847fa-138">您以指派策略的方式指派撥號方案。</span><span class="sxs-lookup"><span data-stu-id="847fa-138">You assign a dial plan in the same way you assign policies.</span></span> [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a><span data-ttu-id="847fa-139">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="847fa-139">Using PowerShell</span></span>
  
### <a name="start-powershell"></a><span data-ttu-id="847fa-140">啟動 PowerShell</span><span class="sxs-lookup"><span data-stu-id="847fa-140">Start PowerShell</span></span>
- <span data-ttu-id="847fa-141">開啟 Windows PowerShell命令提示符，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="847fa-141">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="847fa-142">建立和管理撥號方案</span><span class="sxs-lookup"><span data-stu-id="847fa-142">Create and manage your dial plans</span></span>

<span data-ttu-id="847fa-143">您可以使用單一 Cmdlet 或 PowerShell 腳本來建立和管理租使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="847fa-143">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="847fa-144">使用單一 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="847fa-144">Using single cmdlets</span></span>

- <span data-ttu-id="847fa-145">若要建立新的撥號方案，請執行：</span><span class="sxs-lookup"><span data-stu-id="847fa-145">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="847fa-146">有關其他範例和參數，請參閱 [New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan)。</span><span class="sxs-lookup"><span data-stu-id="847fa-146">For other examples and parameters, see [New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="847fa-147">若要編輯現有撥號方案設定，請執行：</span><span class="sxs-lookup"><span data-stu-id="847fa-147">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="847fa-148">有關其他範例和參數，請參閱 [Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan)。</span><span class="sxs-lookup"><span data-stu-id="847fa-148">For other examples and parameters, see [Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="847fa-149">若要將使用者新增到撥號方案，請執行：</span><span class="sxs-lookup"><span data-stu-id="847fa-149">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="847fa-150">有關其他範例和參數，請參閱 [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan)。</span><span class="sxs-lookup"><span data-stu-id="847fa-150">For other examples and parameters, see [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="847fa-151">若要在撥號方案上查看設定，請執行：</span><span class="sxs-lookup"><span data-stu-id="847fa-151">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="847fa-152">有關其他範例和參數，請參閱 [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="847fa-152">For other examples and parameters, see [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="847fa-153">若要刪除撥號方案，請執行：</span><span class="sxs-lookup"><span data-stu-id="847fa-153">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="847fa-154">有關其他範例和參數，請參閱 [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="847fa-154">For other examples and parameters, see [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="847fa-155">若要查看有效撥號計畫的設定，請執行：</span><span class="sxs-lookup"><span data-stu-id="847fa-155">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="847fa-156">有關其他範例和參數，請參閱 [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan)。</span><span class="sxs-lookup"><span data-stu-id="847fa-156">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="847fa-157">若要測試撥號方案的有效設定，請執行：</span><span class="sxs-lookup"><span data-stu-id="847fa-157">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="847fa-158">有關其他範例和參數，請參閱 [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="847fa-158">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="847fa-159">使用 PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="847fa-159">Using a PowerShell script</span></span>

<span data-ttu-id="847fa-160">執行此操作以刪除與租使用者撥號方案相關聯的標準化規則，而不需要先刪除租使用者撥號方案：</span><span class="sxs-lookup"><span data-stu-id="847fa-160">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="847fa-161">執行此程式，將下列標準化規則新增到名為 RedmondDialPlan 的現有租使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="847fa-161">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="847fa-162">執行此程式，從名為 RedmondDialPlan 的現有租使用者撥號方案移除下列標準化規則。</span><span class="sxs-lookup"><span data-stu-id="847fa-162">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="847fa-163">當您也想要檢查現有的標準化規則、決定要刪除哪些規則，然後使用其索引來移除規則時，請執行下列操作。</span><span class="sxs-lookup"><span data-stu-id="847fa-163">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="847fa-164">標準化規則的陣列會以索引 0 開始。</span><span class="sxs-lookup"><span data-stu-id="847fa-164">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="847fa-165">我們要移除 3 位數的標準化規則，因此這是索引 1。</span><span class="sxs-lookup"><span data-stu-id="847fa-165">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
```PowerShell
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
Description         : 4-digit
Pattern             : ^(\\d{4})$
Translation         : +1426666$1
Name                : NR2
IsInternalExtension : False

Description         : 3-digit
Pattern             : ^(\\d{3})$
Translation         : +14255551$1
Name                : NR12
IsInternalExtension : False

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="847fa-166">執行此程式以尋找所有獲得 RedmondDialPlan 租使用者撥號方案的使用者。</span><span class="sxs-lookup"><span data-stu-id="847fa-166">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="847fa-167">執行此程式以移除所有擁有 HostingProvider sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="847fa-167">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="847fa-168">執行這些操作，將名為 OPDP1 的現有內部部署撥號方案新增為貴組織的租使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="847fa-168">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="847fa-169">您需要先將內部部署撥號方案儲存到.xml，然後使用它來建立新的租使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="847fa-169">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="847fa-170">執行此操作，將內部部署撥號方案儲存到.xml檔案。</span><span class="sxs-lookup"><span data-stu-id="847fa-170">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="847fa-171">執行此程式以建立新的租使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="847fa-171">Run this to create the new tenant dial plan.</span></span>
  
```PowerShell
$DPFileName = "dialplan.xml"
$dp = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" + $nr.Name
 $nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation -IsInternalExtension $nr.IsInternalExtension -InMemory
 $NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
    
## <a name="related-topics"></a><span data-ttu-id="847fa-172">相關主題</span><span class="sxs-lookup"><span data-stu-id="847fa-172">Related topics</span></span>

- [<span data-ttu-id="847fa-173">什麼是撥號對應表？</span><span class="sxs-lookup"><span data-stu-id="847fa-173">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="847fa-174">移轉電話號碼的常見問題</span><span class="sxs-lookup"><span data-stu-id="847fa-174">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)
- [<span data-ttu-id="847fa-175">用於通話方案的各種電話號碼</span><span class="sxs-lookup"><span data-stu-id="847fa-175">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="847fa-176">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="847fa-176">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="847fa-177">緊急通話條款及條件</span><span class="sxs-lookup"><span data-stu-id="847fa-177">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="847fa-178">[緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="847fa-178">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="847fa-179">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="847fa-179">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
