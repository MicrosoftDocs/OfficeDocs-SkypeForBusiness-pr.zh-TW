---
title: 在商務用 Skype Server 2015 中規劃共用行外觀
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/21/2016
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
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: 請閱讀本主題，以瞭解如何在 2015 2015 年11月累積更新 (的 SLA) 商務用 Skype Server 中規劃共用線外觀。
ms.openlocfilehash: 9400a4a68c992c822162be3a5f84ea4a9d0ede31
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847206"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中規劃共用行外觀
 
請閱讀本主題，以瞭解如何在 2015 2015 年11月累積更新 (的 SLA) 商務用 Skype Server 中規劃共用線外觀。 
  
共用列的外觀是商務用 Skype 中的一項功能，用來處理特定號碼（稱為共用號碼）上的多個通話。 SLA 可將任何已啟用企業語音的商務用 Skype 使用者設定為具有多行的共用號碼，以回應多個通話。 呼叫並未實際接收共用號碼，而是轉寄給充當共用號碼代理人的使用者。 任何一位代理人都可以接聽來電，而其餘的代理人會在他們的電話上取得通知，告知已收取通話的人員，以及哪些線路已變得忙碌的結果。 您可以設定 SLA 中共用號碼的行數和代理人。 此外，高級選項（例如 BusyOption (所有線路忙碌) 和 MissedCallOption 時，會發生什麼情況）。 (所有代理人都不會拾取來電) 的情況，也可以設定共用號碼。
  
僅在下列電話裝置上支援 SLA (電腦、行動電話或其他裝置上商務用 Skype 用戶端不支援此項功能) ： 
  
- 含固件更新5.4.1 的 Polycom VVX300
    
- 含固件更新5.4.1 的 Polycom VVX400
    
- 含固件更新5.4.1 的 Polycom VVX500
    
- 含固件更新5.4.1 的 Polycom VVX600
    
SLA 是商務用 Skype Server，2015年11月累積更新的新功能。 
  
如需部署 SLA 的相關資訊，請參閱[在商務用 Skype Server 2015 中部署共用線路外觀](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md)。
  
## <a name="feature-list"></a>功能清單

設定 SLA 群組可啟用下列專案：
  
- 群組中的所有代理人都可以接聽撥入呼叫相同共用號碼。 通話可以是以 PSTN 為基礎或以 SIP 為基礎。
    
- 代理人可以保留及挑選通話。
    
- 代理人可將來電轉接至 SLA 群組以外的號碼。
    
- 代理人可以查看共用號碼目前有多少通話，並查看每個通話的狀態。
    
- 您可以設定共用號碼的並行通話數目上限。 您也可以設定達到上限之後，要如何處理其他呼叫。 過度通話可能會遭到忙碌，但會轉接至備用號碼，或轉接至語音信箱。
    
- 您可以設定在特定時間) 進行處理時，要如何撥打未接來電 (通話的方式。 如果您為群組識別碼啟用語音信箱，未接來電會自動移至語音信箱。 如果您未啟用群組身分識別的「 (共用號碼」) 的語音信箱，您可以選擇將未接來電拒絕為繁忙的信號、轉寄至備用號碼，或中斷連線。
    

