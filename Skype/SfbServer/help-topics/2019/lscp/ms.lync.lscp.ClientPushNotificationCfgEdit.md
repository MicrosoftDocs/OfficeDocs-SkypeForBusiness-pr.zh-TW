---
title: 行動用戶端建立或編輯推播通知設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
ROBOTS: NOINDEX, NOFOLLOW
description: 「推播通知」及「推播通知結算所」(PNCH) 是行動功能的兩個主要部分。推播通知是將訊息傳送至 PNCH 的程序。在訊息送達行動用戶端或超過逾時期限之前，都會保留在這裡。
ms.openlocfilehash: 803bc61d12263e98efe5e74764f9f60f392af95f
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796482"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a><span data-ttu-id="d43aa-105">行動用戶端：建立或編輯推播通知設定</span><span class="sxs-lookup"><span data-stu-id="d43aa-105">Mobile Client: Create or Edit Push Notification Configuration</span></span>
 
<span data-ttu-id="d43aa-p102">「推播通知」及「推播通知結算所」(PNCH) 是行動功能的兩個主要部分。推播通知是將訊息傳送至 PNCH 的程序。在訊息送達行動用戶端或超過逾時期限之前，都會保留在這裡。</span><span class="sxs-lookup"><span data-stu-id="d43aa-p102">Push Notification and the Push Notification Clearing House (PNCH) are two key parts of the mobility feature. Push notification is the process where a message is sent to the PNCH. The message is held here until it can be delivered to the mobile client, or the timeout period expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d43aa-109">此期限是在推播通知結算所設定，部署的使用者或系統管理員無法加以設定。</span><span class="sxs-lookup"><span data-stu-id="d43aa-109">The time period is set at the Push Notification Clearing House and is not configurable by the user or the administrator of your deployment.</span></span> 
  
<span data-ttu-id="d43aa-110">若要啟用 [推播通知]，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d43aa-110">To enable Push Notification, you do the following:</span></span>
  
1. <span data-ttu-id="d43aa-p103">**範圍**：請注意此原則的範圍。該範圍可以是**全域** (適用於此部署中的所有使用者)，或**網站** (僅限於指派給指定網站之主伺服器的使用者)。</span><span class="sxs-lookup"><span data-stu-id="d43aa-p103">**Scope:** Note the scope for this policy. It can either be **Global**, which applies to all users in this deployment, or **Site**, which is only users assigned to home servers in the specified site.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d43aa-113">在一個策略層級套用的原則設定可以覆寫在其他原則層級套用的設定。</span><span class="sxs-lookup"><span data-stu-id="d43aa-113">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="d43aa-114">原則優先順序為：使用者原則（最大影響）會覆寫網站原則，然後網站原則會覆寫全域原則（最小的影響）。</span><span class="sxs-lookup"><span data-stu-id="d43aa-114">Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="d43aa-115">這表示原則設定越接近策略設定的物件，就會受到對物件的影響。</span><span class="sxs-lookup"><span data-stu-id="d43aa-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
2. <span data-ttu-id="d43aa-116">按一下下列核取方塊，來選取要啟用的推播通知服務：</span><span class="sxs-lookup"><span data-stu-id="d43aa-116">Select which push notification services you want to enable by clicking the check box for:</span></span>
    
   - <span data-ttu-id="d43aa-117">**啟用 Microsoft 推播通知**，即可使用商務用 Skype 應用程式將推播通知啟用至 Windows Phone 的雲端 PNCH</span><span class="sxs-lookup"><span data-stu-id="d43aa-117">**Enable Microsoft push notification** will enable the push notification to the cloud-based PNCH for Windows Phone with the Skype for Business app</span></span>
    
   - <span data-ttu-id="d43aa-118">**啟用 apple 推播通知**會針對執行 apple iOS 的裝置（例如，IPhone、iPad）和使用商務用 Skype 應用程式啟用 apple PNCH 的推播通知</span><span class="sxs-lookup"><span data-stu-id="d43aa-118">**Enable Apple push notification** will enable the push notification to the Apple PNCH for devices running Apple's iOS (for example, iPhone, iPad) and using the Skype for Business app</span></span>
    
3. <span data-ttu-id="d43aa-p105">完成原則的編輯作業之後，請按一下 [認可]\*\*\*\*，儲存您所做的變更。如果需要刪除您所做的變更，請選 [取消]\*\*\*\*，這樣就不會將任何變更儲存至原則。</span><span class="sxs-lookup"><span data-stu-id="d43aa-p105">When you have completed the edits of the policy, click **Commit** to save your changes. If you need to delete the changes you have made, select **Cancel**. No changes will be saved to the policy.</span></span>
    

