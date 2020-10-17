---
title: Lync Server 2013：建立或修改網路網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network site
ms:assetid: 14e24856-9996-4da4-9f31-300940bdf5aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398218(v=OCS.15)
ms:contentKeyID: 48183488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60119e137851bbaa8dc7b6735202132085bb8d34
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506120"
---
# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a><span data-ttu-id="737a6-102">在 Lync Server 2013 中建立或修改網路網站</span><span class="sxs-lookup"><span data-stu-id="737a6-102">Create or modify a network site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="737a6-103">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="737a6-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="737a6-104">通話許可控制 (CAC)、E9-1-1 和媒體旁路的部署需視「網站」\*\* 的設定而定，而網站是在網路地區內部定義，且一定與網路地區相關聯。</span><span class="sxs-lookup"><span data-stu-id="737a6-104">Call admission control (CAC), E9-1-1, and media bypass deployments rely on the configuration of *network sites* which are defined within and always associated with a network region.</span></span> <span data-ttu-id="737a6-105">網路網站代表分支辦公室位置、一組大樓或校園。</span><span class="sxs-lookup"><span data-stu-id="737a6-105">A network site represents a branch office location, a set of buildings, or a campus.</span></span> <span data-ttu-id="737a6-106">多個網站可代表具有類似頻寬的子網路集合。</span><span class="sxs-lookup"><span data-stu-id="737a6-106">Network sites represent collections of subnets with similar bandwidth.</span></span>

