---
title: Stop-CcLogging
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
ms.openlocfilehash: 4528f7c1458093874f59f347585a736666a9ea08
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003163"
---
# <a name="stop-cclogging"></a><span data-ttu-id="c20be-103">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="c20be-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="c20be-104">Stop-CcLogging Cmdlet 會停止為商務用 Skype 雲端連接器 Edition 裝置產生來電記錄和呼出通話記錄。</span><span class="sxs-lookup"><span data-stu-id="c20be-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="c20be-105">範例</span><span class="sxs-lookup"><span data-stu-id="c20be-105">Examples</span></span>
<span data-ttu-id="c20be-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="c20be-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="c20be-107">範例 1</span><span class="sxs-lookup"><span data-stu-id="c20be-107">Example 1</span></span>

<span data-ttu-id="c20be-108">下列範例會停止產生來電記錄和撥出通話記錄檔：</span><span class="sxs-lookup"><span data-stu-id="c20be-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="c20be-109">範例 2</span><span class="sxs-lookup"><span data-stu-id="c20be-109">Example 2</span></span>

<span data-ttu-id="c20be-110">下一個範例會停止產生來電記錄和撥出通話記錄，並清除快取檔案：</span><span class="sxs-lookup"><span data-stu-id="c20be-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="c20be-111">詳細描述</span><span class="sxs-lookup"><span data-stu-id="c20be-111">Detailed Description</span></span>
<span data-ttu-id="c20be-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c20be-112"></span></span>

<span data-ttu-id="c20be-113">CcLogging Cmdlet 會停止記錄裝置上的撥入和撥出通話。</span><span class="sxs-lookup"><span data-stu-id="c20be-113">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance.</span></span> <span data-ttu-id="c20be-114">根據預設，記錄會在四個小時後自動停止。</span><span class="sxs-lookup"><span data-stu-id="c20be-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="c20be-115">參數</span><span class="sxs-lookup"><span data-stu-id="c20be-115">Parameters</span></span>
<span data-ttu-id="c20be-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="c20be-116"></span></span>

|<span data-ttu-id="c20be-117">**參數**</span><span class="sxs-lookup"><span data-stu-id="c20be-117">**Parameter**</span></span>|<span data-ttu-id="c20be-118">**必要**</span><span class="sxs-lookup"><span data-stu-id="c20be-118">**Required**</span></span>|<span data-ttu-id="c20be-119">**類型**</span><span class="sxs-lookup"><span data-stu-id="c20be-119">**Type**</span></span>|<span data-ttu-id="c20be-120">**描述**</span><span class="sxs-lookup"><span data-stu-id="c20be-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="c20be-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="c20be-121">RemoveCache</span></span> <br/> | <span data-ttu-id="c20be-122">選用</span><span class="sxs-lookup"><span data-stu-id="c20be-122">Optional</span></span> <br/> | <span data-ttu-id="c20be-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="c20be-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="c20be-124">移除記錄緩衝檔案。</span><span class="sxs-lookup"><span data-stu-id="c20be-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="c20be-125">輸入類型</span><span class="sxs-lookup"><span data-stu-id="c20be-125">Input Types</span></span>
<span data-ttu-id="c20be-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c20be-126"></span></span>

<span data-ttu-id="c20be-127">無。</span><span class="sxs-lookup"><span data-stu-id="c20be-127">None.</span></span> <span data-ttu-id="c20be-128">CcLogging Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="c20be-128">The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="c20be-129">傳回類型</span><span class="sxs-lookup"><span data-stu-id="c20be-129">Return Types</span></span>
<span data-ttu-id="c20be-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c20be-130"></span></span>

<span data-ttu-id="c20be-131">無</span><span class="sxs-lookup"><span data-stu-id="c20be-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c20be-132">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c20be-132">See also</span></span>
<span data-ttu-id="c20be-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="c20be-133"></span></span>

[<span data-ttu-id="c20be-134">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="c20be-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="c20be-135">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="c20be-135">Start-CcLogging</span></span>](start-cclogging.md)
  

