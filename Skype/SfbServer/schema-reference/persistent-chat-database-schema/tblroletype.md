---
title: tblRoleType
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
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType 是一個靜態查閱表格，其中包含角色類型及其關聯的許可權集。
ms.openlocfilehash: 888628c1aca01e90694ed946569a81b1b7394b95
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812901"
---
# <a name="tblroletype"></a><span data-ttu-id="a78d3-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="a78d3-103">tblRoleType</span></span>
 
<span data-ttu-id="a78d3-104">tblRoleType 是一個靜態查閱表格，其中包含角色類型及其關聯的許可權集。</span><span class="sxs-lookup"><span data-stu-id="a78d3-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="a78d3-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="a78d3-105">**Columns**</span></span>

|<span data-ttu-id="a78d3-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="a78d3-106">**Column**</span></span>|<span data-ttu-id="a78d3-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="a78d3-107">**Type**</span></span>|<span data-ttu-id="a78d3-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="a78d3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a78d3-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="a78d3-109">rtypeID</span></span>  <br/> |<span data-ttu-id="a78d3-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="a78d3-110">int, not null</span></span>  <br/> |<span data-ttu-id="a78d3-111">角色類型 ID。</span><span class="sxs-lookup"><span data-stu-id="a78d3-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="a78d3-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="a78d3-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="a78d3-113">Nvarchar （256），not null</span><span class="sxs-lookup"><span data-stu-id="a78d3-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="a78d3-114">角色類型描述。</span><span class="sxs-lookup"><span data-stu-id="a78d3-114">Role type description.</span></span> <span data-ttu-id="a78d3-115">共有四個可用的角色：</span><span class="sxs-lookup"><span data-stu-id="a78d3-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="a78d3-116">成員：聊天室成員</span><span class="sxs-lookup"><span data-stu-id="a78d3-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="a78d3-117">管理員：聊天室管理員</span><span class="sxs-lookup"><span data-stu-id="a78d3-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="a78d3-118">濁音： auditorium 聊天室的簡報者</span><span class="sxs-lookup"><span data-stu-id="a78d3-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="a78d3-119">建立者：可以建立聊天室</span><span class="sxs-lookup"><span data-stu-id="a78d3-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="a78d3-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="a78d3-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="a78d3-121">Bigint，not null</span><span class="sxs-lookup"><span data-stu-id="a78d3-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="a78d3-122">角色的許可權集。</span><span class="sxs-lookup"><span data-stu-id="a78d3-122">Permission set for the role.</span></span> <span data-ttu-id="a78d3-123">已使用的位數如下：</span><span class="sxs-lookup"><span data-stu-id="a78d3-123">The used bits are:</span></span> <br/>  <span data-ttu-id="a78d3-124">2：如果角色可以管理節點，則為 True。</span><span class="sxs-lookup"><span data-stu-id="a78d3-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="a78d3-125">4：如果角色可以建立子節點，則為 True。</span><span class="sxs-lookup"><span data-stu-id="a78d3-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="a78d3-126">7：如果角色可以加入聊天室（或類別的子聊天室），則為 True。</span><span class="sxs-lookup"><span data-stu-id="a78d3-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="a78d3-127">8：如果角色可以在聊天室（或在子類別的 [兒童聊天室] 聊天室）中聊天，則為 True。</span><span class="sxs-lookup"><span data-stu-id="a78d3-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="a78d3-128">10： True，如果角色可以讀取聊天記錄，即使未加入聊天室也一樣。</span><span class="sxs-lookup"><span data-stu-id="a78d3-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="a78d3-129">11：如果角色可以查看聊天室，則為 True。</span><span class="sxs-lookup"><span data-stu-id="a78d3-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="a78d3-130">（例如範圍和可見度等因素進一步改進。）</span><span class="sxs-lookup"><span data-stu-id="a78d3-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="a78d3-131">12：如果角色可以在 auditorium 聊天室中聊天，則為 True。</span><span class="sxs-lookup"><span data-stu-id="a78d3-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="a78d3-132">13：如果角色在查看節點時可以略過可見度規則，則為 True。</span><span class="sxs-lookup"><span data-stu-id="a78d3-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="a78d3-133">**機碼**</span><span class="sxs-lookup"><span data-stu-id="a78d3-133">**Key**</span></span>

|<span data-ttu-id="a78d3-134">**左欄**</span><span class="sxs-lookup"><span data-stu-id="a78d3-134">**Column**</span></span>|<span data-ttu-id="a78d3-135">**說明**</span><span class="sxs-lookup"><span data-stu-id="a78d3-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a78d3-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="a78d3-136">rtypeID</span></span>  <br/> |<span data-ttu-id="a78d3-137">主鍵。</span><span class="sxs-lookup"><span data-stu-id="a78d3-137">Primary key.</span></span>  <br/> |
   

