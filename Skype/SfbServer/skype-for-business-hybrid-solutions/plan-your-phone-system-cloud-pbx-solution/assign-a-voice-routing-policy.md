---
title: 指派語音路由原則
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 摘要：閱讀此主題以瞭解如何使用具有內部部署 PSTN 連線的電話系統，為使用者指派語音原則。
ms.openlocfilehash: f01fcc314cd618150df2c67a2de8b4ea3ee8f9bd7fdb5f4a4c8b3ae24537ee3f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282995"
---
# <a name="assign-a-voice-routing-policy"></a>指派語音路由原則
 
> [!Important]
> 商務用 Skype線上將于2021年7月31日停用，在此之後將無法再存取服務。  此外，您的內部部署環境之間的 PSTN 連線是否會有商務用 Skype Server 或雲端連接器 Edition 和商務用 Skype 線上，都不再支援。  瞭解如何使用[直接路由](/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話語音網路連線至 Teams。

**摘要：** 閱讀此主題以瞭解如何使用具有內部部署 PSTN 連線的電話系統，將語音原則指派給使用者。 
  
當使用者在線上商務用 Skype，並使用內部部署 PSTN 連線電話系統時，會將兩個語音原則套用至他們。 一個是內部部署語音路由原則，您將會指派給內部部署。 這個原則可以是全域或使用者特有的，也可以定義哪些 PSTN 使用方式記錄與使用者相關聯。 本主題說明如何指派此原則。
  
其他語音原則定義使用者可以使用哪些通話功能;這個語音原則是由 Microsoft 定義的，且與內部部署 PSTN 連線使用者的所有電話系統都是相同的。 它會自動指派給電話系統使用者。
  
||**內部部署使用者**|**使用內部部署 PSTN 連線使用者電話系統**|
|:-----|:-----|:-----|
|通話中定義的功能  <br/> |語音原則  <br/> |預先定義的語音原則，會在使用者授權電話系統時自動指派。  <br/> |
|關聯的 PSTN 使用方式記錄  <br/> |語音原則  <br/> |語音路由原則，已指派使用者仍在內部部署。  <br/> |
   
您可以執行下列步驟使用內部部署，而使用者仍是位於內部部署中。
  
## <a name="using-a-global-voice-routing-policy"></a>使用全域語音路由原則

使用內部部署 pstn 連線使用者的電話系統通用語音路由原則之前，您必須將 PSTN 使用方式記錄新增至原則。
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>將 PSTN 使用方式記錄指派給全域語音路由原則

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
3. 將 PSTN 使用方式記錄新增至原則：
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    例如：
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a>建立新的語音路由原則

### <a name="to-create-a-new-voice-routing-policy"></a>若要建立新的語音路由原則

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
3. 建立新的語音路由原則：
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    例如：
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

此範例會建立名為 HybridVoice 的新語音路由原則，該原則有兩個相關聯的 PSTN 使用方式。
  
## <a name="assigning-a-voice-routing-policy"></a>指派語音路由原則

不論您使用的是通用語音路由原則還是特定使用者，請使用下列步驟將原則指派給使用者。
  
### <a name="to-assign-the-voice-routing-policy"></a>指派語音路由原則

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
3. 將現有的語音原則指派給使用者：
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    例如：
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

在此範例中，具有顯示名稱小明凱利的使用者會指派給先前建立的語音原則，名稱為 HybridVoice。
  
如需有關語音路由策略的詳細資訊，請參閱[建立或修改語音原則和設定 PSTN 使用方式記錄的商務用 Skype 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md)、 [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)及[Grant-CsVoicePolicy](/powershell/module/skype/grant-csvoicepolicy?view=skype-ps)。
