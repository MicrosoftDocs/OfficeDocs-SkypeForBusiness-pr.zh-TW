---
title: 行動用戶端推播通知設定
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
ROBOTS: NOINDEX, NOFOLLOW
description: 若要設定 Microsoft 推播通知和 Apple 推播通知，您必須建立原則來定義您需要的推播通知類型。
ms.openlocfilehash: 693b954fffbbce56a2d95ce29128482937b6fa05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836673"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="436ea-103">行動用戶端：推播通知設定</span><span class="sxs-lookup"><span data-stu-id="436ea-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="436ea-104">若要設定 **Microsoft 推播通知** 和 **Apple 推播通知**，您必須建立原則來定義您需要的推播通知類型。</span><span class="sxs-lookup"><span data-stu-id="436ea-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="436ea-105">在 [主要設定] 畫面上，您 **可以按一下 [** 重新整理] 重新整理並重新填入原則清單。</span><span class="sxs-lookup"><span data-stu-id="436ea-105">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies.</span></span> <span data-ttu-id="436ea-106">提供搜尋方塊以縮小顯示原則的清單。</span><span class="sxs-lookup"><span data-stu-id="436ea-106">A search box is provided for narrowing the list of displayed policies.</span></span> <span data-ttu-id="436ea-107">當您輸入要搜尋的名稱時，原則清單會自動縮小。</span><span class="sxs-lookup"><span data-stu-id="436ea-107">As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="436ea-108">在一個原則層級套用的原則設定，可以覆寫在另一個原則層級套用的設定。</span><span class="sxs-lookup"><span data-stu-id="436ea-108">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="436ea-109">原則優先順序是：使用者原則 (最影響) 覆寫網站原則，然後網站原則會覆寫全域原則 (最小影響) 。</span><span class="sxs-lookup"><span data-stu-id="436ea-109">Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="436ea-110">也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。</span><span class="sxs-lookup"><span data-stu-id="436ea-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="436ea-111">有兩個選項可用於原則建立和編輯：</span><span class="sxs-lookup"><span data-stu-id="436ea-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="436ea-112">**新增**：按一下以建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="436ea-112">**New**: Click to create a new policy.</span></span> <span data-ttu-id="436ea-113">您必須提供要套用原則的網站。</span><span class="sxs-lookup"><span data-stu-id="436ea-113">You must provide a site for the policy to apply to.</span></span> <span data-ttu-id="436ea-114">然後，您可以設定推播通知的設定。</span><span class="sxs-lookup"><span data-stu-id="436ea-114">You then configure the settings for the push notification.</span></span> <span data-ttu-id="436ea-115">針對 **推播通知** 設定，您只能為已經建立的網站建立原則。</span><span class="sxs-lookup"><span data-stu-id="436ea-115">For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="436ea-116">**編輯**：選取原則，然後按一下 [編輯]，從下拉式清單中選取動作。</span><span class="sxs-lookup"><span data-stu-id="436ea-116">**Edit**: Select a policy and click Edit to select an action from a drop-down.</span></span> <span data-ttu-id="436ea-117">您只能編輯您已建立的網站，也可以編輯全域原則：</span><span class="sxs-lookup"><span data-stu-id="436ea-117">You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="436ea-118">**顯示詳細資料 ...**：顯示目前所選原則的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="436ea-118">**Show details…**: Displays information about the currently selected policy.</span></span> <span data-ttu-id="436ea-119">您將可以變更現有的原則。</span><span class="sxs-lookup"><span data-stu-id="436ea-119">You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="436ea-120">**全選**：如果您有許多原則，且需要選取所有原則，請按一下 [全選]。</span><span class="sxs-lookup"><span data-stu-id="436ea-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="436ea-121">**Delete**：將會移除選取的原則。</span><span class="sxs-lookup"><span data-stu-id="436ea-121">**Delete**: Will remove the selected policy.</span></span> <span data-ttu-id="436ea-122">使用 [ **全選** ] 及 [ **刪除** ] 將移除所有原則</span><span class="sxs-lookup"><span data-stu-id="436ea-122">Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="436ea-123">您無法刪除預設的 **全域** 原則。</span><span class="sxs-lookup"><span data-stu-id="436ea-123">You cannot delete the default **Global** policy.</span></span> <span data-ttu-id="436ea-124">如果您嘗試刪除它，系統會通知您全域原則已傳回預設值 (也就是說，所有設定都會被清除) ，但無法移除原則。</span><span class="sxs-lookup"><span data-stu-id="436ea-124">If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="436ea-125">建立新原則或編輯現有的原則與兩個動作相關聯：</span><span class="sxs-lookup"><span data-stu-id="436ea-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="436ea-126">**認可** 「認可」動作會建立或更新原則並儲存變更</span><span class="sxs-lookup"><span data-stu-id="436ea-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="436ea-127">**取消** 取消動作會捨棄自上次認可動作後所做的任何變更。</span><span class="sxs-lookup"><span data-stu-id="436ea-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="436ea-128">如果您取消，所做的任何變更都會遺失。</span><span class="sxs-lookup"><span data-stu-id="436ea-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="436ea-129">有兩個設定可用於 **推播通知** 設定。</span><span class="sxs-lookup"><span data-stu-id="436ea-129">Two settings are possible for **Push Notification Configuration**.</span></span> <span data-ttu-id="436ea-130">設定與適用于 Microsoft 的推播通知服務和 Apple 相關聯。</span><span class="sxs-lookup"><span data-stu-id="436ea-130">The settings are associated with the push notification services for Microsoft and for Apple.</span></span> <span data-ttu-id="436ea-131">您可以選取服務名稱旁邊的核取方塊，以啟用任一項服務的推播通知。</span><span class="sxs-lookup"><span data-stu-id="436ea-131">You enable push notification for either service by selecting the check box next to the name of the service.</span></span> <span data-ttu-id="436ea-132">您可以透過選取它來清除核取方塊。</span><span class="sxs-lookup"><span data-stu-id="436ea-132">You can clear the check box by selecting it to clear it.</span></span> <span data-ttu-id="436ea-133">進行選取之後，您可以認可或取消。</span><span class="sxs-lookup"><span data-stu-id="436ea-133">Once you have made your selections, you either commit or cancel.</span></span> <span data-ttu-id="436ea-134">按一下 [認可]，將變更儲存到原則。</span><span class="sxs-lookup"><span data-stu-id="436ea-134">Clicking commit will save the changes to the policy.</span></span>
  

