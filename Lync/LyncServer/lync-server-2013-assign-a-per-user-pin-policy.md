---
title: Lync Server 2013：指派每位使用者的 PIN 原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user PIN policy
ms:assetid: d8211c64-0b63-4193-a074-673da7d14287
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182594(v=OCS.15)
ms:contentKeyID: 48185475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c60943ad13bd03de6e4474ec35f2deea1964bad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978250"
---
# <a name="assign-a-per-user-pin-policy-in-lync-server-2013"></a><span data-ttu-id="c41b9-102">在 Lync Server 2013 中指派每位使用者的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="c41b9-102">Assign a per-user PIN policy in Lync Server 2013</span></span>

 


<span data-ttu-id="c41b9-103">電話撥入式會議個人識別碼（PIN）原則是可在 Lync Server 2013 [控制台] 中設定的使用者帳戶個人設定之一。</span><span class="sxs-lookup"><span data-stu-id="c41b9-103">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="c41b9-104">部署一或多個使用者 PIN 原則是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="c41b9-104">Deploying one or more per-user PIN policies is optional.</span></span> <span data-ttu-id="c41b9-105">您也可以只部署全域層級的 PIN 原則或網站層級的 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="c41b9-105">You can also deploy only a global-level PIN policy or site-level PIN policy.</span></span> <span data-ttu-id="c41b9-106">如果您要部署每個使用者的原則，您必須將它們明確指派給使用者、群組或連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="c41b9-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="c41b9-107">指派電話撥入式會議 Pin 的使用者權利和許可權，在沒有指派任何特定網站層級或每使用者原則時，系統會自動將預設值設為全域層級 PIN 原則中定義的 Pin。</span><span class="sxs-lookup"><span data-stu-id="c41b9-107">User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="c41b9-108">建立至少一個針對每位使用者的 PIN 原則之後，請使用本主題中的程式，指派指定您希望伺服器強加在由特定使用者所建立之 Pin 所產生之限制的原則。</span><span class="sxs-lookup"><span data-stu-id="c41b9-108">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>

