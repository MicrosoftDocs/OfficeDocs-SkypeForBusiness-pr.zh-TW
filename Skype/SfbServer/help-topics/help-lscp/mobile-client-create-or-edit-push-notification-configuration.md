---
title: 行動用戶端建立或編輯推播通知設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
description: 「推播通知」及「推播通知結算所」(PNCH) 是行動功能的兩個主要部分。推播通知是將訊息傳送至 PNCH 的程序。在訊息送達行動用戶端或超過逾時期限之前，都會保留在這裡。
ms.openlocfilehash: 5c7d78174ca4cfe180742fa73a801704cb85997c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192484"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a>行動用戶端：建立或編輯推播通知設定
 
「推播通知」及「推播通知結算所」(PNCH) 是行動功能的兩個主要部分。推播通知是將訊息傳送至 PNCH 的程序。在訊息送達行動用戶端或超過逾時期限之前，都會保留在這裡。 
  
> [!NOTE]
> 此期限是在推播通知結算所設定，部署的使用者或系統管理員無法加以設定。 
  
若要啟用 [推播通知]，請執行下列動作：
  
1. **範圍**：請注意此原則的範圍。該範圍可以是**全域** (適用於此部署中的所有使用者)，或**網站** (僅限於指派給指定網站之主伺服器的使用者)。
    
    > [!IMPORTANT]
    > 在一個策略層級套用的原則設定可以覆寫在其他原則層級套用的設定。 原則優先順序為: 使用者原則 (最大影響) 會覆寫網站原則, 然後網站原則會覆寫全域原則 (最小的影響)。 這表示原則設定越接近策略設定的物件, 就會受到對物件的影響。 
  
2. 按一下下列核取方塊，來選取要啟用的推播通知服務：
    
   - **啟用 Microsoft 推播通知**, 即可使用商務用 Skype 應用程式將推播通知啟用至 Windows Phone 的雲端 PNCH
    
   - **啟用 apple 推播通知**會針對執行 apple iOS 的裝置 (例如, IPhone、iPad) 和使用商務用 Skype 應用程式啟用 apple PNCH 的推播通知
    
3. 完成原則的編輯作業之後，請按一下 [認可]****，儲存您所做的變更。如果需要刪除您所做的變更，請選 [取消]****，這樣就不會將任何變更儲存至原則。
    

