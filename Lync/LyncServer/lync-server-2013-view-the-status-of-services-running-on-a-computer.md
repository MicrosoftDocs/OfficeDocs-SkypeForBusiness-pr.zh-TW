---
title: Lync Server 2013：查看電腦上執行的服務狀態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View the status of services running on a computer
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182606(v=OCS.15)
ms:contentKeyID: 48185804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 984f85fca13704864b3cd47c83e8f6adca575705
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-the-status-of-services-running-on-a-computer-in-lync-server-2013"></a><span data-ttu-id="368b6-102">在 Lync Server 2013 中查看電腦上執行的服務狀態</span><span class="sxs-lookup"><span data-stu-id="368b6-102">View the status of services running on a computer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="368b6-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="368b6-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="368b6-104">您可以使用 Lync Server 2013 [控制台] 來查看在 Lync Server 拓撲中的特定電腦上執行的所有服務，並查看每個服務的狀態。</span><span class="sxs-lookup"><span data-stu-id="368b6-104">You can use Lync Server 2013 Control Panel to view all the services that are running on a specific computer in your Lync Server topology and see the status of each service.</span></span>

<div>

## <a name="to-view-the-status-of-services-running-on-a-computer"></a><span data-ttu-id="368b6-105">若要查看電腦上執行的服務狀態</span><span class="sxs-lookup"><span data-stu-id="368b6-105">To view the status of services running on a computer</span></span>

1.  <span data-ttu-id="368b6-106">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="368b6-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="368b6-107">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="368b6-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="368b6-108">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="368b6-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="368b6-109">在左側導覽列中，按一下 [**拓撲**]。</span><span class="sxs-lookup"><span data-stu-id="368b6-109">In the left navigation bar, click **Topology**.</span></span>

4.  <span data-ttu-id="368b6-110">在 [**狀態**] 頁面上，根據需要排序或搜尋清單，以尋找您感興趣的電腦，然後按一下該電腦的名稱。</span><span class="sxs-lookup"><span data-stu-id="368b6-110">On the **Status** page, sort or search the list, as required, to find the computer you’re interested in, and then click the computer name.</span></span>

5.  <span data-ttu-id="368b6-111">請執行下列任何一項操作：</span><span class="sxs-lookup"><span data-stu-id="368b6-111">Do any of the following:</span></span>
    
      - <span data-ttu-id="368b6-112">若要查看電腦上執行的服務的最新狀態，請按一下 [**取得服務狀態**]。</span><span class="sxs-lookup"><span data-stu-id="368b6-112">To see the latest status of services running on the computer, click **Get service status**.</span></span>
    
      - <span data-ttu-id="368b6-113">若要查看電腦上執行的特定服務清單，以及每個服務的狀態，請按一下 [**屬性**]，然後按一下 [**關閉**] 以返回清單。</span><span class="sxs-lookup"><span data-stu-id="368b6-113">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>

</div>

<div>

## <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="368b6-114">使用 Windows PowerShell Cmdlet 來查看服務狀態</span><span class="sxs-lookup"><span data-stu-id="368b6-114">Viewing Service Status by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="368b6-115">您也可以使用 Windows PowerShell 和**CsWindowsService** Cmdlet 來查看服務狀態。</span><span class="sxs-lookup"><span data-stu-id="368b6-115">You can also view service status by using Windows PowerShell and the **Get-CsWindowsService** cmdlet.</span></span> <span data-ttu-id="368b6-116">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="368b6-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="368b6-117">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="368b6-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-service-status"></a><span data-ttu-id="368b6-118">若要查看服務狀態</span><span class="sxs-lookup"><span data-stu-id="368b6-118">To view service status</span></span>

  - <span data-ttu-id="368b6-119">若要在電腦上查看服務狀態，請在 Lync Server 管理命令介面中輸入類似以下的命令，然後按 Enter：</span><span class="sxs-lookup"><span data-stu-id="368b6-119">To view service status on a computer, type a command similar to the following in the Lync Server Management Shell and then press Enter:</span></span>
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    <span data-ttu-id="368b6-120">這個命令會傳回如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="368b6-120">This command returns information similar to the following:</span></span>
    
        RoleName                                  Status
        --------                                  ------
        {W3SVC}                                   Running
        {CentralManagement}                       Running
        {ClsAgent}                                Running
        {Registrar, UserServer, EdgeServer}       Running
        {ApplicationServer}                       Running
        {ConferencingServer}                      Running
        {MediationServer}                         Running

</div>

<span data-ttu-id="368b6-121">如需詳細資訊，請參閱[CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService)。</span><span class="sxs-lookup"><span data-stu-id="368b6-121">For details, see [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="368b6-122">請參閱</span><span class="sxs-lookup"><span data-stu-id="368b6-122">See Also</span></span>


[<span data-ttu-id="368b6-123">在 Lync Server 2013 中管理裝置、電話及用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="368b6-123">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

