---
title: tblRoleType
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
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType 表格是一種靜態查閱表格，其中含有角色類型與其相關的權限組。
ms.openlocfilehash: c440463d822b908a89c84eb9c85b70e9daf442be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831523"
---
# <a name="tblroletype"></a><span data-ttu-id="422c9-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="422c9-103">tblRoleType</span></span>
 
<span data-ttu-id="422c9-104">tblRoleType 表格是一種靜態查閱表格，其中含有角色類型與其相關的權限組。</span><span class="sxs-lookup"><span data-stu-id="422c9-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="422c9-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="422c9-105">**Columns**</span></span>

|<span data-ttu-id="422c9-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="422c9-106">**Column**</span></span>|<span data-ttu-id="422c9-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="422c9-107">**Type**</span></span>|<span data-ttu-id="422c9-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="422c9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="422c9-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="422c9-109">rtypeID</span></span>  <br/> |<span data-ttu-id="422c9-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="422c9-110">int, not null</span></span>  <br/> |<span data-ttu-id="422c9-111">角色類型識別碼。</span><span class="sxs-lookup"><span data-stu-id="422c9-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="422c9-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="422c9-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="422c9-113">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="422c9-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="422c9-p101">角色類型描述。以下是四個可用的角色：</span><span class="sxs-lookup"><span data-stu-id="422c9-p101">Role type description. There are four available roles:</span></span> <br/>  <span data-ttu-id="422c9-116">Member：聊天室成員</span><span class="sxs-lookup"><span data-stu-id="422c9-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="422c9-117">Manager：聊天室管理員</span><span class="sxs-lookup"><span data-stu-id="422c9-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="422c9-118">Voiced：視聽中心聊天室簡報者</span><span class="sxs-lookup"><span data-stu-id="422c9-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="422c9-119">Creator：可建立聊天室</span><span class="sxs-lookup"><span data-stu-id="422c9-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="422c9-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="422c9-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="422c9-121">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="422c9-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="422c9-p102">角色的權限組。使用的位元如下：</span><span class="sxs-lookup"><span data-stu-id="422c9-p102">Permission set for the role. The used bits are:</span></span> <br/>  <span data-ttu-id="422c9-124">2: 若角色可管理節點則為 True。</span><span class="sxs-lookup"><span data-stu-id="422c9-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="422c9-125">4: 若角色可建立子節點則為 True。</span><span class="sxs-lookup"><span data-stu-id="422c9-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="422c9-126">7: 若角色可加入聊天室 (或類別的子聊天室) 則為 True。</span><span class="sxs-lookup"><span data-stu-id="422c9-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="422c9-127">8: 若角色可在聊天室 (或類別的子聊天室) 中交談則為 True。</span><span class="sxs-lookup"><span data-stu-id="422c9-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="422c9-128">10: 若角色可讀取聊天記錄則為 True (即使未加入聊天室時亦可)。</span><span class="sxs-lookup"><span data-stu-id="422c9-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="422c9-p103">11: 若角色可看到聊天室則為 True (可進一步依據範圍和可見度等因素來調整)。</span><span class="sxs-lookup"><span data-stu-id="422c9-p103">11: True if the role can see the chat room. (This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="422c9-131">12: 若角色可在視聽中心聊天室中交談則為 True。</span><span class="sxs-lookup"><span data-stu-id="422c9-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="422c9-132">13: 若角色可在檢視節點時略過可見度規則則為 True。</span><span class="sxs-lookup"><span data-stu-id="422c9-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="422c9-133">**Key**</span><span class="sxs-lookup"><span data-stu-id="422c9-133">**Key**</span></span>

|<span data-ttu-id="422c9-134">**欄**</span><span class="sxs-lookup"><span data-stu-id="422c9-134">**Column**</span></span>|<span data-ttu-id="422c9-135">**描述**</span><span class="sxs-lookup"><span data-stu-id="422c9-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="422c9-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="422c9-136">rtypeID</span></span>  <br/> |<span data-ttu-id="422c9-137">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="422c9-137">Primary key.</span></span>  <br/> |
   

