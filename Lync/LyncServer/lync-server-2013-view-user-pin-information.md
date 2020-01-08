---
title: Lync Server 2013：查看使用者 PIN 資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View user PIN information
ms:assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688067(v=OCS.15)
ms:contentKeyID: 49733661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb3d854f68e9e22e8d8fb1fa0d26f555f09af1ae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-user-pin-information-in-lync-server-2013"></a><span data-ttu-id="a289d-102">在 Lync Server 2013 中查看使用者 PIN 資訊</span><span class="sxs-lookup"><span data-stu-id="a289d-102">View user PIN information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a289d-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a289d-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a289d-104">若要將電話撥入式會議加入為經過驗證的使用者，擁有 Active Directory 網域服務（AD DS）認證的 Lync Server 2013 使用者需要個人識別碼（PIN）。</span><span class="sxs-lookup"><span data-stu-id="a289d-104">To join a dial-in conference as an authenticated user, a Lync Server 2013 user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="a289d-105">您可以從 Lync Server 2013 的 [控制台] 中查看使用者的 PIN 資訊。</span><span class="sxs-lookup"><span data-stu-id="a289d-105">You can view a user’s PIN information from Lync Server 2013 Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a289d-106">您可以查看 PIN 狀態資訊，例如，PIN 是否已設定，或是 PIN 上次變更的時間，但是您看不到目前的 PIN，只需要查看 PIN 狀態即可。</span><span class="sxs-lookup"><span data-stu-id="a289d-106">You can view PIN status information such as whether the PIN has been set or when the PIN was last changed, but you cannot see the current PIN by looking at the PIN status.</span></span> <span data-ttu-id="a289d-107">如果使用者遺失其 PIN，您可以按照在<A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">Lync Server 2013 中設定使用者的電話撥入式會議 PIN</A>中的程式來重設它。</span><span class="sxs-lookup"><span data-stu-id="a289d-107">If a user has lost their PIN, you can reset it by following the procedures in <A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">Set a user's dial-in conferencing PIN in Lync Server 2013</A></span></span>



</div>

<div>

## <a name="to-view-a-users-pin-in-lync-server-control-panel"></a><span data-ttu-id="a289d-108">在 Lync Server [控制台] 中查看使用者的 PIN</span><span class="sxs-lookup"><span data-stu-id="a289d-108">To view a user’s PIN in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a289d-109">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="a289d-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a289d-110">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="a289d-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a289d-111">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="a289d-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a289d-112">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="a289d-112">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="a289d-113">使用下列其中一種方法來尋找使用者：</span><span class="sxs-lookup"><span data-stu-id="a289d-113">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="a289d-114">在 [**搜尋使用者**] 方塊中，輸入使用者帳戶的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部或第一個部分，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="a289d-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="a289d-115">如果您有已儲存的查詢，請按一下 [**開啟查詢**] 圖示，使用 [**開啟**舊檔] 對話方塊來檢索查詢（usf 檔案），然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="a289d-115">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="a289d-116">可選指定額外的搜尋準則以縮小結果範圍：</span><span class="sxs-lookup"><span data-stu-id="a289d-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="a289d-117">按一下 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="a289d-117">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="a289d-118">輸入使用者屬性或按一下下拉式清單中的箭號，以選取該屬性。</span><span class="sxs-lookup"><span data-stu-id="a289d-118">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="a289d-119">在 [**等於**] 下拉式清單中，按一下運算子（例如 [**等於**] 或 [**不等於**]）。</span><span class="sxs-lookup"><span data-stu-id="a289d-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="a289d-120">根據您所選取的使用者屬性，輸入您想要用來篩選搜尋結果的準則，只要輸入，或按一下下拉式清單中的箭號即可。</span><span class="sxs-lookup"><span data-stu-id="a289d-120">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="a289d-121">若要新增其他搜尋子句至您的查詢，請按一下 [<STRONG>新增篩選</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="a289d-121">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="a289d-122">按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="a289d-122">Click **Find**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a289d-123">如果 PIN 已鎖定，您必須先解除鎖定 PIN，才能進行設定。</span><span class="sxs-lookup"><span data-stu-id="a289d-123">If the PIN is locked, you must unlock the PIN before you can set it.</span></span> <span data-ttu-id="a289d-124">若要解除鎖定 PIN，請按一下使用者，按一下 [<STRONG>動作</STRONG>]，然後按一下 [<STRONG>解除鎖定 pin</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="a289d-124">To unlock the PIN, click the user, click <STRONG>Action</STRONG>, and then click <STRONG>Unlock PIN</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="a289d-125">在搜尋結果中按一下使用者，按一下 [**動作**]，然後按一下 [**查看 PIN 狀態**]。</span><span class="sxs-lookup"><span data-stu-id="a289d-125">Click a user in the search results, click **Action**, and then click **View PIN status**.</span></span>

</div>

<div>

## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a289d-126">使用 Windows PowerShell Cmdlet 來查看使用者 PIN 資訊</span><span class="sxs-lookup"><span data-stu-id="a289d-126">Viewing User PIN Information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="a289d-127">您可以使用 CsClientPinInfo Cmdlet 來查看使用者 PIN 資訊。</span><span class="sxs-lookup"><span data-stu-id="a289d-127">You can view user PIN information by using the Get-CsClientPinInfo cmdlet.</span></span> <span data-ttu-id="a289d-128">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="a289d-128">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a289d-129">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="a289d-129">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-user-pin-information"></a><span data-ttu-id="a289d-130">若要查看使用者 PIN 資訊</span><span class="sxs-lookup"><span data-stu-id="a289d-130">To view user PIN information</span></span>

  - <span data-ttu-id="a289d-131">若要查看使用者的 PIN 資訊，請在 Lync Server 管理命令介面中輸入類似以下的命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="a289d-131">To view PIN information for a user, type a command similar to the following in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientPinInfo -Identity "Ken Myer"
    
    <span data-ttu-id="a289d-132">這會傳回如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="a289d-132">That will return information similar to this:</span></span>
    
        Identity          : sip:kenmyer@litwareinc.com
        IsPinSet          : False
        IsLockedOut       : False
        LastPinChangeTime : 9/25/2012 1:35:03 PM
        PinExpirationTime :

</div>

<span data-ttu-id="a289d-133">如需詳細資訊，請參閱[CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/Get-CsConferenceDisclaimer) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="a289d-133">For more information, see the help topic for the [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/Get-CsConferenceDisclaimer) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a289d-134">請參閱</span><span class="sxs-lookup"><span data-stu-id="a289d-134">See Also</span></span>


[<span data-ttu-id="a289d-135">在 Lync Server 2013 中設定使用者的電話撥入式會議 PIN</span><span class="sxs-lookup"><span data-stu-id="a289d-135">Set a user's dial-in conferencing PIN in Lync Server 2013</span></span>](lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md)  
[<span data-ttu-id="a289d-136">鎖定或解除鎖定 Lync Server 2013 中的使用者 PIN</span><span class="sxs-lookup"><span data-stu-id="a289d-136">Lock or unlock a user PIN in Lync Server 2013</span></span>](lync-server-2013-lock-or-unlock-a-user-pin.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

