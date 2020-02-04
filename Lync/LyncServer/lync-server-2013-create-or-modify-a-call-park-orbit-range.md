---
title: Lync Server 2013：建立或修改通話公園軌道的範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Call Park orbit range
ms:assetid: 549ec118-eee5-4333-9416-80929ec057e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398361(v=OCS.15)
ms:contentKeyID: 48184142
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf215caacd0e380a14429bd2d34791048878fc96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-call-park-orbit-range-in-lync-server-2013"></a><span data-ttu-id="dc12a-102">在 Lync Server 2013 中建立或修改通話駐留軌道的範圍</span><span class="sxs-lookup"><span data-stu-id="dc12a-102">Create or modify a Call Park orbit range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc12a-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="dc12a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="dc12a-104">使用下列其中一個程式來建立或修改通話寄存軌道的範圍。</span><span class="sxs-lookup"><span data-stu-id="dc12a-104">Use one of the following procedures to create or modify a call park orbit range.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="dc12a-105">使用 Lync Server [控制台] 來建立或修改停車通話的數位範圍</span><span class="sxs-lookup"><span data-stu-id="dc12a-105">To use Lync Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1.  <span data-ttu-id="dc12a-106">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="dc12a-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="dc12a-107">如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="dc12a-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="dc12a-108">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="dc12a-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dc12a-109">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="dc12a-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dc12a-110">在左側導覽列中，按一下 [**語音功能**]，然後按一下 [**通話駐留**]。</span><span class="sxs-lookup"><span data-stu-id="dc12a-110">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4.  <span data-ttu-id="dc12a-111">在 [**通話駐留**] 頁面上，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="dc12a-111">On the **Call Park** page, do one of the following:</span></span>
    
      - <span data-ttu-id="dc12a-112">若要建立新的軌道範圍，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="dc12a-112">To create a new orbit range, click **New**.</span></span> <span data-ttu-id="dc12a-113">在 [**名稱**] 中，輸入此數位範圍的識別名稱。</span><span class="sxs-lookup"><span data-stu-id="dc12a-113">In **Name**, type an identifying name for this range of numbers.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="dc12a-114">在您將軌道範圍提交至資料庫之後，您就無法變更此名稱。</span><span class="sxs-lookup"><span data-stu-id="dc12a-114">After you commit the orbit range to the database, you cannot change this name.</span></span>

        
        </div>
    
      - <span data-ttu-id="dc12a-115">若要修改現有的軌道範圍，請在 [搜尋] 欄位中輸入所有或部分的軌道範圍名稱。</span><span class="sxs-lookup"><span data-stu-id="dc12a-115">To modify an existing orbit range, type all or part of the name of the orbit range in the search field.</span></span> <span data-ttu-id="dc12a-116">在 [軌道式] 的結果清單中，按一下您想要的軌道，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="dc12a-116">In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="dc12a-117">在 [第一個**數位範圍**] 欄位中，輸入此通話公園軌道的延伸範圍起始編號，然後在第二個 [**數位範圍**] 欄位中，輸入範圍的結束數位。</span><span class="sxs-lookup"><span data-stu-id="dc12a-117">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="dc12a-118">該範圍的起始號碼必須小於或等於範圍的結束號碼。</span><span class="sxs-lookup"><span data-stu-id="dc12a-118">The beginning number of the range must be less than or equal to the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="dc12a-119">該範圍的起始號碼值的長度必須等於範圍的結束號碼值長度。</span><span class="sxs-lookup"><span data-stu-id="dc12a-119">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="dc12a-120">軌道範圍必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="dc12a-120">The orbit range must be unique.</span></span> <span data-ttu-id="dc12a-121">此範圍不得與其他任何範圍重疊。</span><span class="sxs-lookup"><span data-stu-id="dc12a-121">This range cannot overlap with any other range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="dc12a-122">如果軌道範圍是以字元 \* 或 # 開頭，則範圍必須大於100。</span><span class="sxs-lookup"><span data-stu-id="dc12a-122">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="dc12a-123">有效值：必須符合正則運算式字串（[\*| #]？ [1-9] \d{0,7}） |（[1-9] \d{0,8}）。</span><span class="sxs-lookup"><span data-stu-id="dc12a-123">Valid values: Must match the regular expression string ([\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="dc12a-124">這表示值必須是開頭為字元 \* 或 # 或數字 1 至 9 的字串 (第一個字元不得為零)。</span><span class="sxs-lookup"><span data-stu-id="dc12a-124">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="dc12a-125">如果第一個字元是 \* 或 #，則後續字元必須是數字 1 至 9 (不得為零)。</span><span class="sxs-lookup"><span data-stu-id="dc12a-125">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="dc12a-126">後續字元可以是從0到9的任何數位，最多可達七個其他字元（例如，"#6000"、"*92000"、"* 95551212" 和 "915551212"）。</span><span class="sxs-lookup"><span data-stu-id="dc12a-126">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "*92000", "* 95551212", and "915551212").</span></span> <span data-ttu-id="dc12a-127">如果第一個字元不是 \* 或 #，則第一個字元必須是數位1到9（不能是零），然後再加上最多八個字元（例如，"915551212"，"41212"，"300"）。</span><span class="sxs-lookup"><span data-stu-id="dc12a-127">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span></P>
    > <LI>
    > <P><span data-ttu-id="dc12a-128">每個池子不應超過總計50000的 [軌道式]。</span><span class="sxs-lookup"><span data-stu-id="dc12a-128">You should not have more than a total of 50,000 orbits per pool.</span></span> <span data-ttu-id="dc12a-129">每個軌道範圍通常會包含100或更少的軌道式，但只要包含超過10000的軌道式，就能更大。</span><span class="sxs-lookup"><span data-stu-id="dc12a-129">Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits.</span></span> <span data-ttu-id="dc12a-130">例如，與其指定起始號碼 7000000 與結束號碼 8000000，請考慮指定起始號碼 7000000 與結束號碼 7000100。</span><span class="sxs-lookup"><span data-stu-id="dc12a-130">For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="dc12a-131">在 [**目的地伺服器的 FQDN**] 中，按一下主持通話駐留應用程式之應用程式服務的完整功能變數名稱（FQDN）或服務識別碼。</span><span class="sxs-lookup"><span data-stu-id="dc12a-131">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="dc12a-132">在軌道範圍內由 start 編號和結束編號所指定範圍內的所有來電都會路由到這個伺服器或池子。</span><span class="sxs-lookup"><span data-stu-id="dc12a-132">All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>

