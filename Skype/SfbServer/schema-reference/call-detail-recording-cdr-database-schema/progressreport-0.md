---
title: ProgressReport 視圖
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: '[ProgressReport] 視圖儲存已完成會話的相關資訊。 進度報告只會寫入 Lync Server 2013 決定可能對診斷用途有用的通話和會話。 此視圖已在 Microsoft Lync Server 2013 中推出。'
ms.openlocfilehash: c07b9db8ebd9f898ab9d8feb5b07c4723209522c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814981"
---
# <a name="progressreport-view"></a><span data-ttu-id="d1fdc-105">ProgressReport 視圖</span><span class="sxs-lookup"><span data-stu-id="d1fdc-105">ProgressReport view</span></span>
 
<span data-ttu-id="d1fdc-106">[ProgressReport] 視圖儲存已完成會話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d1fdc-106">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="d1fdc-107">進度報告只會寫入 Lync Server 2013 決定可能對診斷用途有用的通話和會話。</span><span class="sxs-lookup"><span data-stu-id="d1fdc-107">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="d1fdc-108">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="d1fdc-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d1fdc-109">ErrorTime、ErrorReportSeq 和 ProgressReportSeq 欄位不一定會參照錯誤，而是指出通話或訊息狀態的訊息。</span><span class="sxs-lookup"><span data-stu-id="d1fdc-109">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don't necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span> 
  
|<span data-ttu-id="d1fdc-110">**左欄**</span><span class="sxs-lookup"><span data-stu-id="d1fdc-110">**Column**</span></span>|<span data-ttu-id="d1fdc-111">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="d1fdc-111">**Data Type**</span></span>|<span data-ttu-id="d1fdc-112">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="d1fdc-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d1fdc-113">**ErrorTime**</span><span class="sxs-lookup"><span data-stu-id="d1fdc-113">**ErrorTime**</span></span> <br/> |<span data-ttu-id="d1fdc-114">datetime</span><span class="sxs-lookup"><span data-stu-id="d1fdc-114">datetime</span></span>  <br/> |<span data-ttu-id="d1fdc-115">發生錯誤的時間。</span><span class="sxs-lookup"><span data-stu-id="d1fdc-115">Time of error occurred.</span></span> <span data-ttu-id="d1fdc-116">與 ErrorReportSeq 搭配使用，可唯一識別錯誤。</span><span class="sxs-lookup"><span data-stu-id="d1fdc-116">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="d1fdc-117">**ErrorReportSeq**</span><span class="sxs-lookup"><span data-stu-id="d1fdc-117">**ErrorReportSeq**</span></span> <br/> |<span data-ttu-id="d1fdc-118">int</span><span class="sxs-lookup"><span data-stu-id="d1fdc-118">int</span></span>  <br/> |<span data-ttu-id="d1fdc-119">識別錯誤的識別碼號碼。</span><span class="sxs-lookup"><span data-stu-id="d1fdc-119">ID number to identify the error.</span></span> <span data-ttu-id="d1fdc-120">與 ErrorTime 搭配使用，可唯一識別錯誤。</span><span class="sxs-lookup"><span data-stu-id="d1fdc-120">Used in conjunction with ErrorTime to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="d1fdc-121">**ProgressReportSeq**</span><span class="sxs-lookup"><span data-stu-id="d1fdc-121">**ProgressReportSeq**</span></span> <br/> |<span data-ttu-id="d1fdc-122">int</span><span class="sxs-lookup"><span data-stu-id="d1fdc-122">int</span></span>  <br/> |<span data-ttu-id="d1fdc-123">標識進度報表的識別碼。</span><span class="sxs-lookup"><span data-stu-id="d1fdc-123">ID to identify the progress report.</span></span> <span data-ttu-id="d1fdc-124">用來區分相同錯誤報表的進度報告。</span><span class="sxs-lookup"><span data-stu-id="d1fdc-124">Used to distinguish progress reports of the same error report.</span></span>  <br/> |
|<span data-ttu-id="d1fdc-125">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="d1fdc-125">**MsDiagId**</span></span> <br/> |<span data-ttu-id="d1fdc-126">int</span><span class="sxs-lookup"><span data-stu-id="d1fdc-126">int</span></span>  <br/> |<span data-ttu-id="d1fdc-127">錯誤報表的診斷 ID。</span><span class="sxs-lookup"><span data-stu-id="d1fdc-127">Diagnostic ID for the error report.</span></span>  <br/> |
|<span data-ttu-id="d1fdc-128">**從源**</span><span class="sxs-lookup"><span data-stu-id="d1fdc-128">**Source**</span></span> <br/> |<span data-ttu-id="d1fdc-129">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="d1fdc-129">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d1fdc-130">產生錯誤的伺服器名稱（如果報表是從伺服器元件傳送）。</span><span class="sxs-lookup"><span data-stu-id="d1fdc-130">Name of server that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="d1fdc-131">**應用程式**</span><span class="sxs-lookup"><span data-stu-id="d1fdc-131">**Application**</span></span> <br/> |<span data-ttu-id="d1fdc-132">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="d1fdc-132">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d1fdc-133">產生錯誤的應用程式名稱（如果報表是從伺服器元件傳送）。</span><span class="sxs-lookup"><span data-stu-id="d1fdc-133">Name of application that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="d1fdc-134">**TelemetryId**</span><span class="sxs-lookup"><span data-stu-id="d1fdc-134">**TelemetryId**</span></span> <br/> |<span data-ttu-id="d1fdc-135">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="d1fdc-135">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="d1fdc-136">與會議中所涉及之不同元件的加入時間資訊關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="d1fdc-136">Unique identifier correlating join time information for the different components involved in a conference.</span></span>  <br/> |
|<span data-ttu-id="d1fdc-137">**SessionSetupTime**</span><span class="sxs-lookup"><span data-stu-id="d1fdc-137">**SessionSetupTime**</span></span> <br/> |<span data-ttu-id="d1fdc-138">int</span><span class="sxs-lookup"><span data-stu-id="d1fdc-138">int</span></span>  <br/> |<span data-ttu-id="d1fdc-139">特定元件加入會議所需的時間（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="d1fdc-139">Time (in milliseconds) required for a specific component to join a conference.</span></span>  <br/> |
|<span data-ttu-id="d1fdc-140">**MsDiagHeader**</span><span class="sxs-lookup"><span data-stu-id="d1fdc-140">**MsDiagHeader**</span></span> <br/> |<span data-ttu-id="d1fdc-141">Varchar （max）</span><span class="sxs-lookup"><span data-stu-id="d1fdc-141">varchar(max)</span></span>  <br/> |<span data-ttu-id="d1fdc-142">其他錯誤資訊。</span><span class="sxs-lookup"><span data-stu-id="d1fdc-142">Additional error information.</span></span>  <br/> |
   

