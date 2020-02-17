---
title: 'Lync Server 2013: ProgressReport 檢視'
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
ms.openlocfilehash: 916fb459e71460249b47719ab4a4c07f8d082e4d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="781ad-102">Lync Server 2013 中的 ProgressReport 檢視</span><span class="sxs-lookup"><span data-stu-id="781ad-102">ProgressReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="781ad-103">_**主題上次修改日期：** 2012年-10-01_</span><span class="sxs-lookup"><span data-stu-id="781ad-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="781ad-104">ProgressReport 檢視儲存已完成的工作階段的資訊。</span><span class="sxs-lookup"><span data-stu-id="781ad-104">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="781ad-105">進度報告將寫入僅適用於通話和 Lync Server 2013 會決定可能會很有用進行診斷之用的工作階段。</span><span class="sxs-lookup"><span data-stu-id="781ad-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="781ad-106">Microsoft Lync Server 2013 中已採用此檢視。</span><span class="sxs-lookup"><span data-stu-id="781ad-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="781ad-107">ErrorTime、ErrorReportSeq 及 ProgressReportSeq 欄位不一定和錯誤有關，而是有關指出通話或訊息狀態的訊息。</span><span class="sxs-lookup"><span data-stu-id="781ad-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="781ad-108">欄</span><span class="sxs-lookup"><span data-stu-id="781ad-108">Column</span></span></th>
<th><span data-ttu-id="781ad-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="781ad-109">Data Type</span></span></th>
<th><span data-ttu-id="781ad-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="781ad-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="781ad-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="781ad-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="781ad-112">datetime</span><span class="sxs-lookup"><span data-stu-id="781ad-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="781ad-113">發生錯誤的時間。</span><span class="sxs-lookup"><span data-stu-id="781ad-113">Time of error occurred.</span></span> <span data-ttu-id="781ad-114">搭配 ErrorReportSeq 用來唯一地識別錯誤。</span><span class="sxs-lookup"><span data-stu-id="781ad-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="781ad-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="781ad-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="781ad-116">int</span><span class="sxs-lookup"><span data-stu-id="781ad-116">int</span></span></p></td>
<td><p><span data-ttu-id="781ad-117">若要識別錯誤的識別碼。</span><span class="sxs-lookup"><span data-stu-id="781ad-117">ID number to identify the error.</span></span> <span data-ttu-id="781ad-118">ErrorTime 搭配使用來唯一地識別錯誤。</span><span class="sxs-lookup"><span data-stu-id="781ad-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="781ad-119"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="781ad-119"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="781ad-120">int</span><span class="sxs-lookup"><span data-stu-id="781ad-120">int</span></span></p></td>
<td><p><span data-ttu-id="781ad-121">若要識別進度報告的識別碼。</span><span class="sxs-lookup"><span data-stu-id="781ad-121">ID to identify the progress report.</span></span> <span data-ttu-id="781ad-122">用於區分相同的錯誤報告的進度報告。</span><span class="sxs-lookup"><span data-stu-id="781ad-122">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="781ad-123"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="781ad-123"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="781ad-124">int</span><span class="sxs-lookup"><span data-stu-id="781ad-124">int</span></span></p></td>
<td><p><span data-ttu-id="781ad-125">錯誤報告的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="781ad-125">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="781ad-126"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="781ad-126"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="781ad-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="781ad-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="781ad-128">錯誤源自 （如果報告從伺服器元件傳送） 的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="781ad-128">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="781ad-129"><strong>應用程式</strong></span><span class="sxs-lookup"><span data-stu-id="781ad-129"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="781ad-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="781ad-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="781ad-131">錯誤源自 （如果報告從伺服器元件傳送） 的應用程式的名稱。</span><span class="sxs-lookup"><span data-stu-id="781ad-131">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="781ad-132"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="781ad-132"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="781ad-133">唯一</span><span class="sxs-lookup"><span data-stu-id="781ad-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="781ad-134">相互關聯參與會議之不同元件的加入時間資訊的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="781ad-134">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="781ad-135"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="781ad-135"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="781ad-136">int</span><span class="sxs-lookup"><span data-stu-id="781ad-136">int</span></span></p></td>
<td><p><span data-ttu-id="781ad-137">時間 （以毫秒為單位） 所需的特定元件加入會議。</span><span class="sxs-lookup"><span data-stu-id="781ad-137">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="781ad-138"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="781ad-138"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="781ad-139">varchar(max)</span><span class="sxs-lookup"><span data-stu-id="781ad-139">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="781ad-140">其他錯誤資訊。</span><span class="sxs-lookup"><span data-stu-id="781ad-140">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

