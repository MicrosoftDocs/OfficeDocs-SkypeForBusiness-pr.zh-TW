---
title: Lync Server 2013：建立或修改網站
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
ms.openlocfilehash: ed721a48b12a497b25d58e7ebb65ff3a91980904
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a><span data-ttu-id="b7095-102">在 Lync Server 2013 中建立或修改網站</span><span class="sxs-lookup"><span data-stu-id="b7095-102">Create or modify a network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7095-103">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="b7095-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="b7095-104">通話許可控制（CAC）、E9-1-1 和媒體旁路部署，都依賴于定義的*網路網站*設定，且與網路區域之間永遠關聯。</span><span class="sxs-lookup"><span data-stu-id="b7095-104">Call admission control (CAC), E9-1-1, and media bypass deployments rely on the configuration of *network sites* which are defined within and always associated with a network region.</span></span> <span data-ttu-id="b7095-105">網路網站代表分支辦公室位置、一組建築物或校園。</span><span class="sxs-lookup"><span data-stu-id="b7095-105">A network site represents a branch office location, a set of buildings, or a campus.</span></span> <span data-ttu-id="b7095-106">網路網站代表具有相似頻寬的子網集合。</span><span class="sxs-lookup"><span data-stu-id="b7095-106">Network sites represent collections of subnets with similar bandwidth.</span></span>

<span data-ttu-id="b7095-107">使用下列程式來建立或修改網路網站。</span><span class="sxs-lookup"><span data-stu-id="b7095-107">Use the following procedures to create or modify network sites.</span></span> <span data-ttu-id="b7095-108">例如，如果您已建立單一語音功能的網路網站，就不需要建立新的網路網站;其他語音功能將會使用相同的網站。</span><span class="sxs-lookup"><span data-stu-id="b7095-108">For example, if you have already created network sites for one Voice feature, you do not need to create new network sites; other Voice features will use those same sites.</span></span> <span data-ttu-id="b7095-109">不過，您可能需要修改現有的網路網站定義，才能套用特定功能的設定。</span><span class="sxs-lookup"><span data-stu-id="b7095-109">You may, however, need to modify an existing network site definition to apply feature-specific settings.</span></span> <span data-ttu-id="b7095-110">例如，如果您已建立 E9 的網路網站-1-1，您需要在部署通話許可控制期間修改網路網站，以套用頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="b7095-110">For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b7095-111">在其中，您可以找到網路網站的特定範例與需求，因為它們與每個功能之部署檔中的 [高級語音] 功能相關：</span><span class="sxs-lookup"><span data-stu-id="b7095-111">Where they exist, you can find specific examples and requirements for network sites as they pertain to an advanced Voice feature in the Deployment documentation for each feature:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="b7095-112"><A href="lync-server-2013-configure-network-sites-for-cac.md">在 Lync Server 2013 中設定 CAC 的網路網站</A></span><span class="sxs-lookup"><span data-stu-id="b7095-112"><A href="lync-server-2013-configure-network-sites-for-cac.md">Configure network sites for CAC in Lync Server 2013</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="b7095-113">如需使用網路網站的詳細資訊，請參閱適用于下列 Cmdlet 的 Lync Server 管理命令介面檔：</span><span class="sxs-lookup"><span data-stu-id="b7095-113">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="b7095-114">新-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="b7095-114">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [<span data-ttu-id="b7095-115">CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="b7095-115">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [<span data-ttu-id="b7095-116">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="b7095-116">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [<span data-ttu-id="b7095-117">移除-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="b7095-117">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a><span data-ttu-id="b7095-118">建立網路網站</span><span class="sxs-lookup"><span data-stu-id="b7095-118">Create a Network Site</span></span>

<span data-ttu-id="b7095-119">建立可供通話許可控制、E9-1 或媒體旁路使用的網路區域。</span><span class="sxs-lookup"><span data-stu-id="b7095-119">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a><span data-ttu-id="b7095-120">使用管理命令介面建立網路網站</span><span class="sxs-lookup"><span data-stu-id="b7095-120">To create a network site by using Management Shell</span></span>

1.  <span data-ttu-id="b7095-121">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="b7095-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b7095-122">執行新的 CsNetworkSite Cmdlet 來建立網路網站：</span><span class="sxs-lookup"><span data-stu-id="b7095-122">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    <span data-ttu-id="b7095-123">例如：</span><span class="sxs-lookup"><span data-stu-id="b7095-123">For example:</span></span>
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    <span data-ttu-id="b7095-124">在這個範例中，您已建立名為「芝加哥」的網路網站，該網路網站是「北美」網路區域。</span><span class="sxs-lookup"><span data-stu-id="b7095-124">In this example, you created a network site called “Chicago” that is in the “NorthAmerica” network region.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b7095-125">[北美] 網路區域必須已經存在，此命令才能順利執行。</span><span class="sxs-lookup"><span data-stu-id="b7095-125">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

    
    </div>

