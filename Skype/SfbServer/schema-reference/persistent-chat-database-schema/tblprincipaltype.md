---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType 包含主要類型來分類 tblPrincipal 資料表中的內容。
ms.openlocfilehash: 473b718a8a863432a71ff04d709bef4c0ac1327f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192713"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="f0d92-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="f0d92-103">tblPrincipalType</span></span>
 
<span data-ttu-id="f0d92-104">tblPrincipalType 包含主要類型來分類 tblPrincipal 資料表中的內容。</span><span class="sxs-lookup"><span data-stu-id="f0d92-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="f0d92-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="f0d92-105">**Columns**</span></span>

|<span data-ttu-id="f0d92-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="f0d92-106">**Column**</span></span>|<span data-ttu-id="f0d92-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="f0d92-107">**Type**</span></span>|<span data-ttu-id="f0d92-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="f0d92-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f0d92-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="f0d92-109">ptypeID</span></span>  <br/> |<span data-ttu-id="f0d92-110">Smallint, not null</span><span class="sxs-lookup"><span data-stu-id="f0d92-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="f0d92-111">主體類型 ID。</span><span class="sxs-lookup"><span data-stu-id="f0d92-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="f0d92-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="f0d92-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="f0d92-113">Nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="f0d92-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="f0d92-114">類型的描述。</span><span class="sxs-lookup"><span data-stu-id="f0d92-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="f0d92-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="f0d92-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="f0d92-116">bit、not null</span><span class="sxs-lookup"><span data-stu-id="f0d92-116">bit, not null</span></span>  <br/> |<span data-ttu-id="f0d92-117">如果該類型對應到用於內部用途的主體, 則為 True。</span><span class="sxs-lookup"><span data-stu-id="f0d92-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="f0d92-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="f0d92-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="f0d92-119">bit、not null</span><span class="sxs-lookup"><span data-stu-id="f0d92-119">bit, not null</span></span>  <br/> |<span data-ttu-id="f0d92-120">如果該類型是使用者類型, 則為 True。</span><span class="sxs-lookup"><span data-stu-id="f0d92-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="f0d92-121">**快速鍵**</span><span class="sxs-lookup"><span data-stu-id="f0d92-121">**Key**</span></span>

|<span data-ttu-id="f0d92-122">**左欄**</span><span class="sxs-lookup"><span data-stu-id="f0d92-122">**Column**</span></span>|<span data-ttu-id="f0d92-123">**說明**</span><span class="sxs-lookup"><span data-stu-id="f0d92-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f0d92-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="f0d92-124">ptypeID</span></span>  <br/> |<span data-ttu-id="f0d92-125">主鍵。</span><span class="sxs-lookup"><span data-stu-id="f0d92-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="f0d92-126">**主要值**</span><span class="sxs-lookup"><span data-stu-id="f0d92-126">**Principal Values**</span></span>

