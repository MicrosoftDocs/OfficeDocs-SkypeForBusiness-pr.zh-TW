---
title: 從集區中移除前端伺服器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 前端伺服器不能以獨立電腦形式存在。 它必須定義為前端集區，即使集區中只有一部電腦也一樣。
ms.openlocfilehash: 7675ba119fa2937d765d5f4e497fca0a040b3b62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752315"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="b9bee-104">從集區中移除前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b9bee-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="b9bee-105">前端伺服器不能以獨立電腦形式存在。</span><span class="sxs-lookup"><span data-stu-id="b9bee-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="b9bee-106">它必須定義為前端集區，即使集區中只有一部電腦也一樣。</span><span class="sxs-lookup"><span data-stu-id="b9bee-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="b9bee-107">本主題將引導您完成從現有前端集區移除個別前端伺服器的程式。</span><span class="sxs-lookup"><span data-stu-id="b9bee-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="b9bee-108">如果前端伺服器是集區中的最後一部伺服器，或您要完全移除集區，請參閱[移除前端集區或 Standard Edition Server](remove-front-end-pool-or-standard-edition-server.md)。</span><span class="sxs-lookup"><span data-stu-id="b9bee-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="b9bee-109">移除前端集區之前，不需要先移除個別的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="b9bee-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="b9bee-110">當您移除集區時，會移除每個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="b9bee-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="b9bee-111">從集區移除前端伺服器</span><span class="sxs-lookup"><span data-stu-id="b9bee-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="b9bee-112">在商務用 Skype Server 2019 前端伺服器上，開啟拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="b9bee-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="b9bee-113">流覽至 [舊版安裝] 節點。</span><span class="sxs-lookup"><span data-stu-id="b9bee-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="b9bee-114">展開 [ **Enterprise Edition 前端**集區]，展開要移除前端伺服器的前端集區，以滑鼠右鍵按一下您要移除的前端伺服器，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="b9bee-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

