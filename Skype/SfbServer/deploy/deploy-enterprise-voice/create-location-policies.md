---
title: 在商務用 Skype Server 中建立位置原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: 請閱讀本主題, 瞭解如何在商務用 Skype Server Enterprise Voice 中設定增強型緊急服務 (E9-1) 位置原則。
ms.openlocfilehash: e3e98394b660174eeb58b259de0121196934ad3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190468"
---
# <a name="create-location-policies-in-skype-for-business-server"></a>在商務用 Skype Server 中建立位置原則

請閱讀本主題, 瞭解如何在商務用 Skype Server Enterprise Voice 中設定增強型緊急服務 (E9-1) 位置原則。 

商務用 skype 伺服器使用位置原則, 在用戶端註冊期間, 為 E9-1-1 啟用商務用 Skype 用戶端。 位置原則包含定義 E9-1-1 將如何實現的設定。 如需詳細資訊, 請參閱[規劃商務用 Skype Server 的位置原則](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)。

您可以使用商務用 Skype 的 [控制台] 或使用[CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) Cmdlet 來定義位置原則。

> [!NOTE]
> 商務用 Skype 伺服器現在支援設定用戶端的多個緊急電話號碼。 如果您想要設定多個緊急電話號碼, 您必須遵循[規劃商務用 Skype Server 中的多個緊急電話號碼](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md), 並在[商務用 skype 中設定多個緊急電話](configure-multiple-emergency-numbers.md)號碼。 

您可以編輯全域位置原則, 並建立新的標記位置原則。 當用戶端不位於關聯位置原則的子網中, 或用戶端尚未直接指派位置原則時, 用戶端會取得全域原則。 已將標記的原則指派給子網或使用者。 

若要建立位置原則, 您必須使用一個帳戶, 該帳戶是 RTCUniversalServerAdmins 群組的成員, 或是 CsVoiceAdministrator 系統管理角色的成員, 或是具有同等的管理員權利和許可權。

如需詳細資訊, 請參閱[規劃商務用 Skype Server 的位置原則](../../plan-your-deployment/enterprise-voice-solution/location-policies.md)。 此程式中的 Cmdlet 使用使用下列值定義的位置原則。 如需 Cmdlet 參數和值的完整說明, 請參閱[新 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps)。


| **元件**                               | **值**                                                                                                                                                                          |
|:------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| EnhancedEmergencyServicesEnabled  <br/>   | **滿足** <br/>                                                                                                                                                                     |
| LocationRequired  <br/>                   | **免責聲明** <br/>                                                                                                                                                               |
| EnhancedEmergencyServiceDisclaimer  <br/> | 您的公司原則需要您設定位置。 如果您沒有設定位置, 緊急服務將無法在緊急情況下找不到您。 請設定位置。  <br/> |
| UseLocationForE911Only  <br/>             | **虛假** <br/>                                                                                                                                                                    |
| PstnUsage  <br/>                          | **EmergencyUsage** <br/>                                                                                                                                                           |
| EmergencyDialString  <br/>                | **911** <br/>                                                                                                                                                                      |
| EmergencyDialMask  <br/>                  | **112** <br/>                                                                                                                                                                      |
| NotificationUri  <br/>                    | <strong>sip:security@litwareinc.com</strong> <br/>                                                                                                                                 |
| ConferenceUri  <br/>                      | <strong>sip:+14255550123@litwareinc.com</strong> <br/>                                                                                                                             |
| ConferenceMode  <br/>                     | **twoway** <br/>                                                                                                                                                                   |
| LocationRefreshInterval  <br/>            | **pplx-2** <br/>                                                                                                                                                                        |

### <a name="to-create-location-policies"></a>建立位置原則

1. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。

    > [!NOTE]
    > 如果**PstnUsage**的設定尚不在 PstnUsages 的全域清單中, CsLocationPolicy 將會失敗。

2. 或者, 您也可以執行下列 Cmdlet 來編輯全域位置原則:

   ```
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2
   ```

3. 執行下列動作來建立標籤位置原則。

   ```
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2
   ```

4. 執行下列 Cmdlet, 將步驟3中建立的標籤位置原則套用至使用者原則。

   ```
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```
