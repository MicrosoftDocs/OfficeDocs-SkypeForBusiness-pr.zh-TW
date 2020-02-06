---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal 包含指派給節點的作用中。
ms.openlocfilehash: 24a38ef4acf3e0d500c7652f5ca418af585343b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812441"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="a6e7d-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="a6e7d-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="a6e7d-104">tblScopePrincipal 包含指派給節點的作用中。</span><span class="sxs-lookup"><span data-stu-id="a6e7d-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="a6e7d-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="a6e7d-105">**Columns**</span></span>

|<span data-ttu-id="a6e7d-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="a6e7d-106">**Column**</span></span>|<span data-ttu-id="a6e7d-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="a6e7d-107">**Type**</span></span>|<span data-ttu-id="a6e7d-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="a6e7d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a6e7d-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="a6e7d-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="a6e7d-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="a6e7d-110">int, not null</span></span>  <br/> |<span data-ttu-id="a6e7d-111">作用中所適用的節點識別碼。</span><span class="sxs-lookup"><span data-stu-id="a6e7d-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="a6e7d-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="a6e7d-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="a6e7d-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="a6e7d-113">int, not null</span></span>  <br/> |<span data-ttu-id="a6e7d-114">Principal ID。</span><span class="sxs-lookup"><span data-stu-id="a6e7d-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="a6e7d-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="a6e7d-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="a6e7d-116">bit、not null</span><span class="sxs-lookup"><span data-stu-id="a6e7d-116">bit, not null</span></span>  <br/> |<span data-ttu-id="a6e7d-117">如果範圍類型為 Deny，則為 True;如果允許，則為 False。</span><span class="sxs-lookup"><span data-stu-id="a6e7d-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="a6e7d-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="a6e7d-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="a6e7d-119">int，not null</span><span class="sxs-lookup"><span data-stu-id="a6e7d-119">int, not null</span></span>  <br/> |<span data-ttu-id="a6e7d-120">上次更新此專案的主體 ID。</span><span class="sxs-lookup"><span data-stu-id="a6e7d-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="a6e7d-121">**鍵**</span><span class="sxs-lookup"><span data-stu-id="a6e7d-121">**Keys**</span></span>

|<span data-ttu-id="a6e7d-122">**左欄**</span><span class="sxs-lookup"><span data-stu-id="a6e7d-122">**Column**</span></span>|<span data-ttu-id="a6e7d-123">**說明**</span><span class="sxs-lookup"><span data-stu-id="a6e7d-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a6e7d-124">\<scopeNodeID, scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="a6e7d-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="a6e7d-125">主鍵。</span><span class="sxs-lookup"><span data-stu-id="a6e7d-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="a6e7d-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="a6e7d-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="a6e7d-127">在 tblNode 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="a6e7d-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="a6e7d-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="a6e7d-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="a6e7d-129">在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="a6e7d-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

