---
title: tblLastInviteId
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
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId 表格含有每個使用者產生 (也用於 tblPrincipalInvites 表格) 的最後一個邀請 ID。
ms.openlocfilehash: 9d5ec67a4f5c3db8558c58834582d489fde00ab6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815963"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="07853-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="07853-103">tblLastInviteId</span></span>
 
<span data-ttu-id="07853-104">tblLastInviteId 表格含有每個使用者產生 (也用於 tblPrincipalInvites 表格) 的最後一個邀請 ID。</span><span class="sxs-lookup"><span data-stu-id="07853-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="07853-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="07853-105">**Columns**</span></span>

|<span data-ttu-id="07853-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="07853-106">**Column**</span></span>|<span data-ttu-id="07853-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="07853-107">**Type**</span></span>|<span data-ttu-id="07853-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="07853-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="07853-109">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="07853-109">prinID</span></span>  <br/> |<span data-ttu-id="07853-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="07853-110">int, not null</span></span>  <br/> |<span data-ttu-id="07853-111">主體識別碼。</span><span class="sxs-lookup"><span data-stu-id="07853-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="07853-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="07853-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="07853-113">int，非 null</span><span class="sxs-lookup"><span data-stu-id="07853-113">int, not null</span></span>  <br/> |<span data-ttu-id="07853-114">最後一個邀請 ID。</span><span class="sxs-lookup"><span data-stu-id="07853-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="07853-115">**Keys**</span><span class="sxs-lookup"><span data-stu-id="07853-115">**Keys**</span></span>

|<span data-ttu-id="07853-116">**欄**</span><span class="sxs-lookup"><span data-stu-id="07853-116">**Column**</span></span>|<span data-ttu-id="07853-117">**描述**</span><span class="sxs-lookup"><span data-stu-id="07853-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="07853-118">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="07853-118">prinID</span></span>  <br/> |<span data-ttu-id="07853-119">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="07853-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="07853-120">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="07853-120">prinID</span></span>  <br/> |<span data-ttu-id="07853-121">在 tblPrincipal.prinID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="07853-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="07853-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="07853-122">See also</span></span>

[<span data-ttu-id="07853-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="07853-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
