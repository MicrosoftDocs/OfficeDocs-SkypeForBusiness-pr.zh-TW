---
title: Lync Server 2013：指派每位使用者的持續性聊天原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user Persistent Chat policy
ms:assetid: e22168f2-fde1-4f0a-b194-1fc881436822
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721908(v=OCS.15)
ms:contentKeyID: 49733842
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e06d6c7403bd348b44c6ab36216ed7ee9a1c6d02
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134409"
---
# <a name="assign-a-per-user-persistent-chat-policy-in-lync-server-2013"></a><span data-ttu-id="6f4de-102">在 Lync Server 2013 中指派每一使用者的持續性聊天原則</span><span class="sxs-lookup"><span data-stu-id="6f4de-102">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>

 


<span data-ttu-id="6f4de-103">您可以以 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面指派每個使用者的持續聊天原則。</span><span class="sxs-lookup"><span data-stu-id="6f4de-103">You can assign a per-user persistent chat policy with either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="6f4de-104">如需建立 Persistent Chat Server 使用者原則的詳細資訊，請參閱[Create a user policy For Persistent chat In Lync server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="6f4de-104">For details on creating user policies for Persistent Chat Server, see [Create a user policy for Persistent Chat in Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-with-lync-server-control-panel"></a><span data-ttu-id="6f4de-105">使用 Lync Server 控制台指派每位使用者的持續聊天原則</span><span class="sxs-lookup"><span data-stu-id="6f4de-105">To assign a per-user persistent chat policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="6f4de-106">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="6f4de-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6f4de-107">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="6f4de-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6f4de-108">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="6f4de-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6f4de-109">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="6f4de-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="6f4de-110">使用下列其中一種方法，找到使用者：</span><span class="sxs-lookup"><span data-stu-id="6f4de-110">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="6f4de-111">在 **[搜尋使用者]** 方塊中，輸入該使用者帳戶的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的全部或頭幾個字，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="6f4de-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="6f4de-112">如果有儲存的查詢，請按一下 **[開啟查詢]** 圖示、使用 **[開啟]** 對話方塊擷取查詢 (.usf 檔)，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="6f4de-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="6f4de-113">(選用) 指定其他搜尋條件，縮減結果：</span><span class="sxs-lookup"><span data-stu-id="6f4de-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="6f4de-114">按一下 **[新增篩選]**。</span><span class="sxs-lookup"><span data-stu-id="6f4de-114">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="6f4de-115">輸入使用者內容，您可以自行輸入或按一下下拉式清單的箭頭以選取內容。</span><span class="sxs-lookup"><span data-stu-id="6f4de-115">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="6f4de-116">在 **[等於]** 下拉式清單中，按一下運算子 (例如**等於**或**不等於**)。</span><span class="sxs-lookup"><span data-stu-id="6f4de-116">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="6f4de-117">依據您選取的使用者內容，輸入您要用來篩選搜尋結果的條件，您可以自行輸入或按一下下拉式清單的箭頭。</span><span class="sxs-lookup"><span data-stu-id="6f4de-117">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="6f4de-118">若要將更多搜尋子句加入至查詢，請按一下 <STRONG>[新增篩選]</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="6f4de-118">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="6f4de-119">按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="6f4de-119">Click **Find**.</span></span>

6.  <span data-ttu-id="6f4de-120">依序按一下搜尋結果中的某個使用者、**[動作]** 和 **[指派原則]**。</span><span class="sxs-lookup"><span data-stu-id="6f4de-120">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="6f4de-121">如果您要將相同的個別使用者持久聊天原則套用至多位使用者，請在搜尋結果中選取多位使用者，然後按一下 [<STRONG>動作</STRONG>]，再按一下 [<STRONG>指派原則</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="6f4de-121">If you want the same per-user persistent Chat policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="6f4de-122">在 [**指派原則**] 的 [ **Persistent Chat policy**] 底下，執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="6f4de-122">In **Assign Policies**, under **Persistent Chat policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="6f4de-123">因為有多種可使用 [<STRONG>指派原則</STRONG>] 對話方塊進行設定的原則，所以對話方塊中的每個原則預設會選取 [ <STRONG> &lt; &gt; 保留</STRONG>為]。</span><span class="sxs-lookup"><span data-stu-id="6f4de-123">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="6f4de-124">不變更此設定，即可繼續沿用先前指派給使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="6f4de-124">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="6f4de-125">選取 [ \*\* \< 自動 \> \*\* ] 以允許 Lync Server 2013 自動選擇全域層級原則，或網站層級原則（如果已定義）。</span><span class="sxs-lookup"><span data-stu-id="6f4de-125">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="6f4de-126">按一下您先前在 [**持續性聊天原則**] 頁面上定義之個別使用者持續性聊天原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="6f4de-126">Click the name of a per-user Persistent Chat policy you previously defined on the **Persistent Chat Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="6f4de-127">為了協助您判斷應指派哪個原則，在按下原則名稱後，按一下 <STRONG>[檢視]</STRONG> 可以檢視該原則所定義的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="6f4de-127">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="6f4de-128">完成時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6f4de-128">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-persistent-chat-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6f4de-129">使用 Windows PowerShell Cmdlet 指派 Per-User 持續性聊天原則</span><span class="sxs-lookup"><span data-stu-id="6f4de-129">Assigning a Per-User Persistent Chat Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6f4de-130">您也可以使用**Grant-CsPersistentChatPolicy** Cmdlet 指派每位使用者的持續性聊天原則。</span><span class="sxs-lookup"><span data-stu-id="6f4de-130">You can also assign per-user persistent chat policies by using the **Grant-CsPersistentChatPolicy** cmdlet.</span></span> <span data-ttu-id="6f4de-131">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6f4de-131">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6f4de-132">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="6f4de-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-to-a-single-user"></a><span data-ttu-id="6f4de-133">將每一使用者的持續聊天原則指派給單一使用者</span><span class="sxs-lookup"><span data-stu-id="6f4de-133">To assign a per-user persistent chat policy to a single user</span></span>

  - <span data-ttu-id="6f4de-134">下列命令會將每位使用者的 Persistent 聊天原則 RedmondPersistentChatPolicy 指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="6f4de-134">The following command assigns the per-user Persistent Chat policy RedmondPersistentChatPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## <a name="to-assign-a-per-user-persistent-chat-policy-to-multiple-users"></a><span data-ttu-id="6f4de-135">將每一使用者的持續聊天原則指派給多個使用者</span><span class="sxs-lookup"><span data-stu-id="6f4de-135">To assign a per-user persistent chat policy to multiple users</span></span>

  - <span data-ttu-id="6f4de-136">這個命令會將個別使用者的 Persistent 聊天原則 RedmondUsersPersistentChatPolicy 指派給所有為 IT 部門工作的使用者。</span><span class="sxs-lookup"><span data-stu-id="6f4de-136">This command assigns the per-user Persistent Chat policy RedmondUsersPersistentChatPolicy to all the users who work for the IT department.</span></span> <span data-ttu-id="6f4de-137">如需此命令中所用 LdapFilter 參數的詳細資訊，請參閱[Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) Cmdlet 的檔。</span><span class="sxs-lookup"><span data-stu-id="6f4de-137">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## <a name="to-unassign-a-per-user-persistent-chat-policy"></a><span data-ttu-id="6f4de-138">取消指派個別使用者的持續聊天原則</span><span class="sxs-lookup"><span data-stu-id="6f4de-138">To unassign a per-user persistent chat policy</span></span>

  - <span data-ttu-id="6f4de-139">下列命令 unassigns 先前指派給 Ken Myer 的任何個別使用者持續性聊天原則。</span><span class="sxs-lookup"><span data-stu-id="6f4de-139">The following command unassigns any per-user Persistent Chat policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="6f4de-140">一旦解除指派個別使用者原則後，系統會自動使用全域原則或其本機網站原則 (如果有的話) 來管理 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="6f4de-140">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="6f4de-141">網站原則優先順序高於全域原則。</span><span class="sxs-lookup"><span data-stu-id="6f4de-141">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="6f4de-142">如需詳細資訊，請參閱[Grant-CsPersistentChatPolicy](https://technet.microsoft.com/library/jj204907\(v=ocs.15\)) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="6f4de-142">For more information, see the help topic for the [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/library/jj204907\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f4de-143">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6f4de-143">See Also</span></span>


[<span data-ttu-id="6f4de-144">在 Lync Server 2013 中建立持久聊天的使用者原則</span><span class="sxs-lookup"><span data-stu-id="6f4de-144">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

