---
title: 在商務用 Skype 中設定語音原則、PSTN 使用方式記錄及語音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: '摘要: 瞭解如何在商務用 Skype Server 中設定語音原則、PSTN 使用方式記錄及語音路由。'
ms.openlocfilehash: 5ce6b6b3e93804f648529043b9189110d25cbb08
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193257"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a><span data-ttu-id="487bf-103">在商務用 Skype 中設定語音原則、PSTN 使用方式記錄及語音路由</span><span class="sxs-lookup"><span data-stu-id="487bf-103">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>
 
<span data-ttu-id="487bf-104">**摘要:** 瞭解如何在商務用 Skype Server 中設定語音原則、PSTN 使用方式記錄及語音路由。</span><span class="sxs-lookup"><span data-stu-id="487bf-104">**Summary:** Learn how to configure voice policies, PSTN usage records, and voice routes in Skype for Business Server.</span></span>
  
<span data-ttu-id="487bf-105">語音原則、PSTN 使用記錄及語音路由都是 integrally 相關的。</span><span class="sxs-lookup"><span data-stu-id="487bf-105">Voice policies, PSTN usage records, and voice routes are integrally related.</span></span> <span data-ttu-id="487bf-106">您可以透過選取一組通話功能來設定語音原則, 然後將原則指派給一組 PSTN 使用記錄, 指定將哪些權利授權給指派了語音原則的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="487bf-106">You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy.</span></span> <span data-ttu-id="487bf-107">語音路由也是指派 PSTN 使用記錄, 可讓路由與有權使用它們的使用者相符。</span><span class="sxs-lookup"><span data-stu-id="487bf-107">Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them.</span></span> <span data-ttu-id="487bf-108">也就是說, 使用者只能將使用路由的呼叫放在其中, 他們有相符的 PSTN 使用記錄。</span><span class="sxs-lookup"><span data-stu-id="487bf-108">That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>
  
<span data-ttu-id="487bf-109">新企業語音部署的建議工作流程是從設定包含適當 PSTN 使用記錄的語音原則開始, 然後將適當的路由與每個 PSTN 使用量記錄產生關聯。</span><span class="sxs-lookup"><span data-stu-id="487bf-109">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="487bf-110">您也可以使用*使用者*範圍建立語音原則, 並將其指派給個別的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="487bf-110">You can also create voice policies with  *user*  scope and assign them to individual users or groups.</span></span>
  
<span data-ttu-id="487bf-111">如需執行每項工作的詳細步驟, 請參閱本節中的程式。</span><span class="sxs-lookup"><span data-stu-id="487bf-111">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="487bf-112">本節內容</span><span class="sxs-lookup"><span data-stu-id="487bf-112">In this section</span></span>

- [<span data-ttu-id="487bf-113">在商務用 Skype 中建立或修改語音原則及設定 PSTN 使用記錄</span><span class="sxs-lookup"><span data-stu-id="487bf-113">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)
    
- [<span data-ttu-id="487bf-114">在商務用 Skype 中設定語音信箱轉義</span><span class="sxs-lookup"><span data-stu-id="487bf-114">Configure voice mail escape in Skype for Business</span></span>](configure-voice-mail-escape.md)
    
- [<span data-ttu-id="487bf-115">在商務用 Skype 中查看 PSTN 使用狀況記錄</span><span class="sxs-lookup"><span data-stu-id="487bf-115">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)
    
- [<span data-ttu-id="487bf-116">在商務用 Skype 中建立或修改語音路線</span><span class="sxs-lookup"><span data-stu-id="487bf-116">Create or modify a voice route in Skype for Business</span></span>](create-or-modify-a-voice-route.md)
    
- [<span data-ttu-id="487bf-117">在商務用 Skype 中匯出或匯入語音路由設定檔</span><span class="sxs-lookup"><span data-stu-id="487bf-117">Export or import a voice route configuration file in Skype for Business</span></span>](voice-route-configuration-import-export.md)
    
- <span data-ttu-id="487bf-118">[在商務用 Skype 中發佈 [語音路由設定] 的擱置變更](voice-route-config-changes.md)</span><span class="sxs-lookup"><span data-stu-id="487bf-118">[Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md)</span></span>
    

