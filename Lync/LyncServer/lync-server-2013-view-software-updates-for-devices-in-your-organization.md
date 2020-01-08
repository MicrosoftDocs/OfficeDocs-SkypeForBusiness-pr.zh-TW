---
title: Lync Server 2013：查看貴組織中裝置的軟體更新
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06700e198dcd1923e875401b4539a0af84417c44
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40973988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a><span data-ttu-id="92cd4-102">在 Lync Server 2013 中查看裝置的軟體更新</span><span class="sxs-lookup"><span data-stu-id="92cd4-102">View software updates for devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92cd4-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="92cd4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="92cd4-104">使用 Lync Server 2013，您可以使用裝置更新 Web 服務來查看及管理貴組織裝置的軟體更新。</span><span class="sxs-lookup"><span data-stu-id="92cd4-104">With Lync Server 2013, you use Device Update Web service to view and manage software updates for your organization’s devices.</span></span> <span data-ttu-id="92cd4-105">這些更新在來自 Microsoft 支援網站的 .cab （檔櫃）檔案中提供[http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)。</span><span class="sxs-lookup"><span data-stu-id="92cd4-105">These updates are available in .cab (cabinet) files from the Microsoft Support website at [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091).</span></span> <span data-ttu-id="92cd4-106">下載 .cab 檔案之後，請執行匯**入-CSDeviceUpdate** Cmdlet，從 .cab 檔案匯入裝置更新規則。</span><span class="sxs-lookup"><span data-stu-id="92cd4-106">After you download the .cab file, run the **Import-CSDeviceUpdate** cmdlet to import the device update rules from the .cab file.</span></span> <span data-ttu-id="92cd4-107">如需有關**Import CSDeviceUpdate** Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔中的[import CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) 。</span><span class="sxs-lookup"><span data-stu-id="92cd4-107">For details about the **Import-CSDeviceUpdate** cmdlet, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="92cd4-108">在您的組織部署新的更新之前，請確認它能在測試裝置上正常運作。</span><span class="sxs-lookup"><span data-stu-id="92cd4-108">Before deploying a new update to your organization, verify that it functions correctly on a test device.</span></span>



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a><span data-ttu-id="92cd4-109">若要查看 UC 裝置的軟體更新</span><span class="sxs-lookup"><span data-stu-id="92cd4-109">To view software updates for UC devices</span></span>

1.  <span data-ttu-id="92cd4-110">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="92cd4-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="92cd4-111">從 Microsoft 支援網站[http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)，將 .cab 檔案下載至 Lync Server 2013 電腦上的位置（例如，C：\\Updates\\UCUpdates）。</span><span class="sxs-lookup"><span data-stu-id="92cd4-111">From the Microsoft Support website at [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091), download the .cab file to a location on a Lync Server 2013 computer (for example, C:\\Updates\\UCUpdates.cab).</span></span>

3.  <span data-ttu-id="92cd4-112">執行下列其中一個 Cmdlet，從 C：\\Updates\\UCUpdates .cab 檔案匯入裝置更新規則：</span><span class="sxs-lookup"><span data-stu-id="92cd4-112">Import the device update rules from the C:\\Updates\\UCUpdates.cab file by running one of the following cmdlets:</span></span>
    
      - <span data-ttu-id="92cd4-113">如果 .cab 檔案所在的電腦與執行要更新之服務的同一台電腦（服務：雷德蒙-websvc-2），請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="92cd4-113">If the .cab file is located on the same computer as the one running the service to be updated (service:Redmond-websvc-2), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - <span data-ttu-id="92cd4-114">如果 .cab 檔案所在的電腦不同于執行要更新的服務的電腦（服務：雷德蒙-websvc-3），請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="92cd4-114">If the .cab file is located on a different computer than the one running the service to be updated (service:Redmond-websvc-3), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  <span data-ttu-id="92cd4-115">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="92cd4-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="92cd4-116">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="92cd4-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

5.  <span data-ttu-id="92cd4-117">在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**裝置更新**]。</span><span class="sxs-lookup"><span data-stu-id="92cd4-117">In the left navigation bar, click **Clients**, and then click **Device Update**.</span></span>

6.  <span data-ttu-id="92cd4-118">在 [**裝置更新**] 頁面上，按一下清單中的更新，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="92cd4-118">On the **Device Update** page, click an update in the list, and then do one of the following:</span></span>
    
      - <span data-ttu-id="92cd4-119">**解除擱置中的更新。**</span><span class="sxs-lookup"><span data-stu-id="92cd4-119">**Cancel a pending update.**</span></span> <span data-ttu-id="92cd4-120">若要防止選取的更新部署到貴組織的裝置，請按一下 [**動作**] 功能表，然後按一下 [**解除擱置更新**]。</span><span class="sxs-lookup"><span data-stu-id="92cd4-120">To prevent the selected update from being deployed to your organization’s devices, click the **Action** menu, and then click **Cancel pending updates**.</span></span>
    
      - <span data-ttu-id="92cd4-121">**核准更新。**</span><span class="sxs-lookup"><span data-stu-id="92cd4-121">**Approve an update.**</span></span> <span data-ttu-id="92cd4-122">若要允許將所選的更新部署到貴組織的裝置，請按一下 [**動作**] 功能表，然後按一下 [**核准**]。</span><span class="sxs-lookup"><span data-stu-id="92cd4-122">To allow the selected update to be deployed to your organization’s devices, click the **Action** menu, and then click **Approve**.</span></span>
    
      - <span data-ttu-id="92cd4-123">**還原更新。**</span><span class="sxs-lookup"><span data-stu-id="92cd4-123">**Restore an update.**</span></span> <span data-ttu-id="92cd4-124">若要允許先前核准的更新部署到貴組織的裝置，請按一下 [**動作**] 功能表，然後按一下 [**還原**]。</span><span class="sxs-lookup"><span data-stu-id="92cd4-124">To allow a previously approved update to be deployed to your organization’s devices, click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="92cd4-125">請參閱</span><span class="sxs-lookup"><span data-stu-id="92cd4-125">See Also</span></span>


[<span data-ttu-id="92cd4-126">在 Lync Server 2013 中管理裝置、電話及用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="92cd4-126">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

