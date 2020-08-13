---
title: Lync Server 2013：建立或修改未指派號碼範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an unassigned number range
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412748(v=OCS.15)
ms:contentKeyID: 48185013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7252b2cda2f957dc72e006b7ce298bc5dd87fd5a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-unassigned-number-range-in-lync-server-2013"></a><span data-ttu-id="ea1de-102">在 Lync Server 2013 中建立或修改未指派號碼範圍</span><span class="sxs-lookup"><span data-stu-id="ea1de-102">Create or modify an unassigned number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea1de-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ea1de-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ea1de-104">使用下列其中一個程式來設定宣告應用程式的未指派號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="ea1de-104">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ea1de-105">在您設定未指派的號碼表之前，您必須已定義一或多個宣告或設定 Exchange 整合通訊 (UM) 自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="ea1de-105">Before you configure the unassigned number table, you must have already defined one or more announcements or set up an Exchange Unified Messaging (UM) Auto Attendant.</span></span>



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="ea1de-106">使用 Lync Server 控制台設定未指派的電話號碼</span><span class="sxs-lookup"><span data-stu-id="ea1de-106">To use Lync Server Control Panel to configure unassigned phone numbers</span></span>

1.  <span data-ttu-id="ea1de-107">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="ea1de-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="ea1de-108">如需詳細資訊，請參閱[在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="ea1de-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ea1de-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="ea1de-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ea1de-110">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="ea1de-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ea1de-111">在左導覽列中，依序按一下 [**語音功能**] 和 [**未指派的號碼**]。</span><span class="sxs-lookup"><span data-stu-id="ea1de-111">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>

