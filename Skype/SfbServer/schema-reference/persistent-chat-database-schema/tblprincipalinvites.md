---
title: tblPrincipalInvites
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites 包含所有擁有自動邀請之節點之已預配使用者的邀請。
ms.openlocfilehash: dfa41ec5715c7c5255b26fcdb32561e74c4f08df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814181"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="9a1ac-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="9a1ac-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="9a1ac-104">tblPrincipalInvites 包含所有擁有自動邀請之節點之已預配使用者的邀請。</span><span class="sxs-lookup"><span data-stu-id="9a1ac-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="9a1ac-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="9a1ac-105">**Columns**</span></span>

|<span data-ttu-id="9a1ac-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="9a1ac-106">**Column**</span></span>|<span data-ttu-id="9a1ac-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="9a1ac-107">**Type**</span></span>|<span data-ttu-id="9a1ac-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="9a1ac-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9a1ac-109">prinID</span><span class="sxs-lookup"><span data-stu-id="9a1ac-109">prinID</span></span>  <br/> |<span data-ttu-id="9a1ac-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="9a1ac-110">int, not null</span></span>  <br/> |<span data-ttu-id="9a1ac-111">Principal ID。</span><span class="sxs-lookup"><span data-stu-id="9a1ac-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="9a1ac-112">invID</span><span class="sxs-lookup"><span data-stu-id="9a1ac-112">invID</span></span>  <br/> |<span data-ttu-id="9a1ac-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="9a1ac-113">int, not null</span></span>  <br/> |<span data-ttu-id="9a1ac-114">從 tblLastInviteId 資料表產生的唯一順序編號（每個主體識別碼）。</span><span class="sxs-lookup"><span data-stu-id="9a1ac-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="9a1ac-115">個</span><span class="sxs-lookup"><span data-stu-id="9a1ac-115">nodeID</span></span>  <br/> |<span data-ttu-id="9a1ac-116">int，not null</span><span class="sxs-lookup"><span data-stu-id="9a1ac-116">int, not null</span></span>  <br/> |<span data-ttu-id="9a1ac-117">節點識別碼（僅適用于聊天室）。</span><span class="sxs-lookup"><span data-stu-id="9a1ac-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="9a1ac-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="9a1ac-118">createdOn</span></span>  <br/> |<span data-ttu-id="9a1ac-119">datetime、not null</span><span class="sxs-lookup"><span data-stu-id="9a1ac-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="9a1ac-120">建立時間。</span><span class="sxs-lookup"><span data-stu-id="9a1ac-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="9a1ac-121">**鍵**</span><span class="sxs-lookup"><span data-stu-id="9a1ac-121">**Keys**</span></span>

|<span data-ttu-id="9a1ac-122">**左欄**</span><span class="sxs-lookup"><span data-stu-id="9a1ac-122">**Column**</span></span>|<span data-ttu-id="9a1ac-123">**說明**</span><span class="sxs-lookup"><span data-stu-id="9a1ac-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9a1ac-124">\<prinID、\></span><span class="sxs-lookup"><span data-stu-id="9a1ac-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="9a1ac-125">主鍵。</span><span class="sxs-lookup"><span data-stu-id="9a1ac-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="9a1ac-126">prinID</span><span class="sxs-lookup"><span data-stu-id="9a1ac-126">prinID</span></span>  <br/> |<span data-ttu-id="9a1ac-127">在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="9a1ac-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="9a1ac-128">個</span><span class="sxs-lookup"><span data-stu-id="9a1ac-128">nodeID</span></span>  <br/> |<span data-ttu-id="9a1ac-129">在 tblNode 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="9a1ac-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

