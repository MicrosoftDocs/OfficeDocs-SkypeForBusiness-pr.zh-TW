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
ms.openlocfilehash: 4d743e5cdbe8dc7f200175b74f55b1b3d003e769
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a><span data-ttu-id="e395c-102">在 Lync Server 2013 中建立或修改網路子網</span><span class="sxs-lookup"><span data-stu-id="e395c-102">Create or modify network subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e395c-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e395c-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e395c-104">網路子網必須與網路網站建立關聯，才能判斷屬於該子網上之主機的地理位置。</span><span class="sxs-lookup"><span data-stu-id="e395c-104">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="e395c-105">您可以使用 Lync Server [控制台] 來設定子網。</span><span class="sxs-lookup"><span data-stu-id="e395c-105">You can use Lync Server Control Panel to configure subnets.</span></span> <span data-ttu-id="e395c-106">您可以從 Lync Server [控制台] 建立、修改或刪除網路子網。</span><span class="sxs-lookup"><span data-stu-id="e395c-106">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="e395c-107">如需有關刪除網路子網的詳細資訊，請參閱[在 Lync Server 2013 中刪除網路子網](lync-server-2013-deleting-network-subnets.md)。</span><span class="sxs-lookup"><span data-stu-id="e395c-107">For details about deleting network subnets, see [Deleting network subnets in Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span></span>

<span data-ttu-id="e395c-108">在部署呼叫許可控制（CAC）的大多數 Microsoft Lync Server 2013 部署中，通常會有大量的子網。</span><span class="sxs-lookup"><span data-stu-id="e395c-108">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="e395c-109">因此，通常最好是從 Lync Server 管理命令介面設定子網。</span><span class="sxs-lookup"><span data-stu-id="e395c-109">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="e395c-110">您可以從該處呼叫**CsNetworkSubnet** ，並與 Windows PowerShell Cmdlet **Import-CSV**搭配使用。</span><span class="sxs-lookup"><span data-stu-id="e395c-110">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="e395c-111">透過搭配使用這些 Cmdlet，您就可以從逗號分隔值（.csv）檔案朗讀子網設定，並同時建立多個子網。</span><span class="sxs-lookup"><span data-stu-id="e395c-111">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="e395c-112">如需如何從 .csv 檔案建立子網的範例，請參閱[新 CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。</span><span class="sxs-lookup"><span data-stu-id="e395c-112">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-create-a-network-subnet"></a><span data-ttu-id="e395c-113">建立網路子網</span><span class="sxs-lookup"><span data-stu-id="e395c-113">To create a network subnet</span></span>

1.  <span data-ttu-id="e395c-114">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e395c-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e395c-115">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="e395c-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e395c-116">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="e395c-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e395c-117">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**子網**]。</span><span class="sxs-lookup"><span data-stu-id="e395c-117">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="e395c-118">在 [**子網**] 頁面上，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="e395c-118">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="e395c-119">在 [**新子網**] 中，在 [**子網識別碼**] 欄位中輸入一個值。</span><span class="sxs-lookup"><span data-stu-id="e395c-119">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="e395c-120">這必須是 IP 位址（例如，174.11.12.0），而且必須是子網上所定義之 IP 位址範圍中的第一個位址。</span><span class="sxs-lookup"><span data-stu-id="e395c-120">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="e395c-121">在 [ **Mask** ] （遮罩）欄位中，輸入介於1到32的數值。</span><span class="sxs-lookup"><span data-stu-id="e395c-121">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e395c-122">這個值是要套用至要建立之子網上的位元遮罩。</span><span class="sxs-lookup"><span data-stu-id="e395c-122">This value is the bitmask that is to be applied to the subnet being created.</span></span>

    
    </div>

7.  <span data-ttu-id="e395c-123">在 [**網路網站識別碼**] 中，選取此子網所屬的網站。</span><span class="sxs-lookup"><span data-stu-id="e395c-123">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="e395c-124">可選在 [**描述**] 欄位中輸入一個值，以提供此子網無法單獨以名稱表示的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e395c-124">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="e395c-125">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e395c-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-subnet"></a><span data-ttu-id="e395c-126">修改網路子網</span><span class="sxs-lookup"><span data-stu-id="e395c-126">To modify a network subnet</span></span>

1.  <span data-ttu-id="e395c-127">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="e395c-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e395c-128">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="e395c-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e395c-129">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="e395c-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e395c-130">在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**子網**]。</span><span class="sxs-lookup"><span data-stu-id="e395c-130">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="e395c-131">在 [**子網**] 頁面上，按一下您要修改的子網。</span><span class="sxs-lookup"><span data-stu-id="e395c-131">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="e395c-132">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="e395c-132">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="e395c-133">在 [**編輯子網**] 頁面上，您可以修改位元遮罩、相關的網路網站或描述。</span><span class="sxs-lookup"><span data-stu-id="e395c-133">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="e395c-134">如果您修改位元遮罩，請記住，子網識別碼仍必須是子網所定義之 IP 位址範圍中的第一個位址。</span><span class="sxs-lookup"><span data-stu-id="e395c-134">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="e395c-135">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e395c-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e395c-136">請參閱</span><span class="sxs-lookup"><span data-stu-id="e395c-136">See Also</span></span>


[<span data-ttu-id="e395c-137">刪除 Lync Server 2013 中的網路子網</span><span class="sxs-lookup"><span data-stu-id="e395c-137">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  


[<span data-ttu-id="e395c-138">關於 Lync Server 2013 中的網路區域、網站和子網路</span><span class="sxs-lookup"><span data-stu-id="e395c-138">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[<span data-ttu-id="e395c-139">新-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="e395c-139">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[<span data-ttu-id="e395c-140">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="e395c-140">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[<span data-ttu-id="e395c-141">移除-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="e395c-141">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[<span data-ttu-id="e395c-142">CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="e395c-142">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