4.  <span data-ttu-id="ea1de-112">在 [**未指派的號碼**] 頁面上，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="ea1de-112">On the **Unassigned Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="ea1de-113">若要建立新的號碼範圍，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="ea1de-113">To create a new number range, click **New**.</span></span> <span data-ttu-id="ea1de-114">在 **[名稱]** 中，輸入此號碼範圍的識別名稱。</span><span class="sxs-lookup"><span data-stu-id="ea1de-114">In **Name**, type an identifying name for this range of numbers.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ea1de-115">在您認可新的未指派號碼範圍至資料庫之後，就無法變更此名稱。</span><span class="sxs-lookup"><span data-stu-id="ea1de-115">After you commit the new unassigned number range to the database, you cannot change this name.</span></span>

        
        </div>
    
      - <span data-ttu-id="ea1de-116">若要修改現有的號碼範圍，請在 [搜尋] 欄位中輸入編號範圍的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="ea1de-116">To modify an existing number range, type all or part of the name of the number range in the search field.</span></span> <span data-ttu-id="ea1de-117">在產生的號碼範圍清單中，按一下您想要的名稱，然後按一下 [**編輯**]，再按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="ea1de-117">In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="ea1de-118">在第一個 **[號碼範圍]** 欄位中輸入範圍的開始號碼，在第二個 **[號碼範圍]** 欄位中輸入範圍的結束號碼。</span><span class="sxs-lookup"><span data-stu-id="ea1de-118">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="ea1de-119">該範圍的起始號碼必須小於或等於範圍的結束號碼。</span><span class="sxs-lookup"><span data-stu-id="ea1de-119">The beginning number of the range must be less than or equal to the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="ea1de-120">如果範圍的開始號碼或範圍的結束號碼包含分機號碼，則範圍的開始號碼和結束號碼都必須包含分機，且開始號碼和結束號碼的分機號碼必須相同。</span><span class="sxs-lookup"><span data-stu-id="ea1de-120">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="ea1de-121">號碼必須符合正則運算式 (電話： ) ？ (\+) ？ [1-9] \d {0,17} (; ext = [1-9] \d {0,9}) ？。</span><span class="sxs-lookup"><span data-stu-id="ea1de-121">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="ea1de-122">這表示數位可以從電話號碼開始： (若您未指定該字串，就會自動為您新增) 、加號 (+) 及數位1到9。</span><span class="sxs-lookup"><span data-stu-id="ea1de-122">This means the number may begin with the string tel: (if you don’t specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="ea1de-123">電話號碼最多可達 17 位，且後面可以再加分機，格式為 ;ext= 分機號碼。</span><span class="sxs-lookup"><span data-stu-id="ea1de-123">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="ea1de-124">在 **[宣告服務]** 中，執行下列其中一個動作：</span><span class="sxs-lookup"><span data-stu-id="ea1de-124">In **Announcement service**, do one of the following:</span></span>
    
      - <span data-ttu-id="ea1de-125">按一下 **[宣告]**。</span><span class="sxs-lookup"><span data-stu-id="ea1de-125">Click **Announcement**.</span></span>
    
      - <span data-ttu-id="ea1de-126">按一下 **[Exchange UM]**。</span><span class="sxs-lookup"><span data-stu-id="ea1de-126">Click **Exchange UM**.</span></span>

7.  <span data-ttu-id="ea1de-127">如果您在上一個步驟按了 **[宣告]**，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ea1de-127">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    1.  <span data-ttu-id="ea1de-128">在 **[目的地伺服器的 FQDN]** 下方按一下 **[選取]**，按一下執行宣告應用程式之應用程式服務的服務 ID (此服務會處理此未指派號碼範圍的來電)，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ea1de-128">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    2.  <span data-ttu-id="ea1de-129">在 **[宣告]** 中，按一下要針對此未指派號碼範圍播放的宣告。</span><span class="sxs-lookup"><span data-stu-id="ea1de-129">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>

8.  <span data-ttu-id="ea1de-130">如果您在上一個步驟按了 **[Exchange UM]**，請在 **[自動語音應答電話號碼]** 下方按一下 **[選取]**，按一下要用於此未指派號碼範圍的電話號碼，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ea1de-130">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>

9.  <span data-ttu-id="ea1de-131">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ea1de-131">Click **OK**.</span></span>

10. <span data-ttu-id="ea1de-132">在 [**未指派的號碼**] 頁面上，確定未指派的號碼範圍以您想要的順序排列。</span><span class="sxs-lookup"><span data-stu-id="ea1de-132">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want.</span></span> <span data-ttu-id="ea1de-133">若要變更某個範圍在表格中的位置，請在範圍清單中按一下一個或多個連續的名稱，然後按一下向上鍵或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="ea1de-133">To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="ea1de-134">Lync Server 會從上到下搜尋未指派號碼表格，並使用符合未指派號碼的第一個範圍。</span><span class="sxs-lookup"><span data-stu-id="ea1de-134">Lync Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="ea1de-135">如果您有重疊的範圍，且有一個範圍指定最後採取的動作，請確定該範圍位於清單底部。</span><span class="sxs-lookup"><span data-stu-id="ea1de-135">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

    
    </div>

11. <span data-ttu-id="ea1de-136">當您以您想要的順序排列未指派的號碼範圍時，請按一下 [**全部認可**]。</span><span class="sxs-lookup"><span data-stu-id="ea1de-136">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="ea1de-137">使用 Windows PowerShell 設定未指派的電話號碼</span><span class="sxs-lookup"><span data-stu-id="ea1de-137">To use Windows PowerShell to configure unassigned phone numbers</span></span>

1.  <span data-ttu-id="ea1de-138">以[Lync server 2013 的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述，登入安裝了 Lync Server 管理命令介面的電腦，以作為 RTCUniversalServerAdmins 群組的成員或必要的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="ea1de-138">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ea1de-139">啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="ea1de-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ea1de-140">使用**New-CsUnassignedNumber**建立新的未指派號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="ea1de-140">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="ea1de-141">使用**Set-CsUnassignedNumber**修改現有的未指派號碼範圍。</span><span class="sxs-lookup"><span data-stu-id="ea1de-141">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="ea1de-142">如果您有重疊的範圍，且想要依特定順序套用範圍，請包含 Priority 參數。</span><span class="sxs-lookup"><span data-stu-id="ea1de-142">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter.</span></span> <span data-ttu-id="ea1de-143">具有最高優先順序的範圍會套用至通話。</span><span class="sxs-lookup"><span data-stu-id="ea1de-143">The range with the highest priority will be applied to the call.</span></span>

    
    </div>
    
    <span data-ttu-id="ea1de-144">在命令列中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="ea1de-144">At the command line, do one of the following:</span></span>
    
      - <span data-ttu-id="ea1de-145">若要建立宣告服務的號碼範圍，請執行：</span><span class="sxs-lookup"><span data-stu-id="ea1de-145">To create a number range for an Announcement service, run:</span></span>
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - <span data-ttu-id="ea1de-146">或者，若要建立 Exchange UM 自動語音應答的號碼範圍，請執行：</span><span class="sxs-lookup"><span data-stu-id="ea1de-146">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    <span data-ttu-id="ea1de-147">例如：</span><span class="sxs-lookup"><span data-stu-id="ea1de-147">For example:</span></span>
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    <span data-ttu-id="ea1de-148">或</span><span class="sxs-lookup"><span data-stu-id="ea1de-148">Or</span></span>
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    <span data-ttu-id="ea1de-149">下列範例會顯示如何修改現有未指派號碼範圍中的號碼：</span><span class="sxs-lookup"><span data-stu-id="ea1de-149">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ea1de-150">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ea1de-150">See Also</span></span>


[<span data-ttu-id="ea1de-151">在 Lync Server 2013 中刪除未指派的號碼範圍</span><span class="sxs-lookup"><span data-stu-id="ea1de-151">Delete an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-delete-an-unassigned-number-range.md)  


[<span data-ttu-id="ea1de-152">New-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="ea1de-152">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUnassignedNumber)  
[<span data-ttu-id="ea1de-153">Set-CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="ea1de-153">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUnassignedNumber)  
[<span data-ttu-id="ea1de-154">CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="ea1de-154">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

