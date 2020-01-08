---
title: Lync Server 2013： IM 和目前狀態 Cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IM and presence cmdlets
ms:assetid: 7b882480-f3d5-44a2-bb75-fffb7e5caede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398611(v=OCS.15)
ms:contentKeyID: 48184589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5047a8fbb4d9533e7364ca0d566c0a9ce9660fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="im-and-presence-cmdlets-in-lync-server-2013"></a><span data-ttu-id="c78da-102">Lync Server 2013 中的 IM 和目前狀態 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c78da-102">IM and presence cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c78da-103">_**主題上次修改日期：** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="c78da-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="c78da-104">立即訊息（IM）與目前狀態 Cmdlet 可讓您透過 Windows PowerShell 管理這些用戶端功能。</span><span class="sxs-lookup"><span data-stu-id="c78da-104">Instant Messaging (IM) and presence cmdlets allow you to manage those client features through Windows PowerShell.</span></span> <span data-ttu-id="c78da-105">您可以針對全域、網站或每個使用者範圍，設定適用于使用者的目前狀態原則。</span><span class="sxs-lookup"><span data-stu-id="c78da-105">You can set presence policies that apply to users at the global, site, or per-user scope.</span></span> <span data-ttu-id="c78da-106">您也可以設定各種隱私權與 IM 功能。</span><span class="sxs-lookup"><span data-stu-id="c78da-106">You can also configure various privacy and IM features.</span></span>

<div>

## <a name="im-and-presence-cmdlets"></a><span data-ttu-id="c78da-107">IM 和目前狀態 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c78da-107">IM and Presence Cmdlets</span></span>

<span data-ttu-id="c78da-108">[設定 IM 和目前狀態] 使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c78da-108">The configure IM and presence, use the following cmdlets:</span></span>

  - <span></span>  
    <span data-ttu-id="c78da-109">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398463(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-109">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398463(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c78da-110">[授與 CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398571(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-110">[Grant-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg398571(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c78da-111">[New-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg412747(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-111">[New-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg412747(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c78da-112">[Remove-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg399070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-112">[Remove-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg399070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c78da-113">[Set-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg425782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-113">[Set-CsPresencePolicy](https://technet.microsoft.com/en-us/library/Gg425782(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="c78da-114">[CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204705(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-114">[Get-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204705(v=OCS.15))</span></span>

  - <span data-ttu-id="c78da-115">[新-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-115">[New-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204895(v=OCS.15))</span></span>

  - <span data-ttu-id="c78da-116">[移除-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ205036(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-116">[Remove-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ205036(v=OCS.15))</span></span>

  - <span data-ttu-id="c78da-117">[Set-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204833(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-117">[Set-CsPresenceProvider](https://technet.microsoft.com/en-us/library/JJ204833(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c78da-118">[CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg413002(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-118">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg413002(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c78da-119">[新-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398807(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-119">[New-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398807(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c78da-120">[移除-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg425821(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-120">[Remove-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg425821(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c78da-121">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398484(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-121">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/Gg398484(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c78da-122">[Set-CsUserServer](https://technet.microsoft.com/en-us/library/Gg413026(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-122">[Set-CsUserServer](https://technet.microsoft.com/en-us/library/Gg413026(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c78da-123">[CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398133(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-123">[Get-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398133(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c78da-124">[新-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg412926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-124">[New-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg412926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c78da-125">[移除-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-125">[Remove-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398722(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c78da-126">[Set-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398340(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-126">[Set-CsUserServicesConfiguration](https://technet.microsoft.com/en-us/library/Gg398340(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c78da-127">[CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398527(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-127">[Get-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398527(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c78da-128">[新-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425897(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-128">[New-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425897(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c78da-129">[移除-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg413064(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-129">[Remove-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg413064(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c78da-130">[Set-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425736(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-130">[Set-CsFileTransferFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg425736(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c78da-131">[CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398980(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-131">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398980(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c78da-132">[新-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398244(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-132">[New-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398244(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c78da-133">[移除-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398171(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-133">[Remove-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg398171(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c78da-134">[Set-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg412960(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-134">[Set-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/Gg412960(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c78da-135">[Test-CsGroupExpansion](https://technet.microsoft.com/en-us/library/Gg399009(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-135">[Test-CsGroupExpansion](https://technet.microsoft.com/en-us/library/Gg399009(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c78da-136">[Test-CsGroupIM](https://technet.microsoft.com/en-us/library/Gg398273(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-136">[Test-CsGroupIM](https://technet.microsoft.com/en-us/library/Gg398273(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c78da-137">[Test-CsIM](https://technet.microsoft.com/en-us/library/Gg425802(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-137">[Test-CsIM](https://technet.microsoft.com/en-us/library/Gg425802(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c78da-138">[Test-CsP2PAV](https://technet.microsoft.com/en-us/library/Gg412821(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-138">[Test-CsP2PAV](https://technet.microsoft.com/en-us/library/Gg412821(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c78da-139">[Test-CsPresence](https://technet.microsoft.com/en-us/library/Gg398148(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c78da-139">[Test-CsPresence](https://technet.microsoft.com/en-us/library/Gg398148(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c78da-140">請參閱</span><span class="sxs-lookup"><span data-stu-id="c78da-140">See Also</span></span>


[<span data-ttu-id="c78da-141">Lync Server 2013 中的用戶端管理 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c78da-141">Client management cmdlets in Lync Server 2013</span></span>](lync-server-2013-client-management-cmdlets.md)  


[<span data-ttu-id="c78da-142">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="c78da-142">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

