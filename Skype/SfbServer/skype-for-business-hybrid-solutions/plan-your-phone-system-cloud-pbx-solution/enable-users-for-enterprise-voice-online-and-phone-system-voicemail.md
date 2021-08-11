---
title: 為使用者啟用企業語音線上版和電話系統語音信箱
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
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
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: 瞭解如何為您的商務用 Skype 使用者啟用電話系統語音服務。
ms.openlocfilehash: fea5da3bb82281c05edd73ce8e69c7164440513080b7aa804b31abc5d4c65ba7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289071"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a>為使用者啟用企業語音線上版和電話系統語音信箱
 
> [!Important]
> 商務用 Skype線上將于2021年7月31日停用，在此之後將無法再存取服務。  此外，您的內部部署環境之間的 PSTN 連線是否會有商務用 Skype Server 或雲端連接器 Edition 和商務用 Skype 線上，都不再支援。  瞭解如何使用[直接路由](/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話語音網路連線至 Teams。

瞭解如何為您的商務用 Skype 使用者啟用電話系統語音服務。
  
使用內部部署 PSTN 連線部署電話系統的最後一個步驟，就是讓使用者能夠使用電話系統和語音信箱。 若要啟用這些功能，您必須是具有全域系統管理員角色的使用者，而且能夠執行遠端 PowerShell。 您必須依照本主題中的步驟，針對所有尚未啟用企業語音商務用 Skype 線上的使用者帳戶。
  
## <a name="enable-phone-system-voice-services"></a>啟用電話系統語音服務

若要讓使用者能夠電話系統語音及語音信箱，您必須執行一些初始步驟，例如檢查是否已在伺服器上部署商務用 Skype Online 連接器，並為您的使用者啟用主控語音信箱。
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a>若要讓使用者能夠電話系統語音及語音信箱

> [!NOTE]
> 商務用 Skype線上連接器目前是最新 Teams PowerShell 模組的一部分。
> 如果您使用的是最新的[Teams PowerShell 公開版本](https://www.powershellgallery.com/packages/MicrosoftTeams/)，則不需要安裝商務用 Skype 線上連接器。

1. 開始之前，請先檢查 Teams PowerShell 模組是否已安裝在前端伺服器上。 如果不是，請使用[Teams PowerShell 模組安裝](/microsoftteams/teams-powershell-install)中的指示進行安裝。
    
2. 以系統管理員身分啟動 Windows PowerShell。
    
3. 輸入下列專案，然後按 Enter：
    
 ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

  
4. 使用 Set-CsUser Cmdlet，將 $EnterpriseVoiceEnabled 和 $HostedVoiceMail 屬性指派給您的使用者，如下所示：
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    例如：
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > 您也可以使用使用者的 SIP 位址、使用者主體名稱 (UPN) 、功能變數名稱和使用者名稱 (網域 \ 使用者名稱) 及 Active Directory 中的顯示名稱來指定使用者。 ( 「Bob 凱利」 ) 。 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a>為已啟用電話系統的使用者更新行 URI 和撥號對應表

本節說明如何針對為電話系統啟用的使用者更新行 URI 和撥號對應表。 
  
### <a name="to-update-the-line-uri"></a>更新行 URI

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 使用 [[開始] 功能表] 或 [桌面] 快捷方式，開啟 [商務用 Skype Server 控制台]。
    
    > [!NOTE]
    > 您也可以開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 [商務用 Skype Server 控制台]。 
  
3. 在左導覽列中，按一下 **[使用者]**。
    
4. 在 [ **搜尋使用者** ] 方塊中，輸入全部或部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的使用者帳戶，然後按一下 [ **尋找**]。
    
5. 在表格中，按一下您要變更行 URI 的商務用 Skype 使用者帳戶。
    
6. 按一下 [ **行 URI**]，然後輸入唯一的標準化電話號碼 (例如電話： + 14255550200) 。 然後按一下 [ **認可**]。
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>使用內部部署 Windows PowerShell Cmdlet 更新撥號對應表

您可以將個別使用者撥號對應表指派給 Windows PowerShell 和[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) Cmdlet。 您可以從商務用 Skype Server 2015，或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>將每一使用者撥號對應表指派給單一使用者

- 使用 [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) 指令程式，將個別使用者撥號對應表 RedmondDialPlan 指派給使用者 Ken Myer：
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>將每一使用者撥號對應表指派給多位使用者

- 下列命令會將每位使用者的撥號對應表 RedmondDialPlan 指派給 Redmond 的城市中所有工作的使用者。 如需此命令中所使用之 LdapFilter 參數的詳細資訊，請參閱 [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) Cmdlet 的檔：
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> 您可以針對線上使用者使用通用或使用者撥號對應表。 無法使用網站撥號對應表，只適用于裝載內部部署並指派給內部部署網站的使用者。 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>取消指派個別使用者撥號對應表

- 使用 [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) Cmdlet 取消指派先前指派給 Ken Myer 的任何個別使用者撥號對應表。 未指派每個使用者的撥號對應表後，Ken Myer 將會透過使用全域撥號對應表或指派給其註冊機構或 PSTN 閘道的服務範圍撥號對應表，來進行管理。 服務範圍撥號對應表優先于全域撥號對應表：
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>使用內部部署 Windows PowerShell Cmdlet 更新語音路由原則

本節說明如何更新為電話系統啟用之使用者的語音路由策略。
  
電話系統使用者必須將語音路由原則指派給他們，來電才能成功路由傳送。 這與需要將語音原則指派給他們以允許通話成功路由的內部部署商務語音使用者不同。 語音路由原則應包含 PSTN 使用方式，以定義電話系統使用者的授權呼叫和路由。 您可以將這些 PSTN 使用方式從現有的語音原則複製到新的語音路由原則。 如需詳細資訊，請參閱 [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)。
  
> [!NOTE]
> 所有電話系統使用者都被指派了名為 BusinessVoice 的相同線上語音原則，用來定義允許的呼叫功能;例如，允許同時振鈴。 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>將每一使用者的語音路由原則指派給單一使用者

- 使用 [Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) 指令程式將每位使用者的語音路由原則 RedmondVoiceRoutingPolicy 指派給使用者 Ken Myer：
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>將每一使用者的語音路由原則指派給多位使用者

- 下一個命令會將每位使用者的語音路由原則 RedmondVoiceRoutingPolicy 指派給在 Redmond 的城市中工作的所有使用者。 如需此命令中所用 LdapFilter 參數的詳細資訊，請參閱 [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps)。
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > 您可以針對線上使用者使用通用或使用者語音路由策略。 無法使用網站語音路由策略，因為這些原則只適用于內部部署所主控且指派給內部部署網站的使用者。 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>取消指派個別使用者的語音路由原則

- 使用 Grant-CsVoiceRoutingPolicy 取消指派先前指派給 Ken Myer 的任何個別使用者語音路由原則。 未指派每位使用者的語音路由原則之後，將會使用通用語音路由原則來管理 Ken Myer。
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    如需詳細資訊，請參閱 [Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)。
