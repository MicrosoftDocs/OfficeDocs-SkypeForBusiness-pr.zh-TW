---
title: Lync Server 2013：指派每一使用者的封存原則
description: Lync Server 2013：指派每一使用者的封存原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c81d7e426f16c298196aba733d720a92d0854bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559989"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="cf96a-103">在 Lync Server 2013 中指派每一使用者的封存原則</span><span class="sxs-lookup"><span data-stu-id="cf96a-103">Assign a per-user archiving policy in Lync Server 2013</span></span>

 


<span data-ttu-id="cf96a-104">封存原則是您可以在 Lync Server 2013 控制台中設定之使用者帳戶的個別設定之一。</span><span class="sxs-lookup"><span data-stu-id="cf96a-104">The archiving policy is one of the individual settings of a user account that you can configure in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="cf96a-105">部署一或多個個別使用者封存原則是選用的。</span><span class="sxs-lookup"><span data-stu-id="cf96a-105">Deploying one or more per-user archiving policies is optional.</span></span> <span data-ttu-id="cf96a-106">您也可以只部署全域層級的封存原則或網站層級的封存原則。</span><span class="sxs-lookup"><span data-stu-id="cf96a-106">You can also deploy only a global-level archiving policy or site-level archiving policy.</span></span> <span data-ttu-id="cf96a-107">如果您選擇部署個別使用者原則，則必須明確指派原則給使用者、群組或連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="cf96a-107">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="cf96a-108">若未指派任何特定的網站層級或個別使用者原則，則封存需求會自動預設為全域層級會議原則中所定義的使用者。</span><span class="sxs-lookup"><span data-stu-id="cf96a-108">Archiving requirements automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="cf96a-109">在建立至少一個個別使用者封存原則之後，請使用本主題中的程式來指派原則，以適當指定特定使用者的內部通訊、外部通訊或兩者，是否會由伺服器進行封存。</span><span class="sxs-lookup"><span data-stu-id="cf96a-109">After creating at least one per-user archiving policy, use the procedures in this topic to assign the policy that appropriately specifies whether a particular user’s internal communications, external communications, or both, will be archived by the server.</span></span>

<span data-ttu-id="cf96a-110">如需建立個別使用者封存原則的詳細資訊，請參閱 [在 Lync Server 2013 中建立封存原則，以針對特定網站或使用者啟用或停用內部或外部通訊](lync-server-2013-create-archiving-policy-sites-users.md)的封存。</span><span class="sxs-lookup"><span data-stu-id="cf96a-110">For details about creating per-user archiving policies, see [Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of Internal or external communications for specific sites or users](lync-server-2013-create-archiving-policy-sites-users.md).</span></span>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="cf96a-111">指派每位使用者的封存原則</span><span class="sxs-lookup"><span data-stu-id="cf96a-111">To assign a per-user archiving policy</span></span>

1.  <span data-ttu-id="cf96a-112">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="cf96a-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cf96a-113">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="cf96a-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cf96a-114">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="cf96a-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cf96a-115">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="cf96a-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="cf96a-116">使用下列其中一種方法，找到使用者：</span><span class="sxs-lookup"><span data-stu-id="cf96a-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="cf96a-117">在 **[搜尋使用者]** 方塊中，輸入該使用者帳戶的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的全部或頭幾個字，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="cf96a-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="cf96a-118">如果有儲存的查詢，請按一下 **[開啟查詢]** 圖示、使用 **[開啟]** 對話方塊擷取查詢 (.usf 檔)，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="cf96a-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="cf96a-119">(選用) 指定其他搜尋條件，縮減結果：</span><span class="sxs-lookup"><span data-stu-id="cf96a-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="cf96a-120">按一下 **[新增篩選]**。</span><span class="sxs-lookup"><span data-stu-id="cf96a-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="cf96a-121">輸入使用者內容，您可以自行輸入或按一下下拉式清單的箭頭以選取內容。</span><span class="sxs-lookup"><span data-stu-id="cf96a-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="cf96a-122">在 **[等於]** 下拉式清單中，按一下運算子 (例如**等於**或**不等於**)。</span><span class="sxs-lookup"><span data-stu-id="cf96a-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="cf96a-123">依據您選取的使用者內容，輸入您要用來篩選搜尋結果的條件，您可以自行輸入或按一下下拉式清單的箭頭。</span><span class="sxs-lookup"><span data-stu-id="cf96a-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="cf96a-124">若要將更多搜尋子句加入至查詢，請按一下 <STRONG>[新增篩選]</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="cf96a-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="cf96a-125">按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="cf96a-125">Click **Find**.</span></span>

