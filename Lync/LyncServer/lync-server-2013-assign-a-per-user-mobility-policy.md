---
title: Lync Server 2013：指派每個使用者的行動原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user mobility policy
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49733836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e79a9b76ac4774bbbac7772bef19902d6d70f15a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982710"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="a48ad-102">在 Lync Server 2013 中指派每個使用者的行動原則</span><span class="sxs-lookup"><span data-stu-id="a48ad-102">Assign a per-user mobility policy in Lync Server 2013</span></span>

 


<span data-ttu-id="a48ad-103">行動原則是您可以在 Lync Server [控制台] 或 [Lync Server 管理命令介面] 中設定的使用者帳戶個人設定之一。</span><span class="sxs-lookup"><span data-stu-id="a48ad-103">The mobility policy is one of the individual settings of a user account that you can configure in Lync Server Control Panel or Lync Server Management Shell.</span></span>

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="a48ad-104">使用 Lync Server [控制台] 指派每使用者行動原則</span><span class="sxs-lookup"><span data-stu-id="a48ad-104">To assign a per-user mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a48ad-105">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="a48ad-105">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a48ad-106">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="a48ad-106">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a48ad-107">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="a48ad-107">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a48ad-108">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="a48ad-108">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="a48ad-109">使用下列其中一種方法來尋找使用者：</span><span class="sxs-lookup"><span data-stu-id="a48ad-109">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="a48ad-110">在 [**搜尋使用者**] 方塊中，輸入使用者帳戶的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部或第一個部分，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="a48ad-110">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="a48ad-111">如果您有已儲存的查詢，請按一下 [**開啟查詢**] 圖示，使用 [**開啟**舊檔] 對話方塊來檢索查詢（usf 檔案），然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="a48ad-111">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="a48ad-112">可選指定額外的搜尋準則以縮小結果範圍：</span><span class="sxs-lookup"><span data-stu-id="a48ad-112">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="a48ad-113">按一下 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="a48ad-113">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="a48ad-114">輸入使用者屬性或按一下下拉式清單中的箭號，以選取該屬性。</span><span class="sxs-lookup"><span data-stu-id="a48ad-114">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="a48ad-115">在 [**等於**] 下拉式清單中，按一下運算子（例如 [**等於**] 或 [**不等於**]）。</span><span class="sxs-lookup"><span data-stu-id="a48ad-115">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="a48ad-116">根據您所選取的使用者屬性，輸入您想要用來篩選搜尋結果的準則，只要輸入，或按一下下拉式清單中的箭號即可。</span><span class="sxs-lookup"><span data-stu-id="a48ad-116">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="a48ad-117">若要新增其他搜尋子句至您的查詢，請按一下 [<STRONG>新增篩選</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="a48ad-117">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="a48ad-118">按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="a48ad-118">Click **Find**.</span></span>

6.  <span data-ttu-id="a48ad-119">在搜尋結果中按一下使用者，按一下 [**動作**]，然後按一下 [**指派原則**]。</span><span class="sxs-lookup"><span data-stu-id="a48ad-119">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="a48ad-120">如果您想要將相同的每個使用者行動策略套用到多個使用者，請在搜尋結果中選取多位使用者，然後按一下 [<STRONG>動作</STRONG>]，再按一下 [<STRONG>指派原則</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="a48ad-120">If you want the same per-user mobility policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="a48ad-121">在 [**指派原則**] 的 [**行動原則**] 底下，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="a48ad-121">In **Assign Policies**, under **Mobility policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="a48ad-122">因為您可以在<STRONG>指派原則</STRONG>中設定多個原則， <STRONG> &lt; &gt; </STRONG>所以預設會為對話方塊中的每個原則選取 [保留為]。</span><span class="sxs-lookup"><span data-stu-id="a48ad-122">Because there are multiple policies that you can configure in <STRONG>Assign Policies</STRONG>, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="a48ad-123">針對此設定不做任何變更，即可繼續使用先前指派給使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="a48ad-123">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="a48ad-124">選取\*\* \<[\>自動\*\*]，讓 Lync Server 2013 自動選擇 [全域階層原則] 或 [（如果已定義）] 網站層級原則。</span><span class="sxs-lookup"><span data-stu-id="a48ad-124">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="a48ad-125">按一下您先前在 [**行動原則**] 頁面上定義的每個使用者行動原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="a48ad-125">Click the name of a per-user mobility policy you previously defined on the **Mobility Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="a48ad-126">若要協助您決定要指派的原則，請在您按一下策略名稱之後，按一下 [View] （<STRONG>查看</STRONG>），以查看原則中定義的使用者權利和許可權。</span><span class="sxs-lookup"><span data-stu-id="a48ad-126">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="a48ad-127">完成後，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a48ad-127">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a48ad-128">使用 Windows PowerShell Cmdlet 指派每個使用者的移動策略</span><span class="sxs-lookup"><span data-stu-id="a48ad-128">Assigning a Per-User Mobility Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a48ad-129">您可以使用 Windows PowerShell 和**Grant CsMobilityPolicy** Cmdlet 指派每個使用者的行動原則。</span><span class="sxs-lookup"><span data-stu-id="a48ad-129">You can assign per-user mobility policies by using Windows PowerShell and the **Grant-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="a48ad-130">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a48ad-130">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a48ad-131">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="a48ad-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a><span data-ttu-id="a48ad-132">將每個使用者的行動策略指派給單一使用者</span><span class="sxs-lookup"><span data-stu-id="a48ad-132">To assign a per-user mobility policy to a single user</span></span>

  - <span data-ttu-id="a48ad-133">下列命令會將每個使用者的移動策略 RedmondMobilityPolicy 指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="a48ad-133">The following command assigns the per-user mobility policy RedmondMobilityPolicy to the user Ken Myer.</span></span>
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a><span data-ttu-id="a48ad-134">將每個使用者的行動策略指派給多個使用者</span><span class="sxs-lookup"><span data-stu-id="a48ad-134">To assign a per-user mobility policy to multiple users</span></span>

  - <span data-ttu-id="a48ad-135">下列命令會將每個使用者的行動原則 RedmondMobilityPolicy 指派給目前已獲指派 policy NorthAmericaMobilityPolicy 的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="a48ad-135">The following command assigns the per-user mobility policy RedmondMobilityPolicy to all the users who are currently assigned the policy NorthAmericaMobilityPolicy.</span></span> <span data-ttu-id="a48ad-136">如需此命令中使用之篩選參數的詳細資訊，請參閱[move-csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="a48ad-136">For details about the Filter parameter used in this command, see [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)).</span></span>
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a><span data-ttu-id="a48ad-137">若要取消指派每個使用者的行動原則</span><span class="sxs-lookup"><span data-stu-id="a48ad-137">To unassign a per-user mobility policy</span></span>

  - <span data-ttu-id="a48ad-138">下列命令會以前指派給 Ken Myer 的任何每使用者行動原則。</span><span class="sxs-lookup"><span data-stu-id="a48ad-138">The following command unassigns any per-user mobility policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="a48ad-139">未指派每個使用者原則時，會使用全域原則（如果有的話）自動管理 Ken Myer，或在其本機網站原則中使用。</span><span class="sxs-lookup"><span data-stu-id="a48ad-139">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="a48ad-140">網站原則的優先順序高於全域原則。</span><span class="sxs-lookup"><span data-stu-id="a48ad-140">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="a48ad-141">如需詳細資訊，請參閱[授與 CsMobilityPolicy](https://technet.microsoft.com/en-us/library/hh690038\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="a48ad-141">For details, see [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/hh690038\(v=ocs.15\)).</span></span>

## <a name="see-also"></a><span data-ttu-id="a48ad-142">請參閱</span><span class="sxs-lookup"><span data-stu-id="a48ad-142">See Also</span></span>


[<span data-ttu-id="a48ad-143">在 Lync Server 2013 中設定行動原則</span><span class="sxs-lookup"><span data-stu-id="a48ad-143">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)

