---
title: Lync Server 2013：指派每位使用者的位置原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user location policy
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520974(v=OCS.15)
ms:contentKeyID: 48183794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a387d0f603addea31bd1e3ee6b591e06a26b2c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974693"
---
# <a name="assign-a-per-user-location-policy-in-lync-server-2013"></a><span data-ttu-id="45d06-102">在 Lync Server 2013 中指派每位使用者的位置原則</span><span class="sxs-lookup"><span data-stu-id="45d06-102">Assign a per-user location policy in Lync Server 2013</span></span>

 


<span data-ttu-id="45d06-103">位置原則是您可以在 Lync Server [控制台] 中設定之使用者帳戶的個別設定之一。</span><span class="sxs-lookup"><span data-stu-id="45d06-103">The location policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="45d06-104">部署一或多個使用者的位置原則是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="45d06-104">Deploying one or more per-user location policies is optional.</span></span> <span data-ttu-id="45d06-105">您也可以只部署全域層級位置原則或子網層級的位置原則。</span><span class="sxs-lookup"><span data-stu-id="45d06-105">You can also deploy only a global-level location policy or subnet-level location policy.</span></span> <span data-ttu-id="45d06-106">如果您要部署每個使用者的原則，您必須將它們明確指派給使用者、群組或連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="45d06-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="45d06-107">增強型9-1-1 （E9-1-1）設定會自動預設為在未指派特定子網層級或每使用者原則時，在全域層級位置原則中定義的配置。</span><span class="sxs-lookup"><span data-stu-id="45d06-107">Enhanced 9-1-1 (E9-1-1) settings automatically default to those defined in the global-level location policy when no specific subnet-level or per-user policy is assigned.</span></span>

<span data-ttu-id="45d06-108">建立至少一個針對每位使用者的位置原則之後，請使用本主題中的程式，指派給指定您希望伺服器針對特定使用者所發出之緊急通話所套用之設定的原則。</span><span class="sxs-lookup"><span data-stu-id="45d06-108">After creating at least one per-user location policy, use the procedures in this topic to assign to the policy that specifies the settings that you want the server to apply for emergency calls placed by a particular user.</span></span>

