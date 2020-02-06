---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta 包含必須從 Active Directory 網域服務更新的主體。
ms.openlocfilehash: c76f4a74b3f627d360a2d745e46b6f2dac26bff0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813571"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="6cda5-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="6cda5-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="6cda5-104">tblPrincipalMeta 包含必須從 Active Directory 網域服務更新的主體。</span><span class="sxs-lookup"><span data-stu-id="6cda5-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="6cda5-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="6cda5-105">**Columns**</span></span>

|<span data-ttu-id="6cda5-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="6cda5-106">**Column**</span></span>|<span data-ttu-id="6cda5-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="6cda5-107">**Type**</span></span>|<span data-ttu-id="6cda5-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="6cda5-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6cda5-109">prinID</span><span class="sxs-lookup"><span data-stu-id="6cda5-109">prinID</span></span>  <br/> |<span data-ttu-id="6cda5-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="6cda5-110">int, not null</span></span>  <br/> |<span data-ttu-id="6cda5-111">Principal ID。</span><span class="sxs-lookup"><span data-stu-id="6cda5-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="6cda5-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="6cda5-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="6cda5-113">bit、not null</span><span class="sxs-lookup"><span data-stu-id="6cda5-113">bit, not null</span></span>  <br/> |<span data-ttu-id="6cda5-114">如果必須重新整理承擔者隸屬關係，則為 True。</span><span class="sxs-lookup"><span data-stu-id="6cda5-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="6cda5-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="6cda5-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="6cda5-116">bit、not null</span><span class="sxs-lookup"><span data-stu-id="6cda5-116">bit, not null</span></span>  <br/> |<span data-ttu-id="6cda5-117">如果必須重新整理主體屬性，則為 True。</span><span class="sxs-lookup"><span data-stu-id="6cda5-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="6cda5-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="6cda5-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="6cda5-119">bit、not null</span><span class="sxs-lookup"><span data-stu-id="6cda5-119">bit, not null</span></span>  <br/> |<span data-ttu-id="6cda5-120">如果主體已遭刪除，則為 True。</span><span class="sxs-lookup"><span data-stu-id="6cda5-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="6cda5-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="6cda5-121">tryCount</span></span>  <br/> |<span data-ttu-id="6cda5-122">int</span><span class="sxs-lookup"><span data-stu-id="6cda5-122">int</span></span>  <br/> |<span data-ttu-id="6cda5-123">嘗試從目前已發生過的 AD DS 重新整理主體的次數。</span><span class="sxs-lookup"><span data-stu-id="6cda5-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="6cda5-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="6cda5-124">lastTry</span></span>  <br/> |<span data-ttu-id="6cda5-125">datetime</span><span class="sxs-lookup"><span data-stu-id="6cda5-125">datetime</span></span>  <br/> |<span data-ttu-id="6cda5-126">從最新嘗試重新整理主體的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="6cda5-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="6cda5-127">如果尚未嘗試重新整理，則可以是 null。</span><span class="sxs-lookup"><span data-stu-id="6cda5-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="6cda5-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="6cda5-128">nextTry</span></span>  <br/> |<span data-ttu-id="6cda5-129">datetime</span><span class="sxs-lookup"><span data-stu-id="6cda5-129">datetime</span></span>  <br/> |<span data-ttu-id="6cda5-130">下一次排程重新整理的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="6cda5-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="6cda5-131">如果沒有排程進一步的重新整理，就可以是 null。</span><span class="sxs-lookup"><span data-stu-id="6cda5-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="6cda5-132">**鍵**</span><span class="sxs-lookup"><span data-stu-id="6cda5-132">**Keys**</span></span>

|<span data-ttu-id="6cda5-133">**左欄**</span><span class="sxs-lookup"><span data-stu-id="6cda5-133">**Column**</span></span>|<span data-ttu-id="6cda5-134">**說明**</span><span class="sxs-lookup"><span data-stu-id="6cda5-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6cda5-135">prinID</span><span class="sxs-lookup"><span data-stu-id="6cda5-135">prinID</span></span>  <br/> |<span data-ttu-id="6cda5-136">主鍵。</span><span class="sxs-lookup"><span data-stu-id="6cda5-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="6cda5-137">prinID</span><span class="sxs-lookup"><span data-stu-id="6cda5-137">prinID</span></span>  <br/> |<span data-ttu-id="6cda5-138">在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="6cda5-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

