---
title: Lync Server 2013：指派每個使用者的會議原則
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
ms.openlocfilehash: 0d43bf1663a475bed93985b2257eefaaa07ff8c0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738363"
---
# <a name="assign-a-per-user-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="9626b-102">在 Lync Server 2013 中指派每使用者會議原則</span><span class="sxs-lookup"><span data-stu-id="9626b-102">Assign a per-user conferencing policy in Lync Server 2013</span></span>

 


<span data-ttu-id="9626b-103">[會議原則] 是您可以在 Lync Server [控制台] 中設定之使用者帳戶的個別設定之一。</span><span class="sxs-lookup"><span data-stu-id="9626b-103">The conferencing policy is one of the individual settings of a user account that you can configure in Lync Server Control Panel.</span></span>

<span data-ttu-id="9626b-104">部署一或多個使用者會議原則是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="9626b-104">Deploying one or more per-user conferencing policies is optional.</span></span> <span data-ttu-id="9626b-105">您也可以只部署全域層式會議原則或網站層級會議原則。</span><span class="sxs-lookup"><span data-stu-id="9626b-105">You can also deploy only a global-level conferencing policy or site-level conferencing policy.</span></span> <span data-ttu-id="9626b-106">如果您要部署每個使用者的原則，您必須將它們明確指派給使用者、群組或連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="9626b-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects.</span></span> <span data-ttu-id="9626b-107">如果沒有指派特定的網站層級或每使用者原則，會議使用者權利和許可權會自動預設為全域層會議原則中定義的使用者。</span><span class="sxs-lookup"><span data-stu-id="9626b-107">Conferencing user rights and permissions automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="9626b-108">建立至少一個每使用者會議原則之後，請使用本主題中的程式，指派指定您希望伺服器授與特定使用者所組織之會議的使用者權利和許可權的原則。</span><span class="sxs-lookup"><span data-stu-id="9626b-108">After creating at least one per-user conferencing policy, use the procedures in this topic to assign the policy that specifies the user rights and permissions that you want the server to grant to the meetings organized by a particular user.</span></span>

