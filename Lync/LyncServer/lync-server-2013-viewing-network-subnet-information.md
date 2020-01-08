---
title: Lync Server 2013：查看網路子網資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network subnet information
ms:assetid: 46f165f2-efe3-4cc1-9fee-a78b7f2ed41e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688044(v=OCS.15)
ms:contentKeyID: 49733636
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a157746e40de8f4793fab24e7e91121779d7602e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-subnet-information-in-lync-server-2013"></a><span data-ttu-id="d45cf-102">在 Lync Server 2013 中查看網路子網資訊</span><span class="sxs-lookup"><span data-stu-id="d45cf-102">Viewing network subnet information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d45cf-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d45cf-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d45cf-104">您可以使用下列程式來查看網路子網。</span><span class="sxs-lookup"><span data-stu-id="d45cf-104">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="d45cf-105">您可以從 Lync Server [控制台] 建立、修改或刪除網路子網。</span><span class="sxs-lookup"><span data-stu-id="d45cf-105">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="d45cf-106">如需建立或修改網路子網的詳細資料，請參閱[在 Lync Server 2013 中建立或修改網路子網](lync-server-2013-create-or-modify-network-subnets.md)。</span><span class="sxs-lookup"><span data-stu-id="d45cf-106">For details about creating or modifying network subnets, see [Create or modify network subnets in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span></span>

<div>

## <a name="to-view-a-network-subnet"></a><span data-ttu-id="d45cf-107">若要查看網路子網</span><span class="sxs-lookup"><span data-stu-id="d45cf-107">To view a network subnet</span></span>

1.  <span data-ttu-id="d45cf-108">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d45cf-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d45cf-109">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="d45cf-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d45cf-110">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d45cf-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d45cf-111">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**子網**]。</span><span class="sxs-lookup"><span data-stu-id="d45cf-111">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="d45cf-112">在 [**子網**] 頁面上，按一下您要查看的子網。</span><span class="sxs-lookup"><span data-stu-id="d45cf-112">On the **Subnet** page, click the subnet that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d45cf-113">您一次只能查看一個子網。</span><span class="sxs-lookup"><span data-stu-id="d45cf-113">You can only view one subnet at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="d45cf-114">按一下 [**編輯**] 功能表上的 [**顯示詳細資料 ...**]。</span><span class="sxs-lookup"><span data-stu-id="d45cf-114">On the **Edit** menu, click **Show details…**.</span></span>

</div>

<div>

## <a name="viewing-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d45cf-115">使用 Windows PowerShell Cmdlet 來查看網路子網配置資訊</span><span class="sxs-lookup"><span data-stu-id="d45cf-115">Viewing Network Subnet Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d45cf-116">網路子網資訊可以使用 Windows PowerShell 和 CsNetworkSubnet Cmdlet 來查看。</span><span class="sxs-lookup"><span data-stu-id="d45cf-116">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="d45cf-117">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="d45cf-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d45cf-118">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="d45cf-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-subnet-information"></a><span data-ttu-id="d45cf-119">若要查看網路子網資訊</span><span class="sxs-lookup"><span data-stu-id="d45cf-119">To view network subnet information</span></span>

  - <span data-ttu-id="d45cf-120">若要查看所有網路子網的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="d45cf-120">To view information about all your network subnets, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="d45cf-121">這會傳回如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="d45cf-121">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0

</div>

<span data-ttu-id="d45cf-122">如需詳細資訊，請參閱[CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="d45cf-122">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d45cf-123">請參閱</span><span class="sxs-lookup"><span data-stu-id="d45cf-123">See Also</span></span>


[<span data-ttu-id="d45cf-124">在 Lync Server 2013 中建立或修改網路子網</span><span class="sxs-lookup"><span data-stu-id="d45cf-124">Create or modify network subnets in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-network-subnets.md)  
[<span data-ttu-id="d45cf-125">刪除 Lync Server 2013 中的網路子網</span><span class="sxs-lookup"><span data-stu-id="d45cf-125">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

