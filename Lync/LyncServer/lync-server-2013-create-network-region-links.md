---
title: Lync Server 2013：建立網路區域連結
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create network region links
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48185873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c0f21f599b8afa4f9f31ec16aad82e305c8a08e
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40977229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-region-links-in-lync-server-2013"></a><span data-ttu-id="4c863-102">在 Lync Server 2013 中建立網路區域連結</span><span class="sxs-lookup"><span data-stu-id="4c863-102">Create network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c863-103">_**主題上次修改日期：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="4c863-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="4c863-104">網路中的區域是透過物理 WAN 連線來連結。</span><span class="sxs-lookup"><span data-stu-id="4c863-104">Regions within a network are linked through physical WAN connectivity.</span></span> <span data-ttu-id="4c863-105">[*網路區域] 連結*會建立兩個設定為 [呼叫許可控制] （CAC）的區域之間的連結，並設定這些區域之間音訊與視頻流量的頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="4c863-105">A *network region link* creates a link between two regions configured for call admission control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>

<span data-ttu-id="4c863-106">如需使用網路區域連結的詳細資訊，請參閱下列 Cmdlet 的 Lync Server 管理命令介面檔：</span><span class="sxs-lookup"><span data-stu-id="4c863-106">For details about working with network region links, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="4c863-107">新-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="4c863-107">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [<span data-ttu-id="4c863-108">CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="4c863-108">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="4c863-109">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="4c863-109">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [<span data-ttu-id="4c863-110">移除-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="4c863-110">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

<span data-ttu-id="4c863-111">此範例拓撲在北美與 APAC 區域之間有連結，以及 EMEA 與 APAC 區域之間的連結。</span><span class="sxs-lookup"><span data-stu-id="4c863-111">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="4c863-112">上述每一個區域連結都受 WAN 頻寬的限制，如範例中的區域連結頻寬資訊資料表所述：在規劃檔的 [Lync Server 2013] 區段中，[收集您對撥號許可控制的需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="4c863-112">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in the [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) section of the Planning documentation.</span></span>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a><span data-ttu-id="4c863-113">使用 Lync Server 管理命令介面建立網路區域連結</span><span class="sxs-lookup"><span data-stu-id="4c863-113">To create network region links by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="4c863-114">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="4c863-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="4c863-115">執行新的 CsNetworkRegionLink Cmdlet 來建立區域連結，並套用適當的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="4c863-115">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles.</span></span> <span data-ttu-id="4c863-116">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="4c863-116">For example, run:</span></span>
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a><span data-ttu-id="4c863-117">使用 Lync Server [控制台] 建立網路區域連結</span><span class="sxs-lookup"><span data-stu-id="4c863-117">To create network region links by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="4c863-118">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="4c863-118">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4c863-119">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="4c863-119">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="4c863-120">在左側導覽列中，按一下 [**網路**設定]。</span><span class="sxs-lookup"><span data-stu-id="4c863-120">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="4c863-121">按一下 [**地區] 連結**瀏覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="4c863-121">Click the **Region Link** navigation button.</span></span>

4.  <span data-ttu-id="4c863-122">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="4c863-122">Click **New**.</span></span>

5.  <span data-ttu-id="4c863-123">在 [**新增區域連結**] 頁面上，按一下 [**名稱**]，然後輸入網路區域連結的名稱。</span><span class="sxs-lookup"><span data-stu-id="4c863-123">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>

6.  <span data-ttu-id="4c863-124">按一下 [**網路\#區域 1**]，然後按一下清單中您要連結至 [網路區域\#2] 的網路區域。</span><span class="sxs-lookup"><span data-stu-id="4c863-124">Click **Network Region \#1**, and then click the network region in the list that you want to link to Network Region \#2.</span></span>

7.  <span data-ttu-id="4c863-125">按一下 [**網路\#區域 2**]，然後在清單中按一下您要連結至 [網路區域\#1] 的網路區域。</span><span class="sxs-lookup"><span data-stu-id="4c863-125">Click **Network Region \#2**, and then click a network region in the list that you want to link to Network Region \#1.</span></span>

8.  <span data-ttu-id="4c863-126">或者，按一下 [**頻寬原則**]，然後選取您要套用到 [網路區域] 連結的頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="4c863-126">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="4c863-127">只有在 [網路區域] 連結受到頻寬限制且您想要使用 CAC 來控制該連結上的媒體流量時，才能套用頻寬原則。</span><span class="sxs-lookup"><span data-stu-id="4c863-127">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span>

    
    </div>

9.  <span data-ttu-id="4c863-128">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4c863-128">Click **Commit**.</span></span>

10. <span data-ttu-id="4c863-129">若要為您的拓撲建立網路區域連結，請重複步驟4到9，以及其他地區的設定。</span><span class="sxs-lookup"><span data-stu-id="4c863-129">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
