---
title: Lync Server 2013：ProgressReport 表格
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
ms.openlocfilehash: 2e1cb7c8e764097af96981220ee74d481b379341
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="80943-102">Lync Server 2013 中的 ProgressReport 表格</span><span class="sxs-lookup"><span data-stu-id="80943-102">ProgressReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80943-103">_**主題上次修改日期：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="80943-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="80943-104">進度報告是以用戶端在通話或會話完成後上傳到資料庫的資料為基礎。</span><span class="sxs-lookup"><span data-stu-id="80943-104">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="80943-105">進度報告只會寫入 Lync Server 2013 決定可能對診斷用途有用的通話和會話。</span><span class="sxs-lookup"><span data-stu-id="80943-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="80943-106">ErrorTime、ErrorReportSeq 和 ProgressReportSeq 欄位不一定會參照錯誤，而是指出通話或訊息狀態的訊息。</span><span class="sxs-lookup"><span data-stu-id="80943-106">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80943-107">左欄</span><span class="sxs-lookup"><span data-stu-id="80943-107">Column</span></span></th>
<th><span data-ttu-id="80943-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="80943-108">Data Type</span></span></th>
<th><span data-ttu-id="80943-109">索引鍵/索引</span><span class="sxs-lookup"><span data-stu-id="80943-109">Key/Index</span></span></th>
<th><span data-ttu-id="80943-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="80943-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80943-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="80943-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="80943-112">datetime</span><span class="sxs-lookup"><span data-stu-id="80943-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="80943-113">主要、外部</span><span class="sxs-lookup"><span data-stu-id="80943-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="80943-114">包含此進度報告之進度錯誤報表的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="80943-114">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="80943-115">如需詳細資訊，請參閱<a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中</a>的 [ErrorReport] 資料表。</span><span class="sxs-lookup"><span data-stu-id="80943-115">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80943-116"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="80943-116"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="80943-117">int</span><span class="sxs-lookup"><span data-stu-id="80943-117">int</span></span></p></td>
<td><p><span data-ttu-id="80943-118">主要、外部</span><span class="sxs-lookup"><span data-stu-id="80943-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="80943-119">與 ErrorTime、ProgressReportSeq 搭配使用的識別碼編號，可唯一識別進度報告。</span><span class="sxs-lookup"><span data-stu-id="80943-119">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="80943-120">如需詳細資訊，請參閱<a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中</a>的 [ErrorReport] 資料表。</span><span class="sxs-lookup"><span data-stu-id="80943-120">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80943-121"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="80943-121"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="80943-122">int</span><span class="sxs-lookup"><span data-stu-id="80943-122">int</span></span></p></td>
<td><p><span data-ttu-id="80943-123">主要、外部</span><span class="sxs-lookup"><span data-stu-id="80943-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="80943-124">識別錯誤報表的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="80943-124">ID number that identifies the error report.</span></span> <span data-ttu-id="80943-125">ErrorReporSeq 與 ErrorTime 搭配使用，可唯一識別錯誤報表。</span><span class="sxs-lookup"><span data-stu-id="80943-125">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="80943-126">如需詳細資訊，請參閱<a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中</a>的 [ErrorReport] 資料表</span><span class="sxs-lookup"><span data-stu-id="80943-126">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="80943-127">此欄位是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="80943-127">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80943-128"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="80943-128"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="80943-129">int</span><span class="sxs-lookup"><span data-stu-id="80943-129">int</span></span></p></td>
<td><p><span data-ttu-id="80943-130">首選</span><span class="sxs-lookup"><span data-stu-id="80943-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="80943-131">識別進度報表的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="80943-131">ID number to identify the progress report.</span></span> <span data-ttu-id="80943-132">與 ErrorTime 和 ErrorReportSeq 搭配使用，可唯一識別進度報告。</span><span class="sxs-lookup"><span data-stu-id="80943-132">Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80943-133"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="80943-133"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="80943-134">int</span><span class="sxs-lookup"><span data-stu-id="80943-134">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80943-135">進度報告的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="80943-135">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="80943-136">此欄位是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="80943-136">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80943-137"><strong>源</strong></span><span class="sxs-lookup"><span data-stu-id="80943-137"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="80943-138">int</span><span class="sxs-lookup"><span data-stu-id="80943-138">int</span></span></p></td>
<td><p><span data-ttu-id="80943-139">外</span><span class="sxs-lookup"><span data-stu-id="80943-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="80943-140">傳送錯誤報表的伺服器（如果報告是從伺服器元件傳送）。</span><span class="sxs-lookup"><span data-stu-id="80943-140">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="80943-141">如需詳細資訊，請參閱<a href="lync-server-2013-servers-table.md">Lync Server 2013 中</a>的 [伺服器] 資料表。此欄位是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="80943-141">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80943-142"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="80943-142"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="80943-143">int</span><span class="sxs-lookup"><span data-stu-id="80943-143">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80943-144">報告所用的 Lync Server 進程。</span><span class="sxs-lookup"><span data-stu-id="80943-144">The Lync Server process that the report is about.</span></span> <span data-ttu-id="80943-145">如需詳細資訊，請參閱應用程式表格。</span><span class="sxs-lookup"><span data-stu-id="80943-145">See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80943-146"><strong>具體</strong></span><span class="sxs-lookup"><span data-stu-id="80943-146"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="80943-147">影像</span><span class="sxs-lookup"><span data-stu-id="80943-147">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80943-148">以二進位格式儲存的進度報告詳細資料，以節省空間。此資料可以使用下列語法轉換成文字格式：</span><span class="sxs-lookup"><span data-stu-id="80943-148">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="80943-149">cast （以 Varbinary （max）格式轉換為 Varchar （max））</span><span class="sxs-lookup"><span data-stu-id="80943-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80943-150"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="80943-150"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="80943-151">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="80943-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80943-152">與會議中所涉及之不同元件的加入時間資訊關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="80943-152">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="80943-153">此欄位是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="80943-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80943-154"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="80943-154"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="80943-155">int</span><span class="sxs-lookup"><span data-stu-id="80943-155">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="80943-156">特定元件加入會議所需的時間（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="80943-156">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="80943-157">此欄位是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="80943-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

