---
title: Lync Server 2013：指派每個使用者的行動性原則
description: Lync Server 2013：指派每個使用者的行動性原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user mobility policy
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49733836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b17c58cf3477002a7fa43035b72c77963663316
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559829"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="2a80d-103">在 Lync Server 2013 中指派每個使用者的行動性原則</span><span class="sxs-lookup"><span data-stu-id="2a80d-103">Assign a per-user mobility policy in Lync Server 2013</span></span>

 


<span data-ttu-id="2a80d-104">行動性原則是您可以在 Lync Server 控制台或 Lync Server 管理命令介面中設定之使用者帳戶的其中一個個別設定。</span><span class="sxs-lookup"><span data-stu-id="2a80d-104">The mobility policy is one of the individual settings of a user account that you can configure in Lync Server Control Panel or Lync Server Management Shell.</span></span>

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="2a80d-105">使用 Lync Server 控制台指派每個使用者的行動性原則</span><span class="sxs-lookup"><span data-stu-id="2a80d-105">To assign a per-user mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="2a80d-106">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="2a80d-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2a80d-107">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="2a80d-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2a80d-108">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="2a80d-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2a80d-109">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="2a80d-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="2a80d-110">使用下列其中一種方法，找到使用者：</span><span class="sxs-lookup"><span data-stu-id="2a80d-110">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="2a80d-111">在 **[搜尋使用者]** 方塊中，輸入該使用者帳戶的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的全部或頭幾個字，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="2a80d-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="2a80d-112">如果有儲存的查詢，請按一下 **[開啟查詢]** 圖示、使用 **[開啟]** 對話方塊擷取查詢 (.usf 檔)，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="2a80d-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="2a80d-113">(選用) 指定其他搜尋條件，縮減結果：</span><span class="sxs-lookup"><span data-stu-id="2a80d-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="2a80d-114">按一下 **[新增篩選]**。</span><span class="sxs-lookup"><span data-stu-id="2a80d-114">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="2a80d-115">輸入使用者內容，您可以自行輸入或按一下下拉式清單的箭頭以選取內容。</span><span class="sxs-lookup"><span data-stu-id="2a80d-115">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="2a80d-116">在 **[等於]** 下拉式清單中，按一下運算子 (例如**等於**或**不等於**)。</span><span class="sxs-lookup"><span data-stu-id="2a80d-116">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="2a80d-117">依據您選取的使用者內容，輸入您要用來篩選搜尋結果的條件，您可以自行輸入或按一下下拉式清單的箭頭。</span><span class="sxs-lookup"><span data-stu-id="2a80d-117">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="2a80d-118">若要將更多搜尋子句加入至查詢，請按一下 <STRONG>[新增篩選]</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="2a80d-118">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="2a80d-119">按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="2a80d-119">Click **Find**.</span></span>

