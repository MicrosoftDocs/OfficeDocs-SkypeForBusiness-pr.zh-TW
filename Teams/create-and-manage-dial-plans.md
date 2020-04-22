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
description: 瞭解如何建立和管理呼叫撥號方案（PSTN 呼叫撥號方案），以及管理它們的方式。
ms.openlocfilehash: 9c72745e6dee12ffbac4d91df47df37c327aab33
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778259"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="646b6-103">建立和管理撥號對應表</span><span class="sxs-lookup"><span data-stu-id="646b6-103">Create and manage dial plans</span></span>

<span data-ttu-id="646b6-104">規劃貴組織的撥號方案並查明需要為呼叫路由建立的所有正常化規則之後，您就可以開始建立撥號方案了。</span><span class="sxs-lookup"><span data-stu-id="646b6-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="646b6-105">您可以使用 Microsoft 團隊系統管理中心或 Windows PowerShell 來建立及管理撥號方案。</span><span class="sxs-lookup"><span data-stu-id="646b6-105">You can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="646b6-106">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="646b6-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="646b6-107">建立撥號方案</span><span class="sxs-lookup"><span data-stu-id="646b6-107">Create a dial plan</span></span>

1. <span data-ttu-id="646b6-108">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音** > **撥號方案**]。</span><span class="sxs-lookup"><span data-stu-id="646b6-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="646b6-109">按一下 [**新增**]，然後輸入撥號方案的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="646b6-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="646b6-110">![顯示建立撥號方案之 [新增] 頁面的螢幕擷取畫面](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="646b6-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="646b6-111">在 [**撥號方案詳細資料**] 底下，如果使用者需要撥一或多個額外的前導數位（例如9）來取得外部線路，請指定外部撥號首碼。</span><span class="sxs-lookup"><span data-stu-id="646b6-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="646b6-112">若要執行此動作：</span><span class="sxs-lookup"><span data-stu-id="646b6-112">To do this:</span></span>
    1. <span data-ttu-id="646b6-113">在 [**外部撥號首碼**] 方塊中，輸入外部撥號首碼。</span><span class="sxs-lookup"><span data-stu-id="646b6-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="646b6-114">前置詞最多可有四個字元（#、\* 及0-9）。</span><span class="sxs-lookup"><span data-stu-id="646b6-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="646b6-115">開啟**優化的裝置撥號**。</span><span class="sxs-lookup"><span data-stu-id="646b6-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="646b6-116">如果您指定外部撥號首碼，您也必須開啟此設定以套用首碼，以便在您的組織以外進行通話。</span><span class="sxs-lookup"><span data-stu-id="646b6-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="646b6-117">在 [**正常化規則**] 底下，針對撥號方案設定及建立一或多個[正常化規則](what-are-dial-plans.md#normalization-rules)。</span><span class="sxs-lookup"><span data-stu-id="646b6-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="646b6-118">每個撥號方案都必須至少有一個與它相關聯的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="646b6-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="646b6-119">若要這樣做，請執行下列其中一項或多項操作：</span><span class="sxs-lookup"><span data-stu-id="646b6-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="646b6-120">若要建立新的正常化規則，並將它與撥號方案建立關聯，請按一下 [**新增**]，然後定義規則。</span><span class="sxs-lookup"><span data-stu-id="646b6-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="646b6-121">若要編輯已經與撥號方案相關聯的正常化規則，請按一下規則名稱左邊的，然後按一下 [**編輯**]，選取規則。</span><span class="sxs-lookup"><span data-stu-id="646b6-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="646b6-122">進行您想要的變更，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="646b6-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="646b6-123">若要從撥號方案中移除正常化規則，請按一下規則名稱左方，然後按一下 [**移除**]，即可選取規則。</span><span class="sxs-lookup"><span data-stu-id="646b6-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="646b6-124">依您想要的順序排列正常化規則。</span><span class="sxs-lookup"><span data-stu-id="646b6-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="646b6-125">按一下 [**上移** **] 或 [下移]** ，即可變更清單中規則的位置。</span><span class="sxs-lookup"><span data-stu-id="646b6-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="646b6-126">團隊會從上而下遍歷正常化規則清單，並使用與撥號號碼相符的第一個規則。</span><span class="sxs-lookup"><span data-stu-id="646b6-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="646b6-127">如果您設定撥號方案，讓撥入的號碼可以符合多個正常化規則，請確定更嚴格的規則排序在限制性較低的規則上方。</span><span class="sxs-lookup"><span data-stu-id="646b6-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span>

6. <span data-ttu-id="646b6-128">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="646b6-128">Click **Save**.</span></span>
7. <span data-ttu-id="646b6-129">如果您想要測試撥號規劃，請在 [**測試撥號方案**] 下輸入電話號碼，然後按一下 [**測試**]。</span><span class="sxs-lookup"><span data-stu-id="646b6-129">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="646b6-130">編輯撥號方案</span><span class="sxs-lookup"><span data-stu-id="646b6-130">Edit a dial plan</span></span>

1. <span data-ttu-id="646b6-131">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音** > **撥號方案**]。</span><span class="sxs-lookup"><span data-stu-id="646b6-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="646b6-132">按一下撥號方案名稱左邊的，然後按一下 [**編輯**]，選取撥號方案。</span><span class="sxs-lookup"><span data-stu-id="646b6-132">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="646b6-133">進行您想要的變更，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="646b6-133">Make the changes that you want, and then click **Save**.</span></span>

### <a name="add-users-to-a-dial-plan"></a><span data-ttu-id="646b6-134">將使用者新增至撥號方案</span><span class="sxs-lookup"><span data-stu-id="646b6-134">Add users to a dial plan</span></span>

1. <span data-ttu-id="646b6-135">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="646b6-135">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="646b6-136">按一下 [顯示名稱]，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="646b6-136">Select the user by clicking the display name.</span></span>
3. <span data-ttu-id="646b6-137">選取 [**原則**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="646b6-137">Select the **Policies** tab.</span></span>
4. <span data-ttu-id="646b6-138">按一下指派原則右側的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="646b6-138">Click **Edit** to the right of Assigned policies.</span></span>
5. <span data-ttu-id="646b6-139">從 [**撥號方案**] 下拉式功能表中，選取您要指派給使用者的撥號方案，然後按一下 [套用] **。**</span><span class="sxs-lookup"><span data-stu-id="646b6-139">From the **Dial plan** drop-down menu, select the dial plan you want to assign to the user and then click **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="646b6-140">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="646b6-140">Using PowerShell</span></span>
  
### <a name="verify-and-start-remote-powershell"></a><span data-ttu-id="646b6-141">驗證並啟動遠端 PowerShell</span><span class="sxs-lookup"><span data-stu-id="646b6-141">Verify and start Remote PowerShell</span></span>

 <span data-ttu-id="646b6-142">**檢查您執行的是 Windows PowerShell 版本3.0 或更新版本**</span><span class="sxs-lookup"><span data-stu-id="646b6-142">**Check that you are running Windows PowerShell version 3.0 or later**</span></span>
  
1. <span data-ttu-id="646b6-143">若要確認您執行的是版本3.0 或更高版本： [**開始] 功能表** > **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="646b6-143">To verify that you're running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="646b6-144">在**Windows PowerShell**視窗中輸入 [_取得主機_]，以檢查版本。</span><span class="sxs-lookup"><span data-stu-id="646b6-144">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="646b6-145">如果您沒有版本3.0 或更新版本，請下載並安裝 Windows PowerShell 更新。</span><span class="sxs-lookup"><span data-stu-id="646b6-145">If you don't have version 3.0 or later, download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="646b6-146">請參閱[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) ，以下載並更新 Windows PowerShell 至版本4.0。</span><span class="sxs-lookup"><span data-stu-id="646b6-146">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="646b6-147">出現提示時，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="646b6-147">Restart your computer when you're prompted.</span></span>
    
4. <span data-ttu-id="646b6-148">您也需要安裝適用于商務用 Skype Online 的 Windows PowerShell 模組，這可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="646b6-148">You'll also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="646b6-149">您可以在[商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上，下載此模組（只有64位電腦支援）。</span><span class="sxs-lookup"><span data-stu-id="646b6-149">You can download this module, which is supported only on 64-bit computers, at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="646b6-150">如果出現提示，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="646b6-150">Restart your computer if you're prompted.</span></span>
    
<span data-ttu-id="646b6-151">若要深入瞭解，請參閱[在單一 Windows PowerShell 視窗中連接至所有 Office 365 服務](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)。</span><span class="sxs-lookup"><span data-stu-id="646b6-151">To learn more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>
  
 <span data-ttu-id="646b6-152">**啟動 Windows PowerShell 會話**</span><span class="sxs-lookup"><span data-stu-id="646b6-152">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="646b6-153">按一下 [**啟動** > **Windows PowerShell**]。</span><span class="sxs-lookup"><span data-stu-id="646b6-153">Click **Start** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="646b6-154">在**Windows PowerShell**視窗中，執行下列動作以連線至您的 Microsoft 365 或 Office 365：</span><span class="sxs-lookup"><span data-stu-id="646b6-154">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="646b6-155">您在第一次使用商務用 Skype Online Windows PowerShell 模組時，您只需執行匯**入模組**命令。</span><span class="sxs-lookup"><span data-stu-id="646b6-155">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  

    ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="646b6-156">建立及管理您的撥號方案</span><span class="sxs-lookup"><span data-stu-id="646b6-156">Create and manage your dial plans</span></span>

<span data-ttu-id="646b6-157">您可以使用單一 Cmdlet 或 PowerShell 腳本來建立及管理租使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="646b6-157">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="646b6-158">使用單一 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="646b6-158">Using single cmdlets</span></span>

- <span data-ttu-id="646b6-159">若要建立新的撥號方案，請執行：</span><span class="sxs-lookup"><span data-stu-id="646b6-159">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="646b6-160">如需其他範例和參數，請參閱[新 CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan)。</span><span class="sxs-lookup"><span data-stu-id="646b6-160">For other examples and parameters, see [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="646b6-161">若要編輯現有撥號方案的設定，請執行：</span><span class="sxs-lookup"><span data-stu-id="646b6-161">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="646b6-162">如需其他範例和參數，請參閱[設定 CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan)。</span><span class="sxs-lookup"><span data-stu-id="646b6-162">For other examples and parameters, see [Set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="646b6-163">若要將使用者新增至撥號方案，請執行：</span><span class="sxs-lookup"><span data-stu-id="646b6-163">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="646b6-164">如需其他範例和參數，請參閱[授與 CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan)。</span><span class="sxs-lookup"><span data-stu-id="646b6-164">For other examples and parameters, see [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="646b6-165">若要查看撥號計畫的設定，請執行：</span><span class="sxs-lookup"><span data-stu-id="646b6-165">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="646b6-166">如需其他範例和參數，請參閱[CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="646b6-166">For other examples and parameters, see [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="646b6-167">若要刪除撥號方案，請執行：</span><span class="sxs-lookup"><span data-stu-id="646b6-167">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="646b6-168">如需其他範例和參數，請參閱[移除-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="646b6-168">For other examples and parameters, see [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="646b6-169">若要查看有效撥號方案的設定，請執行：</span><span class="sxs-lookup"><span data-stu-id="646b6-169">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="646b6-170">如需其他範例和參數，請參閱[CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan)。</span><span class="sxs-lookup"><span data-stu-id="646b6-170">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="646b6-171">若要測試撥號方案的有效設定，請執行：</span><span class="sxs-lookup"><span data-stu-id="646b6-171">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="646b6-172">如需其他範例和參數，請參閱[測試 CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="646b6-172">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="646b6-173">使用 PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="646b6-173">Using a PowerShell script</span></span>

<span data-ttu-id="646b6-174">執行此動作以刪除與租使用者撥號方案相關聯的正常化規則，而不需要先刪除租使用者撥號方案：</span><span class="sxs-lookup"><span data-stu-id="646b6-174">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="646b6-175">執行此動作，將下列正常化規則新增至現有的租使用者撥號方案（名為 RedmondDialPlan）。</span><span class="sxs-lookup"><span data-stu-id="646b6-175">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="646b6-176">執行此操作，從現有的租使用者撥號方案（名為 RedmondDialPlan）移除下列正常化規則。</span><span class="sxs-lookup"><span data-stu-id="646b6-176">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="646b6-177">當您想要檢查現有的正常化規則時，請執行下列動作，判斷您想要刪除的規則，然後使用其索引將它移除。</span><span class="sxs-lookup"><span data-stu-id="646b6-177">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="646b6-178">正常化規則陣列從索引0開始。</span><span class="sxs-lookup"><span data-stu-id="646b6-178">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="646b6-179">我們想要移除3位數的正常化規則，以便編制索引1。</span><span class="sxs-lookup"><span data-stu-id="646b6-179">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
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

<span data-ttu-id="646b6-180">執行此工作以找出已授與 RedmondDialPlan 租使用者撥號計畫的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="646b6-180">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="646b6-181">執行此 TenantDialPlan，以移除所有擁有 sipfed.online.lync.com HostingProvider 的使用者指派的任何。</span><span class="sxs-lookup"><span data-stu-id="646b6-181">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq “sipfed.online.lync.com”} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="646b6-182">執行這些程式，將名為 OPDP1 的現有內部部署撥號方案新增為貴組織的租使用者撥號計畫。</span><span class="sxs-lookup"><span data-stu-id="646b6-182">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="646b6-183">您必須先將內部部署撥號計畫儲存為 .xml 檔案，然後再用來建立新的租使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="646b6-183">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="646b6-184">執行此工作以將內部部署撥號計畫儲存到 .xml 檔案。</span><span class="sxs-lookup"><span data-stu-id="646b6-184">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="646b6-185">執行此工作來建立新的租使用者撥號方案。</span><span class="sxs-lookup"><span data-stu-id="646b6-185">Run this to create the new tenant dial plan.</span></span>
  
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
    
## <a name="related-topics"></a><span data-ttu-id="646b6-186">相關主題</span><span class="sxs-lookup"><span data-stu-id="646b6-186">Related topics</span></span>

- [<span data-ttu-id="646b6-187">什麼是撥號對應表？</span><span class="sxs-lookup"><span data-stu-id="646b6-187">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="646b6-188">移轉電話號碼的常見問題</span><span class="sxs-lookup"><span data-stu-id="646b6-188">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)
- [<span data-ttu-id="646b6-189">通話方案所用的不同類型的電話號碼</span><span class="sxs-lookup"><span data-stu-id="646b6-189">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="646b6-190">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="646b6-190">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="646b6-191">緊急通話條款及條件</span><span class="sxs-lookup"><span data-stu-id="646b6-191">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="646b6-192">[緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="646b6-192">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="646b6-193">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="646b6-193">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
