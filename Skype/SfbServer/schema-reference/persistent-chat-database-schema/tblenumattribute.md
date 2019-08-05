---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute 是一種硬編碼資料表, 其中包含在節點資料表中使用的 Visibility 和行為屬性。
ms.openlocfilehash: b326ebe98592daccf7560dc90e299f31c158cd5c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192739"
---
# <a name="tblenumattribute"></a><span data-ttu-id="07ce0-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="07ce0-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="07ce0-104">tblEnumAttribute 是一種硬編碼資料表, 其中包含在節點資料表中使用的 Visibility 和行為屬性。</span><span class="sxs-lookup"><span data-stu-id="07ce0-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="07ce0-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="07ce0-105">**Columns**</span></span>

|<span data-ttu-id="07ce0-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="07ce0-106">**Column**</span></span>|<span data-ttu-id="07ce0-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="07ce0-107">**Type**</span></span>|<span data-ttu-id="07ce0-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="07ce0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="07ce0-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="07ce0-109">attributeID</span></span>  <br/> |<span data-ttu-id="07ce0-110">Smallint, not null</span><span class="sxs-lookup"><span data-stu-id="07ce0-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="07ce0-111">屬性識別碼。</span><span class="sxs-lookup"><span data-stu-id="07ce0-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="07ce0-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="07ce0-112">attributeName</span></span>  <br/> |<span data-ttu-id="07ce0-113">Nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="07ce0-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="07ce0-114">屬性的名稱。</span><span class="sxs-lookup"><span data-stu-id="07ce0-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="07ce0-115">**快速鍵**</span><span class="sxs-lookup"><span data-stu-id="07ce0-115">**Key**</span></span>

|<span data-ttu-id="07ce0-116">**左欄**</span><span class="sxs-lookup"><span data-stu-id="07ce0-116">**Column**</span></span>|<span data-ttu-id="07ce0-117">**說明**</span><span class="sxs-lookup"><span data-stu-id="07ce0-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="07ce0-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="07ce0-118">attributeID</span></span>  <br/> |<span data-ttu-id="07ce0-119">主鍵。</span><span class="sxs-lookup"><span data-stu-id="07ce0-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="07ce0-120">**資料表值**</span><span class="sxs-lookup"><span data-stu-id="07ce0-120">**Table Values**</span></span>

|<span data-ttu-id="07ce0-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="07ce0-121">**attributeID**</span></span>|<span data-ttu-id="07ce0-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="07ce0-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="07ce0-123">sr-1</span><span class="sxs-lookup"><span data-stu-id="07ce0-123">1</span></span>  <br/> |<span data-ttu-id="07ce0-124">看見.</span><span class="sxs-lookup"><span data-stu-id="07ce0-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="07ce0-125">pplx-2</span><span class="sxs-lookup"><span data-stu-id="07ce0-125">2</span></span>  <br/> |<span data-ttu-id="07ce0-126">行為.</span><span class="sxs-lookup"><span data-stu-id="07ce0-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="07ce0-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="07ce0-127">See also</span></span>

[<span data-ttu-id="07ce0-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="07ce0-128">tblNode</span></span>](tblnode.md)
