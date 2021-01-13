---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal 包含指派給節點的範圍。
ms.openlocfilehash: efda792ab6f6c6cc7b188a9dffdaa7c324b24797
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831513"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="d8f82-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="d8f82-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="d8f82-104">tblScopePrincipal 包含指派給節點的範圍。</span><span class="sxs-lookup"><span data-stu-id="d8f82-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="d8f82-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="d8f82-105">**Columns**</span></span>

|<span data-ttu-id="d8f82-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="d8f82-106">**Column**</span></span>|<span data-ttu-id="d8f82-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="d8f82-107">**Type**</span></span>|<span data-ttu-id="d8f82-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="d8f82-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d8f82-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="d8f82-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="d8f82-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="d8f82-110">int, not null</span></span>  <br/> |<span data-ttu-id="d8f82-111">套用範圍的節點識別碼。</span><span class="sxs-lookup"><span data-stu-id="d8f82-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="d8f82-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="d8f82-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="d8f82-113">int，非 null</span><span class="sxs-lookup"><span data-stu-id="d8f82-113">int, not null</span></span>  <br/> |<span data-ttu-id="d8f82-114">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="d8f82-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="d8f82-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="d8f82-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="d8f82-116">位元，非 null</span><span class="sxs-lookup"><span data-stu-id="d8f82-116">bit, not null</span></span>  <br/> |<span data-ttu-id="d8f82-117">True 是表示如果範圍的類型是 Deny;False 表示允許。</span><span class="sxs-lookup"><span data-stu-id="d8f82-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="d8f82-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="d8f82-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="d8f82-119">int，非 null</span><span class="sxs-lookup"><span data-stu-id="d8f82-119">int, not null</span></span>  <br/> |<span data-ttu-id="d8f82-120">最後更新此專案的主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="d8f82-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="d8f82-121">**Keys**</span><span class="sxs-lookup"><span data-stu-id="d8f82-121">**Keys**</span></span>

|<span data-ttu-id="d8f82-122">**欄**</span><span class="sxs-lookup"><span data-stu-id="d8f82-122">**Column**</span></span>|<span data-ttu-id="d8f82-123">**描述**</span><span class="sxs-lookup"><span data-stu-id="d8f82-123">**Description**</span></span>|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |<span data-ttu-id="d8f82-124">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="d8f82-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="d8f82-125">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="d8f82-125">scopeNodeID</span></span>  <br/> |<span data-ttu-id="d8f82-126">在 tblNode.nodeID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="d8f82-126">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="d8f82-127">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="d8f82-127">scopePrinID</span></span>  <br/> |<span data-ttu-id="d8f82-128">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="d8f82-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

