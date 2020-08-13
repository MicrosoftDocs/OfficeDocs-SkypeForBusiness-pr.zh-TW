---
title: Lync Server 2013：查看撥號對應表資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View dial plan information
ms:assetid: 25ed0112-a8a7-418a-8c2c-580081be692a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687997(v=OCS.15)
ms:contentKeyID: 49733587
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a4b668291c0e8ba5c402f17288bebe342ccceb1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-dial-plan-information-in-lync-server-2013"></a><span data-ttu-id="f995c-102">在 Lync Server 2013 中查看撥號對應表資訊</span><span class="sxs-lookup"><span data-stu-id="f995c-102">View dial plan information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f995c-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f995c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f995c-104">若要查看現有撥號對應表的資訊，請執行下列程式中的步驟。</span><span class="sxs-lookup"><span data-stu-id="f995c-104">To view information for an existing dial plan, perform the steps in the following procedure.</span></span> <span data-ttu-id="f995c-105">如果您想要建立新的撥號對應表，請參閱 [在 Lync Server 2013 中建立撥號](lync-server-2013-create-a-dial-plan.md)對應表。</span><span class="sxs-lookup"><span data-stu-id="f995c-105">If you want to create a new dial plan, see [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md).</span></span>

<div>

## <a name="to-view-information-about-a-dial-plan-from-lync-server-control-panel"></a><span data-ttu-id="f995c-106">從 Lync Server 控制台查看撥號對應表的相關資訊</span><span class="sxs-lookup"><span data-stu-id="f995c-106">To view information about a dial plan from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f995c-107">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="f995c-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="f995c-108">如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="f995c-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f995c-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="f995c-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f995c-110">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="f995c-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f995c-111">在左導覽列中，依序按一下 [語音路由]\*\*\*\* 和 [撥號對應表]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f995c-111">In the left navigation bar, click **Voice Routing** and then click **Dial Plan**.</span></span>

4.  <span data-ttu-id="f995c-112">在 [撥號對應表]\*\*\*\* 頁面上，按兩下撥號對應表名稱。</span><span class="sxs-lookup"><span data-stu-id="f995c-112">On the **Dial Plan** page, double-click a dial plan name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f995c-113">您一次僅可檢視一個撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="f995c-113">You can view information for only one dial plan at a time.</span></span>

    
    </div>

</div>

<div>

## <a name="to-view-dial-plans-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f995c-114">使用 Windows PowerShell Cmdlet 來查看撥號對應表</span><span class="sxs-lookup"><span data-stu-id="f995c-114">To view dial plans by using Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="f995c-115">您可以使用 Windows PowerShell 命令列介面及 **Get-CsDialPlan** Cmdlet 來查看撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="f995c-115">Dial plans can be viewed by using the Windows PowerShell command-line interface and the **Get-CsDialPlan** cmdlet.</span></span> <span data-ttu-id="f995c-116">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f995c-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f995c-117">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="f995c-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="f995c-118">若要查看所有撥號對應表的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="f995c-118">To view information about all your dial plans, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsDialPlan
    
    <span data-ttu-id="f995c-119">該命令會傳回與下面類似的資訊：</span><span class="sxs-lookup"><span data-stu-id="f995c-119">That command will return information similar to this:</span></span>
    
        Identity                 : Global
        Description              :
        DialinConferencingRegion :
        NormalizationRules       : {Description=;
                                   Pattern=^(\d+)$;Translation=$1;Name=
                                   KeepAll;IsInternalExtension=False}
        CountryCode              :
        State                    :
        City                     :
        ExternalAccessPrefix     :
        SimpleName               : DefaultProfile
        OptimizeDeviceDialing    : False

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f995c-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f995c-120">See Also</span></span>


[<span data-ttu-id="f995c-121">在 Lync Server 2013 中建立撥號對應表</span><span class="sxs-lookup"><span data-stu-id="f995c-121">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="f995c-122">在 Lync Server 2013 中修改撥號對應表</span><span class="sxs-lookup"><span data-stu-id="f995c-122">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

