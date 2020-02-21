---
title: 'Lync Server 2013: IM 和目前狀態 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence cmdlets
ms:assetid: 7b882480-f3d5-44a2-bb75-fffb7e5caede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398611(v=OCS.15)
ms:contentKeyID: 48184589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a39f195bf6424f76a98e2b5c25dc4bf21942911
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="im-and-presence-cmdlets-in-lync-server-2013"></a><span data-ttu-id="7f8ca-102">Lync Server 2013 中的 IM 和目前狀態 cmdlet</span><span class="sxs-lookup"><span data-stu-id="7f8ca-102">IM and presence cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f8ca-103">_**主題上次修改日期：** 2012年-06-26_</span><span class="sxs-lookup"><span data-stu-id="7f8ca-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="7f8ca-104">立即訊息 (IM) 和目前狀態的指令程式可讓您管理這些用戶端的功能，透過 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7f8ca-104">Instant Messaging (IM) and presence cmdlets allow you to manage those client features through Windows PowerShell.</span></span> <span data-ttu-id="7f8ca-105">您可以在全域、站台或個別使用者範圍設定使用者所適用的顯示狀態原則。</span><span class="sxs-lookup"><span data-stu-id="7f8ca-105">You can set presence policies that apply to users at the global, site, or per-user scope.</span></span> <span data-ttu-id="7f8ca-106">您也可以設定各種隱私權和 IM 功能。</span><span class="sxs-lookup"><span data-stu-id="7f8ca-106">You can also configure various privacy and IM features.</span></span>

<div>

## <a name="im-and-presence-cmdlets"></a><span data-ttu-id="7f8ca-107">IM 和顯示狀態 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="7f8ca-107">IM and Presence Cmdlets</span></span>

<span data-ttu-id="7f8ca-108">若要設定 IM 和顯示狀態，請使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="7f8ca-108">The configure IM and presence, use the following cmdlets:</span></span>

  - <span></span>  
    <span data-ttu-id="7f8ca-109">[Get-cspresencepolicy](https://technet.microsoft.com/library/Gg398463(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-109">[Get-CsPresencePolicy](https://technet.microsoft.com/library/Gg398463(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7f8ca-110">[Grant-cspresencepolicy](https://technet.microsoft.com/library/Gg398571(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-110">[Grant-CsPresencePolicy](https://technet.microsoft.com/library/Gg398571(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7f8ca-111">[New-cspresencepolicy](https://technet.microsoft.com/library/Gg412747(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-111">[New-CsPresencePolicy](https://technet.microsoft.com/library/Gg412747(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7f8ca-112">[移除 CsPresencePolicy](https://technet.microsoft.com/library/Gg399070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-112">[Remove-CsPresencePolicy](https://technet.microsoft.com/library/Gg399070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7f8ca-113">[Set-csmonitoringserver](https://technet.microsoft.com/library/Gg425782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-113">[Set-CsPresencePolicy](https://technet.microsoft.com/library/Gg425782(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="7f8ca-114">[Get-cspresenceprovider](https://technet.microsoft.com/library/JJ204705(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-114">[Get-CsPresenceProvider](https://technet.microsoft.com/library/JJ204705(v=OCS.15))</span></span>

  - <span data-ttu-id="7f8ca-115">[New-cspresenceprovider](https://technet.microsoft.com/library/JJ204895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-115">[New-CsPresenceProvider](https://technet.microsoft.com/library/JJ204895(v=OCS.15))</span></span>

  - <span data-ttu-id="7f8ca-116">[Remove-cspresenceprovider](https://technet.microsoft.com/library/JJ205036(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-116">[Remove-CsPresenceProvider](https://technet.microsoft.com/library/JJ205036(v=OCS.15))</span></span>

  - <span data-ttu-id="7f8ca-117">[Set-cspresenceprovider](https://technet.microsoft.com/library/JJ204833(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-117">[Set-CsPresenceProvider](https://technet.microsoft.com/library/JJ204833(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="7f8ca-118">[Get-csprivacyconfiguration](https://technet.microsoft.com/library/Gg413002(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-118">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg413002(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7f8ca-119">[New-csprivacyconfiguration](https://technet.microsoft.com/library/Gg398807(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-119">[New-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398807(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7f8ca-120">[移除 CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg425821(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-120">[Remove-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg425821(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7f8ca-121">[Set-csprivacyconfiguration](https://technet.microsoft.com/library/Gg398484(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-121">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398484(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="7f8ca-122">[設定 CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-122">[Set-CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="7f8ca-123">[Get-csuserservicesconfiguration](https://technet.microsoft.com/library/Gg398133(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-123">[Get-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398133(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7f8ca-124">[New-csuserservicesconfiguration](https://technet.microsoft.com/library/Gg412926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-124">[New-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg412926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7f8ca-125">[移除 CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-125">[Remove-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398722(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7f8ca-126">[Set-csuserservicesconfiguration](https://technet.microsoft.com/library/Gg398340(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-126">[Set-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398340(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="7f8ca-127">[Get-csfiletransferfilterconfiguration](https://technet.microsoft.com/library/Gg398527(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-127">[Get-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg398527(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7f8ca-128">[New-csfiletransferfilterconfiguration](https://technet.microsoft.com/library/Gg425897(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-128">[New-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425897(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7f8ca-129">[Remove-csfiletransferfilterconfiguration](https://technet.microsoft.com/library/Gg413064(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-129">[Remove-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg413064(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7f8ca-130">[Set-csfiletransferfilterconfiguration](https://technet.microsoft.com/library/Gg425736(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-130">[Set-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425736(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="7f8ca-131">[Get-csimfilterconfiguration](https://technet.microsoft.com/library/Gg398980(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-131">[Get-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398980(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7f8ca-132">[新 CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398244(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-132">[New-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398244(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7f8ca-133">[移除 CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398171(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-133">[Remove-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398171(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="7f8ca-134">[設定 CsImFilterConfiguration](https://technet.microsoft.com/library/Gg412960(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-134">[Set-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg412960(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="7f8ca-135">[Test-csgroupexpansion](https://technet.microsoft.com/library/Gg399009(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-135">[Test-CsGroupExpansion](https://technet.microsoft.com/library/Gg399009(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="7f8ca-136">[Test-csgroupim](https://technet.microsoft.com/library/Gg398273(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-136">[Test-CsGroupIM](https://technet.microsoft.com/library/Gg398273(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="7f8ca-137">[Test-csim](https://technet.microsoft.com/library/Gg425802(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-137">[Test-CsIM](https://technet.microsoft.com/library/Gg425802(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="7f8ca-138">[Test-csp2pav](https://technet.microsoft.com/library/Gg412821(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-138">[Test-CsP2PAV](https://technet.microsoft.com/library/Gg412821(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="7f8ca-139">[Test-cspresence](https://technet.microsoft.com/library/Gg398148(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="7f8ca-139">[Test-CsPresence](https://technet.microsoft.com/library/Gg398148(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7f8ca-140">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7f8ca-140">See Also</span></span>


[<span data-ttu-id="7f8ca-141">Lync Server 2013 中的用戶端管理 cmdlet</span><span class="sxs-lookup"><span data-stu-id="7f8ca-141">Client management cmdlets in Lync Server 2013</span></span>](lync-server-2013-client-management-cmdlets.md)  


[<span data-ttu-id="7f8ca-142">Lync Server PowerShell 部落格</span><span class="sxs-lookup"><span data-stu-id="7f8ca-142">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

