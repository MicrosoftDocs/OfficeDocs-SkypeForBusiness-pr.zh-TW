---
title: 定義在商務用 Skype Server 中手動取得位置的使用者體驗
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: 在商務用 Skype Server Enterprise Voice 中使用 SIP 中繼提供者在 E9 部署中規劃漫遊使用者。
ms.openlocfilehash: 85bf13325d3c7c16958877d50f49057a7f402226
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802713"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a>定義在商務用 Skype Server 中手動取得位置的使用者體驗
 
在商務用 Skype Server Enterprise Voice 中使用 SIP 中繼提供者在 E9 部署中規劃漫遊使用者。
  
如果用戶端位於網路以外，或未定義的子網中，使用者可以手動輸入位置。 但在緊急通話期間，通話會先傳送到國家/地區 E9-1-1 緊急通話回應中心（ECRC）發送器，然後再傳送到公用安全回應點（PSAP）。 ECRC 將會 verbally 查詢位置的來電者，然後根據提供的資訊將呼叫轉寄至適當的 PSAP。 
  
**如果使用者不是由位置資訊服務自動提供某個位置，系統會提示使用者輸入位置嗎？**
  
例如，如果用戶端位於未定義的子網、在旅館中，或在網路以外的任何地方，使用者是否必須輸入位置？
    
您可以設定位置原則中**所需的位置**設定，以定義用戶端行為。 將此值設定為 [否] 表示系統不會提示使用者輸入位置。 將此值設定為 [是] 表示系統會提示使用者輸入位置，但可以關閉提示。 將此值設定為 [免責聲明] 表示系統會提示使用者輸入位置，且在他們嘗試關閉提示時，會顯示免責聲明。 在任何情況下，使用者都可以照常繼續使用用戶端。
    
當使用者手動輸入位置時，該位置會對應到用戶端網路預設閘道的 MAC 位址，並儲存在用戶端的每個使用者資料表中。 當使用者回到任何先前儲存的位置時，商務用 Skype 用戶端會自動將自己設為該位置。 
  
> [!NOTE]
> 您只能修改用戶端的目前位置，但您也可以刪除儲存在本機使用者資料表中的任何位置。 
  

