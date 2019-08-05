---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity 包含持續聊天伺服器池中的活動聊天伺服器。
ms.openlocfilehash: b35960bd1deef5470724f580bce2375b2e034cb9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192709"
---
# <a name="tblserveridentity"></a><span data-ttu-id="69323-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="69323-103">tblServerIdentity</span></span>
 
<span data-ttu-id="69323-104">tblServerIdentity 包含持續聊天伺服器池中的活動聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="69323-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="69323-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="69323-105">**Columns**</span></span>

|<span data-ttu-id="69323-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="69323-106">**Column**</span></span>|<span data-ttu-id="69323-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="69323-107">**Type**</span></span>|<span data-ttu-id="69323-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="69323-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="69323-109">serverID</span><span class="sxs-lookup"><span data-stu-id="69323-109">serverID</span></span>  <br/> |<span data-ttu-id="69323-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="69323-110">int, not null</span></span>  <br/> |<span data-ttu-id="69323-111">[伺服器識別碼]。</span><span class="sxs-lookup"><span data-stu-id="69323-111">Server ID.</span></span> <span data-ttu-id="69323-112">與中央管理存放區中的實例識別碼相對應。</span><span class="sxs-lookup"><span data-stu-id="69323-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="69323-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="69323-113">serverAddress</span></span>  <br/> |<span data-ttu-id="69323-114">Nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="69323-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="69323-115">使用 Windows Communication Foundation 位址的伺服器位址。</span><span class="sxs-lookup"><span data-stu-id="69323-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="69323-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="69323-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="69323-117">datetime</span><span class="sxs-lookup"><span data-stu-id="69323-117">datetime</span></span>  <br/> |<span data-ttu-id="69323-118">頻道伺服器更新此列以提供其所執行證據的最晚時間。</span><span class="sxs-lookup"><span data-stu-id="69323-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="69323-119">**快速鍵**</span><span class="sxs-lookup"><span data-stu-id="69323-119">**Key**</span></span>

|<span data-ttu-id="69323-120">**左欄**</span><span class="sxs-lookup"><span data-stu-id="69323-120">**Column**</span></span>|<span data-ttu-id="69323-121">**說明**</span><span class="sxs-lookup"><span data-stu-id="69323-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="69323-122">serverID</span><span class="sxs-lookup"><span data-stu-id="69323-122">serverID</span></span>  <br/> |<span data-ttu-id="69323-123">主鍵。</span><span class="sxs-lookup"><span data-stu-id="69323-123">Primary key.</span></span>  <br/> |
   

