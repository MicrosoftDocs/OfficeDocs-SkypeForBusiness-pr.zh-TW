---
title: 商務用 Skype Server 2015 中的 IMReportSummary 表格
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
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable 會提供組織中的立即訊息會話的整體報告。 此表格是在 Microsoft Lync Server 2013 中推出。
ms.openlocfilehash: f845a882bb8bd6ba5ca434ffc42a34725cfeac51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815141"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="2d6a7-104">商務用 Skype Server 2015 中的 IMReportSummary 表格</span><span class="sxs-lookup"><span data-stu-id="2d6a7-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2d6a7-105">IMReportSummaryTable 會提供組織中的立即訊息會話的整體報告。</span><span class="sxs-lookup"><span data-stu-id="2d6a7-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="2d6a7-106">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="2d6a7-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="2d6a7-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="2d6a7-107">**Column**</span></span>|<span data-ttu-id="2d6a7-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="2d6a7-108">**Data Type**</span></span>|<span data-ttu-id="2d6a7-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="2d6a7-109">**Key/Index**</span></span>|<span data-ttu-id="2d6a7-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="2d6a7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2d6a7-111">**開始**</span><span class="sxs-lookup"><span data-stu-id="2d6a7-111">**StartTime**</span></span> <br/> |<span data-ttu-id="2d6a7-112">datetime</span><span class="sxs-lookup"><span data-stu-id="2d6a7-112">datetime</span></span>  <br/> |<span data-ttu-id="2d6a7-113">首選</span><span class="sxs-lookup"><span data-stu-id="2d6a7-113">Primary</span></span>  <br/> |<span data-ttu-id="2d6a7-114">立即訊息會話開始的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="2d6a7-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="2d6a7-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="2d6a7-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="2d6a7-116">char （1）</span><span class="sxs-lookup"><span data-stu-id="2d6a7-116">char(1)</span></span>  <br/> |<span data-ttu-id="2d6a7-117">首選</span><span class="sxs-lookup"><span data-stu-id="2d6a7-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="2d6a7-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="2d6a7-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="2d6a7-119">Nvarchar （257）</span><span class="sxs-lookup"><span data-stu-id="2d6a7-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="2d6a7-120">首選</span><span class="sxs-lookup"><span data-stu-id="2d6a7-120">Primary</span></span>  <br/> |<span data-ttu-id="2d6a7-121">主持會話之池的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="2d6a7-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="2d6a7-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="2d6a7-122">**AuthType**</span></span> <br/> |<span data-ttu-id="2d6a7-123">int</span><span class="sxs-lookup"><span data-stu-id="2d6a7-123">int</span></span>  <br/> |<span data-ttu-id="2d6a7-124">首選</span><span class="sxs-lookup"><span data-stu-id="2d6a7-124">Primary</span></span>  <br/> |<span data-ttu-id="2d6a7-125">通話的優先順序（例如，緊急或非緊急）。</span><span class="sxs-lookup"><span data-stu-id="2d6a7-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="2d6a7-126">優先順序資訊會儲存在[商務用 Skype Server 2015 的 CallPriorities 表格](callpriorities.md)中。</span><span class="sxs-lookup"><span data-stu-id="2d6a7-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="2d6a7-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="2d6a7-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="2d6a7-128">Bigint</span><span class="sxs-lookup"><span data-stu-id="2d6a7-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="2d6a7-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="2d6a7-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="2d6a7-130">Bigint</span><span class="sxs-lookup"><span data-stu-id="2d6a7-130">bigint</span></span>  <br/> ||<span data-ttu-id="2d6a7-131">會話期間交換的立即訊息總數。</span><span class="sxs-lookup"><span data-stu-id="2d6a7-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