3.  <span data-ttu-id="b7095-126">若要為拓撲建立網路網站，請對 [其他網站] 的設定重複步驟2。</span><span class="sxs-lookup"><span data-stu-id="b7095-126">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="b7095-127">使用 Lync Server [控制台] 建立網路網站</span><span class="sxs-lookup"><span data-stu-id="b7095-127">To create a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b7095-128">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="b7095-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b7095-129">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="b7095-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="b7095-130">在左側導覽列中，按一下 [**網路**設定]。</span><span class="sxs-lookup"><span data-stu-id="b7095-130">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="b7095-131">按一下 [**網站導航**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="b7095-131">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="b7095-132">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="b7095-132">Click **New**.</span></span>

5.  <span data-ttu-id="b7095-133">在 [**新網站**] 頁面上，按一下 [**名稱**]，然後輸入網路網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="b7095-133">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6.  <span data-ttu-id="b7095-134">按一下 [**地區**]，然後按一下清單中的區域。</span><span class="sxs-lookup"><span data-stu-id="b7095-134">Click **Region**, and then click a region in the list.</span></span>

7.  <span data-ttu-id="b7095-135">或者，按一下 [**頻寬原則**]，然後按一下清單中的頻寬原則。</span><span class="sxs-lookup"><span data-stu-id="b7095-135">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b7095-136">只有當您在網站上部署 [通話許可控制] 時，才需要頻寬原則。</span><span class="sxs-lookup"><span data-stu-id="b7095-136">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

    
    </div>

8.  <span data-ttu-id="b7095-137">或者，按一下 [**位置原則**]，然後按一下清單中的位置原則。</span><span class="sxs-lookup"><span data-stu-id="b7095-137">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b7095-138">只有當您在網站上部署 E9-1-1 時，才需要位置原則。</span><span class="sxs-lookup"><span data-stu-id="b7095-138">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

    
    </div>

9.  <span data-ttu-id="b7095-139">或者，按一下 [**描述**]，然後輸入說明此網路網站的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="b7095-139">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="b7095-140">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b7095-140">Click **Commit**.</span></span>

11. <span data-ttu-id="b7095-141">若要為您的拓撲建立網路網站，請重複步驟4至10，並使用 [其他網站] 的設定。</span><span class="sxs-lookup"><span data-stu-id="b7095-141">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-site"></a><span data-ttu-id="b7095-142">修改網路網站</span><span class="sxs-lookup"><span data-stu-id="b7095-142">Modify a Network Site</span></span>

<span data-ttu-id="b7095-143">修改可供通話許可控制、E9-1 或媒體旁路使用的網路區域。</span><span class="sxs-lookup"><span data-stu-id="b7095-143">Modify a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="b7095-144">修改網路網站</span><span class="sxs-lookup"><span data-stu-id="b7095-144">To modify a network site</span></span>

1.  <span data-ttu-id="b7095-145">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="b7095-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b7095-146">執行 CsNetworkSite Cmdlet 來修改網路網站：</span><span class="sxs-lookup"><span data-stu-id="b7095-146">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>
    
        Set-CsNetworkSite -Identity <string>
    
    <span data-ttu-id="b7095-147">例如：</span><span class="sxs-lookup"><span data-stu-id="b7095-147">For example:</span></span>
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    <span data-ttu-id="b7095-148">在這個範例中，名為 "Albuquerque" 的網站會移至 [北美] 網路區域。</span><span class="sxs-lookup"><span data-stu-id="b7095-148">In this example, the site called “Albuquerque” is moved to the “NorthAmerica” network region.</span></span> <span data-ttu-id="b7095-149">若要修改網路網站設定以部署呼叫許可控制、E9-1 或媒體旁路，請分別執行設定 CsNetworkSite Cmdlet 及 BWPolicyProfileID 或 LocationPolicy 參數，以修改網路網站設定。</span><span class="sxs-lookup"><span data-stu-id="b7095-149">To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b7095-150">雖然 BypassID 參數存在於媒體旁路，但我們強烈建議您不要覆寫自動產生的旁路 Id。</span><span class="sxs-lookup"><span data-stu-id="b7095-150">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs.</span></span> <span data-ttu-id="b7095-151">您不需要指定其他參數，即可設定媒體旁路的網路網站。</span><span class="sxs-lookup"><span data-stu-id="b7095-151">You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

    
    </div>

3.  <span data-ttu-id="b7095-152">若要完成拓撲的網路網站修改，請對 [其他網站] 的設定重複步驟2。</span><span class="sxs-lookup"><span data-stu-id="b7095-152">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="b7095-153">使用 Lync Server [控制台] 修改網路網站</span><span class="sxs-lookup"><span data-stu-id="b7095-153">To modify a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b7095-154">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="b7095-154">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b7095-155">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="b7095-155">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="b7095-156">在左側導覽列中，按一下 [**網路**設定]。</span><span class="sxs-lookup"><span data-stu-id="b7095-156">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="b7095-157">按一下 [**網站導航**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="b7095-157">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="b7095-158">在表格中，按一下您要修改的網路網站。</span><span class="sxs-lookup"><span data-stu-id="b7095-158">In the table, click the network site that you want to modify.</span></span>

5.  <span data-ttu-id="b7095-159">按一下 [**編輯**]，然後按一下 [**顯示詳細資料 ...**]。</span><span class="sxs-lookup"><span data-stu-id="b7095-159">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="b7095-160">在 [**編輯網站**] 頁面上，視需要變更此網路網站設定的值。</span><span class="sxs-lookup"><span data-stu-id="b7095-160">On the **Edit Site** page, change the values for this network site’s settings as appropriate.</span></span>

7.  <span data-ttu-id="b7095-161">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b7095-161">Click **Commit**.</span></span>

8.  <span data-ttu-id="b7095-162">若要完成修改網路網站，請重複步驟4至7及 [其他網站] 的設定。</span><span class="sxs-lookup"><span data-stu-id="b7095-162">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

