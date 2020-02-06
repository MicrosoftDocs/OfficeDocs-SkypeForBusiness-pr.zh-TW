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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations 包含描述位置中的成員資格的主要隸屬關係，包括 Active directory 網域服務安全性群組（在 Active Directory 容器中，在網域中）。
ms.openlocfilehash: 542bcc333d815b0577aec1fb11d4070540150d3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814471"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="32dbf-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="32dbf-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="32dbf-104">tblPrincipalAffiliations 包含描述位置中的成員資格的主要隸屬關係，包括 Active directory 網域服務安全性群組（在 Active Directory 容器中，在網域中）。</span><span class="sxs-lookup"><span data-stu-id="32dbf-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="32dbf-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="32dbf-105">**Columns**</span></span>

|<span data-ttu-id="32dbf-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="32dbf-106">**Column**</span></span>|<span data-ttu-id="32dbf-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="32dbf-107">**Type**</span></span>|<span data-ttu-id="32dbf-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="32dbf-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="32dbf-109">principalID</span><span class="sxs-lookup"><span data-stu-id="32dbf-109">principalID</span></span>  <br/> |<span data-ttu-id="32dbf-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="32dbf-110">int, not null</span></span>  <br/> |<span data-ttu-id="32dbf-111">附屬原則的 ID。</span><span class="sxs-lookup"><span data-stu-id="32dbf-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="32dbf-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="32dbf-112">affiliationID</span></span>  <br/> |<span data-ttu-id="32dbf-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="32dbf-113">int, not null</span></span>  <br/> |<span data-ttu-id="32dbf-114">代表隸屬關係的承擔者 ID。</span><span class="sxs-lookup"><span data-stu-id="32dbf-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="32dbf-115">每個主體（除系統使用者類型之外）都有自我隸屬關係。</span><span class="sxs-lookup"><span data-stu-id="32dbf-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="32dbf-116">index</span><span class="sxs-lookup"><span data-stu-id="32dbf-116">index</span></span>  <br/> |<span data-ttu-id="32dbf-117">int，not null</span><span class="sxs-lookup"><span data-stu-id="32dbf-117">int, not null</span></span>  <br/> |<span data-ttu-id="32dbf-118">Index.</span><span class="sxs-lookup"><span data-stu-id="32dbf-118">Index.</span></span> <span data-ttu-id="32dbf-119">自我隸屬關係的值是-1，而其他隸屬關係則會依序從每個\<PrincipalID、affiliationId\> bucket 中的1增加。</span><span class="sxs-lookup"><span data-stu-id="32dbf-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="32dbf-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="32dbf-120">updatedBy</span></span>  <br/> |<span data-ttu-id="32dbf-121">int，not null</span><span class="sxs-lookup"><span data-stu-id="32dbf-121">int, not null</span></span>  <br/> |<span data-ttu-id="32dbf-122">已進行最新更新的主體。</span><span class="sxs-lookup"><span data-stu-id="32dbf-122">Principal that did the latest update.</span></span> <span data-ttu-id="32dbf-123">這通常是1，這表示 Active Directory 同步處理。</span><span class="sxs-lookup"><span data-stu-id="32dbf-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="32dbf-124">**鍵**</span><span class="sxs-lookup"><span data-stu-id="32dbf-124">**Keys**</span></span>

|<span data-ttu-id="32dbf-125">**分欄**</span><span class="sxs-lookup"><span data-stu-id="32dbf-125">**Columns**</span></span>|<span data-ttu-id="32dbf-126">**說明**</span><span class="sxs-lookup"><span data-stu-id="32dbf-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="32dbf-127">\<principalID、index、affiliationID\></span><span class="sxs-lookup"><span data-stu-id="32dbf-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="32dbf-128">主鍵。</span><span class="sxs-lookup"><span data-stu-id="32dbf-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="32dbf-129">principalID</span><span class="sxs-lookup"><span data-stu-id="32dbf-129">principalID</span></span>  <br/> |<span data-ttu-id="32dbf-130">在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="32dbf-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="32dbf-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="32dbf-131">affiliationID</span></span>  <br/> |<span data-ttu-id="32dbf-132">在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="32dbf-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

