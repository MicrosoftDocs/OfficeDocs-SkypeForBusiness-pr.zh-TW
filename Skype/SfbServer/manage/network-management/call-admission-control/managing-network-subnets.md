---
title: 管理網路子網
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 在大部分的商務用 Skype Server 中執行通話許可控制時，會執行 (CAC) 的商務用 Skype 伺服器，通常會有許多子網。 因此，通常最好是從商務用 Skype Server 管理命令介面來設定子網。
ms.openlocfilehash: e2ac69190ab93b4b6d81fed13538cc6fcaa91f20
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816393"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="617b3-104">管理商務用 Skype Server 中的網路子網路</span><span class="sxs-lookup"><span data-stu-id="617b3-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="617b3-105">您可以使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面來管理網路子網。</span><span class="sxs-lookup"><span data-stu-id="617b3-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="617b3-106">在大部分的商務用 Skype Server 中執行通話許可控制時，會執行 (CAC) 的商務用 Skype 伺服器，通常會有許多子網。</span><span class="sxs-lookup"><span data-stu-id="617b3-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="617b3-107">因此，通常最好是從商務用 Skype Server 管理命令介面來設定子網。</span><span class="sxs-lookup"><span data-stu-id="617b3-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="617b3-108">請使用本文中的章節來查看網路子網資訊，或建立、修改或刪除網路子網。</span><span class="sxs-lookup"><span data-stu-id="617b3-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="617b3-109">查看網路子網資訊</span><span class="sxs-lookup"><span data-stu-id="617b3-109">View network subnet information</span></span> 

<span data-ttu-id="617b3-110">您可以使用下列程序來檢視網路子網路。</span><span class="sxs-lookup"><span data-stu-id="617b3-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="617b3-111">您可以從商務用 Skype Server 控制台建立、修改或刪除網路子網。</span><span class="sxs-lookup"><span data-stu-id="617b3-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="617b3-112">檢視網路子網路</span><span class="sxs-lookup"><span data-stu-id="617b3-112">To view a network subnet</span></span>

1.  <span data-ttu-id="617b3-113">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="617b3-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="617b3-114">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="617b3-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="617b3-115">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **子網**]。</span><span class="sxs-lookup"><span data-stu-id="617b3-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="617b3-116">在 **[子網路]** 頁面上，按一下您要檢視的子網路。</span><span class="sxs-lookup"><span data-stu-id="617b3-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="617b3-117">您一次只能檢視一個子網路。</span><span class="sxs-lookup"><span data-stu-id="617b3-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="617b3-118">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="617b3-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="617b3-119">使用 Windows PowerShell Cmdlet 來查看網路子網設定資訊</span><span class="sxs-lookup"><span data-stu-id="617b3-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="617b3-120">您可以使用 Windows PowerShell 和 Get-CsNetworkSubnet Cmdlet 來查看網路子網資訊。</span><span class="sxs-lookup"><span data-stu-id="617b3-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="617b3-121">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="617b3-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="617b3-122">若要查看網路子網資訊</span><span class="sxs-lookup"><span data-stu-id="617b3-122">To view network subnet information</span></span>

  - <span data-ttu-id="617b3-123">若要查看所有網路子網的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="617b3-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="617b3-124">如此將傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="617b3-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="617b3-125">如需詳細資訊，請參閱 [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="617b3-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="617b3-126">建立或修改網路子網</span><span class="sxs-lookup"><span data-stu-id="617b3-126">Create or modify network subnets</span></span> 

<span data-ttu-id="617b3-127">網路子網必須與網路網站相關聯，以判斷屬於該子網之主機的地理位置。</span><span class="sxs-lookup"><span data-stu-id="617b3-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="617b3-128">您可以使用商務用 Skype Server 控制台來設定子網。</span><span class="sxs-lookup"><span data-stu-id="617b3-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="617b3-129">您可以從商務用 Skype Server 控制台建立、修改或刪除網路子網。</span><span class="sxs-lookup"><span data-stu-id="617b3-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="617b3-130">在大部分的商務用 Skype Server 中執行通話許可控制時，會執行 (CAC) 的商務用 Skype 伺服器，通常會有許多子網。</span><span class="sxs-lookup"><span data-stu-id="617b3-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="617b3-131">因此，通常最好是從商務用 Skype Server 管理命令介面來設定子網。</span><span class="sxs-lookup"><span data-stu-id="617b3-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="617b3-132">從那裡，您可以將 **New-CsNetworkSubnet** 與 Windows PowerShell Cmdlet 匯 **入-CSV** 搭配呼叫。</span><span class="sxs-lookup"><span data-stu-id="617b3-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="617b3-133">透過這些 Cmdlet 一起使用，您可以從逗點分隔的值讀取子網設定 ( .csv) 檔案，並同時建立多個子網。</span><span class="sxs-lookup"><span data-stu-id="617b3-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="617b3-134">如需如何從 .csv 檔案建立子網的範例，請參閱 [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。</span><span class="sxs-lookup"><span data-stu-id="617b3-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="617b3-135">建立網路子網</span><span class="sxs-lookup"><span data-stu-id="617b3-135">To create a network subnet</span></span>

1.  <span data-ttu-id="617b3-136">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="617b3-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="617b3-137">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="617b3-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="617b3-138">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **子網**]。</span><span class="sxs-lookup"><span data-stu-id="617b3-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="617b3-139">在 [ **子網** ] 頁面上，按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="617b3-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="617b3-140">在 [ **新建子網上**] 中，于 [ **子網識別碼** ] 欄位中輸入值。</span><span class="sxs-lookup"><span data-stu-id="617b3-140">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="617b3-141">這必須是 IP 位址 (例如，174.11.12.0) ，而且必須是子網定義之 IP 位址範圍中的第一個位址。</span><span class="sxs-lookup"><span data-stu-id="617b3-141">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="617b3-142">在 [ **遮罩** ] 欄位中，輸入介於1到32的數值。</span><span class="sxs-lookup"><span data-stu-id="617b3-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="617b3-143">這個值是要套用至所建立之子網的位元遮罩。</span><span class="sxs-lookup"><span data-stu-id="617b3-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="617b3-144">在 [ **網路網站識別碼**] 中，選取此子網所屬的網站。</span><span class="sxs-lookup"><span data-stu-id="617b3-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="617b3-145"> (選用) 在 [ **描述** ] 欄位中輸入值，以提供無法獨立以名稱表示之子網的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="617b3-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="617b3-146">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="617b3-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="617b3-147">若要修改網路子網</span><span class="sxs-lookup"><span data-stu-id="617b3-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="617b3-148">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="617b3-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="617b3-149">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="617b3-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="617b3-150">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **子網**]。</span><span class="sxs-lookup"><span data-stu-id="617b3-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="617b3-151">在 [ **子網** ] 頁面上，按一下您要修改的子網。</span><span class="sxs-lookup"><span data-stu-id="617b3-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="617b3-152">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="617b3-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="617b3-153">在 [ **編輯子網** ] 頁面上，您可以修改位元遮罩、關聯的網路網站或描述。</span><span class="sxs-lookup"><span data-stu-id="617b3-153">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="617b3-154">如果您修改位元遮罩，請記住子網識別碼仍必須是子網所定義之 IP 位址範圍中的第一個位址。</span><span class="sxs-lookup"><span data-stu-id="617b3-154">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="617b3-155">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="617b3-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="617b3-156">刪除網路子網</span><span class="sxs-lookup"><span data-stu-id="617b3-156">Delete network subnets</span></span>

