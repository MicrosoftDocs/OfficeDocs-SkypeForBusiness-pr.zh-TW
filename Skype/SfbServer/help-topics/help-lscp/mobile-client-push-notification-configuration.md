---
title: 行動用戶端推播通知設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
description: 若要設定 Microsoft 推播通知和 Apple 推播通知, 您必須建立原則, 以定義您需要哪些類型的推播通知。
ms.openlocfilehash: 571efc74050dc7b7cf55677167a803ddcd8c8f14
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192474"
---
# <a name="mobile-client-push-notification-configuration"></a>行動用戶端: 推播通知設定
 
若要設定**Microsoft 推播通知**和**Apple 推播通知**, 您必須建立原則, 以定義您需要哪些類型的推播通知。
  
您可以在 [主要設定] 畫面上**** 按一下 [重新整理], 重新整理並重新填入原則清單。 提供搜尋方塊以縮小顯示原則的清單範圍。 當您輸入您要搜尋的名稱時, 原則清單會自動縮小。
  
> [!IMPORTANT]
> 在一個策略層級套用的原則設定可以覆寫在其他原則層級套用的設定。 原則優先順序為: 使用者原則 (最大影響) 會覆寫網站原則, 然後網站原則會覆寫全域原則 (最小的影響)。 這表示原則設定越接近策略設定的物件, 就會受到對物件的影響。 
  
提供兩個選項供原則建立及編輯:
  
1. [**新增**]: 按一下以建立新原則。 您必須提供要套用至原則的網站。 接著您可以設定推播通知的設定。 針對**推播通知**設定, 您只能針對您已建立的網站建立原則。
    
2. [**編輯**]: 選取原則, 然後按一下 [編輯], 從下拉式清單中選取動作。 您只能編輯已建立的網站, 或編輯全域原則:
    
   - **顯示詳細資料 ...**: 顯示目前所選原則的相關資訊。 您可以對現有的原則進行變更。
    
   - **選取 [全部**]: 如果您有多個原則, 且需要選取所有原則, 請按一下 [全選]。
    
   - [**刪除**]: 將會移除選取的原則。 使用 [**全選**] 和 [**刪除**] 將移除所有原則
    
     > [!NOTE]
     > 您無法刪除預設的**全域**原則。 如果您嘗試將它刪除, 系統會通知全域原則已傳回預設值 (也就是已清除所有設定), 但無法移除原則。
  
建立新的原則或編輯現有的原則時, 會有兩個動作與您產生關聯:
  
- **認可**[Commit] (提交) 動作會建立或更新原則並儲存變更
    
- **取消**[取消] 動作會捨棄自上次認可動作之後所做的任何變更。 如果您取消, 所做的任何變更都會遺失。
    
**推播通知**設定可能有兩種設定。 這些設定與適用于 Microsoft 和 Apple 的推播通知服務相關聯。 您可以選取服務名稱旁的核取方塊, 以啟用任何一個服務的推播通知。 您可以透過選取核取方塊加以清除來清除它。 選取完畢之後, 您就可以進行提交或取消。 按一下 [commit] (提交) 會將變更儲存至原則。
  

