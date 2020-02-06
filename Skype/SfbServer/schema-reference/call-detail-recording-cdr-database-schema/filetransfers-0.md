---
title: 商務用 Skype Server 2015 中的 FileTransfers 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: 每個記錄代表一個檔案傳輸會話。
ms.openlocfilehash: 8b287d2fc2c40fe7e20cb3abc4ed6e403da701b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815211"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="ab88f-103">商務用 Skype Server 2015 中的 FileTransfers 表格</span><span class="sxs-lookup"><span data-stu-id="ab88f-103">FileTransfers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ab88f-104">每個記錄代表一個檔案傳輸會話。</span><span class="sxs-lookup"><span data-stu-id="ab88f-104">Each record represents one file transfer session.</span></span>
  
|<span data-ttu-id="ab88f-105">**左欄**</span><span class="sxs-lookup"><span data-stu-id="ab88f-105">**Column**</span></span>|<span data-ttu-id="ab88f-106">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="ab88f-106">**Data Type**</span></span>|<span data-ttu-id="ab88f-107">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="ab88f-107">**Key/Index**</span></span>|<span data-ttu-id="ab88f-108">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="ab88f-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ab88f-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="ab88f-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="ab88f-110">datetime</span><span class="sxs-lookup"><span data-stu-id="ab88f-110">datetime</span></span>  <br/> |<span data-ttu-id="ab88f-111">主要、外部</span><span class="sxs-lookup"><span data-stu-id="ab88f-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ab88f-112">會話要求的時間。</span><span class="sxs-lookup"><span data-stu-id="ab88f-112">Time of session request.</span></span> <span data-ttu-id="ab88f-113">與**SessionIdSeq**搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="ab88f-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="ab88f-114">如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。</span><span class="sxs-lookup"><span data-stu-id="ab88f-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ab88f-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="ab88f-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="ab88f-116">int</span><span class="sxs-lookup"><span data-stu-id="ab88f-116">int</span></span>  <br/> |<span data-ttu-id="ab88f-117">主要、外部</span><span class="sxs-lookup"><span data-stu-id="ab88f-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="ab88f-118">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="ab88f-118">ID number to identify the session.</span></span> <span data-ttu-id="ab88f-119">與**SessionIdTime**搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="ab88f-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="ab88f-120">如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。</span><span class="sxs-lookup"><span data-stu-id="ab88f-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ab88f-121">**檔案名**</span><span class="sxs-lookup"><span data-stu-id="ab88f-121">**File Name**</span></span> <br/> |<span data-ttu-id="ab88f-122">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ab88f-122">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="ab88f-123">檔案的名稱。</span><span class="sxs-lookup"><span data-stu-id="ab88f-123">Name of the file.</span></span>  <br/> |
|<span data-ttu-id="ab88f-124">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="ab88f-124">**FileIdentity**</span></span> <br/> |<span data-ttu-id="ab88f-125">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="ab88f-125">uniqueidentifier</span></span>  <br/> ||<span data-ttu-id="ab88f-126">唯一識別碼，區分涉及相同檔案名的檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="ab88f-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="ab88f-127">**C**</span><span class="sxs-lookup"><span data-stu-id="ab88f-127">**Cookie**</span></span> <br/> |<span data-ttu-id="ab88f-128">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="ab88f-128">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="ab88f-129">首選</span><span class="sxs-lookup"><span data-stu-id="ab88f-129">Primary</span></span>  <br/> |<span data-ttu-id="ab88f-130">用來識別與此郵件相關聯的每一封後續訊息。</span><span class="sxs-lookup"><span data-stu-id="ab88f-130">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="ab88f-131">**接受**</span><span class="sxs-lookup"><span data-stu-id="ab88f-131">**Accept**</span></span> <br/> |<span data-ttu-id="ab88f-132">稍微</span><span class="sxs-lookup"><span data-stu-id="ab88f-132">bit</span></span>  <br/> ||<span data-ttu-id="ab88f-133">可以是 TRUE 或 Null。</span><span class="sxs-lookup"><span data-stu-id="ab88f-133">Can be TRUE or NULL.</span></span> <span data-ttu-id="ab88f-134">如果為 TRUE，則 [拒絕] 和 [取消] 將會是 Null。</span><span class="sxs-lookup"><span data-stu-id="ab88f-134">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="ab88f-135">**否決**</span><span class="sxs-lookup"><span data-stu-id="ab88f-135">**Reject**</span></span> <br/> |<span data-ttu-id="ab88f-136">稍微</span><span class="sxs-lookup"><span data-stu-id="ab88f-136">bit</span></span>  <br/> ||<span data-ttu-id="ab88f-137">可以是 TRUE 或 Null。</span><span class="sxs-lookup"><span data-stu-id="ab88f-137">Can be TRUE or NULL.</span></span> <span data-ttu-id="ab88f-138">如果為 TRUE，則 [接受] 和 [取消] 將會是 Null。</span><span class="sxs-lookup"><span data-stu-id="ab88f-138">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="ab88f-139">**取消**</span><span class="sxs-lookup"><span data-stu-id="ab88f-139">**Cancel**</span></span> <br/> |<span data-ttu-id="ab88f-140">稍微</span><span class="sxs-lookup"><span data-stu-id="ab88f-140">bit</span></span>  <br/> ||<span data-ttu-id="ab88f-141">可以是 TRUE 或 Null。</span><span class="sxs-lookup"><span data-stu-id="ab88f-141">Can be TRUE or NULL.</span></span> <span data-ttu-id="ab88f-142">如果為 TRUE，則 [接受] 和 [拒絕] 會是 Null。</span><span class="sxs-lookup"><span data-stu-id="ab88f-142">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
|<span data-ttu-id="ab88f-143">**LastModifiedTime**</span><span class="sxs-lookup"><span data-stu-id="ab88f-143">**LastModifiedTime**</span></span> <br/> |<span data-ttu-id="ab88f-144">Datetime</span><span class="sxs-lookup"><span data-stu-id="ab88f-144">Datetime</span></span>  <br/> ||<span data-ttu-id="ab88f-145">供監視服務內部使用。</span><span class="sxs-lookup"><span data-stu-id="ab88f-145">For internal use by the Monitoring service.</span></span>  <br/> <span data-ttu-id="ab88f-146">此欄位是在商務用 Skype Server 2015 中推出。</span><span class="sxs-lookup"><span data-stu-id="ab88f-146">This field was introduced in Skype for Business Server 2015.</span></span>  <br/> |
   

