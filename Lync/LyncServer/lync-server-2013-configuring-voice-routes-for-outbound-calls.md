---
title: Lync Server 2013：設定撥出電話的語音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice routes for outbound calls
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48183875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a697dae1be3d59692746303f230968782db4f38f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a><span data-ttu-id="aa6b0-102">在 Lync Server 2013 中設定撥出電話的語音路由</span><span class="sxs-lookup"><span data-stu-id="aa6b0-102">Configuring voice routes for outbound calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa6b0-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="aa6b0-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="aa6b0-104">Lync Server 2013 語音路由會將目的地電話號碼與一或多個公用交換電話網路 (PSTN) 閘道或 SIP 主幹及一個或多個 PSTN 使用方式記錄產生關聯。</span><span class="sxs-lookup"><span data-stu-id="aa6b0-104">A Lync Server 2013 voice route associates destination phone numbers with one or more public switched telephone network (PSTN) gateways or SIP trunks and one or more PSTN usage records.</span></span>

<span data-ttu-id="aa6b0-105">**使用 Lync Server 控制台來查看語音路由**</span><span class="sxs-lookup"><span data-stu-id="aa6b0-105">**To view voice routes by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="aa6b0-106">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="aa6b0-106">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="aa6b0-107">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="aa6b0-107">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="aa6b0-108">按一下 **[語音路由]**。</span><span class="sxs-lookup"><span data-stu-id="aa6b0-108">Click **Voice Routing**.</span></span>

3.  <span data-ttu-id="aa6b0-109">按一下 **[路由]**。</span><span class="sxs-lookup"><span data-stu-id="aa6b0-109">Click **Route**.</span></span>

4.  <span data-ttu-id="aa6b0-p102">從語音路由清單中按兩下語音路由，即可檢視其他屬性，或選取路由，按一下 **[編輯]**，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="aa6b0-p102">Double-click a voice route to view additional properties from the list of voice routes, or select the route and click **Edit**. Then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aa6b0-112">每次僅可檢視單一路由的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="aa6b0-112">You can only view detailed information for a single route at a time.</span></span>

    
    </div>

<span data-ttu-id="aa6b0-113">**使用 Windows PowerShell 查看語音路由**</span><span class="sxs-lookup"><span data-stu-id="aa6b0-113">**To view voice routes by using Windows PowerShell**</span></span>

  - <span data-ttu-id="aa6b0-114">啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="aa6b0-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="aa6b0-115">您可以使用 Windows PowerShell 和**Get-CsVoiceRoute** Cmdlet 來查看語音路由。</span><span class="sxs-lookup"><span data-stu-id="aa6b0-115">Voice routes can be viewed by using Windows PowerShell and the **Get-CsVoiceRoute** cmdlet.</span></span> <span data-ttu-id="aa6b0-116">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aa6b0-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="aa6b0-117">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="aa6b0-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="aa6b0-118">若要查看所有語音路由的資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="aa6b0-118">To view information about all of your voice routes, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsVoiceRoute
    
    <span data-ttu-id="aa6b0-119">如此將傳回類似如下的資訊：</span><span class="sxs-lookup"><span data-stu-id="aa6b0-119">That will return information similar to this:</span></span>
    
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
> <span data-ttu-id="aa6b0-120">如需詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-voice-routes.md">Lync Server 2013 中的語音路由</A>。</span><span class="sxs-lookup"><span data-stu-id="aa6b0-120">For details, see <A href="lync-server-2013-voice-routes.md">Voice routes in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="aa6b0-121">本章節內容</span><span class="sxs-lookup"><span data-stu-id="aa6b0-121">In This Section</span></span>

  - [<span data-ttu-id="aa6b0-122">在 Lync Server 2013 中建立語音路由</span><span class="sxs-lookup"><span data-stu-id="aa6b0-122">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)

  - [<span data-ttu-id="aa6b0-123">在 Lync Server 2013 中修改語音路由</span><span class="sxs-lookup"><span data-stu-id="aa6b0-123">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aa6b0-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="aa6b0-124">See Also</span></span>


[<span data-ttu-id="aa6b0-125">在 Lync Server 2013 中管理語音路由</span><span class="sxs-lookup"><span data-stu-id="aa6b0-125">Managing voice routing in Lync Server 2013</span></span>](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

