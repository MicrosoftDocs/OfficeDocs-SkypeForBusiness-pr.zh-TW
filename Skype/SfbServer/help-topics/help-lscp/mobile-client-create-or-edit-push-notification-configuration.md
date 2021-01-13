---
title: 行動用戶端建立或編輯推播通知設定
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
description: 推播通知及推播通知的 (PNCH) 是行動功能的兩個重要部分。 推播通知是郵件傳送至 PNCH 的處理常式。 郵件會在這裡保留，直到傳遞給行動用戶端，或超時期限到期為止。
ms.openlocfilehash: 0cd2b17f764891dbb1ad89ada27f6be0b6246ba0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810883"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a><span data-ttu-id="ec1de-105">行動用戶端：建立或編輯推播通知設定</span><span class="sxs-lookup"><span data-stu-id="ec1de-105">Mobile Client: Create or Edit Push Notification Configuration</span></span>
 
<span data-ttu-id="ec1de-106">推播通知及推播通知的 (PNCH) 是行動功能的兩個重要部分。</span><span class="sxs-lookup"><span data-stu-id="ec1de-106">Push Notification and the Push Notification Clearing House (PNCH) are two key parts of the mobility feature.</span></span> <span data-ttu-id="ec1de-107">推播通知是郵件傳送至 PNCH 的處理常式。</span><span class="sxs-lookup"><span data-stu-id="ec1de-107">Push notification is the process where a message is sent to the PNCH.</span></span> <span data-ttu-id="ec1de-108">郵件會在這裡保留，直到傳遞給行動用戶端，或超時期限到期為止。</span><span class="sxs-lookup"><span data-stu-id="ec1de-108">The message is held here until it can be delivered to the mobile client, or the timeout period expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ec1de-109">時段是在推播通知結算所設定，而不是由使用者或您的部署管理員設定。</span><span class="sxs-lookup"><span data-stu-id="ec1de-109">The time period is set at the Push Notification Clearing House and is not configurable by the user or the administrator of your deployment.</span></span> 
  
<span data-ttu-id="ec1de-110">若要啟用推播通知，請執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="ec1de-110">To enable Push Notification, you do the following:</span></span>
  
1. <span data-ttu-id="ec1de-111">**範圍：** 請記下此原則的範圍。</span><span class="sxs-lookup"><span data-stu-id="ec1de-111">**Scope:** Note the scope for this policy.</span></span> <span data-ttu-id="ec1de-112">它可以是 **全域**，也可以套用至此部署中的所有使用者，或 **網站**，這只是在指定的網站中指派給主伺服器的使用者。</span><span class="sxs-lookup"><span data-stu-id="ec1de-112">It can either be **Global**, which applies to all users in this deployment, or **Site**, which is only users assigned to home servers in the specified site.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ec1de-113">在一個原則層級套用的原則設定，可以覆寫在另一個原則層級套用的設定。</span><span class="sxs-lookup"><span data-stu-id="ec1de-113">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="ec1de-114">原則優先順序是：使用者原則 (最影響) 覆寫網站原則，然後網站原則會覆寫全域原則 (最小影響) 。</span><span class="sxs-lookup"><span data-stu-id="ec1de-114">Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="ec1de-115">也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。</span><span class="sxs-lookup"><span data-stu-id="ec1de-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
2. <span data-ttu-id="ec1de-116">按一下下列的核取方塊，以選取您要啟用的推播通知服務：</span><span class="sxs-lookup"><span data-stu-id="ec1de-116">Select which push notification services you want to enable by clicking the check box for:</span></span>
    
   - <span data-ttu-id="ec1de-117">[**啟用 Microsoft 推播通知**] 會針對使用商務用 Skype 應用程式的雲端式 PNCH，啟用 Windows Phone 的推播通知</span><span class="sxs-lookup"><span data-stu-id="ec1de-117">**Enable Microsoft push notification** will enable the push notification to the cloud-based PNCH for Windows Phone with the Skype for Business app</span></span>
    
   - <span data-ttu-id="ec1de-118">[**啟用 apple 推播通知**] 會針對執行 apple iOS (的裝置，啟用 apple PNCH 的推播通知，例如，IPhone、iPad) 和使用商務用 Skype 應用程式</span><span class="sxs-lookup"><span data-stu-id="ec1de-118">**Enable Apple push notification** will enable the push notification to the Apple PNCH for devices running Apple's iOS (for example, iPhone, iPad) and using the Skype for Business app</span></span>
    
3. <span data-ttu-id="ec1de-119">當您完成對原則的編輯時，請按一下 [ **認可** ] 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="ec1de-119">When you have completed the edits of the policy, click **Commit** to save your changes.</span></span> <span data-ttu-id="ec1de-120">如果您需要刪除您所做的變更，請選取 [ **取消**]。</span><span class="sxs-lookup"><span data-stu-id="ec1de-120">If you need to delete the changes you have made, select **Cancel**.</span></span> <span data-ttu-id="ec1de-121">不會將變更儲存至原則。</span><span class="sxs-lookup"><span data-stu-id="ec1de-121">No changes will be saved to the policy.</span></span>
    

