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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole 包含指派給節點的明確角色。
ms.openlocfilehash: 1cc606ec3825bb664d4123154e97fabb15678cfd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813361"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="a2780-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="a2780-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="a2780-104">tblPrincipalRole 包含指派給節點的明確角色。</span><span class="sxs-lookup"><span data-stu-id="a2780-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="a2780-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="a2780-105">**Columns**</span></span>

|<span data-ttu-id="a2780-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="a2780-106">**Column**</span></span>|<span data-ttu-id="a2780-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="a2780-107">**Type**</span></span>|<span data-ttu-id="a2780-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="a2780-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a2780-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="a2780-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="a2780-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="a2780-110">int, not null</span></span>  <br/> |<span data-ttu-id="a2780-111">角色所套用的節點識別碼。</span><span class="sxs-lookup"><span data-stu-id="a2780-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="a2780-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="a2780-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="a2780-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="a2780-113">int, not null</span></span>  <br/> |<span data-ttu-id="a2780-114">Principal ID。</span><span class="sxs-lookup"><span data-stu-id="a2780-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="a2780-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="a2780-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="a2780-116">int，not null</span><span class="sxs-lookup"><span data-stu-id="a2780-116">int, not null</span></span>  <br/> |<span data-ttu-id="a2780-117">角色類型識別碼（從 tblRoleType）。</span><span class="sxs-lookup"><span data-stu-id="a2780-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="a2780-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="a2780-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="a2780-119">int，not null</span><span class="sxs-lookup"><span data-stu-id="a2780-119">int, not null</span></span>  <br/> |<span data-ttu-id="a2780-120">上次更新此專案的主體 ID。</span><span class="sxs-lookup"><span data-stu-id="a2780-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="a2780-121">**鍵**</span><span class="sxs-lookup"><span data-stu-id="a2780-121">**Keys**</span></span>

|<span data-ttu-id="a2780-122">**左欄**</span><span class="sxs-lookup"><span data-stu-id="a2780-122">**Column**</span></span>|<span data-ttu-id="a2780-123">**說明**</span><span class="sxs-lookup"><span data-stu-id="a2780-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a2780-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="a2780-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="a2780-125">主鍵。</span><span class="sxs-lookup"><span data-stu-id="a2780-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="a2780-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="a2780-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="a2780-127">在 tblNode 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="a2780-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="a2780-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="a2780-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="a2780-129">在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="a2780-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="a2780-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="a2780-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="a2780-131">在 tblRoleType rtypeID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="a2780-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

