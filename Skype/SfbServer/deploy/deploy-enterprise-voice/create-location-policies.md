---
title: 在商務用 Skype Server 中建立位置原則
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
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: 閱讀此主題以瞭解如何在商務用 Skype Server 企業語音中設定增強型緊急服務 (E9-1-1) 位置原則。
---

# <a name="create-location-policies-in-skype-for-business-server"></a>在商務用 Skype Server 中建立位置原則

閱讀此主題以瞭解如何在商務用 Skype Server 企業語音中設定增強型緊急服務 (E9-1-1) 位置原則。 

商務用 Skype Server 會使用位置原則，在用戶端註冊期間為 E9-1-1 啟用商務用 Skype 用戶端。 位置原則包含定義 E9-1-1 將如何執行的設定。 如需詳細資訊，請參閱[Plan location 商務用 Skype Server 的位置原則](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)。

您可以使用商務用 Skype 控制台] 或使用[New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) Cmdlet 來定義位置原則。

> [!NOTE]
> 商務用 Skype Server 現在支援用戶端的多個緊急號碼的設定。 如果您想要設定多個緊急號碼，您必須遵循在[商務用 Skype Server 中規劃多個緊急](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)號碼的資訊，並在[商務用 Skype 中設定多個緊急號碼](configure-multiple-emergency-numbers.md)。 

您可以編輯全域位置原則，並建立新的標記位置原則。 當用戶端不是位於關聯位置原則的子網內，或用戶端尚未直接指派位置原則時，用戶端會取得全域原則。 已將標記原則指派給子網或使用者。 

若要建立位置原則，您必須使用 RTCUniversalServerAdmins 群組成員的帳戶，或是 CsVoiceAdministrator 系統管理角色的成員，或具有相等的系統管理員許可權。

如需詳細資訊，請參閱[Plan location 商務用 Skype Server 的位置原則](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)。 此程式中的 Cmdlet 使用使用下列值定義的位置原則。 如需 Cmdlet 參數和值的完整說明，請參閱 [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps)。


| **元素**                               | **值**                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| EnhancedEmergencyServicesEnabled  <br/>   | **True** <br/>                                                                                                                                                                     |
| LocationRequired  <br/>                   | **免責聲明** <br/>                                                                                                                                                               |
| EnhancedEmergencyServiceDisclaimer  <br/> | 您的公司原則需要您設定位置。 如果您未設定位置，緊急服務將無法在緊急情況下找到您。 請設定位置。  <br/> |
| UseLocationForE911Only  <br/>             | **False** <br/>                                                                                                                                                                    |
| PstnUsage  <br/>                          | **EmergencyUsage** <br/>                                                                                                                                                           |
| EmergencyDialString  <br/>                | **911** <br/>                                                                                                                                                                      |
| EmergencyDialMask  <br/>                  | **112** <br/>                                                                                                                                                                      |
| NotificationUri  <br/>                    | <strong>sip:security@litwareinc.com</strong> <br/>                                                                                                                                 |
| ConferenceUri  <br/>                      | <strong>sip:+14255550123@litwareinc.com</strong> <br/>                                                                                                                             |
| ConferenceMode  <br/>                     | **twoway** <br/>                                                                                                                                                                   |
| LocationRefreshInterval  <br/>            | **2** <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a>建立位置原則

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。

    > [!NOTE]
    > 如果 **PstnUsage** 的設定尚未存在於 PstnUsages 的全域清單中，CsLocationPolicy 將會失敗。

2. （選用）執行下列 Cmdlet 以編輯全域位置原則：

   ```powershell
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. 執行下列各項以建立標記位置原則。

   ```powershell
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. 執行下列 Cmdlet，將在步驟3中建立的標記位置原則套用至使用者原則。

   ```powershell
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```