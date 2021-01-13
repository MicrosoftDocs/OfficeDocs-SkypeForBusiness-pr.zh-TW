---
title: 管理商務用 Skype Server 的服務
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
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: 本文說明如何管理在商務用 Skype 伺服器拓撲中執行的服務。
ms.openlocfilehash: 05bf37248e710424b7540fe0dbcc10338bd1f4bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816593"
---
# <a name="manage-services-for-skype-for-business-server"></a><span data-ttu-id="96a67-103">管理商務用 Skype Server 的服務</span><span class="sxs-lookup"><span data-stu-id="96a67-103">Manage services for Skype for Business Server</span></span>

<span data-ttu-id="96a67-104">本文說明如何管理在商務用 Skype 伺服器拓撲中執行的服務。</span><span class="sxs-lookup"><span data-stu-id="96a67-104">This article describes how to manage services running in a Skype for Business Server topology.</span></span>
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="96a67-105">查看執行商務用 Skype 伺服器的電腦清單</span><span class="sxs-lookup"><span data-stu-id="96a67-105">View a list of computers running Skype for Business Server</span></span>
<span data-ttu-id="96a67-106"><a name="view_list"> </a></span><span class="sxs-lookup"><span data-stu-id="96a67-106"><a name="view_list"> </a></span></span>

<span data-ttu-id="96a67-107">您可以使用商務用 Skype Server 控制台，以查看拓撲中執行商務用 Skype 伺服器的所有電腦清單，並查看每個電腦的服務狀態。</span><span class="sxs-lookup"><span data-stu-id="96a67-107">You can use Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business Server in your topology and see the service status of each.</span></span> <span data-ttu-id="96a67-108">您可以依電腦、集區或網站來排序清單。</span><span class="sxs-lookup"><span data-stu-id="96a67-108">You can sort the list by computer, pool, or site.</span></span> 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="96a67-109">若要查看執行商務用 Skype 伺服器的電腦清單</span><span class="sxs-lookup"><span data-stu-id="96a67-109">To view a list of computers running Skype for Business Server</span></span>

1. <span data-ttu-id="96a67-110">從指派給商務用 Skype Server 之任何預先定義的系統管理角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="96a67-110">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="96a67-111">如需商務用 Skype Server 中可用的預先定義管理角色的詳細資訊，請參閱 **規劃 Role-Based 的存取控制**。</span><span class="sxs-lookup"><span data-stu-id="96a67-111">For details about the predefined administrative roles available in Skype for Business Server, see **Planning for Role-Based Access Control**.</span></span>   
2. <span data-ttu-id="96a67-112">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="96a67-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>   
3. <span data-ttu-id="96a67-113">在左導覽列中，按一下 **[拓撲]**，再按一下 **[狀態]**。</span><span class="sxs-lookup"><span data-stu-id="96a67-113">In the left navigation bar, click **Topology** and then click **Status**.</span></span>   
4. <span data-ttu-id="96a67-114">在 **[狀態]** 頁面上，視需要執行下列任何動作：</span><span class="sxs-lookup"><span data-stu-id="96a67-114">On the **Status** page, do any of the following as needed:</span></span>
   - <span data-ttu-id="96a67-115">按一下 **[電腦]**、**[集區]** 或 **[網站]** 欄標題，然後按一下向上箭頭或向下箭頭來排序清單。</span><span class="sxs-lookup"><span data-stu-id="96a67-115">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span> 
   - <span data-ttu-id="96a67-116">按一下 **[重新整理]** 檢視最新清單。</span><span class="sxs-lookup"><span data-stu-id="96a67-116">Click **Refresh** to view the most up-to-date list.</span></span>  
   - <span data-ttu-id="96a67-117">在搜尋欄位中輸入電腦名稱來搜尋特定電腦。</span><span class="sxs-lookup"><span data-stu-id="96a67-117">Search for a specific computer by typing the computer name in the search field.</span></span>
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a><span data-ttu-id="96a67-118">查看商務用 Skype server 上執行的服務狀態</span><span class="sxs-lookup"><span data-stu-id="96a67-118">View the status of services running on a Skype for Business server</span></span>
<span data-ttu-id="96a67-119"><a name="view-status"> </a></span><span class="sxs-lookup"><span data-stu-id="96a67-119"><a name="view-status"> </a></span></span>

