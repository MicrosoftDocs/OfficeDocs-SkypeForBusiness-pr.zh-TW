---
title: Lync Server 2013：指派每個使用者的會議原則
description: Lync Server 2013：指派每個使用者的會議原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user conferencing policy
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521015(v=OCS.15)
ms:contentKeyID: 48184475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 819d1431a2a7a921ff8c306c47c8b5f86bf5d5bb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559919"
---
# <a name="assign-a-per-user-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="2cf81-103">在 Lync Server 2013 中指派每個使用者的會議原則</span><span class="sxs-lookup"><span data-stu-id="2cf81-103">Assign a per-user conferencing policy in Lync Server 2013</span></span>

 


<span data-ttu-id="2cf81-104">會議原則是您可以在 Lync Server 控制台中設定之使用者帳戶的其中一個個別設定。</span><span class="sxs-lookup"><span data-stu-id="2cf81-104">The conferencing policy is one of the individual settings of a user account that you can configure in Lync Server Control Panel.</span></span>

<span data-ttu-id="2cf81-p101">您可以選擇部署一或多個個別使用者會議原則。您也可以只部署一個全域層級會議原則或網站層級會議原則。如果您選擇部署個別使用者原則，則必須明確指派原則給使用者、群組或連絡人物件。未指派特定網站層級或個別使用者原則時，會議使用者權限會自動預設為全域層級會議原則中定義的權限。</span><span class="sxs-lookup"><span data-stu-id="2cf81-p101">Deploying one or more per-user conferencing policies is optional. You can also deploy only a global-level conferencing policy or site-level conferencing policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects. Conferencing user rights and permissions automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="2cf81-109">至少建立一個個別使用者會議原則之後，請使用本主題中的程序來指派原則，此原則指定想要伺服器授與特定使用者所召集之會議的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="2cf81-109">After creating at least one per-user conferencing policy, use the procedures in this topic to assign the policy that specifies the user rights and permissions that you want the server to grant to the meetings organized by a particular user.</span></span>

