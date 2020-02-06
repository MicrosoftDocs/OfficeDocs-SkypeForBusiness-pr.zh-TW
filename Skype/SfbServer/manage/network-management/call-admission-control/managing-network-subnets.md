---
title: 管理網路子網
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 在部署呼叫許可控制（CAC）的大多數商務用 Skype Server 部署中，通常會有大量的子網。 因此，通常是從商務用 Skype Server Management Shell 設定子網的最佳方式。
ms.openlocfilehash: fd7d71b3971b176939967830ca3e071ef4c77dbf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817462"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="9a44c-104">管理商務用 Skype Server 中的網路子網路</span><span class="sxs-lookup"><span data-stu-id="9a44c-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="9a44c-105">您可以使用商務用 Skype Server 的 [控制台] 或 [商務用 Skype 伺服器管理] 命令介面來管理網路子網。</span><span class="sxs-lookup"><span data-stu-id="9a44c-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="9a44c-106">在部署呼叫許可控制（CAC）的大多數商務用 Skype Server 部署中，通常會有大量的子網。</span><span class="sxs-lookup"><span data-stu-id="9a44c-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="9a44c-107">因此，通常是從商務用 Skype Server Management Shell 設定子網的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="9a44c-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="9a44c-108">您可以使用本文中的章節來查看網路子網資訊，或建立、修改或刪除網路子網。</span><span class="sxs-lookup"><span data-stu-id="9a44c-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="9a44c-109">查看網路子網資訊</span><span class="sxs-lookup"><span data-stu-id="9a44c-109">View network subnet information</span></span> 

<span data-ttu-id="9a44c-110">您可以使用下列程式來查看網路子網。</span><span class="sxs-lookup"><span data-stu-id="9a44c-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="9a44c-111">從商務用 Skype Server 的 [控制台] 中，您可以建立、修改或刪除網路子網。</span><span class="sxs-lookup"><span data-stu-id="9a44c-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="9a44c-112">若要查看網路子網</span><span class="sxs-lookup"><span data-stu-id="9a44c-112">To view a network subnet</span></span>

