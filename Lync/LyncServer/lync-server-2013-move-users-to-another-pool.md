---
title: Lync Server 2013：將使用者移至另一個池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fb716c0b551475a53cacf09be10ffdc039f5db8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-another-pool-in-lync-server-2013"></a><span data-ttu-id="d1c05-102">在 Lync Server 2013 中將使用者移至另一個池</span><span class="sxs-lookup"><span data-stu-id="d1c05-102">Move users to another pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="d1c05-103">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="d1c05-103"></span></span>

<span data-ttu-id="d1c05-104">_**主題上次修改日期：** 2018-02-09_</span><span class="sxs-lookup"><span data-stu-id="d1c05-104">_**Topic Last Modified:** 2018-02-09_</span></span>

<span data-ttu-id="d1c05-105">您可以使用 Lync Server [控制台]，將使用者指派給特定的伺服器或文件庫。</span><span class="sxs-lookup"><span data-stu-id="d1c05-105">You can use Lync Server Control Panel to assign users to a specific server or pool.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="d1c05-106">將所有現有使用者從執行 Lync Server 2010 或較舊版本的來源池移至複雜作用中的 Active Directory 環境中的 Lync Server 2013 目的地池，可能會導致較慢的 Active Directory 複製。</span><span class="sxs-lookup"><span data-stu-id="d1c05-106">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Lync Server 2013 destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="d1c05-107">若要避免這種情況，您可以使用搜尋篩選器，從執行 Lync Server 2010 或較舊版本的 pool 中移動使用者，或者您可以使用 Lync Server 管理命令介面來移動使用 Cmdlet 的使用者。</span><span class="sxs-lookup"><span data-stu-id="d1c05-107">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Lync Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="d1c05-108">此外，篩選功能也可與 Lync Server 2013 使用者搭配使用。</span><span class="sxs-lookup"><span data-stu-id="d1c05-108">Also, the filter functionality works with Lync Server 2013 users.</span></span>



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="d1c05-109">若要將選取的使用者移至不同的伺服器或文件庫</span><span class="sxs-lookup"><span data-stu-id="d1c05-109">To move selected users to a different server or pool</span></span>

1.  <span data-ttu-id="d1c05-110">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d1c05-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d1c05-111">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="d1c05-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d1c05-112">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d1c05-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d1c05-113">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="d1c05-113">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="d1c05-114">在 [**搜尋使用者**] 方塊中，輸入您想要的 [顯示名稱]、[名字]、[姓氏]、[安全帳戶管理員] （SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部或第一個部分，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="d1c05-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="d1c05-115">在表格中，選取清單中特定的使用者或使用者。</span><span class="sxs-lookup"><span data-stu-id="d1c05-115">In the table, select a specific user or users in the list.</span></span>

6.  <span data-ttu-id="d1c05-116">在 [**動作**] 功能表上，按一下 [**將選取的使用者移至資源庫**]。</span><span class="sxs-lookup"><span data-stu-id="d1c05-116">On the **Action** menu, click **Move selected users to pool**.</span></span>

7.  <span data-ttu-id="d1c05-117">在 [**移動使用者**] 中，選取您要在 [**目的地註冊機構**] 中將使用者移至哪個池。</span><span class="sxs-lookup"><span data-stu-id="d1c05-117">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>

