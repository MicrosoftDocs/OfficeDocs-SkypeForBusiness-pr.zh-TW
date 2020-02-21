---
title: 'Lync Server 2013: ProgressReport 表格'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c68855f3f0ae36e0934959b820dc84a716cf2a51
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="13c23-102">Lync Server 2013 中的 ProgressReport 表格</span><span class="sxs-lookup"><span data-stu-id="13c23-102">ProgressReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13c23-103">_**主題上次修改日期：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="13c23-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="13c23-104">進度報告是以通話或工作階段完成時，用戶端上傳至資料庫的資料為基礎。</span><span class="sxs-lookup"><span data-stu-id="13c23-104">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="13c23-105">進度報告將寫入僅適用於通話和 Lync Server 2013 會決定可能會很有用進行診斷之用的工作階段。</span><span class="sxs-lookup"><span data-stu-id="13c23-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="13c23-106">ErrorTime、ErrorReportSeq 及 ProgressReportSeq 欄位不一定和錯誤有關，而是有關指出通話或訊息狀態的訊息。</span><span class="sxs-lookup"><span data-stu-id="13c23-106">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="13c23-107">欄</span><span class="sxs-lookup"><span data-stu-id="13c23-107">Column</span></span></th>
<th><span data-ttu-id="13c23-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="13c23-108">Data Type</span></span></th>
<th><span data-ttu-id="13c23-109">主索引鍵 /</span><span class="sxs-lookup"><span data-stu-id="13c23-109">Key/Index</span></span></th>
<th><span data-ttu-id="13c23-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="13c23-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="13c23-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="13c23-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="13c23-112">datetime</span><span class="sxs-lookup"><span data-stu-id="13c23-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="13c23-113">主要、外部</span><span class="sxs-lookup"><span data-stu-id="13c23-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="13c23-114">包含此進度報告之進度錯誤報告的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="13c23-114">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="13c23-115">請參閱<a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="13c23-115">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13c23-116"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="13c23-116"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="13c23-117">int</span><span class="sxs-lookup"><span data-stu-id="13c23-117">int</span></span></p></td>
<td><p><span data-ttu-id="13c23-118">主要、外部</span><span class="sxs-lookup"><span data-stu-id="13c23-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="13c23-119">與 ErrorTime、ProgressReportSeq 搭配使用的識別碼，可識別唯一的進度報告。</span><span class="sxs-lookup"><span data-stu-id="13c23-119">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="13c23-120">請參閱<a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="13c23-120">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13c23-121"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="13c23-121"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="13c23-122">int</span><span class="sxs-lookup"><span data-stu-id="13c23-122">int</span></span></p></td>
<td><p><span data-ttu-id="13c23-123">主要，外部</span><span class="sxs-lookup"><span data-stu-id="13c23-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="13c23-124">識別錯誤報告的識別碼。</span><span class="sxs-lookup"><span data-stu-id="13c23-124">ID number that identifies the error report.</span></span> <span data-ttu-id="13c23-125">ErrorReporSeq 與 ErrorTime 搭配使用，可識別唯一的錯誤報告。</span><span class="sxs-lookup"><span data-stu-id="13c23-125">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="13c23-126">請參閱如需詳細資訊的<a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表格</a></span><span class="sxs-lookup"><span data-stu-id="13c23-126">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="13c23-127">Microsoft Lync Server 2013 中已採用此欄位。</span><span class="sxs-lookup"><span data-stu-id="13c23-127">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13c23-128"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="13c23-128"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="13c23-129">int</span><span class="sxs-lookup"><span data-stu-id="13c23-129">int</span></span></p></td>
<td><p><span data-ttu-id="13c23-130">主要</span><span class="sxs-lookup"><span data-stu-id="13c23-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="13c23-p105">用於識別進度報告的識別碼。與 ErrorTime 及 ErrorReportSeq 搭配使用，可識別唯一的進度報告。</span><span class="sxs-lookup"><span data-stu-id="13c23-p105">ID number to identify the progress report. Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13c23-133"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="13c23-133"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="13c23-134">int</span><span class="sxs-lookup"><span data-stu-id="13c23-134">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="13c23-135">進度報告的診斷 ID。</span><span class="sxs-lookup"><span data-stu-id="13c23-135">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="13c23-136">Microsoft Lync Server 2013 中已採用此欄位。</span><span class="sxs-lookup"><span data-stu-id="13c23-136">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13c23-137"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="13c23-137"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="13c23-138">int</span><span class="sxs-lookup"><span data-stu-id="13c23-138">int</span></span></p></td>
<td><p><span data-ttu-id="13c23-139">Foreign</span><span class="sxs-lookup"><span data-stu-id="13c23-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="13c23-140">（如果報告從伺服器元件傳送） 傳送錯誤報告的伺服器。</span><span class="sxs-lookup"><span data-stu-id="13c23-140">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="13c23-141">請參閱<a href="lync-server-2013-servers-table.md">Lync Server 2013 中的伺服器表格</a>如需詳細資訊。Microsoft Lync Server 2013 中已採用此欄位。</span><span class="sxs-lookup"><span data-stu-id="13c23-141">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13c23-142"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="13c23-142"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="13c23-143">int</span><span class="sxs-lookup"><span data-stu-id="13c23-143">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="13c23-p107">報告針對的 Lync Server 程序。如需詳細資訊，請參閱應用程式表格。</span><span class="sxs-lookup"><span data-stu-id="13c23-p107">The Lync Server process that the report is about. See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13c23-146"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="13c23-146"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="13c23-147">image</span><span class="sxs-lookup"><span data-stu-id="13c23-147">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="13c23-148">進度報告詳細資料，以二進位格式儲存，以節省空間。可使用此語法將資料轉換成文字格式：</span><span class="sxs-lookup"><span data-stu-id="13c23-148">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="13c23-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="13c23-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13c23-150"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="13c23-150"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="13c23-151">唯一</span><span class="sxs-lookup"><span data-stu-id="13c23-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="13c23-152">會議所包含之不同元件的加入時間資訊的相互關聯唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="13c23-152">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="13c23-153">Microsoft Lync Server 2013 中已採用此欄位。</span><span class="sxs-lookup"><span data-stu-id="13c23-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13c23-154"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="13c23-154"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="13c23-155">int</span><span class="sxs-lookup"><span data-stu-id="13c23-155">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="13c23-156">特定元件加入會議的時間 (毫秒)。</span><span class="sxs-lookup"><span data-stu-id="13c23-156">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="13c23-157">Microsoft Lync Server 2013 中已採用此欄位。</span><span class="sxs-lookup"><span data-stu-id="13c23-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

