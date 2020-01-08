---
title: Lync Server 2013：設定撥出電話的語音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring voice routes for outbound calls
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48183875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e91525f5d35110560b28059f774be8d2cb5df6d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a><span data-ttu-id="96705-102">Lync Server 2013 中設定撥出電話的語音路由</span><span class="sxs-lookup"><span data-stu-id="96705-102">Configuring voice routes for outbound calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96705-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="96705-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="96705-104">Lync Server 2013 語音路由會將目的地電話號碼與一或多個公開交換電話網絡（PSTN）閘道或 SIP trunks 及一或多個 PSTN 使用量記錄建立關聯。</span><span class="sxs-lookup"><span data-stu-id="96705-104">A Lync Server 2013 voice route associates destination phone numbers with one or more public switched telephone network (PSTN) gateways or SIP trunks and one or more PSTN usage records.</span></span>

<span data-ttu-id="96705-105">**使用 Lync Server [控制台] 來查看語音路由**</span><span class="sxs-lookup"><span data-stu-id="96705-105">**To view voice routes by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="96705-106">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="96705-106">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="96705-107">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="96705-107">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="96705-108">按一下 [**語音路由**]。</span><span class="sxs-lookup"><span data-stu-id="96705-108">Click **Voice Routing**.</span></span>

3.  <span data-ttu-id="96705-109">按一下 [**傳送**]。</span><span class="sxs-lookup"><span data-stu-id="96705-109">Click **Route**.</span></span>

4.  <span data-ttu-id="96705-110">按兩下語音路線以從語音路由清單中查看其他屬性，或選取路線，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="96705-110">Double-click a voice route to view additional properties from the list of voice routes, or select the route and click **Edit**.</span></span> <span data-ttu-id="96705-111">然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="96705-111">Then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="96705-112">您一次只能查看單一路線的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="96705-112">You can only view detailed information for a single route at a time.</span></span>

    
    </div>

<span data-ttu-id="96705-113">**使用 Windows PowerShell 來查看語音路由**</span><span class="sxs-lookup"><span data-stu-id="96705-113">**To view voice routes by using Windows PowerShell**</span></span>

  - <span data-ttu-id="96705-114">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="96705-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="96705-115">您可以使用 Windows PowerShell 和**CsVoiceRoute** Cmdlet 來查看語音路由。</span><span class="sxs-lookup"><span data-stu-id="96705-115">Voice routes can be viewed by using Windows PowerShell and the **Get-CsVoiceRoute** cmdlet.</span></span> <span data-ttu-id="96705-116">這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。</span><span class="sxs-lookup"><span data-stu-id="96705-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="96705-117">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="96705-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="96705-118">若要查看所有語音路由的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="96705-118">To view information about all of your voice routes, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsVoiceRoute
    
    <span data-ttu-id="96705-119">這會傳回如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="96705-119">That will return information similar to this:</span></span>
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :

<div>


> [!NOTE]  
> <span data-ttu-id="96705-120">如需詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-voice-routes.md">Lync Server 2013 中的語音路由</A>。</span><span class="sxs-lookup"><span data-stu-id="96705-120">For details, see <A href="lync-server-2013-voice-routes.md">Voice routes in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="96705-121">本節內容</span><span class="sxs-lookup"><span data-stu-id="96705-121">In This Section</span></span>

  - [<span data-ttu-id="96705-122">在 Lync Server 2013 中建立語音路由</span><span class="sxs-lookup"><span data-stu-id="96705-122">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)

  - [<span data-ttu-id="96705-123">在 Lync Server 2013 中修改語音路線</span><span class="sxs-lookup"><span data-stu-id="96705-123">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="96705-124">請參閱</span><span class="sxs-lookup"><span data-stu-id="96705-124">See Also</span></span>


[<span data-ttu-id="96705-125">在 Lync Server 2013 中管理語音路由</span><span class="sxs-lookup"><span data-stu-id="96705-125">Managing voice routing in Lync Server 2013</span></span>](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

