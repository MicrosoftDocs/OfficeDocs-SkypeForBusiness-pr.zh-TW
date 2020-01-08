---
title: Lync Server 2013：企業語音 Cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enterprise Voice cmdlets
ms:assetid: 7d7c6d94-3ead-4d99-95f7-c31b448ab9e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415658(v=OCS.15)
ms:contentKeyID: 48184613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf902a7711625121335bc2f387301b8b9457a73c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-cmdlets-in-lync-server-2013"></a><span data-ttu-id="3ecd9-102">Lync Server 2013 中的企業語音 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="3ecd9-102">Enterprise Voice cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ecd9-103">_**主題上次修改日期：** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="3ecd9-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="3ecd9-104">企業語音是 Microsoft 通過 IP （VoIP）執行的語音。</span><span class="sxs-lookup"><span data-stu-id="3ecd9-104">Enterprise Voice is the Microsoft implementation of Voice over IP (VoIP).</span></span> <span data-ttu-id="3ecd9-105">在 Microsoft Lync Server 2013 中管理企業語音的 Cmdlet 可讓您建立及修改撥號方案（先前稱為位置設定檔）、語音原則、路由及正常化規則。</span><span class="sxs-lookup"><span data-stu-id="3ecd9-105">The cmdlets available for managing Enterprise Voice in Microsoft Lync Server 2013 will allow you to create and modify dial plans (formerly known as location profiles), voice policies, routes, and normalization rules.</span></span>

<div>

## <a name="enterprise-voice-cmdlets"></a><span data-ttu-id="3ecd9-106">企業語音 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="3ecd9-106">Enterprise Voice Cmdlets</span></span>

<span data-ttu-id="3ecd9-107">大多數適用于企業語音的管理工作，都可以從 Lync Server [控制台] 執行。</span><span class="sxs-lookup"><span data-stu-id="3ecd9-107">Most management tasks that apply to Enterprise Voice can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="3ecd9-108">您可以使用 Lync Server 管理命令介面或腳本中的 Cmdlet 來執行這些相同的工作，讓您能夠自動執行特定工作。</span><span class="sxs-lookup"><span data-stu-id="3ecd9-108">These same tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script, allowing you to automate certain tasks.</span></span> <span data-ttu-id="3ecd9-109">以下是直接與管理企業語音相關的 Cmdlet 清單：</span><span class="sxs-lookup"><span data-stu-id="3ecd9-109">The following is a list of cmdlets that relate directly to managing Enterprise Voice:</span></span>

<span data-ttu-id="3ecd9-110">**[在 Lync Server 2013 中疑難排解企業語音 Cmdlet](lync-server-2013-troubleshooting-enterprise-voice-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="3ecd9-110">**[Troubleshooting Enterprise Voice cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-enterprise-voice-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-111">[CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-111">[Get-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-112">[移除-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-112">[Remove-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398804(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-113">[Set-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398967(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-113">[Set-CsVoiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398967(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3ecd9-114">[CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-114">[Get-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412957(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-115">[新-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398961(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-115">[New-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398961(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-116">[移除-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412813(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-116">[Remove-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg412813(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-117">[Set-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398614(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-117">[Set-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398614(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-118">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398260(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-118">[Test-CsVoiceTestConfiguration](https://technet.microsoft.com/en-us/library/Gg398260(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3ecd9-119">[Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-119">[Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3ecd9-120">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg399003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-120">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg399003(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3ecd9-121">[Test-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-121">[Test-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3ecd9-122">[Test-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-122">[Test-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3ecd9-123">[Test-CsVoiceUser](https://technet.microsoft.com/en-us/library/Gg413013(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-123">[Test-CsVoiceUser](https://technet.microsoft.com/en-us/library/Gg413013(v=OCS.15))</span></span>

<span data-ttu-id="3ecd9-124">**[Lync Server 2013 中的語音正常化規則 Cmdlet](lync-server-2013-voice-normalization-rules-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="3ecd9-124">**[Voice normalization rules cmdlets in Lync Server 2013](lync-server-2013-voice-normalization-rules-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-125">[CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398393(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-125">[Get-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398393(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-126">[新-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398240(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-126">[New-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398240(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-127">[移除-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398501(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-127">[Remove-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398501(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-128">[Set-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398491(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-128">[Set-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg398491(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-129">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg399003(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-129">[Test-CsVoiceNormalizationRule](https://technet.microsoft.com/en-us/library/Gg399003(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3ecd9-130">[新-CsVoiceRegex](https://technet.microsoft.com/en-us/library/Gg412751(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-130">[New-CsVoiceRegex](https://technet.microsoft.com/en-us/library/Gg412751(v=OCS.15))</span></span>

<span data-ttu-id="3ecd9-131">**[Lync Server 2013 中的語音原則 Cmdlet](lync-server-2013-voice-policy-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="3ecd9-131">**[Voice policy cmdlets in Lync Server 2013](lync-server-2013-voice-policy-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-132">[CsDialPlan](https://technet.microsoft.com/en-us/library/Gg413043(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-132">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg413043(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-133">[授與 CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398547(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-133">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398547(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-134">[新-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg425860(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-134">[New-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg425860(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-135">[移除-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398791(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-135">[Remove-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398791(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-136">[Set-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398644(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-136">[Set-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398644(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-137">[Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-137">[Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3ecd9-138">[CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg412734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-138">[Get-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg412734(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-139">[Set-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg399069(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-139">[Set-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg399069(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3ecd9-140">[CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398101(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-140">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398101(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-141">[授與 CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398828(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-141">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398828(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-142">[New-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg425856(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-142">[New-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg425856(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-143">[移除-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398309(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-143">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398309(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-144">[Set-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg399021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-144">[Set-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg399021(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-145">[Test-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-145">[Test-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))</span></span>

<span data-ttu-id="3ecd9-146">**[Lync Server 2013 中的語音路由 Cmdlet](lync-server-2013-voice-routing-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="3ecd9-146">**[Voice routing cmdlets in Lync Server 2013](lync-server-2013-voice-routing-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-147">[CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-147">[Get-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg425851(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-148">[新-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg399056(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-148">[New-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg399056(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-149">[移除-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398643(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-149">[Remove-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg398643(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-150">[Set-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-150">[Set-CsRoutingConfiguration](https://technet.microsoft.com/en-us/library/Gg412811(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3ecd9-151">[CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-151">[Get-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-152">[新-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398197(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-152">[New-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398197(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-153">[移除-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398468(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-153">[Remove-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg398468(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-154">[Set-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg412893(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-154">[Set-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg412893(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3ecd9-155">[Test-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3ecd9-155">[Test-CsVoiceRoute](https://technet.microsoft.com/en-us/library/Gg425873(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3ecd9-156">請參閱</span><span class="sxs-lookup"><span data-stu-id="3ecd9-156">See Also</span></span>


<span data-ttu-id="3ecd9-157">[Lync Server 2013 中的 [高級企業語音] Cmdlet](lync-server-2013-advanced-enterprise-voice-cmdlets.md)</span><span class="sxs-lookup"><span data-stu-id="3ecd9-157">[Advanced Enterprise Voice cmdlets in Lync Server 2013](lync-server-2013-advanced-enterprise-voice-cmdlets.md)</span></span>  
[<span data-ttu-id="3ecd9-158">Lync Server 2013 中的語音應用程式 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="3ecd9-158">Voice application cmdlets in Lync Server 2013</span></span>](lync-server-2013-voice-application-cmdlets.md)  


[<span data-ttu-id="3ecd9-159">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="3ecd9-159">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

