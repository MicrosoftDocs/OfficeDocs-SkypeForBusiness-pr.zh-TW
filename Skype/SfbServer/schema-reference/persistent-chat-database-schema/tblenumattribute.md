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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute 是一種硬編碼資料表，其中包含在節點資料表中使用的 Visibility 和行為屬性。
ms.openlocfilehash: 8244e2fb6ace6c4ed73f017f52df0c85d1f02315
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814611"
---
# <a name="tblenumattribute"></a><span data-ttu-id="32466-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="32466-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="32466-104">tblEnumAttribute 是一種硬編碼資料表，其中包含在節點資料表中使用的 Visibility 和行為屬性。</span><span class="sxs-lookup"><span data-stu-id="32466-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="32466-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="32466-105">**Columns**</span></span>

|<span data-ttu-id="32466-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="32466-106">**Column**</span></span>|<span data-ttu-id="32466-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="32466-107">**Type**</span></span>|<span data-ttu-id="32466-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="32466-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="32466-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="32466-109">attributeID</span></span>  <br/> |<span data-ttu-id="32466-110">Smallint，not null</span><span class="sxs-lookup"><span data-stu-id="32466-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="32466-111">屬性識別碼。</span><span class="sxs-lookup"><span data-stu-id="32466-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="32466-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="32466-112">attributeName</span></span>  <br/> |<span data-ttu-id="32466-113">Nvarchar （256），not null</span><span class="sxs-lookup"><span data-stu-id="32466-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="32466-114">屬性的名稱。</span><span class="sxs-lookup"><span data-stu-id="32466-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="32466-115">**機碼**</span><span class="sxs-lookup"><span data-stu-id="32466-115">**Key**</span></span>

|<span data-ttu-id="32466-116">**左欄**</span><span class="sxs-lookup"><span data-stu-id="32466-116">**Column**</span></span>|<span data-ttu-id="32466-117">**說明**</span><span class="sxs-lookup"><span data-stu-id="32466-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="32466-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="32466-118">attributeID</span></span>  <br/> |<span data-ttu-id="32466-119">主鍵。</span><span class="sxs-lookup"><span data-stu-id="32466-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="32466-120">**資料表值**</span><span class="sxs-lookup"><span data-stu-id="32466-120">**Table Values**</span></span>

|<span data-ttu-id="32466-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="32466-121">**attributeID**</span></span>|<span data-ttu-id="32466-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="32466-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="32466-123">1</span><span class="sxs-lookup"><span data-stu-id="32466-123">1</span></span>  <br/> |<span data-ttu-id="32466-124">看見.</span><span class="sxs-lookup"><span data-stu-id="32466-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="32466-125">2</span><span class="sxs-lookup"><span data-stu-id="32466-125">2</span></span>  <br/> |<span data-ttu-id="32466-126">行為.</span><span class="sxs-lookup"><span data-stu-id="32466-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="32466-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="32466-127">See also</span></span>

[<span data-ttu-id="32466-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="32466-128">tblNode</span></span>](tblnode.md)