<span data-ttu-id="9626b-109">如需所有可用會議原則設定的清單，請參閱[Lync Server 2013 的會議原則設定參考](lync-server-2013-conferencing-policy-settings-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="9626b-109">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<span data-ttu-id="9626b-110">如需建立會議原則的詳細資訊，請參閱[在 Lync Server 2013 中建立或修改會議原則](lync-server-2013-create-or-modify-a-conferencing-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="9626b-110">For details about creating conferencing policies, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span>

## <a name="to-assign-a-per-user-conferencing-policy"></a><span data-ttu-id="9626b-111">指派每個使用者的會議原則</span><span class="sxs-lookup"><span data-stu-id="9626b-111">To assign a per-user conferencing policy</span></span>

1.  <span data-ttu-id="9626b-112">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="9626b-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9626b-113">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="9626b-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9626b-114">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="9626b-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9626b-115">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="9626b-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="9626b-116">使用下列其中一種方法來尋找使用者：</span><span class="sxs-lookup"><span data-stu-id="9626b-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="9626b-117">在 [**搜尋使用者**] 方塊中，輸入使用者帳戶的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部或第一個部分，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="9626b-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="9626b-118">如果您有已儲存的查詢，請按一下 [**開啟查詢**] 圖示，使用 [**開啟**舊檔] 對話方塊來檢索查詢（usf 檔案），然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="9626b-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="9626b-119">可選指定額外的搜尋準則以縮小結果範圍：</span><span class="sxs-lookup"><span data-stu-id="9626b-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="9626b-120">按一下 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="9626b-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="9626b-121">輸入使用者屬性或按一下下拉式清單中的箭號，以選取該屬性。</span><span class="sxs-lookup"><span data-stu-id="9626b-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="9626b-122">在 [**等於**] 下拉式清單中，按一下運算子（例如 [**等於**] 或 [**不等於**]）。</span><span class="sxs-lookup"><span data-stu-id="9626b-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="9626b-123">根據您所選取的使用者屬性，輸入您想要用來篩選搜尋結果的準則，只要輸入，或按一下下拉式清單中的箭號即可。</span><span class="sxs-lookup"><span data-stu-id="9626b-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="9626b-124">若要新增其他搜尋子句至您的查詢，請按一下 [<STRONG>新增篩選</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="9626b-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="9626b-125">按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="9626b-125">Click **Find**.</span></span>

6.  <span data-ttu-id="9626b-126">在搜尋結果中按一下使用者，按一下 [**動作**]，然後按一下 [**指派原則**]。</span><span class="sxs-lookup"><span data-stu-id="9626b-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="9626b-127">如果您想要將相同的每個使用者會議原則套用至多個使用者，請在搜尋結果中選取多位使用者，然後按一下 [<STRONG>動作</STRONG>]，再按一下 [<STRONG>指派原則</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="9626b-127">If you want the same per-user conferencing policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="9626b-128">在 [**指派原則**] 的 [**會議原則**] 底下，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="9626b-128">In **Assign Policies**, under **Conferencing policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="9626b-129">因為您可以在<STRONG>指派原則</STRONG>中設定多個原則， <STRONG> &lt; &gt; </STRONG>所以預設會為對話方塊中的每個原則選取 [保留為]。</span><span class="sxs-lookup"><span data-stu-id="9626b-129">Because there are multiple policies that you can configure in <STRONG>Assign Policies</STRONG>, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="9626b-130">針對此設定不做任何變更，即可繼續使用先前指派給使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="9626b-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="9626b-131">選取\*\* \<[\>自動\*\*]，讓 Lync Server 2013 自動選擇 [全域階層原則] 或 [（如果已定義）] 網站層級原則。</span><span class="sxs-lookup"><span data-stu-id="9626b-131">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="9626b-132">按一下您先前在 [**會議原則**] 頁面上定義的每個使用者會議原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="9626b-132">Click the name of a per-user conferencing policy you previously defined on the **Conferencing Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="9626b-133">若要協助您決定要指派的原則，請在您按一下策略名稱之後，按一下 [View] （<STRONG>查看</STRONG>），以查看原則中定義的使用者權利和許可權。</span><span class="sxs-lookup"><span data-stu-id="9626b-133">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="9626b-134">完成後，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="9626b-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-conferencing-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9626b-135">使用 Windows PowerShell Cmdlet 指派每使用者會議原則</span><span class="sxs-lookup"><span data-stu-id="9626b-135">Assigning a Per-User Conferencing Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9626b-136">您可以使用 Windows PowerShell 和 Grant CsConferencingPolicy Cmdlet 來指派每使用者會議原則。</span><span class="sxs-lookup"><span data-stu-id="9626b-136">Per-user conferencing policies can be assigned by using Windows PowerShell and the Grant-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="9626b-137">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="9626b-137">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9626b-138">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="9626b-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-conferencing-policy-to-a-single-user"></a><span data-ttu-id="9626b-139">將每個使用者的會議原則指派給單一使用者</span><span class="sxs-lookup"><span data-stu-id="9626b-139">To assign a per-user conferencing policy to a single user</span></span>

  - <span data-ttu-id="9626b-140">下列命令會將每個使用者的會議原則 RedmondConferencingPolicy 指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="9626b-140">The following command assigns the per-user conferencing policy RedmondConferencingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## <a name="to-assign-a-per-user-conferencing-policy-to-multiple-users"></a><span data-ttu-id="9626b-141">將每個使用者的會議原則指派給多個使用者</span><span class="sxs-lookup"><span data-stu-id="9626b-141">To assign a per-user conferencing policy to multiple users</span></span>

  - <span data-ttu-id="9626b-142">這個命令會將每個使用者的會議原則 HRConferencingPolicy 指派給所有工作人力資源部門的使用者。</span><span class="sxs-lookup"><span data-stu-id="9626b-142">This command assigns the per-user conferencing policy HRConferencingPolicy to all the users who work for the Human Resources department.</span></span> <span data-ttu-id="9626b-143">如需此命令中使用之 LdapFilter 參數的詳細資訊，請參閱[move-csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) Cmdlet 的相關檔。</span><span class="sxs-lookup"><span data-stu-id="9626b-143">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## <a name="to-unassign-a-per-user-conferencing-policy"></a><span data-ttu-id="9626b-144">若要取消指派每個使用者的會議原則</span><span class="sxs-lookup"><span data-stu-id="9626b-144">To unassign a per-user conferencing policy</span></span>

  - <span data-ttu-id="9626b-145">下列命令會先前指派給 Ken Myer 的任何每使用者會議原則。</span><span class="sxs-lookup"><span data-stu-id="9626b-145">The following command unassigns any per-user conferencing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="9626b-146">未指派每個使用者原則時，會使用全域原則（如果有的話）自動管理 Ken Myer，或在其本機網站原則中使用。</span><span class="sxs-lookup"><span data-stu-id="9626b-146">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="9626b-147">網站原則的優先順序高於全域原則。</span><span class="sxs-lookup"><span data-stu-id="9626b-147">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="9626b-148">如需詳細資訊，請參閱[Grant CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\)) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="9626b-148">For more information, see the help topic for the [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="9626b-149">請參閱</span><span class="sxs-lookup"><span data-stu-id="9626b-149">See Also</span></span>


[<span data-ttu-id="9626b-150">在 Lync Server 2013 中建立或修改會議原則</span><span class="sxs-lookup"><span data-stu-id="9626b-150">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)  


[<span data-ttu-id="9626b-151">在 Lync Server 2013 中指派每個使用者的原則</span><span class="sxs-lookup"><span data-stu-id="9626b-151">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

