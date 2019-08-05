---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations 包含描述位置中的成員資格的主要隸屬關係, 包括 Active directory 網域服務安全性群組 (在 Active Directory 容器中, 在網域中)。
ms.openlocfilehash: cda9827f4a4ab7e17a156cc867e4925c88d06ff3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192724"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="e8f7a-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="e8f7a-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="e8f7a-104">tblPrincipalAffiliations 包含描述位置中的成員資格的主要隸屬關係, 包括 Active directory 網域服務安全性群組 (在 Active Directory 容器中, 在網域中)。</span><span class="sxs-lookup"><span data-stu-id="e8f7a-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="e8f7a-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="e8f7a-105">**Columns**</span></span>

|<span data-ttu-id="e8f7a-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="e8f7a-106">**Column**</span></span>|<span data-ttu-id="e8f7a-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="e8f7a-107">**Type**</span></span>|<span data-ttu-id="e8f7a-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="e8f7a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e8f7a-109">principalID</span><span class="sxs-lookup"><span data-stu-id="e8f7a-109">principalID</span></span>  <br/> |<span data-ttu-id="e8f7a-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="e8f7a-110">int, not null</span></span>  <br/> |<span data-ttu-id="e8f7a-111">附屬原則的 ID。</span><span class="sxs-lookup"><span data-stu-id="e8f7a-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="e8f7a-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="e8f7a-112">affiliationID</span></span>  <br/> |<span data-ttu-id="e8f7a-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="e8f7a-113">int, not null</span></span>  <br/> |<span data-ttu-id="e8f7a-114">代表隸屬關係的承擔者 ID。</span><span class="sxs-lookup"><span data-stu-id="e8f7a-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="e8f7a-115">每個主體 (除系統使用者類型之外) 都有自我隸屬關係。</span><span class="sxs-lookup"><span data-stu-id="e8f7a-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="e8f7a-116">index</span><span class="sxs-lookup"><span data-stu-id="e8f7a-116">index</span></span>  <br/> |<span data-ttu-id="e8f7a-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="e8f7a-117">int, not null</span></span>  <br/> |<span data-ttu-id="e8f7a-118">Index.</span><span class="sxs-lookup"><span data-stu-id="e8f7a-118">Index.</span></span> <span data-ttu-id="e8f7a-119">自我隸屬關係的值是-1, 而其他隸屬關係則會依序從每個\<PrincipalID、affiliationId\> bucket 中的1增加。</span><span class="sxs-lookup"><span data-stu-id="e8f7a-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="e8f7a-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="e8f7a-120">updatedBy</span></span>  <br/> |<span data-ttu-id="e8f7a-121">int, not null</span><span class="sxs-lookup"><span data-stu-id="e8f7a-121">int, not null</span></span>  <br/> |<span data-ttu-id="e8f7a-122">已進行最新更新的主體。</span><span class="sxs-lookup"><span data-stu-id="e8f7a-122">Principal that did the latest update.</span></span> <span data-ttu-id="e8f7a-123">這通常是 1, 這表示 Active Directory 同步處理。</span><span class="sxs-lookup"><span data-stu-id="e8f7a-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="e8f7a-124">**鍵**</span><span class="sxs-lookup"><span data-stu-id="e8f7a-124">**Keys**</span></span>

|<span data-ttu-id="e8f7a-125">**分欄**</span><span class="sxs-lookup"><span data-stu-id="e8f7a-125">**Columns**</span></span>|<span data-ttu-id="e8f7a-126">**說明**</span><span class="sxs-lookup"><span data-stu-id="e8f7a-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e8f7a-127">\<principalID、index、affiliationID\></span><span class="sxs-lookup"><span data-stu-id="e8f7a-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="e8f7a-128">主鍵。</span><span class="sxs-lookup"><span data-stu-id="e8f7a-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e8f7a-129">principalID</span><span class="sxs-lookup"><span data-stu-id="e8f7a-129">principalID</span></span>  <br/> |<span data-ttu-id="e8f7a-130">在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="e8f7a-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="e8f7a-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="e8f7a-131">affiliationID</span></span>  <br/> |<span data-ttu-id="e8f7a-132">在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="e8f7a-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