<span data-ttu-id="96a67-120">您可以使用商務用 Skype Server 控制台，以查看在商務用 Skype 伺服器拓撲中的特定電腦上執行的所有服務，並查看每個服務的狀態。</span><span class="sxs-lookup"><span data-stu-id="96a67-120">You can use Skype for Business Server Control Panel to view all the services that are running on a specific computer in your Skype for Business Server topology and see the status of each service.</span></span>
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a><span data-ttu-id="96a67-121">若要查看電腦上執行的服務狀態</span><span class="sxs-lookup"><span data-stu-id="96a67-121">To view the status of services running on a computer</span></span>

1. <span data-ttu-id="96a67-122">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="96a67-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="96a67-123">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="96a67-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="96a67-124">在左側導覽列中，按一下 [拓撲]。</span><span class="sxs-lookup"><span data-stu-id="96a67-124">In the left navigation bar, click **Topology**.</span></span> 
4. <span data-ttu-id="96a67-125">在 [ **狀態** ] 頁面上，視需要排序或搜尋清單，以尋找您所感興趣的電腦，然後按一下電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="96a67-125">On the **Status** page, sort or search the list, as required, to find the computer you're interested in, and then click the computer name.</span></span>
5. <span data-ttu-id="96a67-126">執行下列任一項作業：</span><span class="sxs-lookup"><span data-stu-id="96a67-126">Do any of the following:</span></span>
   - <span data-ttu-id="96a67-127">若要查看電腦上執行之服務的最新狀態，請按一下 [ **取得服務狀態**]。</span><span class="sxs-lookup"><span data-stu-id="96a67-127">To see the latest status of services running on the computer, click **Get service status**.</span></span>
   - <span data-ttu-id="96a67-128">若要查看電腦上執行的特定服務清單，以及每項服務的 **狀態，請按一下 [** 內容]，然後按一下 [ **關閉** ] 以回到清單。</span><span class="sxs-lookup"><span data-stu-id="96a67-128">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a><span data-ttu-id="96a67-129">使用 Windows Powershell Cmdlet 查看服務狀態</span><span class="sxs-lookup"><span data-stu-id="96a67-129">Viewing service status with Windows Powershell cmdlets</span></span>

