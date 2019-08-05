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
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId 包含每位使用者所產生 (並在 tblChat 資料表中使用) 的最後一個聊天 ID。
ms.openlocfilehash: f14d8090fd3252d88ef747de93a987f51870a63b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192736"
---
# <a name="tbllastchatid"></a><span data-ttu-id="e1145-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="e1145-103">tblLastChatId</span></span>
 
<span data-ttu-id="e1145-104">tblLastChatId 包含每位使用者所產生 (並在 tblChat 資料表中使用) 的最後一個聊天 ID。</span><span class="sxs-lookup"><span data-stu-id="e1145-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="e1145-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="e1145-105">**Columns**</span></span>

|<span data-ttu-id="e1145-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="e1145-106">**Column**</span></span>|<span data-ttu-id="e1145-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="e1145-107">**Type**</span></span>|<span data-ttu-id="e1145-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="e1145-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e1145-109">個</span><span class="sxs-lookup"><span data-stu-id="e1145-109">nodeID</span></span>  <br/> |<span data-ttu-id="e1145-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="e1145-110">int, not null</span></span>  <br/> |<span data-ttu-id="e1145-111">[Node ID] (聊天室-僅限類型)。</span><span class="sxs-lookup"><span data-stu-id="e1145-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="e1145-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="e1145-112">lastChatID</span></span>  <br/> |<span data-ttu-id="e1145-113">Bigint, not null</span><span class="sxs-lookup"><span data-stu-id="e1145-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="e1145-114">上次使用的聊天 ID。</span><span class="sxs-lookup"><span data-stu-id="e1145-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="e1145-115">**鍵**</span><span class="sxs-lookup"><span data-stu-id="e1145-115">**Keys**</span></span>

|<span data-ttu-id="e1145-116">**左欄**</span><span class="sxs-lookup"><span data-stu-id="e1145-116">**Column**</span></span>|<span data-ttu-id="e1145-117">**說明**</span><span class="sxs-lookup"><span data-stu-id="e1145-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e1145-118">\<lastChatID\></span><span class="sxs-lookup"><span data-stu-id="e1145-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="e1145-119">主鍵 (只有一個代表可充分處理)。</span><span class="sxs-lookup"><span data-stu-id="e1145-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="e1145-120">個</span><span class="sxs-lookup"><span data-stu-id="e1145-120">nodeID</span></span>  <br/> |<span data-ttu-id="e1145-121">在 tblNode 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="e1145-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e1145-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e1145-122">See also</span></span>

[<span data-ttu-id="e1145-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="e1145-123">tblChat</span></span>](tblchat.md)
