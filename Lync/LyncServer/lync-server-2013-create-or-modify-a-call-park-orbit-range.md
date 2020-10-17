---
title: Lync Server 2013：建立或修改通話駐留軌道範圍
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
ms.openlocfilehash: e1ecf0a1313519a74bb054c7fa3b441580758018
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514780"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-lync-server-2013"></a><span data-ttu-id="f041a-102">在 Lync Server 2013 中建立或修改通話駐留軌道範圍</span><span class="sxs-lookup"><span data-stu-id="f041a-102">Create or modify a Call Park orbit range in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f041a-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f041a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f041a-104">使用下列其中一個程序來建立或修改通話駐留軌道範圍。</span><span class="sxs-lookup"><span data-stu-id="f041a-104">Use one of the following procedures to create or modify a call park orbit range.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="f041a-105">使用 Lync Server 控制台建立或修改駐留通話的號碼範圍</span><span class="sxs-lookup"><span data-stu-id="f041a-105">To use Lync Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1.  <span data-ttu-id="f041a-106">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="f041a-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="f041a-107">如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="f041a-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f041a-108">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="f041a-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f041a-109">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="f041a-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f041a-110">在左導覽列中，依序按一下 **[語音功能]**、**[通話駐留]**。</span><span class="sxs-lookup"><span data-stu-id="f041a-110">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4.  <span data-ttu-id="f041a-111">在 **[通話駐留]** 頁面上，執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="f041a-111">On the **Call Park** page, do one of the following:</span></span>
    
      - <span data-ttu-id="f041a-p103">若要建立新的軌道範圍，可按一下 **[新增]**。在 **[名稱]** 中，輸入此號碼範圍的識別名稱。</span><span class="sxs-lookup"><span data-stu-id="f041a-p103">To create a new orbit range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f041a-114">當您將軌道範圍認可至資料庫之後，就無法變更此名稱。</span><span class="sxs-lookup"><span data-stu-id="f041a-114">After you commit the orbit range to the database, you cannot change this name.</span></span>

        
        </div>
    
      - <span data-ttu-id="f041a-p104">若要修改現有的軌道範圍，可在搜尋欄位中輸入軌道範圍的所有或部分名稱。在軌道的結果清單中，按一下您想要的軌道，接著依序按一下 **[編輯]** 及 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="f041a-p104">To modify an existing orbit range, type all or part of the name of the orbit range in the search field. In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f041a-117">在第一個 **[號碼範圍]** 欄位中，輸入此項通話駐留軌道分機號碼範圍的開頭號碼，並在第二個 **[號碼範圍]** 欄位中，輸入該範圍的結束號碼。</span><span class="sxs-lookup"><span data-stu-id="f041a-117">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="f041a-118">該範圍的起始號碼必須小於或等於範圍的結束號碼。</span><span class="sxs-lookup"><span data-stu-id="f041a-118">The beginning number of the range must be less than or equal to the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="f041a-119">該範圍的起始號碼值的長度必須等於範圍的結束號碼值長度。</span><span class="sxs-lookup"><span data-stu-id="f041a-119">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="f041a-p105">軌道範圍必須是唯一的。此範圍不得與其他任何範圍重疊。</span><span class="sxs-lookup"><span data-stu-id="f041a-p105">The orbit range must be unique. This range cannot overlap with any other range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="f041a-122">如果軌道範圍開頭為 \* 或 #，則範圍必須大於 100。</span><span class="sxs-lookup"><span data-stu-id="f041a-122">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="f041a-123">有效的值：必須符合正則運算式字串 ( [ \* | #]？ [1-9] \d {0,7}) | ( [1-9] \d {0,8}) 。</span><span class="sxs-lookup"><span data-stu-id="f041a-123">Valid values: Must match the regular expression string ([\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="f041a-124">這表示值必須是開頭為字元 \* 或 # 或數字 1 至 9 的字串 (第一個字元不得為零)。</span><span class="sxs-lookup"><span data-stu-id="f041a-124">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="f041a-125">如果第一個字元是 \* 或 #，則後續字元必須是數字 1 至 9 (不得為零)。</span><span class="sxs-lookup"><span data-stu-id="f041a-125">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="f041a-126">後續字元可以是0到9的任何數位，最多可以有七個其他字元 (例如，"#6000"、"*92000"、"* 95551212" 和 "915551212" ) 。</span><span class="sxs-lookup"><span data-stu-id="f041a-126">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "*92000", "* 95551212", and "915551212").</span></span> <span data-ttu-id="f041a-127">如果第一個字元不是 \* 或 #，則第一個字元必須是數字 1 至 9 (不得為零)，後面最多接著八個字元，每一個字元都是數字 0 至 9 (例如，"915551212"、"41212"、"300")。</span><span class="sxs-lookup"><span data-stu-id="f041a-127">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span></P>
    > <LI>
    > <P><span data-ttu-id="f041a-p107">每個集區的軌道總數不得超過 50,000 個。每個軌道範圍通常會涵蓋 100 個以下的軌道，但只要總數不超過 10,000 個軌道，可以大一些。例如，與其指定開頭號碼 7000000 與結束號碼 8000000，請考慮指定開始號碼 7000000 與結束號碼 7000100。</span><span class="sxs-lookup"><span data-stu-id="f041a-p107">You should not have more than a total of 50,000 orbits per pool. Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="f041a-p108">在 **[目的地伺服器的 FQDN]** 中，按一下裝載通話保留應用程式的應用程式服務之完整網域名稱 (FQDN) 或服務 ID。保留給軌道範圍中由開始號碼與結束號碼所指定之範圍內的號碼的所有通話，將會轉接至此伺服器或集區。</span><span class="sxs-lookup"><span data-stu-id="f041a-p108">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application. All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>

7.  <span data-ttu-id="f041a-133">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="f041a-133">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="f041a-134">使用 Windows PowerShell 建立或修改駐留通話的號碼範圍</span><span class="sxs-lookup"><span data-stu-id="f041a-134">To use Windows PowerShell to create or modify a range of numbers for parking calls</span></span>

1.  <span data-ttu-id="f041a-135">以 [Lync server 2013 的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述，登入安裝了 Lync Server 管理命令介面的電腦，以作為 RTCUniversalServerAdmins 群組的成員或必要的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="f041a-135">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f041a-136">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="f041a-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f041a-137">使用 **New-CsCallParkOrbit** 來建立新的軌道號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="f041a-137">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="f041a-138">使用 **Set-CsCallParkOrbit** 來修改現有的軌道號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="f041a-138">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>
    
    <span data-ttu-id="f041a-139">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="f041a-139">At the command line, run:</span></span>
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    <span data-ttu-id="f041a-140">例如：</span><span class="sxs-lookup"><span data-stu-id="f041a-140">For example:</span></span>
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    <span data-ttu-id="f041a-141">下列範例示範如何修改現有軌道範圍中的號碼，</span><span class="sxs-lookup"><span data-stu-id="f041a-141">The following example shows how to modify the numbers in an existing orbit range,</span></span>
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f041a-142">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f041a-142">See Also</span></span>


[<span data-ttu-id="f041a-143">在 Lync Server 2013 中刪除通話駐留軌道範圍</span><span class="sxs-lookup"><span data-stu-id="f041a-143">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)  


[<span data-ttu-id="f041a-144">新 Get-cscallparkorbit</span><span class="sxs-lookup"><span data-stu-id="f041a-144">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[<span data-ttu-id="f041a-145">Get-cscallparkorbit</span><span class="sxs-lookup"><span data-stu-id="f041a-145">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

