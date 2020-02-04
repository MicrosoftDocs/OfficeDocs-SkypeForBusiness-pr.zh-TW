---
title: Lync Server 2013：查看網路區域資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region information
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49733672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db5610ddee677af989b16c150ffab96308bbb837
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-information-in-lync-server-2013"></a><span data-ttu-id="72190-102">在 Lync Server 2013 中查看網路區域資訊</span><span class="sxs-lookup"><span data-stu-id="72190-102">Viewing network region information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72190-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="72190-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="72190-104">網路區域跨多個地理區域互連網路的各個部分。</span><span class="sxs-lookup"><span data-stu-id="72190-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="72190-105">每個網路區域都必須與一個中央網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="72190-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="72190-106">中央網站是在其上執行呼叫許可控制（CAC）頻寬原則服務的資料中心網站。</span><span class="sxs-lookup"><span data-stu-id="72190-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="72190-107">您可以使用 Lync Server [控制台] 來查看網路區域。</span><span class="sxs-lookup"><span data-stu-id="72190-107">You can use Lync Server Control Panel to view network regions.</span></span> <span data-ttu-id="72190-108">網路區域包括決定是否允許透過網際網路使用替換路徑進行音訊和視頻連線的設定。</span><span class="sxs-lookup"><span data-stu-id="72190-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="72190-109">您可以使用本主題來查看現有的網路區域。</span><span class="sxs-lookup"><span data-stu-id="72190-109">Use this topic to view existing network regions.</span></span> <span data-ttu-id="72190-110">如需建立或修改現有網路區域的詳細資料，請參閱[在 Lync Server 2013 中建立或修改網路區域](lync-server-2013-creating-or-modifying-network-regions.md)。</span><span class="sxs-lookup"><span data-stu-id="72190-110">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a><span data-ttu-id="72190-111">使用 Lync Server [控制台] 查看網路區域的相關資訊</span><span class="sxs-lookup"><span data-stu-id="72190-111">To view information about a network region with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="72190-112">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="72190-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="72190-113">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="72190-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="72190-114">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="72190-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="72190-115">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區**]。</span><span class="sxs-lookup"><span data-stu-id="72190-115">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="72190-116">在 [**地區**] 頁面上，按一下您要查看的地區。</span><span class="sxs-lookup"><span data-stu-id="72190-116">On the **Region** page, click the region you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="72190-117">一次只能查看一個區域。</span><span class="sxs-lookup"><span data-stu-id="72190-117">You can only view one region at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="72190-118">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="72190-118">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="72190-119">使用 Windows PowerShell Cmdlet 來查看網路區域資訊</span><span class="sxs-lookup"><span data-stu-id="72190-119">Viewing Network Region Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="72190-120">您可以使用 Windows PowerShell 和**CsNetworkRegion** Cmdlet 來查看網路區域資訊。</span><span class="sxs-lookup"><span data-stu-id="72190-120">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="72190-121">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="72190-121">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="72190-122">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="72190-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-information"></a><span data-ttu-id="72190-123">若要查看網路區域資訊</span><span class="sxs-lookup"><span data-stu-id="72190-123">To view network region information</span></span>

  - <span data-ttu-id="72190-124">若要查看所有網路區域的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="72190-124">To view information about all your network regions, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="72190-125">這會傳回如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="72190-125">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

</div>

<span data-ttu-id="72190-126">如需詳細資訊，請參閱[CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="72190-126">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="72190-127">請參閱</span><span class="sxs-lookup"><span data-stu-id="72190-127">See Also</span></span>


[<span data-ttu-id="72190-128">在 Lync Server 2013 中建立或修改網路區域</span><span class="sxs-lookup"><span data-stu-id="72190-128">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
[<span data-ttu-id="72190-129">在 Lync Server 2013 中刪除現有的網路區域</span><span class="sxs-lookup"><span data-stu-id="72190-129">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

