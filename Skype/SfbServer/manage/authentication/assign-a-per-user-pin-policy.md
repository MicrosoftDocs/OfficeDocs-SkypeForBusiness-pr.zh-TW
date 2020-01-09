---
title: 在商務用 Skype Server 中指派每位使用者的 PIN 原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 摘要：適用于商務用 Skype Server 的 [階段 AV] 和 [OAuth 憑證]。
ms.openlocfilehash: 7591464d55970a9aee4fb1f7ddbb28c2efbac601
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992720"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="e1315-103">在商務用 Skype Server 中指派每位使用者的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="e1315-103">Assign a per-user PIN policy in Skype for Business Server</span></span>

<span data-ttu-id="e1315-104">**摘要：** 針對商務用 Skype Server 階段 AV 和 OAuth 憑證。</span><span class="sxs-lookup"><span data-stu-id="e1315-104">**Summary:** Stage AV and OAuth certificates for Skype for Business Server.</span></span>
  
<span data-ttu-id="e1315-105">電話撥入式會議個人識別碼（PIN）原則是可在商務用 Skype Server [控制台] 中設定的使用者帳戶個人設定之一。</span><span class="sxs-lookup"><span data-stu-id="e1315-105">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="e1315-106">部署一或多個使用者 PIN 原則是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="e1315-106">Deploying one or more per-user PIN policies is optional.</span></span> <span data-ttu-id="e1315-107">您也可以只部署全域層級的 PIN 原則或網站層級的 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="e1315-107">You can also deploy only a global-level PIN policy or site-level PIN policy.</span></span> <span data-ttu-id="e1315-108">如果您要部署每個使用者的原則，您必須將它們明確指派給使用者、群組或連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="e1315-108">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="e1315-109">指派電話撥入式會議 Pin 的使用者權利和許可權，在沒有指派任何特定網站層級或每使用者原則時，系統會自動將預設值設為全域層級 PIN 原則中定義的 Pin。</span><span class="sxs-lookup"><span data-stu-id="e1315-109">User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>
  
<span data-ttu-id="e1315-110">建立至少一個針對每位使用者的 PIN 原則之後，請使用本主題中的程式，指派指定您希望伺服器強加在由特定使用者所建立之 Pin 所產生之限制的原則。</span><span class="sxs-lookup"><span data-stu-id="e1315-110">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="e1315-111">指派每位使用者的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="e1315-111">To assign a per-user PIN policy</span></span>

1. <span data-ttu-id="e1315-112">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e1315-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e1315-113">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="e1315-113">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="e1315-114">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="e1315-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="e1315-115">使用下列其中一種方法來尋找使用者：</span><span class="sxs-lookup"><span data-stu-id="e1315-115">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="e1315-116">在 [**搜尋使用者**] 方塊中，輸入使用者帳戶的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部或第一個部分，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="e1315-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="e1315-117">如果您有已儲存的查詢，請按一下 [**開啟查詢**] 圖示，使用 [**開啟**舊檔] 對話方塊來檢索查詢（usf 檔案），然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="e1315-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="e1315-118">可選指定額外的搜尋準則以縮小結果範圍：</span><span class="sxs-lookup"><span data-stu-id="e1315-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="e1315-119">是.</span><span class="sxs-lookup"><span data-stu-id="e1315-119">a.</span></span> <span data-ttu-id="e1315-120">按一下 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="e1315-120">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="e1315-121">乙.</span><span class="sxs-lookup"><span data-stu-id="e1315-121">b.</span></span> <span data-ttu-id="e1315-122">輸入使用者屬性或按一下下拉式清單中的箭號，以選取該屬性。</span><span class="sxs-lookup"><span data-stu-id="e1315-122">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="e1315-123">c-clip.</span><span class="sxs-lookup"><span data-stu-id="e1315-123">c.</span></span> <span data-ttu-id="e1315-124">在 [**等於**] 下拉式清單中，按一下運算子（例如 [**等於**] 或 [**不等於**]）。</span><span class="sxs-lookup"><span data-stu-id="e1315-124">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="e1315-125">希望.</span><span class="sxs-lookup"><span data-stu-id="e1315-125">d.</span></span> <span data-ttu-id="e1315-126">根據您所選取的使用者屬性，輸入您想要用來篩選搜尋結果的準則，只要輸入，或按一下下拉式清單中的箭號即可。</span><span class="sxs-lookup"><span data-stu-id="e1315-126">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e1315-127">若要新增其他搜尋子句至您的查詢，請按一下 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="e1315-127">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="e1315-128">e.</span><span class="sxs-lookup"><span data-stu-id="e1315-128">e.</span></span> <span data-ttu-id="e1315-129">按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="e1315-129">Click **Find**.</span></span>
    
