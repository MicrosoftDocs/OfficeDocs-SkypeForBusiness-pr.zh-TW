---
title: 可選在商務用 Skype 中確認通話駐留部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: 在商務用 Skype Server Enterprise Voice 中驗證撥出電話寄存的部署。
ms.openlocfilehash: d698bf46f0a36a86729856c388fde09514288253
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240434"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>可選在商務用 Skype 中確認通話駐留部署
 
在商務用 Skype Server Enterprise Voice 中驗證撥出電話寄存的部署。 
  
安裝並設定 [通話駐留] 之後, 您必須驗證設定, 以確保停車場和檢索通話如期運作。 至少請確認下列事項:
  
- 呼叫已啟用通話駐留且使用者寄存通話的使用者。
    
    > [!NOTE]
    > 如果您在執行此測試前, 在語音原則中啟用通話駐留, 停用通話的使用者需要登出商務用 Skype, 然後重新登入, 才能在轉移通話清單中看到通話寄存選項。 
  
- 撥打軌道數位以取得通話。
    
- 停用另一個通話, 讓撥出通話超時, 而且不要挑選 ringback。 確認超時通話正確地路由至指定給**OnTimeoutURI**的回退目的地。
    