1.  <span data-ttu-id="9a44c-113">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="9a44c-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9a44c-114">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="9a44c-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9a44c-115">在左導覽列中，按一下 [**網路**設定]，然後按一下 [**子網**]。</span><span class="sxs-lookup"><span data-stu-id="9a44c-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="9a44c-116">在 [**子網**] 頁面上，按一下您要查看的子網。</span><span class="sxs-lookup"><span data-stu-id="9a44c-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="9a44c-117">您一次只能查看一個子網。</span><span class="sxs-lookup"><span data-stu-id="9a44c-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="9a44c-118">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="9a44c-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9a44c-119">使用 Windows PowerShell Cmdlet 來查看網路子網配置資訊</span><span class="sxs-lookup"><span data-stu-id="9a44c-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="9a44c-120">網路子網資訊可以使用 Windows PowerShell 和 CsNetworkSubnet Cmdlet 來查看。</span><span class="sxs-lookup"><span data-stu-id="9a44c-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="9a44c-121">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9a44c-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="9a44c-122">若要查看網路子網資訊</span><span class="sxs-lookup"><span data-stu-id="9a44c-122">To view network subnet information</span></span>

  - <span data-ttu-id="9a44c-123">若要查看所有網路子網的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="9a44c-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="9a44c-124">這會傳回如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="9a44c-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="9a44c-125">如需詳細資訊，請參閱[CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="9a44c-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="9a44c-126">建立或修改網路子網</span><span class="sxs-lookup"><span data-stu-id="9a44c-126">Create or modify network subnets</span></span> 

<span data-ttu-id="9a44c-127">網路子網必須與網路網站建立關聯，才能判斷屬於該子網上之主機的地理位置。</span><span class="sxs-lookup"><span data-stu-id="9a44c-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="9a44c-128">您可以使用商務用 Skype Server 的 [控制台] 來設定子網。</span><span class="sxs-lookup"><span data-stu-id="9a44c-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="9a44c-129">從商務用 Skype Server 的 [控制台] 中，您可以建立、修改或刪除網路子網。</span><span class="sxs-lookup"><span data-stu-id="9a44c-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="9a44c-130">在部署呼叫許可控制（CAC）的大多數商務用 Skype Server 部署中，通常會有大量的子網。</span><span class="sxs-lookup"><span data-stu-id="9a44c-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="9a44c-131">因此，通常是從商務用 Skype Server Management Shell 設定子網的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="9a44c-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="9a44c-132">您可以從該處呼叫**CsNetworkSubnet** ，並與 Windows PowerShell Cmdlet **Import-CSV**搭配使用。</span><span class="sxs-lookup"><span data-stu-id="9a44c-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="9a44c-133">透過搭配使用這些 Cmdlet，您就可以從逗號分隔值（.csv）檔案朗讀子網設定，並同時建立多個子網。</span><span class="sxs-lookup"><span data-stu-id="9a44c-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="9a44c-134">如需如何從 .csv 檔案建立子網的範例，請參閱[新 CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。</span><span class="sxs-lookup"><span data-stu-id="9a44c-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="9a44c-135">建立網路子網</span><span class="sxs-lookup"><span data-stu-id="9a44c-135">To create a network subnet</span></span>

1.  <span data-ttu-id="9a44c-136">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="9a44c-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9a44c-137">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="9a44c-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9a44c-138">在左導覽列中，按一下 [**網路**設定]，然後按一下 [**子網**]。</span><span class="sxs-lookup"><span data-stu-id="9a44c-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="9a44c-139">在 [**子網**] 頁面上，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="9a44c-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="9a44c-140">在 [**新子網**] 中，在 [**子網識別碼**] 欄位中輸入一個值。</span><span class="sxs-lookup"><span data-stu-id="9a44c-140">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="9a44c-141">這必須是 IP 位址（例如，174.11.12.0），而且必須是子網上所定義之 IP 位址範圍中的第一個位址。</span><span class="sxs-lookup"><span data-stu-id="9a44c-141">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="9a44c-142">在 [ **Mask** ] （遮罩）欄位中，輸入介於1到32的數值。</span><span class="sxs-lookup"><span data-stu-id="9a44c-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="9a44c-143">這個值是要套用至要建立之子網上的位元遮罩。</span><span class="sxs-lookup"><span data-stu-id="9a44c-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="9a44c-144">在 [**網路網站識別碼**] 中，選取此子網所屬的網站。</span><span class="sxs-lookup"><span data-stu-id="9a44c-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="9a44c-145">可選在 [**描述**] 欄位中輸入一個值，以提供此子網無法單獨以名稱表示的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9a44c-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="9a44c-146">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9a44c-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="9a44c-147">修改網路子網</span><span class="sxs-lookup"><span data-stu-id="9a44c-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="9a44c-148">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="9a44c-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9a44c-149">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="9a44c-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9a44c-150">在左導覽列中，按一下 [**網路**設定]，然後按一下 [**子網**]。</span><span class="sxs-lookup"><span data-stu-id="9a44c-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="9a44c-151">在 [**子網**] 頁面上，按一下您要修改的子網。</span><span class="sxs-lookup"><span data-stu-id="9a44c-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="9a44c-152">按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="9a44c-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="9a44c-153">在 [**編輯子網**] 頁面上，您可以修改位元遮罩、相關的網路網站或描述。</span><span class="sxs-lookup"><span data-stu-id="9a44c-153">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="9a44c-154">如果您修改位元遮罩，請記住，子網識別碼仍必須是子網所定義之 IP 位址範圍中的第一個位址。</span><span class="sxs-lookup"><span data-stu-id="9a44c-154">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="9a44c-155">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9a44c-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="9a44c-156">刪除網路子網</span><span class="sxs-lookup"><span data-stu-id="9a44c-156">Delete network subnets</span></span>

<span data-ttu-id="9a44c-157">您可以使用下列程式來刪除子網。</span><span class="sxs-lookup"><span data-stu-id="9a44c-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="9a44c-158">從商務用 Skype Server 的 [控制台] 中，您可以建立、修改或刪除網路子網。</span><span class="sxs-lookup"><span data-stu-id="9a44c-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="9a44c-159">在部署呼叫許可控制（CAC）的大多數商務用 Skype Server 部署中，通常會有大量的子網。</span><span class="sxs-lookup"><span data-stu-id="9a44c-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="9a44c-160">因此，通常是從商務用 Skype Server Management Shell 設定子網的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="9a44c-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="9a44c-161">您可以從該處呼叫**CsNetworkSubnet** ，並與 Windows PowerShell Cmdlet **Import-CSV**搭配使用。</span><span class="sxs-lookup"><span data-stu-id="9a44c-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="9a44c-162">透過搭配使用這些 Cmdlet，您就可以從逗號分隔值（.csv）檔案朗讀子網設定，並同時建立多個子網。</span><span class="sxs-lookup"><span data-stu-id="9a44c-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="9a44c-163">如需如何從 .csv 檔案建立子網的範例，請參閱[新 CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。</span><span class="sxs-lookup"><span data-stu-id="9a44c-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="9a44c-164">刪除網路子網</span><span class="sxs-lookup"><span data-stu-id="9a44c-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="9a44c-165">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="9a44c-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9a44c-166">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="9a44c-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9a44c-167">在左導覽列中，按一下 [**網路**設定]，然後按一下 [**子網**]。</span><span class="sxs-lookup"><span data-stu-id="9a44c-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="9a44c-168">在 [**子網**] 頁面上，按一下您要刪除的子網。</span><span class="sxs-lookup"><span data-stu-id="9a44c-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="9a44c-169">您可以一次刪除一個以上的子網。</span><span class="sxs-lookup"><span data-stu-id="9a44c-169">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="9a44c-170">若要這樣做，請按住 CTRL 並選取多個子網，同時按住 CTRL 鍵。</span><span class="sxs-lookup"><span data-stu-id="9a44c-170">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="9a44c-171">或者，若要選取所有子網，請在 [**編輯**] 功能表上，按一下 [全**選**]。</span><span class="sxs-lookup"><span data-stu-id="9a44c-171">Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="9a44c-172">在 [**編輯**] 功能表上，按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="9a44c-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="9a44c-173">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9a44c-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="9a44c-174">請參閱</span><span class="sxs-lookup"><span data-stu-id="9a44c-174">See Also</span></span>

[<span data-ttu-id="9a44c-175">新-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="9a44c-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="9a44c-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="9a44c-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="9a44c-177">移除-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="9a44c-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="9a44c-178">CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="9a44c-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
