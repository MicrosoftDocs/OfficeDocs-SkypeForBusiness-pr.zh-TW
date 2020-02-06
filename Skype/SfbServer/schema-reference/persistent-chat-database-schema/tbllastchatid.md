---
title: tblLastChatId
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
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId 包含每位使用者所產生（並在 tblChat 資料表中使用）的最後一個聊天 ID。
ms.openlocfilehash: 95498f077948e1b400d0a370762c121def703e8c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814581"
---
# <a name="tbllastchatid"></a><span data-ttu-id="c6499-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="c6499-103">tblLastChatId</span></span>
 
<span data-ttu-id="c6499-104">tblLastChatId 包含每位使用者所產生（並在 tblChat 資料表中使用）的最後一個聊天 ID。</span><span class="sxs-lookup"><span data-stu-id="c6499-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="c6499-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="c6499-105">**Columns**</span></span>

|<span data-ttu-id="c6499-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="c6499-106">**Column**</span></span>|<span data-ttu-id="c6499-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="c6499-107">**Type**</span></span>|<span data-ttu-id="c6499-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="c6499-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c6499-109">個</span><span class="sxs-lookup"><span data-stu-id="c6499-109">nodeID</span></span>  <br/> |<span data-ttu-id="c6499-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="c6499-110">int, not null</span></span>  <br/> |<span data-ttu-id="c6499-111">[Node ID] （聊天室-僅限類型）。</span><span class="sxs-lookup"><span data-stu-id="c6499-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="c6499-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="c6499-112">lastChatID</span></span>  <br/> |<span data-ttu-id="c6499-113">Bigint，not null</span><span class="sxs-lookup"><span data-stu-id="c6499-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="c6499-114">上次使用的聊天 ID。</span><span class="sxs-lookup"><span data-stu-id="c6499-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="c6499-115">**鍵**</span><span class="sxs-lookup"><span data-stu-id="c6499-115">**Keys**</span></span>

|<span data-ttu-id="c6499-116">**左欄**</span><span class="sxs-lookup"><span data-stu-id="c6499-116">**Column**</span></span>|<span data-ttu-id="c6499-117">**說明**</span><span class="sxs-lookup"><span data-stu-id="c6499-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c6499-118">\<lastChatID\></span><span class="sxs-lookup"><span data-stu-id="c6499-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="c6499-119">主鍵（只有一個代表可充分處理）。</span><span class="sxs-lookup"><span data-stu-id="c6499-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="c6499-120">個</span><span class="sxs-lookup"><span data-stu-id="c6499-120">nodeID</span></span>  <br/> |<span data-ttu-id="c6499-121">在 tblNode 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="c6499-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c6499-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c6499-122">See also</span></span>

[<span data-ttu-id="c6499-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="c6499-123">tblChat</span></span>](tblchat.md)
