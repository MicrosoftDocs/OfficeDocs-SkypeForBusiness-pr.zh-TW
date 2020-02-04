---
title: Lync Server 2013： Active Directory Cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory cmdlets
ms:assetid: 313d73cb-f3db-4bc4-8708-de4da1d719c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415640(v=OCS.15)
ms:contentKeyID: 48183769
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f77009f20cfbd3e76f5cfc3786bcd9fa9ba2be9b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-cmdlets-in-lync-server-2013"></a><span data-ttu-id="1bf69-102">Lync Server 2013 中的 Active Directory Cmdlet</span><span class="sxs-lookup"><span data-stu-id="1bf69-102">Active Directory cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1bf69-103">_**主題上次修改日期：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="1bf69-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="1bf69-104">Active Directory Cmdlet 通常是由安裝程式所使用，而且很少會由系統管理員直接呼叫。</span><span class="sxs-lookup"><span data-stu-id="1bf69-104">The Active Directory cmdlets are typically used by Setup, and will rarely be called directly by an administrator.</span></span> <span data-ttu-id="1bf69-105">不過，管理員可以使用這些 Cmdlet 來準備（或 unprepare） Microsoft Lync Server 2013 的網域或林，以及安裝所需的 Active Directory 架構檔案。</span><span class="sxs-lookup"><span data-stu-id="1bf69-105">However, administrators can use these cmdlets to prepare (or unprepare) a domain or forest for Microsoft Lync Server 2013, and to install the required Active Directory schema files.</span></span>

<div>

## <a name="active-directory-cmdlets"></a><span data-ttu-id="1bf69-106">Active Directory Cmdlet</span><span class="sxs-lookup"><span data-stu-id="1bf69-106">Active Directory Cmdlets</span></span>

<span data-ttu-id="1bf69-107">以下是直接與管理 Lync Server 2013 Active Directory 設定相關的 Cmdlet 清單：</span><span class="sxs-lookup"><span data-stu-id="1bf69-107">The following is a list of cmdlets that relate directly to managing Lync Server 2013 Active Directory settings:</span></span>

<span data-ttu-id="1bf69-108">**Active Directory**</span><span class="sxs-lookup"><span data-stu-id="1bf69-108">**Active Directory**</span></span>

  - <span></span>  
    <span data-ttu-id="1bf69-109">[Disable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1bf69-109">[Disable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398785(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1bf69-110">[Enable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg412764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1bf69-110">[Enable-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg412764(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1bf69-111">[CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398453(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1bf69-111">[Get-CsAdDomain](https://technet.microsoft.com/en-us/library/Gg398453(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1bf69-112">[Disable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg398122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1bf69-112">[Disable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg398122(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1bf69-113">[Enable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg425713(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1bf69-113">[Enable-CsAdForest](https://technet.microsoft.com/en-us/library/Gg425713(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1bf69-114">[CsAdForest](https://technet.microsoft.com/en-us/library/Gg412995(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1bf69-114">[Get-CsAdForest](https://technet.microsoft.com/en-us/library/Gg412995(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="1bf69-115">[CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg413070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1bf69-115">[Get-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg413070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="1bf69-116">[Install-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg398681(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="1bf69-116">[Install-CsAdServerSchema](https://technet.microsoft.com/en-us/library/Gg398681(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1bf69-117">請參閱</span><span class="sxs-lookup"><span data-stu-id="1bf69-117">See Also</span></span>


[<span data-ttu-id="1bf69-118">Lync Server PowerShell 博客</span><span class="sxs-lookup"><span data-stu-id="1bf69-118">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

