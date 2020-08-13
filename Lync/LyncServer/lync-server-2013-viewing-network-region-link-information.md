---
title: Lync Server 2013：查看網路地區連結資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region link information
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49733701
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: baad9310dc63fb482838e3a003dce8ddbc36c200
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-link-information-in-lync-server-2013"></a><span data-ttu-id="55f8b-102">在 Lync Server 2013 中查看網路地區連結資訊</span><span class="sxs-lookup"><span data-stu-id="55f8b-102">Viewing network region link information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55f8b-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="55f8b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="55f8b-104">您可以透過通話許可控制 (CAC) 檢視兩個網路地區之間的連結。</span><span class="sxs-lookup"><span data-stu-id="55f8b-104">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="55f8b-105">網路中的地區是透過實體廣域網路 (WAN) 連線相連結。</span><span class="sxs-lookup"><span data-stu-id="55f8b-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="55f8b-106">您可以使用 Lync Server 控制台來查看兩個網路地區之間的現有連結。</span><span class="sxs-lookup"><span data-stu-id="55f8b-106">You can use the Lync Server Control Panel to view an existing link between two network regions.</span></span> <span data-ttu-id="55f8b-107">如需建立或修改網路地區連結的詳細資訊，請參閱[在 Lync Server 2013 中設定網路地區連結](lync-server-2013-configuring-network-region-links.md)。</span><span class="sxs-lookup"><span data-stu-id="55f8b-107">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span></span>

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a><span data-ttu-id="55f8b-108">在 Lync Server 控制台中查看網路地區連結</span><span class="sxs-lookup"><span data-stu-id="55f8b-108">To view a network region link in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="55f8b-109">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="55f8b-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="55f8b-110">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="55f8b-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="55f8b-111">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="55f8b-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="55f8b-112">按一下左導覽列中的 [網路設定]\*\*\*\*，然後按一下 [地區連結]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="55f8b-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="55f8b-113">在 [區域連結]\*\*\*\* 頁面中，按一下要檢視的區域連結。</span><span class="sxs-lookup"><span data-stu-id="55f8b-113">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="55f8b-114">一次只能檢視一個區域的資訊。</span><span class="sxs-lookup"><span data-stu-id="55f8b-114">You can only view information about one region link at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="55f8b-115">從 [編輯]\*\*\*\* 功能表中，選取 [顯示詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="55f8b-115">From the **Edit** menu, select **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="55f8b-116">使用 Windows PowerShell Cmdlet 來查看網路地區連結資訊</span><span class="sxs-lookup"><span data-stu-id="55f8b-116">Viewing Network Region Link Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="55f8b-117">您可以使用 Windows PowerShell 和**Get-CsNetworkRegionLink** Cmdlet 來查看網路地區連結。</span><span class="sxs-lookup"><span data-stu-id="55f8b-117">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="55f8b-118">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="55f8b-118">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="55f8b-119">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="55f8b-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-link-information"></a><span data-ttu-id="55f8b-120">檢視網路地區連結資訊</span><span class="sxs-lookup"><span data-stu-id="55f8b-120">To view network region link information</span></span>

  - <span data-ttu-id="55f8b-121">若要查看所有網路地區連結的資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="55f8b-121">To view information about all your network region links, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="55f8b-122">此命令會傳回與下列相似的資訊：</span><span class="sxs-lookup"><span data-stu-id="55f8b-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

<span data-ttu-id="55f8b-123">如需詳細資訊，請參閱 [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)。</span><span class="sxs-lookup"><span data-stu-id="55f8b-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="55f8b-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="55f8b-124">See Also</span></span>


[<span data-ttu-id="55f8b-125">在 Lync Server 2013 中設定網路站台連結</span><span class="sxs-lookup"><span data-stu-id="55f8b-125">Configuring network site links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