6.  <span data-ttu-id="cf96a-126">依序按一下搜尋結果中的某個使用者、**[動作]** 和 **[指派原則]**。</span><span class="sxs-lookup"><span data-stu-id="cf96a-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="cf96a-127">如果您要將相同的個別使用者封存原則套用至多位使用者，請在搜尋結果中選取多位使用者，然後按一下 [ <STRONG>動作</STRONG>]，再按一下 [ <STRONG>指派原則</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="cf96a-127">If you want the same per-user archiving policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="cf96a-128">在 [ **指派原則**] 的 [封存 **原則**] 下，執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="cf96a-128">In **Assign Policies**, under **Archiving policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="cf96a-129">因為有多種可使用 [<STRONG>指派原則</STRONG>] 對話方塊進行設定的原則，所以對話方塊中的每個原則預設會選取 [ <STRONG> &lt; &gt; 保留</STRONG>為]。</span><span class="sxs-lookup"><span data-stu-id="cf96a-129">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="cf96a-130">不變更此設定，即可繼續沿用先前指派給使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="cf96a-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="cf96a-131">允許 Lync Server 2013 自動選擇全域層級原則，或網站層級原則（如果已定義）。</span><span class="sxs-lookup"><span data-stu-id="cf96a-131">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="cf96a-132">按一下您先前在 [封存 **原則** ] 頁面上定義之每一使用者封存原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="cf96a-132">Click the name of a per-user archiving policy you previously defined on the **Archiving Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="cf96a-133">為了協助您判斷應指派哪個原則，在按下原則名稱後，按一下 <STRONG>[檢視]</STRONG> 可以檢視該原則所定義的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="cf96a-133">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="cf96a-134">完成時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="cf96a-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="cf96a-135">使用 Windows PowerShell Cmdlet 指派 Per-User 封存原則</span><span class="sxs-lookup"><span data-stu-id="cf96a-135">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="cf96a-136">您可以使用 Windows PowerShell 和 **Grant-CsArchivingPolicy** Cmdlet 指派每個使用者的封存原則。</span><span class="sxs-lookup"><span data-stu-id="cf96a-136">You can assign per-user archiving policies by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="cf96a-137">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cf96a-137">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cf96a-138">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="cf96a-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="cf96a-139">將每一使用者封存原則指派給單一使用者</span><span class="sxs-lookup"><span data-stu-id="cf96a-139">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="cf96a-140">下列命令將個別使用者封存原則 RedmondArchivingPolicy 指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="cf96a-140">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="cf96a-141">將每一使用者封存原則指派給多個使用者</span><span class="sxs-lookup"><span data-stu-id="cf96a-141">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="cf96a-142">這個命令會將個別使用者的封存原則 RedmondArchivingPolicy 指派給所有在註冊機構集區 atl-cs-001.litwareinc.com 上擁有帳戶的使用者。</span><span class="sxs-lookup"><span data-stu-id="cf96a-142">This command assigns the per-user archiving policy RedmondArchivingPolicy to all the users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="cf96a-143">如需此命令中所使用之 Filter 參數的詳細資訊，請參閱 [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) Cmdlet 的檔。</span><span class="sxs-lookup"><span data-stu-id="cf96a-143">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a><span data-ttu-id="cf96a-144">取消指派個別使用者的封存原則</span><span class="sxs-lookup"><span data-stu-id="cf96a-144">To unassign a per-user archiving policy</span></span>

  - <span data-ttu-id="cf96a-p106">下列命令解除指派任何先前指派給 Ken Myer 的個別使用者封存原則。一旦解除指派個別使用者原則後，系統會自動使用全域原則或其本機網站原則 (如果有的話) 來管理 Ken Myer。網站原則優先順序高於全域原則。</span><span class="sxs-lookup"><span data-stu-id="cf96a-p106">The following command unassigns any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="cf96a-148">如需詳細資訊，請參閱 [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="cf96a-148">For more information, see the help topic for the [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf96a-149">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cf96a-149">See Also</span></span>


[<span data-ttu-id="cf96a-150">在 Lync Server 2013 中建立封存原則，以針對特定網站或使用者啟用或停用內部或外部通訊的封存</span><span class="sxs-lookup"><span data-stu-id="cf96a-150">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for specific sites or users</span></span>](lync-server-2013-create-archiving-policy-sites-users.md)  


[<span data-ttu-id="cf96a-151">在 Lync Server 2013 中指派每一使用者原則</span><span class="sxs-lookup"><span data-stu-id="cf96a-151">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

