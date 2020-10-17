---
title: Lync Server 2013：將使用者移至另一個集區
description: Lync Server 2013：將使用者移至另一個集區。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21012e0df7567a79bca018d194878c85b8653ae4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566389"
---
# <a name="move-users-to-another-pool-in-lync-server-2013"></a><span data-ttu-id="bdf5a-103">在 Lync Server 2013 中將使用者移至另一個集區</span><span class="sxs-lookup"><span data-stu-id="bdf5a-103">Move users to another pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="bdf5a-104">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="bdf5a-104">

<span> </span></span></span>

<span data-ttu-id="bdf5a-105">_**主題上次修改日期：** 2018-02-09_</span><span class="sxs-lookup"><span data-stu-id="bdf5a-105">_**Topic Last Modified:** 2018-02-09_</span></span>

<span data-ttu-id="bdf5a-106">您可以使用 Lync Server 控制台將使用者指派至特定的伺服器或集區。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-106">You can use Lync Server Control Panel to assign users to a specific server or pool.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="bdf5a-107">將所有現有使用者從執行 Lync Server 2010 或更早版本的來源集區移至複雜 Active Directory 環境中的 Lync Server 2013 目的地集區，可能會導致 Active Directory 複寫速度變慢。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-107">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Lync Server 2013 destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="bdf5a-108">若要避免這種情況，您可以使用搜尋篩選器，從執行 Lync Server 2010 或更早版本的集區中移動使用者，也可以使用 Lync Server 管理命令介面來移動具有 Cmdlet 的使用者。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-108">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Lync Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="bdf5a-109">此外，篩選功能可與 Lync Server 2013 使用者搭配使用。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-109">Also, the filter functionality works with Lync Server 2013 users.</span></span>



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="bdf5a-110">將選取的使用者移至不同的伺服器或集區</span><span class="sxs-lookup"><span data-stu-id="bdf5a-110">To move selected users to a different server or pool</span></span>

1.  <span data-ttu-id="bdf5a-111">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bdf5a-112">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bdf5a-113">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bdf5a-114">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="bdf5a-115">在 **[搜尋使用者]** 方塊中，輸入您要的使用者帳戶的完整或開頭部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI)，然後按一下 **[尋找]**。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="bdf5a-116">在表格中，選取清單中的特定使用者或使用者。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-116">In the table, select a specific user or users in the list.</span></span>

6.  <span data-ttu-id="bdf5a-117">在 [ **動作** ] 功能表上，按一下 [ **將選取的使用者移至集**區]。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-117">On the **Action** menu, click **Move selected users to pool**.</span></span>

7.  <span data-ttu-id="bdf5a-118">在 [ **移動使用者**] 中，選取要將使用者移至 [ **目的地註冊區集**區] 的集區。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-118">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>

