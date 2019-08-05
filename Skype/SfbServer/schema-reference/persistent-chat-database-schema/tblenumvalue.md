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
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue 是一種硬編碼資料表, 其中包含在節點資料表中使用之屬性的可見度及行為值。
ms.openlocfilehash: bf1ddf75fc7b7fd78c85f47626b465a4d74e5ca2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192738"
---
# <a name="tblenumvalue"></a><span data-ttu-id="b7f04-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="b7f04-103">tblEnumValue</span></span>
 
<span data-ttu-id="b7f04-104">tblEnumValue 是一種硬編碼資料表, 其中包含在節點資料表中使用之屬性的可見度及行為值。</span><span class="sxs-lookup"><span data-stu-id="b7f04-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="b7f04-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="b7f04-105">**Columns**</span></span>

|<span data-ttu-id="b7f04-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="b7f04-106">**Column**</span></span>|<span data-ttu-id="b7f04-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="b7f04-107">**Type**</span></span>|<span data-ttu-id="b7f04-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="b7f04-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b7f04-109">valueID</span><span class="sxs-lookup"><span data-stu-id="b7f04-109">valueID</span></span>  <br/> |<span data-ttu-id="b7f04-110">Smallint, not null</span><span class="sxs-lookup"><span data-stu-id="b7f04-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="b7f04-111">值的識別碼。</span><span class="sxs-lookup"><span data-stu-id="b7f04-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="b7f04-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="b7f04-112">attributeID</span></span>  <br/> |<span data-ttu-id="b7f04-113">Smallint, not null</span><span class="sxs-lookup"><span data-stu-id="b7f04-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="b7f04-114">屬性識別碼。</span><span class="sxs-lookup"><span data-stu-id="b7f04-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="b7f04-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="b7f04-115">attributeValue</span></span>  <br/> |<span data-ttu-id="b7f04-116">Nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="b7f04-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="b7f04-117">值的名稱。</span><span class="sxs-lookup"><span data-stu-id="b7f04-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="b7f04-118">**鍵**</span><span class="sxs-lookup"><span data-stu-id="b7f04-118">**Keys**</span></span>

|<span data-ttu-id="b7f04-119">**左欄**</span><span class="sxs-lookup"><span data-stu-id="b7f04-119">**Column**</span></span>|<span data-ttu-id="b7f04-120">**說明**</span><span class="sxs-lookup"><span data-stu-id="b7f04-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b7f04-121">valueID</span><span class="sxs-lookup"><span data-stu-id="b7f04-121">valueID</span></span>  <br/> |<span data-ttu-id="b7f04-122">主鍵。</span><span class="sxs-lookup"><span data-stu-id="b7f04-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="b7f04-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="b7f04-123">attributeID</span></span>  <br/> |<span data-ttu-id="b7f04-124">在 tblEnumAttribute attributeID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="b7f04-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="b7f04-125">**資料表值**</span><span class="sxs-lookup"><span data-stu-id="b7f04-125">**Table Values**</span></span>

|<span data-ttu-id="b7f04-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="b7f04-126">**valueID**</span></span>|<span data-ttu-id="b7f04-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="b7f04-127">**attributeID**</span></span>|<span data-ttu-id="b7f04-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="b7f04-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b7f04-129">pplx-2</span><span class="sxs-lookup"><span data-stu-id="b7f04-129">2</span></span>  <br/> |<span data-ttu-id="b7f04-130">sr-1</span><span class="sxs-lookup"><span data-stu-id="b7f04-130">1</span></span>  <br/> |<span data-ttu-id="b7f04-131">私有</span><span class="sxs-lookup"><span data-stu-id="b7f04-131">private</span></span>  <br/> |
|<span data-ttu-id="b7f04-132">3</span><span class="sxs-lookup"><span data-stu-id="b7f04-132">3</span></span>  <br/> |<span data-ttu-id="b7f04-133">sr-1</span><span class="sxs-lookup"><span data-stu-id="b7f04-133">1</span></span>  <br/> |<span data-ttu-id="b7f04-134">討論</span><span class="sxs-lookup"><span data-stu-id="b7f04-134">scope</span></span>  <br/> |
|<span data-ttu-id="b7f04-135">4</span><span class="sxs-lookup"><span data-stu-id="b7f04-135">4</span></span>  <br/> |<span data-ttu-id="b7f04-136">pplx-2</span><span class="sxs-lookup"><span data-stu-id="b7f04-136">2</span></span>  <br/> |<span data-ttu-id="b7f04-137">標準</span><span class="sxs-lookup"><span data-stu-id="b7f04-137">normal</span></span>  <br/> |
|<span data-ttu-id="b7f04-138">500</span><span class="sxs-lookup"><span data-stu-id="b7f04-138">5</span></span>  <br/> |<span data-ttu-id="b7f04-139">pplx-2</span><span class="sxs-lookup"><span data-stu-id="b7f04-139">2</span></span>  <br/> |<span data-ttu-id="b7f04-140">auditorium</span><span class="sxs-lookup"><span data-stu-id="b7f04-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="b7f04-141">6</span><span class="sxs-lookup"><span data-stu-id="b7f04-141">6</span></span>  <br/> |<span data-ttu-id="b7f04-142">sr-1</span><span class="sxs-lookup"><span data-stu-id="b7f04-142">1</span></span>  <br/> |<span data-ttu-id="b7f04-143">開啟</span><span class="sxs-lookup"><span data-stu-id="b7f04-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b7f04-144">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b7f04-144">See also</span></span>

[<span data-ttu-id="b7f04-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="b7f04-145">tblNode</span></span>](tblnode.md)
