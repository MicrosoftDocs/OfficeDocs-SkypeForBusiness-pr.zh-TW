---
title: Lync Server 2013： 信任的應用程式 cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Trusted applications cmdlets
ms:assetid: 4d6ae0dc-e3e0-4519-8b74-9e941dea21e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415652(v=OCS.15)
ms:contentKeyID: 48184071
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 409712a4c29db1c275ae24cc1fe78507342fa27c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193276"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="trusted-applications-cmdlets-in-lync-server-2013"></a><span data-ttu-id="0eb95-102">Lync Server 2013 的信任的應用程式 cmdlet</span><span class="sxs-lookup"><span data-stu-id="0eb95-102">Trusted applications cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0eb95-103">_**主題上次修改日期：** 2012年-06-20 個_</span><span class="sxs-lookup"><span data-stu-id="0eb95-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="0eb95-104">信任的應用程式是由協力廠商是指定信任的狀態] 以執行組件的 Microsoft Lync Server 2013，但不是內建的組件的產品開發應用程式。</span><span class="sxs-lookup"><span data-stu-id="0eb95-104">A trusted application is an application developed by a third party that is given trusted status to run as part of Microsoft Lync Server 2013 but that is not a built-in part of the product.</span></span> <span data-ttu-id="0eb95-105">Lync Server 2013 提供指令程式可以用來設定與管理信任的應用程式。</span><span class="sxs-lookup"><span data-stu-id="0eb95-105">Lync Server 2013 provides cmdlets that can be used to configure and managed trusted applications.</span></span>

<div>

## <a name="trusted-applications-cmdlets"></a><span data-ttu-id="0eb95-106">信任的應用程式 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="0eb95-106">Trusted Applications Cmdlets</span></span>

<span data-ttu-id="0eb95-107">使用下列 Cmdlet 來管理信任的應用程式。</span><span class="sxs-lookup"><span data-stu-id="0eb95-107">Use the following cmdlets to manage trusted applications.</span></span>

<span data-ttu-id="0eb95-108">**信任的應用程式**</span><span class="sxs-lookup"><span data-stu-id="0eb95-108">**Trusted Applications**</span></span>

  - <span></span>  
    <span data-ttu-id="0eb95-109">[Get-cstrustedapplication](https://technet.microsoft.com/library/Gg399025(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0eb95-109">[Get-CsTrustedApplication](https://technet.microsoft.com/library/Gg399025(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0eb95-110">[新 CsTrustedApplication](https://technet.microsoft.com/library/Gg398259(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0eb95-110">[New-CsTrustedApplication](https://technet.microsoft.com/library/Gg398259(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0eb95-111">[Remove-cstrustedapplication](https://technet.microsoft.com/library/Gg398176(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0eb95-111">[Remove-CsTrustedApplication](https://technet.microsoft.com/library/Gg398176(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0eb95-112">[設定 CsTrustedApplication](https://technet.microsoft.com/library/Gg425840(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0eb95-112">[Set-CsTrustedApplication](https://technet.microsoft.com/library/Gg425840(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0eb95-113">[取得 CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg425843(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0eb95-113">[Get-CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg425843(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0eb95-114">[新 CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398405(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0eb95-114">[New-CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398405(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0eb95-115">[移除 CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398838(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0eb95-115">[Remove-CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398838(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0eb95-116">[取得 CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg413035(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0eb95-116">[Get-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg413035(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0eb95-117">[新 CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398594(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0eb95-117">[New-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398594(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0eb95-118">[移除 CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398837(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0eb95-118">[Remove-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398837(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0eb95-119">[設定 CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398509(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0eb95-119">[Set-CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398509(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="0eb95-120">[取得 CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg413055(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0eb95-120">[Get-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg413055(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0eb95-121">[新 CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg425804(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0eb95-121">[New-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg425804(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0eb95-122">[移除 CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg398750(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0eb95-122">[Remove-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg398750(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="0eb95-123">[設定 CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg398187(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="0eb95-123">[Set-CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg398187(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0eb95-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0eb95-124">See Also</span></span>


[<span data-ttu-id="0eb95-125">Lync Server PowerShell 部落格</span><span class="sxs-lookup"><span data-stu-id="0eb95-125">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

