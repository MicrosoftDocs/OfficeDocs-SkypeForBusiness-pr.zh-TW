---
title: Lync Server 2013：重設裝置更新規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reset a Device Update rule
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994069(v=OCS.15)
ms:contentKeyID: 51803980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab03c5c28db28ddbd883f3f50845eaf91d4fd1a9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="ae005-102">在 Lync Server 2013 中重設裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="ae005-102">Reset a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae005-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="ae005-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="ae005-104">如果您不喜歡更新在測試裝置上的運作方式，您可以重設裝置更新規則，移除規則的擱置狀態，並從測試裝置中卸載更新。</span><span class="sxs-lookup"><span data-stu-id="ae005-104">If you don’t like the way that an update works on your test devices, you can reset the device update rule, which removes the rule’s pending status and uninstalls the update from the test devices.</span></span>

<span data-ttu-id="ae005-105">您可以使用 Lync Server [控制台] 或 [Windows PowerShell] 移除裝置更新規則。</span><span class="sxs-lookup"><span data-stu-id="ae005-105">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ae005-106">若要卸載您已核准（也就是已推出）的規則，請將它還原。</span><span class="sxs-lookup"><span data-stu-id="ae005-106">To uninstall a rule that you’ve already approved (that is, rolled out), restore it.</span></span> <span data-ttu-id="ae005-107">如需詳細資訊，請參閱<A href="lync-server-2013-restore-a-device-update-rule.md">在 Lync Server 2013 中還原裝置更新規則</A>。</span><span class="sxs-lookup"><span data-stu-id="ae005-107">For details, see <A href="lync-server-2013-restore-a-device-update-rule.md">Restore a Device Update rule in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="ae005-108">使用 Lync Server [控制台] 重設裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="ae005-108">To reset a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="ae005-109">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="ae005-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ae005-110">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="ae005-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ae005-111">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="ae005-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ae005-112">在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**裝置更新**] 瀏覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="ae005-112">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="ae005-113">在 [**裝置更新**] 頁面上，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="ae005-113">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="ae005-114">若要重設一個規則，請選取您要重設的規則。</span><span class="sxs-lookup"><span data-stu-id="ae005-114">To reset one rule, select the rule you want to reset.</span></span>
    
      - <span data-ttu-id="ae005-115">若要重設所有規則，請在 [**編輯**] 功能表上，按一下 [**全選**]。</span><span class="sxs-lookup"><span data-stu-id="ae005-115">To reset all rules, on the **Edit** menu, click **Select All**.</span></span>
    
      - <span data-ttu-id="ae005-116">若要重設一個品牌的所有規則，請使用 [**品牌**] 欄功能表。</span><span class="sxs-lookup"><span data-stu-id="ae005-116">To reset all rules for one brand, use the **Brand** column menu.</span></span>

5.  <span data-ttu-id="ae005-117">按一下 [**動作**]，然後按一下 [**解除擱置更新**]。</span><span class="sxs-lookup"><span data-stu-id="ae005-117">Click **Action**, and then click **Cancel pending updates**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="ae005-118">如果您確信不想要推出已取消的裝置更新規則，您可能會想要將它們刪除。</span><span class="sxs-lookup"><span data-stu-id="ae005-118">If you’re sure you’ll never want to roll out the device update rule(s) that you cancelled, you might want to delete them.</span></span> <span data-ttu-id="ae005-119">如需詳細資訊，請參閱<A href="lync-server-2013-remove-a-device-update-rule.md">在 Lync Server 2013 中移除裝置更新規則</A>。</span><span class="sxs-lookup"><span data-stu-id="ae005-119">For details, see <A href="lync-server-2013-remove-a-device-update-rule.md">Remove a Device Update rule in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ae005-120">使用 Windows PowerShell Cmdlet 來重設裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="ae005-120">Resetting a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ae005-121">您也可以使用 Windows PowerShell 和**Reset CsDeviceUpdateRule** Cmdlet 來重設裝置更新規則。</span><span class="sxs-lookup"><span data-stu-id="ae005-121">Device update rules can also be reset by using Windows PowerShell and the **Reset-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="ae005-122">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="ae005-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ae005-123">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。</span><span class="sxs-lookup"><span data-stu-id="ae005-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a><span data-ttu-id="ae005-124">在伺服器上重設特定裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="ae005-124">To reset a specific device update rule on a server</span></span>

  - <span data-ttu-id="ae005-125">下列命令會在 Web 服務器 dc2d9b1222ff9 上重設裝置更新規則 d5ce3c10-2588-420a-82ac-atl-cs-001.litwareinc.com：</span><span class="sxs-lookup"><span data-stu-id="ae005-125">The following command resets the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a><span data-ttu-id="ae005-126">若要重設伺服器上的所有裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="ae005-126">To reset all the device update rules on a server</span></span>

  - <span data-ttu-id="ae005-127">這個命令會在 Web 服務器 atl-cs-001.litwareinc.com 上重設所有裝置更新規則：</span><span class="sxs-lookup"><span data-stu-id="ae005-127">This command resets all the device update rules on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a><span data-ttu-id="ae005-128">若要重設所有具有特定品牌的裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="ae005-128">To reset all the device updates rules that have a specific brand</span></span>

  - <span data-ttu-id="ae005-129">在這個範例中，將會重設在整個組織中與 Microsoft 品牌相同的所有裝置更新：</span><span class="sxs-lookup"><span data-stu-id="ae005-129">In this example, all the device updates throughout the organization that have a Brand equal to Microsoft are reset:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

<span data-ttu-id="ae005-130">如需詳細資訊，請參閱[Reset CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="ae005-130">For details, see the Help topic for the [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ae005-131">請參閱</span><span class="sxs-lookup"><span data-stu-id="ae005-131">See Also</span></span>


[<span data-ttu-id="ae005-132">在 Lync Server 2013 中核准裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="ae005-132">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

