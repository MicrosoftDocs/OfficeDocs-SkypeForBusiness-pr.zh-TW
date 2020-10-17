---
title: 刪除現有的 A/V 邊際伺服器設定集合集合
description: 刪除現有的 A/V Edge Server 設定的集合。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of A/V Edge Server configuration settings
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49733673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7fe444e8bcb7e7e8e2633e59c23aeb2e80e9b98
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553619"
---
# <a name="delete-an-existing-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="3ea5a-103">在 Lync Server 2013 中刪除現有的 A/V Edge Server 設定集合集合</span><span class="sxs-lookup"><span data-stu-id="3ea5a-103">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ea5a-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3ea5a-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3ea5a-p101">A/V Edge 服務可讓內部使用者 (即已登入您組織網路的使用者) 將音訊和視訊共用給外部使用者 (即未登入您組織網路的使用者)。此服務主要是採用 A/V Edge 組態設定管理，可以在網站範圍或服務範圍裡完成這些設定 (亦即可以針對個別 A/V Edge 伺服器進行設定)。</span><span class="sxs-lookup"><span data-stu-id="3ea5a-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="3ea5a-107">當您安裝 Lync Server 時，系統會為您建立全域 A/V Edge 設定的集合。</span><span class="sxs-lookup"><span data-stu-id="3ea5a-107">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="3ea5a-108">無法刪除此全域集合。</span><span class="sxs-lookup"><span data-stu-id="3ea5a-108">This global collection cannot be deleted.</span></span> <span data-ttu-id="3ea5a-109">不過，您可以使用 Windows PowerShell 和 Remove-CsAVEdgeConfiguration Cmdlet 「重設」全域集合;這只是表示全域集合中的所有屬性值都會重設為其預設值。</span><span class="sxs-lookup"><span data-stu-id="3ea5a-109">However, you can use the Windows PowerShell and the Remove-CsAVEdgeConfiguration cmdlet to "reset" the global collection; that simply means that all the property values in the global collection will be reset to their default value.</span></span> <span data-ttu-id="3ea5a-110">例如，如果您已將 MaxTokenLifetime 屬性設定為16小時，該屬性將會重設為預設值8小時。</span><span class="sxs-lookup"><span data-stu-id="3ea5a-110">For example, if you have set the MaxTokenLifetime property for 16 hours, that property will be reset to its default value of 8 hours.</span></span>

<span data-ttu-id="3ea5a-p103">然而，使用 Remove-CsAVEdgeConfiguration Cmdlet 可刪除在網站範圍或服務範圍建立的自訂設定集合。如果刪除網站設定，則該網站中的 A/V Edge Server 會由全域設定進行管理。如果刪除服務範圍設定，該伺服器就會由網站設定 (若存在) 或全域設定 (若無網站設定) 進行管理。</span><span class="sxs-lookup"><span data-stu-id="3ea5a-p103">However, custom settings collections that you have created at either the site scope or the service scope can be deleted by using the Remove-CsAVEdgeConfiguration cmdlet. If you delete site settings then A/V Edge servers in that site will be managed by the global settings. If you delete service-scope settings,, that server will then be managed by its site settings, if they exist, or by the global settings if no site settings are available.</span></span>

<span data-ttu-id="3ea5a-114">如需詳細資訊，請參閱 [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15)) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="3ea5a-114">For more information, see the help topic for the [Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15)) cmdlet.</span></span>

<div>

## <a name="to-reset-the-global-collection"></a><span data-ttu-id="3ea5a-115">重設全域集合</span><span class="sxs-lookup"><span data-stu-id="3ea5a-115">To reset the global collection</span></span>

  - <span data-ttu-id="3ea5a-116">下列命令會重設 A/V Edge 組態設定的全域集合：</span><span class="sxs-lookup"><span data-stu-id="3ea5a-116">The following command resets the global collection of A/V Edge configuration settings:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "global"

</div>

<div>

## <a name="to-remove-a-collection-from-the-site-scope"></a><span data-ttu-id="3ea5a-117">從網站範圍中移除集合</span><span class="sxs-lookup"><span data-stu-id="3ea5a-117">To remove a collection from the site scope</span></span>

  - <span data-ttu-id="3ea5a-118">下列命令會移除套用至 Redmond 網站的 A/V Edge 組態設定：</span><span class="sxs-lookup"><span data-stu-id="3ea5a-118">This command removes the A/V Edge configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-a-collection-from-the-service-scope"></a><span data-ttu-id="3ea5a-119">從服務範圍移除集合</span><span class="sxs-lookup"><span data-stu-id="3ea5a-119">To remove a collection from the service scope</span></span>

  - <span data-ttu-id="3ea5a-120">下列命令會移除套用至 A/V Edge Server atl-edge-001.litwareinc.com 的設定：</span><span class="sxs-lookup"><span data-stu-id="3ea5a-120">This command removes the settings applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3ea5a-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3ea5a-121">See Also</span></span>


[<span data-ttu-id="3ea5a-122">傳回 Lync Server 2013 中 A/V Edge Server 設定資訊</span><span class="sxs-lookup"><span data-stu-id="3ea5a-122">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="3ea5a-123">在 Lync Server 2013 中建立或修改 A/V Edge Server 設定的集合</span><span class="sxs-lookup"><span data-stu-id="3ea5a-123">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="3ea5a-124">在 Lync Server 2013 中 Audio/Video (A/V) Edge Server</span><span class="sxs-lookup"><span data-stu-id="3ea5a-124">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="3ea5a-125">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ea5a-125">[Remove-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

