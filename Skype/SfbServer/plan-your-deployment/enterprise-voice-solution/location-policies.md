---
title: 規劃商務用 Skype Server 的位置原則
ms.reviewer: ''
ms.author: v-cichur
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
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: 閱讀此主題以瞭解如何在商務用 Skype Server 企業語音中規劃增強型緊急服務 (E9-1-1) 部署的位置原則。
ms.openlocfilehash: b250108fb20a9a1d75069b1036ab7c2fba332443
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601408"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a>規劃商務用 Skype Server 的位置原則
 
閱讀此主題以瞭解如何在商務用 Skype Server 企業語音中規劃增強型緊急服務 (E9-1-1) 部署的位置原則。 
  
> [!NOTE]
> 商務用 Skype Server 現在支援用戶端的多個緊急號碼的設定。 如果您想要設定多個緊急號碼，您必須遵循在[商務用 Skype Server 中規劃多個緊急](multiple-emergency-numbers.md)號碼的資訊，並在[商務用 Skype 中設定多個緊急號碼](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)。 
  
您可以使用商務用 Skype 控制台] 或使用[New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) Cmdlet 來建立位置原則。 如需詳細資訊，請參閱[在商務用 Skype Server 中建立位置原則](../../deploy/deploy-enterprise-voice/create-location-policies.md)。
  
每個位置原則都包含下列資訊：
  
 **啟用增強型9-1-1**
  
啟用此值時，會為用戶端啟用增強型緊急服務， (E9-1-1) 。 當用戶端註冊時，它會嘗試從 Location 資訊服務取得位置，並將位置資訊包含在緊急通話的一部分中。
  
 **Location**
  
只有在啟用 **增強型 9-1-1** 時，才會使用此設定。
  
您可以設定 **位置** 設定，以定義用戶端行為，如下所示：
  
- 將值設為 [ **否** ] 表示將不會提示使用者輸入位置。
    
- 將值設為 **[是]** ，表示系統會提示使用者輸入位置，但可以關閉提示。
    
- 將值設定為 **免責聲明** 表示會提示使用者輸入位置，而且會在使用者嘗試消除提示時顯示免責聲明。 在所有情況下，使用者都可以繼續使用用戶端。
    
> [!NOTE]
> 若使用者在啟用 E9-1-1 前手動輸入位置，將不會顯示免責聲明文字。 已查看免責聲明的使用者將不會查看免責聲明文字的更新。 
  
 **增強型緊急服務免責聲明**
  
此設定指定使用者在其取消提示的位置時所看到的免責聲明。 在商務用 Skype Server 中，您可以使用位置原則為不同的地區設定或不同的使用者集合設定不同的免責聲明。
  
 **緊急撥號字串 (E9-1-1 撥號號碼)**
  
此撥號字串 (較少的前置 "+"，但包含使用者撥號對應表所完成的任何正規化) 表示通話是緊急通話。 [ **緊急撥號] 字串** 會使用戶端在通話中包含位置和回呼資訊。
  
> [!NOTE]
> 如果您的組織未使用外部線路存取首碼，您不需要建立對應的撥號對應表正規化規則，可在執行商務用 Skype Server 的伺服器上的呼叫輸出路由傳送呼叫之前，將 "+" 新增至911字串。「+」會因位置原則而自動加上商務用 Skype 用戶端。 不過，如果您的網站使用外部存取前置詞，您必須將正規化規則新增至適用的撥號對應表原則，以去掉外部存取前置詞並新增 "+"。 例如，如果您的位置使用外部存取前置詞9，而且使用者可撥打 9 911 撥打緊急電話，用戶端會使用其撥號對應表原則，在來電者位置設定檔中的路由評估撥號號碼之前，先將此值標準化為 + 911。 
  
 **緊急撥號字串遮罩 (E9-1-1 撥號遮罩)**
  
以分號分隔的撥號字串清單，可轉譯成指定的 **緊急撥號字串**。 例如，您可能想要新增112，也就是歐洲大多數的緊急服務號碼。 來自歐洲的來訪商務用 Skype 使用者可能不會知道911是美國的緊急電話號碼，但可以撥打112並取得相同結果。 如使用緊急撥號字串，請勿在每個號碼前加上 "+"，而且如果您使用外部行存取碼，請確定使用者的撥號對應表原則中有正規化規則可去掉存取碼位。
  
 **PSTN 使用方式**
  
PSTN 使用方式的名稱，此介面包含決定 SIP 主幹、PSTN 閘道或 ELIN 閘道緊急通話將前往的路由路徑。
  
> [!NOTE]
> 一個位置原則只能有一個可用的使用方式。 這種 PSTN 使用方式會覆寫指派給使用者語音原則的 PSTN 使用方式，但是只適用于撥入緊急撥號字串或其中一個緊急撥號字串遮罩的來電。 
  
 **通知 URI**
  
指定在進行緊急通話時，接收立即訊息 (IM) 通知的安全性人員一或多個 SIP URIs。 支援通訊群組。
  
 **會議 URI**
  
指定「直接向內撥號 (已) 號碼 (通常是) 的安全性服務台號碼，應警衛在緊急通話時進行此設定。 
  
 **會議模式**
  
指定是否要使用單向或雙向通訊，將會議 URI 警衛至緊急通話。 
  
 **位置重新整理間隔**
  
指定從位置資訊服務之位置更新之用戶端要求 (的時間) （以小時為單位）。 此值可設為1到12之間的任何值。 預設值為 4。
