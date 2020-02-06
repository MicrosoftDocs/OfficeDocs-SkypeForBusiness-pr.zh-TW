---
title: 從集區中移除前端伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 前端伺服器不能以獨立電腦的形式存在。 它必須定義為前端池，即使池中只有一個電腦。
ms.openlocfilehash: 93df9e293f7a1876d4a8b1f172472f708556f67f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813031"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="59442-104">從集區中移除前端伺服器</span><span class="sxs-lookup"><span data-stu-id="59442-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="59442-105">前端伺服器不能以獨立電腦的形式存在。</span><span class="sxs-lookup"><span data-stu-id="59442-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="59442-106">它必須定義為前端池，即使池中只有一個電腦。</span><span class="sxs-lookup"><span data-stu-id="59442-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="59442-107">本主題將引導您完成從現有的前端池移除個別前端伺服器的程式。</span><span class="sxs-lookup"><span data-stu-id="59442-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="59442-108">如果前端伺服器是池中的最後一個伺服器，或如果您要徹底移除該資源池，請參閱[移除前端池或標準版伺服器](remove-front-end-pool-or-standard-edition-server.md)。</span><span class="sxs-lookup"><span data-stu-id="59442-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="59442-109">移除前端池前，不需要移除個別的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="59442-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="59442-110">移除該池後，就會移除每個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="59442-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="59442-111">從池中移除前端伺服器</span><span class="sxs-lookup"><span data-stu-id="59442-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="59442-112">在商務用 Skype Server 2019 前端伺服器上，開啟拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="59442-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="59442-113">流覽至舊版 [安裝] 節點。</span><span class="sxs-lookup"><span data-stu-id="59442-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="59442-114">展開 [**企業版前端池**]，展開要移除之前端伺服器的 [前端] 池，以滑鼠右鍵按一下您要移除的前端伺服器，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="59442-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

