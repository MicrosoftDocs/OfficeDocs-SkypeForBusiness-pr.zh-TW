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
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData 包含尚未由合規性配接器處理的合規性事件。
ms.openlocfilehash: b505b3e05fb2aebba98804f5b7ad6a1d4d2da53e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192753"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="45b1b-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="45b1b-103">tblComplianceData</span></span>
 
<span data-ttu-id="45b1b-104">tblComplianceData 包含尚未由合規性配接器處理的合規性事件。</span><span class="sxs-lookup"><span data-stu-id="45b1b-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="45b1b-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="45b1b-105">**Columns**</span></span>

|<span data-ttu-id="45b1b-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="45b1b-106">**Column**</span></span>|<span data-ttu-id="45b1b-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="45b1b-107">**Type**</span></span>|<span data-ttu-id="45b1b-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="45b1b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="45b1b-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="45b1b-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="45b1b-110">Bigint, not null</span><span class="sxs-lookup"><span data-stu-id="45b1b-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="45b1b-111">事件 ID。</span><span class="sxs-lookup"><span data-stu-id="45b1b-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="45b1b-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="45b1b-112">entryDate</span></span>  <br/> |<span data-ttu-id="45b1b-113">Smalldatetime, not null</span><span class="sxs-lookup"><span data-stu-id="45b1b-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="45b1b-114">插入的時間 (對於 cmplType = 9, 未來可能是目前的時間), 因為該專案只是該案例中的預留位置。</span><span class="sxs-lookup"><span data-stu-id="45b1b-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="45b1b-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="45b1b-115">cmplType</span></span>  <br/> |<span data-ttu-id="45b1b-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="45b1b-116">int, not null</span></span>  <br/> | <span data-ttu-id="45b1b-117">合規性事件的類型:</span><span class="sxs-lookup"><span data-stu-id="45b1b-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="45b1b-118">1: 聊天</span><span class="sxs-lookup"><span data-stu-id="45b1b-118">1: Chat</span></span> <br/>  <span data-ttu-id="45b1b-119">2: Backchat</span><span class="sxs-lookup"><span data-stu-id="45b1b-119">2: Backchat</span></span> <br/>  <span data-ttu-id="45b1b-120">3: 檔案下載</span><span class="sxs-lookup"><span data-stu-id="45b1b-120">3: File download</span></span> <br/>  <span data-ttu-id="45b1b-121">4: 檔案上傳</span><span class="sxs-lookup"><span data-stu-id="45b1b-121">4: File upload</span></span> <br/>  <span data-ttu-id="45b1b-122">9: 暫存檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="45b1b-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="45b1b-123">10: 聊天刪除 (使用 [取代])</span><span class="sxs-lookup"><span data-stu-id="45b1b-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="45b1b-124">11: 聊天清除</span><span class="sxs-lookup"><span data-stu-id="45b1b-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="45b1b-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="45b1b-125">cmplTime</span></span>  <br/> |<span data-ttu-id="45b1b-126">Bigint, not null</span><span class="sxs-lookup"><span data-stu-id="45b1b-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="45b1b-127">事件的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="45b1b-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="45b1b-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="45b1b-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="45b1b-129">Nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="45b1b-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="45b1b-130">通道統一資源識別項 (URI)。</span><span class="sxs-lookup"><span data-stu-id="45b1b-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="45b1b-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="45b1b-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="45b1b-132">Bigint</span><span class="sxs-lookup"><span data-stu-id="45b1b-132">bigint</span></span>  <br/> |<span data-ttu-id="45b1b-133">聊天識別碼 (對應至 tblChat chatId 表)。</span><span class="sxs-lookup"><span data-stu-id="45b1b-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="45b1b-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="45b1b-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="45b1b-135">int, not null</span><span class="sxs-lookup"><span data-stu-id="45b1b-135">int, not null</span></span>  <br/> |<span data-ttu-id="45b1b-136">海報的主體識別碼 (對應至 tblPrincipal prinID)。</span><span class="sxs-lookup"><span data-stu-id="45b1b-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="45b1b-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="45b1b-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="45b1b-138">Nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="45b1b-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="45b1b-139">使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="45b1b-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="45b1b-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="45b1b-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="45b1b-141">Nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="45b1b-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="45b1b-142">訊息 (編碼依據 cmplType)。</span><span class="sxs-lookup"><span data-stu-id="45b1b-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="45b1b-143">**快速鍵**</span><span class="sxs-lookup"><span data-stu-id="45b1b-143">**Key**</span></span>

|<span data-ttu-id="45b1b-144">**左欄**</span><span class="sxs-lookup"><span data-stu-id="45b1b-144">**Column**</span></span>|<span data-ttu-id="45b1b-145">**說明**</span><span class="sxs-lookup"><span data-stu-id="45b1b-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="45b1b-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="45b1b-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="45b1b-147">主鍵。</span><span class="sxs-lookup"><span data-stu-id="45b1b-147">Primary key.</span></span>  <br/> |
   

