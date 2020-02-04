---
title: Lync Server 2013：永久性聊天伺服器 Cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server cmdlets
ms:assetid: 5aa59edb-db57-406f-9fbd-54bf1a55d31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204920(v=OCS.15)
ms:contentKeyID: 48184226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5609939fa28a68e53f3b24cf469df4665bbaaa0b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="e1b27-102">Lync Server 2013 中的持續聊天伺服器 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e1b27-102">Persistent Chat Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1b27-103">_**主題上次修改日期：** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="e1b27-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="e1b27-104">永久聊天 Cmdlet 可讓您管理和設定 Microsoft Lync Server 2013 持續聊天服務（先前稱為群組聊天服務）。</span><span class="sxs-lookup"><span data-stu-id="e1b27-104">The Persistent Chat cmdlets enable you to manage and configure the Microsoft Lync Server 2013 Persistent Chat service (formerly known as the Group Chat service).</span></span> <span data-ttu-id="e1b27-105">持續聊天可讓使用者參與線上立即訊息會議。</span><span class="sxs-lookup"><span data-stu-id="e1b27-105">Persistent Chat enables users to participate in online instant messaging sessions.</span></span> <span data-ttu-id="e1b27-106">雖然這些會話可以即時進行，但每個會話的內容都是永久性的;也就是說，任何人都可以隨時繼續這些交談。</span><span class="sxs-lookup"><span data-stu-id="e1b27-106">Although these sessions can take place in real time, the content of each session is persistent; that means these conversations can be resumed by anyone at any time.</span></span>

<div>

## <a name="persistent-chat-cmdlets"></a><span data-ttu-id="e1b27-107">持續聊天 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e1b27-107">Persistent Chat Cmdlets</span></span>

<span data-ttu-id="e1b27-108">永久聊天 Cmdlet 可讓您管理和設定 Lync Server 持續聊天服務。</span><span class="sxs-lookup"><span data-stu-id="e1b27-108">The Persistent Chat cmdlets enable you to manage and configure the Lync Server Persistent Chat service.</span></span>

<span data-ttu-id="e1b27-109">**持續聊天 Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="e1b27-109">**Persistent Chat Cmdlets**</span></span>

  - <span data-ttu-id="e1b27-110">[CsAdPrincipal](https://technet.microsoft.com/en-us/library/JJ205326(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-110">[Get-CsAdPrincipal](https://technet.microsoft.com/en-us/library/JJ205326(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e1b27-111">[Set-CsPersistentChatActiveServer](https://technet.microsoft.com/en-us/library/JJ205065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-111">[Set-CsPersistentChatActiveServer](https://technet.microsoft.com/en-us/library/JJ205065(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e1b27-112">[CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204670(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-112">[Get-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204670(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-113">[New-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204641(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-113">[New-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204641(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-114">[移除-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ205350(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-114">[Remove-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ205350(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-115">[Set-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204721(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-115">[Set-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204721(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e1b27-116">[CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204771(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-116">[Get-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204771(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-117">[新-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-117">[New-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204803(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-118">[移除-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204660(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-118">[Remove-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204660(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-119">[Set-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204952(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-119">[Set-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204952(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e1b27-120">[CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204625(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-120">[Get-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204625(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-121">[新-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ205163(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-121">[New-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ205163(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-122">[移除-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204767(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-122">[Remove-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204767(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-123">[Set-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-123">[Set-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204949(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e1b27-124">[CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-124">[Get-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205140(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-125">[新-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205330(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-125">[New-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205330(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-126">[移除-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ204927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-126">[Remove-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ204927(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-127">[Set-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-127">[Set-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205122(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e1b27-128">[Export-CsPersistentChatData](https://technet.microsoft.com/en-us/library/JJ205378(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-128">[Export-CsPersistentChatData](https://technet.microsoft.com/en-us/library/JJ205378(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-129">[匯入-CsPersistentChatData](https://technet.microsoft.com/en-us/library/JJ204709(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-129">[Import-CsPersistentChatData](https://technet.microsoft.com/en-us/library/JJ204709(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e1b27-130">[CsPersistentChatEligiblePrincipal](https://technet.microsoft.com/en-us/library/JJ204891(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-130">[Get-CsPersistentChatEligiblePrincipal](https://technet.microsoft.com/en-us/library/JJ204891(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e1b27-131">[CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-131">[Get-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204764(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-132">[新-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-132">[New-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204811(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-133">[移除-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204626(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-133">[Remove-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204626(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e1b27-134">[移除-CsPersistentChatMessage](https://technet.microsoft.com/en-us/library/JJ204668(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-134">[Remove-CsPersistentChatMessage](https://technet.microsoft.com/en-us/library/JJ204668(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-135">[Test-CsPersistentChatMessage](https://technet.microsoft.com/en-us/library/JJ204656(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-135">[Test-CsPersistentChatMessage](https://technet.microsoft.com/en-us/library/JJ204656(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e1b27-136">[Get-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ204673(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-136">[Get-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ204673(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-137">[授與 CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ204907(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-137">[Grant-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ204907(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-138">[New-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205396(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-138">[New-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205396(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-139">[Remove-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205301(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-139">[Remove-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205301(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-140">[Set-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205192(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-140">[Set-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205192(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e1b27-141">[Clear-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204976(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-141">[Clear-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204976(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-142">[CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ205123(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-142">[Get-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ205123(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-143">[新-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ205166(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-143">[New-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ205166(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-144">[移除-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204639(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-144">[Remove-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204639(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-145">[Set-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204801(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-145">[Set-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204801(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="e1b27-146">[Get-CsPersistentChatState](https://technet.microsoft.com/en-us/library/JJ204915(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-146">[Get-CsPersistentChatState](https://technet.microsoft.com/en-us/library/JJ204915(v=OCS.15))</span></span>

  - <span data-ttu-id="e1b27-147">[Set-CsPersistentChatState](https://technet.microsoft.com/en-us/library/JJ205109(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e1b27-147">[Set-CsPersistentChatState](https://technet.microsoft.com/en-us/library/JJ205109(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

