---
title: 行動用戶端推播通知設定
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 2d992fc90891dbbf39d3f18dcce5e6b509e66280
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671799"
---
# <a name="mobile-client-push-notification-configuration"></a>行動用戶端：推播通知設定
 
若要設定 **Microsoft 推播通知** 和 **Apple 推播通知**，您必須建立原則來定義您需要的推播通知類型。
  
在主要設定畫面上，您可以按一下 [ **重新** 整理] 重新整理並重新填入原則清單。 提供搜尋方塊以縮小顯示的原則清單。 當您輸入要搜尋的名稱時，原則清單會自動縮小。
  
> [!IMPORTANT]
> 在一個原則層級套用的原則設定，可以覆寫在另一個原則層級套用的設定。 原則優先順序為：使用者原則 (影響最大) 覆寫網站原則，然後月臺原則會覆寫全域原則 (影響最小的) 。 也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。 
  
有兩個選項可供建立和編輯原則：
  
1. **新增**：按一下以建立新的原則。 您必須提供要套用原則的網站。 然後，您會設定推播通知的設定。 針對 **推播通知組態**，您只能為已建立的網站建立原則。
    
2. **編輯**：選取原則，然後按一下 [編輯] 從下拉式清單中選取動作。 您只能編輯已建立或編輯全域原則的網站：
    
   - **顯示詳細資料...**：顯示目前所選原則的相關資訊。 您將能夠對現有原則進行變更。
    
   - **全選**：如果您有數個原則，而且需要選取所有原則，請按一下 [全選]
    
   - **刪除**：將會移除選取的原則。 使用 **[全選** ] 和 **[刪除]** 會移除所有原則
    
     > [!NOTE]
     > 您無法刪除預設的 **全** 局原則。 如果您嘗試刪除它，系統會通知您全域原則已傳回預設值 (也就是，所有設定都會) 清除，但無法移除原則。
  
建立新原則或編輯現有原則與兩個動作相關聯：
  
- **提交** 認可動作會建立或更新原則，並儲存變更
    
- **取消** 取消動作會捨棄自上次認可動作之後所做的任何變更。 如果您取消，將會遺失所做的任何變更。
    
**推播通知組態** 有兩個可能的設定。 這些設定會與 Microsoft 和 Apple 的推播通知服務相關聯。 您可以選取服務名稱旁邊的核取方塊，為任一服務啟用推播通知。 您可以選取核取方塊來清除核取方塊。 選取之後，您可以認可或取消。 按一下 [認可] 會將變更儲存至原則。
  

