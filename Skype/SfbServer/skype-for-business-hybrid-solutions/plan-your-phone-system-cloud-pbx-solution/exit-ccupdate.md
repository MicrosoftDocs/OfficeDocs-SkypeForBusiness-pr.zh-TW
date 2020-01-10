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
ms.openlocfilehash: f79023c50e951e6678abdccc29b12cb30a329dfc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003443"
---
# <a name="exit-ccupdate"></a><span data-ttu-id="8c9a5-103">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="8c9a5-103">Exit-CcUpdate</span></span>
 
<span data-ttu-id="8c9a5-104">CcUpdate Cmdlet 會在商務用 Skype 雲端連接器 Edition 主機伺服器上退出更新維護模式。</span><span class="sxs-lookup"><span data-stu-id="8c9a5-104">The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
<span data-ttu-id="8c9a5-105">此 Cmdlet 適用于商務用 Skype 雲端連接器 Edition 1.4.1，1.4.2。</span><span class="sxs-lookup"><span data-stu-id="8c9a5-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span> 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="8c9a5-106">參數</span><span class="sxs-lookup"><span data-stu-id="8c9a5-106">Parameters</span></span>

<span data-ttu-id="8c9a5-107">無</span><span class="sxs-lookup"><span data-stu-id="8c9a5-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="8c9a5-108">範例</span><span class="sxs-lookup"><span data-stu-id="8c9a5-108">Examples</span></span>
<span data-ttu-id="8c9a5-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="8c9a5-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="8c9a5-110">範例 1</span><span class="sxs-lookup"><span data-stu-id="8c9a5-110">Example 1</span></span>

<span data-ttu-id="8c9a5-111">下列命令會將它執行的裝置放回生產模式：</span><span class="sxs-lookup"><span data-stu-id="8c9a5-111">The following command puts the appliance on which it runs back into production mode:</span></span> 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a><span data-ttu-id="8c9a5-112">詳細描述</span><span class="sxs-lookup"><span data-stu-id="8c9a5-112">Detailed Description</span></span>
<span data-ttu-id="8c9a5-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8c9a5-113"></span></span>

<span data-ttu-id="8c9a5-114">如果您的裝置是透過指定 CcUpdate Cmdlet 進入維護模式，則 CcUpdate Cmdlet 會將這些裝置放回生產模式。</span><span class="sxs-lookup"><span data-stu-id="8c9a5-114">If you have appliances that you have put in maintenance mode by specifying the Enter-CcUpdate cmdlet, the Exit-CcUpdate cmdlet will put these back into production mode.</span></span> 
  
<span data-ttu-id="8c9a5-115">如需將裝置置於維護模式的詳細資訊，請參閱 Enter-CcUpdate。</span><span class="sxs-lookup"><span data-stu-id="8c9a5-115">For more information about putting appliances in maintenance mode, see Enter-CcUpdate.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="8c9a5-116">輸入類型</span><span class="sxs-lookup"><span data-stu-id="8c9a5-116">Input Types</span></span>
<span data-ttu-id="8c9a5-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8c9a5-117"></span></span>

<span data-ttu-id="8c9a5-118">無。</span><span class="sxs-lookup"><span data-stu-id="8c9a5-118">None.</span></span> <span data-ttu-id="8c9a5-119">Exit CcUpdate Cmdlet 不接受流水線輸入。</span><span class="sxs-lookup"><span data-stu-id="8c9a5-119">The Exit-CcUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="8c9a5-120">傳回類型</span><span class="sxs-lookup"><span data-stu-id="8c9a5-120">Return Types</span></span>
<span data-ttu-id="8c9a5-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8c9a5-121"></span></span>

<span data-ttu-id="8c9a5-122">無</span><span class="sxs-lookup"><span data-stu-id="8c9a5-122">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8c9a5-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8c9a5-123">See also</span></span>
<span data-ttu-id="8c9a5-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8c9a5-124"></span></span>

[<span data-ttu-id="8c9a5-125">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="8c9a5-125">Enter-CcUpdate</span></span>](enter-ccupdate.md)
  

