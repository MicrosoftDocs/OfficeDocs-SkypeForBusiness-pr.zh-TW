---
title: 如何在貴組織中使用本機號碼
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.voice.callerid.overview
ms.custom:
- Calling Plans
description: 您可以使用稱為 CallingLineIdentity 的原則, 控制撥打電話給電話系統使用者的撥入和撥出電話的本機號碼。
ms.openlocfilehash: 31948a8361d8ae5a15ce84549d982d0c7f9adf1b
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2019
ms.locfileid: "36484034"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>如何在貴組織中使用本機號碼

您可以使用稱為 CallingLineIdentity 的原則, 控制撥打電話給電話系統使用者的撥入和撥出電話的本機號碼。
  
不論 PSTN 連線為何, 所有的電話系統使用者都能使用本機號碼功能:
  
- 線上 PSTN 連線能力
    
- 與商務用 Skype 雲端連接器版本的內部部署 PSTN 連線 (需要雲端連接器版本1.4.2 及以上版本)
    
- 與商務用 Skype Server 的內部部署 PSTN 連線 (需要商務用 Skype Server 2015 CU5 及以上版本)
    
> [!NOTE]
> 此原則在商務用 Skype 2015 Server 中無法使用。 
  
## <a name="outbound-caller-id"></a>輸出來電者識別碼

輸出 PSTN 來電者識別碼有三個可用的選項:
  
- 指派給使用者的電話號碼, 這是預設值。
    
- 在 Office 365 電話號碼庫存的通話方案中, 歸類為*服務*和*免付費*電話號碼的電話號碼。 它通常會指派給組織的自動回應或通話佇列。
    
- 設為 [匿名]。
    
不過, 您無法將這些類型的電話號碼指派給輸出來電者識別碼:
  
- 在通話方案中分類為*使用者*的任何電話號碼, 電話號碼庫存
    
- 商務用 Skype Server 內部部署電話號碼
    
若要設定輸出本機號碼, 請參閱[設定使用者的本機號碼](/microsoftteams/set-the-caller-id-for-a-user)。
  
### <a name="end-user-control-of-outbound-caller-id"></a>終端使用者控制撥出本機號碼

EnableUserOverride 屬性可讓單一或多個使用者將其本機號碼設定變更為**Anonymous**。 這僅適用于使用 LineURI 或替代品的 CallingIDSubstitute 參數設定 CallingLineIdentity 原則時。 EnableUserOverride 的預設值為 False。
  
您的使用者可以使用商務用 Skype 電腦版用戶端中的 [**設定**] 索引標籤, 將其本機號碼設定為**匿名**, 選取 [**呼叫使用者**] (如果系統管理員已啟用), 選取 [**隱藏所有通話的電話號碼和設定檔資訊]**.
  
||||
|:-----|:-----|:-----|
|**時間** <br/> |**版本** <br/> |**受** <br/> |
|隨選即用  <br/> |目前已于2016年12月6日發行的頻道-版本 1611 (組建 7571.2072)  <br/> |是的  <br/> |
|隨選即用  <br/> |1701 2017 年2月22日 (組建 7766.2060) 發行之推遲通道的第一個發行版本本  <br/> |是的  <br/> |
|隨選即用  <br/> |已于2017年6月13日發行的延遲頻道-版本 1701 (組建 7766.2092)  <br/> |是的  <br/> |
|.MSI  <br/> |商務用 Skype  <br/> |不  <br/> |
|版  <br/> |商務用 Skype  <br/> |不  <br/> |
   
## <a name="inbound-caller-id"></a>呼入本機號碼

BlockIncomingCallerID 屬性可讓您封鎖撥入的 PSTN 電話上的本機號碼。 您可以設定此屬性, 但您的使用者在 [使用者設定] 頁面上無法使用您的最終使用者。 目前只有線上 PSTN 連線才能使用此功能。
  
若要設定輸出本機號碼, 請參閱[設定使用者的本機號碼](/microsoftteams/set-the-caller-id-for-a-user)。
  
## <a name="related-topics"></a>相關主題
[傳送電話號碼常見問題](/microsoftteams/transferring-phone-numbers-common-questions)

[通話方案所用的不同類型的電話號碼](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[管理貴組織的電話號碼](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話條款與條件](/microsoftteams/emergency-calling-terms-and-conditions)

[商務用 Skype Online: 緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
