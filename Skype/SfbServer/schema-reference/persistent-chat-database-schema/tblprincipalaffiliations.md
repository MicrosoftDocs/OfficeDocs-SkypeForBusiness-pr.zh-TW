---
title: tblPrincipalAffiliations
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
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations 包含主體隸屬關係，描述位置中的成員資格，包括 Active directory 網域服務安全性群組、Active Directory 容器中的網域。
ms.openlocfilehash: 149bb1b4603fa0f0e1909298659b881000464275
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815863"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="e150a-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="e150a-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="e150a-104">tblPrincipalAffiliations 包含主體隸屬關係，描述位置中的成員資格，包括 Active directory 網域服務安全性群組、Active Directory 容器中的網域。</span><span class="sxs-lookup"><span data-stu-id="e150a-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="e150a-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="e150a-105">**Columns**</span></span>

|<span data-ttu-id="e150a-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="e150a-106">**Column**</span></span>|<span data-ttu-id="e150a-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="e150a-107">**Type**</span></span>|<span data-ttu-id="e150a-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="e150a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e150a-109">principalID</span><span class="sxs-lookup"><span data-stu-id="e150a-109">principalID</span></span>  <br/> |<span data-ttu-id="e150a-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="e150a-110">int, not null</span></span>  <br/> |<span data-ttu-id="e150a-111">附屬主體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="e150a-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="e150a-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="e150a-112">affiliationID</span></span>  <br/> |<span data-ttu-id="e150a-113">int，非 null</span><span class="sxs-lookup"><span data-stu-id="e150a-113">int, not null</span></span>  <br/> |<span data-ttu-id="e150a-114">代表隸屬關係之主體的識別碼。</span><span class="sxs-lookup"><span data-stu-id="e150a-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="e150a-115">除了系統使用者類型) 之外，每個主體 (都具有自我從屬。</span><span class="sxs-lookup"><span data-stu-id="e150a-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="e150a-116">index</span><span class="sxs-lookup"><span data-stu-id="e150a-116">index</span></span>  <br/> |<span data-ttu-id="e150a-117">int，非 null</span><span class="sxs-lookup"><span data-stu-id="e150a-117">int, not null</span></span>  <br/> |<span data-ttu-id="e150a-118">指數。</span><span class="sxs-lookup"><span data-stu-id="e150a-118">Index.</span></span> <span data-ttu-id="e150a-119">「自身隸屬于-1」的值是-1，另一個隸屬關係會依序從每個桶中的1增加 \<principalID, affiliationId\> 。</span><span class="sxs-lookup"><span data-stu-id="e150a-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="e150a-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="e150a-120">updatedBy</span></span>  <br/> |<span data-ttu-id="e150a-121">int，非 null</span><span class="sxs-lookup"><span data-stu-id="e150a-121">int, not null</span></span>  <br/> |<span data-ttu-id="e150a-122">進行最新更新的主體。</span><span class="sxs-lookup"><span data-stu-id="e150a-122">Principal that did the latest update.</span></span> <span data-ttu-id="e150a-123">這通常是1，表示 Active Directory 同步處理。</span><span class="sxs-lookup"><span data-stu-id="e150a-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="e150a-124">**Keys**</span><span class="sxs-lookup"><span data-stu-id="e150a-124">**Keys**</span></span>

|<span data-ttu-id="e150a-125">**Columns**</span><span class="sxs-lookup"><span data-stu-id="e150a-125">**Columns**</span></span>|<span data-ttu-id="e150a-126">**描述**</span><span class="sxs-lookup"><span data-stu-id="e150a-126">**Description**</span></span>|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |<span data-ttu-id="e150a-127">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="e150a-127">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e150a-128">principalID</span><span class="sxs-lookup"><span data-stu-id="e150a-128">principalID</span></span>  <br/> |<span data-ttu-id="e150a-129">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="e150a-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="e150a-130">affiliationID</span><span class="sxs-lookup"><span data-stu-id="e150a-130">affiliationID</span></span>  <br/> |<span data-ttu-id="e150a-131">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="e150a-131">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

