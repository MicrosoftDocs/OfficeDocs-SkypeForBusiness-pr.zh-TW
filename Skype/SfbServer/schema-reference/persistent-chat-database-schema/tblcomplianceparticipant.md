---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant 包含每個通道及每個伺服器的目前參與者。
ms.openlocfilehash: 8f4b90cd7e8949451c2b6c1b9bc3cfabbab826e9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814641"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="1675f-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="1675f-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="1675f-104">tblComplianceParticipant 包含每個通道及每個伺服器的目前參與者。</span><span class="sxs-lookup"><span data-stu-id="1675f-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="1675f-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="1675f-105">**Columns**</span></span>

|<span data-ttu-id="1675f-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="1675f-106">**Column**</span></span>|<span data-ttu-id="1675f-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="1675f-107">**Type**</span></span>|<span data-ttu-id="1675f-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="1675f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1675f-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="1675f-109">channelUri</span></span>  <br/> |<span data-ttu-id="1675f-110">Nvarchar （255），not null</span><span class="sxs-lookup"><span data-stu-id="1675f-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="1675f-111">通道統一資源識別項（URI）。</span><span class="sxs-lookup"><span data-stu-id="1675f-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="1675f-112">userId</span><span class="sxs-lookup"><span data-stu-id="1675f-112">userId</span></span>  <br/> |<span data-ttu-id="1675f-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="1675f-113">int, not null</span></span>  <br/> |<span data-ttu-id="1675f-114">參與者的主體識別碼（對應至 tblPrincipal prinID 資料表）。</span><span class="sxs-lookup"><span data-stu-id="1675f-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="1675f-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="1675f-115">joinedAt</span></span>  <br/> |<span data-ttu-id="1675f-116">Bigint，not null</span><span class="sxs-lookup"><span data-stu-id="1675f-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="1675f-117">加入事件的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="1675f-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="1675f-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="1675f-118">partedAt</span></span>  <br/> |<span data-ttu-id="1675f-119">Bigint</span><span class="sxs-lookup"><span data-stu-id="1675f-119">bigint</span></span>  <br/> |<span data-ttu-id="1675f-120">如果參與者仍在加入，則為 Null。</span><span class="sxs-lookup"><span data-stu-id="1675f-120">Null if participant is still joined.</span></span> <span data-ttu-id="1675f-121">如果 not null，則通道的時間戳記會保留事件。</span><span class="sxs-lookup"><span data-stu-id="1675f-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="1675f-122">這些專案會在所有翻譯員處理事件時最終移除。</span><span class="sxs-lookup"><span data-stu-id="1675f-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="1675f-123">userUri</span><span class="sxs-lookup"><span data-stu-id="1675f-123">userUri</span></span>  <br/> |<span data-ttu-id="1675f-124">Nvarchar （255），not null</span><span class="sxs-lookup"><span data-stu-id="1675f-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="1675f-125">使用者 URI。</span><span class="sxs-lookup"><span data-stu-id="1675f-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="1675f-126">serverID</span><span class="sxs-lookup"><span data-stu-id="1675f-126">serverID</span></span>  <br/> |<span data-ttu-id="1675f-127">int</span><span class="sxs-lookup"><span data-stu-id="1675f-127">int</span></span>  <br/> |<span data-ttu-id="1675f-128">伺服器身分識別（例如在 serverID 資料表中則為 tblServerIdentity）。</span><span class="sxs-lookup"><span data-stu-id="1675f-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="1675f-129">識別碼</span><span class="sxs-lookup"><span data-stu-id="1675f-129">sessionId</span></span>  <br/> |<span data-ttu-id="1675f-130">Bigint</span><span class="sxs-lookup"><span data-stu-id="1675f-130">bigint</span></span>  <br/> |<span data-ttu-id="1675f-131">伺服器會話。</span><span class="sxs-lookup"><span data-stu-id="1675f-131">Server session.</span></span> <span data-ttu-id="1675f-132">這是在每次聊天服務啟動時產生的亂數字。</span><span class="sxs-lookup"><span data-stu-id="1675f-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="1675f-133">它是用來區分會話，目的是識別孤立參與者。</span><span class="sxs-lookup"><span data-stu-id="1675f-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="1675f-134">**機碼**</span><span class="sxs-lookup"><span data-stu-id="1675f-134">**Key**</span></span>

|<span data-ttu-id="1675f-135">**左欄**</span><span class="sxs-lookup"><span data-stu-id="1675f-135">**Column**</span></span>|<span data-ttu-id="1675f-136">**說明**</span><span class="sxs-lookup"><span data-stu-id="1675f-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1675f-137">\<channelUri、userId、joinedAt\></span><span class="sxs-lookup"><span data-stu-id="1675f-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="1675f-138">主鍵。</span><span class="sxs-lookup"><span data-stu-id="1675f-138">Primary key.</span></span>  <br/> |
   

