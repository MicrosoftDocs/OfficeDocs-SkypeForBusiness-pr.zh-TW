---
title: Lync Server 2013：查看裝置更新規則的相關資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d873cbd80e599313b60a57cfc28eb9752d85ef66
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a><span data-ttu-id="ebe8c-102">在 Lync Server 2013 中查看裝置更新規則的相關資訊</span><span class="sxs-lookup"><span data-stu-id="ebe8c-102">View information about Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebe8c-103">_**主題上次修改日期：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="ebe8c-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="ebe8c-104">查看已匯入的裝置更新規則的詳細資料，包括更新適用的裝置類型、模型和品牌;更新版本與類型;以及更新的區域設定和池子。</span><span class="sxs-lookup"><span data-stu-id="ebe8c-104">View details about device update rules that have already been imported, including the type, model, and brand of devices the update applies to; version and type of update; and locale and pool for the update.</span></span> <span data-ttu-id="ebe8c-105">所有已匯入的裝置更新規則（待定核准、部署（核准）、撤回（復原），以及您決定不使用（重設）的資訊都能使用。</span><span class="sxs-lookup"><span data-stu-id="ebe8c-105">Information is available for all imported device update rules—those that are pending approval, deployed (approved), recalled (restored), and those you’ve decided not to use (reset).</span></span> <span data-ttu-id="ebe8c-106">從 Lync Server [控制台] 或 [Windows PowerShell] 存取這項資訊。</span><span class="sxs-lookup"><span data-stu-id="ebe8c-106">Access this information from either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ebe8c-107">如需如何匯入、核准、重設、還原及移除規則的詳細資料，請參閱<A href="lync-server-2013-device-update-rules.md">Lync Server 2013 中的裝置更新規則</A>所列的主題。</span><span class="sxs-lookup"><span data-stu-id="ebe8c-107">For details about how to import, approve, reset, restore, and remove rules, see the topics listed at <A href="lync-server-2013-device-update-rules.md">Device Update rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="ebe8c-108">使用 Lync Server [控制台] 來查看裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="ebe8c-108">To view device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="ebe8c-109">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="ebe8c-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ebe8c-110">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="ebe8c-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ebe8c-111">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="ebe8c-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ebe8c-112">在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**裝置更新**] 瀏覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="ebe8c-112">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span> <span data-ttu-id="ebe8c-113">已匯入的規則會列在 [**裝置更新**] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="ebe8c-113">Imported rules are listed on the **Device Update** page.</span></span>

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ebe8c-114">使用 Windows PowerShell Cmdlet 來查看裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="ebe8c-114">Viewing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ebe8c-115">您也可以使用 Windows PowerShell 和**CsDeviceUpdateRule** Cmdlet 來查看所有裝置更新規則的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ebe8c-115">Detailed information about all your device update rules can also be viewed by using Windows PowerShell and the **Get-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="ebe8c-116">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="ebe8c-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ebe8c-117">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。</span><span class="sxs-lookup"><span data-stu-id="ebe8c-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a><span data-ttu-id="ebe8c-118">若要查看您所有的裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="ebe8c-118">To view all your device update rules</span></span>

  - <span data-ttu-id="ebe8c-119">下列命令會傳回所有裝置更新規則的相關資訊，這些規則已設定為在您的組織中使用：</span><span class="sxs-lookup"><span data-stu-id="ebe8c-119">The following command returns information about all the device updates rules configured for use in your organization:</span></span>
    
        Get-CsDeviceUpdateRule
    
    <span data-ttu-id="ebe8c-120">此命令會針對您的每個裝置更新規則傳回類似下列的資訊：</span><span class="sxs-lookup"><span data-stu-id="ebe8c-120">The command returns information similar to the following for each of your device update rules:</span></span>
    
        Identity        : Service:WebServer:pool0.vdomain.com/2de8cbf6-9441-4f61-b755-1e4bef1effde
        Id              : 2de8cbf6-9441-4f61-b755-1e4bef1effde
        DeviceType      : UCPhone
        Brand           : Microsoft
        Model           : CPE
        Revision        : A
        Locale          : ENU
        UpdateType      : CPE
        ApprovedVersion :
        RestoreVersion  :
        PendingVersion  : 4.0.7577.4066

</div>

<div>

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a><span data-ttu-id="ebe8c-121">若要在特定的 web 伺服器上查看所有裝置更新規則</span><span class="sxs-lookup"><span data-stu-id="ebe8c-121">To view all the device update rules on a specific web server</span></span>

  - <span data-ttu-id="ebe8c-122">若要在特定電腦上查看裝置更新規則，請使用篩選參數，後面接著伺服器身分識別和萬用字元（\*）。</span><span class="sxs-lookup"><span data-stu-id="ebe8c-122">To view the device update rules on a specific computer, use the Filter parameter followed by the server Identity and the wildcard character (\*).</span></span> <span data-ttu-id="ebe8c-123">例如：</span><span class="sxs-lookup"><span data-stu-id="ebe8c-123">For example:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

<span data-ttu-id="ebe8c-124">如需詳細資訊，請參閱[CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="ebe8c-124">For details, see the Help topic for the [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

