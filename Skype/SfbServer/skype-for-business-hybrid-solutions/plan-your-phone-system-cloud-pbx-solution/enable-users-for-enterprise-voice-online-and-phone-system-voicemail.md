---
title: 為使用者啟用 Office 365 語音信箱中的企業語音線上版和電話系統
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
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
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: 瞭解如何在商務用 Skype 使用者的 Office 365 語音服務中啟用電話系統。
ms.openlocfilehash: 902d2e1bad76c8275bfc8f4ce7ec7b4243b8572a
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003463"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a>為使用者啟用 Office 365 語音信箱中的企業語音線上版和電話系統
 
瞭解如何在商務用 Skype 使用者的 Office 365 語音服務中啟用電話系統。
  
在 Office 365 中使用內部部署 PSTN 連線來部署電話系統的最後一個步驟是，在 Office 365 和語音信箱中，為您的使用者提供手機系統功能。 若要啟用這些功能，您必須是具備 Office 365 全域系統管理員角色的使用者，並且能夠執行遠端 PowerShell。 您必須遵循本主題中的步驟，找出尚未針對商務用 Skype Online 啟用 Enterprise Voice 的所有使用者帳戶。
  
## <a name="enable-phone-system-in-office-365-voice-services"></a>在 Office 365 語音服務中啟用電話系統

若要讓使用者在 Office 365 語音及語音信箱中使用電話系統，您必須執行一些初始步驟，例如檢查您的伺服器是否已部署商務用 Skype Online 連接器，並允許您的使用者擁有託管語音信箱。
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a>在 Office 365 語音及語音信箱中，為您的使用者啟用電話系統

