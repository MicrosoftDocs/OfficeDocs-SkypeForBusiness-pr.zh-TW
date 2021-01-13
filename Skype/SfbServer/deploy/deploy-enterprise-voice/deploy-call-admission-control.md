---
title: 在商務用 Skype Server 中部署通話許可控制
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 通話許可控制 (CAC) 是一種方案，可判斷即時會話是否可以根據可用的頻寬建立，以協助避免網路擁塞之使用者的音訊/視頻品質不良。
ms.openlocfilehash: af08afe02b1dc138aa38ded654d567aed6a09247
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836883"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="9dbeb-103">在商務用 Skype Server 中部署通話許可控制</span><span class="sxs-lookup"><span data-stu-id="9dbeb-103">Deploy call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="9dbeb-104">通話許可控制 (CAC) 是一種方案，可判斷即時會話是否可以根據可用的頻寬建立，以協助避免網路擁塞之使用者的音訊/視頻品質不良。</span><span class="sxs-lookup"><span data-stu-id="9dbeb-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="9dbeb-105">如需詳細資訊，請參閱 [在商務用 Skype Server 中規劃通話許可控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。</span><span class="sxs-lookup"><span data-stu-id="9dbeb-105">For more information, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
### <a name="to-deploy-call-admission-control"></a><span data-ttu-id="9dbeb-106">若要部署通話許可控制</span><span class="sxs-lookup"><span data-stu-id="9dbeb-106">To deploy Call Admission Control</span></span>

1.  <span data-ttu-id="9dbeb-107">收集商業網路拓撲的所有必要資訊，如範例所述 [：在商務用 Skype Server 中收集通話許可控制需求](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9dbeb-107">Gather all of the required information for your enterprise network topology, as described in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
    
2. <span data-ttu-id="9dbeb-108">若尚未這麼做，則必須定義網路地區和網站，並將子網與網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="9dbeb-108">If you have not done so already, you must define network regions and sites, and associate subnets with network sites.</span></span> <span data-ttu-id="9dbeb-109">如需詳細資訊，請參閱 [在商務用 Skype 中部署網路地區、網站和子網](deploy-network.md)。</span><span class="sxs-lookup"><span data-stu-id="9dbeb-109">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
3. <span data-ttu-id="9dbeb-110">建立頻寬原則設定檔，如在[商務用 Skype Server 中建立頻寬原則設定檔](create-bandwidth-policy-profiles.md)的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="9dbeb-110">Create bandwidth policy profiles, as detailed in [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md)</span></span>
    
4. <span data-ttu-id="9dbeb-111">建立網路地區連結，如 [在商務用 Skype Server 中建立網路地區連結](create-network-region-links.md)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9dbeb-111">Create network region links, as detailed in [Create network region links in Skype for Business Server](create-network-region-links.md).</span></span>
    
5. <span data-ttu-id="9dbeb-112">建立網路間區域路由，如在商務用 [Skype Server 中建立網路 interregional 路由](create-network-interregional-routes.md)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9dbeb-112">Create network inter-region routes, as detailed in [Create network interregional routes in Skype for Business Server](create-network-interregional-routes.md).</span></span>
    
6. <span data-ttu-id="9dbeb-113">建立網路站間原則，如在 [商務用 Skype Server 中建立網路網站間原則](create-network-intersite-policies.md)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9dbeb-113">Create network intersite policies, as detailed in [Create network intersite policies in Skype for Business Server](create-network-intersite-policies.md).</span></span>
    
7. <span data-ttu-id="9dbeb-114">啟用通話許可控制，如 [在商務用 Skype Server 中啟用通話許可控制中](enable-call-admission-control.md)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9dbeb-114">Enable call admission control, as detailed in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
8. <span data-ttu-id="9dbeb-115">請查看一些最後的設定，以確保已正確設定所有專案。</span><span class="sxs-lookup"><span data-stu-id="9dbeb-115">Check a few final settings, to make sure everything is set up correctly.</span></span> <span data-ttu-id="9dbeb-116">如需詳細資訊，請參閱 [通話許可控制部署：商務用 Skype 伺服器的最終檢查清單](final-checklist.md)。</span><span class="sxs-lookup"><span data-stu-id="9dbeb-116">For details, see [Call admission control deployment: final checklist for Skype for Business Server](final-checklist.md).</span></span>
    

