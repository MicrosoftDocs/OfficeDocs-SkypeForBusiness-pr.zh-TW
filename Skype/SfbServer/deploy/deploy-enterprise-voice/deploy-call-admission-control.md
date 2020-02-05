---
title: 在商務用 Skype Server 中部署呼叫許可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: 通話許可控制（CAC）是一個方案，可判斷是否可以根據可用頻寬建立即時會話，以協助避免使用者在擁擠的網路上發生的音訊/視頻品質不佳。
ms.openlocfilehash: 2e41d5a26e99c482041fb29e204f777a6c1a7cd7
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767666"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="938a1-103">在商務用 Skype Server 中部署呼叫許可控制</span><span class="sxs-lookup"><span data-stu-id="938a1-103">Deploy call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="938a1-104">通話許可控制（CAC）是一個方案，可判斷是否可以根據可用頻寬建立即時會話，以協助避免使用者在擁擠的網路上發生的音訊/視頻品質不佳。</span><span class="sxs-lookup"><span data-stu-id="938a1-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="938a1-105">如需詳細資訊，請參閱[在商務用 Skype 伺服器中規劃通話許可控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="938a1-105">For more information, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="938a1-106">部署通話許可控制</span><span class="sxs-lookup"><span data-stu-id="938a1-106">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="938a1-107">收集商業網路拓朴所需的所有資訊，如範例所述[：在商務用 Skype Server 中收集通話許可控制需求](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="938a1-107">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="938a1-108">如果您還沒有這麼做，您必須定義網路區域和網站，並將子網與網路網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="938a1-108">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="938a1-109">如需詳細資訊，請參閱[在商務用 Skype 中部署網路區域、網站和子網](deploy-network.md)。</span><span class="sxs-lookup"><span data-stu-id="938a1-109">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
3. <span data-ttu-id="938a1-110">建立頻寬原則設定檔，如在[商務用 Skype Server 中建立頻寬原則設定檔中](create-bandwidth-policy-profiles.md)的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="938a1-110">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="938a1-111">建立網路區域連結，具體請見在[商務用 Skype Server 中建立網路區域連結](create-network-region-links.md)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="938a1-111">Create network region links, as detailed in [Create network region links in Skype for Business Server](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="938a1-112">在[商務用 Skype Server 中建立網路 interregional 路由](create-network-interregional-routes.md)，以建立網路區域內路由的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="938a1-112">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="938a1-113">建立網路站間原則，具體請見在[商務用 Skype Server 中建立網路站間原則](create-network-intersite-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="938a1-113">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="938a1-114">啟用 [呼叫許可控制]，如在[商務用 Skype Server 的 [啟用呼叫許可控制](enable-call-admission-control.md)] 中詳細說明。</span><span class="sxs-lookup"><span data-stu-id="938a1-114">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="938a1-115">檢查一些最終設定，以確保所有專案都設定正確。</span><span class="sxs-lookup"><span data-stu-id="938a1-115">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="938a1-116">如需詳細資訊，請參閱[呼叫許可控制部署：適用于商務用 Skype Server 的最終檢查清單](final-checklist.md)。</span><span class="sxs-lookup"><span data-stu-id="938a1-116">For details, see [Call admission control deployment: final checklist for Skype for Business Server](final-checklist.md).</span></span>
    