1. 開始之前，請檢查您的前端伺服器上是否已部署商務用 Skype Online 連接器（Windows PowerShell 模組）。 如果不是，您可以從[下載中心](https://www.microsoft.com/en-us/download/details.aspx?id=39366)下載它。 您可以在[針對商務用 Skype Online 管理設定您的電腦](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx)上，找到有關使用此模組的詳細資訊。
    
2. 以系統管理員身分啟動 Windows PowerShell。
    
3. 輸入下列內容，然後按 Enter 鍵：
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. 輸入下列內容，然後按 Enter 鍵：
    
   ```powershell
   $cred = Get-Credential
   ```

    按 Enter 之後，您應該會看到 [Windows PowerShell 認證] 對話方塊。
    
5. 輸入您的租使用者管理員的使用者名稱和密碼，然後按一下 **[確定]**。
    
6. 在 PowerShell 視窗中，輸入下列內容，然後按 Enter 鍵：
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. 輸入下列 Cmdlet 來匯入會話：
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    當您在商務用 Skype 伺服器上執行 PowerShell 時，在您開啟 PowerShell 時會載入本機商務用 Skype Cmdlet。 您必須指定-AllowClobber 參數，才能讓線上 Cmdlet 覆寫相同名稱的內部部署 Cmdlet。
    
8. 使用 Move-csuser Cmdlet 來指派 $EnterpriseVoiceEnabled，並 $HostedVoiceMail 屬性指派給使用者，如下所示：
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    例如：
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > 您也可以透過其 SIP 位址、使用者主體名稱（UPN）、功能變數名稱與使用者名（[Bob]），以及 Active Directory 中的顯示名稱來指定使用者（「Bob 凱利」）。 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a>更新在 Office 365 中為手機系統啟用的使用者的行 URI 和撥號方案

本節說明如何在 Office 365 中為已啟用電話系統的使用者更新行 URI 與撥號計畫。 
  
### <a name="to-update-the-line-uri"></a>更新行 URI

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2. 使用 [開始] 功能表或 [桌面] 快捷方式來開啟商務用 Skype Server 的 [控制台]。
    
    > [!NOTE]
    > 您也可以開啟瀏覽器視窗，然後輸入系統管理員 URL 來開啟商務用 Skype Server 的 [控制台]。 
  
3. 在左側導覽列中，按一下 [**使用者**]。
    
4. 在 [**搜尋使用者**] 方塊中，輸入您要啟用的使用者帳戶的全部或第一部分的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI），然後按一下 [**尋找**]。
    
5. 在表格中，按一下您想要變更行 URI 的商務用 Skype 使用者帳戶。
    
6. 按一下 [**行 URI**]，然後輸入唯一的、標準化的電話號碼（例如電話： + 14255550200）。 然後按一下 [**確認**]。
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>使用內部部署的 Windows PowerShell Cmdlet 更新撥號方案

您可以將每個使用者的撥號方案指派給 Windows PowerShell 和[Grant CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) Cmdlet。 您可以從商務用 Skype Server 2015 或從 Windows PowerShell 遠端會話中執行此 Cmdlet。
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>若要將每個使用者的撥號方案指派給單一使用者

- 使用[授與 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) Cmdlet，將每個使用者的撥號方案 RedmondDialPlan 指派給使用者 Ken Myer：
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>若要將每個使用者的撥號方案指派給多個使用者

- 下列命令會將每個使用者的撥號方案 RedmondDialPlan 指派給在雷德蒙者所在城市的所有使用者。 如需此命令中使用之 LdapFilter 參數的詳細資訊，請參閱[move-csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) Cmdlet 的相關檔：
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> 您可以針對線上使用者使用全域或使用者撥號方案。 無法使用網站撥號計畫，因為這些方案只適用于內部部署的使用者，且已指派至內部部署網站。 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>取消指派每個使用者的撥號方案

- 使用[授與 CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) Cmdlet，取消指派先前指派給 Ken Myer 的任何每使用者撥號方案。 未指派每個使用者的撥號方案後，會使用全域撥號方案或指派給其註冊機構或 PSTN 閘道的服務範圍撥號方案，自動管理 Ken Myer。 服務範圍撥號計畫的優先順序高於全域撥號方案：
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>使用內部部署的 Windows PowerShell Cmdlet 更新語音路由策略

本節說明如何在 Office 365 中針對啟用電話系統的使用者更新語音路由策略。
  
Office 365 使用者中的電話系統必須已獲指派語音路由策略，才能讓呼叫順利路由。 這與需要指派語音原則的內部部署商務語音使用者不同，允許呼叫順利路由。 語音路由策略應包含 PSTN 用途，這些用法定義 Office 365 使用者中的電話系統的授權呼叫和路線。 您可以將這些 PSTN 用途從現有的語音原則複製到新的語音路由策略。 如需詳細資訊，請參閱[新 CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)。
  
> [!NOTE]
> Office 365 使用者中的所有電話系統都會獲指派名為 BusinessVoice 的相同線上語音原則，以定義所允許的通話功能;例如，允許同時撥打。 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>將每位使用者的語音路由策略指派給單一使用者

- 使用[授與 CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) Cmdlet，將每位使用者的語音路由原則 RedmondVoiceRoutingPolicy 指派給使用者 Ken Myer：
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>將每個使用者的語音路由策略指派給多個使用者

- 下一個命令會將每個使用者的語音路由原則 RedmondVoiceRoutingPolicy 指派給所有在雷德蒙者中工作的使用者。 如需此命令中使用之 LdapFilter 參數的詳細資訊，請參閱[move-csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)。
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > 您可以使用全域或使用者語音路由策略來進行線上使用者。 無法使用網站語音路由策略，因為這些原則只適用于內部部署的使用者，且已指派至內部部署網站。 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>若要取消指派每位使用者的語音路由策略

- 使用授與 CsVoiceRoutingPolicy 取消指派先前指派給 Ken Myer 的任何每使用者語音路由原則。 未指派每個使用者的語音路由策略之後，Ken Myer 將會使用全域語音路由策略自動進行管理。
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    如需詳細資訊，請參閱[授與 CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)。
    

