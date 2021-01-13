---
title: tblFileToken
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
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken 包含用於檔案傳輸的臨時權杖。
ms.openlocfilehash: 75d3d4df3affe3d12f94499efdb4337ade11af27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816013"
---
# <a name="tblfiletoken"></a><span data-ttu-id="5e056-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="5e056-103">tblFileToken</span></span>
 
<span data-ttu-id="5e056-104">tblFileToken 包含用於檔案傳輸的臨時權杖。</span><span class="sxs-lookup"><span data-stu-id="5e056-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="5e056-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="5e056-105">**Columns**</span></span>

|<span data-ttu-id="5e056-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="5e056-106">**Column**</span></span>|<span data-ttu-id="5e056-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="5e056-107">**Type**</span></span>|<span data-ttu-id="5e056-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="5e056-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5e056-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="5e056-109">fileToken</span></span>  <br/> |<span data-ttu-id="5e056-110">nvarchar (50)，非 null</span><span class="sxs-lookup"><span data-stu-id="5e056-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="5e056-111">唯一 Token (GUID)。</span><span class="sxs-lookup"><span data-stu-id="5e056-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="5e056-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="5e056-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="5e056-113">int，非 null</span><span class="sxs-lookup"><span data-stu-id="5e056-113">int, not null</span></span>  <br/> |<span data-ttu-id="5e056-114">傳輸檔案之主體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="5e056-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="5e056-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="5e056-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="5e056-116">GUID，非 null</span><span class="sxs-lookup"><span data-stu-id="5e056-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="5e056-117">聊天室節點的 GUID。</span><span class="sxs-lookup"><span data-stu-id="5e056-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="5e056-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="5e056-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="5e056-119">datetime，非 null</span><span class="sxs-lookup"><span data-stu-id="5e056-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="5e056-p101">到期時間 (權杖於 30 分鐘後到期，除非已固定 (請參閱此欄中下列說明)。</span><span class="sxs-lookup"><span data-stu-id="5e056-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="5e056-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="5e056-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="5e056-123">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="5e056-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="5e056-124">已傳輸檔案的 URL (供 Compliance Service 使用)。</span><span class="sxs-lookup"><span data-stu-id="5e056-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="5e056-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="5e056-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="5e056-126">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="5e056-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="5e056-127">已傳輸檔案的縮圖 URL (供 Compliance Service 使用)。</span><span class="sxs-lookup"><span data-stu-id="5e056-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="5e056-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="5e056-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="5e056-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="5e056-129">datetime2</span></span>  <br/> |<span data-ttu-id="5e056-130">實際檔案傳輸作業的時間戳記 (供 Compliance Service 使用)。</span><span class="sxs-lookup"><span data-stu-id="5e056-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="5e056-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="5e056-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="5e056-132">位</span><span class="sxs-lookup"><span data-stu-id="5e056-132">bit</span></span>  <br/> |<span data-ttu-id="5e056-133">若上傳則為 True；若下載則為 False (供 Compliance Service 使用)。</span><span class="sxs-lookup"><span data-stu-id="5e056-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="5e056-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="5e056-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="5e056-135">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="5e056-135">bit, not null</span></span>  <br/> |<span data-ttu-id="5e056-136">True 是表示如果鎖定標記。</span><span class="sxs-lookup"><span data-stu-id="5e056-136">True if token is pinned.</span></span> <span data-ttu-id="5e056-137">它是用來保留表格中的標記，直到合規性服務有機會從該介面中取回相關的欄位。</span><span class="sxs-lookup"><span data-stu-id="5e056-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="5e056-138">**Keys**</span><span class="sxs-lookup"><span data-stu-id="5e056-138">**Keys**</span></span>

|<span data-ttu-id="5e056-139">**欄**</span><span class="sxs-lookup"><span data-stu-id="5e056-139">**Column**</span></span>|<span data-ttu-id="5e056-140">**描述**</span><span class="sxs-lookup"><span data-stu-id="5e056-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5e056-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="5e056-141">fileToken</span></span>  <br/> |<span data-ttu-id="5e056-142">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="5e056-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="5e056-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="5e056-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="5e056-144">在 Node.nodeGuid 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="5e056-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

