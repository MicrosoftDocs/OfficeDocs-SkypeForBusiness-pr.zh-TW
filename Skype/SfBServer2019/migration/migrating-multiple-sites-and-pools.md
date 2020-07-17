---
title: 移轉多個網站與集區
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
description: 商務用 Skype Server 2019 支援多個網站和多個集區的部署。 將多個集區遷移至商務用 Skype Server 2019 的程式需要下列考慮：
ms.openlocfilehash: 4906b05138d546e685a06acecc4f7adc4e88516e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752655"
---
# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="c40d7-104">移轉多個網站與集區</span><span class="sxs-lookup"><span data-stu-id="c40d7-104">Migrating multiple sites and pools</span></span>

<span data-ttu-id="c40d7-105">商務用 Skype Server 2019 支援多個網站和多個集區的部署。</span><span class="sxs-lookup"><span data-stu-id="c40d7-105">Skype for Business Server 2019 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="c40d7-106">將多個集區遷移至商務用 Skype Server 2019 的程式需要下列考慮：</span><span class="sxs-lookup"><span data-stu-id="c40d7-106">The process of migrating multiple pools to Skype for Business Server 2019 requires the following considerations:</span></span> 
  
1. <span data-ttu-id="c40d7-107">部署商務用 Skype Server 2019 試驗集區之後，您必須定義將要移至商務用 Skype Server 2019 集區的試驗使用者子集，以及驗證使用者功能的方法。</span><span class="sxs-lookup"><span data-stu-id="c40d7-107">After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="c40d7-108">例如，將使用者移至試驗集區後，請確認使用者的會議原則已移至商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="c40d7-108">For example, after moving a user to the pilot pool, verify that the user's conference policy has moved to Skype for Business Server 2019.</span></span> 
    
2. <span data-ttu-id="c40d7-109">在試驗集區中部署 Edge Server 之後，您需要驗證外部使用者是否可以與商務用 Skype Server 2019 集區通訊。</span><span class="sxs-lookup"><span data-stu-id="c40d7-109">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.</span></span>

3. <span data-ttu-id="c40d7-110">在商務用 Skype Server 2019 中已被取代，且無法再以商務用 Skype Server 2019 的功能使用，但仍可在共存環境中使用，但如果這些功能先前是部署于舊版環境中，則可繼續進行。</span><span class="sxs-lookup"><span data-stu-id="c40d7-110">Persistent Chat, SQL Mirroring, and XMPP functionality are deprecated in Skype for Business Server 2019 and no longer available as Skype for Business Server 2019 features, but they can be continued in a coexistence environment if they were previously deployed in a legacy environment.</span></span> <span data-ttu-id="c40d7-111">如果您想要繼續使用這些功能，您應該計畫繼續共存環境，而某些使用者仍會保留在舊版集區中。</span><span class="sxs-lookup"><span data-stu-id="c40d7-111">If you want to continue using these features, you should plan to continue with a coexistence environment where certain users will remain in legacy pools.</span></span>
    
4. <span data-ttu-id="c40d7-112">將同盟路由的 Edge server 轉換至試驗商務用 Skype Server 2019 Edge server 之後，您需要驗證同盟使用者是否可以與商務用 Skype Server 2019 集區通訊。</span><span class="sxs-lookup"><span data-stu-id="c40d7-112">After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Servers, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="c40d7-113">移動所有使用者與非使用者的連絡人物件之後，您必須驗證舊版集區是否為空。</span><span class="sxs-lookup"><span data-stu-id="c40d7-113">After moving all users and non-user contact objects, you need to validate that the legacy pool is empty.</span></span>
    
6. <span data-ttu-id="c40d7-114">驗證舊版集區是空的之後，即可停用該集區。</span><span class="sxs-lookup"><span data-stu-id="c40d7-114">After verifying that the legacy pool is empty, you can then deactivate the pool.</span></span> 
    
    <span data-ttu-id="c40d7-115">如需如何停用舊版集區和伺服器的詳細資訊，請參閱[階段8：解除委任舊版](phase-8-decommission-legacy-pools.md)集區。</span><span class="sxs-lookup"><span data-stu-id="c40d7-115">For details about how to deactivate the legacy pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>
    

