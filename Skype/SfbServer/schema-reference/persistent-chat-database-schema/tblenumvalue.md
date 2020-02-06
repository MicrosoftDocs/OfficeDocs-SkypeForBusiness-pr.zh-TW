---
title: tblEnumValue
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
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue 是一種硬編碼資料表，其中包含在節點資料表中使用之屬性的可見度及行為值。
ms.openlocfilehash: accb9cb4801984bd4b3839cd44e5b7feb8d06baa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814601"
---
# <a name="tblenumvalue"></a><span data-ttu-id="e62e5-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="e62e5-103">tblEnumValue</span></span>
 
<span data-ttu-id="e62e5-104">tblEnumValue 是一種硬編碼資料表，其中包含在節點資料表中使用之屬性的可見度及行為值。</span><span class="sxs-lookup"><span data-stu-id="e62e5-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="e62e5-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="e62e5-105">**Columns**</span></span>

|<span data-ttu-id="e62e5-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="e62e5-106">**Column**</span></span>|<span data-ttu-id="e62e5-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="e62e5-107">**Type**</span></span>|<span data-ttu-id="e62e5-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="e62e5-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e62e5-109">valueID</span><span class="sxs-lookup"><span data-stu-id="e62e5-109">valueID</span></span>  <br/> |<span data-ttu-id="e62e5-110">Smallint，not null</span><span class="sxs-lookup"><span data-stu-id="e62e5-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="e62e5-111">值的識別碼。</span><span class="sxs-lookup"><span data-stu-id="e62e5-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="e62e5-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="e62e5-112">attributeID</span></span>  <br/> |<span data-ttu-id="e62e5-113">Smallint，not null</span><span class="sxs-lookup"><span data-stu-id="e62e5-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="e62e5-114">屬性識別碼。</span><span class="sxs-lookup"><span data-stu-id="e62e5-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="e62e5-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="e62e5-115">attributeValue</span></span>  <br/> |<span data-ttu-id="e62e5-116">Nvarchar （256），not null</span><span class="sxs-lookup"><span data-stu-id="e62e5-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="e62e5-117">值的名稱。</span><span class="sxs-lookup"><span data-stu-id="e62e5-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="e62e5-118">**鍵**</span><span class="sxs-lookup"><span data-stu-id="e62e5-118">**Keys**</span></span>

|<span data-ttu-id="e62e5-119">**左欄**</span><span class="sxs-lookup"><span data-stu-id="e62e5-119">**Column**</span></span>|<span data-ttu-id="e62e5-120">**說明**</span><span class="sxs-lookup"><span data-stu-id="e62e5-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e62e5-121">valueID</span><span class="sxs-lookup"><span data-stu-id="e62e5-121">valueID</span></span>  <br/> |<span data-ttu-id="e62e5-122">主鍵。</span><span class="sxs-lookup"><span data-stu-id="e62e5-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e62e5-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="e62e5-123">attributeID</span></span>  <br/> |<span data-ttu-id="e62e5-124">在 tblEnumAttribute attributeID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="e62e5-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="e62e5-125">**資料表值**</span><span class="sxs-lookup"><span data-stu-id="e62e5-125">**Table Values**</span></span>

|<span data-ttu-id="e62e5-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="e62e5-126">**valueID**</span></span>|<span data-ttu-id="e62e5-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="e62e5-127">**attributeID**</span></span>|<span data-ttu-id="e62e5-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="e62e5-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e62e5-129">2</span><span class="sxs-lookup"><span data-stu-id="e62e5-129">2</span></span>  <br/> |<span data-ttu-id="e62e5-130">1</span><span class="sxs-lookup"><span data-stu-id="e62e5-130">1</span></span>  <br/> |<span data-ttu-id="e62e5-131">私有</span><span class="sxs-lookup"><span data-stu-id="e62e5-131">private</span></span>  <br/> |
|<span data-ttu-id="e62e5-132">3</span><span class="sxs-lookup"><span data-stu-id="e62e5-132">3</span></span>  <br/> |<span data-ttu-id="e62e5-133">1</span><span class="sxs-lookup"><span data-stu-id="e62e5-133">1</span></span>  <br/> |<span data-ttu-id="e62e5-134">討論</span><span class="sxs-lookup"><span data-stu-id="e62e5-134">scope</span></span>  <br/> |
|<span data-ttu-id="e62e5-135">4</span><span class="sxs-lookup"><span data-stu-id="e62e5-135">4</span></span>  <br/> |<span data-ttu-id="e62e5-136">2</span><span class="sxs-lookup"><span data-stu-id="e62e5-136">2</span></span>  <br/> |<span data-ttu-id="e62e5-137">標準</span><span class="sxs-lookup"><span data-stu-id="e62e5-137">normal</span></span>  <br/> |
|<span data-ttu-id="e62e5-138">500</span><span class="sxs-lookup"><span data-stu-id="e62e5-138">5</span></span>  <br/> |<span data-ttu-id="e62e5-139">2</span><span class="sxs-lookup"><span data-stu-id="e62e5-139">2</span></span>  <br/> |<span data-ttu-id="e62e5-140">auditorium</span><span class="sxs-lookup"><span data-stu-id="e62e5-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="e62e5-141">6</span><span class="sxs-lookup"><span data-stu-id="e62e5-141">6</span></span>  <br/> |<span data-ttu-id="e62e5-142">1</span><span class="sxs-lookup"><span data-stu-id="e62e5-142">1</span></span>  <br/> |<span data-ttu-id="e62e5-143">開啟</span><span class="sxs-lookup"><span data-stu-id="e62e5-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e62e5-144">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e62e5-144">See also</span></span>

[<span data-ttu-id="e62e5-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="e62e5-145">tblNode</span></span>](tblnode.md)
