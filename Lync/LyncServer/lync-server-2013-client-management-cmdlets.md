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
ms.openlocfilehash: 61854b9205c2c195d38d0252421357b94104e7e3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="client-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="c16c5-102">Lync Server 2013 中的用戶端管理 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c16c5-102">Client management cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c16c5-103">_**主題上次修改日期：** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="c16c5-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="c16c5-104">用戶端管理主要主要是決定 (（例如 Microsoft Lync 2013) ）可登入 Lync Server 2013 的用戶端應用程式，以及決定用戶端應用程式在登入之後可使用的功能。</span><span class="sxs-lookup"><span data-stu-id="c16c5-104">Client management consists primarily of determining which client applications (such as Microsoft Lync 2013) will be allowed to log on to Lync Server 2013 and determining the capabilities available to those client applications after they have logged on.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="c16c5-105">如需 Cmdlet 的詳細資訊，請參閱 Lync Server &nbsp; Windows PowerShell 的博客，網址為 <A href="https://go.microsoft.com/fwlink/p/?linkid=263432">https://go.microsoft.com/fwlink/p/?linkId=263432</A> 。</span><span class="sxs-lookup"><span data-stu-id="c16c5-105">For additional information about cmdlets, see the Lync Server&nbsp;Windows PowerShell Blog at <A href="https://go.microsoft.com/fwlink/p/?linkid=263432">https://go.microsoft.com/fwlink/p/?linkId=263432</A>.</span></span> <span data-ttu-id="c16c5-106">每個網誌的內容及其 URL 如有變更，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="c16c5-106">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

<div>

## <a name="client-management-cmdlets"></a><span data-ttu-id="c16c5-107">用戶端管理 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="c16c5-107">Client Management Cmdlets</span></span>

<span data-ttu-id="c16c5-108">大多數適用于用戶端管理的管理工作可以從 Lync Server 2013 控制台執行。</span><span class="sxs-lookup"><span data-stu-id="c16c5-108">Most management tasks that apply to client management can be performed from the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="c16c5-109">您可以使用 Lync Server 管理命令介面或腳本中的 Cmdlet 執行這些相同的工作。</span><span class="sxs-lookup"><span data-stu-id="c16c5-109">These same tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="c16c5-110">您可以利用指令碼來自動執行某些工作。</span><span class="sxs-lookup"><span data-stu-id="c16c5-110">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="c16c5-111">以下是與用戶端管理直接相關的 Cmdlet 清單：</span><span class="sxs-lookup"><span data-stu-id="c16c5-111">The following is a list of cmdlets that relate directly to client management:</span></span>

  - <span></span>  
    <span data-ttu-id="c16c5-112">[Get-CsClientPolicy](https://technet.microsoft.com/library/Gg398830(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c16c5-112">[Get-CsClientPolicy](https://technet.microsoft.com/library/Gg398830(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c16c5-113">[Grant-CsClientPolicy](https://technet.microsoft.com/library/Gg412942(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c16c5-113">[Grant-CsClientPolicy](https://technet.microsoft.com/library/Gg412942(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c16c5-114">[New-CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c16c5-114">[New-CsClientPolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c16c5-115">[Remove-CsClientPolicy](https://technet.microsoft.com/library/Gg425772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c16c5-115">[Remove-CsClientPolicy](https://technet.microsoft.com/library/Gg425772(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c16c5-116">[Set-CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c16c5-116">[Set-CsClientPolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c16c5-117">[New-CsClientPolicyEntry](https://technet.microsoft.com/library/Gg399046(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c16c5-117">[New-CsClientPolicyEntry](https://technet.microsoft.com/library/Gg399046(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c16c5-118">[Get-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399072(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c16c5-118">[Get-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399072(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c16c5-119">[新 Set-csclientversionconfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c16c5-119">[New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c16c5-120">[Remove-Set-csclientversionconfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c16c5-120">[Remove-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c16c5-121">[Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c16c5-121">[Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c16c5-122">[Get-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398957(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c16c5-122">[Get-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398957(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c16c5-123">[授與 Get-csclientversionpolicy](https://technet.microsoft.com/library/Gg412903(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c16c5-123">[Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg412903(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c16c5-124">[New-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398709(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c16c5-124">[New-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398709(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c16c5-125">[Remove-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg425801(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c16c5-125">[Remove-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg425801(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c16c5-126">[Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c16c5-126">[Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="c16c5-127">[Get-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg413048(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c16c5-127">[Get-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg413048(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c16c5-128">[New-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398905(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c16c5-128">[New-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398905(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c16c5-129">[Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398541(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c16c5-129">[Remove-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398541(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="c16c5-130">[CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg425790(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c16c5-130">[Set-CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg425790(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

