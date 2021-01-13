---
title: SessionCorrelation 表格
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
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation 表格是支援的表格。 每筆記錄代表一個用於關聯多個會話的 CorrelationID。
ms.openlocfilehash: 36b617517f3642a2150c72369db858eee62a4a87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802653"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="a78c5-104">SessionCorrelation 表格</span><span class="sxs-lookup"><span data-stu-id="a78c5-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="a78c5-105">SessionCorrelation 表格是支援的表格。</span><span class="sxs-lookup"><span data-stu-id="a78c5-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="a78c5-106">每筆記錄代表一個用於關聯多個會話的 CorrelationID。</span><span class="sxs-lookup"><span data-stu-id="a78c5-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="a78c5-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="a78c5-107">**Column**</span></span>|<span data-ttu-id="a78c5-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="a78c5-108">**Data Type**</span></span>|<span data-ttu-id="a78c5-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="a78c5-109">**Key/Index**</span></span>|<span data-ttu-id="a78c5-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="a78c5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a78c5-111">**校驗**</span><span class="sxs-lookup"><span data-stu-id="a78c5-111">**Checksum**</span></span> <br/> |<span data-ttu-id="a78c5-112">int</span><span class="sxs-lookup"><span data-stu-id="a78c5-112">int</span></span>  <br/> |||
|<span data-ttu-id="a78c5-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="a78c5-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="a78c5-114">int</span><span class="sxs-lookup"><span data-stu-id="a78c5-114">int</span></span>  <br/> |<span data-ttu-id="a78c5-115">主要</span><span class="sxs-lookup"><span data-stu-id="a78c5-115">Primary</span></span>  <br/> |<span data-ttu-id="a78c5-116">用於識別此 A/V 會議伺服器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="a78c5-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="a78c5-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="a78c5-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="a78c5-118">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="a78c5-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a78c5-119">Unique</span><span class="sxs-lookup"><span data-stu-id="a78c5-119">Unique</span></span>  <br/> |<span data-ttu-id="a78c5-120">關聯的會話會有相同的相互關聯識別碼。</span><span class="sxs-lookup"><span data-stu-id="a78c5-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="a78c5-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="a78c5-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="a78c5-122">datetime</span><span class="sxs-lookup"><span data-stu-id="a78c5-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="a78c5-123">僅限內部使用。</span><span class="sxs-lookup"><span data-stu-id="a78c5-123">For internal use only.</span></span>  <br/> |
   

