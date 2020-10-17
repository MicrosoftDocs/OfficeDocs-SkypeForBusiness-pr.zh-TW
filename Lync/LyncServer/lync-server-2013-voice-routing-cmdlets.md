---
title: Lync Server 2013：語音路由 Cmdlet
description: Lync Server 2013：語音路由 Cmdlet。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice routing cmdlets
ms:assetid: 8f05b25e-cc62-4d85-a5d8-4ed56f28dfbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416494(v=OCS.15)
ms:contentKeyID: 48184821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b895eb84bccea6fcb014e61d5609b45c8c14d4cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554069"
---
# <a name="voice-routing-cmdlets-in-lync-server-2013"></a><span data-ttu-id="d2bbe-103">Lync Server 2013 中的語音路由 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d2bbe-103">Voice routing cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2bbe-104">_**主題上次修改日期：** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="d2bbe-104">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="d2bbe-105">語音路由包含的指示可告訴 Microsoft Lync Server 2013 如何在公用交換電話網路 (PSTN) 或專用交換機 (PBX) 中，將來自 Enterprise Voice 使用者的通話路由傳送至電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d2bbe-105">Voice routes contain instructions that tell Microsoft Lync Server 2013 how to route calls from Enterprise Voice users to phone numbers on the public switched telephone network (PSTN) or a private branch exchange (PBX).</span></span>

<div>

## <a name="voice-routing-cmdlets"></a><span data-ttu-id="d2bbe-106">Voice Routing Cmdlets</span><span class="sxs-lookup"><span data-stu-id="d2bbe-106">Voice Routing Cmdlets</span></span>

<span data-ttu-id="d2bbe-107">使用下列 Cmdlet 來設定語音路由。</span><span class="sxs-lookup"><span data-stu-id="d2bbe-107">Use the following cmdlets to configure voice routes.</span></span>

<span data-ttu-id="d2bbe-108">**語音路由**</span><span class="sxs-lookup"><span data-stu-id="d2bbe-108">**Voice Routing**</span></span>

  - <span></span>  
    <span data-ttu-id="d2bbe-109">[Get-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2bbe-109">[Get-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d2bbe-110">[新 CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2bbe-110">[New-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d2bbe-111">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2bbe-111">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d2bbe-112">[CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2bbe-112">[Set-CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="d2bbe-113">[Get-CsVoiceRoute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2bbe-113">[Get-CsVoiceRoute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d2bbe-114">[New-CsVoiceRoute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2bbe-114">[New-CsVoiceRoute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d2bbe-115">[Remove-Get-csvoiceroute](https://technet.microsoft.com/library/Gg398468(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2bbe-115">[Remove-CsVoiceRoute](https://technet.microsoft.com/library/Gg398468(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d2bbe-116">[Get-csvoiceroute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2bbe-116">[Set-CsVoiceRoute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d2bbe-117">[測試-Get-csvoiceroute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2bbe-117">[Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="d2bbe-118">[Get-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ204940(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2bbe-118">[Get-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ204940(v=OCS.15))</span></span>

  - <span data-ttu-id="d2bbe-119">[Grant-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205141(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2bbe-119">[Grant-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205141(v=OCS.15))</span></span>

  - <span data-ttu-id="d2bbe-120">[New-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2bbe-120">[New-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205135(v=OCS.15))</span></span>

  - <span data-ttu-id="d2bbe-121">[Remove-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ204799(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2bbe-121">[Remove-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ204799(v=OCS.15))</span></span>

  - <span data-ttu-id="d2bbe-122">[Set-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205313(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2bbe-122">[Set-CsVoiceRoutingPolicy](https://technet.microsoft.com/library/JJ205313(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="d2bbe-123">[Get-CsPstnUsage](https://technet.microsoft.com/library/Gg412734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2bbe-123">[Get-CsPstnUsage](https://technet.microsoft.com/library/Gg412734(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="d2bbe-124">[Get-cspstnusage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d2bbe-124">[Set-CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d2bbe-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d2bbe-125">See Also</span></span>


[<span data-ttu-id="d2bbe-126">Lync Server 2013 中的 Enterprise Voice Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d2bbe-126">Enterprise Voice cmdlets in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-cmdlets.md)  
[<span data-ttu-id="d2bbe-127">Lync Server 2013 中的 PSTN 連線 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="d2bbe-127">PSTN connectivity cmdlets in Lync Server 2013</span></span>](lync-server-2013-pstn-connectivity-cmdlets.md)  


[<span data-ttu-id="d2bbe-128">Lync Server PowerShell 的博客</span><span class="sxs-lookup"><span data-stu-id="d2bbe-128">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

