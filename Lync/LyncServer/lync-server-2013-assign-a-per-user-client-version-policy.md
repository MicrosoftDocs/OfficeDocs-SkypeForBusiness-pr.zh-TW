---
title: Lync Server 2013：指派每位使用者的用戶端版本原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77b84c4550d44a09e786d09d093e64cbc1901d91
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134459"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="e8921-102">在 Lync Server 2013 中指派每個使用者的用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="e8921-102">Assign a per-user client version policy in Lync Server 2013</span></span>

 


<span data-ttu-id="e8921-103">用戶端版本原則是您可以在 Lync Server 控制台中設定之使用者帳戶的其中一個個別設定。</span><span class="sxs-lookup"><span data-stu-id="e8921-103">The client version policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="e8921-104">部署一或多個個別使用者用戶端版本原則是選用的。</span><span class="sxs-lookup"><span data-stu-id="e8921-104">Deploying one or more per-user client version policies is optional.</span></span> <span data-ttu-id="e8921-105">您也可以只部署全域層級用戶端版本原則，或網站層級或集區層級的用戶端版本原則。</span><span class="sxs-lookup"><span data-stu-id="e8921-105">You can also deploy only a global-level client version policy, or site-level or pool-level client version policies.</span></span> <span data-ttu-id="e8921-106">如果您選擇部署個別使用者原則，則必須明確指派原則給使用者、群組或連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="e8921-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="e8921-107">若未指派任何特定的網站層級、集區層級或個別使用者原則，則允許以 Lync Server 2013 註冊的預設用戶端為全域層級用戶端版本原則中所定義的用戶端。</span><span class="sxs-lookup"><span data-stu-id="e8921-107">When no specific site-level, pool-level, or per-user policy is assigned, the default clients that are allowed to register with Lync Server 2013 are those defined in the global-level client version policy.</span></span>

<span data-ttu-id="e8921-108">至少建立一個個別使用者用戶端版本原則後，請使用本主題中的程式來指派原則，以指定您要允許其註冊 Lync Server 的用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="e8921-108">After creating at least one per-user client version policy, use the procedures in this topic to assign the policy that specifies the client versions that you want to allow to register with Lync Server.</span></span>

