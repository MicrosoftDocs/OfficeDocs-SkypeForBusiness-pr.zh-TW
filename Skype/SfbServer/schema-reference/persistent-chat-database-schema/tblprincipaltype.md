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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType 包含主要類型來分類 tblPrincipal 資料表中的內容。
ms.openlocfilehash: 1aacfdf34689bebc2c7e012c926731ae1f4a8349
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812931"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="b94bb-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="b94bb-103">tblPrincipalType</span></span>
 
<span data-ttu-id="b94bb-104">tblPrincipalType 包含主要類型來分類 tblPrincipal 資料表中的內容。</span><span class="sxs-lookup"><span data-stu-id="b94bb-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="b94bb-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="b94bb-105">**Columns**</span></span>

|<span data-ttu-id="b94bb-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="b94bb-106">**Column**</span></span>|<span data-ttu-id="b94bb-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="b94bb-107">**Type**</span></span>|<span data-ttu-id="b94bb-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="b94bb-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b94bb-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="b94bb-109">ptypeID</span></span>  <br/> |<span data-ttu-id="b94bb-110">Smallint，not null</span><span class="sxs-lookup"><span data-stu-id="b94bb-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="b94bb-111">主體類型 ID。</span><span class="sxs-lookup"><span data-stu-id="b94bb-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="b94bb-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="b94bb-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="b94bb-113">Nvarchar （256），not null</span><span class="sxs-lookup"><span data-stu-id="b94bb-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="b94bb-114">類型的描述。</span><span class="sxs-lookup"><span data-stu-id="b94bb-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="b94bb-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="b94bb-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="b94bb-116">bit、not null</span><span class="sxs-lookup"><span data-stu-id="b94bb-116">bit, not null</span></span>  <br/> |<span data-ttu-id="b94bb-117">如果該類型對應到用於內部用途的主體，則為 True。</span><span class="sxs-lookup"><span data-stu-id="b94bb-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="b94bb-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="b94bb-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="b94bb-119">bit、not null</span><span class="sxs-lookup"><span data-stu-id="b94bb-119">bit, not null</span></span>  <br/> |<span data-ttu-id="b94bb-120">如果該類型是使用者類型，則為 True。</span><span class="sxs-lookup"><span data-stu-id="b94bb-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="b94bb-121">**機碼**</span><span class="sxs-lookup"><span data-stu-id="b94bb-121">**Key**</span></span>

|<span data-ttu-id="b94bb-122">**左欄**</span><span class="sxs-lookup"><span data-stu-id="b94bb-122">**Column**</span></span>|<span data-ttu-id="b94bb-123">**說明**</span><span class="sxs-lookup"><span data-stu-id="b94bb-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b94bb-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="b94bb-124">ptypeID</span></span>  <br/> |<span data-ttu-id="b94bb-125">主鍵。</span><span class="sxs-lookup"><span data-stu-id="b94bb-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="b94bb-126">**主要值**</span><span class="sxs-lookup"><span data-stu-id="b94bb-126">**Principal Values**</span></span>

