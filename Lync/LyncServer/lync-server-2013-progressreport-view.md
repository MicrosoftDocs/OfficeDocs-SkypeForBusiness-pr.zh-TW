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
ms.openlocfilehash: 4fa8d73981490503b26b77b79be6f42aab77703e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="1104e-102">Lync Server 2013 中的 [ProgressReport] 視圖</span><span class="sxs-lookup"><span data-stu-id="1104e-102">ProgressReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1104e-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="1104e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="1104e-104">[ProgressReport] 視圖儲存已完成會話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1104e-104">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="1104e-105">進度報告只會寫入 Lync Server 2013 決定可能對診斷用途有用的通話和會話。</span><span class="sxs-lookup"><span data-stu-id="1104e-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="1104e-106">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="1104e-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1104e-107">ErrorTime、ErrorReportSeq 和 ProgressReportSeq 欄位不一定會參照錯誤，而是指出通話或訊息狀態的訊息。</span><span class="sxs-lookup"><span data-stu-id="1104e-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1104e-108">左欄</span><span class="sxs-lookup"><span data-stu-id="1104e-108">Column</span></span></th>
<th><span data-ttu-id="1104e-109">資料類型</span><span class="sxs-lookup"><span data-stu-id="1104e-109">Data Type</span></span></th>
<th><span data-ttu-id="1104e-110">詳細資料</span><span class="sxs-lookup"><span data-stu-id="1104e-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1104e-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="1104e-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1104e-112">datetime</span><span class="sxs-lookup"><span data-stu-id="1104e-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="1104e-113">發生錯誤的時間。</span><span class="sxs-lookup"><span data-stu-id="1104e-113">Time of error occurred.</span></span> <span data-ttu-id="1104e-114">與 ErrorReportSeq 搭配使用，可唯一識別錯誤。</span><span class="sxs-lookup"><span data-stu-id="1104e-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1104e-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1104e-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1104e-116">int</span><span class="sxs-lookup"><span data-stu-id="1104e-116">int</span></span></p></td>
<td><p><span data-ttu-id="1104e-117">識別錯誤的識別碼號碼。</span><span class="sxs-lookup"><span data-stu-id="1104e-117">ID number to identify the error.</span></span> <span data-ttu-id="1104e-118">與 ErrorTime 搭配使用，可唯一識別錯誤。</span><span class="sxs-lookup"><span data-stu-id="1104e-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1104e-119"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1104e-119"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1104e-120">int</span><span class="sxs-lookup"><span data-stu-id="1104e-120">int</span></span></p></td>
<td><p><span data-ttu-id="1104e-121">標識進度報表的識別碼。</span><span class="sxs-lookup"><span data-stu-id="1104e-121">ID to identify the progress report.</span></span> <span data-ttu-id="1104e-122">用來區分相同錯誤報表的進度報告。</span><span class="sxs-lookup"><span data-stu-id="1104e-122">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1104e-123"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="1104e-123"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="1104e-124">int</span><span class="sxs-lookup"><span data-stu-id="1104e-124">int</span></span></p></td>
<td><p><span data-ttu-id="1104e-125">錯誤報表的診斷 ID。</span><span class="sxs-lookup"><span data-stu-id="1104e-125">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1104e-126"><strong>從源</strong></span><span class="sxs-lookup"><span data-stu-id="1104e-126"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="1104e-127">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="1104e-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1104e-128">產生錯誤的伺服器名稱（如果報表是從伺服器元件傳送）。</span><span class="sxs-lookup"><span data-stu-id="1104e-128">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1104e-129"><strong>應用程式</strong></span><span class="sxs-lookup"><span data-stu-id="1104e-129"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="1104e-130">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="1104e-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1104e-131">產生錯誤的應用程式名稱（如果報表是從伺服器元件傳送）。</span><span class="sxs-lookup"><span data-stu-id="1104e-131">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1104e-132"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="1104e-132"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="1104e-133">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="1104e-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="1104e-134">與會議中所涉及之不同元件的加入時間資訊關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="1104e-134">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1104e-135"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="1104e-135"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1104e-136">int</span><span class="sxs-lookup"><span data-stu-id="1104e-136">int</span></span></p></td>
<td><p><span data-ttu-id="1104e-137">特定元件加入會議所需的時間（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="1104e-137">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1104e-138"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="1104e-138"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="1104e-139">Varchar （max）</span><span class="sxs-lookup"><span data-stu-id="1104e-139">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="1104e-140">其他錯誤資訊。</span><span class="sxs-lookup"><span data-stu-id="1104e-140">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

