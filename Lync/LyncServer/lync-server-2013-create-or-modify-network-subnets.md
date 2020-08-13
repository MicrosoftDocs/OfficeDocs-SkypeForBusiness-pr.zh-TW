---
title: Lync Server 2013：建立或修改網路子網
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1eafbf7322fadd8d0373d3f2c40a0f495928c98
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a><span data-ttu-id="c488b-102">在 Lync Server 2013 中建立或修改網路子網</span><span class="sxs-lookup"><span data-stu-id="c488b-102">Create or modify network subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c488b-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c488b-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c488b-104">網路子網必須與網路網站相關聯，以判斷屬於該子網之主機的地理位置。</span><span class="sxs-lookup"><span data-stu-id="c488b-104">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="c488b-105">您可以使用 Lync Server 控制台設定子網。</span><span class="sxs-lookup"><span data-stu-id="c488b-105">You can use Lync Server Control Panel to configure subnets.</span></span> <span data-ttu-id="c488b-106">在 [Lync Server 控制台] 中，您可以建立、修改或刪除網路子網。</span><span class="sxs-lookup"><span data-stu-id="c488b-106">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="c488b-107">如需有關刪除網路子網的詳細資訊，請參閱[刪除網路子網中的 Lync Server 2013](lync-server-2013-deleting-network-subnets.md)。</span><span class="sxs-lookup"><span data-stu-id="c488b-107">For details about deleting network subnets, see [Deleting network subnets in Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span></span>

<span data-ttu-id="c488b-108">在大多數安裝通話許可控制 (CAC) 的 Microsoft Lync Server 2013 中，通常會有大量子網。</span><span class="sxs-lookup"><span data-stu-id="c488b-108">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="c488b-109">因此，通常最好是從 Lync Server 管理命令介面來設定子網。</span><span class="sxs-lookup"><span data-stu-id="c488b-109">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="c488b-110">從那裡，您可以將**New-CsNetworkSubnet**與 Windows PowerShell Cmdlet 匯**入-CSV**搭配呼叫。</span><span class="sxs-lookup"><span data-stu-id="c488b-110">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="c488b-111">透過這些 Cmdlet 一起使用，您可以從逗點分隔的值讀取子網設定 ( .csv) 檔案，並同時建立多個子網。</span><span class="sxs-lookup"><span data-stu-id="c488b-111">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="c488b-112">如需如何從 .csv 檔案建立子網的範例，請參閱[New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。</span><span class="sxs-lookup"><span data-stu-id="c488b-112">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-create-a-network-subnet"></a><span data-ttu-id="c488b-113">建立網路子網</span><span class="sxs-lookup"><span data-stu-id="c488b-113">To create a network subnet</span></span>

1.  <span data-ttu-id="c488b-114">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c488b-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c488b-115">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="c488b-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c488b-116">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="c488b-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c488b-117">在左導覽列中，依序按一下 **[網路設定]** 和 **[子網路]**。</span><span class="sxs-lookup"><span data-stu-id="c488b-117">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="c488b-118">在 [**子網**] 頁面上，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="c488b-118">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="c488b-119">在 [**新建子網上**] 中，于 [**子網識別碼**] 欄位中輸入值。</span><span class="sxs-lookup"><span data-stu-id="c488b-119">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="c488b-120">這必須是 IP 位址 (例如，174.11.12.0) ，而且必須是子網定義之 IP 位址範圍中的第一個位址。</span><span class="sxs-lookup"><span data-stu-id="c488b-120">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="c488b-121">在 [**遮罩**] 欄位中，輸入介於1到32的數值。</span><span class="sxs-lookup"><span data-stu-id="c488b-121">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c488b-122">這個值是要套用至所建立之子網的位元遮罩。</span><span class="sxs-lookup"><span data-stu-id="c488b-122">This value is the bitmask that is to be applied to the subnet being created.</span></span>

    
    </div>

7.  <span data-ttu-id="c488b-123">在 [**網路網站識別碼**] 中，選取此子網所屬的網站。</span><span class="sxs-lookup"><span data-stu-id="c488b-123">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="c488b-124"> (選用) 在 [**描述**] 欄位中輸入值，以提供無法獨立以名稱表示之子網的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="c488b-124">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="c488b-125">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="c488b-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-subnet"></a><span data-ttu-id="c488b-126">若要修改網路子網</span><span class="sxs-lookup"><span data-stu-id="c488b-126">To modify a network subnet</span></span>

1.  <span data-ttu-id="c488b-127">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c488b-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c488b-128">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="c488b-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c488b-129">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="c488b-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c488b-130">在左導覽列中，依序按一下 **[網路設定]** 和 **[子網路]**。</span><span class="sxs-lookup"><span data-stu-id="c488b-130">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="c488b-131">在 [**子網**] 頁面上，按一下您要修改的子網。</span><span class="sxs-lookup"><span data-stu-id="c488b-131">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="c488b-132">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="c488b-132">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="c488b-133">在 [**編輯子網**] 頁面上，您可以修改位元遮罩、關聯的網路網站或描述。</span><span class="sxs-lookup"><span data-stu-id="c488b-133">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="c488b-134">如果您修改位元遮罩，請記住子網識別碼仍必須是子網所定義之 IP 位址範圍中的第一個位址。</span><span class="sxs-lookup"><span data-stu-id="c488b-134">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="c488b-135">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="c488b-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c488b-136">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c488b-136">See Also</span></span>


[<span data-ttu-id="c488b-137">在 Lync Server 2013 中刪除網路子網</span><span class="sxs-lookup"><span data-stu-id="c488b-137">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  


[<span data-ttu-id="c488b-138">關於 Lync Server 2013 中的網路地區、網站和子網</span><span class="sxs-lookup"><span data-stu-id="c488b-138">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[<span data-ttu-id="c488b-139">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="c488b-139">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[<span data-ttu-id="c488b-140">CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="c488b-140">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[<span data-ttu-id="c488b-141">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="c488b-141">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[<span data-ttu-id="c488b-142">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="c488b-142">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

