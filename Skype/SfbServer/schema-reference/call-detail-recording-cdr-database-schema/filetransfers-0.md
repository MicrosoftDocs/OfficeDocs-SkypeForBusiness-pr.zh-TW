---
title: 商務用 Skype Server 2015 中的 FileTransfers 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: 每筆記錄代表一個檔案傳輸工作階段。
ms.openlocfilehash: fde871bb434a2aa458bc59cfdf098c82ba3a7093
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821693"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a><span data-ttu-id="aa648-103">商務用 Skype Server 2015 中的 FileTransfers 表格</span><span class="sxs-lookup"><span data-stu-id="aa648-103">FileTransfers table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="aa648-104">每筆記錄代表一個檔案傳輸工作階段。</span><span class="sxs-lookup"><span data-stu-id="aa648-104">Each record represents one file transfer session.</span></span>
  
|<span data-ttu-id="aa648-105">**欄**</span><span class="sxs-lookup"><span data-stu-id="aa648-105">**Column**</span></span>|<span data-ttu-id="aa648-106">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="aa648-106">**Data Type**</span></span>|<span data-ttu-id="aa648-107">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="aa648-107">**Key/Index**</span></span>|<span data-ttu-id="aa648-108">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="aa648-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="aa648-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="aa648-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="aa648-110">datetime</span><span class="sxs-lookup"><span data-stu-id="aa648-110">datetime</span></span>  <br/> |<span data-ttu-id="aa648-111">主要，外部</span><span class="sxs-lookup"><span data-stu-id="aa648-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="aa648-112">工作階段要求的時間。</span><span class="sxs-lookup"><span data-stu-id="aa648-112">Time of session request.</span></span> <span data-ttu-id="aa648-113">其會與 **SessionIdSeq** 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="aa648-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="aa648-114">如需詳細資訊，請參閱 [商務用 Skype Server 2015 中的對話方塊表格](dialogs.md) 。</span><span class="sxs-lookup"><span data-stu-id="aa648-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="aa648-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="aa648-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="aa648-116">int</span><span class="sxs-lookup"><span data-stu-id="aa648-116">int</span></span>  <br/> |<span data-ttu-id="aa648-117">主要，外部</span><span class="sxs-lookup"><span data-stu-id="aa648-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="aa648-118">用來識別工作階段的識別碼。</span><span class="sxs-lookup"><span data-stu-id="aa648-118">ID number to identify the session.</span></span> <span data-ttu-id="aa648-119">會與 **SessionIdTime** 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="aa648-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="aa648-120">如需詳細資訊，請參閱 [商務用 Skype Server 2015 中的對話方塊表格](dialogs.md) 。</span><span class="sxs-lookup"><span data-stu-id="aa648-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="aa648-121">**檔案名稱**</span><span class="sxs-lookup"><span data-stu-id="aa648-121">**File Name**</span></span> <br/> |<span data-ttu-id="aa648-122">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="aa648-122">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="aa648-123">檔案的名稱。</span><span class="sxs-lookup"><span data-stu-id="aa648-123">Name of the file.</span></span>  <br/> |
|<span data-ttu-id="aa648-124">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="aa648-124">**FileIdentity**</span></span> <br/> |<span data-ttu-id="aa648-125">唯一</span><span class="sxs-lookup"><span data-stu-id="aa648-125">uniqueidentifier</span></span>  <br/> ||<span data-ttu-id="aa648-126">唯一識別碼，用於分辨包含相同檔名的檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="aa648-126">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="aa648-127">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="aa648-127">**Cookie**</span></span> <br/> |<span data-ttu-id="aa648-128">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="aa648-128">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="aa648-129">主要</span><span class="sxs-lookup"><span data-stu-id="aa648-129">Primary</span></span>  <br/> |<span data-ttu-id="aa648-130">可用來識別與此訊息相關聯的每則後續訊息。</span><span class="sxs-lookup"><span data-stu-id="aa648-130">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="aa648-131">**Accept**</span><span class="sxs-lookup"><span data-stu-id="aa648-131">**Accept**</span></span> <br/> |<span data-ttu-id="aa648-132">位</span><span class="sxs-lookup"><span data-stu-id="aa648-132">bit</span></span>  <br/> ||<span data-ttu-id="aa648-p103">可為 TRUE 或 NULL。若為 TRUE，則「拒絕」和「取消」為 NULL。</span><span class="sxs-lookup"><span data-stu-id="aa648-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="aa648-135">**Reject**</span><span class="sxs-lookup"><span data-stu-id="aa648-135">**Reject**</span></span> <br/> |<span data-ttu-id="aa648-136">位</span><span class="sxs-lookup"><span data-stu-id="aa648-136">bit</span></span>  <br/> ||<span data-ttu-id="aa648-p104">可為 TRUE 或 NULL。若為 TRUE，則「接受」和「取消」為 NULL。</span><span class="sxs-lookup"><span data-stu-id="aa648-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="aa648-139">**Cancel**</span><span class="sxs-lookup"><span data-stu-id="aa648-139">**Cancel**</span></span> <br/> |<span data-ttu-id="aa648-140">位</span><span class="sxs-lookup"><span data-stu-id="aa648-140">bit</span></span>  <br/> ||<span data-ttu-id="aa648-p105">可為 TRUE 或 NULL。若為 TRUE，則「接受」和「拒絕」為 NULL。</span><span class="sxs-lookup"><span data-stu-id="aa648-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
|<span data-ttu-id="aa648-143">**LastModifiedTime**</span><span class="sxs-lookup"><span data-stu-id="aa648-143">**LastModifiedTime**</span></span> <br/> |<span data-ttu-id="aa648-144">Datetime</span><span class="sxs-lookup"><span data-stu-id="aa648-144">Datetime</span></span>  <br/> ||<span data-ttu-id="aa648-145">供監控服務內部使用。</span><span class="sxs-lookup"><span data-stu-id="aa648-145">For internal use by the Monitoring service.</span></span>  <br/> <span data-ttu-id="aa648-146">此欄位已引進商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="aa648-146">This field was introduced in Skype for Business Server 2015.</span></span>  <br/> |
   

