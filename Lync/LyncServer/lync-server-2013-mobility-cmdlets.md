---
title: Lync Server 2013： 行動 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility cmdlets
ms:assetid: 42a30a34-d66b-4c91-b596-a6fc7666e600
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690019(v=OCS.15)
ms:contentKeyID: 48183973
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f7e996499497bd663ad0f2135b0745c1c96f8dc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mobility-cmdlets-in-lync-server-2013"></a><span data-ttu-id="151fd-102">Lync Server 2013 中的行動性 cmdlet</span><span class="sxs-lookup"><span data-stu-id="151fd-102">Mobility cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="151fd-103">_**主題上次修改日期：** 2012年-06-20 個_</span><span class="sxs-lookup"><span data-stu-id="151fd-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="151fd-104">已引進 mobility cmdlet 來管理行動功能新增 Lync Server 2010 的累計更新： 2011 年 11 月。</span><span class="sxs-lookup"><span data-stu-id="151fd-104">Mobility cmdlets were introduced to manage the mobility feature added in cumulative update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="151fd-105">您可以使用這些 Cmdlet 來管理行動功能的設定，例如 Mobility Service 設定和使用者原則。</span><span class="sxs-lookup"><span data-stu-id="151fd-105">Use these cmdlets to manage settings for mobility features, such as Mobility Service configuration and user policies.</span></span>

<div>

## <a name="mobility-cmdlets"></a><span data-ttu-id="151fd-106">行動 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="151fd-106">Mobility Cmdlets</span></span>

<span data-ttu-id="151fd-107">設定行動功能 cmdlet 可讓您從 Lync Server 管理命令介面中執行命令，或是寫入指令碼，以設定及測試各種行動設定。</span><span class="sxs-lookup"><span data-stu-id="151fd-107">The cmdlets that configure mobility features allow you to run commands from the Lync Server Management Shell or to write scripts to configure and test various mobility settings.</span></span>

  - <span></span>  
    <span data-ttu-id="151fd-108">[Get-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh690014(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="151fd-108">[Get-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh690014(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="151fd-109">[New-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh690022(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="151fd-109">[New-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh690022(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="151fd-110">[Remove-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh690054(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="151fd-110">[Remove-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh690054(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="151fd-111">[Set-csautodiscoverconfiguration](https://technet.microsoft.com/library/Hh689980(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="151fd-111">[Set-CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh689980(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="151fd-112">[新 CsWebLink](https://technet.microsoft.com/library/Hh690053(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="151fd-112">[New-CsWebLink](https://technet.microsoft.com/library/Hh690053(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="151fd-113">[Get-csmcxconfiguration](https://technet.microsoft.com/library/Hh690031(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="151fd-113">[Get-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690031(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="151fd-114">[新 CsMcxConfiguration](https://technet.microsoft.com/library/Hh690035(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="151fd-114">[New-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690035(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="151fd-115">[Remove-csmcxconfiguration](https://technet.microsoft.com/library/Hh690026(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="151fd-115">[Remove-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690026(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="151fd-116">[Set-csmcxconfiguration](https://technet.microsoft.com/library/Hh690050(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="151fd-116">[Set-CsMcxConfiguration](https://technet.microsoft.com/library/Hh690050(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="151fd-117">[Get-csmobilitypolicy](https://technet.microsoft.com/library/Hh690017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="151fd-117">[Get-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690017(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="151fd-118">[Grant-csmobilitypolicy](https://technet.microsoft.com/library/Hh690038(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="151fd-118">[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690038(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="151fd-119">[新 CsMobilityPolicy](https://technet.microsoft.com/library/Hh689987(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="151fd-119">[New-CsMobilityPolicy](https://technet.microsoft.com/library/Hh689987(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="151fd-120">[Remove-csmobilitypolicy](https://technet.microsoft.com/library/Hh690048(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="151fd-120">[Remove-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690048(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="151fd-121">[Set-csmobilitypolicy](https://technet.microsoft.com/library/Hh690021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="151fd-121">[Set-CsMobilityPolicy](https://technet.microsoft.com/library/Hh690021(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="151fd-122">[Get-cspushnotificationconfiguration](https://technet.microsoft.com/library/Hh690049(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="151fd-122">[Get-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690049(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="151fd-123">[New-cspushnotificationconfiguration](https://technet.microsoft.com/library/Hh690027(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="151fd-123">[New-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690027(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="151fd-124">[Remove-cspushnotificationconfiguration](https://technet.microsoft.com/library/Hh690028(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="151fd-124">[Remove-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690028(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="151fd-125">[Set-cspushnotificationconfiguration](https://technet.microsoft.com/library/Hh690013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="151fd-125">[Set-CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690013(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="151fd-126">[Test-csmcxconference](https://technet.microsoft.com/library/Hh690045(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="151fd-126">[Test-CsMcxConference](https://technet.microsoft.com/library/Hh690045(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="151fd-127">[Test-csmcxp2pim](https://technet.microsoft.com/library/Hh690020(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="151fd-127">[Test-CsMcxP2PIM](https://technet.microsoft.com/library/Hh690020(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="151fd-128">[Test-csmcxpushnotification](https://technet.microsoft.com/library/Hh690043(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="151fd-128">[Test-CsMcxPushNotification](https://technet.microsoft.com/library/Hh690043(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="151fd-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="151fd-129">See Also</span></span>


[<span data-ttu-id="151fd-130">Lync Server PowerShell 部落格</span><span class="sxs-lookup"><span data-stu-id="151fd-130">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