<span data-ttu-id="96a67-130">您也可以使用 Windows PowerShell 和 **Get-CsWindowsService** Cmdlet 來查看服務狀態。</span><span class="sxs-lookup"><span data-stu-id="96a67-130">You can also view service status by using Windows PowerShell and the **Get-CsWindowsService** cmdlet.</span></span> <span data-ttu-id="96a67-131">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端工作階段執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="96a67-131">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="96a67-132">如需使用遠端 Windows PowerShell 連線到商務用 Skype 伺服器的詳細資訊，請參閱博客文章 [：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。</span><span class="sxs-lookup"><span data-stu-id="96a67-132">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="96a67-133">商務用 Skype Server 中的程式相同。</span><span class="sxs-lookup"><span data-stu-id="96a67-133">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-service-status"></a><span data-ttu-id="96a67-134">若要查看服務狀態</span><span class="sxs-lookup"><span data-stu-id="96a67-134">To view service status</span></span>

<span data-ttu-id="96a67-135">若要在電腦上查看服務狀態，請在商務用 Skype Server 管理命令介面中輸入類似下列的命令，然後按 Enter：</span><span class="sxs-lookup"><span data-stu-id="96a67-135">To view service status on a computer, type a command similar to the following in the Skype for Business Server Management Shell and then press Enter:</span></span>
  
```PowerShell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

<span data-ttu-id="96a67-136">此命令會傳回與下列相似的資訊：</span><span class="sxs-lookup"><span data-stu-id="96a67-136">This command returns information similar to the following:</span></span>
  
|<span data-ttu-id="96a67-137">**擁有**</span><span class="sxs-lookup"><span data-stu-id="96a67-137">**RoleName**</span></span>|<span data-ttu-id="96a67-138">**狀態**</span><span class="sxs-lookup"><span data-stu-id="96a67-138">**Status**</span></span>|
|:-----|:-----|
|<span data-ttu-id="96a67-139">{W3SVC}</span><span class="sxs-lookup"><span data-stu-id="96a67-139">{W3SVC}</span></span>  <br/> |<span data-ttu-id="96a67-140">正在執行</span><span class="sxs-lookup"><span data-stu-id="96a67-140">Running</span></span>  <br/> |
|<span data-ttu-id="96a67-141">{CentralManagement}</span><span class="sxs-lookup"><span data-stu-id="96a67-141">{CentralManagement}</span></span>  <br/> | <span data-ttu-id="96a67-142">正在執行</span><span class="sxs-lookup"><span data-stu-id="96a67-142">Running</span></span> <br/> |
|<span data-ttu-id="96a67-143">{ClsAgent}</span><span class="sxs-lookup"><span data-stu-id="96a67-143">{ClsAgent}</span></span>  <br/> |<span data-ttu-id="96a67-144">正在執行</span><span class="sxs-lookup"><span data-stu-id="96a67-144">Running</span></span>  <br/> |
|<span data-ttu-id="96a67-145">{註冊機構，UserServer，Edgeserver atl-edge}</span><span class="sxs-lookup"><span data-stu-id="96a67-145">{Registrar, UserServer, EdgeServer}</span></span>  <br/> |<span data-ttu-id="96a67-146">正在執行</span><span class="sxs-lookup"><span data-stu-id="96a67-146">Running</span></span>  <br/> |
|<span data-ttu-id="96a67-147">{ApplicationServer}</span><span class="sxs-lookup"><span data-stu-id="96a67-147">{ApplicationServer}</span></span>  <br/> |<span data-ttu-id="96a67-148">正在執行</span><span class="sxs-lookup"><span data-stu-id="96a67-148">Running</span></span>  <br/> |
|<span data-ttu-id="96a67-149">{ConferencingServer}</span><span class="sxs-lookup"><span data-stu-id="96a67-149">{ConferencingServer}</span></span>  <br/> |<span data-ttu-id="96a67-150">正在執行</span><span class="sxs-lookup"><span data-stu-id="96a67-150">Running</span></span>  <br/> |
|<span data-ttu-id="96a67-151">{MediationServer}</span><span class="sxs-lookup"><span data-stu-id="96a67-151">{MediationServer}</span></span>  <br/> |<span data-ttu-id="96a67-152">正在執行</span><span class="sxs-lookup"><span data-stu-id="96a67-152">Running</span></span>  <br/> |
   
<span data-ttu-id="96a67-153">如需詳細資訊，請參閱 [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="96a67-153">For details, see [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps).</span></span>
  
## <a name="view-details-about-a-service"></a><span data-ttu-id="96a67-154">查看服務的詳細資料</span><span class="sxs-lookup"><span data-stu-id="96a67-154">View details about a service</span></span>
<span data-ttu-id="96a67-155"><a name="view_details"> </a></span><span class="sxs-lookup"><span data-stu-id="96a67-155"><a name="view_details"> </a></span></span>

<span data-ttu-id="96a67-156">您可以使用商務用 Skype Server 控制台，以查看拓撲中特定電腦上執行之每個服務的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="96a67-156">You can use Skype for Business Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="96a67-157">您可以查看每個服務的狀態，以及相關聯的資料庫、埠和相依服務等詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="96a67-157">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>
  
### <a name="to-view-details-for-a-service"></a><span data-ttu-id="96a67-158">若要查看服務的詳細資料</span><span class="sxs-lookup"><span data-stu-id="96a67-158">To view details for a service</span></span>

1. <span data-ttu-id="96a67-159">從指派給商務用 Skype Server 之任何預先定義的系統管理角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="96a67-159">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="96a67-160">如需商務用 Skype Server 中可用的預先定義管理角色的詳細資訊，請參閱 **規劃 Role-Based 的存取控制**。</span><span class="sxs-lookup"><span data-stu-id="96a67-160">For details about the predefined administrative roles available in Skype for Business Server, see **Planning for Role-Based Access Control**.</span></span>
2. <span data-ttu-id="96a67-161">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="96a67-161">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="96a67-162">在左導覽列中，按一下 **[拓樸]**，再按一下 **[狀態]**。</span><span class="sxs-lookup"><span data-stu-id="96a67-162">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="96a67-163">在 [ **狀態** ] 頁面中，排序或搜尋清單，然後按一下您要查看的電腦。</span><span class="sxs-lookup"><span data-stu-id="96a67-163">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>
5. <span data-ttu-id="96a67-164">按一下 **[內容]**。</span><span class="sxs-lookup"><span data-stu-id="96a67-164">Click **Properties**.</span></span>
6. <span data-ttu-id="96a67-165">在 [ **View Computer Detail] （詳細資料** ）視窗中，根據需要排序服務清單，然後按一下您要查看的服務。</span><span class="sxs-lookup"><span data-stu-id="96a67-165">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>
7. <span data-ttu-id="96a67-166">請視需要執行下列任何動作：</span><span class="sxs-lookup"><span data-stu-id="96a67-166">Do any of the following as needed:</span></span>
   - <span data-ttu-id="96a67-167">若要查看該特定服務的最新狀態，請按一下 [ **取得服務狀態**]。</span><span class="sxs-lookup"><span data-stu-id="96a67-167">To see the latest status of that specific service, click **Get service status**.</span></span>
   - <span data-ttu-id="96a67-168">若要查看該特定服務的詳細資料，請按一下 [ **屬性** ]，然後按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="96a67-168">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
   - <span data-ttu-id="96a67-169">若要回到拓撲中的所有電腦清單，請按一下 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="96a67-169">To return to the list of all computers in your topology, click **Close**.</span></span>
    
## <a name="start-or-stop-skype-for-business-server-services"></a><span data-ttu-id="96a67-170">啟動或停止商務用 Skype Server 服務</span><span class="sxs-lookup"><span data-stu-id="96a67-170">Start or stop Skype for Business Server services</span></span>
<span data-ttu-id="96a67-171"><a name="StartStop"> </a></span><span class="sxs-lookup"><span data-stu-id="96a67-171"><a name="StartStop"> </a></span></span>

<span data-ttu-id="96a67-172">您可以使用商務用 Skype Server 控制台來開始或停止在特定電腦上執行的所有商務用 Skype Server 服務，或是啟動或停止特定的服務。</span><span class="sxs-lookup"><span data-stu-id="96a67-172">You can use Skype for Business Server Control Panel to start or stop all the Skype for Business Server services running on a specific computer or to start or stop a specific service.</span></span>
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a><span data-ttu-id="96a67-173">啟動或停止電腦上所有的商務用 Skype 服務</span><span class="sxs-lookup"><span data-stu-id="96a67-173">To start or stop all Skype for Business services on a computer</span></span>

1. <span data-ttu-id="96a67-174">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="96a67-174">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span> <span data-ttu-id="96a67-175">您可以執行類似下列的命令，判斷是否已指派 CsServerAdministrator 或 CsAdministrator RBAC 角色：</span><span class="sxs-lookup"><span data-stu-id="96a67-175">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>
    
   ```PowerShell
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. <span data-ttu-id="96a67-176">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="96a67-176">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="96a67-177">在左導覽列中，按一下 **[拓撲]**，再按一下 **[狀態]**。</span><span class="sxs-lookup"><span data-stu-id="96a67-177">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="96a67-178">在 **[狀態]** 頁面上，視需要排序或搜尋清單，找到正在執行您要啟動或停止之服務的電腦，然後按一下該電腦。</span><span class="sxs-lookup"><span data-stu-id="96a67-178">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="96a67-179">按一下 **[動作]**。</span><span class="sxs-lookup"><span data-stu-id="96a67-179">Click **Action**.</span></span>
6. <span data-ttu-id="96a67-180">按一下 **[啟動所有服務]** 或 **[停止所有服務]**。</span><span class="sxs-lookup"><span data-stu-id="96a67-180">Click **Start All services** or **Stop All services**.</span></span>
    
### <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="96a67-181">啟動或停止特定服務</span><span class="sxs-lookup"><span data-stu-id="96a67-181">To start or stop a specific service</span></span>

1. <span data-ttu-id="96a67-182">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="96a67-182">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="96a67-183">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="96a67-183">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="96a67-184">在左導覽列中，按一下 **[拓樸]**，再按一下 **[狀態]**。</span><span class="sxs-lookup"><span data-stu-id="96a67-184">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="96a67-185">在 **[狀態]** 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要啟動或停止服務的電腦，然後按一下該電腦。</span><span class="sxs-lookup"><span data-stu-id="96a67-185">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="96a67-186">按一下 **[內容]**。</span><span class="sxs-lookup"><span data-stu-id="96a67-186">Click **Properties**.</span></span>
6. <span data-ttu-id="96a67-187">視需要排序服務清單，然後按一下您要啟動或停止的服務。</span><span class="sxs-lookup"><span data-stu-id="96a67-187">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>
7. <span data-ttu-id="96a67-188">按一下 **[動作]**。</span><span class="sxs-lookup"><span data-stu-id="96a67-188">Click **Action**.</span></span>
8. <span data-ttu-id="96a67-189">按一下 **[啟動服務]** 或 **[停止服務]**。</span><span class="sxs-lookup"><span data-stu-id="96a67-189">Click **Start service** or **Stop service**.</span></span>
9. <span data-ttu-id="96a67-190">按一下 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="96a67-190">Click **Close**.</span></span>
    
## <a name="prevent-sessions-for-services"></a><span data-ttu-id="96a67-191">防止服務的工作階段</span><span class="sxs-lookup"><span data-stu-id="96a67-191">Prevent sessions for services</span></span>
<span data-ttu-id="96a67-192"><a name="prevent_session"> </a></span><span class="sxs-lookup"><span data-stu-id="96a67-192"><a name="prevent_session"> </a></span></span>

<span data-ttu-id="96a67-193">您可以使用商務用 Skype Server 控制台，以防止在特定電腦上執行的所有商務用 Skype Server 服務的新會話，或阻止特定商務用 Skype Server 服務的新會話。</span><span class="sxs-lookup"><span data-stu-id="96a67-193">You can use Skype for Business Server Control Panel to prevent new sessions for all the Skype for Business Server services running on a specific computer or to prevent new sessions for a specific Skype for Business Server service.</span></span>
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a><span data-ttu-id="96a67-194">若要防止電腦上所有商務用 Skype 服務的新會話</span><span class="sxs-lookup"><span data-stu-id="96a67-194">To prevent new sessions for all Skype for Business services on a computer</span></span>

1. <span data-ttu-id="96a67-195">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="96a67-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="96a67-196">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="96a67-196">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="96a67-197">在左導覽列中，按一下 **[拓樸]**，再按一下 **[狀態]**。</span><span class="sxs-lookup"><span data-stu-id="96a67-197">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="96a67-198">在 **[狀態]** 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要阻止新工作階段之服務的電腦，然後按一下該電腦。</span><span class="sxs-lookup"><span data-stu-id="96a67-198">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>
5. <span data-ttu-id="96a67-199">按一下 **[動作]**。</span><span class="sxs-lookup"><span data-stu-id="96a67-199">Click **Action**.</span></span>
6. <span data-ttu-id="96a67-200">按一下 **[阻止對所有服務的新工作階段]**。</span><span class="sxs-lookup"><span data-stu-id="96a67-200">Click **Prevent new sessions for all services**.</span></span>
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="96a67-201">阻止特定服務的新工作階段</span><span class="sxs-lookup"><span data-stu-id="96a67-201">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="96a67-202">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="96a67-202">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="96a67-203">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="96a67-203">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
3. <span data-ttu-id="96a67-204">在左導覽列中，按一下 **[拓樸]**，再按一下 **[狀態]**。</span><span class="sxs-lookup"><span data-stu-id="96a67-204">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="96a67-205">在 **[狀態]** 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要啟動或停止服務的電腦，然後按一下該電腦。</span><span class="sxs-lookup"><span data-stu-id="96a67-205">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
5. <span data-ttu-id="96a67-206">按一下 **[內容]**。</span><span class="sxs-lookup"><span data-stu-id="96a67-206">Click **Properties**.</span></span>
6. <span data-ttu-id="96a67-207">視需要排序服務清單，然後按一下要阻止新工作階段的服務。</span><span class="sxs-lookup"><span data-stu-id="96a67-207">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
7. <span data-ttu-id="96a67-208">按一下 **[動作]**。</span><span class="sxs-lookup"><span data-stu-id="96a67-208">Click **Action**.</span></span>
8. <span data-ttu-id="96a67-209">按一下 **[阻止對服務的新工作階段]**。</span><span class="sxs-lookup"><span data-stu-id="96a67-209">Click **Prevent new sessions for service**.</span></span>
9. <span data-ttu-id="96a67-210">按一下 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="96a67-210">Click **Close**.</span></span>
    

