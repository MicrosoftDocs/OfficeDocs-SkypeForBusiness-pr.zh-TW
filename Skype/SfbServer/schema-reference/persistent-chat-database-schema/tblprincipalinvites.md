---
title: tblPrincipalInvites
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites 包含所有提供給啟動自動邀請的所有節點之佈建使用者的邀請。
ms.openlocfilehash: 5bbccd582442001bd2122dcbacdbe3634fcfd649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815853"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="4e228-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="4e228-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="4e228-104">tblPrincipalInvites 包含所有提供給啟動自動邀請的所有節點之佈建使用者的邀請。</span><span class="sxs-lookup"><span data-stu-id="4e228-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="4e228-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="4e228-105">**Columns**</span></span>

|<span data-ttu-id="4e228-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="4e228-106">**Column**</span></span>|<span data-ttu-id="4e228-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="4e228-107">**Type**</span></span>|<span data-ttu-id="4e228-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="4e228-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4e228-109">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="4e228-109">prinID</span></span>  <br/> |<span data-ttu-id="4e228-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="4e228-110">int, not null</span></span>  <br/> |<span data-ttu-id="4e228-111">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="4e228-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="4e228-112">尹雯德</span><span class="sxs-lookup"><span data-stu-id="4e228-112">invID</span></span>  <br/> |<span data-ttu-id="4e228-113">int，非 null</span><span class="sxs-lookup"><span data-stu-id="4e228-113">int, not null</span></span>  <br/> |<span data-ttu-id="4e228-114">從 tblLastInviteId 表格產生的唯一序號 (每個主體識別碼)。</span><span class="sxs-lookup"><span data-stu-id="4e228-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="4e228-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="4e228-115">nodeID</span></span>  <br/> |<span data-ttu-id="4e228-116">int，非 null</span><span class="sxs-lookup"><span data-stu-id="4e228-116">int, not null</span></span>  <br/> |<span data-ttu-id="4e228-117">節點識別碼 (僅限聊天室)。</span><span class="sxs-lookup"><span data-stu-id="4e228-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="4e228-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="4e228-118">createdOn</span></span>  <br/> |<span data-ttu-id="4e228-119">日期時間，非 null</span><span class="sxs-lookup"><span data-stu-id="4e228-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="4e228-120">建立的時間。</span><span class="sxs-lookup"><span data-stu-id="4e228-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="4e228-121">**Keys**</span><span class="sxs-lookup"><span data-stu-id="4e228-121">**Keys**</span></span>

|<span data-ttu-id="4e228-122">**欄**</span><span class="sxs-lookup"><span data-stu-id="4e228-122">**Column**</span></span>|<span data-ttu-id="4e228-123">**描述**</span><span class="sxs-lookup"><span data-stu-id="4e228-123">**Description**</span></span>|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |<span data-ttu-id="4e228-124">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="4e228-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="4e228-125">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="4e228-125">prinID</span></span>  <br/> |<span data-ttu-id="4e228-126">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="4e228-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="4e228-127">nodeID</span><span class="sxs-lookup"><span data-stu-id="4e228-127">nodeID</span></span>  <br/> |<span data-ttu-id="4e228-128">在 tblNode.nodeID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="4e228-128">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

