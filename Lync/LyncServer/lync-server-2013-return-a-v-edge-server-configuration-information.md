---
title: Lync Server 2013：退回 A/V Edge Server 設定資訊
description: Lync Server 2013：退回 A/V Edge Server 設定資訊。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4f72fccfe51b946dc0dc285aee12a07e59c844b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575439"
---
# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a><span data-ttu-id="c409d-103">傳回 Lync Server 2013 中 A/V Edge Server 設定資訊</span><span class="sxs-lookup"><span data-stu-id="c409d-103">Return A/V Edge Server configuration information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c409d-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c409d-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c409d-p101">A/V Edge 服務可讓內部使用者 (即已登入您組織網路的使用者) 將音訊和視訊共用給外部使用者 (即未登入您組織網路的使用者)。此服務主要是採用 A/V Edge 組態設定管理，可以在網站範圍或服務範圍裡完成這些設定 (亦即可以針對個別 A/V Edge 伺服器進行設定)。</span><span class="sxs-lookup"><span data-stu-id="c409d-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="c409d-107">若要傳回組織中使用之 A/V Edge 設定設定的相關資訊，您必須使用 Windows PowerShell 和 Get-CsAVEdgeConfiguration Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c409d-107">To return information about the A/V Edge configuration settings in use in your organization, you must use Windows PowerShell and the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="c409d-108">如需詳細資訊，請參閱 [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="c409d-108">For more information, see the help topic for the [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) cmdlet.</span></span>

<span data-ttu-id="c409d-109">從 Get-CsAVEdgeConfiguration Cmdlet 傳回的資訊看起來如下所示：</span><span class="sxs-lookup"><span data-stu-id="c409d-109">Information returned from the Get-CsAVEdgeConfiguration cmdlet will look similar to this:</span></span>

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a><span data-ttu-id="c409d-110">若要傳回所有 A/V Edge 設定設定的資訊</span><span class="sxs-lookup"><span data-stu-id="c409d-110">To return information for all your A/V Edge configuration settings</span></span>

  - <span data-ttu-id="c409d-111">下列命令會傳回組織目前所使用之所有 A/V Edge 設定設定的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="c409d-111">The following command returns information about all the A/V Edge configuration settings currently in use in your organization:</span></span>
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a><span data-ttu-id="c409d-112">若要傳回網站範圍的 A/V Edge 設定設定的資訊</span><span class="sxs-lookup"><span data-stu-id="c409d-112">To return information for site-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="c409d-113">若要傳回特定 A/V Edge 設定設定集合的資訊，請在執行 Get-CsAVEdgeConfiguration Cmdlet 時，指定該集合的身分識別。</span><span class="sxs-lookup"><span data-stu-id="c409d-113">To return information about a specific collection of A/V Edge configuration settings, specify the Identity of that collection when running the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="c409d-114">例如，下列命令只會傳回套用至 Redmond 網站之設定的資訊：</span><span class="sxs-lookup"><span data-stu-id="c409d-114">For example, this command returns information only for the settings applied to the Redmond site:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a><span data-ttu-id="c409d-115">傳回服務範圍 A/V Edge 設定設定的資訊</span><span class="sxs-lookup"><span data-stu-id="c409d-115">To return information for service-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="c409d-116">而且，此命令只會傳回套用特定 A/V Edge server 之設定的資訊：</span><span class="sxs-lookup"><span data-stu-id="c409d-116">And this command returns information only for settings applied the a specific A/V Edge server:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c409d-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c409d-117">See Also</span></span>


[<span data-ttu-id="c409d-118">在 Lync Server 2013 中建立或修改 A/V Edge Server 設定的集合</span><span class="sxs-lookup"><span data-stu-id="c409d-118">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[<span data-ttu-id="c409d-119">在 Lync Server 2013 中刪除現有的 A/V Edge Server 設定集合集合</span><span class="sxs-lookup"><span data-stu-id="c409d-119">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="c409d-120">在 Lync Server 2013 中 Audio/Video (A/V) Edge Server</span><span class="sxs-lookup"><span data-stu-id="c409d-120">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

