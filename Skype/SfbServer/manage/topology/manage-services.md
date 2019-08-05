---
title: 管理商務用 Skype Server 中的服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 瞭解如何查看服務狀態、啟動和停止服務, 以及防範服務的會話。
ms.openlocfilehash: c3c0ad3a61543caf7866582413a67968c4c1c2d6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187099"
---
# <a name="manage-services-in-skype-for-business-server"></a><span data-ttu-id="4765d-103">管理商務用 Skype Server 中的服務</span><span class="sxs-lookup"><span data-stu-id="4765d-103">Manage services in Skype for Business Server</span></span>

<span data-ttu-id="4765d-104">您可以使用商務用 Skype Server 的 [控制台] 來查看在您的拓撲中執行商務用 Skype 伺服器的所有電腦清單、查看服務狀態、開始或停止服務, 以及防止服務的會話。</span><span class="sxs-lookup"><span data-stu-id="4765d-104">You can use the Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business Server in your topology, view the status of services, start or stop services, and prevent sessions for services.</span></span>

- [<span data-ttu-id="4765d-105">查看執行商務用 Skype Server 的電腦清單</span><span class="sxs-lookup"><span data-stu-id="4765d-105">View a list of computers running Skype for Business Server</span></span>](#view-a-list-of-computers-running-skype-for-business-server)
- [<span data-ttu-id="4765d-106">在商務用 Skype 中查看電腦上執行的服務狀態</span><span class="sxs-lookup"><span data-stu-id="4765d-106">View the status of services running on a computer in Skype for Business</span></span>](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [<span data-ttu-id="4765d-107">啟動或停止商務用 Skype 服務</span><span class="sxs-lookup"><span data-stu-id="4765d-107">Start or stop Skype for Business services</span></span>](#start-or-stop-skype-for-business-services)
- [<span data-ttu-id="4765d-108">避免服務的會話</span><span class="sxs-lookup"><span data-stu-id="4765d-108">Prevent sessions for services</span></span>](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a><span data-ttu-id="4765d-109">查看執行商務用 Skype Server 的電腦清單</span><span class="sxs-lookup"><span data-stu-id="4765d-109">View a list of computers running Skype for Business Server</span></span>

<span data-ttu-id="4765d-110">使用商務用 Skype Server [控制台] 來查看在您的拓撲中執行商務用 Skype 的所有電腦清單, 並查看每個電腦的服務狀態。</span><span class="sxs-lookup"><span data-stu-id="4765d-110">Use the Skype for Business Server Control Panel to view a list of all the computers that are running Skype for Business in your topology and see the service status of each.</span></span> <span data-ttu-id="4765d-111">您可以依電腦、池或網站排序清單。</span><span class="sxs-lookup"><span data-stu-id="4765d-111">You can sort the list by computer, pool, or site.</span></span> 

1. <span data-ttu-id="4765d-112">從指派給商務用 Skype Server 任何預先定義之系統管理角色的使用者帳戶, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="4765d-112">From a user account that is assigned to any of the predefined administrative roles for Skype for Business Server, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="4765d-113">如需詳細資訊, 請參閱[商務用 Skype Server 的角色式存取控制 (RBAC)](../../plan-your-deployment/security/role-based-access-control-rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="4765d-113">For more information, see [Role-based access control (RBAC) for Skype for Business Server](../../plan-your-deployment/security/role-based-access-control-rbac.md).</span></span>
2. <span data-ttu-id="4765d-114">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="4765d-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="4765d-115">如需可用於啟動商務用 Skype Server 控制台的不同方法的詳細資訊, 請參閱[安裝及開啟 [管理工具](../../management-tools/install-and-open-administrative-tools.md)]。</span><span class="sxs-lookup"><span data-stu-id="4765d-115">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="4765d-116">在左側導覽列中, 按一下 [**拓撲**], 然後按一下 [**狀態**]。</span><span class="sxs-lookup"><span data-stu-id="4765d-116">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="4765d-117">在 [狀態] 頁面上, 視需要執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="4765d-117">On the Status page, do either of the following as needed:</span></span>
    - <span data-ttu-id="4765d-118">按一下 [**電腦**]、[**池**] 或 [**網站**欄] 標題, 然後按一下向上箭號或向下箭號, 即可排序清單。</span><span class="sxs-lookup"><span data-stu-id="4765d-118">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span>
    - <span data-ttu-id="4765d-119">按一下\*\*\*\* [重新整理], 以查看最新的清單。</span><span class="sxs-lookup"><span data-stu-id="4765d-119">Click **Refresh** to view the most up-to-date list.</span></span>
    - <span data-ttu-id="4765d-120">在搜尋欄位中輸入電腦名稱稱, 以搜尋特定電腦。</span><span class="sxs-lookup"><span data-stu-id="4765d-120">Search for a specific computer by typing the computer name in the search field.</span></span>
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a><span data-ttu-id="4765d-121">在商務用 Skype 中查看電腦上執行的服務狀態</span><span class="sxs-lookup"><span data-stu-id="4765d-121">View the status of services running on a computer in Skype for Business</span></span>

<span data-ttu-id="4765d-122">使用商務用 Skype Server 的 [控制台] 來查看所有在商務用 Skype Server 拓撲中的特定電腦上執行的服務, 並查看每個服務的狀態。</span><span class="sxs-lookup"><span data-stu-id="4765d-122">Use the Skype for Business Server Control Panel to view all the services that are running on a specific computer in your Skype for Business Server topology and see the status of each service.</span></span>

1. <span data-ttu-id="4765d-123">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="4765d-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="4765d-124">開啟瀏覽器視窗, 然後輸入管理員 URL 來開啟 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="4765d-124">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="4765d-125">如需可用於啟動商務用 Skype Server 控制台的不同方法的詳細資訊, 請參閱[安裝及開啟 [管理工具](../../management-tools/install-and-open-administrative-tools.md)]。</span><span class="sxs-lookup"><span data-stu-id="4765d-125">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="4765d-126">在左側導覽列中, 按一下 [**拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="4765d-126">In the left navigation bar, click **Topology**.</span></span>
4. <span data-ttu-id="4765d-127">在 [狀態] 頁面上, 根據需要排序或搜尋清單, 以尋找您感興趣的電腦, 然後按一下該電腦的名稱。</span><span class="sxs-lookup"><span data-stu-id="4765d-127">On the Status page, sort or search the list, as required, to find the computer you’re interested in, and then click the computer name.</span></span>
5. <span data-ttu-id="4765d-128">請執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="4765d-128">Do either of the following:</span></span>
    - <span data-ttu-id="4765d-129">若要查看電腦上執行的服務的最新狀態, 請按一下 [**取得服務狀態**]。</span><span class="sxs-lookup"><span data-stu-id="4765d-129">To see the latest status of services running on the computer, click **Get service status**.</span></span>
    - <span data-ttu-id="4765d-130">若要查看電腦上執行的特定服務清單, 以及每個服務的狀態, 請按一下 [**屬性**], 然後按一下 [**關閉**] 以返回清單。</span><span class="sxs-lookup"><span data-stu-id="4765d-130">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4765d-131">使用 Windows PowerShell Cmdlet 來查看服務狀態</span><span class="sxs-lookup"><span data-stu-id="4765d-131">Viewing service status by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4765d-132">您也可以使用 Windows PowerShell 和 CsWindowsService Cmdlet 來查看服務狀態。</span><span class="sxs-lookup"><span data-stu-id="4765d-132">You can also view service status by using Windows PowerShell and the Get-CsWindowsService cmdlet.</span></span> <span data-ttu-id="4765d-133">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4765d-133">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4765d-134">如需詳細資訊, 請參閱[商務用 Skype Server 管理命令](../management-shell.md)介面。</span><span class="sxs-lookup"><span data-stu-id="4765d-134">For more information, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>

<span data-ttu-id="4765d-135">**若要查看服務狀態**</span><span class="sxs-lookup"><span data-stu-id="4765d-135">**To view service status**</span></span>

<span data-ttu-id="4765d-136">若要在電腦上查看服務狀態, 請在商務用 Skype Server Management Shell 中輸入類似以下的命令, 然後按 Enter:</span><span class="sxs-lookup"><span data-stu-id="4765d-136">To view service status on a computer, type a command similar to the following in the Skype for Business Server Management Shell, and then press Enter:</span></span>

`Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status`

<span data-ttu-id="4765d-137">這個命令會傳回如下所示的資訊:</span><span class="sxs-lookup"><span data-stu-id="4765d-137">This command returns information similar to the following:</span></span>

```
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

<span data-ttu-id="4765d-138">如需詳細資訊, 請參閱[CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService)。</span><span class="sxs-lookup"><span data-stu-id="4765d-138">For details, see [Get-CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService).</span></span>

## <a name="start-or-stop-skype-for-business-services"></a><span data-ttu-id="4765d-139">啟動或停止商務用 Skype 服務</span><span class="sxs-lookup"><span data-stu-id="4765d-139">Start or stop Skype for Business services</span></span>

<span data-ttu-id="4765d-140">使用商務用 Skype Server 的 [控制台] 來啟動或停止在特定電腦上執行的所有商務用 Skype Server 服務, 或是啟動或停止特定服務。</span><span class="sxs-lookup"><span data-stu-id="4765d-140">Use the Skype for Business Server Control Panel to start or stop all the Skype for Business Server services running on a specific computer or to start or stop a specific service.</span></span>

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a><span data-ttu-id="4765d-141">在電腦上啟動或停止所有商務用 Skype Server 服務</span><span class="sxs-lookup"><span data-stu-id="4765d-141">Start or stop all Skype for Business Server services on a computer</span></span>

1. <span data-ttu-id="4765d-142">從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權利), 或指派給 CsServerAdministrator 或 CsAdministrator 角色, 登入您在其中部署商務用 Skype Server 的網路中的任何電腦.</span><span class="sxs-lookup"><span data-stu-id="4765d-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span> <span data-ttu-id="4765d-143">您可以執行如下所示的命令來判斷您是否已獲指派 CsServerAdministrator 或 CsAdministrator RBAC 角色:</span><span class="sxs-lookup"><span data-stu-id="4765d-143">You can determine whether you have been assigned the CsServerAdministrator or the CsAdministrator RBAC role by running a command similar to the following:</span></span>

    `Get-CsAdminRoleAssignment -Identity "kenmyer"`

2. <span data-ttu-id="4765d-144">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="4765d-144">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="4765d-145">如需可用於啟動商務用 Skype Server 控制台的不同方法的詳細資訊, 請參閱[安裝及開啟 [管理工具](../../management-tools/install-and-open-administrative-tools.md)]。</span><span class="sxs-lookup"><span data-stu-id="4765d-145">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="4765d-146">在左側導覽列中, 按一下 [**拓撲**], 然後按一下 [**狀態**]。</span><span class="sxs-lookup"><span data-stu-id="4765d-146">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="4765d-147">在 [狀態] 頁面上, 視需要排序或搜尋清單, 以尋找執行您要開始或停止之服務的電腦, 然後按一下它。</span><span class="sxs-lookup"><span data-stu-id="4765d-147">On the Status page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="4765d-148">按一下 [**動作**]。</span><span class="sxs-lookup"><span data-stu-id="4765d-148">Click **Action**.</span></span>
6. <span data-ttu-id="4765d-149">按一下 [**啟動所有服務**] 或 [**停止所有服務**]。</span><span class="sxs-lookup"><span data-stu-id="4765d-149">Click **Start All services** or **Stop All services**.</span></span>

### <a name="start-or-stop-a-specific-service"></a><span data-ttu-id="4765d-150">啟動或停止特定服務</span><span class="sxs-lookup"><span data-stu-id="4765d-150">Start or stop a specific service</span></span>

1. <span data-ttu-id="4765d-151">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="4765d-151">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
2. <span data-ttu-id="4765d-152">開啟瀏覽器視窗, 然後輸入管理員 URL 來開啟 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="4765d-152">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="4765d-153">如需可用於啟動商務用 Skype Server 控制台的不同方法的詳細資訊, 請參閱[安裝及開啟 [管理工具](../../management-tools/install-and-open-administrative-tools.md)]。</span><span class="sxs-lookup"><span data-stu-id="4765d-153">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="4765d-154">在左側導覽列中, 按一下 [**拓撲**], 然後按一下 [**狀態**]。</span><span class="sxs-lookup"><span data-stu-id="4765d-154">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="4765d-155">在 [狀態] 頁面上, 視需要排序或搜尋清單, 以尋找執行您要開始或停止之服務的電腦, 然後按一下它。</span><span class="sxs-lookup"><span data-stu-id="4765d-155">On the Status page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>
5. <span data-ttu-id="4765d-156">按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="4765d-156">Click **Properties**.</span></span>
6. <span data-ttu-id="4765d-157">如有需要, 請排序服務清單, 然後按一下您要開始或停止的服務。</span><span class="sxs-lookup"><span data-stu-id="4765d-157">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>
7. <span data-ttu-id="4765d-158">按一下 [**動作**]。</span><span class="sxs-lookup"><span data-stu-id="4765d-158">Click **Action**.</span></span>
8. <span data-ttu-id="4765d-159">按一下 [**開始服務**] 或 [**停止服務**]。</span><span class="sxs-lookup"><span data-stu-id="4765d-159">Click **Start service** or **Stop service**.</span></span>
9. <span data-ttu-id="4765d-160">按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="4765d-160">Click **Close**.</span></span>


## <a name="prevent-sessions-for-services"></a><span data-ttu-id="4765d-161">避免服務的會話</span><span class="sxs-lookup"><span data-stu-id="4765d-161">Prevent sessions for services</span></span>

<span data-ttu-id="4765d-162">使用商務用 Skype 的 [控制台] 來避免在特定電腦上執行所有商務用 Skype Server 服務的新會話, 或避免特定服務的新會話。</span><span class="sxs-lookup"><span data-stu-id="4765d-162">Use the Skype for Business Control Panel to prevent new sessions for all the Skype for Business Server services running on a specific computer or to prevent new sessions for a specific service.</span></span>

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a><span data-ttu-id="4765d-163">避免電腦上所有商務用 Skype Server 服務的新會話</span><span class="sxs-lookup"><span data-stu-id="4765d-163">Prevent new sessions for all  Skype for Business Server services on a computer</span></span>

1. <span data-ttu-id="4765d-164">從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權利), 或指派給 CsServerAdministrator 或 CsAdministrator 角色, 登入您在其中部署商務用 Skype Server 的網路中的任何電腦.</span><span class="sxs-lookup"><span data-stu-id="4765d-164">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="4765d-165">開啟瀏覽器視窗, 然後輸入管理員 URL 來開啟 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="4765d-165">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="4765d-166">如需可用於啟動商務用 Skype Server 控制台的不同方法的詳細資訊, 請參閱[安裝及開啟 [管理工具](../../management-tools/install-and-open-administrative-tools.md)]。</span><span class="sxs-lookup"><span data-stu-id="4765d-166">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="4765d-167">在左側導覽列中, 按一下 [**拓撲**], 然後按一下 [**狀態**]。</span><span class="sxs-lookup"><span data-stu-id="4765d-167">In the left navigation bar, click **Topology** and then click **Status**.</span></span>
4. <span data-ttu-id="4765d-168">在 [狀態] 頁面上, 視需要排序或搜尋清單, 以尋找執行您想要防止新會話之服務的電腦, 然後按一下該電腦。</span><span class="sxs-lookup"><span data-stu-id="4765d-168">On the Status page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>
5. <span data-ttu-id="4765d-169">按一下 [**動作**]。</span><span class="sxs-lookup"><span data-stu-id="4765d-169">Click **Action**.</span></span>
6. <span data-ttu-id="4765d-170">按一下 [**防止所有服務的新會話**]。</span><span class="sxs-lookup"><span data-stu-id="4765d-170">Click **Prevent new sessions for all services**.</span></span>

### <a name="prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="4765d-171">防止特定服務的新會話</span><span class="sxs-lookup"><span data-stu-id="4765d-171">Prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="4765d-172">從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權利), 或指派給 CsServerAdministrator 或 CsAdministrator 角色, 登入您在其中部署商務用 Skype Server 的網路中的任何電腦.</span><span class="sxs-lookup"><span data-stu-id="4765d-172">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
2. <span data-ttu-id="4765d-173">開啟瀏覽器視窗, 然後輸入管理員 URL 來開啟 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="4765d-173">Open a browser window, and then enter the Admin URL to open the Control Panel.</span></span> <span data-ttu-id="4765d-174">如需可用於啟動商務用 Skype Server 控制台的不同方法的詳細資訊, 請參閱[安裝及開啟 [管理工具](../../management-tools/install-and-open-administrative-tools.md)]。</span><span class="sxs-lookup"><span data-stu-id="4765d-174">For details about the different methods you can use to start the Skype for Business Server Control Panel, see [Install and open administrative tools](../../management-tools/install-and-open-administrative-tools.md).</span></span>
3. <span data-ttu-id="4765d-175">在左側導覽列中, 按一下 [**拓撲**], 然後按一下 [**狀態**]。</span><span class="sxs-lookup"><span data-stu-id="4765d-175">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
4. <span data-ttu-id="4765d-176">按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="4765d-176">Click **Properties**.</span></span>
5. <span data-ttu-id="4765d-177">如有需要, 請排序服務清單, 然後按一下您要防止新會話的服務。</span><span class="sxs-lookup"><span data-stu-id="4765d-177">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
6. <span data-ttu-id="4765d-178">按一下 [**動作**]。</span><span class="sxs-lookup"><span data-stu-id="4765d-178">Click **Action**.</span></span>
7. <span data-ttu-id="4765d-179">按一下 [**避免新的服務會話**]。</span><span class="sxs-lookup"><span data-stu-id="4765d-179">Click **Prevent new sessions for service**.</span></span>
8. <span data-ttu-id="4765d-180">按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="4765d-180">Click **Close**.</span></span>
