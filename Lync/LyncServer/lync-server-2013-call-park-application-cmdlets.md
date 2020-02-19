---
title: Lync Server 2013： 通話駐留應用程式 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park application cmdlets
ms:assetid: 30cc001f-b29e-4d44-bad7-65e1133e67b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415639(v=OCS.15)
ms:contentKeyID: 48183764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d616a10282deaa7b62c5dfc0783e58c919128b8d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-park-application-cmdlets-in-lync-server-2013"></a><span data-ttu-id="c44d3-102">Lync Server 2013 中的通話駐留應用程式 cmdlet</span><span class="sxs-lookup"><span data-stu-id="c44d3-102">Call Park application cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c44d3-103">_**主題上次修改日期：** 2012年-03-21_</span><span class="sxs-lookup"><span data-stu-id="c44d3-103">_**Topic Last Modified:** 2012-03-21_</span></span>

<span data-ttu-id="c44d3-104">通話駐留應用程式可讓使用者撥打通話保留，然後從不同的電話中擷取該通話。</span><span class="sxs-lookup"><span data-stu-id="c44d3-104">Call Park application allows a user to place a call on hold, then retrieve that call from a different phone.</span></span> <span data-ttu-id="c44d3-105">使用這些 cmdlet 來設定通話駐留軌道和通話駐留應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="c44d3-105">Use these cmdlets to configure settings for call park orbits and the Call Park application.</span></span>

<div>

## <a name="call-park-application-cmdlets"></a><span data-ttu-id="c44d3-106">Call Park Application Cmdlets</span><span class="sxs-lookup"><span data-stu-id="c44d3-106">Call Park Application Cmdlets</span></span>

<span data-ttu-id="c44d3-107">下列指令程式可用來管理通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="c44d3-107">The following cmdlets can be used to manage Call Park application.</span></span>

<span data-ttu-id="c44d3-108">**通話保留應用程式**</span><span class="sxs-lookup"><span data-stu-id="c44d3-108">**Call Park Application**</span></span>

  - <span></span>  
    <span data-ttu-id="c44d3-109">[Get-cscallparkorbit](https://technet.microsoft.com/library/Gg398554(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c44d3-109">[Get-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398554(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c44d3-110">[新 CsCallParkOrbit](https://technet.microsoft.com/library/Gg398936(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c44d3-110">[New-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398936(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c44d3-111">[Remove-cscallparkorbit](https://technet.microsoft.com/library/Gg412901(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c44d3-111">[Remove-CsCallParkOrbit](https://technet.microsoft.com/library/Gg412901(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c44d3-112">[設定 CsCallParkOrbit](https://technet.microsoft.com/library/Gg398796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c44d3-112">[Set-CsCallParkOrbit](https://technet.microsoft.com/library/Gg398796(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c44d3-113">[Set-cscallparkservicemusiconholdfile](https://technet.microsoft.com/library/Gg412836(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c44d3-113">[Set-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/library/Gg412836(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c44d3-114">[取得 CsCpsConfiguration](https://technet.microsoft.com/library/Gg398948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c44d3-114">[Get-CsCpsConfiguration](https://technet.microsoft.com/library/Gg398948(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c44d3-115">[新 CsCpsConfiguration](https://technet.microsoft.com/library/Gg412919(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c44d3-115">[New-CsCpsConfiguration](https://technet.microsoft.com/library/Gg412919(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c44d3-116">[移除 CsCpsConfiguration](https://technet.microsoft.com/library/Gg398358(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c44d3-116">[Remove-CsCpsConfiguration](https://technet.microsoft.com/library/Gg398358(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c44d3-117">[Set-cscpsconfiguration](https://technet.microsoft.com/library/Gg412721(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c44d3-117">[Set-CsCpsConfiguration](https://technet.microsoft.com/library/Gg412721(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c44d3-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c44d3-118">See Also</span></span>


[<span data-ttu-id="c44d3-119">Lync Server PowerShell 部落格</span><span class="sxs-lookup"><span data-stu-id="c44d3-119">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

