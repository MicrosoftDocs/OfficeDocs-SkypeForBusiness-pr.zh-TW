---
title: 透過商務用 Skype Server 中的工作部署通話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: '摘要: 瞭解如何在商務用 Skype Server 中針對部分或所有使用者部署通話。'
ms.openlocfilehash: d1c55e44cae944664a51eaddb2ad54e758d4f52c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234521"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>透過商務用 Skype Server 中的工作部署通話
 
**摘要:** 瞭解如何透過商務用 Skype Server 中的工作, 為部分或所有使用者部署通話。
  
使用這些步驟來為您的使用者部署通話。 規劃[使用商務用 Skype Server 中的工作來進行通話](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)的規劃考慮。 在舊版 Lync Server 遠端通話控制中, 這項功能可讓使用者使用 Lync Server 控制其 PBX 手機。 在商務用 Skype Server 中, 此功能已由 [透過工作通話] 取代。 
  
## <a name="prerequisites-for-call-via-work"></a>透過工作進行通話的先決條件

[透過公司通話] 使用整合通訊 Web API (UCWA), 它會自動安裝在所有商務用 Skype Server 前端伺服器上。 若要讓使用者能夠透過公司通話, 您也必須準備好下列先決條件: 
  
- 您必須部署中繼伺服器, 要麼是作為前端伺服器的一部分, 要麼是獨立角色。 您也必須部署 IP PBX 閘道。
    
- 所有將透過工作啟用呼叫的使用者, 都必須在 PBX 電話系統上進行直接撥出 (已執行)。 
    
- 您必須透過企業語音的工作使用者來啟用所有通話。 當您這麼做時, 必須針對對應的 PBX 電話系統, 將每個使用者的商務用 Skype 的號碼設定為相對應的號碼。 
    
- 在其商務用 Skype 用戶端的 [**高級**連線] 選項中, 所有將透過工作使用呼叫的使用者, 都必須已選取 [**自動**設定]。 這可讓用戶端探索 UCWA Url。 [**自動**設定] 是預設的選取專案。
    
- 針對每個使用者的呼叫, 請啟用來電轉接及同時撥打。 
    
- 針對每個工作使用者的通話, 請確定已啟用電話撥入式會議和會議撥出功能。 這可讓這些使用者進入和登出商務用 Skype 會議。
    
- 確保透過工作使用者針對每個通話停用委派、小組通話及回應群組。
    
## <a name="deploy-call-via-work"></a>部署從公司撥號功能

在先決條件就緒之後, 請執行下列動作:
  
- 為您的部署建立全域電話號碼, 該商務用 Skype 會在 PBX 來電者 ID 上顯示的是透過工作通話撥打的使用者。 
    
- 透過工作原則建立一或多個通話
    
- 將 [透過工作原則撥打電話] 指派給每個將可透過工作通話的使用者
    
### <a name="create-the-call-via-work-global-phone-number"></a>透過公司全球電話號碼建立通話

- 輸入下列 Cmdlet
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    例如, 下列 Cmdlet 會將全域電話號碼設定為1-555-123-4567。
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>透過工作原則建立通話

- 輸入下列 Cmdlet
    
  ```
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    例如, 下列 Cmdlet 會透過名為 ContosoUser1CvWP 的工作原則建立通話, 要求使用者使用系統管理員回撥號碼, 並將該回撥號碼設定為1-555-789-1234。
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>透過工作原則指派通話給使用者

- 輸入下列 Cmdlet
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    例如, 下列 Cmdlet 會透過工作原則 "ContosoUser1CvWP" 將呼叫指派給名為**ContosoUser1**的使用者。
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>另請參閱

[透過商務用 Skype Server 中的工作規劃通話](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

