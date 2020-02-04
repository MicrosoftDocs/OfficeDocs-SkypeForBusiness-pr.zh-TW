---
title: Lync Server 2013：通話駐留應用程式 Cmdlet
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
ms.openlocfilehash: 3ebd91f563348575e7498cd3441ffdadb35fec15
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-application-cmdlets-in-lync-server-2013"></a><span data-ttu-id="06983-102">在 Lync Server 2013 中通話駐留應用程式 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="06983-102">Call Park application cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06983-103">_**主題上次修改日期：** 2012-03-21_</span><span class="sxs-lookup"><span data-stu-id="06983-103">_**Topic Last Modified:** 2012-03-21_</span></span>

<span data-ttu-id="06983-104">通話寄存應用程式可讓使用者保留通話，然後從其他電話取回該通話。</span><span class="sxs-lookup"><span data-stu-id="06983-104">Call Park application allows a user to place a call on hold, then retrieve that call from a different phone.</span></span> <span data-ttu-id="06983-105">使用這些 Cmdlet 來設定通話駐留軌道式和通話駐留應用程式的設定。</span><span class="sxs-lookup"><span data-stu-id="06983-105">Use these cmdlets to configure settings for call park orbits and the Call Park application.</span></span>

<div>

## <a name="call-park-application-cmdlets"></a><span data-ttu-id="06983-106">通話駐留應用程式 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="06983-106">Call Park Application Cmdlets</span></span>

<span data-ttu-id="06983-107">下列 Cmdlet 可用來管理通話駐留應用程式。</span><span class="sxs-lookup"><span data-stu-id="06983-107">The following cmdlets can be used to manage Call Park application.</span></span>

<span data-ttu-id="06983-108">**通話駐留應用程式**</span><span class="sxs-lookup"><span data-stu-id="06983-108">**Call Park Application**</span></span>

  - <span></span>  
    <span data-ttu-id="06983-109">[CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398554(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="06983-109">[Get-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398554(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="06983-110">[新-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398936(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="06983-110">[New-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398936(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="06983-111">[移除-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg412901(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="06983-111">[Remove-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg412901(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="06983-112">[Set-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="06983-112">[Set-CsCallParkOrbit](https://technet.microsoft.com/en-us/library/Gg398796(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="06983-113">[Set-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/en-us/library/Gg412836(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="06983-113">[Set-CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/en-us/library/Gg412836(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="06983-114">[CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398948(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="06983-114">[Get-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398948(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="06983-115">[新-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412919(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="06983-115">[New-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412919(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="06983-116">[移除-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398358(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="06983-116">[Remove-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg398358(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="06983-117">[Set-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412721(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="06983-117">[Set-CsCpsConfiguration](https://technet.microsoft.com/en-us/library/Gg412721(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="06983-118">請參閱</span><span class="sxs-lookup"><span data-stu-id="06983-118">See Also</span></span>


[<span data-ttu-id="06983-119">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="06983-119">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

