---
title: Lync Server 2013：核准裝置更新規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Approve a Device Update rule
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994053(v=OCS.15)
ms:contentKeyID: 51803964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd5112f4be1f6c192d78d3b87b21094c2b04c4df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504911"
---
# <a name="approve-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="9a848-102">核准 Lync Server 2013 中的裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="9a848-102">Approve a Device Update rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a848-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9a848-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9a848-104">在您匯入裝置更新規則之後，它會安裝在測試裝置上。</span><span class="sxs-lookup"><span data-stu-id="9a848-104">After you import a device update rule, it’s installed on your test devices.</span></span> <span data-ttu-id="9a848-105">如果測試成功，且想要向組織推出更新，請使用 Lync Server 控制台或 Windows PowerShell 進行核准。</span><span class="sxs-lookup"><span data-stu-id="9a848-105">If your testing is successful, and you want to roll out the update to your organization, approve it by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="9a848-106">使用 Lync Server 控制台核准裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="9a848-106">To approve a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9a848-107">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="9a848-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9a848-108">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="9a848-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9a848-109">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="9a848-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9a848-110">在 [ **裝置更新** ] 頁面上，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="9a848-110">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="9a848-111">若要核准一個規則，請選取該規則。</span><span class="sxs-lookup"><span data-stu-id="9a848-111">To approve one rule, select that rule.</span></span>
    
      - <span data-ttu-id="9a848-112">若要核准所有規則，請按一下 [ **編輯**]，然後按一下 [ **全選**]。</span><span class="sxs-lookup"><span data-stu-id="9a848-112">To approve all rules, click **Edit**, and then click **Select All**.</span></span>

4.  <span data-ttu-id="9a848-113">按一下 [ **動作**]，然後按一下 [ **核准**]。</span><span class="sxs-lookup"><span data-stu-id="9a848-113">Click **Action**, and then click **Approve**.</span></span>

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9a848-114">使用 Windows PowerShell Cmdlet 核准裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="9a848-114">Approving a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9a848-115">您也可以使用 Windows PowerShell 和 **核准-CsDeviceUpdateRule 指令程式** 來核准裝置更新規則。</span><span class="sxs-lookup"><span data-stu-id="9a848-115">Device update rules can also be approved by using Windows PowerShell and the **Approve-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="9a848-116">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9a848-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9a848-117">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。</span><span class="sxs-lookup"><span data-stu-id="9a848-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a><span data-ttu-id="9a848-118">核准單一裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="9a848-118">To approve a single device update rule</span></span>

  - <span data-ttu-id="9a848-119">下列命令會核准在網頁伺服器上上找到的裝置更新規則 d5ce3c10-2588-420a-82ac-dc2d9b1222ff9-82ac-atl-cs-001.litwareinc.com：</span><span class="sxs-lookup"><span data-stu-id="9a848-119">The following command approves the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 found on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a><span data-ttu-id="9a848-120">核准多個裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="9a848-120">To approve multiple device update rules</span></span>

  - <span data-ttu-id="9a848-121">此命令會核准 Microsoft 署名裝置的所有裝置更新規則：</span><span class="sxs-lookup"><span data-stu-id="9a848-121">This command approves all the device update rules for Microsoft-branded devices:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

<span data-ttu-id="9a848-122">如需詳細資訊，請參閱 [CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="9a848-122">For details, see the Help topic for the [Approve-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9a848-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9a848-123">See Also</span></span>


[<span data-ttu-id="9a848-124">在 Lync Server 2013 中匯入裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="9a848-124">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)  
[<span data-ttu-id="9a848-125">在 Lync Server 2013 中還原裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="9a848-125">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

