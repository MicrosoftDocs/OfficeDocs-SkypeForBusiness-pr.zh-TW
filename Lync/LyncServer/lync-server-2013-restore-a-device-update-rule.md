---
title: Lync Server 2013：還原裝置更新規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restore a Device Update rule
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994061(v=OCS.15)
ms:contentKeyID: 51803972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ca4874e7ec0ae462be7360ad62e18cfbdcf018
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restore-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="9ca98-102">在 Lync Server 2013 中還原裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="9ca98-102">Restore a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ca98-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9ca98-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9ca98-104">若要從部署中的裝置卸載裝置更新規則，請將其還原。</span><span class="sxs-lookup"><span data-stu-id="9ca98-104">To uninstall a device update rule from the devices in your deployment, restore it.</span></span> <span data-ttu-id="9ca98-105">還原裝置更新規則會同時卸載此更新，並重新安裝該規則的先前版本。</span><span class="sxs-lookup"><span data-stu-id="9ca98-105">Restoring a device update rule both uninstalls the update and reinstalls the previous version of that rule.</span></span>

<span data-ttu-id="9ca98-106">您可以使用 Lync Server 控制台或 Windows PowerShell 還原裝置更新規則。</span><span class="sxs-lookup"><span data-stu-id="9ca98-106">You can restore a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-restore-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="9ca98-107">使用 Lync Server 控制台還原裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="9ca98-107">To restore device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9ca98-108">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="9ca98-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9ca98-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="9ca98-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9ca98-110">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="9ca98-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9ca98-111">在左導覽列中，按一下 [**用戶端**]，然後按一下 [**裝置更新**] 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="9ca98-111">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="9ca98-112">在 [**裝置更新**] 頁面上，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="9ca98-112">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="9ca98-113">若要還原一個規則，請選取該規則。</span><span class="sxs-lookup"><span data-stu-id="9ca98-113">To restore one rule, select that rule.</span></span>
    
      - <span data-ttu-id="9ca98-114">若要還原所有規則，請按一下 [**編輯**]，然後按一下 [**全選**]。</span><span class="sxs-lookup"><span data-stu-id="9ca98-114">To restore all rules, click **Edit**, and then click **Select All**.</span></span>

5.  <span data-ttu-id="9ca98-115">按一下 [**動作**] 功能表，然後按一下 [**還原**]。</span><span class="sxs-lookup"><span data-stu-id="9ca98-115">Click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="restoring-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9ca98-116">使用 Windows PowerShell Cmdlet 還原裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="9ca98-116">Restoring Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9ca98-117">您也可以使用 Windows PowerShell 和**CsDeviceUpdateRule** Cmdlet 來還原裝置更新規則。</span><span class="sxs-lookup"><span data-stu-id="9ca98-117">Device updates rules can also be restored by using Windows PowerShell and the **Restore-CsDeviceUpdateRule** cmdlet..</span></span> <span data-ttu-id="9ca98-118">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9ca98-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9ca98-119">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。</span><span class="sxs-lookup"><span data-stu-id="9ca98-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-restore-a-single-device-update-rule-on-a-server"></a><span data-ttu-id="9ca98-120">在伺服器上還原單一裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="9ca98-120">To restore a single device update rule on a server</span></span>

  - <span data-ttu-id="9ca98-121">下列命令會在網頁伺服器上上還原裝置更新規則 d5ce3c10-2588-420a-82ac-dc2d9b1222ff9-82ac-atl-cs-001.litwareinc.com：</span><span class="sxs-lookup"><span data-stu-id="9ca98-121">The following command restores the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-restore-all-the-device-update-rules-on-a-server"></a><span data-ttu-id="9ca98-122">在伺服器上還原所有裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="9ca98-122">To restore all the device update rules on a server</span></span>

  - <span data-ttu-id="9ca98-123">這個命令會還原網頁伺服器 atl-cs-001.litwareinc.com 上的所有裝置更新規則：</span><span class="sxs-lookup"><span data-stu-id="9ca98-123">This command restores all the device update rules on the web server atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

</div>

<span data-ttu-id="9ca98-124">如需詳細資訊，請參閱[CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="9ca98-124">For details, see the Help topic for the [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

