---
title: 定義在商務用 Skype Server 中手動取得位置的使用者體驗
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: 在商務用 Skype Server 企業語音中使用 SIP 主幹提供者，在 E9-1-1 部署中規劃漫遊使用者。
ms.openlocfilehash: 263c2e79e340492b27d196f73373505f7c1e4f66
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60770111"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a>定義在商務用 Skype Server 中手動取得位置的使用者體驗
 
在商務用 Skype Server 企業語音中使用 SIP 主幹提供者，在 E9-1-1 部署中規劃漫遊使用者。
  
如果用戶端位於網路之外，或是未定義的子網中，使用者可以手動輸入位置。 不過，在緊急通話期間，來電會先路由傳送到國家/地區 E9-1-1 緊急呼叫回應中心 (ECRC) dispatcher，再路由傳送至公用安全回應點 (PSAP) 。 ECRC 會口頭查詢位置的來電者，然後根據提供的資訊，將通話轉寄給適當的 PSAP。 
  
**當使用者未自動提供位置資訊服務時，是否要提示使用者輸入位置？**
  
例如，如果用戶端位於未定義的子網、家裡、酒店或網路以外的其他地方，是否應使用者輸入位置？
    
您可以在位置原則中設定 [ **必要的位置** ] 設定，以定義用戶端行為。 將此值設為 [否] 表示將不會提示使用者輸入位置。 將此值設為 [是]，表示系統會提示使用者輸入位置，但可以關閉提示。 將此值設為免責聲明表示將會提示使用者輸入位置，如果使用者嘗試關閉提示，將會顯示免責聲明。 在所有情況下，使用者都可以繼續照常使用用戶端。
    
當使用者手動輸入位置時，該位置會對應至用戶端網路之預設閘道的 MAC 位址，並儲存在用戶端的每一位使用者資料表中。 當使用者回到任何先前儲存的位置時，商務用 Skype 用戶端會自動將自己設定到該位置。 
  
> [!NOTE]
> 您可以只修改用戶端的目前位置，但也可以刪除儲存在本機使用者資料表中的任何位置。 
  

