---
title: 行動用戶端推播通知設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
description: 若要設定 Microsoft 推播通知和 Apple 推播通知，您必須建立原則，以定義您需要哪些類型的推播通知。
ms.openlocfilehash: 36cf19d42a2378e024f90d3dbe60123b3d5473fa
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700028"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="b1342-103">行動用戶端：推播通知設定</span><span class="sxs-lookup"><span data-stu-id="b1342-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="b1342-104">若要設定**Microsoft 推播通知**和**Apple 推播通知**，您必須建立原則，以定義您需要哪些類型的推播通知。</span><span class="sxs-lookup"><span data-stu-id="b1342-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="b1342-105">您可以在 [主要設定] 畫面上**按一下 [** 重新整理]，重新整理並重新填入原則清單。</span><span class="sxs-lookup"><span data-stu-id="b1342-105">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies.</span></span> <span data-ttu-id="b1342-106">提供搜尋方塊以縮小顯示原則的清單範圍。</span><span class="sxs-lookup"><span data-stu-id="b1342-106">A search box is provided for narrowing the list of displayed policies.</span></span> <span data-ttu-id="b1342-107">當您輸入您要搜尋的名稱時，原則清單會自動縮小。</span><span class="sxs-lookup"><span data-stu-id="b1342-107">As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b1342-108">在一個策略層級套用的原則設定可以覆寫在其他原則層級套用的設定。</span><span class="sxs-lookup"><span data-stu-id="b1342-108">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="b1342-109">原則優先順序為：使用者原則（最大影響）會覆寫網站原則，然後網站原則會覆寫全域原則（最小的影響）。</span><span class="sxs-lookup"><span data-stu-id="b1342-109">Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="b1342-110">這表示原則設定越接近策略設定的物件，就會受到對物件的影響。</span><span class="sxs-lookup"><span data-stu-id="b1342-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="b1342-111">提供兩個選項供原則建立及編輯：</span><span class="sxs-lookup"><span data-stu-id="b1342-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="b1342-112">[**新增**]：按一下以建立新原則。</span><span class="sxs-lookup"><span data-stu-id="b1342-112">**New**: Click to create a new policy.</span></span> <span data-ttu-id="b1342-113">您必須提供要套用至原則的網站。</span><span class="sxs-lookup"><span data-stu-id="b1342-113">You must provide a site for the policy to apply to.</span></span> <span data-ttu-id="b1342-114">接著您可以設定推播通知的設定。</span><span class="sxs-lookup"><span data-stu-id="b1342-114">You then configure the settings for the push notification.</span></span> <span data-ttu-id="b1342-115">針對**推播通知**設定，您只能針對您已建立的網站建立原則。</span><span class="sxs-lookup"><span data-stu-id="b1342-115">For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="b1342-116">[**編輯**]：選取原則，然後按一下 [編輯]，從下拉式清單中選取動作。</span><span class="sxs-lookup"><span data-stu-id="b1342-116">**Edit**: Select a policy and click Edit to select an action from a drop-down.</span></span> <span data-ttu-id="b1342-117">您只能編輯已建立的網站，或編輯全域原則：</span><span class="sxs-lookup"><span data-stu-id="b1342-117">You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="b1342-118">**顯示詳細資料 ...**：顯示目前所選原則的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b1342-118">**Show details…**: Displays information about the currently selected policy.</span></span> <span data-ttu-id="b1342-119">您可以對現有的原則進行變更。</span><span class="sxs-lookup"><span data-stu-id="b1342-119">You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="b1342-120">**選取 [全部**]：如果您有多個原則，且需要選取所有原則，請按一下 [全選]。</span><span class="sxs-lookup"><span data-stu-id="b1342-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="b1342-121">[**刪除**]：將會移除選取的原則。</span><span class="sxs-lookup"><span data-stu-id="b1342-121">**Delete**: Will remove the selected policy.</span></span> <span data-ttu-id="b1342-122">使用 [**全選**] 和 [**刪除**] 將移除所有原則</span><span class="sxs-lookup"><span data-stu-id="b1342-122">Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="b1342-123">您無法刪除預設的**全域**原則。</span><span class="sxs-lookup"><span data-stu-id="b1342-123">You cannot delete the default **Global** policy.</span></span> <span data-ttu-id="b1342-124">如果您嘗試將它刪除，系統會通知全域原則已傳回預設值（也就是已清除所有設定），但無法移除原則。</span><span class="sxs-lookup"><span data-stu-id="b1342-124">If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="b1342-125">建立新的原則或編輯現有的原則時，會有兩個動作與您產生關聯：</span><span class="sxs-lookup"><span data-stu-id="b1342-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="b1342-126">**認可**[Commit] （提交）動作會建立或更新原則並儲存變更</span><span class="sxs-lookup"><span data-stu-id="b1342-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="b1342-127">**取消**[取消] 動作會捨棄自上次認可動作之後所做的任何變更。</span><span class="sxs-lookup"><span data-stu-id="b1342-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="b1342-128">如果您取消，所做的任何變更都會遺失。</span><span class="sxs-lookup"><span data-stu-id="b1342-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="b1342-129">**推播通知**設定可能有兩種設定。</span><span class="sxs-lookup"><span data-stu-id="b1342-129">Two settings are possible for **Push Notification Configuration**.</span></span> <span data-ttu-id="b1342-130">這些設定與適用于 Microsoft 和 Apple 的推播通知服務相關聯。</span><span class="sxs-lookup"><span data-stu-id="b1342-130">The settings are associated with the push notification services for Microsoft and for Apple.</span></span> <span data-ttu-id="b1342-131">您可以選取服務名稱旁的核取方塊，以啟用任何一個服務的推播通知。</span><span class="sxs-lookup"><span data-stu-id="b1342-131">You enable push notification for either service by selecting the check box next to the name of the service.</span></span> <span data-ttu-id="b1342-132">您可以透過選取核取方塊加以清除來清除它。</span><span class="sxs-lookup"><span data-stu-id="b1342-132">You can clear the check box by selecting it to clear it.</span></span> <span data-ttu-id="b1342-133">選取完畢之後，您就可以進行提交或取消。</span><span class="sxs-lookup"><span data-stu-id="b1342-133">Once you have made your selections, you either commit or cancel.</span></span> <span data-ttu-id="b1342-134">按一下 [commit] （提交）會將變更儲存至原則。</span><span class="sxs-lookup"><span data-stu-id="b1342-134">Clicking commit will save the changes to the policy.</span></span>
  

