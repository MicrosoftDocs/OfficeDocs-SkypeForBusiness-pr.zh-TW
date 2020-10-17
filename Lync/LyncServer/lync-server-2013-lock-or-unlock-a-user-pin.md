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
ms.openlocfilehash: bf8e009e2e93b8de06e1c42aae376987ce96ff5e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513760"
---
# <a name="lock-or-unlock-a-user-pin-in-lync-server-2013"></a><span data-ttu-id="3a0a4-102">鎖定或解除鎖定 Lync Server 2013 中的使用者 PIN</span><span class="sxs-lookup"><span data-stu-id="3a0a4-102">Lock or unlock a user PIN in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a0a4-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="3a0a4-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="3a0a4-104">您可以從 Lync Server 2013 控制台的 [ **使用者** ] 區段鎖定或解除鎖定使用者的 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-104">You can lock or unlock a user’s PIN from the **Users** section of Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="to-lock-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="3a0a4-105">在 Lync Server 控制台中鎖定使用者的 PIN</span><span class="sxs-lookup"><span data-stu-id="3a0a4-105">To lock a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3a0a4-106">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3a0a4-107">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3a0a4-108">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3a0a4-109">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="3a0a4-110">使用下列其中一種方法，找到使用者：</span><span class="sxs-lookup"><span data-stu-id="3a0a4-110">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="3a0a4-111">在 **[搜尋使用者]** 方塊中，輸入該使用者帳戶的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的全部或頭幾個字，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="3a0a4-112">如果有儲存的查詢，請按一下 **[開啟查詢]** 圖示、使用 **[開啟]** 對話方塊擷取查詢 (.usf 檔)，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="3a0a4-113">(選用) 指定其他搜尋條件，縮減結果：</span><span class="sxs-lookup"><span data-stu-id="3a0a4-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="3a0a4-114">按一下 **[新增篩選]**。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-114">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="3a0a4-115">輸入使用者內容，您可以自行輸入或按一下下拉式清單的箭頭以選取內容。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-115">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="3a0a4-116">在 **[等於]** 下拉式清單中，按一下運算子 (例如 **[等於]** 或 **[不等於]**)。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-116">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="3a0a4-117">視您選取的使用者內容而定，透過直接輸入文字或按一下下拉式清單中的箭頭，輸入您要用來篩選搜尋結果的準則。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-117">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="3a0a4-118">若要將更多搜尋子句加入至查詢，請按一下 <STRONG>[新增篩選]</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-118">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="3a0a4-119">按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-119">Click **Find**.</span></span>
    
    6.  <span data-ttu-id="3a0a4-120">按一下使用者、**[動作]**，然後按一下 **[鎖定 PIN]**。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-120">Click the user, click **Action**, and then click **Lock PIN**.</span></span>

</div>

<div>

## <a name="to-unlock-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="3a0a4-121">在 Lync Server 控制台中解除鎖定使用者的 PIN</span><span class="sxs-lookup"><span data-stu-id="3a0a4-121">To unlock a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3a0a4-122">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3a0a4-123">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3a0a4-124">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3a0a4-125">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-125">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="3a0a4-126">使用下列其中一種方法，找到使用者：</span><span class="sxs-lookup"><span data-stu-id="3a0a4-126">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="3a0a4-127">在 **[搜尋使用者]** 方塊中，輸入該使用者帳戶的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的全部或頭幾個字，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-127">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="3a0a4-128">如果有儲存的查詢，請按一下 **[開啟查詢]** 圖示、使用 **[開啟]** 對話方塊擷取查詢 (.usf 檔)，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-128">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="3a0a4-129">(選用) 指定其他搜尋條件，縮減結果：</span><span class="sxs-lookup"><span data-stu-id="3a0a4-129">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="3a0a4-130">按一下 **[新增篩選]**。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-130">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="3a0a4-131">輸入使用者內容，您可以自行輸入或按一下下拉式清單的箭頭以選取內容。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-131">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="3a0a4-132">在 **[等於]** 下拉式清單中，按一下運算子 (例如 **[等於]** 或 **[不等於]**)。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-132">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="3a0a4-133">視您選取的使用者內容而定，透過直接輸入文字或按一下下拉式清單中的箭頭，輸入您要用來篩選搜尋結果的準則。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-133">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="3a0a4-134">若要將更多搜尋子句加入至查詢，請按一下 <STRONG>[新增篩選]</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-134">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="3a0a4-135">按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-135">Click **Find**.</span></span>
    
    6.  <span data-ttu-id="3a0a4-136">按一下使用者、**[動作]**，然後按一下 **[解除鎖定 PIN]**。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-136">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>

</div>

<div>

## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3a0a4-137">使用 Windows PowerShell Cmdlet 鎖定和解除鎖定使用者 Pin</span><span class="sxs-lookup"><span data-stu-id="3a0a4-137">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3a0a4-138">您可以使用 Windows PowerShell 和 Lock-CsClientPin 及 Unlock-CsClientPin Cmdlet 來鎖定和解除鎖定使用者 Pin。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-138">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="3a0a4-139">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-139">You can run these cmdlets either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3a0a4-140">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-140">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-lock-a-user-pin"></a><span data-ttu-id="3a0a4-141">鎖定使用者 PIN</span><span class="sxs-lookup"><span data-stu-id="3a0a4-141">To lock a user PIN</span></span>

  - <span data-ttu-id="3a0a4-p104">如要鎖定使用者的 PIN，請使用 Lock-CsClientPin Cmdlet。例如：</span><span class="sxs-lookup"><span data-stu-id="3a0a4-p104">To lock a user’s PIN, use the Lock-CsClientPin cmdlet. For example:</span></span>
    
        Lock-CsClientPin -Identity "Ken Myer"

</div>

<div>

## <a name="to-unlock-a-user-pin"></a><span data-ttu-id="3a0a4-144">解除鎖定使用者 PIN</span><span class="sxs-lookup"><span data-stu-id="3a0a4-144">To unlock a user PIN</span></span>

  - <span data-ttu-id="3a0a4-p105">如要解除鎖定使用者的 PIN，請使用 Unlock-CsClientPin Cmdlet。例如：</span><span class="sxs-lookup"><span data-stu-id="3a0a4-p105">To unlock a user’s PIN, use the Unlock-CsClientPin cmdlet. For example:</span></span>
    
        Unlock-CsClientPin -Identity "Ken Myer"

</div>

<span data-ttu-id="3a0a4-147">如需詳細資訊，請參閱 [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin) 和 [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="3a0a4-147">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

