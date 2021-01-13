---
title: tblComplianceData
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
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData 包含法規相符性介面卡尚未處理的規範事件。
ms.openlocfilehash: e4ceda662b2f601660c144319a4231cebeea39ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809853"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="475fb-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="475fb-103">tblComplianceData</span></span>
 
<span data-ttu-id="475fb-104">tblComplianceData 包含法規相符性介面卡尚未處理的規範事件。</span><span class="sxs-lookup"><span data-stu-id="475fb-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="475fb-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="475fb-105">**Columns**</span></span>

|<span data-ttu-id="475fb-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="475fb-106">**Column**</span></span>|<span data-ttu-id="475fb-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="475fb-107">**Type**</span></span>|<span data-ttu-id="475fb-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="475fb-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="475fb-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="475fb-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="475fb-110">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="475fb-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="475fb-111">事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="475fb-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="475fb-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="475fb-112">entryDate</span></span>  <br/> |<span data-ttu-id="475fb-113">smalldatetime，非 null</span><span class="sxs-lookup"><span data-stu-id="475fb-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="475fb-114">插入時間 (若是 cmplType=9，則可能是未來很久以後，因為此項目在此情況下只是預留位置)。</span><span class="sxs-lookup"><span data-stu-id="475fb-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="475fb-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="475fb-115">cmplType</span></span>  <br/> |<span data-ttu-id="475fb-116">int，非 null</span><span class="sxs-lookup"><span data-stu-id="475fb-116">int, not null</span></span>  <br/> | <span data-ttu-id="475fb-117">規範事件的類型：</span><span class="sxs-lookup"><span data-stu-id="475fb-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="475fb-118">1: 聊天</span><span class="sxs-lookup"><span data-stu-id="475fb-118">1: Chat</span></span> <br/>  <span data-ttu-id="475fb-119">2: 對話</span><span class="sxs-lookup"><span data-stu-id="475fb-119">2: Backchat</span></span> <br/>  <span data-ttu-id="475fb-120">3: 檔案下載</span><span class="sxs-lookup"><span data-stu-id="475fb-120">3: File download</span></span> <br/>  <span data-ttu-id="475fb-121">4: 檔案上傳</span><span class="sxs-lookup"><span data-stu-id="475fb-121">4: File upload</span></span> <br/>  <span data-ttu-id="475fb-122">9: 暫時性檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="475fb-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="475fb-123">10: 聊天刪除 (及取代)</span><span class="sxs-lookup"><span data-stu-id="475fb-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="475fb-124">11: 聊天清除</span><span class="sxs-lookup"><span data-stu-id="475fb-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="475fb-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="475fb-125">cmplTime</span></span>  <br/> |<span data-ttu-id="475fb-126">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="475fb-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="475fb-127">事件的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="475fb-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="475fb-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="475fb-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="475fb-129">nvarchar (255)，非 null</span><span class="sxs-lookup"><span data-stu-id="475fb-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="475fb-130">通道統一資源識別項 (URI)。</span><span class="sxs-lookup"><span data-stu-id="475fb-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="475fb-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="475fb-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="475fb-132">Bigint</span><span class="sxs-lookup"><span data-stu-id="475fb-132">bigint</span></span>  <br/> |<span data-ttu-id="475fb-133">聊天識別碼 (對應至 tblChat.chatId 表格)。</span><span class="sxs-lookup"><span data-stu-id="475fb-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="475fb-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="475fb-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="475fb-135">int，非 null</span><span class="sxs-lookup"><span data-stu-id="475fb-135">int, not null</span></span>  <br/> |<span data-ttu-id="475fb-136">發佈者的主體識別碼 (對應至 tblPrincipal.prinID 表格)。</span><span class="sxs-lookup"><span data-stu-id="475fb-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="475fb-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="475fb-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="475fb-138">nvarchar (255)，非 null</span><span class="sxs-lookup"><span data-stu-id="475fb-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="475fb-139">使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="475fb-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="475fb-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="475fb-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="475fb-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="475fb-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="475fb-142">訊息 (編碼取決於 cmplType)。</span><span class="sxs-lookup"><span data-stu-id="475fb-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="475fb-143">**Key**</span><span class="sxs-lookup"><span data-stu-id="475fb-143">**Key**</span></span>

|<span data-ttu-id="475fb-144">**欄**</span><span class="sxs-lookup"><span data-stu-id="475fb-144">**Column**</span></span>|<span data-ttu-id="475fb-145">**描述**</span><span class="sxs-lookup"><span data-stu-id="475fb-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="475fb-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="475fb-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="475fb-147">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="475fb-147">Primary key.</span></span>  <br/> |
   

