---
title: tblLastChatId
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
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId 表格包含為每個使用者產生 (且用於 tblChat 表格) 的最後一個交談 ID。
ms.openlocfilehash: 80664d6b296fce9b4909674f9d21b1aa13285826
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816003"
---
# <a name="tbllastchatid"></a><span data-ttu-id="84fd9-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="84fd9-103">tblLastChatId</span></span>
 
<span data-ttu-id="84fd9-104">tblLastChatId 表格包含為每個使用者產生 (且用於 tblChat 表格) 的最後一個交談 ID。</span><span class="sxs-lookup"><span data-stu-id="84fd9-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="84fd9-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="84fd9-105">**Columns**</span></span>

|<span data-ttu-id="84fd9-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="84fd9-106">**Column**</span></span>|<span data-ttu-id="84fd9-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="84fd9-107">**Type**</span></span>|<span data-ttu-id="84fd9-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="84fd9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="84fd9-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="84fd9-109">nodeID</span></span>  <br/> |<span data-ttu-id="84fd9-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="84fd9-110">int, not null</span></span>  <br/> |<span data-ttu-id="84fd9-111">節點識別碼 (僅聊天室類型)。</span><span class="sxs-lookup"><span data-stu-id="84fd9-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="84fd9-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="84fd9-112">lastChatID</span></span>  <br/> |<span data-ttu-id="84fd9-113">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="84fd9-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="84fd9-114">最後一個使用的交談 ID。</span><span class="sxs-lookup"><span data-stu-id="84fd9-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="84fd9-115">**Keys**</span><span class="sxs-lookup"><span data-stu-id="84fd9-115">**Keys**</span></span>

|<span data-ttu-id="84fd9-116">**欄**</span><span class="sxs-lookup"><span data-stu-id="84fd9-116">**Column**</span></span>|<span data-ttu-id="84fd9-117">**描述**</span><span class="sxs-lookup"><span data-stu-id="84fd9-117">**Description**</span></span>|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |<span data-ttu-id="84fd9-118">主索引鍵 (處理時僅有 nodeID 已足夠)。</span><span class="sxs-lookup"><span data-stu-id="84fd9-118">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="84fd9-119">nodeID</span><span class="sxs-lookup"><span data-stu-id="84fd9-119">nodeID</span></span>  <br/> |<span data-ttu-id="84fd9-120">在 tblNode.nodeID 表格中查閱外部索引鍵。</span><span class="sxs-lookup"><span data-stu-id="84fd9-120">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="84fd9-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="84fd9-121">See also</span></span>

[<span data-ttu-id="84fd9-122">tblChat</span><span class="sxs-lookup"><span data-stu-id="84fd9-122">tblChat</span></span>](tblchat.md)