<span data-ttu-id="2cf81-110">如需所有可用之會議原則設定的清單，請參閱 [Lync Server 2013 的會議原則設定參考](lync-server-2013-conferencing-policy-settings-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="2cf81-110">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<span data-ttu-id="2cf81-111">如需建立會議原則的詳細資訊，請參閱 [建立或修改 Lync Server 2013 中的會議原則](lync-server-2013-create-or-modify-a-conferencing-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="2cf81-111">For details about creating conferencing policies, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span>

## <a name="to-assign-a-per-user-conferencing-policy"></a><span data-ttu-id="2cf81-112">指派個別使用者會議原則</span><span class="sxs-lookup"><span data-stu-id="2cf81-112">To assign a per-user conferencing policy</span></span>

1.  <span data-ttu-id="2cf81-113">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="2cf81-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2cf81-114">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="2cf81-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2cf81-115">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="2cf81-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2cf81-116">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="2cf81-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="2cf81-117">使用下列其中一種方法，找到使用者：</span><span class="sxs-lookup"><span data-stu-id="2cf81-117">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="2cf81-118">在 **[搜尋使用者]** 方塊中，輸入該使用者帳戶的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的全部或頭幾個字，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="2cf81-118">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="2cf81-119">如果有儲存的查詢，請按一下 **[開啟查詢]** 圖示、使用 **[開啟]** 對話方塊擷取查詢 (.usf 檔)，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="2cf81-119">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="2cf81-120">(選用) 指定其他搜尋條件，縮減結果：</span><span class="sxs-lookup"><span data-stu-id="2cf81-120">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="2cf81-121">按一下 **[新增篩選]**。</span><span class="sxs-lookup"><span data-stu-id="2cf81-121">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="2cf81-122">輸入使用者內容，您可以自行輸入或按一下下拉式清單的箭頭以選取內容。</span><span class="sxs-lookup"><span data-stu-id="2cf81-122">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="2cf81-123">在 **[等於]** 下拉式清單中，按一下運算子 (例如**等於**或**不等於**)。</span><span class="sxs-lookup"><span data-stu-id="2cf81-123">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="2cf81-124">依據您選取的使用者內容，輸入您要用來篩選搜尋結果的條件，您可以自行輸入或按一下下拉式清單的箭頭。</span><span class="sxs-lookup"><span data-stu-id="2cf81-124">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="2cf81-125">若要將更多搜尋子句加入至查詢，請按一下 <STRONG>[新增篩選]</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="2cf81-125">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="2cf81-126">按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="2cf81-126">Click **Find**.</span></span>

6.  <span data-ttu-id="2cf81-127">依序按一下搜尋結果中的某個使用者、**[動作]** 和 **[指派原則]**。</span><span class="sxs-lookup"><span data-stu-id="2cf81-127">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="2cf81-128">如果想將同一個個別使用者會議原則套用至多位使用者，請在搜尋結果中選取多位使用者，然後依序按一下<STRONG>[動作]</STRONG> 和 <STRONG>[指派原則]</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="2cf81-128">If you want the same per-user conferencing policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="2cf81-129">在 **[指派原則]** 的 **[會議原則]** 下方，執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="2cf81-129">In **Assign Policies**, under **Conferencing policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="2cf81-130">因為您可以在 [<STRONG>指派原則</STRONG>] 中設定多個原則，所以對話方塊中的每個原則預設會選取 [ <STRONG> &lt; &gt; 保留</STRONG>為]。</span><span class="sxs-lookup"><span data-stu-id="2cf81-130">Because there are multiple policies that you can configure in <STRONG>Assign Policies</STRONG>, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="2cf81-131">不變更此設定，即可繼續沿用先前指派給使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="2cf81-131">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="2cf81-132">選取 **\<Automatic\>** 此項可讓 Lync Server 2013 自動選擇全域層級原則或網站層級原則（如果已定義）。</span><span class="sxs-lookup"><span data-stu-id="2cf81-132">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="2cf81-133">按一下先前在 **[會議原則]** 頁面上定義的個別使用者會議原則名稱。</span><span class="sxs-lookup"><span data-stu-id="2cf81-133">Click the name of a per-user conferencing policy you previously defined on the **Conferencing Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="2cf81-134">為了協助您判斷應指派哪個原則，在按下原則名稱後，按一下 <STRONG>[檢視]</STRONG> 可以檢視該原則所定義的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="2cf81-134">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="2cf81-135">完成時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="2cf81-135">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-conferencing-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2cf81-136">使用 Windows PowerShell Cmdlet 指派 Per-User 會議原則</span><span class="sxs-lookup"><span data-stu-id="2cf81-136">Assigning a Per-User Conferencing Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2cf81-137">您可以使用 Windows PowerShell 和 Grant-CsConferencingPolicy Cmdlet 指派每個使用者的會議原則。</span><span class="sxs-lookup"><span data-stu-id="2cf81-137">Per-user conferencing policies can be assigned by using Windows PowerShell and the Grant-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="2cf81-138">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2cf81-138">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2cf81-139">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="2cf81-139">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-conferencing-policy-to-a-single-user"></a><span data-ttu-id="2cf81-140">將每一使用者會議原則指派給單一使用者</span><span class="sxs-lookup"><span data-stu-id="2cf81-140">To assign a per-user conferencing policy to a single user</span></span>

  - <span data-ttu-id="2cf81-141">下列命令可將個別使用者會議原則 RedmondConferencingPolicy 指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="2cf81-141">The following command assigns the per-user conferencing policy RedmondConferencingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## <a name="to-assign-a-per-user-conferencing-policy-to-multiple-users"></a><span data-ttu-id="2cf81-142">將每一使用者會議原則指派給多位使用者</span><span class="sxs-lookup"><span data-stu-id="2cf81-142">To assign a per-user conferencing policy to multiple users</span></span>

  - <span data-ttu-id="2cf81-143">此命令可將個別使用者會議原則 HRConferencingPolicy，指派給所有任職於人力資源部門的使用者。</span><span class="sxs-lookup"><span data-stu-id="2cf81-143">This command assigns the per-user conferencing policy HRConferencingPolicy to all the users who work for the Human Resources department.</span></span> <span data-ttu-id="2cf81-144">如需此命令中所用 LdapFilter 參數的詳細資訊，請參閱 [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) Cmdlet 的檔。</span><span class="sxs-lookup"><span data-stu-id="2cf81-144">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## <a name="to-unassign-a-per-user-conferencing-policy"></a><span data-ttu-id="2cf81-145">取消指派個別使用者會議原則</span><span class="sxs-lookup"><span data-stu-id="2cf81-145">To unassign a per-user conferencing policy</span></span>

  - <span data-ttu-id="2cf81-p106">下列命令可將先前指派給 Ken Myer 的任何個別使用者會議原則予以解除指派。一旦解除指派個別使用者原則，即會自動使用全域原則或其本機網站原則 (如果存在的話) 來管理 Ken Myer。網站原則的優先順序高於全域原則。</span><span class="sxs-lookup"><span data-stu-id="2cf81-p106">The following command unassigns any per-user conferencing policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="2cf81-149">如需詳細資訊，請參閱 [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\)) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="2cf81-149">For more information, see the help topic for the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="2cf81-150">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2cf81-150">See Also</span></span>


[<span data-ttu-id="2cf81-151">在 Lync Server 2013 中建立或修改會議原則</span><span class="sxs-lookup"><span data-stu-id="2cf81-151">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)  


[<span data-ttu-id="2cf81-152">在 Lync Server 2013 中指派每一使用者原則</span><span class="sxs-lookup"><span data-stu-id="2cf81-152">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

