---
title: ProgressReport view
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: ProgressReport view 儲存已完成會話的相關資訊。 進度報告只會寫入 Lync Server 2013 決定可用於診斷目的的呼叫和會話。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: 6cc8295e73463fff9d4913efbf9d4844f9316149
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823183"
---
# <a name="progressreport-view"></a><span data-ttu-id="6cc56-105">ProgressReport view</span><span class="sxs-lookup"><span data-stu-id="6cc56-105">ProgressReport view</span></span>
 
<span data-ttu-id="6cc56-106">ProgressReport view 儲存已完成會話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="6cc56-106">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="6cc56-107">進度報告只會寫入 Lync Server 2013 決定可用於診斷目的的呼叫和會話。</span><span class="sxs-lookup"><span data-stu-id="6cc56-107">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="6cc56-108">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="6cc56-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6cc56-109">[ErrorTime]、[ErrorReportSeq] 和 [ProgressReportSeq] 欄位不一定會參考錯誤，而是指出來電或郵件狀態的訊息。</span><span class="sxs-lookup"><span data-stu-id="6cc56-109">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don't necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span> 
  
|<span data-ttu-id="6cc56-110">**欄**</span><span class="sxs-lookup"><span data-stu-id="6cc56-110">**Column**</span></span>|<span data-ttu-id="6cc56-111">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="6cc56-111">**Data Type**</span></span>|<span data-ttu-id="6cc56-112">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="6cc56-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6cc56-113">**ErrorTime**</span><span class="sxs-lookup"><span data-stu-id="6cc56-113">**ErrorTime**</span></span> <br/> |<span data-ttu-id="6cc56-114">datetime</span><span class="sxs-lookup"><span data-stu-id="6cc56-114">datetime</span></span>  <br/> |<span data-ttu-id="6cc56-115">發生錯誤的時間。</span><span class="sxs-lookup"><span data-stu-id="6cc56-115">Time of error occurred.</span></span> <span data-ttu-id="6cc56-116">與 ErrorReportSeq 搭配使用，以唯一識別錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cc56-116">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="6cc56-117">**ErrorReportSeq**</span><span class="sxs-lookup"><span data-stu-id="6cc56-117">**ErrorReportSeq**</span></span> <br/> |<span data-ttu-id="6cc56-118">int</span><span class="sxs-lookup"><span data-stu-id="6cc56-118">int</span></span>  <br/> |<span data-ttu-id="6cc56-119">用以識別錯誤的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="6cc56-119">ID number to identify the error.</span></span> <span data-ttu-id="6cc56-120">與 ErrorTime 搭配使用，以唯一識別錯誤。</span><span class="sxs-lookup"><span data-stu-id="6cc56-120">Used in conjunction with ErrorTime to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="6cc56-121">**ProgressReportSeq**</span><span class="sxs-lookup"><span data-stu-id="6cc56-121">**ProgressReportSeq**</span></span> <br/> |<span data-ttu-id="6cc56-122">int</span><span class="sxs-lookup"><span data-stu-id="6cc56-122">int</span></span>  <br/> |<span data-ttu-id="6cc56-123">識別進度報表的識別碼。</span><span class="sxs-lookup"><span data-stu-id="6cc56-123">ID to identify the progress report.</span></span> <span data-ttu-id="6cc56-124">用來區分相同錯誤報表的進度報告。</span><span class="sxs-lookup"><span data-stu-id="6cc56-124">Used to distinguish progress reports of the same error report.</span></span>  <br/> |
|<span data-ttu-id="6cc56-125">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="6cc56-125">**MsDiagId**</span></span> <br/> |<span data-ttu-id="6cc56-126">int</span><span class="sxs-lookup"><span data-stu-id="6cc56-126">int</span></span>  <br/> |<span data-ttu-id="6cc56-127">錯誤報表的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="6cc56-127">Diagnostic ID for the error report.</span></span>  <br/> |
|<span data-ttu-id="6cc56-128">**Source**</span><span class="sxs-lookup"><span data-stu-id="6cc56-128">**Source**</span></span> <br/> |<span data-ttu-id="6cc56-129">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="6cc56-129">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6cc56-130">起源錯誤的伺服器名稱 (如果報告是從伺服器元件傳送) 中。</span><span class="sxs-lookup"><span data-stu-id="6cc56-130">Name of server that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="6cc56-131">**應用程式**</span><span class="sxs-lookup"><span data-stu-id="6cc56-131">**Application**</span></span> <br/> |<span data-ttu-id="6cc56-132">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="6cc56-132">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6cc56-133">起源錯誤的應用程式名稱 (如果報告是從伺服器元件傳送) 。</span><span class="sxs-lookup"><span data-stu-id="6cc56-133">Name of application that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="6cc56-134">**TelemetryId**</span><span class="sxs-lookup"><span data-stu-id="6cc56-134">**TelemetryId**</span></span> <br/> |<span data-ttu-id="6cc56-135">唯一</span><span class="sxs-lookup"><span data-stu-id="6cc56-135">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="6cc56-136">與會議相關聯之不同元件的加入時間資訊的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="6cc56-136">Unique identifier correlating join time information for the different components involved in a conference.</span></span>  <br/> |
|<span data-ttu-id="6cc56-137">**SessionSetupTime**</span><span class="sxs-lookup"><span data-stu-id="6cc56-137">**SessionSetupTime**</span></span> <br/> |<span data-ttu-id="6cc56-138">int</span><span class="sxs-lookup"><span data-stu-id="6cc56-138">int</span></span>  <br/> |<span data-ttu-id="6cc56-139">特定元件加入會議所需的時間 (（毫秒）) 。</span><span class="sxs-lookup"><span data-stu-id="6cc56-139">Time (in milliseconds) required for a specific component to join a conference.</span></span>  <br/> |
|<span data-ttu-id="6cc56-140">**MsDiagHeader**</span><span class="sxs-lookup"><span data-stu-id="6cc56-140">**MsDiagHeader**</span></span> <br/> |<span data-ttu-id="6cc56-141">Varchar (max) </span><span class="sxs-lookup"><span data-stu-id="6cc56-141">varchar(max)</span></span>  <br/> |<span data-ttu-id="6cc56-142">其他錯誤資訊。</span><span class="sxs-lookup"><span data-stu-id="6cc56-142">Additional error information.</span></span>  <br/> |
   