7.  <span data-ttu-id="dc12a-133">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dc12a-133">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="dc12a-134">使用 Windows PowerShell 來建立或修改停用通話的數位範圍</span><span class="sxs-lookup"><span data-stu-id="dc12a-134">To use Windows PowerShell to create or modify a range of numbers for parking calls</span></span>

1.  <span data-ttu-id="dc12a-135">登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組的成員的電腦，或使用[Lync server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者許可權。</span><span class="sxs-lookup"><span data-stu-id="dc12a-135">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="dc12a-136">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="dc12a-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="dc12a-137">使用 [**新-CsCallParkOrbit** ] 建立新的軌道編號範圍。</span><span class="sxs-lookup"><span data-stu-id="dc12a-137">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="dc12a-138">使用 [**設定] CsCallParkOrbit**來修改現有的軌道編號範圍。</span><span class="sxs-lookup"><span data-stu-id="dc12a-138">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>
    
    <span data-ttu-id="dc12a-139">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="dc12a-139">At the command line, run:</span></span>
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    <span data-ttu-id="dc12a-140">例如：</span><span class="sxs-lookup"><span data-stu-id="dc12a-140">For example:</span></span>
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    <span data-ttu-id="dc12a-141">下列範例顯示如何修改現有的軌道範圍中的數位，</span><span class="sxs-lookup"><span data-stu-id="dc12a-141">The following example shows how to modify the numbers in an existing orbit range,</span></span>
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dc12a-142">請參閱</span><span class="sxs-lookup"><span data-stu-id="dc12a-142">See Also</span></span>


[<span data-ttu-id="dc12a-143">在 Lync Server 2013 中刪除通話駐留軌道範圍</span><span class="sxs-lookup"><span data-stu-id="dc12a-143">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)  


[<span data-ttu-id="dc12a-144">新-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="dc12a-144">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[<span data-ttu-id="dc12a-145">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="dc12a-145">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

