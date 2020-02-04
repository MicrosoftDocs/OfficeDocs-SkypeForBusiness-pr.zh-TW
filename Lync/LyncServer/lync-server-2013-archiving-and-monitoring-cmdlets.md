---
title: Lync Server 2013：存檔與監控 Cmdlet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Archiving and Monitoring cmdlets
ms:assetid: 04e1d0f6-d00e-4d8f-b969-daf092b2cdb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415629(v=OCS.15)
ms:contentKeyID: 48183281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58f7242ee62bb7f9796b1f8445d49dc5efd32c06
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="archiving-and-monitoring-cmdlets-in-lync-server-2013"></a><span data-ttu-id="3342a-102">Lync Server 2013 中的 [封存與監控] Cmdlet</span><span class="sxs-lookup"><span data-stu-id="3342a-102">Archiving and Monitoring cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3342a-103">_**主題上次修改日期：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="3342a-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="3342a-104">[封存與監控] Cmdlet 可讓系統管理員管理立即訊息和會議會話封存;記錄通話詳細資訊;以及使用體驗品質（QoE）來監視 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="3342a-104">The archiving and monitoring cmdlets enable administrators to manage instant message and conference session archiving; to record call detail information; and to monitor Microsoft Lync Server 2013 using Quality of Experience (QoE).</span></span>


> [!NOTE]
> <span data-ttu-id="3342a-105">如需有關 Cmdlet 的其他資訊，請參閱&nbsp;Lync Server Windows PowerShell <A href="http://go.microsoft.com/fwlink/p/?linkid=263432">http://go.microsoft.com/fwlink/p/?linkId=263432</A>博客（位於）。</span><span class="sxs-lookup"><span data-stu-id="3342a-105">For additional information about cmdlets, see the Lync Server&nbsp;Windows PowerShell Blog at <A href="http://go.microsoft.com/fwlink/p/?linkid=263432">http://go.microsoft.com/fwlink/p/?linkId=263432</A>.</span></span> <span data-ttu-id="3342a-106">每個博客及其 URL 的內容可能會變更，恕不另行通知。</span><span class="sxs-lookup"><span data-stu-id="3342a-106">The content of each blog and its URL are subject to change without notice.</span></span>



<div>

## <a name="archiving-and-monitoring-cmdlets"></a><span data-ttu-id="3342a-107">存檔與監控 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="3342a-107">Archiving and Monitoring Cmdlets</span></span>

<span data-ttu-id="3342a-108">以下是直接與管理封存與監控相關的 Cmdlet 清單：</span><span class="sxs-lookup"><span data-stu-id="3342a-108">The following is a list of cmdlets that relate directly to managing archiving and monitoring:</span></span>

<span data-ttu-id="3342a-109">**封存與監控**</span><span class="sxs-lookup"><span data-stu-id="3342a-109">**Archiving and Monitoring**</span></span>

  - <span></span>  
    <span data-ttu-id="3342a-110">[CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg399012(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-110">[Get-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg399012(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3342a-111">[新-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg398471(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-111">[New-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg398471(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3342a-112">[移除-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg398951(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-112">[Remove-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg398951(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3342a-113">[Set-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg413030(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-113">[Set-CsArchivingConfiguration](https://technet.microsoft.com/en-us/library/Gg413030(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3342a-114">[Export-CsArchivingData](https://technet.microsoft.com/en-us/library/Gg398452(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-114">[Export-CsArchivingData](https://technet.microsoft.com/en-us/library/Gg398452(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3342a-115">[Invoke-CsArchivingDatabasePurge](https://technet.microsoft.com/en-us/library/JJ204627(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-115">[Invoke-CsArchivingDatabasePurge](https://technet.microsoft.com/en-us/library/JJ204627(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3342a-116">[Get-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg425731(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-116">[Get-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg425731(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3342a-117">[授與 CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg398475(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-117">[Grant-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg398475(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3342a-118">[New-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg399032(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-118">[New-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg399032(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3342a-119">[Remove-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg425924(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-119">[Remove-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg425924(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3342a-120">[Set-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg398294(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-120">[Set-CsArchivingPolicy](https://technet.microsoft.com/en-us/library/Gg398294(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3342a-121">[Set-CsArchivingServer](https://technet.microsoft.com/en-us/library/Gg398923(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-121">[Set-CsArchivingServer](https://technet.microsoft.com/en-us/library/Gg398923(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3342a-122">[CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398298(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-122">[Get-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398298(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3342a-123">[新-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg399018(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-123">[New-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg399018(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3342a-124">[移除-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398451(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-124">[Remove-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398451(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3342a-125">[Set-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398774(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-125">[Set-CsCdrConfiguration](https://technet.microsoft.com/en-us/library/Gg398774(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3342a-126">[Set-CsMonitoringServer](https://technet.microsoft.com/en-us/library/Gg425776(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-126">[Set-CsMonitoringServer](https://technet.microsoft.com/en-us/library/Gg425776(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3342a-127">[CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg399004(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-127">[Get-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg399004(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3342a-128">[新-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg398325(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-128">[New-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg398325(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3342a-129">[移除-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg425879(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-129">[Remove-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg425879(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3342a-130">[Set-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg398245(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-130">[Set-CsQoEConfiguration](https://technet.microsoft.com/en-us/library/Gg398245(v=OCS.15))</span></span>

<span data-ttu-id="3342a-131">[Invoke-CsCdrDatabasePurge](https://technet.microsoft.com/en-us/library/JJ205113(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-131">[Invoke-CsCdrDatabasePurge](https://technet.microsoft.com/en-us/library/JJ205113(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3342a-132">[Export-CsArchivingData](https://technet.microsoft.com/en-us/library/Gg398452(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-132">[Export-CsArchivingData](https://technet.microsoft.com/en-us/library/Gg398452(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3342a-133">[Invoke-CsQoEDatabasePurge](https://technet.microsoft.com/en-us/library/JJ205247(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-133">[Invoke-CsQoEDatabasePurge](https://technet.microsoft.com/en-us/library/JJ205247(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3342a-134">[CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ205356(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-134">[Get-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ205356(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3342a-135">[新-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ204787(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-135">[New-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ204787(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3342a-136">[移除-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ204711(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-136">[Remove-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ204711(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3342a-137">[Set-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ205075(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-137">[Set-CsReportingConfiguration](https://technet.microsoft.com/en-us/library/JJ205075(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3342a-138">[CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ204759(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-138">[Get-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ204759(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3342a-139">[移除-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ204870(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-139">[Remove-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ204870(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3342a-140">[Set-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-140">[Set-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3342a-141">[CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-141">[Get-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204739(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3342a-142">[New-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ205254(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-142">[New-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ205254(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3342a-143">[移除-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-143">[Remove-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3342a-144">[Set-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204620(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-144">[Set-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204620(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="3342a-145">[Test-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204652(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-145">[Test-CsWatcherNodeConfiguration](https://technet.microsoft.com/en-us/library/JJ204652(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="3342a-146">[新-CsExtendedTest](https://technet.microsoft.com/en-us/library/JJ205275(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3342a-146">[New-CsExtendedTest](https://technet.microsoft.com/en-us/library/JJ205275(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

