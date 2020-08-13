---
title: Lync Server 2013：移除裝置更新規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13b639e6541478874e80ab632b2ee231ea65151d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="bf679-102">在 Lync Server 2013 中移除裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="bf679-102">Remove a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf679-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="bf679-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="bf679-104">移除裝置更新規則會將其永久移出裝置更新佇列。</span><span class="sxs-lookup"><span data-stu-id="bf679-104">Removing a device update rule takes it permanently out of the device update queue.</span></span>

<span data-ttu-id="bf679-105">移除規則與從您部署中的裝置卸載或從測試裝置卸載的更新不同。</span><span class="sxs-lookup"><span data-stu-id="bf679-105">Removing a rule is different from uninstalling an update from the devices in your deployment or from your test devices.</span></span> <span data-ttu-id="bf679-106">若要從您的部署卸載已核准的更新，請 *還原* 裝置更新規則。</span><span class="sxs-lookup"><span data-stu-id="bf679-106">To uninstall an approved update from your deployment, you *restore* the device update rule.</span></span> <span data-ttu-id="bf679-107">如需詳細資訊，請參閱 [Restore a Device Update rule In Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md)。</span><span class="sxs-lookup"><span data-stu-id="bf679-107">For details, see [Restore a Device Update rule in Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md).</span></span> <span data-ttu-id="bf679-108">若要卸載尚未從測試裝置核准的更新，請將其 *重設* 。</span><span class="sxs-lookup"><span data-stu-id="bf679-108">To uninstall an update you haven’t approved from your test devices, you *reset* it.</span></span> <span data-ttu-id="bf679-109">如需詳細資訊，請參閱 [Reset a Device Update rule In Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md)。</span><span class="sxs-lookup"><span data-stu-id="bf679-109">For details, see [Reset a Device Update rule in Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).</span></span>

<span data-ttu-id="bf679-110">您可以使用 Lync Server 控制台或 Windows PowerShell 移除裝置更新規則。</span><span class="sxs-lookup"><span data-stu-id="bf679-110">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="bf679-111">使用 Lync Server 控制台移除裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="bf679-111">To remove device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="bf679-112">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="bf679-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bf679-113">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="bf679-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bf679-114">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="bf679-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bf679-115">在左導覽列中，按一下 [ **用戶端**]，然後按一下 [ **裝置更新** ] 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="bf679-115">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="bf679-116">在 [ **裝置更新** ] 頁面上，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="bf679-116">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="bf679-117">若要移除一個規則，請選取您要刪除的規則。</span><span class="sxs-lookup"><span data-stu-id="bf679-117">To remove one rule, select the rule you want to delete.</span></span>
    
      - <span data-ttu-id="bf679-118">若要移除所有規則，請按一下 [ **編輯** ] 功能表，然後按一下 [ **全選**]。</span><span class="sxs-lookup"><span data-stu-id="bf679-118">To remove all rules, click the **Edit** menu, and then click **Select All**.</span></span>

5.  <span data-ttu-id="bf679-119">按一下 [ **編輯**]，然後按一下 [ **刪除**]。</span><span class="sxs-lookup"><span data-stu-id="bf679-119">Click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bf679-120">使用 Windows PowerShell Cmdlet 移除裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="bf679-120">Removing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="bf679-121">您也可以使用 Windows PowerShell 和 **CsDeviceUpdateRule** Cmdlet 來移除裝置更新規則。</span><span class="sxs-lookup"><span data-stu-id="bf679-121">Device update rules can also be removed by using Windows PowerShell and the **Remove-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="bf679-122">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bf679-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bf679-123">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="bf679-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a><span data-ttu-id="bf679-124">從伺服器移除單一裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="bf679-124">To remove a single device update rule from a server</span></span>

  - <span data-ttu-id="bf679-125">下列命令會從上上的網頁伺服器中移除裝置更新規則 d5ce3c10-2588-420a-82ac-dc2d9b1222ff9-82ac-atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="bf679-125">The following command removes the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 from the Web server on atl-cs-001.litwareinc.com.</span></span>
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a><span data-ttu-id="bf679-126">從伺服器移除所有裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="bf679-126">To remove all the device update rules from a server</span></span>

  - <span data-ttu-id="bf679-127">此命令會從 atl-cs-001.litwareinc.com 上的網頁伺服器中移除所有裝置更新規則。</span><span class="sxs-lookup"><span data-stu-id="bf679-127">This command removes all the device update rules from the web server on atl-cs-001.litwareinc.com.</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

<span data-ttu-id="bf679-128">如需詳細資訊，請參閱 [CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="bf679-128">For details, see the Help topic for the [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bf679-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bf679-129">See Also</span></span>


[<span data-ttu-id="bf679-130">核准 Lync Server 2013 中的裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="bf679-130">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

