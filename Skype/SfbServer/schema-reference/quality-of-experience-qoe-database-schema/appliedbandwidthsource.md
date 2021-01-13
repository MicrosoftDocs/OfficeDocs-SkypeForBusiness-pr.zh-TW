---
title: AppliedBandwidthSource 表格
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
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource 表格是支援的表格。 每筆記錄代表一個來源。
ms.openlocfilehash: bf7e1be3b98bcd56fea16dbd7aa7171b056a7f3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831403"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="80397-104">AppliedBandwidthSource 表格</span><span class="sxs-lookup"><span data-stu-id="80397-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="80397-p102">AppliedBandwidthSource 表格是一種支援資料表，其中的每一項記錄都代表一種來源。</span><span class="sxs-lookup"><span data-stu-id="80397-p102">The AppliedBandwidthSource table is a supporting table. Each record represents one source.</span></span>
  
|<span data-ttu-id="80397-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="80397-107">**Column**</span></span>|<span data-ttu-id="80397-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="80397-108">**Data Type**</span></span>|<span data-ttu-id="80397-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="80397-109">**Key/Index**</span></span>|<span data-ttu-id="80397-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="80397-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="80397-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="80397-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="80397-112">int</span><span class="sxs-lookup"><span data-stu-id="80397-112">int</span></span>  <br/> |<span data-ttu-id="80397-113">主要</span><span class="sxs-lookup"><span data-stu-id="80397-113">Primary</span></span>  <br/> |<span data-ttu-id="80397-114">用於識別來源的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="80397-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="80397-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="80397-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="80397-116">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="80397-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="80397-117">Unique</span><span class="sxs-lookup"><span data-stu-id="80397-117">Unique</span></span>  <br/> |<span data-ttu-id="80397-118">這是所採用的頻寬容量來源。</span><span class="sxs-lookup"><span data-stu-id="80397-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="80397-119">它說明頻寬限制來自 (，例如「原則伺服器」、「輪流伺服器」或「模態」 ) 。</span><span class="sxs-lookup"><span data-stu-id="80397-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