<span data-ttu-id="45d06-109">如需所有可用位置原則設定的清單，請參閱[定義 Lync Server 2013 的位置原則](lync-server-2013-defining-the-location-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="45d06-109">For a list of all available location policy settings, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="45d06-110">如需建立位置原則的詳細資訊，請參閱[在 Lync Server 2013 中建立位置原則](lync-server-2013-create-location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="45d06-110">For details about creating location policies, see [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md).</span></span>

## <a name="to-assign-a-per-user-location-policy-with-the-lync-server-control-panel"></a><span data-ttu-id="45d06-111">使用 Lync Server [控制台] 指派每個使用者的位置原則</span><span class="sxs-lookup"><span data-stu-id="45d06-111">To assign a per-user location policy with the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="45d06-112">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="45d06-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="45d06-113">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="45d06-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="45d06-114">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="45d06-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="45d06-115">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="45d06-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="45d06-116">使用下列其中一種方法來尋找使用者：</span><span class="sxs-lookup"><span data-stu-id="45d06-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="45d06-117">在 [**搜尋使用者**] 方塊中，輸入使用者帳戶的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部或第一個部分，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="45d06-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="45d06-118">如果您有已儲存的查詢，請按一下 [**開啟查詢**] 圖示，使用 [**開啟**舊檔] 對話方塊來檢索查詢（usf 檔案），然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="45d06-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="45d06-119">可選指定額外的搜尋準則以縮小結果範圍：</span><span class="sxs-lookup"><span data-stu-id="45d06-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="45d06-120">按一下 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="45d06-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="45d06-121">輸入使用者屬性或按一下下拉式清單中的箭號，以選取該屬性。</span><span class="sxs-lookup"><span data-stu-id="45d06-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="45d06-122">在 [**等於**] 下拉式清單中，按一下運算子（例如 [**等於**] 或 [**不等於**]）。</span><span class="sxs-lookup"><span data-stu-id="45d06-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="45d06-123">根據您所選取的使用者屬性，輸入您想要用來篩選搜尋結果的準則，只要輸入，或按一下下拉式清單中的箭號即可。</span><span class="sxs-lookup"><span data-stu-id="45d06-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="45d06-124">若要新增其他搜尋子句至您的查詢，請按一下 [<STRONG>新增篩選</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="45d06-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="45d06-125">按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="45d06-125">Click **Find**.</span></span>

6.  <span data-ttu-id="45d06-126">在搜尋結果中按一下使用者，按一下 [**動作**]，然後按一下 [**指派原則**]。</span><span class="sxs-lookup"><span data-stu-id="45d06-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="45d06-127">如果您想要將相同的每個使用者位置原則套用到多個使用者，請在搜尋結果中選取多位使用者，然後按一下 [<STRONG>動作</STRONG>]，再按一下 [<STRONG>指派原則</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="45d06-127">If you want the same per-user location policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="45d06-128">在 [**指派原則**] 的 [**位置原則**] 底下，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="45d06-128">In **Assign Policies**, under **Location policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="45d06-129">因為您可以使用 [<STRONG>指派原則</STRONG>] 對話方塊來設定多個原則， <STRONG> &lt; &gt; </STRONG>所以對話方塊中的每個原則預設都會選取 [持續保持為]。</span><span class="sxs-lookup"><span data-stu-id="45d06-129">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="45d06-130">針對此設定不做任何變更，即可繼續使用先前指派給使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="45d06-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="45d06-131">[允許 Lync Server 2013] 自動選擇 [全域等級原則] 或 [（如果已定義的話）] 子網層級原則。</span><span class="sxs-lookup"><span data-stu-id="45d06-131">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the subnet-level policy.</span></span>
    
      - <span data-ttu-id="45d06-132">按一下您先前透過執行**CsLocationPolicy** Cmdlet 定義的每個使用者位置原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="45d06-132">Click the name of a per-user location policy you previously defined by running the **New-CsLocationPolicy** cmdlet.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="45d06-133">若要協助您決定要指派的原則，請在您按一下策略名稱之後，按一下 [ <STRONG>view</STRONG> ] （查看），以查看原則中定義的使用者權利和許可權。</span><span class="sxs-lookup"><span data-stu-id="45d06-133">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="45d06-134">完成後，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="45d06-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-location-policy-by-using-lync-server-management-shell-cmdlets"></a><span data-ttu-id="45d06-135">使用 Lync Server 管理命令介面 Cmdlet 指派每個使用者的位置原則</span><span class="sxs-lookup"><span data-stu-id="45d06-135">Assigning a Per-User Location Policy by Using Lync Server Management Shell Cmdlets</span></span>

<span data-ttu-id="45d06-136">您可以使用 Grant CsLocationPolicy Cmdlet 指派每個使用者的位置原則。</span><span class="sxs-lookup"><span data-stu-id="45d06-136">You can assign per-user location policies by using the Grant-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="45d06-137">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="45d06-137">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="45d06-138">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="45d06-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-location-policy-to-a-single-user"></a><span data-ttu-id="45d06-139">將每個使用者的位置原則指派給單一使用者</span><span class="sxs-lookup"><span data-stu-id="45d06-139">To assign a per-user location policy to a single user</span></span>

  - <span data-ttu-id="45d06-140">下列命令會將每個使用者的位置原則 RedmondLocationPolicy 指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="45d06-140">The following command assigns the per-user location policy RedmondLocationPolicy to the user Ken Myer.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## <a name="to-assign-a-per-user-location-policy-to-multiple-users"></a><span data-ttu-id="45d06-141">將每個使用者的位置原則指派給多個使用者</span><span class="sxs-lookup"><span data-stu-id="45d06-141">To assign a per-user location policy to multiple users</span></span>

  - <span data-ttu-id="45d06-142">這個命令會將每個使用者的位置原則 AccountingDepartmentLocationPolicy 指派給所有公司的會計部門使用者。</span><span class="sxs-lookup"><span data-stu-id="45d06-142">This command assigns the per-user location policy AccountingDepartmentLocationPolicy to all the users who work for the Accounting department.</span></span> <span data-ttu-id="45d06-143">如需此命令中使用之 LdapFilter 參數的詳細資訊，請參閱[move-csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) Cmdlet 的相關檔。</span><span class="sxs-lookup"><span data-stu-id="45d06-143">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## <a name="to-unassign-a-per-user-location-policy"></a><span data-ttu-id="45d06-144">若要取消指派每個使用者的位置原則</span><span class="sxs-lookup"><span data-stu-id="45d06-144">To unassign a per-user location policy</span></span>

  - <span data-ttu-id="45d06-145">下列命令會先前指派給 Ken Myer 的任何每使用者位置原則。</span><span class="sxs-lookup"><span data-stu-id="45d06-145">The following command unassigns any per-user location policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="45d06-146">未指派每個使用者原則時，會使用全域原則（如果有的話）自動管理 Ken Myer，或在其本機網站原則中使用。</span><span class="sxs-lookup"><span data-stu-id="45d06-146">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="45d06-147">網站原則的優先順序高於全域原則。</span><span class="sxs-lookup"><span data-stu-id="45d06-147">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="45d06-148">如需詳細資訊，請參閱[Grant CsLocationPolicy](https://technet.microsoft.com/en-us/library/gg413049\(v=ocs.15\)) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="45d06-148">For more information, see the help topic for the [Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/gg413049\(v=ocs.15\)) cmdlet.</span></span>