<span data-ttu-id="e8921-109">如需建立各使用者用戶端版本原則的詳細資訊，請參閱[指定可用於登入 Lync Server 2013 的用戶端應用程式](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="e8921-109">For details about creating per-user client version policies, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span></span>

## <a name="to-assign-a-per-user-client-version-policy"></a><span data-ttu-id="e8921-110">指派每位使用者的用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="e8921-110">To assign a per-user client version policy</span></span>

1.  <span data-ttu-id="e8921-111">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e8921-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e8921-112">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="e8921-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e8921-113">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="e8921-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e8921-114">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="e8921-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="e8921-115">使用下列其中一種方法，找到使用者：</span><span class="sxs-lookup"><span data-stu-id="e8921-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="e8921-116">在 **[搜尋使用者]** 方塊中，輸入該使用者帳戶的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的全部或頭幾個字，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="e8921-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="e8921-117">如果有儲存的查詢，請按一下 **[開啟查詢]** 圖示、使用 **[開啟]** 對話方塊擷取查詢 (.usf 檔)，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="e8921-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="e8921-118">(選用) 指定其他搜尋條件，縮減結果：</span><span class="sxs-lookup"><span data-stu-id="e8921-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="e8921-119">按一下 **[新增篩選]**。</span><span class="sxs-lookup"><span data-stu-id="e8921-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="e8921-120">輸入使用者內容，您可以自行輸入或按一下下拉式清單的箭頭以選取內容。</span><span class="sxs-lookup"><span data-stu-id="e8921-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="e8921-121">在 **[等於]** 下拉式清單中，按一下運算子 (例如**等於**或**不等於**)。</span><span class="sxs-lookup"><span data-stu-id="e8921-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="e8921-122">依據您選取的使用者內容，輸入您要用來篩選搜尋結果的條件，您可以自行輸入或按一下下拉式清單的箭頭。</span><span class="sxs-lookup"><span data-stu-id="e8921-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="e8921-123">若要將更多搜尋子句加入至查詢，請按一下 <STRONG>[新增篩選]</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="e8921-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="e8921-124">按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="e8921-124">Click **Find**.</span></span>

6.  <span data-ttu-id="e8921-125">依序按一下搜尋結果中的某個使用者、**[動作]** 和 **[指派原則]**。</span><span class="sxs-lookup"><span data-stu-id="e8921-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="e8921-126">如果您要將相同的個別使用者用戶端版本原則套用至多位使用者，請在搜尋結果中選取多位使用者，然後按一下 [<STRONG>動作</STRONG>]，再按一下 [<STRONG>指派原則</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="e8921-126">If you want the same per-user client version policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="e8921-127">在 [**指派原則**] 的 [**用戶端版本原則**] 底下，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="e8921-127">In **Assign Policies**, under **Client version policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="e8921-128">因為有多種可使用 [<STRONG>指派原則</STRONG>] 對話方塊進行設定的原則，所以對話方塊中的每個原則預設會選取 [ <STRONG> &lt; &gt; 保留</STRONG>為]。</span><span class="sxs-lookup"><span data-stu-id="e8921-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="e8921-129">不變更此設定，即可繼續沿用先前指派給使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="e8921-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="e8921-130">允許 Lync Server 自動選擇全域層級原則，或在網站層級原則或集區層級原則（如果有定義）。</span><span class="sxs-lookup"><span data-stu-id="e8921-130">Allow Lync Server to automatically choose either the global-level policy or, if defined, the site-level policy or pool-level policy.</span></span>
    
      - <span data-ttu-id="e8921-131">在 [**用戶端版本原則**] 頁面上，按一下您先前定義的每個使用者用戶端版本原則名稱。</span><span class="sxs-lookup"><span data-stu-id="e8921-131">Click the name of a per-user client version policy you previously defined on the **Client Version Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="e8921-132">為了協助您判斷應指派哪個原則，在按下原則名稱後，按一下 <STRONG>[檢視]</STRONG> 可以檢視該原則所定義的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="e8921-132">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="e8921-133">完成時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e8921-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e8921-134">使用 Windows PowerShell Cmdlet 指派 Per-User 用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="e8921-134">Assigning a Per-User Client Version Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e8921-135">您可以使用授與 Get-csclientversionpolicy 指令程式指派每個使用者的用戶端版本原則。</span><span class="sxs-lookup"><span data-stu-id="e8921-135">You can assign per-user client version policies by using the Grant-CsClientVersionPolicy cmdlet.</span></span> <span data-ttu-id="e8921-136">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e8921-136">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e8921-137">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="e8921-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a><span data-ttu-id="e8921-138">將每一使用者用戶端版本原則指派給單一使用者</span><span class="sxs-lookup"><span data-stu-id="e8921-138">To assign a per-user client version policy to a single user</span></span>

  - <span data-ttu-id="e8921-139">下列命令會將每個使用者的用戶端版本原則 RedmondClientVersionPolicy 指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="e8921-139">The following command assigns the per-user client version policy RedmondClientVersionPolicy to the user Ken Myer.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a><span data-ttu-id="e8921-140">將每位使用者的用戶端版本原則指派給多位使用者</span><span class="sxs-lookup"><span data-stu-id="e8921-140">To assign a per-user client version policy to multiple users</span></span>

  - <span data-ttu-id="e8921-141">此命令會將每位使用者的用戶端版本原則 RedmondClientVersionPolicy 指派給目前已指派語音原則 RedmondVoicePolicy 的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="e8921-141">This command assigns the per-user client version policy RedmondClientVersionPolicy to all the users who are currently assigned the voice policy RedmondVoicePolicy.</span></span> <span data-ttu-id="e8921-142">如需此命令中所使用之 Filter 參數的詳細資訊，請參閱[Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) Cmdlet 的檔。</span><span class="sxs-lookup"><span data-stu-id="e8921-142">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a><span data-ttu-id="e8921-143">取消指派每位使用者的用戶端版本原則</span><span class="sxs-lookup"><span data-stu-id="e8921-143">To unassign a per-user client version policy</span></span>

  - <span data-ttu-id="e8921-144">下列命令 unassigns 先前指派給 Ken Myer 的任何個別使用者用戶端版本原則。</span><span class="sxs-lookup"><span data-stu-id="e8921-144">The following command unassigns any per-user client version policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="e8921-145">未指派每個使用者原則之後，Ken Myer 將會透過全域原則自動進行管理，其本機網站原則 (（如果有的話）) 或指派給他的註冊服務範圍原則。</span><span class="sxs-lookup"><span data-stu-id="e8921-145">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy, his local site policy (if one exists), or the service-scope policy assigned to his Registrar.</span></span> <span data-ttu-id="e8921-146">服務範圍原則的優先順序高於任何網站原則，而網站原則則優先于全域原則。</span><span class="sxs-lookup"><span data-stu-id="e8921-146">A service scope policy takes precedence over any site policy, and a site policy takes precedence over the global policy.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="e8921-147">如需詳細資訊，請參閱[get-csclientversionpolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="e8921-147">For more information, see the help topic for the [Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8921-148">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e8921-148">See Also</span></span>


[<span data-ttu-id="e8921-149">在 Lync Server 2013 中指派每一使用者原則</span><span class="sxs-lookup"><span data-stu-id="e8921-149">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
[<span data-ttu-id="e8921-150">在 Lync Server 2013 中管理裝置、電話及用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="e8921-150">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)

