---
title: tblFileToken
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken 包含臨時權杖以進行檔案傳輸。
ms.openlocfilehash: 108c9738657354881324ec720f50a51605530922
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192737"
---
# <a name="tblfiletoken"></a><span data-ttu-id="00989-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="00989-103">tblFileToken</span></span>
 
<span data-ttu-id="00989-104">tblFileToken 包含臨時權杖以進行檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="00989-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="00989-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="00989-105">**Columns**</span></span>

|<span data-ttu-id="00989-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="00989-106">**Column**</span></span>|<span data-ttu-id="00989-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="00989-107">**Type**</span></span>|<span data-ttu-id="00989-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="00989-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="00989-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="00989-109">fileToken</span></span>  <br/> |<span data-ttu-id="00989-110">Nvarchar (50), not null</span><span class="sxs-lookup"><span data-stu-id="00989-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="00989-111">唯一標記 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="00989-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="00989-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="00989-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="00989-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="00989-113">int, not null</span></span>  <br/> |<span data-ttu-id="00989-114">要轉移檔案之主體的 ID。</span><span class="sxs-lookup"><span data-stu-id="00989-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="00989-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="00989-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="00989-116">GUID, 不是 null</span><span class="sxs-lookup"><span data-stu-id="00989-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="00989-117">聊天室節點的 GUID。</span><span class="sxs-lookup"><span data-stu-id="00989-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="00989-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="00989-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="00989-119">datetime、not null</span><span class="sxs-lookup"><span data-stu-id="00989-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="00989-120">到期時間。</span><span class="sxs-lookup"><span data-stu-id="00989-120">Expiration time.</span></span> <span data-ttu-id="00989-121">(權杖會在30分鐘之後到期, 除非已固定 (請參閱此欄中的下列描述)。</span><span class="sxs-lookup"><span data-stu-id="00989-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="00989-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="00989-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="00989-123">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="00989-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="00989-124">已傳送檔案的 URL (適用于合規性服務使用)。</span><span class="sxs-lookup"><span data-stu-id="00989-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="00989-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="00989-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="00989-126">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="00989-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="00989-127">已傳送檔案的縮圖 URL (適用于合規性服務使用)。</span><span class="sxs-lookup"><span data-stu-id="00989-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="00989-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="00989-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="00989-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="00989-129">datetime2</span></span>  <br/> |<span data-ttu-id="00989-130">實際檔案傳輸作業 (適用于合規性服務使用) 的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="00989-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="00989-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="00989-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="00989-132">稍微</span><span class="sxs-lookup"><span data-stu-id="00989-132">bit</span></span>  <br/> |<span data-ttu-id="00989-133">如果上傳則為 True;如果下載 (適用于相容性服務使用), 則為 False。</span><span class="sxs-lookup"><span data-stu-id="00989-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="00989-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="00989-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="00989-135">bit、not null</span><span class="sxs-lookup"><span data-stu-id="00989-135">bit, not null</span></span>  <br/> |<span data-ttu-id="00989-136">如果權杖已釘選, 則為 True。</span><span class="sxs-lookup"><span data-stu-id="00989-136">True if token is pinned.</span></span> <span data-ttu-id="00989-137">它是用來在表格中保留權杖, 直到合規性服務有機會從它取得相關欄位為止。</span><span class="sxs-lookup"><span data-stu-id="00989-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="00989-138">**鍵**</span><span class="sxs-lookup"><span data-stu-id="00989-138">**Keys**</span></span>

|<span data-ttu-id="00989-139">**左欄**</span><span class="sxs-lookup"><span data-stu-id="00989-139">**Column**</span></span>|<span data-ttu-id="00989-140">**說明**</span><span class="sxs-lookup"><span data-stu-id="00989-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="00989-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="00989-141">fileToken</span></span>  <br/> |<span data-ttu-id="00989-142">主鍵。</span><span class="sxs-lookup"><span data-stu-id="00989-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="00989-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="00989-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="00989-144">在 tblNode nodeGuid 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="00989-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