|<span data-ttu-id="f0d92-127">**標識號**</span><span class="sxs-lookup"><span data-stu-id="f0d92-127">**ID**</span></span>|<span data-ttu-id="f0d92-128">**角色**</span><span class="sxs-lookup"><span data-stu-id="f0d92-128">**Role**</span></span>|<span data-ttu-id="f0d92-129">**說明**</span><span class="sxs-lookup"><span data-stu-id="f0d92-129">**Description**</span></span>|<span data-ttu-id="f0d92-130">**使用者名**</span><span class="sxs-lookup"><span data-stu-id="f0d92-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f0d92-131">sr-1</span><span class="sxs-lookup"><span data-stu-id="f0d92-131">1</span></span>  <br/> |<span data-ttu-id="f0d92-132">每</span><span class="sxs-lookup"><span data-stu-id="f0d92-132">Any</span></span>  <br/> |<span data-ttu-id="f0d92-133">沒有已知類型的一般原則。</span><span class="sxs-lookup"><span data-stu-id="f0d92-133">Generic principal with no known type.</span></span> <span data-ttu-id="f0d92-134">在 tblPrincipal 表格中未使用。</span><span class="sxs-lookup"><span data-stu-id="f0d92-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="f0d92-135">pplx-2</span><span class="sxs-lookup"><span data-stu-id="f0d92-135">2</span></span>  <br/> |<span data-ttu-id="f0d92-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="f0d92-136">AnyUser</span></span>  <br/> |<span data-ttu-id="f0d92-137">使用者類型的一般主體。</span><span class="sxs-lookup"><span data-stu-id="f0d92-137">Generic principal of user type.</span></span> <span data-ttu-id="f0d92-138">在 tblPrincipal 表格中未使用。</span><span class="sxs-lookup"><span data-stu-id="f0d92-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="f0d92-139">是的</span><span class="sxs-lookup"><span data-stu-id="f0d92-139">Yes</span></span>  <br/> |
|<span data-ttu-id="f0d92-140">3</span><span class="sxs-lookup"><span data-stu-id="f0d92-140">3</span></span>  <br/> |<span data-ttu-id="f0d92-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="f0d92-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="f0d92-142">含有群組語義的一般主體。</span><span class="sxs-lookup"><span data-stu-id="f0d92-142">Generic principal with group semantic.</span></span> <span data-ttu-id="f0d92-143">在 tblPrincipal 表格中未使用。</span><span class="sxs-lookup"><span data-stu-id="f0d92-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="f0d92-144">4</span><span class="sxs-lookup"><span data-stu-id="f0d92-144">4</span></span>  <br/> |<span data-ttu-id="f0d92-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="f0d92-145">SystemUser</span></span>  <br/> |<span data-ttu-id="f0d92-146">永久聊天伺服器在內部使用的主要原則。</span><span class="sxs-lookup"><span data-stu-id="f0d92-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="f0d92-147">500</span><span class="sxs-lookup"><span data-stu-id="f0d92-147">5</span></span>  <br/> |<span data-ttu-id="f0d92-148">使用者名</span><span class="sxs-lookup"><span data-stu-id="f0d92-148">User</span></span>  <br/> |<span data-ttu-id="f0d92-149">一般使用者。</span><span class="sxs-lookup"><span data-stu-id="f0d92-149">Regular user.</span></span>  <br/> |<span data-ttu-id="f0d92-150">是的</span><span class="sxs-lookup"><span data-stu-id="f0d92-150">Yes</span></span>  <br/> |
|<span data-ttu-id="f0d92-151">型</span><span class="sxs-lookup"><span data-stu-id="f0d92-151">8</span></span>  <br/> |<span data-ttu-id="f0d92-152">DC</span><span class="sxs-lookup"><span data-stu-id="f0d92-152">DC</span></span>  <br/> |<span data-ttu-id="f0d92-153">Active Directory 網域服務網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="f0d92-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="f0d92-154">9</span><span class="sxs-lookup"><span data-stu-id="f0d92-154">9</span></span>  <br/> |<span data-ttu-id="f0d92-155">群組</span><span class="sxs-lookup"><span data-stu-id="f0d92-155">Group</span></span>  <br/> |<span data-ttu-id="f0d92-156">Active Directory 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="f0d92-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="f0d92-157">第</span><span class="sxs-lookup"><span data-stu-id="f0d92-157">10</span></span>  <br/> |<span data-ttu-id="f0d92-158">資料夾</span><span class="sxs-lookup"><span data-stu-id="f0d92-158">Folder</span></span>  <br/> |<span data-ttu-id="f0d92-159">Active Directory 容器或組織單位。</span><span class="sxs-lookup"><span data-stu-id="f0d92-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="f0d92-160">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f0d92-160">See also</span></span>

[<span data-ttu-id="f0d92-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="f0d92-161">tblPrincipal</span></span>](tblprincipal.md)
