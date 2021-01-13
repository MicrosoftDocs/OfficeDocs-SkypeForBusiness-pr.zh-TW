---
title: 商務用 Skype Server 2015 中的 IMReportSummary 表格
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
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable 會提供組織中保留之立即訊息工作階段的整體報告。 此表格已引進 Microsoft Lync Server 2013。
ms.openlocfilehash: 6a80918376440c13d60e059744d88c09c2705853
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821523"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="8db37-104">商務用 Skype Server 2015 中的 IMReportSummary 表格</span><span class="sxs-lookup"><span data-stu-id="8db37-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8db37-105">IMReportSummaryTable 會提供組織中保留之立即訊息工作階段的整體報告。</span><span class="sxs-lookup"><span data-stu-id="8db37-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="8db37-106">此表格已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="8db37-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="8db37-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="8db37-107">**Column**</span></span>|<span data-ttu-id="8db37-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="8db37-108">**Data Type**</span></span>|<span data-ttu-id="8db37-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="8db37-109">**Key/Index**</span></span>|<span data-ttu-id="8db37-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="8db37-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8db37-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="8db37-111">**StartTime**</span></span> <br/> |<span data-ttu-id="8db37-112">datetime</span><span class="sxs-lookup"><span data-stu-id="8db37-112">datetime</span></span>  <br/> |<span data-ttu-id="8db37-113">主要</span><span class="sxs-lookup"><span data-stu-id="8db37-113">Primary</span></span>  <br/> |<span data-ttu-id="8db37-114">立即訊息工作階段開始的日期及時間。</span><span class="sxs-lookup"><span data-stu-id="8db37-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="8db37-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="8db37-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="8db37-116">char (1) </span><span class="sxs-lookup"><span data-stu-id="8db37-116">char(1)</span></span>  <br/> |<span data-ttu-id="8db37-117">主要</span><span class="sxs-lookup"><span data-stu-id="8db37-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="8db37-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="8db37-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="8db37-119">Nvarchar (257) </span><span class="sxs-lookup"><span data-stu-id="8db37-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="8db37-120">主要</span><span class="sxs-lookup"><span data-stu-id="8db37-120">Primary</span></span>  <br/> |<span data-ttu-id="8db37-121">裝載此工作階段之集區的完整網域名稱。</span><span class="sxs-lookup"><span data-stu-id="8db37-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="8db37-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="8db37-122">**AuthType**</span></span> <br/> |<span data-ttu-id="8db37-123">int</span><span class="sxs-lookup"><span data-stu-id="8db37-123">int</span></span>  <br/> |<span data-ttu-id="8db37-124">主要</span><span class="sxs-lookup"><span data-stu-id="8db37-124">Primary</span></span>  <br/> |<span data-ttu-id="8db37-125">電話的優先順序 (例如，緊急或非緊急)。</span><span class="sxs-lookup"><span data-stu-id="8db37-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="8db37-126">優先順序資訊會儲存在 [商務用 Skype Server 2015 的 CallPriorities 表格](callpriorities.md)中。</span><span class="sxs-lookup"><span data-stu-id="8db37-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="8db37-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="8db37-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="8db37-128">Bigint</span><span class="sxs-lookup"><span data-stu-id="8db37-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="8db37-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="8db37-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="8db37-130">Bigint</span><span class="sxs-lookup"><span data-stu-id="8db37-130">bigint</span></span>  <br/> ||<span data-ttu-id="8db37-131">工作階段期間交換的立即訊息總數。</span><span class="sxs-lookup"><span data-stu-id="8db37-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

