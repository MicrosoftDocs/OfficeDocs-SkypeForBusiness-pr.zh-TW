---
title: Lync Server 2013：查看網路網站資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network site information
ms:assetid: 24a97d98-b168-4016-81bf-c2c478092b87
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687996(v=OCS.15)
ms:contentKeyID: 49733586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d3c6b0e4855cd8620205a70d6538465c32c0f0d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-site-information-in-lync-server-2013"></a><span data-ttu-id="776d4-102">在 Lync Server 2013 中查看網路網站資訊</span><span class="sxs-lookup"><span data-stu-id="776d4-102">Viewing network site information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="776d4-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="776d4-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="776d4-104">[網路網站] 是在通話許可控制（CAC）或增強型9-1-1 部署的每個區域中設定的辦公室或位置。</span><span class="sxs-lookup"><span data-stu-id="776d4-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="776d4-105">您可以在 Lync Server 2013 的 [控制台] 或 [Lync Server 管理命令介面] 中查看網路網站資訊。</span><span class="sxs-lookup"><span data-stu-id="776d4-105">You can view network site information in either Lync Server 2013 Control Panel or Lync Server Management Shell .</span></span> <span data-ttu-id="776d4-106">如需建立或修改網路網站的詳細資料，請參閱[在 Lync Server 2013 中建立或修改網路網站](lync-server-2013-creating-or-modifying-network-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="776d4-106">For details about creating or modifying network sites, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

<div>

## <a name="to-view-network-site-information-in-lync-server-control-panel"></a><span data-ttu-id="776d4-107">在 Lync Server [控制台] 中查看網路網站資訊</span><span class="sxs-lookup"><span data-stu-id="776d4-107">To view network site information in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="776d4-108">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="776d4-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="776d4-109">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="776d4-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="776d4-110">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="776d4-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="776d4-111">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**網站**]。</span><span class="sxs-lookup"><span data-stu-id="776d4-111">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="776d4-112">在 [**網站**] 頁面上，按一下您要查看的網站。</span><span class="sxs-lookup"><span data-stu-id="776d4-112">On the **Site** page, click the site that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="776d4-113">您一次只能查看一個網站的資訊。</span><span class="sxs-lookup"><span data-stu-id="776d4-113">You can only view information for one site at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="776d4-114">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="776d4-114">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="776d4-115">使用 Windows PowerShell Cmdlet 查看網路網站資訊</span><span class="sxs-lookup"><span data-stu-id="776d4-115">Viewing Network Site Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="776d4-116">您可以使用 Windows PowerShell 和 CsNetworkSite Cmdlet 來查看網路網站資訊。</span><span class="sxs-lookup"><span data-stu-id="776d4-116">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="776d4-117">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="776d4-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="776d4-118">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="776d4-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-site-information"></a><span data-ttu-id="776d4-119">若要查看網路網站資訊</span><span class="sxs-lookup"><span data-stu-id="776d4-119">To view network site information</span></span>

  - <span data-ttu-id="776d4-120">若要查看所有網路網站的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="776d4-120">To view information about all your network sites, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="776d4-121">這會傳回如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="776d4-121">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

</div>

<span data-ttu-id="776d4-122">如需詳細資訊，請參閱[CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="776d4-122">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="776d4-123">請參閱</span><span class="sxs-lookup"><span data-stu-id="776d4-123">See Also</span></span>


[<span data-ttu-id="776d4-124">在 Lync Server 2013 中建立或修改網路網站</span><span class="sxs-lookup"><span data-stu-id="776d4-124">Creating or modifying network sites in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-sites.md)  
[<span data-ttu-id="776d4-125">在 Lync Server 2013 中刪除現有的網路網站</span><span class="sxs-lookup"><span data-stu-id="776d4-125">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

