---
title: 在商務用 Skype Server 中指派每個使用者的 PIN 原則
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 摘要：為商務用 Skype Server 階段 AV 和 OAuth 憑證。
ms.openlocfilehash: 6a0d0a1824e809a70dfee419fb5da1f663d8d779
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828523"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="54be7-103">在商務用 Skype Server 中指派每個使用者的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="54be7-103">Assign a per-user PIN policy in Skype for Business Server</span></span>

<span data-ttu-id="54be7-104">**摘要：** 階段 AV 和 OAuth 商務用 Skype Server 的憑證。</span><span class="sxs-lookup"><span data-stu-id="54be7-104">**Summary:** Stage AV and OAuth certificates for Skype for Business Server.</span></span>
  
<span data-ttu-id="54be7-105">電話撥入式會議個人身分識別號碼 (PIN) 原則是可在商務用 Skype Server 控制台中設定之使用者帳戶的個別設定之一。</span><span class="sxs-lookup"><span data-stu-id="54be7-105">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="54be7-106">部署一或多個個別使用者 PIN 碼原則是選用的。</span><span class="sxs-lookup"><span data-stu-id="54be7-106">Deploying one or more per-user PIN policies is optional.</span></span> <span data-ttu-id="54be7-107">您也可以只部署全域層級的 PIN 原則或網站層級的 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="54be7-107">You can also deploy only a global-level PIN policy or site-level PIN policy.</span></span> <span data-ttu-id="54be7-108">如果您選擇部署個別使用者原則，則必須明確指派原則給使用者、群組或連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="54be7-108">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="54be7-109">在未指派任何特定的網站層級或個別使用者原則時，自動將電話撥入式會議 Pin 使用之 Pin 的使用者權利和許可權預設設為全域層級 PIN 原則中所定義的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="54be7-109">User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>
  
<span data-ttu-id="54be7-110">在建立至少一個個別使用者 PIN 原則之後，請使用本主題中的程式來指派原則，以指定您想要讓伺服器強加于特定使用者所建立及使用之 Pin 的限制。</span><span class="sxs-lookup"><span data-stu-id="54be7-110">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="54be7-111">若要指派每個使用者的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="54be7-111">To assign a per-user PIN policy</span></span>

1. <span data-ttu-id="54be7-112">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="54be7-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="54be7-113">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="54be7-113">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="54be7-114">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="54be7-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="54be7-115">使用下列其中一種方法，找到使用者：</span><span class="sxs-lookup"><span data-stu-id="54be7-115">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="54be7-116">在 **[搜尋使用者]** 方塊中，輸入該使用者帳戶的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的全部或頭幾個字，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="54be7-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="54be7-117">如果有儲存的查詢，請按一下 **[開啟查詢]** 圖示、使用 **[開啟]** 對話方塊擷取查詢 (.usf 檔)，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="54be7-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="54be7-118">(選用) 指定其他搜尋條件，縮減結果：</span><span class="sxs-lookup"><span data-stu-id="54be7-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="54be7-119">a.</span><span class="sxs-lookup"><span data-stu-id="54be7-119">a.</span></span> <span data-ttu-id="54be7-120">按一下 **[新增篩選]**。</span><span class="sxs-lookup"><span data-stu-id="54be7-120">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="54be7-121">b.</span><span class="sxs-lookup"><span data-stu-id="54be7-121">b.</span></span> <span data-ttu-id="54be7-122">輸入使用者內容，您可以自行輸入或按一下下拉式清單的箭頭以選取內容。</span><span class="sxs-lookup"><span data-stu-id="54be7-122">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="54be7-123">c.</span><span class="sxs-lookup"><span data-stu-id="54be7-123">c.</span></span> <span data-ttu-id="54be7-124">在 **[等於]** 下拉式清單中，按一下運算子 (例如 **等於** 或 **不等於**)。</span><span class="sxs-lookup"><span data-stu-id="54be7-124">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="54be7-125">d.</span><span class="sxs-lookup"><span data-stu-id="54be7-125">d.</span></span> <span data-ttu-id="54be7-126">依據您選取的使用者內容，輸入您要用來篩選搜尋結果的條件，您可以自行輸入或按一下下拉式清單的箭頭。</span><span class="sxs-lookup"><span data-stu-id="54be7-126">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="54be7-127">若要將更多搜尋子句加入至查詢，請按一下 **[新增篩選]**。</span><span class="sxs-lookup"><span data-stu-id="54be7-127">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="54be7-128">e.</span><span class="sxs-lookup"><span data-stu-id="54be7-128">e.</span></span> <span data-ttu-id="54be7-129">按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="54be7-129">Click **Find**.</span></span>
    
