---
title: SessionCorrelation 表格
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
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation 資料表是支援資料表。 每筆記錄代表一個 CorrelationID，用於關聯多個會話。
ms.openlocfilehash: cd9f477ad71b836fb204aab651aceb7bbb5832f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805741"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="f08a4-104">SessionCorrelation 表格</span><span class="sxs-lookup"><span data-stu-id="f08a4-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="f08a4-105">SessionCorrelation 資料表是支援資料表。</span><span class="sxs-lookup"><span data-stu-id="f08a4-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="f08a4-106">每筆記錄代表一個 CorrelationID，用於關聯多個會話。</span><span class="sxs-lookup"><span data-stu-id="f08a4-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="f08a4-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="f08a4-107">**Column**</span></span>|<span data-ttu-id="f08a4-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="f08a4-108">**Data Type**</span></span>|<span data-ttu-id="f08a4-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="f08a4-109">**Key/Index**</span></span>|<span data-ttu-id="f08a4-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="f08a4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f08a4-111">**求和**</span><span class="sxs-lookup"><span data-stu-id="f08a4-111">**Checksum**</span></span> <br/> |<span data-ttu-id="f08a4-112">int</span><span class="sxs-lookup"><span data-stu-id="f08a4-112">int</span></span>  <br/> |||
|<span data-ttu-id="f08a4-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="f08a4-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="f08a4-114">int</span><span class="sxs-lookup"><span data-stu-id="f08a4-114">int</span></span>  <br/> |<span data-ttu-id="f08a4-115">首選</span><span class="sxs-lookup"><span data-stu-id="f08a4-115">Primary</span></span>  <br/> |<span data-ttu-id="f08a4-116">識別這個 A/V 會議伺服器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="f08a4-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="f08a4-117">**Id**</span><span class="sxs-lookup"><span data-stu-id="f08a4-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="f08a4-118">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="f08a4-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="f08a4-119">唯一</span><span class="sxs-lookup"><span data-stu-id="f08a4-119">Unique</span></span>  <br/> |<span data-ttu-id="f08a4-120">關聯的會話將具有相同的關聯 ID。</span><span class="sxs-lookup"><span data-stu-id="f08a4-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="f08a4-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="f08a4-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="f08a4-122">datetime</span><span class="sxs-lookup"><span data-stu-id="f08a4-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="f08a4-123">僅供內部使用。</span><span class="sxs-lookup"><span data-stu-id="f08a4-123">For internal use only.</span></span>  <br/> |
   

