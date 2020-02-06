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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef 表格會儲存可能發生的每個錯誤類型的相關資訊。 每一筆記錄都是一種錯誤類型。
ms.openlocfilehash: f686692bee334c0927b6e8342cfb7152b3e54f0c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815231"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="363b5-104">商務用 Skype Server 2015 中的 ErrorDef 表格</span><span class="sxs-lookup"><span data-stu-id="363b5-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="363b5-105">ErrorDef 表格會儲存可能發生的每個錯誤類型的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="363b5-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="363b5-106">每一筆記錄都是一種錯誤類型。</span><span class="sxs-lookup"><span data-stu-id="363b5-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="363b5-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="363b5-107">**Column**</span></span>|<span data-ttu-id="363b5-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="363b5-108">**Data Type**</span></span>|<span data-ttu-id="363b5-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="363b5-109">**Key/Index**</span></span>|<span data-ttu-id="363b5-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="363b5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="363b5-111">**ErrorId**</span><span class="sxs-lookup"><span data-stu-id="363b5-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="363b5-112">int</span><span class="sxs-lookup"><span data-stu-id="363b5-112">int</span></span>  <br/> |<span data-ttu-id="363b5-113">首選</span><span class="sxs-lookup"><span data-stu-id="363b5-113">Primary</span></span>  <br/> |<span data-ttu-id="363b5-114">標識此類型錯誤的唯一識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="363b5-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="363b5-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="363b5-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="363b5-116">int</span><span class="sxs-lookup"><span data-stu-id="363b5-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="363b5-117">與此錯誤相關聯的標準 SIP 回應程式碼。</span><span class="sxs-lookup"><span data-stu-id="363b5-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="363b5-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="363b5-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="363b5-119">int</span><span class="sxs-lookup"><span data-stu-id="363b5-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="363b5-120">Microsoft 診斷 ID。</span><span class="sxs-lookup"><span data-stu-id="363b5-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="363b5-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="363b5-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="363b5-122">Int</span><span class="sxs-lookup"><span data-stu-id="363b5-122">Int</span></span>  <br/> |<span data-ttu-id="363b5-123">外</span><span class="sxs-lookup"><span data-stu-id="363b5-123">Foreign</span></span>  <br/> |<span data-ttu-id="363b5-124">通話的類型。</span><span class="sxs-lookup"><span data-stu-id="363b5-124">Type of the call.</span></span> <span data-ttu-id="363b5-125">如需詳細資訊，請參閱[商務用 Skype Server 2015 中](calltype.md)的 [CallType] 資料表。</span><span class="sxs-lookup"><span data-stu-id="363b5-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="363b5-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="363b5-126">**RequestType**</span></span> <br/> |<span data-ttu-id="363b5-127">Varbinary （33）</span><span class="sxs-lookup"><span data-stu-id="363b5-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="363b5-128">失敗的要求類型。</span><span class="sxs-lookup"><span data-stu-id="363b5-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="363b5-129">您可以使用下列語法，將此資料轉換成文字格式：</span><span class="sxs-lookup"><span data-stu-id="363b5-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="363b5-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="363b5-130">**ContentType**</span></span> <br/> |<span data-ttu-id="363b5-131">Varbinary （257）</span><span class="sxs-lookup"><span data-stu-id="363b5-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="363b5-132">失敗之要求的內容類型。</span><span class="sxs-lookup"><span data-stu-id="363b5-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="363b5-133">您可以使用此 syntaxt，將此資料轉換成文字格式：</span><span class="sxs-lookup"><span data-stu-id="363b5-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