<span data-ttu-id="617b3-157">您可以使用下列程式來刪除子網。</span><span class="sxs-lookup"><span data-stu-id="617b3-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="617b3-158">您可以從商務用 Skype Server 控制台建立、修改或刪除網路子網。</span><span class="sxs-lookup"><span data-stu-id="617b3-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="617b3-159">在大部分的商務用 Skype Server 中執行通話許可控制時，會執行 (CAC) 的商務用 Skype 伺服器，通常會有許多子網。</span><span class="sxs-lookup"><span data-stu-id="617b3-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="617b3-160">因此，通常最好是從商務用 Skype Server 管理命令介面來設定子網。</span><span class="sxs-lookup"><span data-stu-id="617b3-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="617b3-161">從那裡，您可以將 **New-CsNetworkSubnet** 與 Windows PowerShell Cmdlet 匯 **入-CSV** 搭配呼叫。</span><span class="sxs-lookup"><span data-stu-id="617b3-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="617b3-162">透過這些 Cmdlet 一起使用，您可以從逗點分隔的值讀取子網設定 ( .csv) 檔案，並同時建立多個子網。</span><span class="sxs-lookup"><span data-stu-id="617b3-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="617b3-163">如需如何從 .csv 檔案建立子網的範例，請參閱 [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)。</span><span class="sxs-lookup"><span data-stu-id="617b3-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="617b3-164">若要刪除網路子網</span><span class="sxs-lookup"><span data-stu-id="617b3-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="617b3-165">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="617b3-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="617b3-166">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="617b3-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="617b3-167">在左導覽列中，按一下 [ **網路** 設定]，然後按一下 [ **子網**]。</span><span class="sxs-lookup"><span data-stu-id="617b3-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="617b3-168">在 [ **子網** ] 頁面上，按一下您要刪除的子網。</span><span class="sxs-lookup"><span data-stu-id="617b3-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="617b3-169">您可以一次刪除一個以上的子網。</span><span class="sxs-lookup"><span data-stu-id="617b3-169">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="617b3-170">若要執行此動作，請按住 CTRL 鍵並選取多個子網，然後按住 CTRL 鍵。</span><span class="sxs-lookup"><span data-stu-id="617b3-170">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="617b3-171">或者，若要選取所有子網，請按一下 [**編輯**] 功能表上的 [全 **選**]。</span><span class="sxs-lookup"><span data-stu-id="617b3-171">Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="617b3-172">在 **[編輯]** 功能表中，按一下 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="617b3-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="617b3-173">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="617b3-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="617b3-174">另請參閱</span><span class="sxs-lookup"><span data-stu-id="617b3-174">See Also</span></span>

[<span data-ttu-id="617b3-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="617b3-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="617b3-176">CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="617b3-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="617b3-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="617b3-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="617b3-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="617b3-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
