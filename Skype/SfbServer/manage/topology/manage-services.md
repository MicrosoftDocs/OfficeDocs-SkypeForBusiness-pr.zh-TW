---
title: 管理商務用 Skype Server 中的服務
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
description: 瞭解如何查看服務狀態、啟動和停止服務，以及防止服務的會話。
ms.openlocfilehash: 6071526febcd3a4c1cb925ae3fb704eca6db575c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826313"
---
# <a name="manage-services-in-skype-for-business-server"></a><span data-ttu-id="564a4-103">管理商務用 Skype Server 中的服務</span><span class="sxs-lookup"><span data-stu-id="564a4-103">Manage services in Skype for Business Server</span></span>

<span data-ttu-id="564a4-104">您可以使用商務用 Skype Server 控制台，以查看拓撲中執行商務用 Skype 伺服器的所有電腦清單、查看服務的狀態、啟動或停止服務，以及阻止服務的會話。</span><span class="sxs-lookup"><span data-stu-id="564a4-104">You can use the Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business Server in your topology, view the status of services, start or stop services, and prevent sessions for services.</span></span>

- [<span data-ttu-id="564a4-105">查看執行商務用 Skype 伺服器的電腦清單</span><span class="sxs-lookup"><span data-stu-id="564a4-105">View a list of computers running Skype for Business Server</span></span>](#view-a-list-of-computers-running-skype-for-business-server)
- [<span data-ttu-id="564a4-106">在商務用 Skype 中查看電腦上執行的服務狀態</span><span class="sxs-lookup"><span data-stu-id="564a4-106">View the status of services running on a computer in Skype for Business</span></span>](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [<span data-ttu-id="564a4-107">啟動或停止商務用 Skype 服務</span><span class="sxs-lookup"><span data-stu-id="564a4-107">Start or stop Skype for Business services</span></span>](#start-or-stop-skype-for-business-services)
- [<span data-ttu-id="564a4-108">防止服務的工作階段</span><span class="sxs-lookup"><span data-stu-id="564a4-108">Prevent sessions for services</span></span>](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="564a4-109">查看執行商務用 Skype 伺服器的電腦清單</span><span class="sxs-lookup"><span data-stu-id="564a4-109">View a list of computers running Skype for Business Server</span></span>

<span data-ttu-id="564a4-110">使用商務用 Skype Server 控制台，以查看拓撲中所有執行商務用 Skype 的電腦清單，並查看每個電腦的服務狀態。</span><span class="sxs-lookup"><span data-stu-id="564a4-110">Use the Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business in your topology and see the service status of each.</span></span> <span data-ttu-id="564a4-111">您可以依電腦、集區或網站來排序清單。</span><span class="sxs-lookup"><span data-stu-id="564a4-111">You can sort the list by computer, pool, or site.</span></span> 

1. <span data-ttu-id="564a4-112">從指派給商務用 Skype Server 之任何預先定義的系統管理角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="564a4-112">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="564a4-113">如需詳細資訊，請參閱 [以角色為基礎的存取控制 (用於商務用 Skype Server 的 RBAC) ](../../plan-your-deployment/security/role-based-access-control-rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="564a4-113">For more information, see [Role-based access control (RBAC) for Skype for Business Server](../../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>
2. <span data-ttu-id="564a4-114">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="564a4-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="564a4-115">如需您可以用來啟動商務用 Skype Server 控制台之不同方法的詳細資訊，請參閱 [安裝及開啟系統管理工具](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="564a4-115">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="564a4-116">在左導覽列中，按一下 [ **拓撲**]，然後按一下 [ **狀態**]。</span><span class="sxs-lookup"><span data-stu-id="564a4-116">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="564a4-117">在 [狀態] 頁面上，視需要執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="564a4-117">On the Status page, do either of the following as needed:</span></span>
    - <span data-ttu-id="564a4-118">按一下 **[電腦]**、**[集區]** 或 **[網站]** 欄標題，然後按一下向上箭頭或向下箭頭來排序清單。</span><span class="sxs-lookup"><span data-stu-id="564a4-118">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span>
    - <span data-ttu-id="564a4-119">按一下 **[重新整理]** 檢視最新清單。</span><span class="sxs-lookup"><span data-stu-id="564a4-119">Click **Refresh** to view the most up-to-date list.</span></span>
    - <span data-ttu-id="564a4-120">在搜尋欄位中輸入電腦名稱來搜尋特定電腦。</span><span class="sxs-lookup"><span data-stu-id="564a4-120">Search for a specific computer by typing the computer name in the search field.</span></span>
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a><span data-ttu-id="564a4-121">在商務用 Skype 中查看電腦上執行的服務狀態</span><span class="sxs-lookup"><span data-stu-id="564a4-121">View the status of services running on a computer in Skype for Business</span></span>

<span data-ttu-id="564a4-122">使用商務用 Skype Server 控制台，以查看在商務用 Skype 伺服器拓撲中的特定電腦上執行的所有服務，並查看每個服務的狀態。</span><span class="sxs-lookup"><span data-stu-id="564a4-122">Use the Skype for Business Server Control Panel to view all the services that are running on a specific computer in your Skype for Business Server topology and see the status of each service.</span></span>

1. <span data-ttu-id="564a4-123">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="564a4-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="564a4-124">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="564a4-124">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="564a4-125">如需您可以用來啟動商務用 Skype Server 控制台之不同方法的詳細資訊，請參閱 [安裝及開啟系統管理工具](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="564a4-125">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="564a4-126">在左側導覽列中，按一下 [拓撲]。</span><span class="sxs-lookup"><span data-stu-id="564a4-126">In the left navigation bar, click **Topology**.</span></span>
4. <span data-ttu-id="564a4-127">在 [狀態] 頁面上，視需要排序或搜尋清單，以尋找您所感興趣的電腦，然後按一下電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="564a4-127">On the Status page, sort or search the list, as required, to find the computer you’re interested in, and then click the computer name.</span></span>
5. <span data-ttu-id="564a4-128">請執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="564a4-128">Do either of the following:</span></span>
    - <span data-ttu-id="564a4-129">若要查看電腦上執行之服務的最新狀態，請按一下 [ **取得服務狀態**]。</span><span class="sxs-lookup"><span data-stu-id="564a4-129">To see the latest status of services running on the computer, click **Get service status**.</span></span>
    - <span data-ttu-id="564a4-130">若要查看電腦上執行的特定服務清單，以及每項服務的 **狀態，請按一下 [** 內容]，然後按一下 [ **關閉** ] 以回到清單。</span><span class="sxs-lookup"><span data-stu-id="564a4-130">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="564a4-131">使用 Windows PowerShell Cmdlet 來查看服務狀態</span><span class="sxs-lookup"><span data-stu-id="564a4-131">Viewing service status by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="564a4-132">您也可以使用 Windows PowerShell 和 Get-CsWindowsService Cmdlet 來查看服務狀態。</span><span class="sxs-lookup"><span data-stu-id="564a4-132">You can also view service status by using Windows PowerShell and the Get-CsWindowsService cmdlet.</span></span> <span data-ttu-id="564a4-133">您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端工作階段執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="564a4-133">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="564a4-134">如需詳細資訊，請參閱 [商務用 Skype Server 管理命令](../management-shell.md)介面。</span><span class="sxs-lookup"><span data-stu-id="564a4-134">For more information, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>

<span data-ttu-id="564a4-135">**若要查看服務狀態**</span><span class="sxs-lookup"><span data-stu-id="564a4-135">**To view service status**</span></span>

<span data-ttu-id="564a4-136">若要在電腦上查看服務狀態，請在商務用 Skype Server 管理命令介面中輸入類似下列的命令，然後按 Enter：</span><span class="sxs-lookup"><span data-stu-id="564a4-136">To view service status on a computer, type a command similar to the following in the Skype for Business Server Management Shell, and then press Enter:</span></span>

```powershell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

<span data-ttu-id="564a4-137">此命令會傳回與下列相似的資訊：</span><span class="sxs-lookup"><span data-stu-id="564a4-137">This command returns information similar to the following:</span></span>

```console
RoleName                                  Status
--------                                  ------
{W3SVC}                                   Running
{CentralManagement}                       Running
{ClsAgent}                                Running
{Registrar, UserServer, EdgeServer}       Running
{ApplicationServer}                       Running
{ConferencingServer}                      Running
{MediationServer}                         Running
```

<span data-ttu-id="564a4-138">如需詳細資訊，請參閱 [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService)。</span><span class="sxs-lookup"><span data-stu-id="564a4-138">For details, see [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).</span></span>

## <a name="start-or-stop-skype-for-business-services"></a><span data-ttu-id="564a4-139">啟動或停止商務用 Skype 服務</span><span class="sxs-lookup"><span data-stu-id="564a4-139">Start or stop Skype for Business services</span></span>

<span data-ttu-id="564a4-140">使用商務用 Skype Server 控制台來開始或停止在特定電腦上執行的所有商務用 Skype Server 服務，或是啟動或停止特定的服務。</span><span class="sxs-lookup"><span data-stu-id="564a4-140">Use the Skype for Business Server Control Panel to start or stop all the Skype for Business Server services running on a specific computer or to start or stop a specific service.</span></span>

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a><span data-ttu-id="564a4-141">啟動或停止電腦上的所有商務用 Skype Server 服務</span><span class="sxs-lookup"><span data-stu-id="564a4-141">Start or stop all Skype for Business Server services on a computer</span></span>

1. <span data-ttu-id="564a4-142">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="564a4-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span> <span data-ttu-id="564a4-143">您可以執行類似下列的命令，判斷是否已指派 CsServerAdministrator 或 CsAdministrator RBAC 角色：</span><span class="sxs-lookup"><span data-stu-id="564a4-143">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>

    ```powershell
    Get-CsAdminRoleAssignment -Identity "kenmyer"`
    ```

2. <span data-ttu-id="564a4-144">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="564a4-144">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="564a4-145">如需您可以用來啟動商務用 Skype Server 控制台之不同方法的詳細資訊，請參閱 [安裝及開啟系統管理工具](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="564a4-145">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="564a4-146">在左導覽列中，按一下 [ **拓撲**]，然後按一下 [ **狀態**]。</span><span class="sxs-lookup"><span data-stu-id="564a4-146">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="564a4-147">在 [狀態] 頁面上，視需要排序或搜尋清單，找到正在執行您要啟動或停止之服務的電腦，然後按一下該電腦。</span><span class="sxs-lookup"><span data-stu-id="564a4-147">On the Status page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="564a4-148">按一下 **[動作]**。</span><span class="sxs-lookup"><span data-stu-id="564a4-148">Click **Action**.</span></span>
6. <span data-ttu-id="564a4-149">按一下 **[啟動所有服務]** 或 **[停止所有服務]**。</span><span class="sxs-lookup"><span data-stu-id="564a4-149">Click **Start All services** or **Stop All services**.</span></span>

### <a name="start-or-stop-a-specific-service"></a><span data-ttu-id="564a4-150">啟動或停止特定服務</span><span class="sxs-lookup"><span data-stu-id="564a4-150">Start or stop a specific service</span></span>

1. <span data-ttu-id="564a4-151">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="564a4-151">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="564a4-152">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="564a4-152">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="564a4-153">如需您可以用來啟動商務用 Skype Server 控制台之不同方法的詳細資訊，請參閱 [安裝及開啟系統管理工具](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="564a4-153">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="564a4-154">在左導覽列中，按一下 [ **拓撲**]，然後按一下 [ **狀態**]。</span><span class="sxs-lookup"><span data-stu-id="564a4-154">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="564a4-155">在 [狀態] 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要啟動或停止服務的電腦，然後按一下該電腦。</span><span class="sxs-lookup"><span data-stu-id="564a4-155">On the Status page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="564a4-156">按一下 **[內容]**。</span><span class="sxs-lookup"><span data-stu-id="564a4-156">Click **Properties**.</span></span>
6. <span data-ttu-id="564a4-157">視需要排序服務清單，然後按一下您要啟動或停止的服務。</span><span class="sxs-lookup"><span data-stu-id="564a4-157">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>
7. <span data-ttu-id="564a4-158">按一下 **[動作]**。</span><span class="sxs-lookup"><span data-stu-id="564a4-158">Click **Action**.</span></span>
8. <span data-ttu-id="564a4-159">按一下 **[啟動服務]** 或 **[停止服務]**。</span><span class="sxs-lookup"><span data-stu-id="564a4-159">Click **Start service** or **Stop service**.</span></span>
9. <span data-ttu-id="564a4-160">按一下 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="564a4-160">Click **Close**.</span></span>


## <a name="prevent-sessions-for-services"></a><span data-ttu-id="564a4-161">防止服務的工作階段</span><span class="sxs-lookup"><span data-stu-id="564a4-161">Prevent sessions for services</span></span>

<span data-ttu-id="564a4-162">使用商務用 Skype 控制台，以防止在特定電腦上執行的所有商務用 Skype Server 服務的新會話，或阻止特定服務的新會話。</span><span class="sxs-lookup"><span data-stu-id="564a4-162">Use the Skype for Business Control Panel to prevent new sessions for all the Skype for Business Server services running on a specific computer or to prevent new sessions for a specific service.</span></span>

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a><span data-ttu-id="564a4-163">在電腦上阻止所有商務用 Skype Server 服務的新會話</span><span class="sxs-lookup"><span data-stu-id="564a4-163">Prevent new sessions for all  Skype for Business Server services on a computer</span></span>

1. <span data-ttu-id="564a4-164">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="564a4-164">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="564a4-165">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="564a4-165">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="564a4-166">如需您可以用來啟動商務用 Skype Server 控制台之不同方法的詳細資訊，請參閱 [安裝及開啟系統管理工具](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="564a4-166">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="564a4-167">在左導覽列中，按一下 **[拓樸]**，再按一下 **[狀態]**。</span><span class="sxs-lookup"><span data-stu-id="564a4-167">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="564a4-168">在 [狀態] 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要阻止新工作階段之服務的電腦，然後按一下該電腦。</span><span class="sxs-lookup"><span data-stu-id="564a4-168">On the Status page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>
5. <span data-ttu-id="564a4-169">按一下 **[動作]**。</span><span class="sxs-lookup"><span data-stu-id="564a4-169">Click **Action**.</span></span>
6. <span data-ttu-id="564a4-170">按一下 **[阻止對所有服務的新工作階段]**。</span><span class="sxs-lookup"><span data-stu-id="564a4-170">Click **Prevent new sessions for all services**.</span></span>

### <a name="prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="564a4-171">防止特定服務的新會話</span><span class="sxs-lookup"><span data-stu-id="564a4-171">Prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="564a4-172">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="564a4-172">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="564a4-173">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="564a4-173">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="564a4-174">如需您可以用來啟動商務用 Skype Server 控制台之不同方法的詳細資訊，請參閱 [安裝及開啟系統管理工具](../../management-tools/install-and-open-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="564a4-174">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="564a4-175">在左導覽列中，按一下 [ **拓撲**]，然後按一下 [ **狀態**]。</span><span class="sxs-lookup"><span data-stu-id="564a4-175">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="564a4-176">按一下 **[內容]**。</span><span class="sxs-lookup"><span data-stu-id="564a4-176">Click **Properties**.</span></span>
5. <span data-ttu-id="564a4-177">視需要排序服務清單，然後按一下要阻止新工作階段的服務。</span><span class="sxs-lookup"><span data-stu-id="564a4-177">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
6. <span data-ttu-id="564a4-178">按一下 **[動作]**。</span><span class="sxs-lookup"><span data-stu-id="564a4-178">Click **Action**.</span></span>
7. <span data-ttu-id="564a4-179">按一下 **[阻止對服務的新工作階段]**。</span><span class="sxs-lookup"><span data-stu-id="564a4-179">Click **Prevent new sessions for service**.</span></span>
8. <span data-ttu-id="564a4-180">按一下 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="564a4-180">Click **Close**.</span></span>
