---
title: Pool 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Pool 表格是一種支援資料表，可儲存各種前端集區的相關資訊。 資料表中的每一筆記錄都代表一個集區。
ms.openlocfilehash: e90b9b2a34a184e1d8cdb23dc3d33b1c41367584
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815813"
---
# <a name="pool-table"></a><span data-ttu-id="4b370-104">Pool 表格</span><span class="sxs-lookup"><span data-stu-id="4b370-104">Pool table</span></span>
 
<span data-ttu-id="4b370-105">Pool 表格是一種支援資料表，可儲存各種前端集區的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4b370-105">The Pool table is a supporting table that stores information about the various Front End pools.</span></span> <span data-ttu-id="4b370-106">資料表中的每一筆記錄都代表一個集區。</span><span class="sxs-lookup"><span data-stu-id="4b370-106">Each record in the table represents one pool.</span></span>
  
|<span data-ttu-id="4b370-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="4b370-107">**Column**</span></span>|<span data-ttu-id="4b370-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="4b370-108">**Data Type**</span></span>|<span data-ttu-id="4b370-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="4b370-109">**Key/Index**</span></span>|<span data-ttu-id="4b370-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="4b370-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4b370-111">**PoolKey**</span><span class="sxs-lookup"><span data-stu-id="4b370-111">**PoolKey**</span></span> <br/> |<span data-ttu-id="4b370-112">int</span><span class="sxs-lookup"><span data-stu-id="4b370-112">int</span></span>  <br/> |<span data-ttu-id="4b370-113">主要</span><span class="sxs-lookup"><span data-stu-id="4b370-113">Primary</span></span>  <br/> |<span data-ttu-id="4b370-114">用於識別此集區的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="4b370-114">Unique number identifying this pool.</span></span>  <br/> |
|<span data-ttu-id="4b370-115">**PoolName**</span><span class="sxs-lookup"><span data-stu-id="4b370-115">**PoolName**</span></span> <br/> |<span data-ttu-id="4b370-116">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="4b370-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="4b370-117">Unique</span><span class="sxs-lookup"><span data-stu-id="4b370-117">Unique</span></span>  <br/> |<span data-ttu-id="4b370-118">集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="4b370-118">Pool FQDN.</span></span>  <br/> |
   

