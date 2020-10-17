---
title: Lync Server 2013：查看電腦上執行之服務的狀態
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
ms.openlocfilehash: 95c633079e45eba40bd59c7666c752c2ef68b498
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518390"
---
# <a name="view-the-status-of-services-running-on-a-computer-in-lync-server-2013"></a><span data-ttu-id="23f48-102">在 Lync Server 2013 中查看電腦上執行的服務狀態</span><span class="sxs-lookup"><span data-stu-id="23f48-102">View the status of services running on a computer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23f48-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="23f48-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="23f48-104">您可以使用 Lync Server 2013 控制台，在 Lync Server 拓撲中查看在特定電腦上執行的所有服務，並查看每個服務的狀態。</span><span class="sxs-lookup"><span data-stu-id="23f48-104">You can use Lync Server 2013 Control Panel to view all the services that are running on a specific computer in your Lync Server topology and see the status of each service.</span></span>

<div>

## <a name="to-view-the-status-of-services-running-on-a-computer"></a><span data-ttu-id="23f48-105">若要查看電腦上執行的服務狀態</span><span class="sxs-lookup"><span data-stu-id="23f48-105">To view the status of services running on a computer</span></span>

1.  <span data-ttu-id="23f48-106">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="23f48-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="23f48-107">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="23f48-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="23f48-108">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="23f48-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="23f48-109">在左側導覽列中，按一下 [拓撲]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="23f48-109">In the left navigation bar, click **Topology**.</span></span>

4.  <span data-ttu-id="23f48-110">在 [ **狀態** ] 頁面上，視需要排序或搜尋清單，以尋找您所感興趣的電腦，然後按一下電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="23f48-110">On the **Status** page, sort or search the list, as required, to find the computer you’re interested in, and then click the computer name.</span></span>

5.  <span data-ttu-id="23f48-111">執行下列任一項作業：</span><span class="sxs-lookup"><span data-stu-id="23f48-111">Do any of the following:</span></span>
    
      - <span data-ttu-id="23f48-112">若要查看電腦上執行之服務的最新狀態，請按一下 [ **取得服務狀態**]。</span><span class="sxs-lookup"><span data-stu-id="23f48-112">To see the latest status of services running on the computer, click **Get service status**.</span></span>
    
      - <span data-ttu-id="23f48-113">若要查看電腦上執行的特定服務清單，以及每項服務的 **狀態，請按一下 [** 內容]，然後按一下 [ **關閉** ] 以回到清單。</span><span class="sxs-lookup"><span data-stu-id="23f48-113">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>

</div>

<div>

## <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="23f48-114">使用 Windows PowerShell Cmdlet 來查看服務狀態</span><span class="sxs-lookup"><span data-stu-id="23f48-114">Viewing Service Status by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="23f48-115">您也可以使用 Windows PowerShell 和 **Get-CsWindowsService** Cmdlet 來查看服務狀態。</span><span class="sxs-lookup"><span data-stu-id="23f48-115">You can also view service status by using Windows PowerShell and the **Get-CsWindowsService** cmdlet.</span></span> <span data-ttu-id="23f48-116">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="23f48-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="23f48-117">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="23f48-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-service-status"></a><span data-ttu-id="23f48-118">若要查看服務狀態</span><span class="sxs-lookup"><span data-stu-id="23f48-118">To view service status</span></span>

  - <span data-ttu-id="23f48-119">若要在電腦上查看服務狀態，請在 Lync Server 管理命令介面中輸入類似下列的命令，然後按 Enter：</span><span class="sxs-lookup"><span data-stu-id="23f48-119">To view service status on a computer, type a command similar to the following in the Lync Server Management Shell and then press Enter:</span></span>
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    <span data-ttu-id="23f48-120">此命令會傳回與下列相似的資訊：</span><span class="sxs-lookup"><span data-stu-id="23f48-120">This command returns information similar to the following:</span></span>
    
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

<span data-ttu-id="23f48-121">如需詳細資訊，請參閱 [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService)。</span><span class="sxs-lookup"><span data-stu-id="23f48-121">For details, see [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="23f48-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="23f48-122">See Also</span></span>


[<span data-ttu-id="23f48-123">在 Lync Server 2013 中管理裝置、電話及用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="23f48-123">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

