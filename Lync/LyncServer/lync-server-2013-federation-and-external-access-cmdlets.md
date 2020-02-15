---
title: Lync Server 2013： 同盟和外部存取 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Federation and external access cmdlets
ms:assetid: 4a384a57-257f-47a6-98d9-54cea2c647b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415651(v=OCS.15)
ms:contentKeyID: 48184018
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 032258e6fe7d77808b3bf4731049ee9df49d1162
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="federation-and-external-access-cmdlets-in-lync-server-2013"></a><span data-ttu-id="2de8e-102">同盟和 Lync Server 2013 中的外部存取 cmdlet</span><span class="sxs-lookup"><span data-stu-id="2de8e-102">Federation and external access cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2de8e-103">_**主題上次修改日期：** 2012年-06-26_</span><span class="sxs-lookup"><span data-stu-id="2de8e-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="2de8e-104">同盟和外部存取提供兩個重要功能： 同盟可讓使用者能夠與組織外的人員時外部存取可讓使用者連線到 Microsoft Lync Server 2013 中從內部網路之外。</span><span class="sxs-lookup"><span data-stu-id="2de8e-104">Federation and external access provide two important capabilities: federation enables users to communicate with people outside your organization, while external access enables users to connect to Microsoft Lync Server 2013 from outside the internal network.</span></span> <span data-ttu-id="2de8e-105">可用於管理同盟與外部存取 Lync Server 2013 中的 cmdlet 可讓您決定您的使用者可以 （而且也無法） 通訊，並決定這些使用者可以連線至 Lync Server 而不必登入內部網路。</span><span class="sxs-lookup"><span data-stu-id="2de8e-105">The cmdlets available for managing federation and external access in Lync Server 2013 let you determine who your users can (and cannot) communicate with, and determine whether or not those users can connect to Lync Server without having to log on to the internal network.</span></span>

<div>

## <a name="federation-and-external-access-cmdlets"></a><span data-ttu-id="2de8e-106">同盟和外部存取 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2de8e-106">Federation and External Access Cmdlets</span></span>

