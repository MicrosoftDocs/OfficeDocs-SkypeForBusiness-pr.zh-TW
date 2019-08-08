---
title: 遷移多個網站和池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '商務用 Skype Server 2019 支援多網站和多池部署。 將多個池遷移到商務用 Skype Server 2019 的程式需要下列考慮:'
ms.openlocfilehash: e2577b6af1430be90e30fff3236d7ea3cf473cd5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238464"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="1adfc-104">遷移多個網站和池</span><span class="sxs-lookup"><span data-stu-id="1adfc-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="1adfc-105">商務用 Skype Server 2019 支援多網站和多池部署。</span><span class="sxs-lookup"><span data-stu-id="1adfc-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="1adfc-106">將多個池遷移到商務用 Skype Server 2019 的程式需要下列考慮:</span><span class="sxs-lookup"><span data-stu-id="1adfc-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="1adfc-107">在部署商務用 Skype Server 2019 試生產池之後, 您必須定義將移至商務用 Skype Server 2019 池的試驗使用者子集, 以及驗證使用者功能的方法。</span><span class="sxs-lookup"><span data-stu-id="1adfc-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="1adfc-108">例如, 將使用者移至 [試驗] 池之後, 請確認使用者的會議原則已移至 [商務用 Skype Server 2019]。</span><span class="sxs-lookup"><span data-stu-id="1adfc-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="1adfc-109">在試驗池中部署邊緣伺服器之後, 您必須確認外部使用者可以與商務用 Skype Server 2019 池通訊。</span><span class="sxs-lookup"><span data-stu-id="1adfc-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="1adfc-110">在商務用 Skype server 2019 中, 持續式聊天、SQL 鏡像及 XMPP 功能已棄用, 且不再以商務用 Skype Server 2019 功能提供, 但在共存環境中, 如果它們先前部署在舊版環境。</span><span class="sxs-lookup"><span data-stu-id="1adfc-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="1adfc-111">如果您想要繼續使用這些功能, 您應該規劃繼續共存環境, 讓特定使用者保留在舊版池中。</span><span class="sxs-lookup"><span data-stu-id="1adfc-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="1adfc-112">將同盟路由的邊緣伺服器轉換為試點商務用 Skype Server 2019 Edge 伺服器之後, 您必須確認聯盟使用者可以與商務用 Skype Server 2019 池通訊。</span><span class="sxs-lookup"><span data-stu-id="1adfc-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="1adfc-113">移動所有使用者和非使用者連絡人物件之後, 您必須驗證舊版池是否為空白。</span><span class="sxs-lookup"><span data-stu-id="1adfc-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="1adfc-114">在驗證舊版池為空白之後, 您可以將該池停用。</span><span class="sxs-lookup"><span data-stu-id="1adfc-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="1adfc-115">如需如何停用舊版池和伺服器的詳細資料, 請參閱[階段 8: 解除舊版池](phase-8-decommission-legacy-pools.md)。</span><span class="sxs-lookup"><span data-stu-id="1adfc-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

