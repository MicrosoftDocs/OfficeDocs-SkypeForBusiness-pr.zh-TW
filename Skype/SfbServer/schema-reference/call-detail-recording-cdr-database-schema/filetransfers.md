---
title: FileTransfers view
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
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTransfer view 會儲存對等檔案傳輸會話的資訊。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: 8b3c2db012b8969bd4b5b75ca19ed090f8227c53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821683"
---
# <a name="filetransfers-view"></a><span data-ttu-id="1066c-104">FileTransfers view</span><span class="sxs-lookup"><span data-stu-id="1066c-104">FileTransfers view</span></span>
 
<span data-ttu-id="1066c-105">FileTransfer view 會儲存對等檔案傳輸會話的資訊。</span><span class="sxs-lookup"><span data-stu-id="1066c-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="1066c-106">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="1066c-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1066c-107">FileTransfers view 包含 [SessionDetails 視圖](sessiondetails-0.md) 中的所有欄，此外還會包含下列欄。</span><span class="sxs-lookup"><span data-stu-id="1066c-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="1066c-108">**欄**</span><span class="sxs-lookup"><span data-stu-id="1066c-108">**Column**</span></span>|<span data-ttu-id="1066c-109">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="1066c-109">**Data Type**</span></span>|<span data-ttu-id="1066c-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="1066c-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1066c-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="1066c-111">**FileName**</span></span> <br/> |<span data-ttu-id="1066c-112">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="1066c-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="1066c-113">已傳輸的檔案名稱。</span><span class="sxs-lookup"><span data-stu-id="1066c-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="1066c-114">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="1066c-114">**Cookie**</span></span> <br/> |<span data-ttu-id="1066c-115">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="1066c-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="1066c-116">可用來識別與此訊息相關聯的每則後續訊息。</span><span class="sxs-lookup"><span data-stu-id="1066c-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="1066c-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="1066c-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="1066c-118">唯一</span><span class="sxs-lookup"><span data-stu-id="1066c-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="1066c-119">唯一識別碼，用於分辨包含相同檔名的檔案傳輸。</span><span class="sxs-lookup"><span data-stu-id="1066c-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="1066c-120">**Accept**</span><span class="sxs-lookup"><span data-stu-id="1066c-120">**Accept**</span></span> <br/> |<span data-ttu-id="1066c-121">位</span><span class="sxs-lookup"><span data-stu-id="1066c-121">bit</span></span>  <br/> |<span data-ttu-id="1066c-p103">可為 TRUE 或 NULL。若為 TRUE，則「拒絕」和「取消」為 NULL。</span><span class="sxs-lookup"><span data-stu-id="1066c-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="1066c-124">**Reject**</span><span class="sxs-lookup"><span data-stu-id="1066c-124">**Reject**</span></span> <br/> |<span data-ttu-id="1066c-125">位</span><span class="sxs-lookup"><span data-stu-id="1066c-125">bit</span></span>  <br/> |<span data-ttu-id="1066c-p104">可為 TRUE 或 NULL。若為 TRUE，則「接受」和「取消」為 NULL。</span><span class="sxs-lookup"><span data-stu-id="1066c-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="1066c-128">**Cancel**</span><span class="sxs-lookup"><span data-stu-id="1066c-128">**Cancel**</span></span> <br/> |<span data-ttu-id="1066c-129">位</span><span class="sxs-lookup"><span data-stu-id="1066c-129">bit</span></span>  <br/> |<span data-ttu-id="1066c-p105">可為 TRUE 或 NULL。若為 TRUE，則「接受」和「拒絕」為 NULL。</span><span class="sxs-lookup"><span data-stu-id="1066c-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   

