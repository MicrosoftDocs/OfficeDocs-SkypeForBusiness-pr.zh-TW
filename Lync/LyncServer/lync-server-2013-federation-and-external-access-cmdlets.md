---
title: Lync Server 2013：同盟與外部存取 Cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Federation and external access cmdlets
ms:assetid: 4a384a57-257f-47a6-98d9-54cea2c647b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415651(v=OCS.15)
ms:contentKeyID: 48184018
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc44d6d8dbd196e720d836ba8c3417e06a44c988
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="federation-and-external-access-cmdlets-in-lync-server-2013"></a><span data-ttu-id="4652a-102">Lync Server 2013 中的同盟與外部存取 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="4652a-102">Federation and external access cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4652a-103">_**主題上次修改日期：** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="4652a-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="4652a-104">同盟和外部存取提供兩項重要的功能：同盟可讓使用者與組織外部的人員通訊，而外部存取可讓使用者從內部網路外部連線到 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="4652a-104">Federation and external access provide two important capabilities: federation enables users to communicate with people outside your organization, while external access enables users to connect to Microsoft Lync Server 2013 from outside the internal network.</span></span> <span data-ttu-id="4652a-105">您可以在 Lync Server 2013 中管理同盟和外部存取的 Cmdlet，讓您判斷使用者可以（和無法）與哪些人通訊，並判斷這些使用者是否可以連線到 Lync Server，而不需要登入內部局域網.</span><span class="sxs-lookup"><span data-stu-id="4652a-105">The cmdlets available for managing federation and external access in Lync Server 2013 let you determine who your users can (and cannot) communicate with, and determine whether or not those users can connect to Lync Server without having to log on to the internal network.</span></span>

<div>

## <a name="federation-and-external-access-cmdlets"></a><span data-ttu-id="4652a-106">同盟與外部存取 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="4652a-106">Federation and External Access Cmdlets</span></span>

<span data-ttu-id="4652a-107">大多數適用于同盟和外部存取的管理工作，都可以從 Lync Server [控制台] 執行。</span><span class="sxs-lookup"><span data-stu-id="4652a-107">Most management tasks that apply to federation and external access can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="4652a-108">您可以使用 Lync Server 管理命令介面或腳本中的 Cmdlet 來執行這些相同的工作;使用腳本可讓您自動執行特定工作。</span><span class="sxs-lookup"><span data-stu-id="4652a-108">These same tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script; using a script enables you to automate certain tasks.</span></span> <span data-ttu-id="4652a-109">以下是直接與管理同盟及外部存取相關的 Cmdlet 清單：</span><span class="sxs-lookup"><span data-stu-id="4652a-109">The following is a list of cmdlets that relate directly to managing federation and external access:</span></span>

  - <span></span>  
    <span data-ttu-id="4652a-110">[CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398164(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-110">[Get-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398164(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4652a-111">[New-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398628(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-111">[New-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398628(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4652a-112">[移除-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398913(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-112">[Remove-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398913(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4652a-113">[Set-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398931(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-113">[Set-CsAllowedDomain](https://technet.microsoft.com/en-us/library/Gg398931(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4652a-114">[CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398424(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-114">[Get-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398424(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4652a-115">[新-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398822(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-115">[New-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398822(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4652a-116">[移除-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg425832(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-116">[Remove-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg425832(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4652a-117">[Set-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398090(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-117">[Set-CsBlockedDomain](https://technet.microsoft.com/en-us/library/Gg398090(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4652a-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4652a-119">[授與 CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425942(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-119">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425942(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4652a-120">[New-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398441(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-120">[New-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398441(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4652a-121">[Remove-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg399057(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-121">[Remove-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg399057(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4652a-122">[Set-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398916(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-122">[Set-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg398916(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="4652a-123">[CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ204904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-123">[Get-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ204904(v=OCS.15))</span></span>

  - <span data-ttu-id="4652a-124">[新-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205114(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-124">[New-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205114(v=OCS.15))</span></span>

  - <span data-ttu-id="4652a-125">[移除-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205201(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-125">[Remove-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205201(v=OCS.15))</span></span>

  - <span data-ttu-id="4652a-126">[Set-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205084(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-126">[Set-CsFIPSConfiguration](https://technet.microsoft.com/en-us/library/JJ205084(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4652a-127">[Disable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398481(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-127">[Disable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398481(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4652a-128">[Enable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398166(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-128">[Enable-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398166(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4652a-129">[CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-129">[Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4652a-130">[新-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-130">[New-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4652a-131">[移除-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg425809(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-131">[Remove-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg425809(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4652a-132">[Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-132">[Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4652a-133">[Disable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398984(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-133">[Disable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398984(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4652a-134">[Enable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398780(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-134">[Enable-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398780(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4652a-135">[CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412945(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-135">[Get-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412945(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4652a-136">[New-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398161(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-136">[New-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg398161(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4652a-137">[移除-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412906(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-137">[Remove-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg412906(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="4652a-138">[Set-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg413087(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-138">[Set-CsPublicProvider](https://technet.microsoft.com/en-us/library/Gg413087(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="4652a-139">[Test-CsFederatedPartner](https://technet.microsoft.com/en-us/library/Gg398281(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-139">[Test-CsFederatedPartner](https://technet.microsoft.com/en-us/library/Gg398281(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="4652a-140">[CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-140">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))</span></span>

  - <span data-ttu-id="4652a-141">[新-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204631(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-141">[New-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204631(v=OCS.15))</span></span>

  - <span data-ttu-id="4652a-142">[移除-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ205055(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-142">[Remove-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ205055(v=OCS.15))</span></span>

  - <span data-ttu-id="4652a-143">[Set-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204686(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-143">[Set-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204686(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="4652a-144">[CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-144">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))</span></span>

  - <span data-ttu-id="4652a-145">[Set-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-145">[Set-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204769(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="4652a-146">[Test-CsXmppIM](https://technet.microsoft.com/en-us/library/JJ205423(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4652a-146">[Test-CsXmppIM](https://technet.microsoft.com/en-us/library/JJ205423(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4652a-147">請參閱</span><span class="sxs-lookup"><span data-stu-id="4652a-147">See Also</span></span>


[<span data-ttu-id="4652a-148">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="4652a-148">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