6. <span data-ttu-id="e1315-130">在搜尋結果中按一下使用者，按一下 [**動作**]，然後按一下 [**指派原則**]。</span><span class="sxs-lookup"><span data-stu-id="e1315-130">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e1315-131">如果您想要將相同的每個使用者 PIN 原則套用到多個使用者，請在搜尋結果中選取多位使用者，然後按一下 [**動作**]，再按一下 [**指派原則**]。</span><span class="sxs-lookup"><span data-stu-id="e1315-131">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click **Actions**, and then click **Assign policies**.</span></span> 
  
7. <span data-ttu-id="e1315-132">在 [**指派原則**] 的 [ **PIN 原則**] 底下，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="e1315-132">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e1315-133">因為您可以使用 [**指派原則**] 對話方塊來設定多個原則， \*\* \< \> \*\*所以對話方塊中的每個原則預設都會選取 [持續保持為]。</span><span class="sxs-lookup"><span data-stu-id="e1315-133">Because there are multiple policies that you can configure by using the **Assign Policies** dialog box, **\<Keep as is\>** is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="e1315-134">針對此設定不做任何變更，即可繼續使用先前指派給使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="e1315-134">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>
  
   - <span data-ttu-id="e1315-135">[允許商務用 Skype 伺服器] 自動選擇 [全域層級原則] 或 [（如果已定義）] 網站層級原則。</span><span class="sxs-lookup"><span data-stu-id="e1315-135">Allow Skype for Business Server to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
   - <span data-ttu-id="e1315-136">按一下您先前在 [ **PIN 策略**] 頁面上定義之每個使用者 PIN 原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="e1315-136">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
    
     > [!TIP]
     > <span data-ttu-id="e1315-137">若要協助您決定要指派的原則，請在您按一下策略名稱之後，按一下 [View] （**查看**），以查看原則中定義的使用者權利和許可權。</span><span class="sxs-lookup"><span data-stu-id="e1315-137">To help you decide the policy you want to assign, after you click a policy name, click **View** to view the user rights and permissions defined in the policy.</span></span>
  
8. <span data-ttu-id="e1315-138">完成後，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e1315-138">When you are finished, click **OK**.</span></span>
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e1315-139">使用 Windows PowerShell Cmdlet 指派每個使用者的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="e1315-139">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e1315-140">您可以使用 Windows PowerShell 和**Grant CsPinPolicy** Cmdlet 來指派每個使用者的 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="e1315-140">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="e1315-141">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e1315-141">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e1315-142">如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="e1315-142">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="e1315-143">在商務用 Skype 伺服器中，程式是一樣的。</span><span class="sxs-lookup"><span data-stu-id="e1315-143">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="e1315-144">將每位使用者 PIN 原則指派給單一使用者</span><span class="sxs-lookup"><span data-stu-id="e1315-144">To assign a per-user PIN policy to a single user</span></span>

- <span data-ttu-id="e1315-145">下列命令會將每個使用者的 PIN 原則 RedmondPinPolicy 指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="e1315-145">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="e1315-146">將每位使用者 PIN 原則指派給多個使用者</span><span class="sxs-lookup"><span data-stu-id="e1315-146">To assign a per-user PIN policy to multiple users</span></span>

- <span data-ttu-id="e1315-147">下列命令會將每位使用者的 PIN 原則 RedmondUsersPinPolicy 指派給所有在雷蒙德市中工作的使用者。</span><span class="sxs-lookup"><span data-stu-id="e1315-147">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="e1315-148">如需此命令中使用之 LdapFilter 參數的詳細資訊，請參閱[move-csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="e1315-148">For details about the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="e1315-149">若要取消指派每位使用者的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="e1315-149">To unassign a per-user PIN policy</span></span>

- <span data-ttu-id="e1315-150">下列命令會以前指派給 Ken Myer 的任何每使用者 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="e1315-150">The following command unassigns any per-user PIN policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="e1315-151">未指派每個使用者原則時，會使用全域原則（如果有的話）自動管理 Ken Myer，或在其本機網站原則中使用。</span><span class="sxs-lookup"><span data-stu-id="e1315-151">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="e1315-152">網站原則的優先順序高於全域原則。</span><span class="sxs-lookup"><span data-stu-id="e1315-152">A site policy takes precedence over the global policy.</span></span>
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

<span data-ttu-id="e1315-153">如需詳細資訊，請參閱[授與 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="e1315-153">For details, see [Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e1315-154">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e1315-154">See also</span></span>

[<span data-ttu-id="e1315-155">在商務用 Skype Server 中建立新的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="e1315-155">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)
