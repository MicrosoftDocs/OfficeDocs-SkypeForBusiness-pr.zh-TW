---
title: Lync Server 2013：用戶端管理 Cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client management cmdlets
ms:assetid: 0384f8ab-453d-49d6-aaa7-52439e27b7e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398087(v=OCS.15)
ms:contentKeyID: 48183261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 023b7c165d1366d42303f4b609401fcc7bbe6a1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="c5853-102">Lync Server 2013 中的用戶端管理 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c5853-102">Client management cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5853-103">_**主題上次修改日期：** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="c5853-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="c5853-104">用戶端管理主要是決定允許哪些用戶端應用程式（例如 Microsoft Lync 2013）登入 Lync Server 2013，並決定這些用戶端應用程式在登入後可使用的功能。</span><span class="sxs-lookup"><span data-stu-id="c5853-104">Client management consists primarily of determining which client applications (such as Microsoft Lync 2013) will be allowed to log on to Lync Server 2013 and determining the capabilities available to those client applications after they have logged on.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="c5853-105">如需有關 Cmdlet 的其他資訊，請參閱&nbsp;Lync Server Windows PowerShell <A href="http://go.microsoft.com/fwlink/p/?linkid=263432">http://go.microsoft.com/fwlink/p/?linkId=263432</A>博客（位於）。</span><span class="sxs-lookup"><span data-stu-id="c5853-105">For additional information about cmdlets, see the Lync Server&nbsp;Windows PowerShell Blog at <A href="http://go.microsoft.com/fwlink/p/?linkid=263432">http://go.microsoft.com/fwlink/p/?linkId=263432</A>.</span></span> <span data-ttu-id="c5853-106">每個博客及其 URL 的內容可能會變更，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="c5853-106">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<div>

## <a name="client-management-cmdlets"></a><span data-ttu-id="c5853-107">用戶端管理 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c5853-107">Client Management Cmdlets</span></span>

<span data-ttu-id="c5853-108">大多數適用于用戶端管理的管理工作，都可以從 Lync Server 2013 [控制台] 執行。</span><span class="sxs-lookup"><span data-stu-id="c5853-108">Most management tasks that apply to client management can be performed from the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="c5853-109">您可以使用 Lync Server 管理命令介面或腳本中的 Cmdlet 來執行這些相同的工作。</span><span class="sxs-lookup"><span data-stu-id="c5853-109">These same tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="c5853-110">您可以使用腳本來自動執行特定工作。</span><span class="sxs-lookup"><span data-stu-id="c5853-110">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="c5853-111">以下是直接與用戶端管理相關的 Cmdlet 清單：</span><span class="sxs-lookup"><span data-stu-id="c5853-111">The following is a list of cmdlets that relate directly to client management:</span></span>

  - <span></span>  
    <span data-ttu-id="c5853-112">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398830(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5853-112">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398830(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c5853-113">[授與 CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg412942(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5853-113">[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg412942(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c5853-114">[New-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5853-114">[New-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425949(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c5853-115">[Remove-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5853-115">[Remove-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg425772(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c5853-116">[Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398300(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5853-116">[Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/Gg398300(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c5853-117">[新-CsClientPolicyEntry](https://technet.microsoft.com/en-us/library/Gg399046(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5853-117">[New-CsClientPolicyEntry](https://technet.microsoft.com/en-us/library/Gg399046(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c5853-118">[CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399072(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5853-118">[Get-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399072(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c5853-119">[新-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5853-119">[New-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c5853-120">[移除-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5853-120">[Remove-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c5853-121">[Set-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5853-121">[Set-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c5853-122">[Get-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5853-122">[Get-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398957(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c5853-123">[授與 CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg412903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5853-123">[Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg412903(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c5853-124">[New-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398709(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5853-124">[New-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398709(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c5853-125">[Remove-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg425801(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5853-125">[Remove-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg425801(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c5853-126">[Set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5853-126">[Set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c5853-127">[Get-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg413048(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5853-127">[Get-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg413048(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c5853-128">[New-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398905(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5853-128">[New-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398905(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c5853-129">[Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398541(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5853-129">[Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg398541(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c5853-130">[Set-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg425790(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c5853-130">[Set-CsClientVersionPolicyRule](https://technet.microsoft.com/en-us/library/Gg425790(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

