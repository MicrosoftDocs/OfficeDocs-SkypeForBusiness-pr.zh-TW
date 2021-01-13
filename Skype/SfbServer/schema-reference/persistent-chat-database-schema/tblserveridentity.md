---
title: tblServerIdentity
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
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity 包含 Persistent Chat Server 集區中的主動聊天伺服器。
ms.openlocfilehash: 7fa8c1b804432b3a9368785682f45e9ce8d7898e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831493"
---
# <a name="tblserveridentity"></a><span data-ttu-id="c9d83-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="c9d83-103">tblServerIdentity</span></span>
 
<span data-ttu-id="c9d83-104">tblServerIdentity 包含 Persistent Chat Server 集區中的主動聊天伺服器。</span><span class="sxs-lookup"><span data-stu-id="c9d83-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="c9d83-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="c9d83-105">**Columns**</span></span>

|<span data-ttu-id="c9d83-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="c9d83-106">**Column**</span></span>|<span data-ttu-id="c9d83-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="c9d83-107">**Type**</span></span>|<span data-ttu-id="c9d83-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="c9d83-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c9d83-109">serverID</span><span class="sxs-lookup"><span data-stu-id="c9d83-109">serverID</span></span>  <br/> |<span data-ttu-id="c9d83-110">int，非 null</span><span class="sxs-lookup"><span data-stu-id="c9d83-110">int, not null</span></span>  <br/> |<span data-ttu-id="c9d83-111">伺服器識別碼。</span><span class="sxs-lookup"><span data-stu-id="c9d83-111">Server ID.</span></span> <span data-ttu-id="c9d83-112">對應至中央管理存放區的實例識別碼。</span><span class="sxs-lookup"><span data-stu-id="c9d83-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="c9d83-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="c9d83-113">serverAddress</span></span>  <br/> |<span data-ttu-id="c9d83-114">nvarchar (256)，非 null</span><span class="sxs-lookup"><span data-stu-id="c9d83-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="c9d83-115">使用 Windows Communication Foundation 位址的伺服器位址。</span><span class="sxs-lookup"><span data-stu-id="c9d83-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="c9d83-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="c9d83-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="c9d83-117">datetime</span><span class="sxs-lookup"><span data-stu-id="c9d83-117">datetime</span></span>  <br/> |<span data-ttu-id="c9d83-118">通道伺服器更新此列以證明其為執行中的最新時間。</span><span class="sxs-lookup"><span data-stu-id="c9d83-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="c9d83-119">**Key**</span><span class="sxs-lookup"><span data-stu-id="c9d83-119">**Key**</span></span>

|<span data-ttu-id="c9d83-120">**欄**</span><span class="sxs-lookup"><span data-stu-id="c9d83-120">**Column**</span></span>|<span data-ttu-id="c9d83-121">**描述**</span><span class="sxs-lookup"><span data-stu-id="c9d83-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9d83-122">serverID</span><span class="sxs-lookup"><span data-stu-id="c9d83-122">serverID</span></span>  <br/> |<span data-ttu-id="c9d83-123">主索引鍵。</span><span class="sxs-lookup"><span data-stu-id="c9d83-123">Primary key.</span></span>  <br/> |
   

