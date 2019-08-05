---
title: Exit-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: CcUpdate Cmdlet 會在商務用 Skype 雲端連接器 Edition 主機伺服器上退出更新維護模式。
ms.openlocfilehash: b3558a81e1d4bc6c833cca157c2b31f2f252b595
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190828"
---
# <a name="exit-ccupdate"></a><span data-ttu-id="19ce8-103">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="19ce8-103">Exit-CcUpdate</span></span>
 
<span data-ttu-id="19ce8-104">CcUpdate Cmdlet 會在商務用 Skype 雲端連接器 Edition 主機伺服器上退出更新維護模式。</span><span class="sxs-lookup"><span data-stu-id="19ce8-104">The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
<span data-ttu-id="19ce8-105">此 Cmdlet 適用于商務用 Skype 雲端連接器 Edition 1.4.1, 1.4.2。</span><span class="sxs-lookup"><span data-stu-id="19ce8-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span> 
  
```
Exit-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="19ce8-106">參數</span><span class="sxs-lookup"><span data-stu-id="19ce8-106">Parameters</span></span>

<span data-ttu-id="19ce8-107">無</span><span class="sxs-lookup"><span data-stu-id="19ce8-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="19ce8-108">範例</span><span class="sxs-lookup"><span data-stu-id="19ce8-108">Examples</span></span>
<span data-ttu-id="19ce8-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="19ce8-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="19ce8-110">範例 1</span><span class="sxs-lookup"><span data-stu-id="19ce8-110">Example 1</span></span>

<span data-ttu-id="19ce8-111">下列命令會將它執行的裝置放回生產模式:</span><span class="sxs-lookup"><span data-stu-id="19ce8-111">The following command puts the appliance on which it runs back into production mode:</span></span> 
  
```
Exit-CcUpdate
```

## <a name="detailed-description"></a><span data-ttu-id="19ce8-112">詳細描述</span><span class="sxs-lookup"><span data-stu-id="19ce8-112">Detailed Description</span></span>
<span data-ttu-id="19ce8-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="19ce8-113"></span></span>

<span data-ttu-id="19ce8-114">如果您的裝置是透過指定 CcUpdate Cmdlet 進入維護模式, 則 CcUpdate Cmdlet 會將這些裝置放回生產模式。</span><span class="sxs-lookup"><span data-stu-id="19ce8-114">If you have appliances that you have put in maintenance mode by specifying the Enter-CcUpdate cmdlet, the Exit-CcUpdate cmdlet will put these back into production mode.</span></span> 
  
<span data-ttu-id="19ce8-115">如需將裝置置於維護模式的詳細資訊, 請參閱 Enter-CcUpdate。</span><span class="sxs-lookup"><span data-stu-id="19ce8-115">For more information about putting appliances in maintenance mode, see Enter-CcUpdate.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="19ce8-116">輸入類型</span><span class="sxs-lookup"><span data-stu-id="19ce8-116">Input Types</span></span>
<span data-ttu-id="19ce8-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="19ce8-117"></span></span>

<span data-ttu-id="19ce8-118">無。</span><span class="sxs-lookup"><span data-stu-id="19ce8-118">None.</span></span> <span data-ttu-id="19ce8-119">Exit CcUpdate Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="19ce8-119">The Exit-CcUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="19ce8-120">傳回類型</span><span class="sxs-lookup"><span data-stu-id="19ce8-120">Return Types</span></span>
<span data-ttu-id="19ce8-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="19ce8-121"></span></span>

<span data-ttu-id="19ce8-122">無</span><span class="sxs-lookup"><span data-stu-id="19ce8-122">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="19ce8-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="19ce8-123">See also</span></span>
<span data-ttu-id="19ce8-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="19ce8-124"></span></span>

[<span data-ttu-id="19ce8-125">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="19ce8-125">Enter-CcUpdate</span></span>](enter-ccupdate.md)
  

