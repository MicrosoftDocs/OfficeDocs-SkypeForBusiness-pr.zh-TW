---
title: 建立或修改一群 A / V Edge Server 組態設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 576fcb445eb37b92356ad9fdf36de716581ca6fa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="39c7f-102">建立或修改一群 A / V Edge Server 組態設定 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="39c7f-102">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39c7f-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="39c7f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="39c7f-p101">A/V Edge 服務可讓內部使用者 (即已登入您組織網路的使用者) 將音訊和視訊共用給外部使用者 (即未登入您組織網路的使用者)。此服務主要是採用 A/V Edge 組態設定管理，可以在網站範圍或服務範圍裡完成這些設定 (亦即可以針對個別 A/V Edge 伺服器進行設定)。</span><span class="sxs-lookup"><span data-stu-id="39c7f-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="39c7f-106">當您安裝 Lync Server，全域集合的 A / V Edge 組態設定會加以建立。</span><span class="sxs-lookup"><span data-stu-id="39c7f-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="39c7f-107">除了，您可以使用 Windows PowerShell 和新增 CsAVEdgeConfiguration cmdlet 在網站範圍或服務範圍建立新的設定 (也就是個別的 a / V Edge server)。</span><span class="sxs-lookup"><span data-stu-id="39c7f-107">In addition to that, you can use the Windows PowerShell and the New-CsAVEdgeConfiguration cmdlet to create new settings at the site scope or the service scope (that is, for an individual A/V Edge server).</span></span> <span data-ttu-id="39c7f-108">若要建立新設定，請務必記住：</span><span class="sxs-lookup"><span data-stu-id="39c7f-108">If you create new settings keep in mind that:</span></span>

  - <span data-ttu-id="39c7f-109">服務範圍 (亦即在個別伺服器) 中的設定優先使用。</span><span class="sxs-lookup"><span data-stu-id="39c7f-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="39c7f-110">在網站範圍設定的設定優先於全域範圍設定的設定。</span><span class="sxs-lookup"><span data-stu-id="39c7f-110">Settings configured at the site scope take priority over settings configured at the global scope.</span></span> <span data-ttu-id="39c7f-111">不過，服務範圍設定也會取代網站範圍設定。</span><span class="sxs-lookup"><span data-stu-id="39c7f-111">However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="39c7f-112">若個別伺服器裡未進行任何服務設定，且該伺服器所處的網站無任何網站設定，才會使用全域範圍的設定。</span><span class="sxs-lookup"><span data-stu-id="39c7f-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="39c7f-113">任何設定都可以使用 Set-CsAVEdgeConfiguration Cmdlet 修改。</span><span class="sxs-lookup"><span data-stu-id="39c7f-113">Any of your settings can then be modified by using the Set-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="39c7f-114">如需詳細資訊，請參閱[新增 CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))和[Set-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="39c7f-114">For more information, see the help topics for the [New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) and the [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) cmdlets.</span></span>

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="39c7f-115">若要建立新的 A / V Edge 組態設定，在網站範圍</span><span class="sxs-lookup"><span data-stu-id="39c7f-115">To create new A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="39c7f-116">以下的命令會針對 Redmond 網站，建立新的 A/V Edge 組態設定集合。</span><span class="sxs-lookup"><span data-stu-id="39c7f-116">The following command creates a new collection of A/V Edge configuration settings for the Redmond site:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="39c7f-117">若要建立自訂的 A / V Edge 組態設定，在網站範圍</span><span class="sxs-lookup"><span data-stu-id="39c7f-117">To create custom A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="39c7f-p105">由於這些新設定不包含其他參數，因此會使用 A/V Edge 服務的預設值。您也可以選擇新增其他參數和參數值來建立自訂集合。舉例來說，此命令將 MaxTokenLifetime 屬性設為 4 小時 (04 時 : 00 分 : 00 秒)：</span><span class="sxs-lookup"><span data-stu-id="39c7f-p105">Because no additional parameters were included, these new settings will use the default values for the A/V Edge service. Alternatively, you can add additional parameters and parameter values to create a custom collection. For example, this command sets the MaxTokenLifetime property to 4 hours (04 hours : 00 minutes : 00 seconds):</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a><span data-ttu-id="39c7f-121">若要建立自訂的 A / V Edge 組態設定，在服務範圍</span><span class="sxs-lookup"><span data-stu-id="39c7f-121">To create custom A/V Edge configuration settings at the service scope</span></span>

  - <span data-ttu-id="39c7f-122">此命令建立套用至 A/V Edge 伺服器 atl-edge-001.litwareinc.com 的相似集合：</span><span class="sxs-lookup"><span data-stu-id="39c7f-122">This command creates a similar collection applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a><span data-ttu-id="39c7f-123">若要修改現有的 A / V Edge 組態設定</span><span class="sxs-lookup"><span data-stu-id="39c7f-123">To modify existing A/V Edge configuration settings</span></span>

  - <span data-ttu-id="39c7f-124">本範例是使用 Set-CsAVEdgeConfiguration Cmdlet 將 Redmond 網站的最大權杖存留期更改為 12 小時：</span><span class="sxs-lookup"><span data-stu-id="39c7f-124">In this example, the Set-CsAVEdgeConfiguration cmdlet is used to change the maximum token lifetime for the Redmond site to 12 hours:</span></span>
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="39c7f-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="39c7f-125">See Also</span></span>


[<span data-ttu-id="39c7f-126">傳回 A / V Edge Server 在 Lync Server 2013 中的組態資訊</span><span class="sxs-lookup"><span data-stu-id="39c7f-126">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="39c7f-127">刪除現有集合的 A / V Edge Server 組態設定 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="39c7f-127">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="39c7f-128">音訊/視訊 (A / V) Lync Server 2013 中的 Edge Server</span><span class="sxs-lookup"><span data-stu-id="39c7f-128">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="39c7f-129">[新 CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="39c7f-129">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span></span>  
<span data-ttu-id="39c7f-130">[Set-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="39c7f-130">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