<span data-ttu-id="c41b9-109">如需有關建立針對每位使用者的電話撥入式會議 PIN 原則的詳細資料，請參閱[在 Lync Server 2013 中為網站或使用者群組建立或修改電話撥入式會議 pin 設定](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)。</span><span class="sxs-lookup"><span data-stu-id="c41b9-109">For details about creating per-user dial-in conferencing PIN policies, see [Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span></span>

## <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="c41b9-110">指派每位使用者的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="c41b9-110">To assign a per-user PIN policy</span></span>

1.  <span data-ttu-id="c41b9-111">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c41b9-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c41b9-112">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="c41b9-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c41b9-113">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="c41b9-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c41b9-114">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="c41b9-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="c41b9-115">使用下列其中一種方法來尋找使用者：</span><span class="sxs-lookup"><span data-stu-id="c41b9-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="c41b9-116">在 [**搜尋使用者**] 方塊中，輸入使用者帳戶的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部或第一個部分，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="c41b9-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="c41b9-117">如果您有已儲存的查詢，請按一下 [**開啟查詢**] 圖示，使用 [**開啟**舊檔] 對話方塊來檢索查詢（usf 檔案），然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="c41b9-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="c41b9-118">可選指定額外的搜尋準則以縮小結果範圍：</span><span class="sxs-lookup"><span data-stu-id="c41b9-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="c41b9-119">按一下 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="c41b9-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="c41b9-120">輸入使用者屬性或按一下下拉式清單中的箭號，以選取該屬性。</span><span class="sxs-lookup"><span data-stu-id="c41b9-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="c41b9-121">在 [**等於**] 下拉式清單中，按一下運算子（例如 [**等於**] 或 [**不等於**]）。</span><span class="sxs-lookup"><span data-stu-id="c41b9-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="c41b9-122">根據您所選取的使用者屬性，輸入您想要用來篩選搜尋結果的準則，只要輸入，或按一下下拉式清單中的箭號即可。</span><span class="sxs-lookup"><span data-stu-id="c41b9-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="c41b9-123">若要新增其他搜尋子句至您的查詢，請按一下 [<STRONG>新增篩選</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="c41b9-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="c41b9-124">按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="c41b9-124">Click **Find**.</span></span>

6.  <span data-ttu-id="c41b9-125">在搜尋結果中按一下使用者，按一下 [**動作**]，然後按一下 [**指派原則**]。</span><span class="sxs-lookup"><span data-stu-id="c41b9-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="c41b9-126">如果您想要將相同的每個使用者 PIN 原則套用到多個使用者，請在搜尋結果中選取多位使用者，然後按一下 [<STRONG>動作</STRONG>]，再按一下 [<STRONG>指派原則</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="c41b9-126">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="c41b9-127">在 [**指派原則**] 的 [ **PIN 原則**] 底下，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="c41b9-127">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="c41b9-128">因為您可以使用 [<STRONG>指派原則</STRONG>] 對話方塊來設定多個原則， <STRONG> &lt; &gt; </STRONG>所以對話方塊中的每個原則預設都會選取 [持續保持為]。</span><span class="sxs-lookup"><span data-stu-id="c41b9-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="c41b9-129">針對此設定不做任何變更，即可繼續使用先前指派給使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="c41b9-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="c41b9-130">[允許 Lync Server 2013] 自動選擇 [全域階層原則] 或 [（如果已定義）] 網站層級原則。</span><span class="sxs-lookup"><span data-stu-id="c41b9-130">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="c41b9-131">按一下您先前在 [ **PIN 策略**] 頁面上定義之每個使用者 PIN 原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="c41b9-131">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="c41b9-132">若要協助您決定要指派的原則，請在您按一下策略名稱之後，按一下 [View] （<STRONG>查看</STRONG>），以查看原則中定義的使用者權利和許可權。</span><span class="sxs-lookup"><span data-stu-id="c41b9-132">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="c41b9-133">完成後，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c41b9-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c41b9-134">使用 Windows PowerShell Cmdlet 指派每個使用者的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="c41b9-134">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c41b9-135">您可以使用 Windows PowerShell 和**Grant CsPinPolicy** Cmdlet 來指派每個使用者的 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="c41b9-135">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="c41b9-136">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c41b9-136">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c41b9-137">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="c41b9-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="c41b9-138">將每位使用者 PIN 原則指派給單一使用者</span><span class="sxs-lookup"><span data-stu-id="c41b9-138">To assign a per-user PIN policy to a single user</span></span>

  - <span data-ttu-id="c41b9-139">下列命令會將每個使用者的 PIN 原則 RedmondPinPolicy 指派給使用者 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="c41b9-139">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"

## <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="c41b9-140">將每位使用者 PIN 原則指派給多個使用者</span><span class="sxs-lookup"><span data-stu-id="c41b9-140">To assign a per-user PIN policy to multiple users</span></span>

  - <span data-ttu-id="c41b9-141">下列命令會將每位使用者的 PIN 原則 RedmondUsersPinPolicy 指派給所有在雷蒙德市中工作的使用者。</span><span class="sxs-lookup"><span data-stu-id="c41b9-141">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="c41b9-142">如需此命令中使用之 LdapFilter 參數的詳細資訊，請參閱[move-csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="c41b9-142">For details about the LdapFilter parameter used in this command, see [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)).</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

## <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="c41b9-143">若要取消指派每位使用者的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="c41b9-143">To unassign a per-user PIN policy</span></span>

  - <span data-ttu-id="c41b9-144">下列命令會以前指派給 Ken Myer 的任何每使用者 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="c41b9-144">The following command unassigns any per-user PIN policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="c41b9-145">未指派每個使用者原則時，會使用全域原則（如果有的話）自動管理 Ken Myer，或在其本機網站原則中使用。</span><span class="sxs-lookup"><span data-stu-id="c41b9-145">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="c41b9-146">網站原則的優先順序高於全域原則。</span><span class="sxs-lookup"><span data-stu-id="c41b9-146">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="c41b9-147">如需詳細資訊，請參閱[授與 CsPinPolicy](https://technet.microsoft.com/en-us/library/gg398871\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="c41b9-147">For details, see [Grant-CsPinPolicy](https://technet.microsoft.com/en-us/library/gg398871\(v=ocs.15\)).</span></span>

## <a name="see-also"></a><span data-ttu-id="c41b9-148">請參閱</span><span class="sxs-lookup"><span data-stu-id="c41b9-148">See Also</span></span>


[<span data-ttu-id="c41b9-149">在 Lync Server 2013 中建立新的 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="c41b9-149">Create a new PIN policy in Lync Server 2013</span></span>](lync-server-2013-create-a-new-pin-policy.md)  


[<span data-ttu-id="c41b9-150">在 Lync Server 2013 中指派每個使用者的原則</span><span class="sxs-lookup"><span data-stu-id="c41b9-150">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

