---
title: tblPrincipalType
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
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType 含有主要類型以分類 tblPrincipal 表格中的項目。
ms.openlocfilehash: 110818db0fb3c742491adfeed23362a2bcbebab2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831533"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="b53f7-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="b53f7-103">tblPrincipalType</span></span>
 
<span data-ttu-id="b53f7-104">tblPrincipalType 含有主要類型以分類 tblPrincipal 表格中的項目。</span><span class="sxs-lookup"><span data-stu-id="b53f7-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="b53f7-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="b53f7-105">**Columns**</span></span>

|<span data-ttu-id="b53f7-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="b53f7-106">**Column**</span></span>|<span data-ttu-id="b53f7-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="b53f7-107">**Type**</span></span>|<span data-ttu-id="b53f7-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="b53f7-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b53f7-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="b53f7-109">ptypeID</span></span>  <br/> |<span data-ttu-id="b53f7-110">smallint，非 null</span><span class="sxs-lookup"><span data-stu-id="b53f7-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="b53f7-111">主體類型識別碼。</span><span class="sxs-lookup"><span data-stu-id="b53f7-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="b53f7-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="b53f7-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="b53f7-113">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="b53f7-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="b53f7-114">類型的描述。</span><span class="sxs-lookup"><span data-stu-id="b53f7-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="b53f7-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="b53f7-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="b53f7-116">bit，非 null</span><span class="sxs-lookup"><span data-stu-id="b53f7-116">bit, not null</span></span>  <br/> |<span data-ttu-id="b53f7-117">如果類型對應至作為內部用途的主體，則為 True。</span><span class="sxs-lookup"><span data-stu-id="b53f7-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="b53f7-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="b53f7-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="b53f7-119">bit，非 null</span><span class="sxs-lookup"><span data-stu-id="b53f7-119">bit, not null</span></span>  <br/> |<span data-ttu-id="b53f7-120">如果類型為使用者類型，則為 True。</span><span class="sxs-lookup"><span data-stu-id="b53f7-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="b53f7-121">**Key**</span><span class="sxs-lookup"><span data-stu-id="b53f7-121">**Key**</span></span>

|<span data-ttu-id="b53f7-122">**欄**</span><span class="sxs-lookup"><span data-stu-id="b53f7-122">**Column**</span></span>|<span data-ttu-id="b53f7-123">**描述**</span><span class="sxs-lookup"><span data-stu-id="b53f7-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b53f7-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="b53f7-124">ptypeID</span></span>  <br/> |<span data-ttu-id="b53f7-125">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="b53f7-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="b53f7-126">**主體值**</span><span class="sxs-lookup"><span data-stu-id="b53f7-126">**Principal Values**</span></span>

|<span data-ttu-id="b53f7-127">**識別碼**</span><span class="sxs-lookup"><span data-stu-id="b53f7-127">**ID**</span></span>|<span data-ttu-id="b53f7-128">**Role**</span><span class="sxs-lookup"><span data-stu-id="b53f7-128">**Role**</span></span>|<span data-ttu-id="b53f7-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="b53f7-129">**Description**</span></span>|<span data-ttu-id="b53f7-130">**使用者**</span><span class="sxs-lookup"><span data-stu-id="b53f7-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b53f7-131">1 </span><span class="sxs-lookup"><span data-stu-id="b53f7-131">1</span></span>  <br/> |<span data-ttu-id="b53f7-132">任何</span><span class="sxs-lookup"><span data-stu-id="b53f7-132">Any</span></span>  <br/> |<span data-ttu-id="b53f7-p101">不含已知類型的一般主體。不使用在 tblPrincipal 表格中。</span><span class="sxs-lookup"><span data-stu-id="b53f7-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="b53f7-135">2 </span><span class="sxs-lookup"><span data-stu-id="b53f7-135">2</span></span>  <br/> |<span data-ttu-id="b53f7-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="b53f7-136">AnyUser</span></span>  <br/> |<span data-ttu-id="b53f7-p102">使用者類型的一般主體。不使用在 tblPrincipal 表格中。</span><span class="sxs-lookup"><span data-stu-id="b53f7-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="b53f7-139">是</span><span class="sxs-lookup"><span data-stu-id="b53f7-139">Yes</span></span>  <br/> |
|<span data-ttu-id="b53f7-140">3 </span><span class="sxs-lookup"><span data-stu-id="b53f7-140">3</span></span>  <br/> |<span data-ttu-id="b53f7-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="b53f7-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="b53f7-p103">含群組語意的一般主體。不使用在 tblPrincipal 表格中。</span><span class="sxs-lookup"><span data-stu-id="b53f7-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="b53f7-144">4 </span><span class="sxs-lookup"><span data-stu-id="b53f7-144">4</span></span>  <br/> |<span data-ttu-id="b53f7-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="b53f7-145">SystemUser</span></span>  <br/> |<span data-ttu-id="b53f7-146">Persistent Chat Server 內部使用的主體。</span><span class="sxs-lookup"><span data-stu-id="b53f7-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="b53f7-147">5 </span><span class="sxs-lookup"><span data-stu-id="b53f7-147">5</span></span>  <br/> |<span data-ttu-id="b53f7-148">使用者</span><span class="sxs-lookup"><span data-stu-id="b53f7-148">User</span></span>  <br/> |<span data-ttu-id="b53f7-149">一般使用者。</span><span class="sxs-lookup"><span data-stu-id="b53f7-149">Regular user.</span></span>  <br/> |<span data-ttu-id="b53f7-150">是</span><span class="sxs-lookup"><span data-stu-id="b53f7-150">Yes</span></span>  <br/> |
|<span data-ttu-id="b53f7-151">8 </span><span class="sxs-lookup"><span data-stu-id="b53f7-151">8</span></span>  <br/> |<span data-ttu-id="b53f7-152">直流</span><span class="sxs-lookup"><span data-stu-id="b53f7-152">DC</span></span>  <br/> |<span data-ttu-id="b53f7-153">Active Directory 網域服務網域控制站。</span><span class="sxs-lookup"><span data-stu-id="b53f7-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="b53f7-154">9 </span><span class="sxs-lookup"><span data-stu-id="b53f7-154">9</span></span>  <br/> |<span data-ttu-id="b53f7-155">群組</span><span class="sxs-lookup"><span data-stu-id="b53f7-155">Group</span></span>  <br/> |<span data-ttu-id="b53f7-156">Active Directory 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="b53f7-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="b53f7-157">10 </span><span class="sxs-lookup"><span data-stu-id="b53f7-157">10</span></span>  <br/> |<span data-ttu-id="b53f7-158">資料夾</span><span class="sxs-lookup"><span data-stu-id="b53f7-158">Folder</span></span>  <br/> |<span data-ttu-id="b53f7-159">Active Directory 容器或組織單位。</span><span class="sxs-lookup"><span data-stu-id="b53f7-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="b53f7-160">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b53f7-160">See also</span></span>

[<span data-ttu-id="b53f7-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="b53f7-161">tblPrincipal</span></span>](tblprincipal.md)
