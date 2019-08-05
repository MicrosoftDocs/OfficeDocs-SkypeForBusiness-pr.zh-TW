---
title: 規劃商務用 Skype Server 的位置原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: 請閱讀本主題, 以瞭解如何在商務用 Skype Server Enterprise Voice 中規劃增強式緊急服務 (E9-1) 部署的位置原則。
ms.openlocfilehash: 8f21a5a0f54fbeaca4c46ed51bf4dafe4c2a3dcb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187648"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a>規劃商務用 Skype Server 的位置原則
 
請閱讀本主題, 以瞭解如何在商務用 Skype Server Enterprise Voice 中規劃增強式緊急服務 (E9-1) 部署的位置原則。 
  
> [!NOTE]
> 商務用 Skype 伺服器現在支援設定用戶端的多個緊急電話號碼。 如果您想要設定多個緊急電話號碼, 您必須遵循[規劃商務用 Skype Server 中的多個緊急電話號碼](multiple-emergency-numbers.md), 並在[商務用 skype 中設定多個緊急電話](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)號碼。 
  
您可以使用商務用 Skype 的 [控制台] 或使用[CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) Cmdlet 來建立位置原則。 如需詳細資訊, 請參閱[在商務用 Skype Server 中建立位置原則](../../deploy/deploy-enterprise-voice/create-location-policies.md)。
  
每個位置原則都包含下列資訊:
  
 **啟用增強型9-1-1**
  
啟用此值時, 會啟用用戶端以增強緊急服務 (E9-1-1)。 用戶端註冊時, 它會嘗試從位置資訊服務取得位置, 並將位置資訊包含在緊急通話的一部分。
  
 **位置**
  
此設定僅在啟用 [**啟用增強型 9-1-1** ] 時使用。
  
您可以設定**位置**設定, 以定義用戶端行為, 如下所示:
  
- 將此值設定為 [**否**] 表示系統不會提示使用者輸入位置。
    
- 將此值設定為 **[是]** 表示系統會提示使用者輸入位置, 但可以關閉提示。
    
- 將此值設定為 [**免責聲明**] 表示系統會提示使用者輸入位置, 而且在他們嘗試關閉提示時也會顯示免責聲明。 在任何情況下, 使用者都可以繼續使用用戶端。
    
> [!NOTE]
> 如果使用者在啟用 E9 前手動輸入位置, 則不會顯示免責聲明文字-1-1。 已查看免責聲明的使用者將不會看到免責聲明文字的更新。 
  
 **增強的緊急服務免責聲明**
  
此設定會指定使用者在關閉位置提示時所看到的免責聲明。 在商務用 Skype Server 中, 您可以使用位置原則, 針對不同的地區設定或不同的使用者集設定不同的免責聲明。
  
 **緊急撥號字串 (E9-1-1 個撥號號碼)**
  
這個撥號字串 (較少前導 "+", 但包含使用者撥號計畫所完成的任何正常化) 表示通話是緊急通話。 [**緊急撥號字串**] 會讓用戶端在通話中加入位置和回呼資訊。
  
> [!NOTE]
> 如果您的組織未使用外部線路存取首碼, 您就不需要建立對應的撥號方案正常化規則, 在執行商務用 Skype Server 的伺服器上, 將呼叫新增至911字串。[+] 會自動前置商務用 Skype 用戶端, 因為位置原則。 不過, 如果您的網站使用外部存取前置詞, 您必須將正常化規則新增到可分割外部存取前置詞的適用撥號方案原則, 並新增 "+"。 例如, 如果您的位置使用外部存取首碼 9, 且使用者將 9 911 撥打電話給您, 則在呼叫者的位置設定檔中, 用戶端將會使用其撥號方案原則將此值與 + 911 標準化。 
  
 **緊急撥號字串遮罩 (E9-1-1) 撥號遮罩)**
  
以分號分隔的撥號字串清單, 可翻譯成指定的**緊急撥號字串**。 例如, 您可能會想要新增 112, 這是大多數歐洲的緊急服務號碼。 從歐洲造訪商務用 Skype 使用者可能不知道911是美國的緊急電話號碼, 但他們可以撥打112並取得相同的結果。 就像緊急撥號字串一樣, 請不要在每個數位前加上 "+", 而且如果您使用外部線路存取代碼, 請務必在使用者的撥號計畫原則中有正常化規則來剝離存取代碼位數。
  
 **PSTN 使用量**
  
PSTN 使用的名稱, 其中包含判斷哪些 SIP 幹線、PSTN 閘道或 ELIN 閘道緊急呼叫將前往的路由路徑。
  
> [!NOTE]
> 位置原則只能指派一個用法。 此 PSTN 使用會覆寫指派給使用者語音原則的 PSTN 使用量, 但只適用于緊急撥號字串或其中一個緊急撥號字串遮罩的呼叫。 
  
 **通知 URI**
  
指定在發出緊急通話時接收立即訊息 (IM) 通知的安全性人員的一個或多個 SIP Uri。 支援通訊群組。
  
 **會議 URI**
  
指定在發出緊急通話時, 應 conferenced 的直接向內撥號 (已登錄) 號碼 (通常是安全服務台號碼)。 
  
 **會議模式**
  
指定是否要使用單向或雙向通訊, 將會議 URI conferenced 到緊急通話中。 
  
 **位置重新整理間隔**
  
指定從位置資訊服務傳送位置更新之用戶端要求的時間長度 (以小時為單位)。 這個值可以設定為1到12之間的任何值。 預設值為4。
  

