---
title: Lync Server 2013：指派每個使用者的持續聊天原則
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
ms.openlocfilehash: 616a171d4aedcc6014ddea3c5993a097d410a5e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722823"
---
# <a name="assign-a-per-user-persistent-chat-policy-in-lync-server-2013"></a><span data-ttu-id="29d5a-102">指派 Lync Server 2013 中的每個使用者持續聊天原則</span><span class="sxs-lookup"><span data-stu-id="29d5a-102">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>

 


<span data-ttu-id="29d5a-103">您可以將每個使用者的持續聊天原則指派給 Lync Server 2013 [控制台] 或 [Lync Server 2013 管理命令介面]。</span><span class="sxs-lookup"><span data-stu-id="29d5a-103">You can assign a per-user persistent chat policy with either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="29d5a-104">如需有關建立持續聊天伺服器的使用者原則的詳細資料，請參閱[在 Lync Server 2013 中建立持續聊天的使用者原則](lync-server-2013-create-a-user-policy-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="29d5a-104">For details on creating user policies for Persistent Chat Server, see [Create a user policy for Persistent Chat in Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-with-lync-server-control-panel"></a><span data-ttu-id="29d5a-105">使用 Lync Server [控制台] 指派每使用者持續聊天原則</span><span class="sxs-lookup"><span data-stu-id="29d5a-105">To assign a per-user persistent chat policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="29d5a-106">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="29d5a-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="29d5a-107">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="29d5a-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="29d5a-108">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="29d5a-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="29d5a-109">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="29d5a-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="29d5a-110">使用下列其中一種方法來尋找使用者：</span><span class="sxs-lookup"><span data-stu-id="29d5a-110">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="29d5a-111">在 [**搜尋使用者**] 方塊中，輸入使用者帳戶的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部或第一個部分，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="29d5a-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="29d5a-112">如果您有已儲存的查詢，請按一下 [**開啟查詢**] 圖示，使用 [**開啟**舊檔] 對話方塊來檢索查詢（usf 檔案），然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="29d5a-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="29d5a-113">可選指定額外的搜尋準則以縮小結果範圍：</span><span class="sxs-lookup"><span data-stu-id="29d5a-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="29d5a-114">按一下 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="29d5a-114">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="29d5a-115">輸入使用者屬性或按一下下拉式清單中的箭號，以選取該屬性。</span><span class="sxs-lookup"><span data-stu-id="29d5a-115">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="29d5a-116">在 [**等於**] 下拉式清單中，按一下運算子（例如 [**等於**] 或 [**不等於**]）。</span><span class="sxs-lookup"><span data-stu-id="29d5a-116">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="29d5a-117">根據您所選取的使用者屬性，輸入您想要用來篩選搜尋結果的準則，只要輸入，或按一下下拉式清單中的箭號即可。</span><span class="sxs-lookup"><span data-stu-id="29d5a-117">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="29d5a-118">若要新增其他搜尋子句至您的查詢，請按一下 [<STRONG>新增篩選</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="29d5a-118">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="29d5a-119">按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="29d5a-119">Click **Find**.</span></span>

6.  <span data-ttu-id="29d5a-120">在搜尋結果中按一下使用者，按一下 [**動作**]，然後按一下 [**指派原則**]。</span><span class="sxs-lookup"><span data-stu-id="29d5a-120">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="29d5a-121">如果您想要將相同的每個使用者持久聊天原則套用到多個使用者，請在搜尋結果中選取多位使用者，然後按一下 [<STRONG>動作</STRONG>]，再按一下 [<STRONG>指派原則</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="29d5a-121">If you want the same per-user persistent Chat policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="29d5a-122">在 [**指派原則**] 的 [**持續聊天原則**] 底下，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="29d5a-122">In **Assign Policies**, under **Persistent Chat policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="29d5a-123">因為您可以使用 [<STRONG>指派原則</STRONG>] 對話方塊來設定多個原則， <STRONG> &lt; &gt; </STRONG>所以對話方塊中的每個原則預設都會選取 [持續保持為]。</span><span class="sxs-lookup"><span data-stu-id="29d5a-123">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="29d5a-124">針對此設定不做任何變更，即可繼續使用先前指派給使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="29d5a-124">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="29d5a-125">選取\*\* \<[\>自動\*\*]，讓 Lync Server 2013 自動選擇 [全域階層原則] 或 [（如果已定義）] 網站層級原則。</span><span class="sxs-lookup"><span data-stu-id="29d5a-125">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="29d5a-126">按一下您先前在 [**永久聊天原則**] 頁面上定義的每個使用者持續聊天原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="29d5a-126">Click the name of a per-user Persistent Chat policy you previously defined on the **Persistent Chat Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="29d5a-127">若要協助您決定要指派的原則，請在您按一下策略名稱之後，按一下 [View] （<STRONG>查看</STRONG>），以查看原則中定義的使用者權利和許可權。</span><span class="sxs-lookup"><span data-stu-id="29d5a-127">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="29d5a-128">完成後，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="29d5a-128">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-persistent-chat-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="29d5a-129">使用 Windows PowerShell Cmdlet 指派每個使用者的持續聊天原則</span><span class="sxs-lookup"><span data-stu-id="29d5a-129">Assigning a Per-User Persistent Chat Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="29d5a-130">您也可以使用**授與 CsPersistentChatPolicy** Cmdlet，指派針對每位使用者持久的聊天原則。</span><span class="sxs-lookup"><span data-stu-id="29d5a-130">You can also assign per-user persistent chat policies by using the **Grant-CsPersistentChatPolicy** cmdlet.</span></span> <span data-ttu-id="29d5a-131">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="29d5a-131">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="29d5a-132">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="29d5a-132">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-persistent-chat-policy-to-a-single-user"></a><span data-ttu-id="29d5a-133">將每個使用者的持續聊天原則指派給單一使用者</span><span class="sxs-lookup"><span data-stu-id="29d5a-133">To assign a per-user persistent chat policy to a single user</span></span>

  - <span data-ttu-id="29d5a-134">下列命令會將每個使用者的持續聊天原則 RedmondPersistentChatPolicy 指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="29d5a-134">The following command assigns the per-user Persistent Chat policy RedmondPersistentChatPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## <a name="to-assign-a-per-user-persistent-chat-policy-to-multiple-users"></a><span data-ttu-id="29d5a-135">將每個使用者的持續聊天原則指派給多個使用者</span><span class="sxs-lookup"><span data-stu-id="29d5a-135">To assign a per-user persistent chat policy to multiple users</span></span>

  - <span data-ttu-id="29d5a-136">這個命令會將每個使用者的持續聊天原則 RedmondUsersPersistentChatPolicy 指派給所有適用于 IT 部門的使用者。</span><span class="sxs-lookup"><span data-stu-id="29d5a-136">This command assigns the per-user Persistent Chat policy RedmondUsersPersistentChatPolicy to all the users who work for the IT department.</span></span> <span data-ttu-id="29d5a-137">如需此命令中使用之 LdapFilter 參數的詳細資訊，請參閱[move-csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) Cmdlet 的相關檔。</span><span class="sxs-lookup"><span data-stu-id="29d5a-137">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## <a name="to-unassign-a-per-user-persistent-chat-policy"></a><span data-ttu-id="29d5a-138">若要取消指派每個使用者的持續聊天原則</span><span class="sxs-lookup"><span data-stu-id="29d5a-138">To unassign a per-user persistent chat policy</span></span>

  - <span data-ttu-id="29d5a-139">下列命令會先前指派給 Ken Myer 的任何每使用者持續性聊天原則。</span><span class="sxs-lookup"><span data-stu-id="29d5a-139">The following command unassigns any per-user Persistent Chat policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="29d5a-140">未指派每個使用者原則時，會使用全域原則（如果有的話）自動管理 Ken Myer，或在其本機網站原則中使用。</span><span class="sxs-lookup"><span data-stu-id="29d5a-140">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="29d5a-141">網站原則的優先順序高於全域原則。</span><span class="sxs-lookup"><span data-stu-id="29d5a-141">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="29d5a-142">如需詳細資訊，請參閱[Grant CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/jj204907\(v=ocs.15\)) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="29d5a-142">For more information, see the help topic for the [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/jj204907\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="29d5a-143">請參閱</span><span class="sxs-lookup"><span data-stu-id="29d5a-143">See Also</span></span>


[<span data-ttu-id="29d5a-144">在 Lync Server 2013 中建立常設聊天室的使用者原則</span><span class="sxs-lookup"><span data-stu-id="29d5a-144">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

