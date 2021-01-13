---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant 包含每個通道和每部伺服器的目前參與者。
ms.openlocfilehash: c6aae3c1e7b13456708034512c6b68d67d6d1f92
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809743"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="43238-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="43238-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="43238-104">tblComplianceParticipant 包含每個通道和每部伺服器的目前參與者。</span><span class="sxs-lookup"><span data-stu-id="43238-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="43238-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="43238-105">**Columns**</span></span>

|<span data-ttu-id="43238-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="43238-106">**Column**</span></span>|<span data-ttu-id="43238-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="43238-107">**Type**</span></span>|<span data-ttu-id="43238-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="43238-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="43238-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="43238-109">channelUri</span></span>  <br/> |<span data-ttu-id="43238-110">nvarchar (255)，非 null</span><span class="sxs-lookup"><span data-stu-id="43238-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="43238-111">通道統一資源識別項 (URI)。</span><span class="sxs-lookup"><span data-stu-id="43238-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="43238-112">userId</span><span class="sxs-lookup"><span data-stu-id="43238-112">userId</span></span>  <br/> |<span data-ttu-id="43238-113">int，非 null</span><span class="sxs-lookup"><span data-stu-id="43238-113">int, not null</span></span>  <br/> |<span data-ttu-id="43238-114">參與者的主體識別碼 (對應至 tblPrincipal.prinID 表格)。</span><span class="sxs-lookup"><span data-stu-id="43238-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="43238-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="43238-115">joinedAt</span></span>  <br/> |<span data-ttu-id="43238-116">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="43238-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="43238-117">加入活動的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="43238-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="43238-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="43238-118">partedAt</span></span>  <br/> |<span data-ttu-id="43238-119">Bigint</span><span class="sxs-lookup"><span data-stu-id="43238-119">bigint</span></span>  <br/> |<span data-ttu-id="43238-p101">如果參與者仍加入，則為 Null。如果不是 Null，則是通道離開事件的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="43238-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="43238-122">當所有轉譯器處理事件時，這些項目最後都會移除。</span><span class="sxs-lookup"><span data-stu-id="43238-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="43238-123">userUri</span><span class="sxs-lookup"><span data-stu-id="43238-123">userUri</span></span>  <br/> |<span data-ttu-id="43238-124">nvarchar(255)，非 null</span><span class="sxs-lookup"><span data-stu-id="43238-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="43238-125">使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="43238-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="43238-126">serverID</span><span class="sxs-lookup"><span data-stu-id="43238-126">serverID</span></span>  <br/> |<span data-ttu-id="43238-127">int</span><span class="sxs-lookup"><span data-stu-id="43238-127">int</span></span>  <br/> |<span data-ttu-id="43238-128">伺服器識別碼 (如 tblServerIdentity.serverID 表格中所示)。</span><span class="sxs-lookup"><span data-stu-id="43238-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="43238-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="43238-129">sessionId</span></span>  <br/> |<span data-ttu-id="43238-130">Bigint</span><span class="sxs-lookup"><span data-stu-id="43238-130">bigint</span></span>  <br/> |<span data-ttu-id="43238-p102">伺服器工作階段。這是聊天服務每次啟動時，所產生的隨機號碼。在識別孤立的參與者時，可使用此號碼來區別工作階段。</span><span class="sxs-lookup"><span data-stu-id="43238-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="43238-134">**Key**</span><span class="sxs-lookup"><span data-stu-id="43238-134">**Key**</span></span>

|<span data-ttu-id="43238-135">**欄**</span><span class="sxs-lookup"><span data-stu-id="43238-135">**Column**</span></span>|<span data-ttu-id="43238-136">**描述**</span><span class="sxs-lookup"><span data-stu-id="43238-136">**Description**</span></span>|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |<span data-ttu-id="43238-137">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="43238-137">Primary key.</span></span>  <br/> |
   

