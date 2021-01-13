---
title: tblEnumValue
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
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue 是包含在節點表格中所使用之屬性的 Visibility 和行為值的硬編碼表格。
ms.openlocfilehash: a13bfbe79d1eb118f0727f390816a26d35a508d0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816023"
---
# <a name="tblenumvalue"></a><span data-ttu-id="3e0ac-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="3e0ac-103">tblEnumValue</span></span>
 
<span data-ttu-id="3e0ac-104">tblEnumValue 是包含在節點表格中所使用之屬性的 Visibility 和行為值的硬編碼表格。</span><span class="sxs-lookup"><span data-stu-id="3e0ac-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="3e0ac-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="3e0ac-105">**Columns**</span></span>

|<span data-ttu-id="3e0ac-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="3e0ac-106">**Column**</span></span>|<span data-ttu-id="3e0ac-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="3e0ac-107">**Type**</span></span>|<span data-ttu-id="3e0ac-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="3e0ac-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3e0ac-109">valueID</span><span class="sxs-lookup"><span data-stu-id="3e0ac-109">valueID</span></span>  <br/> |<span data-ttu-id="3e0ac-110">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="3e0ac-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="3e0ac-111">值的識別碼。</span><span class="sxs-lookup"><span data-stu-id="3e0ac-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="3e0ac-112">attributeID:</span><span class="sxs-lookup"><span data-stu-id="3e0ac-112">attributeID</span></span>  <br/> |<span data-ttu-id="3e0ac-113">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="3e0ac-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="3e0ac-114">屬性的識別碼。</span><span class="sxs-lookup"><span data-stu-id="3e0ac-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="3e0ac-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="3e0ac-115">attributeValue</span></span>  <br/> |<span data-ttu-id="3e0ac-116">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="3e0ac-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="3e0ac-117">值的名稱。</span><span class="sxs-lookup"><span data-stu-id="3e0ac-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="3e0ac-118">**Keys**</span><span class="sxs-lookup"><span data-stu-id="3e0ac-118">**Keys**</span></span>

|<span data-ttu-id="3e0ac-119">**欄**</span><span class="sxs-lookup"><span data-stu-id="3e0ac-119">**Column**</span></span>|<span data-ttu-id="3e0ac-120">**描述**</span><span class="sxs-lookup"><span data-stu-id="3e0ac-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3e0ac-121">valueID</span><span class="sxs-lookup"><span data-stu-id="3e0ac-121">valueID</span></span>  <br/> |<span data-ttu-id="3e0ac-122">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="3e0ac-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="3e0ac-123">attributeID:</span><span class="sxs-lookup"><span data-stu-id="3e0ac-123">attributeID</span></span>  <br/> |<span data-ttu-id="3e0ac-124">在 tblEnumAttribute.attributeID 表格中查閱的外鍵。</span><span class="sxs-lookup"><span data-stu-id="3e0ac-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="3e0ac-125">**表格值**</span><span class="sxs-lookup"><span data-stu-id="3e0ac-125">**Table Values**</span></span>

|<span data-ttu-id="3e0ac-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="3e0ac-126">**valueID**</span></span>|<span data-ttu-id="3e0ac-127">**attributeID:**</span><span class="sxs-lookup"><span data-stu-id="3e0ac-127">**attributeID**</span></span>|<span data-ttu-id="3e0ac-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="3e0ac-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3e0ac-129">2 </span><span class="sxs-lookup"><span data-stu-id="3e0ac-129">2</span></span>  <br/> |<span data-ttu-id="3e0ac-130">1 </span><span class="sxs-lookup"><span data-stu-id="3e0ac-130">1</span></span>  <br/> |<span data-ttu-id="3e0ac-131">私人</span><span class="sxs-lookup"><span data-stu-id="3e0ac-131">private</span></span>  <br/> |
|<span data-ttu-id="3e0ac-132">3 </span><span class="sxs-lookup"><span data-stu-id="3e0ac-132">3</span></span>  <br/> |<span data-ttu-id="3e0ac-133">1 </span><span class="sxs-lookup"><span data-stu-id="3e0ac-133">1</span></span>  <br/> |<span data-ttu-id="3e0ac-134">範圍</span><span class="sxs-lookup"><span data-stu-id="3e0ac-134">scope</span></span>  <br/> |
|<span data-ttu-id="3e0ac-135">4 </span><span class="sxs-lookup"><span data-stu-id="3e0ac-135">4</span></span>  <br/> |<span data-ttu-id="3e0ac-136">2 </span><span class="sxs-lookup"><span data-stu-id="3e0ac-136">2</span></span>  <br/> |<span data-ttu-id="3e0ac-137">正常</span><span class="sxs-lookup"><span data-stu-id="3e0ac-137">normal</span></span>  <br/> |
|<span data-ttu-id="3e0ac-138">5 </span><span class="sxs-lookup"><span data-stu-id="3e0ac-138">5</span></span>  <br/> |<span data-ttu-id="3e0ac-139">2 </span><span class="sxs-lookup"><span data-stu-id="3e0ac-139">2</span></span>  <br/> |<span data-ttu-id="3e0ac-140">禮堂</span><span class="sxs-lookup"><span data-stu-id="3e0ac-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="3e0ac-141">6 </span><span class="sxs-lookup"><span data-stu-id="3e0ac-141">6</span></span>  <br/> |<span data-ttu-id="3e0ac-142">1 </span><span class="sxs-lookup"><span data-stu-id="3e0ac-142">1</span></span>  <br/> |<span data-ttu-id="3e0ac-143">打開</span><span class="sxs-lookup"><span data-stu-id="3e0ac-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3e0ac-144">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3e0ac-144">See also</span></span>

[<span data-ttu-id="3e0ac-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="3e0ac-145">tblNode</span></span>](tblnode.md)
