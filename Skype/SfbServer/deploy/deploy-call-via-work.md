---
title: 從商務用 Skype Server 中的工作部署通話
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 摘要：瞭解如何在部分或所有使用者的商務用 Skype Server 中，部署通話的功能。
ms.openlocfilehash: ce4c49a1ba8766dbec6efbfe2b04ea91702eadf40c91cb6108f027765609cac4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303157"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>從商務用 Skype Server 中的工作部署通話
 
**摘要：** 瞭解如何在商務用 Skype Server 中為部分或所有使用者部署通話的功能。
  
使用下列步驟，為您的使用者部署「透過運作」的呼叫。 規劃[從商務用 Skype Server 中的工作進行通話](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)時，會討論規劃的考慮。 在舊版的 Lync Server 遠端呼叫控制中，有一個功能可讓使用者透過 Lync Server 控制其 PBX 電話。 在商務用 Skype Server 中，此功能已由「透過運作」的呼叫取代。 
  
## <a name="prerequisites-for-call-via-work"></a>從公司通話的必要條件

「透過公司通話」使用整合通訊 Web API (UCWA) ，它會自動安裝在所有商務用 Skype Server 前端伺服器上。 若要讓使用者能夠透過公司通話，您也必須具備下列必要條件： 
  
- 您必須已部署轉送伺服器，既可以作為前端伺服器的一部分，也可以是獨立的角色。 您也必須部署 IP-PBX 閘道。
    
- 所有可透過工作進行呼叫的使用者，都必須在 PBX 電話系統上) 直接向內撥號 (。 
    
- 您必須啟用企業語音的所有使用者呼叫。 當您執行此動作時，您必須將每位使用者的商務用 Skype 的號碼，設定為對應之 PBX 電話系統的對應號碼。 
    
- 所有將使用「從公司撥號」的使用者，都必須在其商務用 Skype 用戶端的 [ **Advanced Connections** ] 選項中選取 **自動** 設定。 這可讓用戶端探索 UCWA URLs。 [**自動** 設定] 是預設的選取範圍。
    
- 針對每位使用者的通話，啟用來電轉接和同時響鈴。 
    
- 針對透過工作使用者的每一個呼叫，請確定已啟用電話撥入式會議和會議撥出功能。 這可讓這些使用者進入和商務用 Skype 會議。
    
- 確定已透過工作使用者的每一個呼叫停用委派、小組通話及回應群組。
    
## <a name="deploy-call-via-work"></a>部署從公司撥號功能

準備好必要條件後，請執行下列動作：
  
- 為您的部署建立全域電話號碼，商務用 Skype 會在 PBX 來電者 ID 上顯示，以供透過通話通話的使用者使用。 
    
- 透過工作原則建立一或多個通話
    
- 將「透過工作原則的來電」指派給將啟用透過工作呼叫的每位使用者
    
### <a name="create-the-call-via-work-global-phone-number"></a>透過工作通用電話號碼建立通話

- 輸入下列 Cmdlet
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    例如，下列 Cmdlet 會將全域電話號碼設定為1-555-123-4567。
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>通過工作原則建立通話

- 輸入下列 Cmdlet
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    例如，下列 Cmdlet 會透過名為 ContosoUser1CvWP 的工作原則建立呼叫，要求使用者使用系統管理員回撥號碼，並將該回撥號碼設定為1-555-789-1234。
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>將透過工作原則的呼叫指派給使用者

- 輸入下列 Cmdlet
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    例如，下列 Cmdlet 會將呼叫從工作原則 "ContosoUser1CvWP" 指派給名為 **ContosoUser1** 的使用者。
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>另請參閱

[規劃商務用 Skype Server 中的工作通話](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

