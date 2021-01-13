---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole 包含指派給節點的明確角色。
ms.openlocfilehash: 13c9c25db9ba1dbe281947468bbd834e80417899
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831553"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="f59c8-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="f59c8-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="f59c8-104">tblPrincipalRole 包含指派給節點的明確角色。</span><span class="sxs-lookup"><span data-stu-id="f59c8-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="f59c8-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="f59c8-105">**Columns**</span></span>

|<span data-ttu-id="f59c8-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="f59c8-106">**Column**</span></span>|<span data-ttu-id="f59c8-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="f59c8-107">**Type**</span></span>|<span data-ttu-id="f59c8-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="f59c8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f59c8-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="f59c8-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="f59c8-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="f59c8-110">int, not null</span></span>  <br/> |<span data-ttu-id="f59c8-111">套用角色的節點識別碼。</span><span class="sxs-lookup"><span data-stu-id="f59c8-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="f59c8-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="f59c8-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="f59c8-113">int，非 null</span><span class="sxs-lookup"><span data-stu-id="f59c8-113">int, not null</span></span>  <br/> |<span data-ttu-id="f59c8-114">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="f59c8-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="f59c8-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="f59c8-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="f59c8-116">int，非 null</span><span class="sxs-lookup"><span data-stu-id="f59c8-116">int, not null</span></span>  <br/> |<span data-ttu-id="f59c8-117">TblRoleType) 的角色類型識別碼 (。</span><span class="sxs-lookup"><span data-stu-id="f59c8-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="f59c8-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="f59c8-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="f59c8-119">int，非 null</span><span class="sxs-lookup"><span data-stu-id="f59c8-119">int, not null</span></span>  <br/> |<span data-ttu-id="f59c8-120">最後更新此專案的主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="f59c8-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="f59c8-121">**Keys**</span><span class="sxs-lookup"><span data-stu-id="f59c8-121">**Keys**</span></span>

|<span data-ttu-id="f59c8-122">**欄**</span><span class="sxs-lookup"><span data-stu-id="f59c8-122">**Column**</span></span>|<span data-ttu-id="f59c8-123">**描述**</span><span class="sxs-lookup"><span data-stu-id="f59c8-123">**Description**</span></span>|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |<span data-ttu-id="f59c8-124">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="f59c8-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f59c8-125">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="f59c8-125">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="f59c8-126">在 tblNode.nodeID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="f59c8-126">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="f59c8-127">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="f59c8-127">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="f59c8-128">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="f59c8-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="f59c8-129">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="f59c8-129">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="f59c8-130">在 tblRoleType.rtypeID 表格中查閱的外鍵。</span><span class="sxs-lookup"><span data-stu-id="f59c8-130">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

