---
title: 商務用 Skype Server 2015 中的 ConferenceJoinTimeThresholds 表格
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
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: ConferenceJoinTimeThresholds 表格中包含「會議加入時間摘要報告」所使用的分類界限。「會議加入時間摘要報告」摘要說明了使用者成功加入會議所需的時間；在報告中這些時間值會以平均值及下列其中一項類別表示：
ms.openlocfilehash: dfa7293307376b5fb5c86cec6f7504d363b005f5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813303"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="820b3-104">商務用 Skype Server 2015 中的 ConferenceJoinTimeThresholds 表格</span><span class="sxs-lookup"><span data-stu-id="820b3-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="820b3-p102">ConferenceJoinTimeThresholds 表格中包含「會議加入時間摘要報告」所使用的分類界限。「會議加入時間摘要報告」摘要說明了使用者成功加入會議所需的時間；在報告中這些時間值會以平均值及下列其中一項類別表示：</span><span class="sxs-lookup"><span data-stu-id="820b3-p102">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report. The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="820b3-107">少於 2 秒。</span><span class="sxs-lookup"><span data-stu-id="820b3-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="820b3-108">介於 2 秒和 5 秒之間。</span><span class="sxs-lookup"><span data-stu-id="820b3-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="820b3-109">介於 5 秒和 10 秒之間。</span><span class="sxs-lookup"><span data-stu-id="820b3-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="820b3-110">超過 10 秒。</span><span class="sxs-lookup"><span data-stu-id="820b3-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="820b3-111">ConferenceJoinTimeThresholds 表格包含 2 秒、5 秒及 10 秒的分類值。</span><span class="sxs-lookup"><span data-stu-id="820b3-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="820b3-112">此表格已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="820b3-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="820b3-113">**欄**</span><span class="sxs-lookup"><span data-stu-id="820b3-113">**Column**</span></span>|<span data-ttu-id="820b3-114">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="820b3-114">**Data Type**</span></span>|<span data-ttu-id="820b3-115">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="820b3-115">**Key/Index**</span></span>|<span data-ttu-id="820b3-116">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="820b3-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="820b3-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="820b3-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="820b3-118">int</span><span class="sxs-lookup"><span data-stu-id="820b3-118">int</span></span>  <br/> |<span data-ttu-id="820b3-119">主要</span><span class="sxs-lookup"><span data-stu-id="820b3-119">Primary</span></span>  <br/> |<span data-ttu-id="820b3-120">分類的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="820b3-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="820b3-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="820b3-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="820b3-122">int</span><span class="sxs-lookup"><span data-stu-id="820b3-122">int</span></span>  <br/> || <span data-ttu-id="820b3-p103">分類的上限。允許的值為：</span><span class="sxs-lookup"><span data-stu-id="820b3-p103">Upper limit for the classification. Allowed values are:</span></span> <br/>  <span data-ttu-id="820b3-125">2 </span><span class="sxs-lookup"><span data-stu-id="820b3-125">2</span></span> <br/>  <span data-ttu-id="820b3-126">5 </span><span class="sxs-lookup"><span data-stu-id="820b3-126">5</span></span> <br/>  <span data-ttu-id="820b3-127">10 </span><span class="sxs-lookup"><span data-stu-id="820b3-127">10</span></span> <br/> |
   

