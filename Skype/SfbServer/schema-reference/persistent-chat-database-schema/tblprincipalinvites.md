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
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites 包含所有擁有自動邀請之節點之已預配使用者的邀請。
ms.openlocfilehash: 21344cfc34ce046a1dffdf7cd3ee9557da20a7ef
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192723"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="80455-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="80455-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="80455-104">tblPrincipalInvites 包含所有擁有自動邀請之節點之已預配使用者的邀請。</span><span class="sxs-lookup"><span data-stu-id="80455-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="80455-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="80455-105">**Columns**</span></span>

|<span data-ttu-id="80455-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="80455-106">**Column**</span></span>|<span data-ttu-id="80455-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="80455-107">**Type**</span></span>|<span data-ttu-id="80455-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="80455-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="80455-109">prinID</span><span class="sxs-lookup"><span data-stu-id="80455-109">prinID</span></span>  <br/> |<span data-ttu-id="80455-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="80455-110">int, not null</span></span>  <br/> |<span data-ttu-id="80455-111">Principal ID。</span><span class="sxs-lookup"><span data-stu-id="80455-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="80455-112">invID</span><span class="sxs-lookup"><span data-stu-id="80455-112">invID</span></span>  <br/> |<span data-ttu-id="80455-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="80455-113">int, not null</span></span>  <br/> |<span data-ttu-id="80455-114">從 tblLastInviteId 資料表產生的唯一順序編號 (每個主體識別碼)。</span><span class="sxs-lookup"><span data-stu-id="80455-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="80455-115">個</span><span class="sxs-lookup"><span data-stu-id="80455-115">nodeID</span></span>  <br/> |<span data-ttu-id="80455-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="80455-116">int, not null</span></span>  <br/> |<span data-ttu-id="80455-117">節點識別碼 (僅適用于聊天室)。</span><span class="sxs-lookup"><span data-stu-id="80455-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="80455-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="80455-118">createdOn</span></span>  <br/> |<span data-ttu-id="80455-119">datetime、not null</span><span class="sxs-lookup"><span data-stu-id="80455-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="80455-120">建立時間。</span><span class="sxs-lookup"><span data-stu-id="80455-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="80455-121">**鍵**</span><span class="sxs-lookup"><span data-stu-id="80455-121">**Keys**</span></span>

|<span data-ttu-id="80455-122">**左欄**</span><span class="sxs-lookup"><span data-stu-id="80455-122">**Column**</span></span>|<span data-ttu-id="80455-123">**說明**</span><span class="sxs-lookup"><span data-stu-id="80455-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="80455-124">\<prinID、\></span><span class="sxs-lookup"><span data-stu-id="80455-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="80455-125">主鍵。</span><span class="sxs-lookup"><span data-stu-id="80455-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="80455-126">prinID</span><span class="sxs-lookup"><span data-stu-id="80455-126">prinID</span></span>  <br/> |<span data-ttu-id="80455-127">在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="80455-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="80455-128">個</span><span class="sxs-lookup"><span data-stu-id="80455-128">nodeID</span></span>  <br/> |<span data-ttu-id="80455-129">在 tblNode 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="80455-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

