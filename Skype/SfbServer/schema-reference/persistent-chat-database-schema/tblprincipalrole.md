---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole 包含指派給節點的明確角色。
ms.openlocfilehash: 9675713afba5753378f4d01b70489d0eee93b8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192715"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="1e01e-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="1e01e-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="1e01e-104">tblPrincipalRole 包含指派給節點的明確角色。</span><span class="sxs-lookup"><span data-stu-id="1e01e-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="1e01e-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="1e01e-105">**Columns**</span></span>

|<span data-ttu-id="1e01e-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="1e01e-106">**Column**</span></span>|<span data-ttu-id="1e01e-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="1e01e-107">**Type**</span></span>|<span data-ttu-id="1e01e-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="1e01e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1e01e-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="1e01e-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="1e01e-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="1e01e-110">int, not null</span></span>  <br/> |<span data-ttu-id="1e01e-111">角色所套用的節點識別碼。</span><span class="sxs-lookup"><span data-stu-id="1e01e-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="1e01e-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="1e01e-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="1e01e-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="1e01e-113">int, not null</span></span>  <br/> |<span data-ttu-id="1e01e-114">Principal ID。</span><span class="sxs-lookup"><span data-stu-id="1e01e-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="1e01e-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="1e01e-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="1e01e-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="1e01e-116">int, not null</span></span>  <br/> |<span data-ttu-id="1e01e-117">角色類型識別碼 (從 tblRoleType)。</span><span class="sxs-lookup"><span data-stu-id="1e01e-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="1e01e-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="1e01e-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="1e01e-119">int, not null</span><span class="sxs-lookup"><span data-stu-id="1e01e-119">int, not null</span></span>  <br/> |<span data-ttu-id="1e01e-120">上次更新此專案的主體 ID。</span><span class="sxs-lookup"><span data-stu-id="1e01e-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="1e01e-121">**鍵**</span><span class="sxs-lookup"><span data-stu-id="1e01e-121">**Keys**</span></span>

|<span data-ttu-id="1e01e-122">**左欄**</span><span class="sxs-lookup"><span data-stu-id="1e01e-122">**Column**</span></span>|<span data-ttu-id="1e01e-123">**說明**</span><span class="sxs-lookup"><span data-stu-id="1e01e-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1e01e-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="1e01e-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="1e01e-125">主鍵。</span><span class="sxs-lookup"><span data-stu-id="1e01e-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="1e01e-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="1e01e-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="1e01e-127">在 tblNode 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="1e01e-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="1e01e-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="1e01e-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="1e01e-129">在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="1e01e-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="1e01e-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="1e01e-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="1e01e-131">在 tblRoleType rtypeID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="1e01e-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

