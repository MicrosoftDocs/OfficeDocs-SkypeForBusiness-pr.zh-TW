---
title: 行動用戶端推播通知設定
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
description: 若要設定 Microsoft 推播通知和 Apple 推播通知，您必須建立原則來定義您需要的推播通知類型。
ms.openlocfilehash: 22b1174eee06fd46bd69d1d9b6c1c4f3f12ac01f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841525"
---
# <a name="mobile-client-push-notification-configuration"></a>行動用戶端：推播通知設定
 
若要設定 **Microsoft 推播通知** 和 **Apple 推播通知**，您必須建立原則來定義您需要的推播通知類型。
  
在 [主要設定] 畫面上，您 **可以按一下 [** 重新整理] 重新整理並重新填入原則清單。 提供搜尋方塊以縮小顯示原則的清單。 當您輸入要搜尋的名稱時，原則清單會自動縮小。
  
> [!IMPORTANT]
> 在一個原則層級套用的原則設定，可以覆寫在另一個原則層級套用的設定。 原則優先順序是：使用者原則 (最影響) 覆寫網站原則，然後網站原則會覆寫全域原則 (最小影響) 。 也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。 
  
有兩個選項可用於原則建立和編輯：
  
1. **新增**：按一下以建立新的原則。 您必須提供要套用原則的網站。 然後，您可以設定推播通知的設定。 針對 **推播通知** 設定，您只能為已經建立的網站建立原則。
    
2. **編輯**：選取原則，然後按一下 [編輯]，從下拉式清單中選取動作。 您只能編輯您已建立的網站，也可以編輯全域原則：
    
   - **顯示詳細資料 ...**：顯示目前所選原則的相關資訊。 您將可以變更現有的原則。
    
   - **全選**：如果您有許多原則，且需要選取所有原則，請按一下 [全選]。
    
   - **Delete**：將會移除選取的原則。 使用 [ **全選** ] 及 [ **刪除** ] 將移除所有原則
    
     > [!NOTE]
     > 您無法刪除預設的 **全域** 原則。 如果您嘗試刪除它，系統會通知您全域原則已傳回預設值 (也就是說，所有設定都會被清除) ，但無法移除原則。
  
建立新原則或編輯現有的原則與兩個動作相關聯：
  
- **認可** 「認可」動作會建立或更新原則並儲存變更
    
- **取消** 取消動作會捨棄自上次認可動作後所做的任何變更。 如果您取消，所做的任何變更都會遺失。
    
有兩個設定可用於 **推播通知** 設定。 設定與適用于 Microsoft 的推播通知服務和 Apple 相關聯。 您可以選取服務名稱旁邊的核取方塊，以啟用任一項服務的推播通知。 您可以透過選取它來清除核取方塊。 進行選取之後，您可以認可或取消。 按一下 [認可]，將變更儲存到原則。
  

