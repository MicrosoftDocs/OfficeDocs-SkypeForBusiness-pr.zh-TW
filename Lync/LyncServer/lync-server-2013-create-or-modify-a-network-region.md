---
title: Lync Server 2013：建立或修改網路地區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 417fece34f8e5177760e470083cd929cbddaab60
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a><span data-ttu-id="ea749-102">在 Lync Server 2013 中建立或修改網路地區</span><span class="sxs-lookup"><span data-stu-id="ea749-102">Create or modify a network region in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea749-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="ea749-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="ea749-104">「網路區域」\*\* 是用於通話許可控制、E9-1-1 及媒體旁路設定的網路中樞或骨幹。</span><span class="sxs-lookup"><span data-stu-id="ea749-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="ea749-105">請使用下列程式來建立或修改網路地區。</span><span class="sxs-lookup"><span data-stu-id="ea749-105">Use the following procedures to create or modify network regions.</span></span> <span data-ttu-id="ea749-106">例如，您已為一個語音功能建立網路區域，便不需要建立新的網路區域；其他的進階 Enterprise Voice 功能會使用那些相同的網路區域。</span><span class="sxs-lookup"><span data-stu-id="ea749-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="ea749-107">不過，您必須修改現有的網路區域定義，以套用功能特定的設定。</span><span class="sxs-lookup"><span data-stu-id="ea749-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="ea749-108">例如，您已為 E9-1-1 (其不需要相關的中央網站) 建立網路區域，而您接著要部署通話許可控制，您便必須修改網路區域定義來指定中央網站。</span><span class="sxs-lookup"><span data-stu-id="ea749-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="ea749-109">如需詳細資訊，請參閱[在 Lync Server 2013 中設定 CAC 的網路地區](lync-server-2013-configure-network-regions-for-cac.md)。</span><span class="sxs-lookup"><span data-stu-id="ea749-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ea749-110">網路地區定義的任何功能特定需求都記載在功能的部署主題中。</span><span class="sxs-lookup"><span data-stu-id="ea749-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<span data-ttu-id="ea749-111">如需使用網路地區的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ea749-111">For details about working with network regions, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="ea749-112">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="ea749-112">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [<span data-ttu-id="ea749-113">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="ea749-113">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="ea749-114">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="ea749-114">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [<span data-ttu-id="ea749-115">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="ea749-115">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a><span data-ttu-id="ea749-116">建立網路地區</span><span class="sxs-lookup"><span data-stu-id="ea749-116">Create a Network Region</span></span>

<span data-ttu-id="ea749-117">建立網路地區，以便提供給通話許可控制、E9-1-1 或媒體旁路使用。</span><span class="sxs-lookup"><span data-stu-id="ea749-117">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="ea749-118">使用 Lync Server 管理命令介面建立網路地區</span><span class="sxs-lookup"><span data-stu-id="ea749-118">To create a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="ea749-119">啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="ea749-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ea749-120">執行 New-CsNetworkRegion Cmdlet 來建立網路地區：</span><span class="sxs-lookup"><span data-stu-id="ea749-120">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="ea749-121">例如：</span><span class="sxs-lookup"><span data-stu-id="ea749-121">For example:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    <span data-ttu-id="ea749-122">在此範例中，您會建立一個名為「NorthAmerica」的網路地區，該網路地區與網站識別碼芝加哥相關聯的中央網站。</span><span class="sxs-lookup"><span data-stu-id="ea749-122">In this example, you created a network region called “NorthAmerica” that is associated with a central site with site ID CHICAGO.</span></span>

3.  <span data-ttu-id="ea749-123">若要完成建立拓撲的網路地區，請使用每個網路地區的設定重複步驟2。</span><span class="sxs-lookup"><span data-stu-id="ea749-123">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="ea749-124">使用 Lync Server 控制台建立網路地區</span><span class="sxs-lookup"><span data-stu-id="ea749-124">To create a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="ea749-125">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="ea749-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ea749-126">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="ea749-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="ea749-127">在左導覽列中，按一下 **[網路組態]**。</span><span class="sxs-lookup"><span data-stu-id="ea749-127">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="ea749-128">按一下 [**地區**]。</span><span class="sxs-lookup"><span data-stu-id="ea749-128">Click **Region**.</span></span>