<span data-ttu-id="2de8e-107">從 Lync Server Control Panel 可執行大部分適用於同盟和外部存取的管理工作。</span><span class="sxs-lookup"><span data-stu-id="2de8e-107">Most management tasks that apply to federation and external access can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="2de8e-108">這些相同的工作可以使用 cmdlet 從 Lync Server 管理命令介面或從內執行的指令碼;使用指令碼，可讓您自動執行特定工作。</span><span class="sxs-lookup"><span data-stu-id="2de8e-108">These same tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script; using a script enables you to automate certain tasks.</span></span> <span data-ttu-id="2de8e-109">以下列出與管理同盟和外部存取直接相關的 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2de8e-109">The following is a list of cmdlets that relate directly to managing federation and external access:</span></span>

  - <span></span>  
    <span data-ttu-id="2de8e-110">[Get-csalloweddomain](https://technet.microsoft.com/library/Gg398164(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-110">[Get-CsAllowedDomain](https://technet.microsoft.com/library/Gg398164(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2de8e-111">[新 CsAllowedDomain](https://technet.microsoft.com/library/Gg398628(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-111">[New-CsAllowedDomain](https://technet.microsoft.com/library/Gg398628(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2de8e-112">[移除 CsAllowedDomain](https://technet.microsoft.com/library/Gg398913(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-112">[Remove-CsAllowedDomain](https://technet.microsoft.com/library/Gg398913(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2de8e-113">[Set-csalloweddomain](https://technet.microsoft.com/library/Gg398931(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-113">[Set-CsAllowedDomain](https://technet.microsoft.com/library/Gg398931(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2de8e-114">[Get-csblockeddomain](https://technet.microsoft.com/library/Gg398424(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-114">[Get-CsBlockedDomain](https://technet.microsoft.com/library/Gg398424(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2de8e-115">[新 New-csblockeddomain](https://technet.microsoft.com/library/Gg398822(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-115">[New-CsBlockedDomain](https://technet.microsoft.com/library/Gg398822(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2de8e-116">[移除 New-csblockeddomain](https://technet.microsoft.com/library/Gg425832(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-116">[Remove-CsBlockedDomain](https://technet.microsoft.com/library/Gg425832(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2de8e-117">[設定 New-csblockeddomain](https://technet.microsoft.com/library/Gg398090(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-117">[Set-CsBlockedDomain](https://technet.microsoft.com/library/Gg398090(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2de8e-118">[Get-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2de8e-119">[Grant-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg425942(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-119">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425942(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2de8e-120">[新 CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398441(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-120">[New-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398441(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2de8e-121">[Remove-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg399057(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-121">[Remove-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg399057(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2de8e-122">[設定 CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398916(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-122">[Set-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg398916(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="2de8e-123">[Get-csfipsconfiguration](https://technet.microsoft.com/library/JJ204904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-123">[Get-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ204904(v=OCS.15))</span></span>

  - <span data-ttu-id="2de8e-124">[New-csfipsconfiguration](https://technet.microsoft.com/library/JJ205114(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-124">[New-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205114(v=OCS.15))</span></span>

  - <span data-ttu-id="2de8e-125">[Remove-csfipsconfiguration](https://technet.microsoft.com/library/JJ205201(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-125">[Remove-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205201(v=OCS.15))</span></span>

  - <span data-ttu-id="2de8e-126">[Set-csfipsconfiguration](https://technet.microsoft.com/library/JJ205084(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-126">[Set-CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205084(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2de8e-127">[停用 CsHostingProvider](https://technet.microsoft.com/library/Gg398481(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-127">[Disable-CsHostingProvider](https://technet.microsoft.com/library/Gg398481(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2de8e-128">[啟用 CsHostingProvider](https://technet.microsoft.com/library/Gg398166(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-128">[Enable-CsHostingProvider](https://technet.microsoft.com/library/Gg398166(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2de8e-129">[Get-cshostingprovider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-129">[Get-CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2de8e-130">[新 CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-130">[New-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2de8e-131">[移除 CsHostingProvider](https://technet.microsoft.com/library/Gg425809(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-131">[Remove-CsHostingProvider](https://technet.microsoft.com/library/Gg425809(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2de8e-132">[設定 CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-132">[Set-CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2de8e-133">[停用 CsPublicProvider](https://technet.microsoft.com/library/Gg398984(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-133">[Disable-CsPublicProvider](https://technet.microsoft.com/library/Gg398984(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2de8e-134">[啟用 CsPublicProvider](https://technet.microsoft.com/library/Gg398780(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-134">[Enable-CsPublicProvider](https://technet.microsoft.com/library/Gg398780(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2de8e-135">[取得 CsPublicProvider](https://technet.microsoft.com/library/Gg412945(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-135">[Get-CsPublicProvider](https://technet.microsoft.com/library/Gg412945(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2de8e-136">[新 CsPublicProvider](https://technet.microsoft.com/library/Gg398161(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-136">[New-CsPublicProvider](https://technet.microsoft.com/library/Gg398161(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2de8e-137">[移除 CsPublicProvider](https://technet.microsoft.com/library/Gg412906(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-137">[Remove-CsPublicProvider](https://technet.microsoft.com/library/Gg412906(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="2de8e-138">[設定 CsPublicProvider](https://technet.microsoft.com/library/Gg413087(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-138">[Set-CsPublicProvider](https://technet.microsoft.com/library/Gg413087(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="2de8e-139">[Test-csfederatedpartner](https://technet.microsoft.com/library/Gg398281(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-139">[Test-CsFederatedPartner](https://technet.microsoft.com/library/Gg398281(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="2de8e-140">[Get-csxmppallowedpartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-140">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span></span>

  - <span data-ttu-id="2de8e-141">[New-csxmppallowedpartner](https://technet.microsoft.com/library/JJ204631(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-141">[New-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204631(v=OCS.15))</span></span>

  - <span data-ttu-id="2de8e-142">[Remove-csxmppallowedpartner](https://technet.microsoft.com/library/JJ205055(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-142">[Remove-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ205055(v=OCS.15))</span></span>

  - <span data-ttu-id="2de8e-143">[Set-csxmppallowedpartner](https://technet.microsoft.com/library/JJ204686(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-143">[Set-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204686(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="2de8e-144">[Get-csxmppgatewayconfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-144">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span></span>

  - <span data-ttu-id="2de8e-145">[Set-csxmppgatewayconfiguration](https://technet.microsoft.com/library/JJ204769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-145">[Set-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204769(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="2de8e-146">[Test-csxmppim](https://technet.microsoft.com/library/JJ205423(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2de8e-146">[Test-CsXmppIM](https://technet.microsoft.com/library/JJ205423(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2de8e-147">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2de8e-147">See Also</span></span>


[<span data-ttu-id="2de8e-148">Lync Server PowerShell 部落格</span><span class="sxs-lookup"><span data-stu-id="2de8e-148">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

