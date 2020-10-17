---
title: Lync Server 2013： ProgressReport view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport view
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49733790
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 492f7f5e34631de5ff843a00dd3fdf75b6f32f00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513220"
---
# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="ad164-102">Lync Server 2013 中的 ProgressReport 視圖</span><span class="sxs-lookup"><span data-stu-id="ad164-102">ProgressReport view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad164-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ad164-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ad164-104">ProgressReport view 儲存已完成會話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ad164-104">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="ad164-105">進度報告只會寫入 Lync Server 2013 決定可用於診斷目的的呼叫和會話。</span><span class="sxs-lookup"><span data-stu-id="ad164-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="ad164-106">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="ad164-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ad164-107">ErrorTime、ErrorReportSeq 及 ProgressReportSeq 欄位不一定和錯誤有關，而是有關指出通話或訊息狀態的訊息。</span><span class="sxs-lookup"><span data-stu-id="ad164-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad164-108">欄</span><span class="sxs-lookup"><span data-stu-id="ad164-108">Column</span></span></th>
<th><span data-ttu-id="ad164-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="ad164-109">Data Type</span></span></th>
<th><span data-ttu-id="ad164-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="ad164-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad164-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="ad164-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ad164-112">datetime</span><span class="sxs-lookup"><span data-stu-id="ad164-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="ad164-113">發生錯誤的時間。</span><span class="sxs-lookup"><span data-stu-id="ad164-113">Time of error occurred.</span></span> <span data-ttu-id="ad164-114">與 ErrorReportSeq 搭配使用，以唯一識別錯誤。</span><span class="sxs-lookup"><span data-stu-id="ad164-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad164-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ad164-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ad164-116">int</span><span class="sxs-lookup"><span data-stu-id="ad164-116">int</span></span></p></td>
<td><p><span data-ttu-id="ad164-117">用以識別錯誤的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="ad164-117">ID number to identify the error.</span></span> <span data-ttu-id="ad164-118">與 ErrorTime 搭配使用，以唯一識別錯誤。</span><span class="sxs-lookup"><span data-stu-id="ad164-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad164-119"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ad164-119"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ad164-120">int</span><span class="sxs-lookup"><span data-stu-id="ad164-120">int</span></span></p></td>
<td><p><span data-ttu-id="ad164-121">識別進度報表的識別碼。</span><span class="sxs-lookup"><span data-stu-id="ad164-121">ID to identify the progress report.</span></span> <span data-ttu-id="ad164-122">用來區分相同錯誤報表的進度報告。</span><span class="sxs-lookup"><span data-stu-id="ad164-122">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad164-123"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="ad164-123"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="ad164-124">int</span><span class="sxs-lookup"><span data-stu-id="ad164-124">int</span></span></p></td>
<td><p><span data-ttu-id="ad164-125">錯誤報表的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="ad164-125">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad164-126"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="ad164-126"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="ad164-127">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="ad164-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ad164-128">起源錯誤的伺服器名稱 (如果報告是從伺服器元件傳送) 中。</span><span class="sxs-lookup"><span data-stu-id="ad164-128">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad164-129"><strong>應用程式</strong></span><span class="sxs-lookup"><span data-stu-id="ad164-129"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="ad164-130">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="ad164-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ad164-131">起源錯誤的應用程式名稱 (如果報告是從伺服器元件傳送) 。</span><span class="sxs-lookup"><span data-stu-id="ad164-131">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad164-132"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="ad164-132"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="ad164-133">唯一</span><span class="sxs-lookup"><span data-stu-id="ad164-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ad164-134">與會議相關聯之不同元件的加入時間資訊的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="ad164-134">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad164-135"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="ad164-135"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ad164-136">int</span><span class="sxs-lookup"><span data-stu-id="ad164-136">int</span></span></p></td>
<td><p><span data-ttu-id="ad164-137">特定元件加入會議所需的時間 (（毫秒）) 。</span><span class="sxs-lookup"><span data-stu-id="ad164-137">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad164-138"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="ad164-138"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="ad164-139">Varchar (max) </span><span class="sxs-lookup"><span data-stu-id="ad164-139">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="ad164-140">其他錯誤資訊。</span><span class="sxs-lookup"><span data-stu-id="ad164-140">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

