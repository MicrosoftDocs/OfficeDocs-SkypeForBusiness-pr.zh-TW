---
title: 商務用 Skype Server 2015 中的 ErrorDef 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef 表格會儲存可能發生的每個錯誤類型的相關資訊。 每一筆記錄都是一種錯誤類型。
ms.openlocfilehash: c6157bb62df47b8fcb1cd158605c5a357e623adf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192864"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="0cfb9-104">商務用 Skype Server 2015 中的 ErrorDef 表格</span><span class="sxs-lookup"><span data-stu-id="0cfb9-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0cfb9-105">ErrorDef 表格會儲存可能發生的每個錯誤類型的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0cfb9-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="0cfb9-106">每一筆記錄都是一種錯誤類型。</span><span class="sxs-lookup"><span data-stu-id="0cfb9-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="0cfb9-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="0cfb9-107">**Column**</span></span>|<span data-ttu-id="0cfb9-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="0cfb9-108">**Data Type**</span></span>|<span data-ttu-id="0cfb9-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="0cfb9-109">**Key/Index**</span></span>|<span data-ttu-id="0cfb9-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="0cfb9-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0cfb9-111">**ErrorId**</span><span class="sxs-lookup"><span data-stu-id="0cfb9-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="0cfb9-112">int</span><span class="sxs-lookup"><span data-stu-id="0cfb9-112">int</span></span>  <br/> |<span data-ttu-id="0cfb9-113">首選</span><span class="sxs-lookup"><span data-stu-id="0cfb9-113">Primary</span></span>  <br/> |<span data-ttu-id="0cfb9-114">標識此類型錯誤的唯一識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="0cfb9-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="0cfb9-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="0cfb9-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="0cfb9-116">int</span><span class="sxs-lookup"><span data-stu-id="0cfb9-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="0cfb9-117">與此錯誤相關聯的標準 SIP 回應程式碼。</span><span class="sxs-lookup"><span data-stu-id="0cfb9-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="0cfb9-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="0cfb9-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="0cfb9-119">int</span><span class="sxs-lookup"><span data-stu-id="0cfb9-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="0cfb9-120">Microsoft 診斷 ID。</span><span class="sxs-lookup"><span data-stu-id="0cfb9-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="0cfb9-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="0cfb9-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="0cfb9-122">Int</span><span class="sxs-lookup"><span data-stu-id="0cfb9-122">Int</span></span>  <br/> |<span data-ttu-id="0cfb9-123">外</span><span class="sxs-lookup"><span data-stu-id="0cfb9-123">Foreign</span></span>  <br/> |<span data-ttu-id="0cfb9-124">通話的類型。</span><span class="sxs-lookup"><span data-stu-id="0cfb9-124">Type of the call.</span></span> <span data-ttu-id="0cfb9-125">如需詳細資訊, 請參閱[商務用 Skype Server 2015 中](calltype.md)的 [CallType] 資料表。</span><span class="sxs-lookup"><span data-stu-id="0cfb9-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="0cfb9-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="0cfb9-126">**RequestType**</span></span> <br/> |<span data-ttu-id="0cfb9-127">Varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="0cfb9-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="0cfb9-128">失敗的要求類型。</span><span class="sxs-lookup"><span data-stu-id="0cfb9-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="0cfb9-129">您可以使用下列語法, 將此資料轉換成文字格式:</span><span class="sxs-lookup"><span data-stu-id="0cfb9-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="0cfb9-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="0cfb9-130">**ContentType**</span></span> <br/> |<span data-ttu-id="0cfb9-131">Varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="0cfb9-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="0cfb9-132">失敗之要求的內容類型。</span><span class="sxs-lookup"><span data-stu-id="0cfb9-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="0cfb9-133">您可以使用此 syntaxt, 將此資料轉換成文字格式:</span><span class="sxs-lookup"><span data-stu-id="0cfb9-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