8.  <span data-ttu-id="bdf5a-119"> (選用) 若目的地伺服器或集區無法使用，請選取 [ **強制** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-119">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="bdf5a-120">如果您選取 [ <STRONG>強制</STRONG>]，使用者帳戶會移動，但不會移動已排程會議和連絡人的相關使用者資料。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-120">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="bdf5a-121">將一個伺服器或集區中的所有使用者移至不同的伺服器或集區</span><span class="sxs-lookup"><span data-stu-id="bdf5a-121">To move all users from one server or pool to a different server or pool</span></span>

1.  <span data-ttu-id="bdf5a-122">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bdf5a-123">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bdf5a-124">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bdf5a-125">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-125">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="bdf5a-126">在 [ **動作** ] 功能表上，按一下 [ **將所有使用者移至集**區]。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-126">On the **Action** menu, click **Move all users to pool**.</span></span>

5.  <span data-ttu-id="bdf5a-127">在 [ **移動使用者**] 的 [ **來源註冊集**區] 中，選取包含您要移動之使用者帳戶的集區。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-127">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

6.  <span data-ttu-id="bdf5a-128">在 [ **目的地登記集**區] 中，選取要將使用者移至其中的集區。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-128">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>

7.  <span data-ttu-id="bdf5a-129"> (選用) 若目的地伺服器或集區無法使用，請選取 [ **強制** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-129">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="bdf5a-130">如果您選取 [ <STRONG>強制</STRONG>]，使用者帳戶會移動，但不會移動已排程會議和連絡人的相關使用者資料。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-130">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="bdf5a-131">若要使用篩選將使用者從一個集區移至另一個集區</span><span class="sxs-lookup"><span data-stu-id="bdf5a-131">To move users from one pool to a different pool by using a filter</span></span>

1.  <span data-ttu-id="bdf5a-132">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bdf5a-133">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bdf5a-134">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bdf5a-135">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-135">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="bdf5a-136">在 [ **使用者搜尋**] 中，按一下 [ **搜尋**]，然後按一下 [ **新增篩選**]。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-136">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>

5.  <span data-ttu-id="bdf5a-137">在搜尋準則中，選取 [ **註冊集**區]，選取 [ **等於**]，選取 [目前的 **集區 FQDN**]，然後按一下 [ **尋找**]。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-137">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>

6.  <span data-ttu-id="bdf5a-138">在 [ **動作** ] 功能表上，按一下 [ **將所有使用者移至集**區]。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-138">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bdf5a-139">將篩選套用至現有的一組使用者時，選項 [ <STRONG>將所有使用者移至</STRONG> 集區] 是在篩選的使用者子集的內容中，而不是 <STRONG><EM>所有</EM></STRONG> 可能的使用者。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-139">When a filter is applied to an existing set of users, the option <STRONG>Move all users to pool</STRONG> is in the context of the filtered subset of users, not <STRONG><EM>all</EM></STRONG> possible users.</span></span>

    
    </div>

7.  <span data-ttu-id="bdf5a-140">在 [ **移動使用者**] 的 [ **來源註冊集**區] 中，選取包含您要移動之使用者帳戶的集區。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-140">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>

8.  <span data-ttu-id="bdf5a-141">在 [ **目的地登記集**區] 中，選取要將使用者移至其中的集區。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-141">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>

9.  <span data-ttu-id="bdf5a-142"> (選用) 若目的地伺服器或集區無法使用，請選取 [ **強制** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-142">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="bdf5a-143">如果您選取 [ <STRONG>強制</STRONG>]，使用者帳戶會移動，但不會移動已排程會議和連絡人的相關使用者資料。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-143">If you select <STRONG>Force</STRONG>, the user account is moved, but associated user data such scheduled conferences and contacts is not moved.</span></span>

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="bdf5a-144">使用 Windows PowerShell Cmdlet 將使用者從一個集區移至另一個集區</span><span class="sxs-lookup"><span data-stu-id="bdf5a-144">To move users from one pool to another using Windows PowerShell cmdlets</span></span>

1.  <span data-ttu-id="bdf5a-145">根據您執行 Windows PowerShell 命令的方式 (（本機或遠端) ），您必須以正確的 Lync Server 2013 系統管理角色的成員身分登入，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bdf5a-145">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Lync Server 2013 administrative roles as follows:</span></span>
    
    1.  <span data-ttu-id="bdf5a-146">如果您是在本機電腦上執行命令 (例如，您可以直接登入前端伺服器) ：登入安裝了 Lync Server 管理命令介面的電腦作為 RTCUniversalServerAdmins 群組的成員，或使用 [Lync server 2013 的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者權限。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-146">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>
    
    2.  <span data-ttu-id="bdf5a-147">如果您是在另一部電腦上遠端執行命令 (例如，登入您的電腦，然後從遠端的 Standard Edition 前端伺服器上執行命令) ：從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-147">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bdf5a-148">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="bdf5a-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="bdf5a-149">若要移動單一使用者，請使用 Move-CsUser Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bdf5a-149">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    <span data-ttu-id="bdf5a-150">若要移動的使用者為使用者 Pilar Ackerman，使用者將從目前指派的主集區移至集區 pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="bdf5a-150">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>

4.  <span data-ttu-id="bdf5a-151">若要移動大量的使用者，請搭配 **Get-CsUser** Cmdlet 使用篩選器，並將產生的使用者集合傳遞給 **Move-CsUser**：</span><span class="sxs-lookup"><span data-stu-id="bdf5a-151">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    <span data-ttu-id="bdf5a-152">**Get-CsUser**和**Move-CsUser**的合併命令可能會造成下列情況：</span><span class="sxs-lookup"><span data-stu-id="bdf5a-152">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bdf5a-153">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bdf5a-153">See Also</span></span>


[<span data-ttu-id="bdf5a-154">在 Lync Server 2013 中修改使用者帳戶屬性</span><span class="sxs-lookup"><span data-stu-id="bdf5a-154">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

<span data-ttu-id="bdf5a-155"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="bdf5a-155"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

