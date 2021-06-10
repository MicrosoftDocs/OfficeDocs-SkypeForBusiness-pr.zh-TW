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
ms.openlocfilehash: f94c847f5c75e793856c0975678e2806629e2dcd
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282360"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="4461e-103">建立和管理撥號對應表</span><span class="sxs-lookup"><span data-stu-id="4461e-103">Create and manage dial plans</span></span>

<span data-ttu-id="4461e-104">規劃組織的撥號方案，並找出呼叫路由需要建立的所有標準化規則之後，就可以建立撥號方案了。</span><span class="sxs-lookup"><span data-stu-id="4461e-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="4461e-105">使用具有有效授權Teams系統管理員帳戶，您可以使用 Microsoft Teams或Windows PowerShell建立和管理撥號方案。</span><span class="sxs-lookup"><span data-stu-id="4461e-105">With an administrator account that has a valid Teams license, you can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4461e-106">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="4461e-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="4461e-107">建立撥號方案</span><span class="sxs-lookup"><span data-stu-id="4461e-107">Create a dial plan</span></span>

1. <span data-ttu-id="4461e-108">在系統管理中心的左側導Microsoft Teams，請前往 **語音**  >  **撥號方案**。</span><span class="sxs-lookup"><span data-stu-id="4461e-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="4461e-109">按一下 **[新增**」，然後輸入撥號方案的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="4461e-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="4461e-110">![顯示建立撥號方案之新增頁面的螢幕擷取畫面](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="4461e-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="4461e-111">在 **撥號方案詳細資料** 下，指定外部撥號首碼，如果使用者需要撥打一或多個額外的前導 (，例如 9) 以取得外部線路。</span><span class="sxs-lookup"><span data-stu-id="4461e-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="4461e-112">若要這麼做：</span><span class="sxs-lookup"><span data-stu-id="4461e-112">To do this:</span></span>
    1. <span data-ttu-id="4461e-113">在外部 **撥號首碼** 方塊中，輸入外部撥號首碼。</span><span class="sxs-lookup"><span data-stu-id="4461e-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="4461e-114">首碼最多四個字元 (#，\*，以及 0-9) 。</span><span class="sxs-lookup"><span data-stu-id="4461e-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="4461e-115">開啟優化 **的裝置撥號**。</span><span class="sxs-lookup"><span data-stu-id="4461e-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="4461e-116">如果您指定外部撥號首碼，您也必須開啟此設定，才能使用首碼，好在組織外部撥打電話。</span><span class="sxs-lookup"><span data-stu-id="4461e-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="4461e-117">在 **標準化規則** 下，為撥號方案設定一 [或多個標準化](what-are-dial-plans.md#normalization-rules) 規則並關聯。</span><span class="sxs-lookup"><span data-stu-id="4461e-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="4461e-118">每個撥號方案都必須至少有一個與其相關聯的標準化規則。</span><span class="sxs-lookup"><span data-stu-id="4461e-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="4461e-119">若要這麼做，請執行下列一或多個操作：</span><span class="sxs-lookup"><span data-stu-id="4461e-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="4461e-120">若要建立新常態化規則並將其與撥號方案建立關聯，請按一下 [ **新增**」，然後定義規則。</span><span class="sxs-lookup"><span data-stu-id="4461e-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="4461e-121">若要編輯已與撥號方案相關聯的標準化規則，請按一下規則名稱左側以選取規則，然後按一下 [ **編輯**。</span><span class="sxs-lookup"><span data-stu-id="4461e-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="4461e-122">進行您想要的變更，然後按一下 [ **儲存**。</span><span class="sxs-lookup"><span data-stu-id="4461e-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="4461e-123">若要從撥號方案移除標準化規則，請按一下規則名稱左側以選取規則，然後按一下 [ **移除**。</span><span class="sxs-lookup"><span data-stu-id="4461e-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="4461e-124">以您想要的順序排列標準化規則。</span><span class="sxs-lookup"><span data-stu-id="4461e-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="4461e-125">按一下 **[上移** 或 **下** 移來變更規則在清單中的位置。</span><span class="sxs-lookup"><span data-stu-id="4461e-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4461e-126">Teams由上而下，然後使用符合撥號號碼的第一個規則，來執行標準化規則清單。</span><span class="sxs-lookup"><span data-stu-id="4461e-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="4461e-127">如果您設定撥號方案，讓撥號號碼可以比對多個標準化規則，請確定較嚴格的規則會排序在較不嚴格的規則上方。</span><span class="sxs-lookup"><span data-stu-id="4461e-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span>

6. <span data-ttu-id="4461e-128">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="4461e-128">Click **Save**.</span></span>
7. <span data-ttu-id="4461e-129">如果您想要測試撥號方案，請在 [測試撥號方案> 下輸入電話號碼，然後按一下 [**測試**。</span><span class="sxs-lookup"><span data-stu-id="4461e-129">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="4461e-130">編輯撥號方案</span><span class="sxs-lookup"><span data-stu-id="4461e-130">Edit a dial plan</span></span>

1. <span data-ttu-id="4461e-131">在系統管理中心的左側導Microsoft Teams，請前往 **語音**  >  **撥號方案**。</span><span class="sxs-lookup"><span data-stu-id="4461e-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="4461e-132">按一下撥號方案名稱左側的撥號方案，然後按一下 [編輯」，以選取 **撥號方案**。</span><span class="sxs-lookup"><span data-stu-id="4461e-132">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="4461e-133">進行您想要的變更，然後按一下 [ **儲存**。</span><span class="sxs-lookup"><span data-stu-id="4461e-133">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-dial-plan-to-users"></a><span data-ttu-id="4461e-134">指派撥號方案給使用者</span><span class="sxs-lookup"><span data-stu-id="4461e-134">Assign a dial plan to users</span></span>

<span data-ttu-id="4461e-135">您以指派策略的方式指派撥號方案。</span><span class="sxs-lookup"><span data-stu-id="4461e-135">You assign a dial plan in the same way you assign policies.</span></span> [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a><span data-ttu-id="4461e-136">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="4461e-136">Using PowerShell</span></span>
  
### <a name="start-powershell"></a><span data-ttu-id="4461e-137">啟動 PowerShell</span><span class="sxs-lookup"><span data-stu-id="4461e-137">Start PowerShell</span></span>
- <span data-ttu-id="4461e-138">開啟 Windows PowerShell命令提示符，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="4461e-138">Open a Windows PowerShell command prompt and run the following commands:</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="4461e-139">建立和管理撥號方案</span><span class="sxs-lookup"><span data-stu-id="4461e-139">Create and manage your dial plans</span></span>

<span data-ttu-id="4461e-140">您可以使用單一 Cmdlet 或 PowerShell 腳本來建立和管理租使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="4461e-140">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="4461e-141">使用單一 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="4461e-141">Using single cmdlets</span></span>

- <span data-ttu-id="4461e-142">若要建立新的撥號方案，請執行：</span><span class="sxs-lookup"><span data-stu-id="4461e-142">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="4461e-143">有關其他範例和參數，請參閱 [New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan)。</span><span class="sxs-lookup"><span data-stu-id="4461e-143">For other examples and parameters, see [New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="4461e-144">若要編輯現有撥號方案設定，請執行：</span><span class="sxs-lookup"><span data-stu-id="4461e-144">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="4461e-145">有關其他範例和參數，請參閱 [Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan)。</span><span class="sxs-lookup"><span data-stu-id="4461e-145">For other examples and parameters, see [Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="4461e-146">若要將使用者新增到撥號方案，請執行：</span><span class="sxs-lookup"><span data-stu-id="4461e-146">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="4461e-147">有關其他範例和參數，請參閱 [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan)。</span><span class="sxs-lookup"><span data-stu-id="4461e-147">For other examples and parameters, see [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="4461e-148">若要在撥號方案上查看設定，請執行：</span><span class="sxs-lookup"><span data-stu-id="4461e-148">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="4461e-149">有關其他範例和參數，請參閱 [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="4461e-149">For other examples and parameters, see [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="4461e-150">若要刪除撥號方案，請執行：</span><span class="sxs-lookup"><span data-stu-id="4461e-150">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="4461e-151">有關其他範例和參數，請參閱 [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="4461e-151">For other examples and parameters, see [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="4461e-152">若要查看有效撥號計畫的設定，請執行：</span><span class="sxs-lookup"><span data-stu-id="4461e-152">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="4461e-153">有關其他範例和參數，請參閱 [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan)。</span><span class="sxs-lookup"><span data-stu-id="4461e-153">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="4461e-154">若要測試撥號方案的有效設定，請執行：</span><span class="sxs-lookup"><span data-stu-id="4461e-154">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="4461e-155">有關其他範例和參數，請參閱 [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="4461e-155">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="4461e-156">使用 PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="4461e-156">Using a PowerShell script</span></span>

<span data-ttu-id="4461e-157">執行此操作以刪除與租使用者撥號方案相關聯的標準化規則，而不需要先刪除租使用者撥號方案：</span><span class="sxs-lookup"><span data-stu-id="4461e-157">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="4461e-158">執行此程式，將下列標準化規則新增到名為 RedmondDialPlan 的現有租使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="4461e-158">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="4461e-159">執行此程式，從名為 RedmondDialPlan 的現有租使用者撥號方案移除下列標準化規則。</span><span class="sxs-lookup"><span data-stu-id="4461e-159">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="4461e-160">當您也想要檢查現有的標準化規則、決定要刪除哪些規則，然後使用其索引來移除規則時，請執行下列操作。</span><span class="sxs-lookup"><span data-stu-id="4461e-160">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="4461e-161">標準化規則的陣列會以索引 0 開始。</span><span class="sxs-lookup"><span data-stu-id="4461e-161">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="4461e-162">我們要移除 3 位數的標準化規則，因此這是索引 1。</span><span class="sxs-lookup"><span data-stu-id="4461e-162">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
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

<span data-ttu-id="4461e-163">執行此程式以尋找所有獲得 RedmondDialPlan 租使用者撥號方案的使用者。</span><span class="sxs-lookup"><span data-stu-id="4461e-163">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="4461e-164">執行此程式以移除所有擁有 HostingProvider sipfed.online.lync.com。</span><span class="sxs-lookup"><span data-stu-id="4461e-164">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="4461e-165">執行這些操作，將名為 OPDP1 的現有內部部署撥號方案新增為貴組織的租使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="4461e-165">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="4461e-166">您需要先將內部部署撥號方案儲存到.xml，然後使用它來建立新的租使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="4461e-166">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="4461e-167">執行此操作，將內部部署撥號方案儲存到.xml檔案。</span><span class="sxs-lookup"><span data-stu-id="4461e-167">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="4461e-168">執行此程式以建立新的租使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="4461e-168">Run this to create the new tenant dial plan.</span></span>
  
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
    
## <a name="related-topics"></a><span data-ttu-id="4461e-169">相關主題</span><span class="sxs-lookup"><span data-stu-id="4461e-169">Related topics</span></span>

- [<span data-ttu-id="4461e-170">什麼是撥號對應表？</span><span class="sxs-lookup"><span data-stu-id="4461e-170">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="4461e-171">移轉電話號碼的常見問題</span><span class="sxs-lookup"><span data-stu-id="4461e-171">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)
- [<span data-ttu-id="4461e-172">用於通話方案的各種電話號碼</span><span class="sxs-lookup"><span data-stu-id="4461e-172">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="4461e-173">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="4461e-173">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="4461e-174">緊急通話條款及條件</span><span class="sxs-lookup"><span data-stu-id="4461e-174">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="4461e-175">[緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="4461e-175">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="4461e-176">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="4461e-176">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
