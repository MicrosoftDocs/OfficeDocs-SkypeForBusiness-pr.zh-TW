---
title: 在商務用 Skype 中設定語音原則、PSTN 使用方式記錄和語音路由
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
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 摘要：瞭解如何在商務用 Skype Server 中設定語音原則、PSTN 使用方式記錄和語音路由。
ms.openlocfilehash: f8c9f75f24a06b210a1c17ed11a1485ab5158f3d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830443"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a><span data-ttu-id="10e0b-103">在商務用 Skype 中設定語音原則、PSTN 使用方式記錄和語音路由</span><span class="sxs-lookup"><span data-stu-id="10e0b-103">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>
 
<span data-ttu-id="10e0b-104">**摘要：** 瞭解如何在商務用 Skype Server 中設定語音原則、PSTN 使用方式記錄和語音路由。</span><span class="sxs-lookup"><span data-stu-id="10e0b-104">**Summary:** Learn how to configure voice policies, PSTN usage records, and voice routes in Skype for Business Server.</span></span>
  
<span data-ttu-id="10e0b-p101">語音原則、PSTN 使用方式記錄和語音路由密切相關。您可以選取一組撥號功能，接著指派一組 PSTN 使用方式記錄給原則，以便指定獲指派語音原則的使用者或群組可獲得哪些權限授權，如此就能設定語音原則。語音路由也會被指派 PSTN 使用方式記錄，這些記錄會用來比對路由與獲授權使用這些路由的使用者。也就是說，使用者可以撥打的電話，只限於使用他們有相符 PSTN 使用方式記錄之路由的電話。</span><span class="sxs-lookup"><span data-stu-id="10e0b-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>
  
<span data-ttu-id="10e0b-109">新 Enterprise Voice 部署的建議工作流程是：從設定包含適當 PSTN 使用方式記錄的語音原則開始，接著將適當路由關聯給每個 PSTN 使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="10e0b-109">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="10e0b-110">您也可以建立具有  *使用者*  範圍的語音原則，並將其指派給個別使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="10e0b-110">You can also create voice policies with  *user*  scope and assign them to individual users or groups.</span></span>
  
<span data-ttu-id="10e0b-111">如需執行每項工作的詳細步驟，請參閱本節程序。</span><span class="sxs-lookup"><span data-stu-id="10e0b-111">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="10e0b-112">本節內容</span><span class="sxs-lookup"><span data-stu-id="10e0b-112">In this section</span></span>

- [<span data-ttu-id="10e0b-113">在商務用 Skype 中建立或修改語音原則及設定 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="10e0b-113">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)
    
- [<span data-ttu-id="10e0b-114">在商務用 Skype 中設定語音信箱轉義</span><span class="sxs-lookup"><span data-stu-id="10e0b-114">Configure voice mail escape in Skype for Business</span></span>](configure-voice-mail-escape.md)
    
- [<span data-ttu-id="10e0b-115">在商務用 Skype 中查看 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="10e0b-115">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)
    
- [<span data-ttu-id="10e0b-116">在商務用 Skype 中建立或修改語音路由</span><span class="sxs-lookup"><span data-stu-id="10e0b-116">Create or modify a voice route in Skype for Business</span></span>](create-or-modify-a-voice-route.md)
    
- [<span data-ttu-id="10e0b-117">在商務用 Skype 中匯出或匯入語音路由設定檔</span><span class="sxs-lookup"><span data-stu-id="10e0b-117">Export or import a voice route configuration file in Skype for Business</span></span>](voice-route-configuration-import-export.md)
    
- [<span data-ttu-id="10e0b-118">在商務用 Skype 中將擱置的變更發佈至語音路由設定</span><span class="sxs-lookup"><span data-stu-id="10e0b-118">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)
    

