---
title: Lync Server 2013：語音原則 Cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice policy cmdlets
ms:assetid: 92744ec6-754d-498b-b430-dcd5c985ce10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415663(v=OCS.15)
ms:contentKeyID: 48184800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00f45a7da053dd6dc150ae99e93b780117ba01e1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-policy-cmdlets-in-lync-server-2013"></a><span data-ttu-id="fa93a-102">Lync Server 2013 中的語音原則 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="fa93a-102">Voice policy cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa93a-103">_**主題上次修改日期：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="fa93a-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="fa93a-104">管理企業語音包括設定語音原則和撥號方案等專案，以及將語音原則與語音路由建立關聯。</span><span class="sxs-lookup"><span data-stu-id="fa93a-104">Managing Enterprise Voice includes configuring such things as voice policies and dial plans, and associating voice policies with voice routes.</span></span> <span data-ttu-id="fa93a-105">與管理語音原則相關的 Cmdlet 可用來設定同時撥打的功能（每次有人呼叫您的 office phone 時都有第二個電話響鈴）、來電轉接及撥號需求。</span><span class="sxs-lookup"><span data-stu-id="fa93a-105">Cmdlets related to managing voice policies can be used to set features such as simultaneous ringing (the ability to have a second phone ring each time someone calls your office phone), call forwarding, and dialing requirement.</span></span>

<div>

## <a name="voice-policy-cmdlets"></a><span data-ttu-id="fa93a-106">語音原則 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="fa93a-106">Voice Policy Cmdlets</span></span>

<span data-ttu-id="fa93a-107">下列 Cmdlet 可用來管理企業語音的語音原則和撥號方案。</span><span class="sxs-lookup"><span data-stu-id="fa93a-107">The following cmdlets can be used to manage voice policies and dial plans for Enterprise Voice.</span></span>

<span data-ttu-id="fa93a-108">**語音原則**</span><span class="sxs-lookup"><span data-stu-id="fa93a-108">**Voice Policy**</span></span>

  - <span></span>  
    <span data-ttu-id="fa93a-109">[CsDialPlan](https://technet.microsoft.com/en-us/library/Gg413043(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fa93a-109">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg413043(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fa93a-110">[授與 CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398547(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fa93a-110">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398547(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fa93a-111">[新-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg425860(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fa93a-111">[New-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg425860(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fa93a-112">[移除-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398791(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fa93a-112">[Remove-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398791(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fa93a-113">[Set-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398644(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fa93a-113">[Set-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg398644(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fa93a-114">[Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fa93a-114">[Test-CsDialPlan](https://technet.microsoft.com/en-us/library/Gg399024(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fa93a-115">[CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg412734(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fa93a-115">[Get-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg412734(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fa93a-116">[Set-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg399069(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fa93a-116">[Set-CsPstnUsage](https://technet.microsoft.com/en-us/library/Gg399069(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="fa93a-117">[CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398101(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fa93a-117">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398101(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fa93a-118">[授與 CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398828(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fa93a-118">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398828(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fa93a-119">[New-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg425856(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fa93a-119">[New-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg425856(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fa93a-120">[移除-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398309(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fa93a-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398309(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fa93a-121">[Set-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg399021(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fa93a-121">[Set-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg399021(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="fa93a-122">[Test-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="fa93a-122">[Test-CsVoicePolicy](https://technet.microsoft.com/en-us/library/Gg398310(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fa93a-123">請參閱</span><span class="sxs-lookup"><span data-stu-id="fa93a-123">See Also</span></span>


[<span data-ttu-id="fa93a-124">Lync Server 2013 中的企業語音 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="fa93a-124">Enterprise Voice cmdlets in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-cmdlets.md)  


[<span data-ttu-id="fa93a-125">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="fa93a-125">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

