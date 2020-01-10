---
title: Start-CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 01b62253-2aaf-43ed-9d63-804e31edc522
description: CcLogging Cmdlet 會針對商務用 Skype 雲端連接器 Edition 裝置產生呼入和呼出通話記錄。
ms.openlocfilehash: 2064fa4efd730812b5073821784ff5c524056341
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003173"
---
# <a name="start-cclogging"></a><span data-ttu-id="4d190-103">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="4d190-103">Start-CcLogging</span></span>
 
<span data-ttu-id="4d190-104">CcLogging Cmdlet 會針對商務用 Skype 雲端連接器 Edition 裝置產生呼入和呼出通話記錄。</span><span class="sxs-lookup"><span data-stu-id="4d190-104">The Start-CcLogging cmdlet generates the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span> 
  
```powershell
Start-CcLogging
```

## <a name="parameters"></a><span data-ttu-id="4d190-105">參數</span><span class="sxs-lookup"><span data-stu-id="4d190-105">Parameters</span></span>

<span data-ttu-id="4d190-106">無</span><span class="sxs-lookup"><span data-stu-id="4d190-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="4d190-107">範例</span><span class="sxs-lookup"><span data-stu-id="4d190-107">Examples</span></span>
<span data-ttu-id="4d190-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4d190-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="4d190-109">範例 1</span><span class="sxs-lookup"><span data-stu-id="4d190-109">Example 1</span></span>

<span data-ttu-id="4d190-110">下列範例會產生呼入和呼出通話記錄檔：</span><span class="sxs-lookup"><span data-stu-id="4d190-110">The following example generates the incoming and outgoing call log:</span></span>
  
```powershell
Start-CcLogging
```

## <a name="detailed-description"></a><span data-ttu-id="4d190-111">詳細描述</span><span class="sxs-lookup"><span data-stu-id="4d190-111">Detailed Description</span></span>
<span data-ttu-id="4d190-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4d190-112"></span></span>

<span data-ttu-id="4d190-113">CcLogging Cmdlet 提供一種方式，讓管理員在雲端連接器裝置上開始記錄來電和撥出通話。</span><span class="sxs-lookup"><span data-stu-id="4d190-113">The Start-CcLogging cmdlet provides a way for administrators to begin logging incoming and outgoing calls on a Cloud Connector appliance.</span></span> <span data-ttu-id="4d190-114">根據預設，記錄會在四個小時後自動停止。</span><span class="sxs-lookup"><span data-stu-id="4d190-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="4d190-115">輸入類型</span><span class="sxs-lookup"><span data-stu-id="4d190-115">Input Types</span></span>
<span data-ttu-id="4d190-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4d190-116"></span></span>

<span data-ttu-id="4d190-117">無。</span><span class="sxs-lookup"><span data-stu-id="4d190-117">None.</span></span> <span data-ttu-id="4d190-118">Start-CcLogging Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="4d190-118">The Start-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="4d190-119">傳回類型</span><span class="sxs-lookup"><span data-stu-id="4d190-119">Return Types</span></span>
<span data-ttu-id="4d190-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4d190-120"></span></span>

<span data-ttu-id="4d190-121">無</span><span class="sxs-lookup"><span data-stu-id="4d190-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4d190-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4d190-122">See also</span></span>
<span data-ttu-id="4d190-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4d190-123"></span></span>

[<span data-ttu-id="4d190-124">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="4d190-124">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="4d190-125">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="4d190-125">Stop-CcLogging</span></span>](stop-cclogging.md)
  

