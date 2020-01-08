---
title: Lync Server 2013：建立或修改網路區域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21a9b7a8adbb4ca4c0853aa7013662433701201d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a><span data-ttu-id="81326-102">在 Lync Server 2013 中建立或修改網路區域</span><span class="sxs-lookup"><span data-stu-id="81326-102">Create or modify a network region in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81326-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="81326-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="81326-104">*網路區域*是網路中樞或 backbones，用於設定通話許可控制、E9-1 及媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="81326-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="81326-105">使用下列程式來建立或修改網路區域。</span><span class="sxs-lookup"><span data-stu-id="81326-105">Use the following procedures to create or modify network regions.</span></span> <span data-ttu-id="81326-106">例如，如果您已為單一語音功能建立網路區域，就不需要建立新的網路區域;其他高級企業語音功能將會使用相同的網路區域。</span><span class="sxs-lookup"><span data-stu-id="81326-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="81326-107">不過，您可能需要修改現有的網路區域定義，才能套用特定功能的設定。</span><span class="sxs-lookup"><span data-stu-id="81326-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="81326-108">例如，如果您已建立 E9 的網路區域（不需要關聯的中央網站），而您想要部署 [呼叫許可控制]，您必須修改網路區域定義，以指定中央網站。</span><span class="sxs-lookup"><span data-stu-id="81326-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="81326-109">如需詳細資訊，請參閱[在 Lync Server 2013 中設定 CAC 的網路區域](lync-server-2013-configure-network-regions-for-cac.md)。</span><span class="sxs-lookup"><span data-stu-id="81326-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81326-110">此功能的部署主題中記錄了網路區域定義的任何特定功能需求。</span><span class="sxs-lookup"><span data-stu-id="81326-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<span data-ttu-id="81326-111">如需有關使用網路區域的詳細資訊，請參閱 Lync Server 管理命令介面檔，瞭解下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="81326-111">For details about working with network regions, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="81326-112">新-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="81326-112">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [<span data-ttu-id="81326-113">CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="81326-113">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="81326-114">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="81326-114">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [<span data-ttu-id="81326-115">移除-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="81326-115">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a><span data-ttu-id="81326-116">建立網路區域</span><span class="sxs-lookup"><span data-stu-id="81326-116">Create a Network Region</span></span>

<span data-ttu-id="81326-117">建立可供通話許可控制、E9-1 或媒體旁路使用的網路區域。</span><span class="sxs-lookup"><span data-stu-id="81326-117">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="81326-118">使用 Lync Server 管理命令介面建立網路區域</span><span class="sxs-lookup"><span data-stu-id="81326-118">To create a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="81326-119">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="81326-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="81326-120">執行新的 CsNetworkRegion Cmdlet 來建立網路區域：</span><span class="sxs-lookup"><span data-stu-id="81326-120">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="81326-121">例如：</span><span class="sxs-lookup"><span data-stu-id="81326-121">For example:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    <span data-ttu-id="81326-122">在這個範例中，您建立了一個名為「北美洲」的網路區域，該區域與含「網站 ID 芝加哥」的中央網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="81326-122">In this example, you created a network region called “NorthAmerica” that is associated with a central site with site ID CHICAGO.</span></span>

3.  <span data-ttu-id="81326-123">若要為您的拓撲建立網路區域，請對每個網路區域重複步驟2的設定。</span><span class="sxs-lookup"><span data-stu-id="81326-123">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="81326-124">使用 Lync Server [控制台] 建立網路區域</span><span class="sxs-lookup"><span data-stu-id="81326-124">To create a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="81326-125">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="81326-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="81326-126">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="81326-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="81326-127">在左側導覽列中，按一下 [**網路**設定]。</span><span class="sxs-lookup"><span data-stu-id="81326-127">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="81326-128">按一下 [**地區**]。</span><span class="sxs-lookup"><span data-stu-id="81326-128">Click **Region**.</span></span>

4.  <span data-ttu-id="81326-129">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="81326-129">Click **New**.</span></span>

5.  <span data-ttu-id="81326-130">在 [**新區域**] 頁面上，按一下 [**名稱**]，然後輸入網路區域的名稱。</span><span class="sxs-lookup"><span data-stu-id="81326-130">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6.  <span data-ttu-id="81326-131">按一下 [**中央網站**]，然後按一下清單中的中央網站。</span><span class="sxs-lookup"><span data-stu-id="81326-131">Click **Central site**, and then click a central site in the list.</span></span>

7.  <span data-ttu-id="81326-132">或者，按一下 [**描述**]，然後輸入說明此網路網站的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="81326-132">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8.  <span data-ttu-id="81326-133">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="81326-133">Click **Commit**.</span></span>

9.  <span data-ttu-id="81326-134">若要為您的拓撲建立網路區域，請重複步驟4至8及其他地區的設定。</span><span class="sxs-lookup"><span data-stu-id="81326-134">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-region"></a><span data-ttu-id="81326-135">修改網路區域</span><span class="sxs-lookup"><span data-stu-id="81326-135">Modify a Network Region</span></span>

<span data-ttu-id="81326-136">修改現有網路區域的設定，以適應基本區域資訊的變更，或新功能所需的變更。</span><span class="sxs-lookup"><span data-stu-id="81326-136">Modify settings for an existing network region to accommodate changes to the basic region information or changes required by a new feature.</span></span>

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="81326-137">使用 Lync Server 管理命令介面修改網路區域</span><span class="sxs-lookup"><span data-stu-id="81326-137">To modify a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="81326-138">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="81326-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="81326-139">執行 CsNetworkRegion Cmdlet 來修改現有的網路區域：</span><span class="sxs-lookup"><span data-stu-id="81326-139">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="81326-140">例如：</span><span class="sxs-lookup"><span data-stu-id="81326-140">For example:</span></span>
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    <span data-ttu-id="81326-141">在這個範例中，您修改了「北美」（使用本主題先前的程式建立）的現有網路區域，方法是變更說明。</span><span class="sxs-lookup"><span data-stu-id="81326-141">In this example, you modified an existing network region called “NorthAmerica” (created using the procedures earlier in this topic) by changing the description.</span></span> <span data-ttu-id="81326-142">如果「北美」區域的描述存在，這個命令會以這個值覆寫;如果沒有設定描述，則這個命令會將其設定。</span><span class="sxs-lookup"><span data-stu-id="81326-142">If a description existed for the “NorthAmerica” region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3.  <span data-ttu-id="81326-143">若要修改其他網路區域，請對其他地區的設定重複步驟2。</span><span class="sxs-lookup"><span data-stu-id="81326-143">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="81326-144">使用 Lync Server [控制台] 修改網路區域</span><span class="sxs-lookup"><span data-stu-id="81326-144">To modify a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="81326-145">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="81326-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="81326-146">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="81326-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="81326-147">在左側導覽列中，按一下 [**網路**設定]。</span><span class="sxs-lookup"><span data-stu-id="81326-147">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="81326-148">按一下 [**地區**] 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="81326-148">Click the **Region** navigation button.</span></span>

4.  <span data-ttu-id="81326-149">在表格中，按一下您要修改的網路區域。</span><span class="sxs-lookup"><span data-stu-id="81326-149">In the table, click the network region that you want to modify.</span></span>

5.  <span data-ttu-id="81326-150">按一下 [**編輯**]，然後按一下 [**顯示詳細資料 ...**]。</span><span class="sxs-lookup"><span data-stu-id="81326-150">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="81326-151">在 [**編輯區域**] 頁面上，視需要變更這個網路區域設定的值。</span><span class="sxs-lookup"><span data-stu-id="81326-151">On the **Edit Region** page, change the values for this network region’s settings as appropriate.</span></span>

7.  <span data-ttu-id="81326-152">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="81326-152">Click **Commit**.</span></span>

8.  <span data-ttu-id="81326-153">若要完成修改網路區域，請重複步驟4至7及其他地區的設定。</span><span class="sxs-lookup"><span data-stu-id="81326-153">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