8.  <span data-ttu-id="d1c05-118">可選如果目的地伺服器或池無法使用，請選取 [**強制**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d1c05-118">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="d1c05-119">如果您選取 [<STRONG>強制</STRONG>]，使用者帳戶就會移動，但相關的使用者資料（例如，已安排的會議和連絡人）不會移動。</span><span class="sxs-lookup"><span data-stu-id="d1c05-119">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="d1c05-120">將所有使用者從一個伺服器或文檔池移至另一個伺服器或文檔池中</span><span class="sxs-lookup"><span data-stu-id="d1c05-120">To move all users from one server or pool to a different server or pool</span></span>

1.  <span data-ttu-id="d1c05-121">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d1c05-121">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d1c05-122">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="d1c05-122">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d1c05-123">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d1c05-123">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d1c05-124">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="d1c05-124">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="d1c05-125">在 [**動作**] 功能表上，按一下 [**將所有使用者移至資源庫**]。</span><span class="sxs-lookup"><span data-stu-id="d1c05-125">On the **Action** menu, click **Move all users to pool**.</span></span>

5.  <span data-ttu-id="d1c05-126">在 [**移動使用者**] 中，選取包含您要在 [**來源註冊機構] 池中**移動之使用者帳戶的池。</span><span class="sxs-lookup"><span data-stu-id="d1c05-126">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

6.  <span data-ttu-id="d1c05-127">在 [**目的地註冊機構] 池中**，選取您要將使用者移至哪個池。</span><span class="sxs-lookup"><span data-stu-id="d1c05-127">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>

7.  <span data-ttu-id="d1c05-128">可選如果目的地伺服器或池無法使用，請選取 [**強制**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d1c05-128">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="d1c05-129">如果您選取 [<STRONG>強制</STRONG>]，使用者帳戶就會移動，但相關的使用者資料（例如，已安排的會議和連絡人）不會移動。</span><span class="sxs-lookup"><span data-stu-id="d1c05-129">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="d1c05-130">使用篩選將使用者從一個池中移到另一個池</span><span class="sxs-lookup"><span data-stu-id="d1c05-130">To move users from one pool to a different pool by using a filter</span></span>

1.  <span data-ttu-id="d1c05-131">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d1c05-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d1c05-132">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="d1c05-132">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d1c05-133">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d1c05-133">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d1c05-134">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="d1c05-134">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="d1c05-135">在 [**使用者搜尋**] 中，按一下 [**搜尋**]，然後按一下 [**新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="d1c05-135">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>

5.  <span data-ttu-id="d1c05-136">在搜尋準則中，選取 [**註冊機構池**]，選取 [**等於**]，選取 [**目前池 FQDN**]，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="d1c05-136">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>

6.  <span data-ttu-id="d1c05-137">在 [**動作**] 功能表上，按一下 [**將所有使用者移至資源庫**]。</span><span class="sxs-lookup"><span data-stu-id="d1c05-137">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1c05-138">當篩選套用至現有的一組使用者時，會在篩選的使用者子集的內容（而非<STRONG><EM>所有</EM></STRONG>可能的使用者）中，選擇 [<STRONG>將所有使用者移至資源庫</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="d1c05-138">When a filter is applied to an existing set of users, the option <STRONG>Move all users to pool</STRONG> is in the context of the filtered subset of users, not <STRONG><EM>all</EM></STRONG> possible users.</span></span>

    
    </div>

7.  <span data-ttu-id="d1c05-139">在 [**移動使用者**] 中，選取包含您要在 [**來源註冊機構] 池中**移動之使用者帳戶的池。</span><span class="sxs-lookup"><span data-stu-id="d1c05-139">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

8.  <span data-ttu-id="d1c05-140">在 [**目的地註冊機構] 池中**，選取您要移動使用者的池。</span><span class="sxs-lookup"><span data-stu-id="d1c05-140">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>

9.  <span data-ttu-id="d1c05-141">可選如果目的地伺服器或池無法使用，請選取 [**強制**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d1c05-141">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="d1c05-142">如果您選取 [<STRONG>強制</STRONG>]，使用者帳戶就會移動，但相關的使用者資料（例如，已安排的會議和連絡人）不會移動。</span><span class="sxs-lookup"><span data-stu-id="d1c05-142">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="d1c05-143">使用 Windows PowerShell Cmdlet 將使用者從一個池中移至另一個池</span><span class="sxs-lookup"><span data-stu-id="d1c05-143">To move users from one pool to another using Windows PowerShell cmdlets</span></span>

1.  <span data-ttu-id="d1c05-144">視您執行的是 Windows PowerShell 命令（本機或遠端）而定，您需要以正確的 Lync Server 2013 管理角色的成員身分登入，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d1c05-144">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Lync Server 2013 administrative roles as follows:</span></span>
    
    1.  <span data-ttu-id="d1c05-145">如果您在本機電腦上執行命令（例如，您是直接登入前端伺服器）：登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組成員的電腦，或使用[Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者權利。</span><span class="sxs-lookup"><span data-stu-id="d1c05-145">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>
    
    2.  <span data-ttu-id="d1c05-146">如果您是在另一部電腦遠端執行命令（例如，登入您的電腦，並在標準版前端伺服器上遠端執行命令）：從指派給 CsUserAdministrator 角色或 CsAdministrator 的使用者帳戶。角色，請登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d1c05-146">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d1c05-147">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="d1c05-147">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d1c05-148">若要移動單一使用者，請使用 Move-csuser Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d1c05-148">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    <span data-ttu-id="d1c05-149">使用者要移動的使用者是 Pilar 方，而使用者會從目前指派的主池中移至 [資源庫] pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="d1c05-149">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>

4.  <span data-ttu-id="d1c05-150">若要移動大量的使用者，請使用**move-csuser** Cmdlet 的篩選器，並將產生的使用者組傳遞到**move-csuser**：</span><span class="sxs-lookup"><span data-stu-id="d1c05-150">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    <span data-ttu-id="d1c05-151">**Move-csuser**和**move-csuser**的合併命令可能會造成下列情況：</span><span class="sxs-lookup"><span data-stu-id="d1c05-151">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d1c05-152">請參閱</span><span class="sxs-lookup"><span data-stu-id="d1c05-152">See Also</span></span>


[<span data-ttu-id="d1c05-153">在 Lync Server 2013 中修改使用者帳戶屬性</span><span class="sxs-lookup"><span data-stu-id="d1c05-153">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

<span data-ttu-id="d1c05-154"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="d1c05-154"></span></span></div>

