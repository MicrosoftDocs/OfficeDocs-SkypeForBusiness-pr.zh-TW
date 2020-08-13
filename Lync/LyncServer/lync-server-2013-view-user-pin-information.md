---
title: Lync Server 2013：查看使用者 PIN 碼資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View user PIN information
ms:assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688067(v=OCS.15)
ms:contentKeyID: 49733661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18f2e9a8c5013a17a35a6f13cf67d9924a9fed78
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-user-pin-information-in-lync-server-2013"></a><span data-ttu-id="950c8-102">在 Lync Server 2013 中查看使用者 PIN 資訊</span><span class="sxs-lookup"><span data-stu-id="950c8-102">View user PIN information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="950c8-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="950c8-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="950c8-104">若要將電話撥入式會議加入為已驗證的使用者，使用 Active Directory 網域服務 (AD DS) 認證的 Lync Server 2013 使用者需要個人識別碼)  (PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="950c8-104">To join a dial-in conference as an authenticated user, a Lync Server 2013 user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="950c8-105">您可以從 Lync Server 2013 控制台中查看使用者的 PIN 碼資訊。</span><span class="sxs-lookup"><span data-stu-id="950c8-105">You can view a user’s PIN information from Lync Server 2013 Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="950c8-106">您可以檢視諸如是否已設定 PIN 或上次變更 PIN 的時間之類的 PIN 狀態資訊，但無法藉由查看 PIN 狀態來查看目前的 PIN。</span><span class="sxs-lookup"><span data-stu-id="950c8-106">You can view PIN status information such as whether the PIN has been set or when the PIN was last changed, but you cannot see the current PIN by looking at the PIN status.</span></span> <span data-ttu-id="950c8-107">如果使用者已遺失 PIN 碼，您可以遵循在<A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">Lync Server 2013 中設定使用者的電話撥入式會議 PIN</A>中的程式來重設它。</span><span class="sxs-lookup"><span data-stu-id="950c8-107">If a user has lost their PIN, you can reset it by following the procedures in <A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">Set a user's dial-in conferencing PIN in Lync Server 2013</A></span></span>



</div>

<div>

## <a name="to-view-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="950c8-108">在 Lync Server 控制台中查看使用者的 PIN</span><span class="sxs-lookup"><span data-stu-id="950c8-108">To view a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="950c8-109">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="950c8-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="950c8-110">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="950c8-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="950c8-111">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="950c8-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="950c8-112">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="950c8-112">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="950c8-113">使用下列其中一種方法，找到使用者：</span><span class="sxs-lookup"><span data-stu-id="950c8-113">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="950c8-114">在 **[搜尋使用者]** 方塊中，輸入該使用者帳戶的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的全部或頭幾個字，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="950c8-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="950c8-115">如果有儲存的查詢，請按一下 **[開啟查詢]** 圖示、使用 **[開啟]** 對話方塊擷取查詢 (.usf 檔)，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="950c8-115">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="950c8-116">(選用) 指定其他搜尋條件，縮減結果：</span><span class="sxs-lookup"><span data-stu-id="950c8-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="950c8-117">按一下 **[新增篩選]**。</span><span class="sxs-lookup"><span data-stu-id="950c8-117">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="950c8-118">輸入使用者內容，您可以自行輸入或按一下下拉式清單的箭頭以選取內容。</span><span class="sxs-lookup"><span data-stu-id="950c8-118">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="950c8-119">在 **[等於]** 下拉式清單中，按一下運算子 (例如 **[等於]** 或 **[不等於]**)。</span><span class="sxs-lookup"><span data-stu-id="950c8-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="950c8-120">視您選取的使用者內容而定，透過直接輸入文字或按一下下拉式清單中的箭頭，輸入您要用來篩選搜尋結果的準則。</span><span class="sxs-lookup"><span data-stu-id="950c8-120">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="950c8-121">若要將更多搜尋子句加入至查詢，請按一下 <STRONG>[新增篩選]</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="950c8-121">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="950c8-122">按一下 [尋找]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="950c8-122">Click **Find**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="950c8-p104">如果 PIN 已鎖定，您必須解除鎖定 PIN，才能設定 PIN。若要解除鎖定 PIN，請依序按一下使用者、[執行]<STRONG></STRONG> 和 [解除鎖定 PIN]<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="950c8-p104">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click <STRONG>Action</STRONG>, and then click <STRONG>Unlock PIN</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="950c8-125">依序按一下搜尋結果中的使用者、[執行]\*\*\*\* 和 [檢視 PIN 狀態]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="950c8-125">Click a user in the search results, click **Action**, and then click **View PIN status**.</span></span>

</div>

<div>

## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="950c8-126">使用 Windows PowerShell Cmdlet 來查看使用者 PIN 碼資訊</span><span class="sxs-lookup"><span data-stu-id="950c8-126">Viewing User PIN Information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="950c8-127">您可以使用 Get-CsClientPinInfo Cmdlet 來檢視使用者 PIN 資訊。</span><span class="sxs-lookup"><span data-stu-id="950c8-127">You can view user PIN information by using the Get-CsClientPinInfo cmdlet.</span></span> <span data-ttu-id="950c8-128">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="950c8-128">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="950c8-129">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="950c8-129">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-user-pin-information"></a><span data-ttu-id="950c8-130">檢視使用者 PIN 資訊</span><span class="sxs-lookup"><span data-stu-id="950c8-130">To view user PIN information</span></span>

  - <span data-ttu-id="950c8-131">若要查看使用者的 PIN 資訊，請在 Lync Server 管理命令介面中輸入類似下列的命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="950c8-131">To view PIN information for a user, type a command similar to the following in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientPinInfo -Identity "Ken Myer"
    
    <span data-ttu-id="950c8-132">如此將傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="950c8-132">That will return information similar to this:</span></span>
    
        Identity          : sip:kenmyer@litwareinc.com
        IsPinSet          : False
        IsLockedOut       : False
        LastPinChangeTime : 9/25/2012 1:35:03 PM
        PinExpirationTime :

</div>

<span data-ttu-id="950c8-133">如需詳細資訊，請參閱[Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/Get-CsConferenceDisclaimer) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="950c8-133">For more information, see the help topic for the [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/Get-CsConferenceDisclaimer) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="950c8-134">另請參閱</span><span class="sxs-lookup"><span data-stu-id="950c8-134">See Also</span></span>


[<span data-ttu-id="950c8-135">在 Lync Server 2013 中設定使用者的電話撥入式會議 PIN</span><span class="sxs-lookup"><span data-stu-id="950c8-135">Set a user's dial-in conferencing PIN in Lync Server 2013</span></span>](lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md)  
[<span data-ttu-id="950c8-136">鎖定或解除鎖定 Lync Server 2013 中的使用者 PIN</span><span class="sxs-lookup"><span data-stu-id="950c8-136">Lock or unlock a user PIN in Lync Server 2013</span></span>](lync-server-2013-lock-or-unlock-a-user-pin.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

