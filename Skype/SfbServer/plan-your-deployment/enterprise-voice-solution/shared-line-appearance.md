---
title: 在商務用 Skype Server 2015 中規劃共用線外觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/21/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: 請閱讀本主題, 瞭解如何在商務用 Skype Server 2015 (2015 年11月累計更新) 中規劃共用線外觀 (SLA)。
ms.openlocfilehash: 966c9f32a27ba936e880bdb51690bcefed4ffbe4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187558"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中規劃共用線外觀
 
請閱讀本主題, 瞭解如何在商務用 Skype Server 2015 (2015 年11月累計更新) 中規劃共用線外觀 (SLA)。 
  
共用線外觀是商務用 Skype 中的一項功能, 可在稱為共用電話號碼的特定號碼上處理多個通話。 SLA 可以設定任何已啟用企業語音功能的商務用 Skype 使用者作為含多個線路的共用號碼, 以回應多個通話。 通話不會在共用電話號碼上實際接收, 而是將其轉寄給充當共用號碼代理人的使用者。 任何一個代理人都可以接聽通話, 而其餘的代理人會在他們的電話上收到通知, 告知他們接聽通話的人, 以及哪個線路變得占線。 您可以在 SLA 中, 將行數和代理人都設定為共用的號碼。 此外, 高級選項 (例如 BusyOption (所有線路都忙的情況下會發生什麼情況) 和 MissedCallOption (沒有任何代理人都能接聽通話的情況), 也可以設定共用的電話號碼。
  
只有下列電話裝置支援 SLA (電腦、行動電話或其他裝置上的商務用 Skype 用戶端不支援此功能): 
  
- 含固件更新5.4.1 的 Polycom VVX300
    
- 含固件更新5.4.1 的 Polycom VVX400
    
- 含固件更新5.4.1 的 Polycom VVX500
    
- 含固件更新5.4.1 的 Polycom VVX600
    
SLA 是商務用 Skype Server 中的新功能, 2015 年11月累計更新。 
  
如需有關部署 SLA 的資訊, 請參閱[在商務用 Skype Server 2015 中部署共用行外觀](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md)。
  
## <a name="feature-list"></a>功能清單

設定 SLA 群組可啟用下列功能:
  
- 群組中的所有代理人都可以將來電應答給相同的共用號碼。 通話可以是 PSTN 或以 SIP 為基礎。
    
- 代理人可以保留並挑選通話。
    
- 代理人可以將來電轉接到 SLA 群組以外的號碼。
    
- 代理人可以查看共用電話號碼目前有多少來電, 以及每個通話的狀態。
    
- 您可以設定共用電話號碼的最大併發通話數。 您也可以設定在達到此上限之後, 您想要處理其他通話的方式。 過多的通話可能會受到占線、轉寄至備用號碼, 或轉接至語音信箱。
    
- 您可以設定要處理的未接來電 (在某個時間之後未拾取來電)。 如果您啟用 [群組身分識別] 的語音信箱, 未接來電會自動移至 [語音信箱]。 如果您沒有為群組身分識別 (共用電話號碼) 啟用語音信箱, 您可以選擇讓未接來電遭到使用占線信號, 轉寄到備用號碼或中斷連線。
    

