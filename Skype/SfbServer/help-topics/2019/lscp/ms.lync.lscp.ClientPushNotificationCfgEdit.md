---
title: 行動用戶端建立或編輯推播通知設定
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
ROBOTS: NOINDEX, NOFOLLOW
description: 推播通知及推播通知的 (PNCH) 是行動功能的兩個重要部分。 推播通知是郵件傳送至 PNCH 的處理常式。 郵件會在這裡保留，直到傳遞給行動用戶端，或超時期限到期為止。
ms.openlocfilehash: 7e148074690f7895a04e2d217b513eac8f7f148c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583177"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a>行動用戶端：建立或編輯推播通知設定
 
推播通知及推播通知的 (PNCH) 是行動功能的兩個重要部分。 推播通知是郵件傳送至 PNCH 的處理常式。 郵件會在這裡保留，直到傳遞給行動用戶端，或超時期限到期為止。 
  
> [!NOTE]
> 時段是在推播通知結算所設定，而不是由使用者或您的部署管理員設定。 
  
若要啟用推播通知，請執行下列作業：
  
1. **範圍：** 請記下此原則的範圍。 它可以是 **全域**，也可以套用至此部署中的所有使用者，或 **網站**，這只是在指定的網站中指派給主伺服器的使用者。
    
    > [!IMPORTANT]
    > 在一個原則層級套用的原則設定，可以覆寫在另一個原則層級套用的設定。 原則優先順序是：使用者原則 (最影響) 覆寫網站原則，然後網站原則會覆寫全域原則 (最小影響) 。 也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。 
  
2. 按一下下列的核取方塊，以選取您要啟用的推播通知服務：
    
   - [**啟用 Microsoft 推播通知**] 會針對使用商務用 Skype 應用程式的 Windows Phone，啟用以雲端為基礎之 PNCH 的推播通知。
    
   - [**啟用 apple 推播通知**] 會針對執行 apple iOS (的裝置，啟用 apple PNCH 的推播通知，例如，iPhone、iPad) 以及使用商務用 Skype 應用程式。
    
3. 當您完成對原則的編輯時，請按一下 [ **認可** ] 以儲存變更。 如果您需要刪除您所做的變更，請選取 [ **取消**]。 不會將變更儲存至原則。
    

