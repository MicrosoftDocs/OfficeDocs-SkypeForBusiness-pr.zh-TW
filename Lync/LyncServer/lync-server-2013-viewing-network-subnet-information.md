---
title: Lync Server 2013：查看網路子網資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network subnet information
ms:assetid: 46f165f2-efe3-4cc1-9fee-a78b7f2ed41e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688044(v=OCS.15)
ms:contentKeyID: 49733636
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c61c6c9c27fb6ba642a8996588dc2e4a3c3c42d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-subnet-information-in-lync-server-2013"></a><span data-ttu-id="bd827-102">在 Lync Server 2013 中查看網路子網資訊</span><span class="sxs-lookup"><span data-stu-id="bd827-102">Viewing network subnet information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd827-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="bd827-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="bd827-104">您可以使用下列程序來檢視網路子網路。</span><span class="sxs-lookup"><span data-stu-id="bd827-104">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="bd827-105">在 [Lync Server 控制台] 中，您可以建立、修改或刪除網路子網。</span><span class="sxs-lookup"><span data-stu-id="bd827-105">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="bd827-106">如需建立或修改網路子網的詳細資訊，請參閱[在 Lync Server 2013 中建立或修改網路子網](lync-server-2013-create-or-modify-network-subnets.md)。</span><span class="sxs-lookup"><span data-stu-id="bd827-106">For details about creating or modifying network subnets, see [Create or modify network subnets in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span></span>

<div>

## <a name="to-view-a-network-subnet"></a><span data-ttu-id="bd827-107">檢視網路子網路</span><span class="sxs-lookup"><span data-stu-id="bd827-107">To view a network subnet</span></span>

1.  <span data-ttu-id="bd827-108">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="bd827-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bd827-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="bd827-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bd827-110">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="bd827-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bd827-111">在左導覽列中，依序按一下 **[網路設定]** 和 **[子網路]**。</span><span class="sxs-lookup"><span data-stu-id="bd827-111">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="bd827-112">在 **[子網路]** 頁面上，按一下您要檢視的子網路。</span><span class="sxs-lookup"><span data-stu-id="bd827-112">On the **Subnet** page, click the subnet that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bd827-113">您一次只能檢視一個子網路。</span><span class="sxs-lookup"><span data-stu-id="bd827-113">You can only view one subnet at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="bd827-114">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料...]**。</span><span class="sxs-lookup"><span data-stu-id="bd827-114">On the **Edit** menu, click **Show details…**.</span></span>

</div>

<div>

## <a name="viewing-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bd827-115">使用 Windows PowerShell Cmdlet 來查看網路子網設定資訊</span><span class="sxs-lookup"><span data-stu-id="bd827-115">Viewing Network Subnet Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="bd827-116">您可以使用 Windows PowerShell 和 Get-CsNetworkSubnet Cmdlet 來查看網路子網資訊。</span><span class="sxs-lookup"><span data-stu-id="bd827-116">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="bd827-117">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bd827-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bd827-118">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="bd827-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-subnet-information"></a><span data-ttu-id="bd827-119">若要查看網路子網資訊</span><span class="sxs-lookup"><span data-stu-id="bd827-119">To view network subnet information</span></span>

  - <span data-ttu-id="bd827-120">若要查看所有網路子網的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="bd827-120">To view information about all your network subnets, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="bd827-121">如此將傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="bd827-121">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0

</div>

<span data-ttu-id="bd827-122">如需詳細資訊，請參閱 [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="bd827-122">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bd827-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bd827-123">See Also</span></span>


[<span data-ttu-id="bd827-124">在 Lync Server 2013 中建立或修改網路子網</span><span class="sxs-lookup"><span data-stu-id="bd827-124">Create or modify network subnets in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-network-subnets.md)  
[<span data-ttu-id="bd827-125">在 Lync Server 2013 中刪除網路子網</span><span class="sxs-lookup"><span data-stu-id="bd827-125">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

