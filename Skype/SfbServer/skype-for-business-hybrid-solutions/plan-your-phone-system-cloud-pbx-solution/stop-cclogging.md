---
title: 停止 CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Stop-CcLogging Cmdlet 會停止為商務用 Skype 雲端連接器 Edition 裝置產生來電記錄和呼出通話記錄。
ms.openlocfilehash: dcc62e8ec772912a8275f5321a6c91e28dde8c25
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190615"
---
# <a name="stop-cclogging"></a><span data-ttu-id="8a1a4-103">停止 CcLogging</span><span class="sxs-lookup"><span data-stu-id="8a1a4-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="8a1a4-104">Stop-CcLogging Cmdlet 會停止為商務用 Skype 雲端連接器 Edition 裝置產生來電記錄和呼出通話記錄。</span><span class="sxs-lookup"><span data-stu-id="8a1a4-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="8a1a4-105">範例</span><span class="sxs-lookup"><span data-stu-id="8a1a4-105">Examples</span></span>
<span data-ttu-id="8a1a4-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="8a1a4-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="8a1a4-107">範例 1</span><span class="sxs-lookup"><span data-stu-id="8a1a4-107">Example 1</span></span>

<span data-ttu-id="8a1a4-108">下列範例會停止產生來電記錄和撥出通話記錄檔:</span><span class="sxs-lookup"><span data-stu-id="8a1a4-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="8a1a4-109">範例 2</span><span class="sxs-lookup"><span data-stu-id="8a1a4-109">Example 2</span></span>

<span data-ttu-id="8a1a4-110">下一個範例會停止產生來電記錄和撥出通話記錄, 並清除快取檔案:</span><span class="sxs-lookup"><span data-stu-id="8a1a4-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="8a1a4-111">詳細描述</span><span class="sxs-lookup"><span data-stu-id="8a1a4-111">Detailed Description</span></span>
<span data-ttu-id="8a1a4-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8a1a4-112"></span></span>

<span data-ttu-id="8a1a4-113">CcLogging Cmdlet 會停止記錄裝置上的撥入和撥出通話。</span><span class="sxs-lookup"><span data-stu-id="8a1a4-113">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance.</span></span> <span data-ttu-id="8a1a4-114">根據預設, 記錄會在四個小時後自動停止。</span><span class="sxs-lookup"><span data-stu-id="8a1a4-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="8a1a4-115">參數</span><span class="sxs-lookup"><span data-stu-id="8a1a4-115">Parameters</span></span>
<span data-ttu-id="8a1a4-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8a1a4-116"></span></span>

|<span data-ttu-id="8a1a4-117">**參數**</span><span class="sxs-lookup"><span data-stu-id="8a1a4-117">**Parameter**</span></span>|<span data-ttu-id="8a1a4-118">**必要**</span><span class="sxs-lookup"><span data-stu-id="8a1a4-118">**Required**</span></span>|<span data-ttu-id="8a1a4-119">**類型**</span><span class="sxs-lookup"><span data-stu-id="8a1a4-119">**Type**</span></span>|<span data-ttu-id="8a1a4-120">**說明**</span><span class="sxs-lookup"><span data-stu-id="8a1a4-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="8a1a4-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="8a1a4-121">RemoveCache</span></span> <br/> | <span data-ttu-id="8a1a4-122">選用</span><span class="sxs-lookup"><span data-stu-id="8a1a4-122">Optional</span></span> <br/> | <span data-ttu-id="8a1a4-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="8a1a4-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="8a1a4-124">移除記錄緩衝檔案。</span><span class="sxs-lookup"><span data-stu-id="8a1a4-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="8a1a4-125">輸入類型</span><span class="sxs-lookup"><span data-stu-id="8a1a4-125">Input Types</span></span>
<span data-ttu-id="8a1a4-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8a1a4-126"></span></span>

<span data-ttu-id="8a1a4-127">無。</span><span class="sxs-lookup"><span data-stu-id="8a1a4-127">None.</span></span> <span data-ttu-id="8a1a4-128">CcLogging Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="8a1a4-128">The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="8a1a4-129">傳回類型</span><span class="sxs-lookup"><span data-stu-id="8a1a4-129">Return Types</span></span>
<span data-ttu-id="8a1a4-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8a1a4-130"></span></span>

<span data-ttu-id="8a1a4-131">無</span><span class="sxs-lookup"><span data-stu-id="8a1a4-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8a1a4-132">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8a1a4-132">See also</span></span>
<span data-ttu-id="8a1a4-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8a1a4-133"></span></span>

[<span data-ttu-id="8a1a4-134">搜尋-CcLog</span><span class="sxs-lookup"><span data-stu-id="8a1a4-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="8a1a4-135">開始-CcLogging</span><span class="sxs-lookup"><span data-stu-id="8a1a4-135">Start-CcLogging</span></span>](start-cclogging.md)
  

