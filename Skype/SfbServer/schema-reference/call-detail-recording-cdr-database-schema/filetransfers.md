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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTransfer view 會儲存對等檔案傳輸會話的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。
ms.openlocfilehash: d650c04b8dada5828eed5d7bc3039cb77570ce2b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815201"
---
# <a name="filetransfers-view"></a><span data-ttu-id="d6a83-104">FileTransfers 視圖</span><span class="sxs-lookup"><span data-stu-id="d6a83-104">FileTransfers view</span></span>
 
<span data-ttu-id="d6a83-105">FileTransfer view 會儲存對等檔案傳輸會話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d6a83-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="d6a83-106">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="d6a83-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d6a83-107">[FileTransfers] 視圖會包含 [ [SessionDetails] 視圖](sessiondetails-0.md)中的所有資料行，以及下方所列的欄。</span><span class="sxs-lookup"><span data-stu-id="d6a83-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="d6a83-108">**左欄**</span><span class="sxs-lookup"><span data-stu-id="d6a83-108">**Column**</span></span>|<span data-ttu-id="d6a83-109">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="d6a83-109">**Data Type**</span></span>|<span data-ttu-id="d6a83-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="d6a83-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d6a83-111">**副檔名**</span><span class="sxs-lookup"><span data-stu-id="d6a83-111">**FileName**</span></span> <br/> |<span data-ttu-id="d6a83-112">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="d6a83-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d6a83-113">已傳輸檔案的名稱。</span><span class="sxs-lookup"><span data-stu-id="d6a83-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="d6a83-114">**C**</span><span class="sxs-lookup"><span data-stu-id="d6a83-114">**Cookie**</span></span> <br/> |<span data-ttu-id="d6a83-115">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="d6a83-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="d6a83-116">用來識別與此郵件相關聯的每一封後續訊息。</span><span class="sxs-lookup"><span data-stu-id="d6a83-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="d6a83-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="d6a83-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="d6a83-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="d6a83-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="d6a83-119">唯一識別碼，區分涉及相同檔案名的檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="d6a83-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="d6a83-120">**接受**</span><span class="sxs-lookup"><span data-stu-id="d6a83-120">**Accept**</span></span> <br/> |<span data-ttu-id="d6a83-121">稍微</span><span class="sxs-lookup"><span data-stu-id="d6a83-121">bit</span></span>  <br/> |<span data-ttu-id="d6a83-122">可以是 TRUE 或 Null。</span><span class="sxs-lookup"><span data-stu-id="d6a83-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="d6a83-123">如果為 TRUE，則 [拒絕] 和 [取消] 將會是 Null。</span><span class="sxs-lookup"><span data-stu-id="d6a83-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="d6a83-124">**否決**</span><span class="sxs-lookup"><span data-stu-id="d6a83-124">**Reject**</span></span> <br/> |<span data-ttu-id="d6a83-125">稍微</span><span class="sxs-lookup"><span data-stu-id="d6a83-125">bit</span></span>  <br/> |<span data-ttu-id="d6a83-126">可以是 TRUE 或 Null。</span><span class="sxs-lookup"><span data-stu-id="d6a83-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="d6a83-127">如果為 TRUE，則 [接受] 和 [取消] 將會是 Null。</span><span class="sxs-lookup"><span data-stu-id="d6a83-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="d6a83-128">**取消**</span><span class="sxs-lookup"><span data-stu-id="d6a83-128">**Cancel**</span></span> <br/> |<span data-ttu-id="d6a83-129">稍微</span><span class="sxs-lookup"><span data-stu-id="d6a83-129">bit</span></span>  <br/> |<span data-ttu-id="d6a83-130">可以是 TRUE 或 Null。</span><span class="sxs-lookup"><span data-stu-id="d6a83-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="d6a83-131">如果為 TRUE，則 [接受] 和 [拒絕] 會是 Null。</span><span class="sxs-lookup"><span data-stu-id="d6a83-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

