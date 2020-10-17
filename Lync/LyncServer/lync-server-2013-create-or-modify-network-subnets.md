---
title: Lync Server 2013：建立或修改網路子網
description: Lync Server 2013：建立或修改網路子網。
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
ms.openlocfilehash: 37695707bf39b10c351a4990b132c9799406f9c4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546919"
---
# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a><span data-ttu-id="c238b-103">在 Lync Server 2013 中建立或修改網路子網</span><span class="sxs-lookup"><span data-stu-id="c238b-103">Create or modify network subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c238b-104">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c238b-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c238b-105">網路子網必須與網路網站相關聯，以判斷屬於該子網之主機的地理位置。</span><span class="sxs-lookup"><span data-stu-id="c238b-105">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="c238b-106">您可以使用 Lync Server 控制台設定子網。</span><span class="sxs-lookup"><span data-stu-id="c238b-106">You can use Lync Server Control Panel to configure subnets.</span></span> <span data-ttu-id="c238b-107">在 [Lync Server 控制台] 中，您可以建立、修改或刪除網路子網。</span><span class="sxs-lookup"><span data-stu-id="c238b-107">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="c238b-108">如需有關刪除網路子網的詳細資訊，請參閱 [刪除網路子網中的 Lync Server 2013](lync-server-2013-deleting-network-subnets.md)。</span><span class="sxs-lookup"><span data-stu-id="c238b-108">For details about deleting network subnets, see [Deleting network subnets in Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span></span>

<span data-ttu-id="c238b-109">在大多數安裝通話許可控制 (CAC) 的 Microsoft Lync Server 2013 中，通常會有大量子網。</span><span class="sxs-lookup"><span data-stu-id="c238b-109">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="c238b-110">因此，通常最好是從 Lync Server 管理命令介面來設定子網。</span><span class="sxs-lookup"><span data-stu-id="c238b-110">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="c238b-111">從那裡，您可以將 **New-CsNetworkSubnet** 與 Windows PowerShell Cmdlet 匯 **入-CSV**搭配呼叫。</span><span class="sxs-lookup"><span data-stu-id="c238b-111">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="c238b-112">透過這些 Cmdlet 一起使用，您可以從逗點分隔的值讀取子網設定 ( .csv) 檔案，並同時建立多個子網。</span><span class="sxs-lookup"><span data-stu-id="c238b-112">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="c238b-113">如需如何從 .csv 檔案建立子網的範例，請參閱 [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。</span><span class="sxs-lookup"><span data-stu-id="c238b-113">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-create-a-network-subnet"></a><span data-ttu-id="c238b-114">建立網路子網</span><span class="sxs-lookup"><span data-stu-id="c238b-114">To create a network subnet</span></span>

1.  <span data-ttu-id="c238b-115">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c238b-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c238b-116">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="c238b-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c238b-117">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="c238b-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c238b-118">在左導覽列中，依序按一下 **[網路設定]** 和 **[子網路]**。</span><span class="sxs-lookup"><span data-stu-id="c238b-118">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="c238b-119">在 [ **子網** ] 頁面上，按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="c238b-119">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="c238b-120">在 [ **新建子網上**] 中，于 [ **子網識別碼** ] 欄位中輸入值。</span><span class="sxs-lookup"><span data-stu-id="c238b-120">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="c238b-121">這必須是 IP 位址 (例如，174.11.12.0) ，而且必須是子網定義之 IP 位址範圍中的第一個位址。</span><span class="sxs-lookup"><span data-stu-id="c238b-121">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="c238b-122">在 [ **遮罩** ] 欄位中，輸入介於1到32的數值。</span><span class="sxs-lookup"><span data-stu-id="c238b-122">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c238b-123">這個值是要套用至所建立之子網的位元遮罩。</span><span class="sxs-lookup"><span data-stu-id="c238b-123">This value is the bitmask that is to be applied to the subnet being created.</span></span>

    
    </div>

7.  <span data-ttu-id="c238b-124">在 [ **網路網站識別碼**] 中，選取此子網所屬的網站。</span><span class="sxs-lookup"><span data-stu-id="c238b-124">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="c238b-125"> (選用) 在 [ **描述** ] 欄位中輸入值，以提供無法獨立以名稱表示之子網的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="c238b-125">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="c238b-126">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="c238b-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-subnet"></a><span data-ttu-id="c238b-127">若要修改網路子網</span><span class="sxs-lookup"><span data-stu-id="c238b-127">To modify a network subnet</span></span>

1.  <span data-ttu-id="c238b-128">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="c238b-128">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c238b-129">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="c238b-129">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c238b-130">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="c238b-130">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c238b-131">在左導覽列中，依序按一下 **[網路設定]** 和 **[子網路]**。</span><span class="sxs-lookup"><span data-stu-id="c238b-131">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="c238b-132">在 [ **子網** ] 頁面上，按一下您要修改的子網。</span><span class="sxs-lookup"><span data-stu-id="c238b-132">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="c238b-133">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="c238b-133">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="c238b-134">在 [ **編輯子網** ] 頁面上，您可以修改位元遮罩、關聯的網路網站或描述。</span><span class="sxs-lookup"><span data-stu-id="c238b-134">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="c238b-135">如果您修改位元遮罩，請記住子網識別碼仍必須是子網所定義之 IP 位址範圍中的第一個位址。</span><span class="sxs-lookup"><span data-stu-id="c238b-135">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="c238b-136">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="c238b-136">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c238b-137">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c238b-137">See Also</span></span>


[<span data-ttu-id="c238b-138">在 Lync Server 2013 中刪除網路子網</span><span class="sxs-lookup"><span data-stu-id="c238b-138">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  


[<span data-ttu-id="c238b-139">關於 Lync Server 2013 中的網路地區、網站和子網</span><span class="sxs-lookup"><span data-stu-id="c238b-139">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[<span data-ttu-id="c238b-140">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="c238b-140">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[<span data-ttu-id="c238b-141">CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="c238b-141">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[<span data-ttu-id="c238b-142">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="c238b-142">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[<span data-ttu-id="c238b-143">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="c238b-143">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

