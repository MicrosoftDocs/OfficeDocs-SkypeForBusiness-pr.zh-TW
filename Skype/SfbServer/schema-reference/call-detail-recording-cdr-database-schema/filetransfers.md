---
title: FileTransfers 視圖
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTransfer view 會儲存對等檔案傳輸會話的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。
ms.openlocfilehash: 303a8cf624b19f9701cabbd491fcb7b08dfba25d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192856"
---
# <a name="filetransfers-view"></a><span data-ttu-id="913d5-104">FileTransfers 視圖</span><span class="sxs-lookup"><span data-stu-id="913d5-104">FileTransfers view</span></span>
 
<span data-ttu-id="913d5-105">FileTransfer view 會儲存對等檔案傳輸會話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="913d5-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="913d5-106">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="913d5-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="913d5-107">[FileTransfers] 視圖會包含 [ [SessionDetails] 視圖](sessiondetails-0.md)中的所有資料行, 以及下方所列的欄。</span><span class="sxs-lookup"><span data-stu-id="913d5-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="913d5-108">**左欄**</span><span class="sxs-lookup"><span data-stu-id="913d5-108">**Column**</span></span>|<span data-ttu-id="913d5-109">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="913d5-109">**Data Type**</span></span>|<span data-ttu-id="913d5-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="913d5-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="913d5-111">**副檔名**</span><span class="sxs-lookup"><span data-stu-id="913d5-111">**FileName**</span></span> <br/> |<span data-ttu-id="913d5-112">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="913d5-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="913d5-113">已傳輸檔案的名稱。</span><span class="sxs-lookup"><span data-stu-id="913d5-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="913d5-114">**C**</span><span class="sxs-lookup"><span data-stu-id="913d5-114">**Cookie**</span></span> <br/> |<span data-ttu-id="913d5-115">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="913d5-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="913d5-116">用來識別與此郵件相關聯的每一封後續訊息。</span><span class="sxs-lookup"><span data-stu-id="913d5-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="913d5-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="913d5-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="913d5-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="913d5-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="913d5-119">唯一識別碼, 區分涉及相同檔案名的檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="913d5-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="913d5-120">**接受**</span><span class="sxs-lookup"><span data-stu-id="913d5-120">**Accept**</span></span> <br/> |<span data-ttu-id="913d5-121">稍微</span><span class="sxs-lookup"><span data-stu-id="913d5-121">bit</span></span>  <br/> |<span data-ttu-id="913d5-122">可以是 TRUE 或 Null。</span><span class="sxs-lookup"><span data-stu-id="913d5-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="913d5-123">如果為 TRUE, 則 [拒絕] 和 [取消] 將會是 Null。</span><span class="sxs-lookup"><span data-stu-id="913d5-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="913d5-124">**否決**</span><span class="sxs-lookup"><span data-stu-id="913d5-124">**Reject**</span></span> <br/> |<span data-ttu-id="913d5-125">稍微</span><span class="sxs-lookup"><span data-stu-id="913d5-125">bit</span></span>  <br/> |<span data-ttu-id="913d5-126">可以是 TRUE 或 Null。</span><span class="sxs-lookup"><span data-stu-id="913d5-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="913d5-127">如果為 TRUE, 則 [接受] 和 [取消] 將會是 Null。</span><span class="sxs-lookup"><span data-stu-id="913d5-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="913d5-128">**取消**</span><span class="sxs-lookup"><span data-stu-id="913d5-128">**Cancel**</span></span> <br/> |<span data-ttu-id="913d5-129">稍微</span><span class="sxs-lookup"><span data-stu-id="913d5-129">bit</span></span>  <br/> |<span data-ttu-id="913d5-130">可以是 TRUE 或 Null。</span><span class="sxs-lookup"><span data-stu-id="913d5-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="913d5-131">如果為 TRUE, 則 [接受] 和 [拒絕] 會是 Null。</span><span class="sxs-lookup"><span data-stu-id="913d5-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

