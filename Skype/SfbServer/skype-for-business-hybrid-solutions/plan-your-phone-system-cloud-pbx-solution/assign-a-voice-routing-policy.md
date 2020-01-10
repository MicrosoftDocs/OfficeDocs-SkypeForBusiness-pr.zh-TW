---
title: 指派語音路由策略
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 摘要：請閱讀本主題，以瞭解如何在 Office 365 中使用電話系統以內部部署 PSTN 連線來指派語音原則。
ms.openlocfilehash: fc1bf50eabc1b596ba54e3447c0357cfd304ad2c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003033"
---
# <a name="assign-a-voice-routing-policy"></a>指派語音路由策略
 
**摘要：** 請閱讀本主題，以瞭解如何在 Office 365 中使用電話系統與內部部署 PSTN 連線來指派語音原則。 
  
一旦使用者位於商務用 Skype Online，且使用 Office 365 中的電話系統與內部部署 PSTN 連線，就會套用兩個語音原則。 一個是您將在內部部署指派的內部部署語音路由原則。 這個原則可以是全域或使用者專用的，並定義哪些 PSTN 使用記錄與使用者相關聯。 本主題說明如何指派此原則。
  
其他語音原則定義使用者可以使用的通話功能。此語音原則是由 Microsoft 定義，且與內部部署 PSTN 連線使用者在 Office 365 中的所有電話系統都是相同的。 系統會自動將它指派給 Office 365 使用者中的 [電話系統]。
  
||**內部部署使用者**|**Office 365 中的電話系統與內部部署 PSTN 連線使用者**|
|:-----|:-----|:-----|
|中定義的通話功能  <br/> |語音原則  <br/> |預先定義的語音原則，在使用者使用 Office 365 中的電話系統授權時自動指派。  <br/> |
|關聯的 PSTN 使用記錄  <br/> |語音原則  <br/> |語音路由策略，在使用者仍在內部部署時指派。  <br/> |
   
您可以使用內部部署部署執行下列步驟，而使用者仍在內部部署的部署中。
  
## <a name="using-a-global-voice-routing-policy"></a>使用全域語音路由策略

您必須先將 PSTN 使用記錄新增至原則，才能在 Office 365 中的電話系統中使用全域語音路由策略。
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>將 PSTN 使用記錄指派給全域語音路由策略

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。
    
3. 將 PSTN 使用記錄新增至原則：
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    例如：
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a>建立新的語音路由策略

### <a name="to-create-a-new-voice-routing-policy"></a>若要建立新的語音路由策略

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。
    
3. 建立新的語音路由策略：
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    例如：
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

這個範例會建立名為 HybridVoice 的新語音路由策略，其中有兩個與它相關聯的 PSTN 用法。
  
## <a name="assigning-a-voice-routing-policy"></a>指派語音路由策略

不論您使用的是全域語音路由策略，還是使用者專用的，請使用下列步驟將原則指派給使用者。
  
### <a name="to-assign-the-voice-routing-policy"></a>指派語音路由策略

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。
    
3. 將現有的語音原則指派給使用者：
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    例如：
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

在這個範例中，將顯示名稱 Bob 凱利的使用者指派給先前建立的名稱為 HybridVoice 的語音原則。
  
如需有關語音路由策略的詳細資訊，請參閱[建立或修改語音原則，以及在商務用 Skype 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md)、[新-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)及[贈與 CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps)中設定 PSTN 使用記錄。
  

