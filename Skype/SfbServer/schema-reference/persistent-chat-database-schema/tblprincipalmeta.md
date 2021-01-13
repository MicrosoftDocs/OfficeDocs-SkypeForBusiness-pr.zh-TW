---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta 包含必須從 Active Directory 網域服務重新整理的主體。
ms.openlocfilehash: e10b56a8a3a1c25f73cd1a07f4fdcde18c6f1215
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831543"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="10c64-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="10c64-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="10c64-104">tblPrincipalMeta 包含必須從 Active Directory 網域服務重新整理的主體。</span><span class="sxs-lookup"><span data-stu-id="10c64-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="10c64-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="10c64-105">**Columns**</span></span>

|<span data-ttu-id="10c64-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="10c64-106">**Column**</span></span>|<span data-ttu-id="10c64-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="10c64-107">**Type**</span></span>|<span data-ttu-id="10c64-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="10c64-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="10c64-109">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="10c64-109">prinID</span></span>  <br/> |<span data-ttu-id="10c64-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="10c64-110">int, not null</span></span>  <br/> |<span data-ttu-id="10c64-111">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="10c64-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="10c64-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="10c64-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="10c64-113">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="10c64-113">bit, not null</span></span>  <br/> |<span data-ttu-id="10c64-114">若主體關係必須重新整理，則為 True。</span><span class="sxs-lookup"><span data-stu-id="10c64-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="10c64-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="10c64-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="10c64-116">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="10c64-116">bit, not null</span></span>  <br/> |<span data-ttu-id="10c64-117">若主體屬性必須重新整理，則為 True。</span><span class="sxs-lookup"><span data-stu-id="10c64-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="10c64-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="10c64-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="10c64-119">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="10c64-119">bit, not null</span></span>  <br/> |<span data-ttu-id="10c64-120">若主體已刪除，則為 True。</span><span class="sxs-lookup"><span data-stu-id="10c64-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="10c64-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="10c64-121">tryCount</span></span>  <br/> |<span data-ttu-id="10c64-122">int</span><span class="sxs-lookup"><span data-stu-id="10c64-122">int</span></span>  <br/> |<span data-ttu-id="10c64-123">至今嘗試從 AD DS 重新整理主體的次數。</span><span class="sxs-lookup"><span data-stu-id="10c64-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="10c64-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="10c64-124">lastTry</span></span>  <br/> |<span data-ttu-id="10c64-125">datetime</span><span class="sxs-lookup"><span data-stu-id="10c64-125">datetime</span></span>  <br/> |<span data-ttu-id="10c64-p101">最近一次嘗試重新整理主體的時間戳記。若尚未重新整理過，可以是 null。</span><span class="sxs-lookup"><span data-stu-id="10c64-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="10c64-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="10c64-128">nextTry</span></span>  <br/> |<span data-ttu-id="10c64-129">datetime</span><span class="sxs-lookup"><span data-stu-id="10c64-129">datetime</span></span>  <br/> |<span data-ttu-id="10c64-p102">排定下次重新整理時間戳記。若未排定之後的重新整理，可以是 null。</span><span class="sxs-lookup"><span data-stu-id="10c64-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="10c64-132">**Keys**</span><span class="sxs-lookup"><span data-stu-id="10c64-132">**Keys**</span></span>

|<span data-ttu-id="10c64-133">**欄**</span><span class="sxs-lookup"><span data-stu-id="10c64-133">**Column**</span></span>|<span data-ttu-id="10c64-134">**描述**</span><span class="sxs-lookup"><span data-stu-id="10c64-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="10c64-135">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="10c64-135">prinID</span></span>  <br/> |<span data-ttu-id="10c64-136">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="10c64-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="10c64-137">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="10c64-137">prinID</span></span>  <br/> |<span data-ttu-id="10c64-138">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="10c64-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

