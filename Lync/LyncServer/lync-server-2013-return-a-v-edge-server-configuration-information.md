---
title: Lync Server 2013：傳回 A/V 邊緣伺服器配置資訊
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
ms.openlocfilehash: 2ea7d7ed1ef74c092dac60ecfb2f009219564455
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a><span data-ttu-id="c4f2c-102">在 Lync Server 2013 中傳回 A/V 邊緣伺服器配置資訊</span><span class="sxs-lookup"><span data-stu-id="c4f2c-102">Return A/V Edge Server configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4f2c-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c4f2c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c4f2c-104">A/V Edge 服務為內部使用者（登入組織網路的使用者）提供一種方式，與外部使用者（沒有登入組織網路的使用者）共用音訊和影片。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="c4f2c-105">A/V Edge 服務主要是使用 A/V 邊緣設定設定來管理，設定可以在網站範圍或服務範圍（也就是針對個別的 A/V 邊緣伺服器進行設定）進行設定。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-105">The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="c4f2c-106">若要傳回在貴組織中使用之 A/V 邊緣設定的相關資訊，您必須使用 Windows PowerShell 及 CsAVEdgeConfiguration Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-106">To return information about the A/V Edge configuration settings in use in your organization, you must use Windows PowerShell and the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="c4f2c-107">如需詳細資訊，請參閱[CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-107">For more information, see the help topic for the [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) cmdlet.</span></span>

<span data-ttu-id="c4f2c-108">從 CsAVEdgeConfiguration Cmdlet 傳回的資訊看起來會像這樣：</span><span class="sxs-lookup"><span data-stu-id="c4f2c-108">Information returned from the Get-CsAVEdgeConfiguration cmdlet will look similar to this:</span></span>

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a><span data-ttu-id="c4f2c-109">若要傳回所有 A/V 邊緣設定的資訊</span><span class="sxs-lookup"><span data-stu-id="c4f2c-109">To return information for all your A/V Edge configuration settings</span></span>

  - <span data-ttu-id="c4f2c-110">下列命令會傳回貴組織中目前使用的所有 A/V 邊緣設定資訊：</span><span class="sxs-lookup"><span data-stu-id="c4f2c-110">The following command returns information about all the A/V Edge configuration settings currently in use in your organization:</span></span>
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a><span data-ttu-id="c4f2c-111">若要傳回網站範圍的 A/V 邊緣設定的資訊</span><span class="sxs-lookup"><span data-stu-id="c4f2c-111">To return information for site-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="c4f2c-112">若要傳回特定的 A/V 邊緣配置設定集合的相關資訊，請在執行 CsAVEdgeConfiguration Cmdlet 時指定該集合的身分識別。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-112">To return information about a specific collection of A/V Edge configuration settings, specify the Identity of that collection when running the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="c4f2c-113">例如，這個命令只會傳回套用至雷德蒙者網站之設定的資訊：</span><span class="sxs-lookup"><span data-stu-id="c4f2c-113">For example, this command returns information only for the settings applied to the Redmond site:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a><span data-ttu-id="c4f2c-114">返回服務範圍的 A/V 邊緣設定的資訊</span><span class="sxs-lookup"><span data-stu-id="c4f2c-114">To return information for service-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="c4f2c-115">這個命令只會傳回已套用特定 A/V 邊緣伺服器之設定的資訊：</span><span class="sxs-lookup"><span data-stu-id="c4f2c-115">And this command returns information only for settings applied the a specific A/V Edge server:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c4f2c-116">請參閱</span><span class="sxs-lookup"><span data-stu-id="c4f2c-116">See Also</span></span>


[<span data-ttu-id="c4f2c-117">在 Lync Server 2013 中建立或修改 A/V 邊緣伺服器設定的集合</span><span class="sxs-lookup"><span data-stu-id="c4f2c-117">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[<span data-ttu-id="c4f2c-118">刪除 Lync Server 2013 中現有的 A/V 邊緣伺服器設定集合</span><span class="sxs-lookup"><span data-stu-id="c4f2c-118">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="c4f2c-119">Lync Server 2013 中的音訊/視頻（A/V）邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="c4f2c-119">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