6. <span data-ttu-id="54be7-130">依序按一下搜尋結果中的某個使用者、**[動作]** 和 **[指派原則]**。</span><span class="sxs-lookup"><span data-stu-id="54be7-130">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="54be7-131">如果您要將相同的個別使用者 PIN 原則套用至多位使用者，請在搜尋結果中選取多位使用者，然後按一下 [ **動作**]，再按一下 [ **指派原則**]。</span><span class="sxs-lookup"><span data-stu-id="54be7-131">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click **Actions**, and then click **Assign policies**.</span></span> 
  
7. <span data-ttu-id="54be7-132">在 [ **指派原則**] 的 [ **PIN 原則**] 底下，執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="54be7-132">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="54be7-133">因為有多種可使用 [ **指派原則** ] 對話方塊進行設定的原則，所以 **\<Keep as is\>** 預設會選取對話方塊中的每個原則。</span><span class="sxs-lookup"><span data-stu-id="54be7-133">Because there are multiple policies that you can configure by using the **Assign Policies** dialog box, **\<Keep as is\>** is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="54be7-134">不變更此設定，即可繼續沿用先前指派給使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="54be7-134">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>
  
   - <span data-ttu-id="54be7-135">允許商務用 Skype 伺服器自動選擇全域層級原則，或在網站層級原則（如果有定義）。</span><span class="sxs-lookup"><span data-stu-id="54be7-135">Allow Skype for Business Server to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
   - <span data-ttu-id="54be7-136">按一下您先前在 [ **PIN 原則** ] 頁面上定義之個別使用者 PIN 原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="54be7-136">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
    
     > [!TIP]
     > <span data-ttu-id="54be7-137">為了協助您判斷應指派哪個原則，在按下原則名稱後，按一下 **[檢視]** 可以檢視該原則所定義的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="54be7-137">To help you decide the policy you want to assign, after you click a policy name, click **View** to view the user rights and permissions defined in the policy.</span></span>
  
8. <span data-ttu-id="54be7-138">完成時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="54be7-138">When you are finished, click **OK**.</span></span>
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="54be7-139">使用 Windows PowerShell Cmdlet 指派 Per-User PIN 原則</span><span class="sxs-lookup"><span data-stu-id="54be7-139">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="54be7-140">您可以使用 Windows PowerShell 和 **get-cspinpolicy 指令程式** 指派每個使用者的 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="54be7-140">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="54be7-141">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端工作階段執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="54be7-141">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="54be7-142">如需使用遠端 Windows PowerShell 連線到商務用 Skype 伺服器的詳細資訊，請參閱博客文章 [：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="54be7-142">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="54be7-143">商務用 Skype Server 中的程式相同。</span><span class="sxs-lookup"><span data-stu-id="54be7-143">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="54be7-144">將每一使用者 PIN 原則指派給單一使用者</span><span class="sxs-lookup"><span data-stu-id="54be7-144">To assign a per-user PIN policy to a single user</span></span>

- <span data-ttu-id="54be7-145">下列命令會將每位使用者 PIN 原則 RedmondPinPolicy 指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="54be7-145">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="54be7-146">將每一使用者 PIN 原則指派給多個使用者</span><span class="sxs-lookup"><span data-stu-id="54be7-146">To assign a per-user PIN policy to multiple users</span></span>

- <span data-ttu-id="54be7-147">下列命令會將個別使用者 PIN 原則 RedmondUsersPinPolicy 指派給 Redmond 的城市中所有工作的使用者。</span><span class="sxs-lookup"><span data-stu-id="54be7-147">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="54be7-148">如需此命令中使用之 LdapFilter 參數的詳細資訊，請參閱 [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="54be7-148">For details about the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="54be7-149">取消指派每個使用者的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="54be7-149">To unassign a per-user PIN policy</span></span>

- <span data-ttu-id="54be7-150">下列命令 unassigns 先前指派給 Ken Myer 的任何個別使用者 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="54be7-150">The following command unassigns any per-user PIN policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="54be7-151">一旦解除指派個別使用者原則後，系統會自動使用全域原則或其本機網站原則 (如果有的話) 來管理 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="54be7-151">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="54be7-152">網站原則優先順序高於全域原則。</span><span class="sxs-lookup"><span data-stu-id="54be7-152">A site policy takes precedence over the global policy.</span></span>
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

<span data-ttu-id="54be7-153">如需詳細資訊，請參閱 [授與 get-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="54be7-153">For details, see [Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="54be7-154">另請參閱</span><span class="sxs-lookup"><span data-stu-id="54be7-154">See also</span></span>

[<span data-ttu-id="54be7-155">在商務用 Skype Server 中建立新的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="54be7-155">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)