|<span data-ttu-id="b94bb-127">**標識號**</span><span class="sxs-lookup"><span data-stu-id="b94bb-127">**ID**</span></span>|<span data-ttu-id="b94bb-128">**角色**</span><span class="sxs-lookup"><span data-stu-id="b94bb-128">**Role**</span></span>|<span data-ttu-id="b94bb-129">**說明**</span><span class="sxs-lookup"><span data-stu-id="b94bb-129">**Description**</span></span>|<span data-ttu-id="b94bb-130">**使用者**</span><span class="sxs-lookup"><span data-stu-id="b94bb-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b94bb-131">1</span><span class="sxs-lookup"><span data-stu-id="b94bb-131">1</span></span>  <br/> |<span data-ttu-id="b94bb-132">每</span><span class="sxs-lookup"><span data-stu-id="b94bb-132">Any</span></span>  <br/> |<span data-ttu-id="b94bb-133">沒有已知類型的一般原則。</span><span class="sxs-lookup"><span data-stu-id="b94bb-133">Generic principal with no known type.</span></span> <span data-ttu-id="b94bb-134">在 tblPrincipal 表格中未使用。</span><span class="sxs-lookup"><span data-stu-id="b94bb-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="b94bb-135">2</span><span class="sxs-lookup"><span data-stu-id="b94bb-135">2</span></span>  <br/> |<span data-ttu-id="b94bb-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="b94bb-136">AnyUser</span></span>  <br/> |<span data-ttu-id="b94bb-137">使用者類型的一般主體。</span><span class="sxs-lookup"><span data-stu-id="b94bb-137">Generic principal of user type.</span></span> <span data-ttu-id="b94bb-138">在 tblPrincipal 表格中未使用。</span><span class="sxs-lookup"><span data-stu-id="b94bb-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="b94bb-139">是</span><span class="sxs-lookup"><span data-stu-id="b94bb-139">Yes</span></span>  <br/> |
|<span data-ttu-id="b94bb-140">3</span><span class="sxs-lookup"><span data-stu-id="b94bb-140">3</span></span>  <br/> |<span data-ttu-id="b94bb-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="b94bb-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="b94bb-142">含有群組語義的一般主體。</span><span class="sxs-lookup"><span data-stu-id="b94bb-142">Generic principal with group semantic.</span></span> <span data-ttu-id="b94bb-143">在 tblPrincipal 表格中未使用。</span><span class="sxs-lookup"><span data-stu-id="b94bb-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="b94bb-144">4</span><span class="sxs-lookup"><span data-stu-id="b94bb-144">4</span></span>  <br/> |<span data-ttu-id="b94bb-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="b94bb-145">SystemUser</span></span>  <br/> |<span data-ttu-id="b94bb-146">永久聊天伺服器在內部使用的主要原則。</span><span class="sxs-lookup"><span data-stu-id="b94bb-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="b94bb-147">500</span><span class="sxs-lookup"><span data-stu-id="b94bb-147">5</span></span>  <br/> |<span data-ttu-id="b94bb-148">使用者</span><span class="sxs-lookup"><span data-stu-id="b94bb-148">User</span></span>  <br/> |<span data-ttu-id="b94bb-149">一般使用者。</span><span class="sxs-lookup"><span data-stu-id="b94bb-149">Regular user.</span></span>  <br/> |<span data-ttu-id="b94bb-150">是</span><span class="sxs-lookup"><span data-stu-id="b94bb-150">Yes</span></span>  <br/> |
|<span data-ttu-id="b94bb-151">型</span><span class="sxs-lookup"><span data-stu-id="b94bb-151">8</span></span>  <br/> |<span data-ttu-id="b94bb-152">DC</span><span class="sxs-lookup"><span data-stu-id="b94bb-152">DC</span></span>  <br/> |<span data-ttu-id="b94bb-153">Active Directory 網域服務網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="b94bb-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="b94bb-154">9</span><span class="sxs-lookup"><span data-stu-id="b94bb-154">9</span></span>  <br/> |<span data-ttu-id="b94bb-155">群組</span><span class="sxs-lookup"><span data-stu-id="b94bb-155">Group</span></span>  <br/> |<span data-ttu-id="b94bb-156">Active Directory 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="b94bb-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="b94bb-157">第</span><span class="sxs-lookup"><span data-stu-id="b94bb-157">10</span></span>  <br/> |<span data-ttu-id="b94bb-158">資料夾</span><span class="sxs-lookup"><span data-stu-id="b94bb-158">Folder</span></span>  <br/> |<span data-ttu-id="b94bb-159">Active Directory 容器或組織單位。</span><span class="sxs-lookup"><span data-stu-id="b94bb-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="b94bb-160">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b94bb-160">See also</span></span>

[<span data-ttu-id="b94bb-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="b94bb-161">tblPrincipal</span></span>](tblprincipal.md)
