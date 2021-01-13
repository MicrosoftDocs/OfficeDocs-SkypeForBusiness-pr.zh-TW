---
title: tblEnumAttribute
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
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute 表格是一種硬式編碼的表格，其中含有節點表格中所用的可見度及行為屬性。
ms.openlocfilehash: 698eda1e6e815ad4de4042312be1738a3a41d1f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809713"
---
# <a name="tblenumattribute"></a><span data-ttu-id="034b0-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="034b0-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="034b0-104">tblEnumAttribute 表格是一種硬式編碼的表格，其中含有節點表格中所用的可見度及行為屬性。</span><span class="sxs-lookup"><span data-stu-id="034b0-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="034b0-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="034b0-105">**Columns**</span></span>

|<span data-ttu-id="034b0-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="034b0-106">**Column**</span></span>|<span data-ttu-id="034b0-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="034b0-107">**Type**</span></span>|<span data-ttu-id="034b0-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="034b0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="034b0-109">attributeID:</span><span class="sxs-lookup"><span data-stu-id="034b0-109">attributeID</span></span>  <br/> |<span data-ttu-id="034b0-110">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="034b0-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="034b0-111">屬性的識別碼。</span><span class="sxs-lookup"><span data-stu-id="034b0-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="034b0-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="034b0-112">attributeName</span></span>  <br/> |<span data-ttu-id="034b0-113">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="034b0-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="034b0-114">屬性名稱。</span><span class="sxs-lookup"><span data-stu-id="034b0-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="034b0-115">**Key**</span><span class="sxs-lookup"><span data-stu-id="034b0-115">**Key**</span></span>

|<span data-ttu-id="034b0-116">**欄**</span><span class="sxs-lookup"><span data-stu-id="034b0-116">**Column**</span></span>|<span data-ttu-id="034b0-117">**描述**</span><span class="sxs-lookup"><span data-stu-id="034b0-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="034b0-118">attributeID:</span><span class="sxs-lookup"><span data-stu-id="034b0-118">attributeID</span></span>  <br/> |<span data-ttu-id="034b0-119">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="034b0-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="034b0-120">**表格值**</span><span class="sxs-lookup"><span data-stu-id="034b0-120">**Table Values**</span></span>

|<span data-ttu-id="034b0-121">**attributeID:**</span><span class="sxs-lookup"><span data-stu-id="034b0-121">**attributeID**</span></span>|<span data-ttu-id="034b0-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="034b0-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="034b0-123">1 </span><span class="sxs-lookup"><span data-stu-id="034b0-123">1</span></span>  <br/> |<span data-ttu-id="034b0-124">知名度。</span><span class="sxs-lookup"><span data-stu-id="034b0-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="034b0-125">2 </span><span class="sxs-lookup"><span data-stu-id="034b0-125">2</span></span>  <br/> |<span data-ttu-id="034b0-126">行為。</span><span class="sxs-lookup"><span data-stu-id="034b0-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="034b0-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="034b0-127">See also</span></span>

[<span data-ttu-id="034b0-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="034b0-128">tblNode</span></span>](tblnode.md)
