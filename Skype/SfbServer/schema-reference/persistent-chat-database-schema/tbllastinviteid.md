---
title: tblLastInviteId
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
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId 包含每位使用者所產生（並在 tblPrincipalInvites 資料表中使用）的最後一個邀請識別碼。
ms.openlocfilehash: 17d1b725da034f79f8efc9ff9071c36430efde7d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814571"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="3d0e8-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="3d0e8-103">tblLastInviteId</span></span>
 
<span data-ttu-id="3d0e8-104">tblLastInviteId 包含每位使用者所產生（並在 tblPrincipalInvites 資料表中使用）的最後一個邀請識別碼。</span><span class="sxs-lookup"><span data-stu-id="3d0e8-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="3d0e8-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="3d0e8-105">**Columns**</span></span>

|<span data-ttu-id="3d0e8-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="3d0e8-106">**Column**</span></span>|<span data-ttu-id="3d0e8-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="3d0e8-107">**Type**</span></span>|<span data-ttu-id="3d0e8-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="3d0e8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3d0e8-109">prinID</span><span class="sxs-lookup"><span data-stu-id="3d0e8-109">prinID</span></span>  <br/> |<span data-ttu-id="3d0e8-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="3d0e8-110">int, not null</span></span>  <br/> |<span data-ttu-id="3d0e8-111">Principal ID。</span><span class="sxs-lookup"><span data-stu-id="3d0e8-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="3d0e8-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="3d0e8-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="3d0e8-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="3d0e8-113">int, not null</span></span>  <br/> |<span data-ttu-id="3d0e8-114">上次使用邀請 ID。</span><span class="sxs-lookup"><span data-stu-id="3d0e8-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="3d0e8-115">**鍵**</span><span class="sxs-lookup"><span data-stu-id="3d0e8-115">**Keys**</span></span>

|<span data-ttu-id="3d0e8-116">**左欄**</span><span class="sxs-lookup"><span data-stu-id="3d0e8-116">**Column**</span></span>|<span data-ttu-id="3d0e8-117">**說明**</span><span class="sxs-lookup"><span data-stu-id="3d0e8-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3d0e8-118">prinID</span><span class="sxs-lookup"><span data-stu-id="3d0e8-118">prinID</span></span>  <br/> |<span data-ttu-id="3d0e8-119">主鍵。</span><span class="sxs-lookup"><span data-stu-id="3d0e8-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="3d0e8-120">prinID</span><span class="sxs-lookup"><span data-stu-id="3d0e8-120">prinID</span></span>  <br/> |<span data-ttu-id="3d0e8-121">在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="3d0e8-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3d0e8-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3d0e8-122">See also</span></span>

[<span data-ttu-id="3d0e8-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="3d0e8-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
