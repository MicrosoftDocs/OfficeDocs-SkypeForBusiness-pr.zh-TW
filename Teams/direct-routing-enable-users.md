---
title: 允許使用者直接傳送
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解如何啟用使用者 Microsoft Phone 系統 Direct 路由。
ms.openlocfilehash: f89133b5205dc77f8045c484b97d3049773c28e2
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814542"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>允許使用者使用直接路由、語音及語音信箱

本文說明如何讓使用者使用電話系統直接路由。  以下是設定直接路由的步驟2：

- 步驟1。 [將 SBC 與 Microsoft Phone 系統連接並驗證連接](direct-routing-connect-the-sbc.md) 
- **步驟2。在本文中，讓使用者使用直接路由、語音及語音信箱**   () 
- 步驟3。 [設定語音路由](direct-routing-voice-routing.md)
- 步驟4。 [將數位轉換成替換格式](direct-routing-translate-numbers.md) 


如需設定直接路由所需的所有步驟的詳細資訊，請參閱設定 [直接路由](direct-routing-configure.md)。

當您準備好要讓使用者能夠直接傳送時，請遵循下列步驟： 

1. 在 Microsoft 365 或 Office 365 中建立使用者，並指派電話系統授權。 
2. 確定使用者是駐留在商務用 Skype Online 中。 
3. 設定電話號碼，並啟用企業語音及語音信箱。 
4. 將 [團隊專用] 模式指派給使用者。

## <a name="create-a-user-and-assign-the-license"></a>建立使用者並指派授權 

在 Microsoft 365 或 Office 365 中建立新使用者有兩個選項。 不過，Microsoft 建議您的組織選擇一個選項來避免路由問題： 

- 在內部部署的 Active Directory 中建立使用者，並將使用者同步處理到雲端。 請參閱 [將您的內部部署目錄與 Azure Active Directory 整合](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)。
- 直接在 Microsoft 365 系統管理中心建立使用者。 請參閱 [個別或大量將使用者新增至 Microsoft 365 或 Office 365-系統管理協助](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)。 

如果您的商務用 skype Online 部署 coexists 使用商務用 Skype 2015 或 Lync 2010 或2013內部部署，則唯一支援的選項是在內部部署 Active Directory 中建立使用者，並將使用者同步處理到雲端 (選項 1) 。 

如需授權需求的相關資訊，請參閱[規劃直接路由](direct-routing-plan.md)中的[授權和其他需求](direct-routing-plan.md#licensing-and-other-requirements)。

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a>確定使用者已託管線上且電話號碼未從內部部署進行同步處理 (適用于商務用 Skype Server 企業語音的使用者已遷移至團隊直接路由) 

[直接傳送] 要求使用者在線上中駐留。 您可以查看 RegistrarPool 參數，該參數必須在 infra.lync.com 網域中有值。 OnPremLineUriManuallySet 參數也應該設定為 True。 這是透過設定電話號碼，並使用商務用 Skype Online PowerShell 啟用企業語音及語音信箱來實現。

1. 連接商務用 Skype Online PowerShell 會話。

2. 發出命令： 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    如果將 OnPremLineUriManuallySet 設定為 False，並以 <E. 164 個電話號碼> 填入，請在使用商務用 Skype Online PowerShell 設定電話號碼前，使用內部部署商務用 Skype 管理命令介面清除參數。 

1. 從商務用 Skype 管理 Shell 發出命令： 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   在變更已同步處理到 Office 365 之後，預期的輸出為 `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` ：

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>設定電話號碼並啟用企業語音及語音信箱 

在您建立使用者並指派授權之後，下一步就是設定使用者的電話號碼和語音信箱。 

若要新增電話號碼並啟用語音信箱：
 
1. 連接商務用 Skype Online PowerShell 會話。 

2. 發出命令： 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```
    
    例如，若要將使用者的電話號碼新增至 [Spencer Low]，請輸入下列內容： 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    所使用的電話號碼必須設定為完整的 E. 164 電話號碼（國家/地區碼）。 

    > [!NOTE]
    > 如果使用者的電話號碼是在內部部署管理，請使用內部部署商務用 Skype 管理命令介面或 [控制台] 來設定使用者的電話號碼。 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>設定直接傳送來電至語音信箱

[直接路由] 可讓您結束通話呼叫並直接傳送給使用者的語音信箱。 如果您想要直接將來電傳送到語音信箱，請將不透明的 = app 附加至 [要求 URI 標頭]。 例如，「sip： user@yourdomain .com; 不透明 = app：語音信箱」。 在這種情況下，小組使用者將不會收到來電通知，該通話會直接連線至使用者的語音信箱。

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>將 [僅限團隊] 模式指派給使用者，以確保在 Microsoft 團隊中撥打土地

直接路由要求使用者只能在 [僅限團隊] 模式中，以確保來電在團隊用戶端中保持通話。 若要將使用者置於 [僅限團隊] 模式，請將 [UpgradeToTeams] TeamsUpgradePolicy 的實例指派給他們。 如需詳細資訊，請參閱適用 [于 IT 系統管理員的升級指導](upgrade-to-teams-on-prem-overview.md)方針。 如果您的組織是使用商務用 Skype Server 或商務用 Skype Online，請參閱下列文章，瞭解 Skype 與團隊之間的互通性資訊： [與商務用 skype 的遷移與互通性](migration-interop-guidance-for-teams-with-skype.md)。

## <a name="see-also"></a>另請參閱

[規劃直接路由](direct-routing-plan.md)

[設定直接路由](direct-routing-configure.md)