6.  <span data-ttu-id="2a80d-120">依序按一下搜尋結果中的某個使用者、**[動作]** 和 **[指派原則]**。</span><span class="sxs-lookup"><span data-stu-id="2a80d-120">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="2a80d-121">如果您要將相同的個別使用者行動原則套用至多位使用者，請在搜尋結果中選取多位使用者，然後按一下 [ <STRONG>動作</STRONG>]，再按一下 [ <STRONG>指派原則</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="2a80d-121">If you want the same per-user mobility policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="2a80d-122">在 [ **指派原則**] 的 [ **行動原則**] 底下，執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="2a80d-122">In **Assign Policies**, under **Mobility policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="2a80d-123">因為您可以在 [<STRONG>指派原則</STRONG>] 中設定多個原則，所以對話方塊中的每個原則預設會選取 [ <STRONG> &lt; &gt; 保留</STRONG>為]。</span><span class="sxs-lookup"><span data-stu-id="2a80d-123">Because there are multiple policies that you can configure in <STRONG>Assign Policies</STRONG>, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="2a80d-124">不變更此設定，即可繼續沿用先前指派給使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="2a80d-124">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="2a80d-125">選取 **\<Automatic\>** 此項可讓 Lync Server 2013 自動選擇全域層級原則或網站層級原則（如果已定義）。</span><span class="sxs-lookup"><span data-stu-id="2a80d-125">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="2a80d-126">在 [ **行動性原則** ] 頁面上，按一下您先前定義的每個使用者行動性原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="2a80d-126">Click the name of a per-user mobility policy you previously defined on the **Mobility Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="2a80d-127">為了協助您判斷應指派哪個原則，在按下原則名稱後，按一下 <STRONG>[檢視]</STRONG> 可以檢視該原則所定義的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="2a80d-127">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="2a80d-128">完成時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="2a80d-128">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2a80d-129">使用 Windows PowerShell Cmdlet 指派 Per-User 行動性原則</span><span class="sxs-lookup"><span data-stu-id="2a80d-129">Assigning a Per-User Mobility Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2a80d-130">您可以使用 Windows PowerShell 和 **Grant-CsMobilityPolicy** Cmdlet 指派每個使用者的行動性原則。</span><span class="sxs-lookup"><span data-stu-id="2a80d-130">You can assign per-user mobility policies by using Windows PowerShell and the **Grant-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="2a80d-131">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2a80d-131">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2a80d-132">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="2a80d-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a><span data-ttu-id="2a80d-133">將每一使用者行動性原則指派給單一使用者</span><span class="sxs-lookup"><span data-stu-id="2a80d-133">To assign a per-user mobility policy to a single user</span></span>

  - <span data-ttu-id="2a80d-134">下列命令會指派每個使用者的行動性原則 RedmondMobilityPolicy 至使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="2a80d-134">The following command assigns the per-user mobility policy RedmondMobilityPolicy to the user Ken Myer.</span></span>
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a><span data-ttu-id="2a80d-135">將每一使用者行動性原則指派給多個使用者</span><span class="sxs-lookup"><span data-stu-id="2a80d-135">To assign a per-user mobility policy to multiple users</span></span>

  - <span data-ttu-id="2a80d-136">下列命令會將每個使用者的行動原則 RedmondMobilityPolicy 指派給目前已指派原則 NorthAmericaMobilityPolicy 的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="2a80d-136">The following command assigns the per-user mobility policy RedmondMobilityPolicy to all the users who are currently assigned the policy NorthAmericaMobilityPolicy.</span></span> <span data-ttu-id="2a80d-137">如需此命令中使用之 Filter 參數的詳細資訊，請參閱 [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="2a80d-137">For details about the Filter parameter used in this command, see [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).</span></span>
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a><span data-ttu-id="2a80d-138">取消指派每個使用者的行動性原則</span><span class="sxs-lookup"><span data-stu-id="2a80d-138">To unassign a per-user mobility policy</span></span>

  - <span data-ttu-id="2a80d-139">下列命令 unassigns 先前指派給 Ken Myer 的任何個別使用者行動性原則。</span><span class="sxs-lookup"><span data-stu-id="2a80d-139">The following command unassigns any per-user mobility policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="2a80d-140">一旦解除指派個別使用者原則後，系統會自動使用全域原則或其本機網站原則 (如果有的話) 來管理 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="2a80d-140">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="2a80d-141">網站原則優先順序高於全域原則。</span><span class="sxs-lookup"><span data-stu-id="2a80d-141">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="2a80d-142">如需詳細資訊，請參閱 [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/hh690038\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="2a80d-142">For details, see [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/hh690038\(v=ocs.15\)).</span></span>

## <a name="see-also"></a><span data-ttu-id="2a80d-143">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2a80d-143">See Also</span></span>


[<span data-ttu-id="2a80d-144">在 Lync Server 2013 中設定行動性原則</span><span class="sxs-lookup"><span data-stu-id="2a80d-144">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)

