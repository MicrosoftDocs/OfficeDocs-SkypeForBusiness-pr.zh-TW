---
title: AppliedBandwidthSource 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource 資料表是支援資料表。 每個記錄代表一個來源。
ms.openlocfilehash: 875f6d105a2fef0bf710e57ec389bee4f2613c66
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811441"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="a3237-104">AppliedBandwidthSource 表格</span><span class="sxs-lookup"><span data-stu-id="a3237-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="a3237-105">AppliedBandwidthSource 資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="a3237-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="a3237-106">每個記錄代表一個來源。</span><span class="sxs-lookup"><span data-stu-id="a3237-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="a3237-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="a3237-107">**Column**</span></span>|<span data-ttu-id="a3237-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="a3237-108">**Data Type**</span></span>|<span data-ttu-id="a3237-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="a3237-109">**Key/Index**</span></span>|<span data-ttu-id="a3237-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="a3237-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a3237-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="a3237-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="a3237-112">int</span><span class="sxs-lookup"><span data-stu-id="a3237-112">int</span></span>  <br/> |<span data-ttu-id="a3237-113">首選</span><span class="sxs-lookup"><span data-stu-id="a3237-113">Primary</span></span>  <br/> |<span data-ttu-id="a3237-114">標識來源的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="a3237-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="a3237-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="a3237-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="a3237-116">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="a3237-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="a3237-117">唯一</span><span class="sxs-lookup"><span data-stu-id="a3237-117">Unique</span></span>  <br/> |<span data-ttu-id="a3237-118">這是強加頻寬上限的來源。</span><span class="sxs-lookup"><span data-stu-id="a3237-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="a3237-119">它描述頻寬限制的來源（例如，「原則伺服器」、「轉換伺服器」或「模態」）。</span><span class="sxs-lookup"><span data-stu-id="a3237-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