4.  <span data-ttu-id="ea749-129">按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="ea749-129">Click **New**.</span></span>

5.  <span data-ttu-id="ea749-130">在 [**新地區**] 頁面上，按一下 [**名稱**]，然後輸入網路地區的名稱。</span><span class="sxs-lookup"><span data-stu-id="ea749-130">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6.  <span data-ttu-id="ea749-131">按一下 [**中央網站**]，然後按一下清單中的中央網站。</span><span class="sxs-lookup"><span data-stu-id="ea749-131">Click **Central site**, and then click a central site in the list.</span></span>

7.  <span data-ttu-id="ea749-132">(選用) 按一下 **[描述]**，然後輸入用來描述此網站的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="ea749-132">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8.  <span data-ttu-id="ea749-133">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="ea749-133">Click **Commit**.</span></span>

9.  <span data-ttu-id="ea749-134">若要完成建立拓撲的網路地區，請使用其他地區的設定重複步驟4到8。</span><span class="sxs-lookup"><span data-stu-id="ea749-134">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-region"></a><span data-ttu-id="ea749-135">修改網路地區</span><span class="sxs-lookup"><span data-stu-id="ea749-135">Modify a Network Region</span></span>

<span data-ttu-id="ea749-136">修改現有網路地區的設定，以容納基本區域資訊的變更或新功能所需的變更。</span><span class="sxs-lookup"><span data-stu-id="ea749-136">Modify settings for an existing network region to accommodate changes to the basic region information or changes required by a new feature.</span></span>

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="ea749-137">使用 Lync Server 管理命令介面來修改網路地區</span><span class="sxs-lookup"><span data-stu-id="ea749-137">To modify a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="ea749-138">啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="ea749-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ea749-139">執行 Set-CsNetworkRegion Cmdlet 以修改現有的網路地區：</span><span class="sxs-lookup"><span data-stu-id="ea749-139">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="ea749-140">例如：</span><span class="sxs-lookup"><span data-stu-id="ea749-140">For example:</span></span>
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    <span data-ttu-id="ea749-141">在此範例中，您會使用本) 主題稍早的程式（透過變更描述）來建立名為「NorthAmerica」 (的現有網路地區。</span><span class="sxs-lookup"><span data-stu-id="ea749-141">In this example, you modified an existing network region called “NorthAmerica” (created using the procedures earlier in this topic) by changing the description.</span></span> <span data-ttu-id="ea749-142">如果「NorthAmerica」區域的描述存在，此命令會以此值覆寫該描述。如果未設定任何描述，則此命令會將其設定。</span><span class="sxs-lookup"><span data-stu-id="ea749-142">If a description existed for the “NorthAmerica” region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3.  <span data-ttu-id="ea749-143">若要修改其他網路地區，請使用其他地區的設定重複步驟2。</span><span class="sxs-lookup"><span data-stu-id="ea749-143">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="ea749-144">使用 Lync Server 控制台修改網路地區</span><span class="sxs-lookup"><span data-stu-id="ea749-144">To modify a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="ea749-145">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="ea749-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ea749-146">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="ea749-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="ea749-147">在左導覽列中，按一下 **[網路組態]**。</span><span class="sxs-lookup"><span data-stu-id="ea749-147">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="ea749-148">按一下 [**地區**] 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="ea749-148">Click the **Region** navigation button.</span></span>

4.  <span data-ttu-id="ea749-149">在表格中，按一下您要修改的網路地區。</span><span class="sxs-lookup"><span data-stu-id="ea749-149">In the table, click the network region that you want to modify.</span></span>

5.  <span data-ttu-id="ea749-150">按一下 **[編輯]**，然後按一下 **[顯示詳細資料...]**。</span><span class="sxs-lookup"><span data-stu-id="ea749-150">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="ea749-151">在 [**編輯地區**] 頁面上，視需要變更此網路地區的設定值。</span><span class="sxs-lookup"><span data-stu-id="ea749-151">On the **Edit Region** page, change the values for this network region’s settings as appropriate.</span></span>

7.  <span data-ttu-id="ea749-152">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="ea749-152">Click **Commit**.</span></span>

8.  <span data-ttu-id="ea749-153">若要完成修改網路地區，請使用其他地區的設定重複步驟4到7。</span><span class="sxs-lookup"><span data-stu-id="ea749-153">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

