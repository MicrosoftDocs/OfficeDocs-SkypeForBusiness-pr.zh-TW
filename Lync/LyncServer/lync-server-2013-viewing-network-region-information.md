---
title: Lync Server 2013：查看網路地區資訊
description: Lync Server 2013：查看網路地區資訊。
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
ms.openlocfilehash: 225cafc392b9b9d0c23f3882d530ad6d2b59f165
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565369"
---
# <a name="viewing-network-region-information-in-lync-server-2013"></a><span data-ttu-id="d0bc0-103">在 Lync Server 2013 中查看網路地區資訊</span><span class="sxs-lookup"><span data-stu-id="d0bc0-103">Viewing network region information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0bc0-104">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d0bc0-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d0bc0-105">網路地區會與跨多個地理區域的網路不同部分交互連線。</span><span class="sxs-lookup"><span data-stu-id="d0bc0-105">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="d0bc0-106">每個網路地區都必須與中央網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="d0bc0-106">Every network region must be associated with a central site.</span></span> <span data-ttu-id="d0bc0-107">中央網站是執行通話許可控制服務 (CAC) 頻寬原則服務的資料中心網站。</span><span class="sxs-lookup"><span data-stu-id="d0bc0-107">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="d0bc0-108">您可以使用 Lync Server 控制台來查看網路地區。</span><span class="sxs-lookup"><span data-stu-id="d0bc0-108">You can use Lync Server Control Panel to view network regions.</span></span> <span data-ttu-id="d0bc0-109">網路地區包含的設定可決定是否允許透過網際網路的替代路徑進行音訊和視訊連線。</span><span class="sxs-lookup"><span data-stu-id="d0bc0-109">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="d0bc0-110">請使用本主題檢視現有的網路地區。</span><span class="sxs-lookup"><span data-stu-id="d0bc0-110">Use this topic to view existing network regions.</span></span> <span data-ttu-id="d0bc0-111">如需建立或修改現有網路地區的詳細資訊，請參閱 [在 Lync Server 2013 中建立或修改網路地區](lync-server-2013-creating-or-modifying-network-regions.md)。</span><span class="sxs-lookup"><span data-stu-id="d0bc0-111">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a><span data-ttu-id="d0bc0-112">使用 Lync Server 控制台查看網路區域的相關資訊</span><span class="sxs-lookup"><span data-stu-id="d0bc0-112">To view information about a network region with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d0bc0-113">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d0bc0-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d0bc0-114">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="d0bc0-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d0bc0-115">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d0bc0-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d0bc0-116">在左導覽列中，依序按一下 **[網路設定]** 和 **[地區]**。</span><span class="sxs-lookup"><span data-stu-id="d0bc0-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="d0bc0-117">在 **[地區]** 頁面上，按一下您要檢視的區域。</span><span class="sxs-lookup"><span data-stu-id="d0bc0-117">On the **Region** page, click the region you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0bc0-118">您一次僅可檢視一個區域。</span><span class="sxs-lookup"><span data-stu-id="d0bc0-118">You can only view one region at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="d0bc0-119">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="d0bc0-119">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d0bc0-120">使用 Windows PowerShell Cmdlet 來查看網路地區資訊</span><span class="sxs-lookup"><span data-stu-id="d0bc0-120">Viewing Network Region Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d0bc0-121">您可以使用 Windows PowerShell 和 **Get-CsNetworkRegion** Cmdlet 來查看網路地區資訊。</span><span class="sxs-lookup"><span data-stu-id="d0bc0-121">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="d0bc0-122">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d0bc0-122">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d0bc0-123">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="d0bc0-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-information"></a><span data-ttu-id="d0bc0-124">若要查看網路地區資訊</span><span class="sxs-lookup"><span data-stu-id="d0bc0-124">To view network region information</span></span>

  - <span data-ttu-id="d0bc0-125">若要查看所有網路區域的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="d0bc0-125">To view information about all your network regions, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="d0bc0-126">如此將傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="d0bc0-126">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

</div>

<span data-ttu-id="d0bc0-127">如需詳細資訊，請參閱 [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="d0bc0-127">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d0bc0-128">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d0bc0-128">See Also</span></span>


[<span data-ttu-id="d0bc0-129">在 Lync Server 2013 中建立或修改網路地區</span><span class="sxs-lookup"><span data-stu-id="d0bc0-129">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
[<span data-ttu-id="d0bc0-130">在 Lync Server 2013 中刪除現有的網路地區</span><span class="sxs-lookup"><span data-stu-id="d0bc0-130">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

