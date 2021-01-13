---
title: 商務用 Skype Server 2015 中的 ErrorDef 表格
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
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef 表會儲存可能發生的每一種錯誤類型的相關資訊。 每個記錄是一種錯誤類型。
ms.openlocfilehash: 50d7b76e1fc7edb53fbe0b299673b7281a394463
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821723"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="db4db-104">商務用 Skype Server 2015 中的 ErrorDef 表格</span><span class="sxs-lookup"><span data-stu-id="db4db-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="db4db-105">ErrorDef 表會儲存可能發生的每一種錯誤類型的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="db4db-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="db4db-106">每個記錄是一種錯誤類型。</span><span class="sxs-lookup"><span data-stu-id="db4db-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="db4db-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="db4db-107">**Column**</span></span>|<span data-ttu-id="db4db-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="db4db-108">**Data Type**</span></span>|<span data-ttu-id="db4db-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="db4db-109">**Key/Index**</span></span>|<span data-ttu-id="db4db-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="db4db-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="db4db-111">**ErrorId**</span><span class="sxs-lookup"><span data-stu-id="db4db-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="db4db-112">int</span><span class="sxs-lookup"><span data-stu-id="db4db-112">int</span></span>  <br/> |<span data-ttu-id="db4db-113">主要</span><span class="sxs-lookup"><span data-stu-id="db4db-113">Primary</span></span>  <br/> |<span data-ttu-id="db4db-114">用來識別這種錯誤類型的唯一識別碼號碼。</span><span class="sxs-lookup"><span data-stu-id="db4db-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="db4db-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="db4db-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="db4db-116">int</span><span class="sxs-lookup"><span data-stu-id="db4db-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="db4db-117">與此錯誤相關聯的標準 SIP 回應碼。</span><span class="sxs-lookup"><span data-stu-id="db4db-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="db4db-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="db4db-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="db4db-119">int</span><span class="sxs-lookup"><span data-stu-id="db4db-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="db4db-120">Microsoft 診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="db4db-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="db4db-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="db4db-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="db4db-122">臨界值</span><span class="sxs-lookup"><span data-stu-id="db4db-122">Int</span></span>  <br/> |<span data-ttu-id="db4db-123">Foreign</span><span class="sxs-lookup"><span data-stu-id="db4db-123">Foreign</span></span>  <br/> |<span data-ttu-id="db4db-124">通話的類型。</span><span class="sxs-lookup"><span data-stu-id="db4db-124">Type of the call.</span></span> <span data-ttu-id="db4db-125">如需詳細資訊，請參閱 [商務用 Skype Server 2015 中的 CallType 表格](calltype.md) 。</span><span class="sxs-lookup"><span data-stu-id="db4db-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="db4db-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="db4db-126">**RequestType**</span></span> <br/> |<span data-ttu-id="db4db-127">Varbinary (33) </span><span class="sxs-lookup"><span data-stu-id="db4db-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="db4db-128">失敗的要求類型。</span><span class="sxs-lookup"><span data-stu-id="db4db-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="db4db-129">您可以使用下列語法將此資料轉換成文字格式：</span><span class="sxs-lookup"><span data-stu-id="db4db-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="db4db-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="db4db-130">**ContentType**</span></span> <br/> |<span data-ttu-id="db4db-131">Varbinary (257) </span><span class="sxs-lookup"><span data-stu-id="db4db-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="db4db-132">失敗之要求的內容類型。</span><span class="sxs-lookup"><span data-stu-id="db4db-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="db4db-133">您可以使用此 syntaxt 將此資料轉換成文字格式：</span><span class="sxs-lookup"><span data-stu-id="db4db-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