<span data-ttu-id="737a6-p102">使用下列程序可建立或修改網站。例如，如果您已為一個語音功能建立網站，就不需要再建立新的網站，其他語音功能會使用這些相同的網站。不過，您可能需要修改現有網站定義，以便套用特定的功能設定。例如，如果已為 E9-1-1 建立了網站，在部署通話許可控制期間需要修改網站，以便套用頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="737a6-p102">Use the following procedures to create or modify network sites. For example, if you have already created network sites for one Voice feature, you do not need to create new network sites; other Voice features will use those same sites. You may, however, need to modify an existing network site definition to apply feature-specific settings. For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="737a6-111">您可在部署文件中，找到與每個進階語音功能相關之網站的特定範例與需求：</span><span class="sxs-lookup"><span data-stu-id="737a6-111">Where they exist, you can find specific examples and requirements for network sites as they pertain to an advanced Voice feature in the Deployment documentation for each feature:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="737a6-112"><A href="lync-server-2013-configure-network-sites-for-cac.md">在 Lync Server 2013 中設定 CAC 的網路網站</A></span><span class="sxs-lookup"><span data-stu-id="737a6-112"><A href="lync-server-2013-configure-network-sites-for-cac.md">Configure network sites for CAC in Lync Server 2013</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="737a6-113">如需使用網路網站的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="737a6-113">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="737a6-114">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="737a6-114">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [<span data-ttu-id="737a6-115">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="737a6-115">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [<span data-ttu-id="737a6-116">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="737a6-116">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [<span data-ttu-id="737a6-117">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="737a6-117">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a><span data-ttu-id="737a6-118">建立網站</span><span class="sxs-lookup"><span data-stu-id="737a6-118">Create a Network Site</span></span>

<span data-ttu-id="737a6-119">建立網路地區，以便提供給通話許可控制、E9-1-1 或媒體旁路使用。</span><span class="sxs-lookup"><span data-stu-id="737a6-119">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a><span data-ttu-id="737a6-120">使用管理命令介面建立網站</span><span class="sxs-lookup"><span data-stu-id="737a6-120">To create a network site by using Management Shell</span></span>

1.  <span data-ttu-id="737a6-121">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="737a6-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="737a6-122">執行 New-CsNetworkSite Cmdlet 建立網站：</span><span class="sxs-lookup"><span data-stu-id="737a6-122">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    <span data-ttu-id="737a6-123">例如：</span><span class="sxs-lookup"><span data-stu-id="737a6-123">For example:</span></span>
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    <span data-ttu-id="737a6-124">此範例會建立一個稱為「芝加哥」的網站，位於「北美地區」網路地區中。</span><span class="sxs-lookup"><span data-stu-id="737a6-124">In this example, you created a network site called “Chicago” that is in the “NorthAmerica” network region.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="737a6-125">「北美地區」網路地區必須已經存在，此命令才能成功執行。</span><span class="sxs-lookup"><span data-stu-id="737a6-125">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

    
    </div>

3.  <span data-ttu-id="737a6-126">使用其他網站的設定重複執行步驟 2，完成建立拓撲的網站。</span><span class="sxs-lookup"><span data-stu-id="737a6-126">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="737a6-127">使用 Lync Server 控制台建立網站</span><span class="sxs-lookup"><span data-stu-id="737a6-127">To create a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="737a6-128">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="737a6-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="737a6-129">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="737a6-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="737a6-130">在左導覽列中，按一下 **[網路組態]**。</span><span class="sxs-lookup"><span data-stu-id="737a6-130">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="737a6-131">按一下 **[站台]** 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="737a6-131">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="737a6-132">按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="737a6-132">Click **New**.</span></span>

5.  <span data-ttu-id="737a6-133">在 **[新增站台]** 頁面上，按一下 **[名稱]**，然後為網站輸入名稱。</span><span class="sxs-lookup"><span data-stu-id="737a6-133">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6.  <span data-ttu-id="737a6-134">按一下 **[地區]**，然後按一下清單中的地區。</span><span class="sxs-lookup"><span data-stu-id="737a6-134">Click **Region**, and then click a region in the list.</span></span>

7.  <span data-ttu-id="737a6-135">(選用) 按一下 **[頻寬原則]**，然後按一下清單中的頻寬原則。</span><span class="sxs-lookup"><span data-stu-id="737a6-135">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="737a6-136">如果您要在網站部署通話許可控制，才需要頻寬原則。</span><span class="sxs-lookup"><span data-stu-id="737a6-136">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

    
    </div>

8.  <span data-ttu-id="737a6-137">(選用) 按一下 **[位置原則]**，然後按一下清單中的位置原則。</span><span class="sxs-lookup"><span data-stu-id="737a6-137">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="737a6-138">如果您要在網站部署 E9-1-1，才需要位置原則。</span><span class="sxs-lookup"><span data-stu-id="737a6-138">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

    
    </div>

9.  <span data-ttu-id="737a6-139">(選用) 按一下 **[描述]**，然後輸入用來描述此網站的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="737a6-139">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="737a6-140">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="737a6-140">Click **Commit**.</span></span>

11. <span data-ttu-id="737a6-141">使用其他網站的設定重複執行步驟 4 至 10，完成建立拓撲的網站。</span><span class="sxs-lookup"><span data-stu-id="737a6-141">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-site"></a><span data-ttu-id="737a6-142">修改網站</span><span class="sxs-lookup"><span data-stu-id="737a6-142">Modify a Network Site</span></span>

<span data-ttu-id="737a6-143">修改網路地區，以便提供給通話許可控制、E9-1-1 或媒體旁路使用。</span><span class="sxs-lookup"><span data-stu-id="737a6-143">Modify a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="737a6-144">修改網站</span><span class="sxs-lookup"><span data-stu-id="737a6-144">To modify a network site</span></span>

1.  <span data-ttu-id="737a6-145">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="737a6-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="737a6-146">執行 Set-CsNetworkSite Cmdlet 以修改網站：</span><span class="sxs-lookup"><span data-stu-id="737a6-146">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>
    
        Set-CsNetworkSite -Identity <string>
    
    <span data-ttu-id="737a6-147">例如：</span><span class="sxs-lookup"><span data-stu-id="737a6-147">For example:</span></span>
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    <span data-ttu-id="737a6-p104">此範例會將稱為「阿布奎基」的網站移至「北美地區」網路地區。若要修改網站設定以便部署通話許可控制、E9-1-1 或媒體旁路，請執行 Set-CsNetworkSite Cmdlet 並分別搭配 BWPolicyProfileID 或 LocationPolicy 參數，修改網站設定。</span><span class="sxs-lookup"><span data-stu-id="737a6-p104">In this example, the site called “Albuquerque” is moved to the “NorthAmerica” network region. To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="737a6-p105">媒體旁路還有一個 BypassID 參數，但強烈建議您不要覆寫自動產生的旁路 ID。為媒體旁路設定網站時，不需要指定其他參數。</span><span class="sxs-lookup"><span data-stu-id="737a6-p105">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs. You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

    
    </div>

3.  <span data-ttu-id="737a6-152">使用其他網站的設定重複執行步驟 2，完成修改拓撲的網站。</span><span class="sxs-lookup"><span data-stu-id="737a6-152">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="737a6-153">使用 Lync Server 控制台修改網站</span><span class="sxs-lookup"><span data-stu-id="737a6-153">To modify a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="737a6-154">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="737a6-154">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="737a6-155">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="737a6-155">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="737a6-156">在左導覽列中，按一下 **[網路組態]**。</span><span class="sxs-lookup"><span data-stu-id="737a6-156">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="737a6-157">按一下 **[站台]** 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="737a6-157">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="737a6-158">在表格中，按一下您要修改的網站。</span><span class="sxs-lookup"><span data-stu-id="737a6-158">In the table, click the network site that you want to modify.</span></span>

5.  <span data-ttu-id="737a6-159">按一下 **[編輯]**，然後按一下 **[顯示詳細資料...]**。</span><span class="sxs-lookup"><span data-stu-id="737a6-159">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="737a6-160">在 **[編輯站台]** 頁面中，視需要變更此網站的設定值。</span><span class="sxs-lookup"><span data-stu-id="737a6-160">On the **Edit Site** page, change the values for this network site’s settings as appropriate.</span></span>

7.  <span data-ttu-id="737a6-161">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="737a6-161">Click **Commit**.</span></span>

8.  <span data-ttu-id="737a6-162">使用其他網站的設定重複執行步驟 4 至 7，完成修改網站。</span><span class="sxs-lookup"><span data-stu-id="737a6-162">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

