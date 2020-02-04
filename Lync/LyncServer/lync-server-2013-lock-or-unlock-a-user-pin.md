---
title: Lync Server 2013：鎖定或解除鎖定使用者 PIN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lock or unlock a user PIN
ms:assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688028(v=OCS.15)
ms:contentKeyID: 49733618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce748039b0e8f19a4efee56424c7661908fe6552
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765544"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lock-or-unlock-a-user-pin-in-lync-server-2013"></a><span data-ttu-id="559e1-102">鎖定或解除鎖定 Lync Server 2013 中的使用者 PIN</span><span class="sxs-lookup"><span data-stu-id="559e1-102">Lock or unlock a user PIN in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="559e1-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="559e1-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="559e1-104">您可以從 Lync Server 2013 [控制台] 的 [**使用者**] 區段鎖定或解除鎖定使用者的 PIN。</span><span class="sxs-lookup"><span data-stu-id="559e1-104">You can lock or unlock a user’s PIN from the **Users** section of Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="to-lock-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="559e1-105">在 Lync Server [控制台] 中鎖定使用者的 PIN</span><span class="sxs-lookup"><span data-stu-id="559e1-105">To lock a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="559e1-106">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="559e1-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="559e1-107">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="559e1-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="559e1-108">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="559e1-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="559e1-109">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="559e1-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="559e1-110">使用下列其中一種方法來尋找使用者：</span><span class="sxs-lookup"><span data-stu-id="559e1-110">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="559e1-111">在 [**搜尋使用者**] 方塊中，輸入使用者帳戶的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部或第一個部分，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="559e1-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="559e1-112">如果您有已儲存的查詢，請按一下 [**開啟查詢**] 圖示，使用 [**開啟**舊檔] 對話方塊來檢索查詢（usf 檔案），然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="559e1-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="559e1-113">可選指定額外的搜尋準則以縮小結果範圍：</span><span class="sxs-lookup"><span data-stu-id="559e1-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="559e1-114">按一下 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="559e1-114">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="559e1-115">輸入使用者屬性或按一下下拉式清單中的箭號，以選取該屬性。</span><span class="sxs-lookup"><span data-stu-id="559e1-115">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="559e1-116">在 [**等於**] 下拉式清單中，按一下運算子（例如 [**等於**] 或 [**不等於**]）。</span><span class="sxs-lookup"><span data-stu-id="559e1-116">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="559e1-117">根據您所選取的使用者屬性，輸入您想要用來篩選搜尋結果的準則，只要輸入，或按一下下拉式清單中的箭號即可。</span><span class="sxs-lookup"><span data-stu-id="559e1-117">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="559e1-118">若要新增其他搜尋子句至您的查詢，請按一下 [<STRONG>新增篩選</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="559e1-118">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="559e1-119">按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="559e1-119">Click **Find**.</span></span>
    
    6.  <span data-ttu-id="559e1-120">按一下使用者，按一下 [**動作**]，然後按一下 [**鎖定 PIN**]。</span><span class="sxs-lookup"><span data-stu-id="559e1-120">Click the user, click **Action**, and then click **Lock PIN**.</span></span>

</div>

<div>

## <a name="to-unlock-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="559e1-121">在 Lync Server [控制台] 中解除鎖定使用者的 PIN</span><span class="sxs-lookup"><span data-stu-id="559e1-121">To unlock a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="559e1-122">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="559e1-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="559e1-123">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="559e1-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="559e1-124">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="559e1-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="559e1-125">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="559e1-125">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="559e1-126">使用下列其中一種方法來尋找使用者：</span><span class="sxs-lookup"><span data-stu-id="559e1-126">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="559e1-127">在 [**搜尋使用者**] 方塊中，輸入使用者帳戶的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部或第一個部分，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="559e1-127">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="559e1-128">如果您有已儲存的查詢，請按一下 [**開啟查詢**] 圖示，使用 [**開啟**舊檔] 對話方塊來檢索查詢（usf 檔案），然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="559e1-128">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="559e1-129">可選指定額外的搜尋準則以縮小結果範圍：</span><span class="sxs-lookup"><span data-stu-id="559e1-129">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="559e1-130">按一下 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="559e1-130">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="559e1-131">輸入使用者屬性或按一下下拉式清單中的箭號，以選取該屬性。</span><span class="sxs-lookup"><span data-stu-id="559e1-131">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="559e1-132">在 [**等於**] 下拉式清單中，按一下運算子（例如 [**等於**] 或 [**不等於**]）。</span><span class="sxs-lookup"><span data-stu-id="559e1-132">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="559e1-133">根據您所選取的使用者屬性，輸入您想要用來篩選搜尋結果的準則，只要輸入，或按一下下拉式清單中的箭號即可。</span><span class="sxs-lookup"><span data-stu-id="559e1-133">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="559e1-134">若要新增其他搜尋子句至您的查詢，請按一下 [<STRONG>新增篩選</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="559e1-134">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="559e1-135">按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="559e1-135">Click **Find**.</span></span>
    
    6.  <span data-ttu-id="559e1-136">按一下使用者，按一下 [**動作**]，然後按一下 [**解除鎖定 PIN**]。</span><span class="sxs-lookup"><span data-stu-id="559e1-136">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>

</div>

<div>

## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="559e1-137">使用 Windows PowerShell Cmdlet 鎖定及解除鎖定使用者 Pin</span><span class="sxs-lookup"><span data-stu-id="559e1-137">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="559e1-138">您可以使用 Windows PowerShell 以及 Lock CsClientPin 和解除 CsClientPin Cmdlet 來鎖定和解除鎖定使用者 Pin。</span><span class="sxs-lookup"><span data-stu-id="559e1-138">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="559e1-139">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="559e1-139">You can run these cmdlets either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="559e1-140">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="559e1-140">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-lock-a-user-pin"></a><span data-ttu-id="559e1-141">鎖定使用者 PIN</span><span class="sxs-lookup"><span data-stu-id="559e1-141">To lock a user PIN</span></span>

  - <span data-ttu-id="559e1-142">若要鎖定使用者的 PIN，請使用 Lock CsClientPin Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="559e1-142">To lock a user’s PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="559e1-143">例如：</span><span class="sxs-lookup"><span data-stu-id="559e1-143">For example:</span></span>
    
        Lock-CsClientPin -Identity "Ken Myer"

</div>

<div>

## <a name="to-unlock-a-user-pin"></a><span data-ttu-id="559e1-144">解除鎖定使用者 PIN</span><span class="sxs-lookup"><span data-stu-id="559e1-144">To unlock a user PIN</span></span>

  - <span data-ttu-id="559e1-145">若要解除鎖定使用者的 PIN，請使用 Unlock CsClientPin Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="559e1-145">To unlock a user’s PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="559e1-146">例如：</span><span class="sxs-lookup"><span data-stu-id="559e1-146">For example:</span></span>
    
        Unlock-CsClientPin -Identity "Ken Myer"

</div>

<span data-ttu-id="559e1-147">如需詳細資訊，請參閱[Lock CsClientPin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin)和[解除 CsClientPin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="559e1-147">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

