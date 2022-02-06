---
title: ' (選用) 在商務用 Skype 中驗證通話駐留部署'
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: 在商務用 Skype Server 企業語音中驗證通話駐留的部署。
---

# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a> (選用) 在商務用 Skype 中驗證通話駐留部署
 
在商務用 Skype Server 企業語音中驗證通話駐留的部署。 
  
安裝及設定通話駐留後，您必須確認設定，以確定停車場和取回通話如預期般地運作。 請至少確認下列項目：
  
- 呼叫已啟用通話駐留且使用者寄存通話的使用者。
    
    > [!NOTE]
    > 如果您在執行此測試之前，在語音原則中啟用通話駐留，則寄存通話的使用者必須登出商務用 Skype，然後重新登入，才能在轉接通話清單中看到通話駐留選項。 
  
- 撥打軌道號碼以取得通話。
    
- 寄存另一次通話，讓寄存通話超時，但不要挑選回電。 確認已超時呼叫已正確路由傳送至 **OnTimeoutURI** 所指定的回退目的地。
    

