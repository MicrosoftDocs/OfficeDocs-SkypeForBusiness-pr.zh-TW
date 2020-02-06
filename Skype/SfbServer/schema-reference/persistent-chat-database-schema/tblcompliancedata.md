---
title: tblComplianceData
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
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData 包含尚未由合規性配接器處理的合規性事件。
ms.openlocfilehash: f09acd44e803c629e45afa18683ac7bc863564a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814661"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="2e07e-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="2e07e-103">tblComplianceData</span></span>
 
<span data-ttu-id="2e07e-104">tblComplianceData 包含尚未由合規性配接器處理的合規性事件。</span><span class="sxs-lookup"><span data-stu-id="2e07e-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="2e07e-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="2e07e-105">**Columns**</span></span>

|<span data-ttu-id="2e07e-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="2e07e-106">**Column**</span></span>|<span data-ttu-id="2e07e-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="2e07e-107">**Type**</span></span>|<span data-ttu-id="2e07e-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="2e07e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2e07e-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="2e07e-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="2e07e-110">Bigint，not null</span><span class="sxs-lookup"><span data-stu-id="2e07e-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="2e07e-111">事件 ID。</span><span class="sxs-lookup"><span data-stu-id="2e07e-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="2e07e-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="2e07e-112">entryDate</span></span>  <br/> |<span data-ttu-id="2e07e-113">Smalldatetime，not null</span><span class="sxs-lookup"><span data-stu-id="2e07e-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="2e07e-114">插入的時間（對於 cmplType = 9，未來可能是目前的時間），因為該專案只是該案例中的預留位置。</span><span class="sxs-lookup"><span data-stu-id="2e07e-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="2e07e-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="2e07e-115">cmplType</span></span>  <br/> |<span data-ttu-id="2e07e-116">int，not null</span><span class="sxs-lookup"><span data-stu-id="2e07e-116">int, not null</span></span>  <br/> | <span data-ttu-id="2e07e-117">合規性事件的類型：</span><span class="sxs-lookup"><span data-stu-id="2e07e-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="2e07e-118">1：聊天</span><span class="sxs-lookup"><span data-stu-id="2e07e-118">1: Chat</span></span> <br/>  <span data-ttu-id="2e07e-119">2： Backchat</span><span class="sxs-lookup"><span data-stu-id="2e07e-119">2: Backchat</span></span> <br/>  <span data-ttu-id="2e07e-120">3：檔案下載</span><span class="sxs-lookup"><span data-stu-id="2e07e-120">3: File download</span></span> <br/>  <span data-ttu-id="2e07e-121">4：檔案上傳</span><span class="sxs-lookup"><span data-stu-id="2e07e-121">4: File upload</span></span> <br/>  <span data-ttu-id="2e07e-122">9：暫存檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="2e07e-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="2e07e-123">10：聊天刪除（使用 [取代]）</span><span class="sxs-lookup"><span data-stu-id="2e07e-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="2e07e-124">11：聊天清除</span><span class="sxs-lookup"><span data-stu-id="2e07e-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="2e07e-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="2e07e-125">cmplTime</span></span>  <br/> |<span data-ttu-id="2e07e-126">Bigint，not null</span><span class="sxs-lookup"><span data-stu-id="2e07e-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="2e07e-127">事件的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="2e07e-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="2e07e-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="2e07e-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="2e07e-129">Nvarchar （255），not null</span><span class="sxs-lookup"><span data-stu-id="2e07e-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="2e07e-130">通道統一資源識別項（URI）。</span><span class="sxs-lookup"><span data-stu-id="2e07e-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="2e07e-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="2e07e-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="2e07e-132">Bigint</span><span class="sxs-lookup"><span data-stu-id="2e07e-132">bigint</span></span>  <br/> |<span data-ttu-id="2e07e-133">聊天識別碼（對應至 tblChat chatId 表）。</span><span class="sxs-lookup"><span data-stu-id="2e07e-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="2e07e-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="2e07e-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="2e07e-135">int，not null</span><span class="sxs-lookup"><span data-stu-id="2e07e-135">int, not null</span></span>  <br/> |<span data-ttu-id="2e07e-136">海報的主體識別碼（對應至 tblPrincipal prinID）。</span><span class="sxs-lookup"><span data-stu-id="2e07e-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="2e07e-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="2e07e-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="2e07e-138">Nvarchar （255），not null</span><span class="sxs-lookup"><span data-stu-id="2e07e-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="2e07e-139">使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="2e07e-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="2e07e-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="2e07e-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="2e07e-141">Nvarchar （max）</span><span class="sxs-lookup"><span data-stu-id="2e07e-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="2e07e-142">訊息（編碼依據 cmplType）。</span><span class="sxs-lookup"><span data-stu-id="2e07e-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="2e07e-143">**機碼**</span><span class="sxs-lookup"><span data-stu-id="2e07e-143">**Key**</span></span>

|<span data-ttu-id="2e07e-144">**左欄**</span><span class="sxs-lookup"><span data-stu-id="2e07e-144">**Column**</span></span>|<span data-ttu-id="2e07e-145">**說明**</span><span class="sxs-lookup"><span data-stu-id="2e07e-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2e07e-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="2e07e-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="2e07e-147">主鍵。</span><span class="sxs-lookup"><span data-stu-id="2e07e-147">Primary key.</span></span>  <br/> |
   

