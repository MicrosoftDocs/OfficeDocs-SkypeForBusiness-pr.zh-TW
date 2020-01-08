---
title: Lync Server 2013：網路會議 Cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Web conferencing cmdlets
ms:assetid: dac4d934-1500-4799-be4d-82809d4e7eb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415675(v=OCS.15)
ms:contentKeyID: 48185556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 407fc4645f01692c664d80d0c60b337efa28f20f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="web-conferencing-cmdlets-in-lync-server-2013"></a><span data-ttu-id="2ad0d-102">Lync Server 2013 中的網路會議 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2ad0d-102">Web conferencing cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ad0d-103">_**主題上次修改日期：** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="2ad0d-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="2ad0d-104">在 Microsoft Lync Server 2013 中，會議和線上會議是重要的元素。</span><span class="sxs-lookup"><span data-stu-id="2ad0d-104">Conferencing and online meetings are important elements in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="2ad0d-105">CsConferencingConfiguration 和 CsConferencingPolicy Cmdlet 是使用 Windows PowerShell 管理會議的主要管理工具。</span><span class="sxs-lookup"><span data-stu-id="2ad0d-105">The CsConferencingConfiguration and CsConferencingPolicy cmdlets are the primary administrative tools for managing conferences by using Windows PowerShell.</span></span>

<div>

## <a name="web-conferencing-cmdlets"></a><span data-ttu-id="2ad0d-106">網路會議 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2ad0d-106">Web Conferencing Cmdlets</span></span>

<span data-ttu-id="2ad0d-107">[新的 CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425949(v=OCS.15))和[CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398300(v=OCS.15)) Cmdlet 提供其他設定和管理 Lync Server 2013 的方法。</span><span class="sxs-lookup"><span data-stu-id="2ad0d-107">The [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425949(v=OCS.15)) and [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398300(v=OCS.15)) cmdlets provide additional ways to configure and manage Lync Server 2013.</span></span>

<span data-ttu-id="2ad0d-108">**Web 會議**</span><span class="sxs-lookup"><span data-stu-id="2ad0d-108">**Web Conferencing**</span></span>

  - <span></span>  
    <span data-ttu-id="2ad0d-109">[CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425714(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-109">[Get-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425714(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2ad0d-110">[移除-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398243(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-110">[Remove-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398243(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2ad0d-111">[Set-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-111">[Set-CsConferenceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398776(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2ad0d-112">[Set-CsConferenceServer](https://technet.microsoft.com/en-us/library/Gg398738(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-112">[Set-CsConferenceServer](https://technet.microsoft.com/en-us/library/Gg398738(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2ad0d-113">[CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398965(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-113">[Get-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg398965(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2ad0d-114">[New-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-114">[New-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412967(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2ad0d-115">[移除-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412767(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-115">[Remove-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412767(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2ad0d-116">[Set-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412969(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-116">[Set-CsConferencingConfiguration](https://technet.microsoft.com/en-us/library/Gg412969(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2ad0d-117">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398293(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-117">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398293(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2ad0d-118">[授與 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425937(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-118">[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425937(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2ad0d-119">[New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg413019(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-119">[New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg413019(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2ad0d-120">[Remove-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398728(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-120">[Remove-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg398728(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2ad0d-121">[Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425788(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-121">[Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/Gg425788(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2ad0d-122">[CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg425875(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-122">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg425875(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2ad0d-123">[New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-123">[New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2ad0d-124">[移除-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-124">[Remove-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2ad0d-125">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398648(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-125">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398648(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="2ad0d-126">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-126">[Disable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204723(v=OCS.15))</span></span>

  - <span data-ttu-id="2ad0d-127">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205062(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-127">[Enable-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205062(v=OCS.15))</span></span>

  - <span data-ttu-id="2ad0d-128">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205277(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-128">[Get-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ205277(v=OCS.15))</span></span>

  - <span data-ttu-id="2ad0d-129">[移動流覽 CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204889(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-129">[Move-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204889(v=OCS.15))</span></span>

  - <span data-ttu-id="2ad0d-130">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204831(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-130">[Set-CsMeetingRoom](https://technet.microsoft.com/en-us/library/JJ204831(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2ad0d-131">[Test-CsASConference](https://technet.microsoft.com/en-us/library/JJ205227(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-131">[Test-CsASConference](https://technet.microsoft.com/en-us/library/JJ205227(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2ad0d-132">[Test-CsAVConference](https://technet.microsoft.com/en-us/library/Gg412749(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-132">[Test-CsAVConference](https://technet.microsoft.com/en-us/library/Gg412749(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2ad0d-133">[Test-CsDataConference](https://technet.microsoft.com/en-us/library/JJ205219(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-133">[Test-CsDataConference](https://technet.microsoft.com/en-us/library/JJ205219(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2ad0d-134">[Test-CsWebApp](https://technet.microsoft.com/en-us/library/Hh689989(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-134">[Test-CsWebApp](https://technet.microsoft.com/en-us/library/Hh689989(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2ad0d-135">[Test-CsWebAppAnonymous](https://technet.microsoft.com/en-us/library/Hh690041(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-135">[Test-CsWebAppAnonymous](https://technet.microsoft.com/en-us/library/Hh690041(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2ad0d-136">[Test-CsWebScheduler](https://technet.microsoft.com/en-us/library/JJ204829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ad0d-136">[Test-CsWebScheduler](https://technet.microsoft.com/en-us/library/JJ204829(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2ad0d-137">請參閱</span><span class="sxs-lookup"><span data-stu-id="2ad0d-137">See Also</span></span>


[<span data-ttu-id="2ad0d-138">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="2ad0d-138">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

