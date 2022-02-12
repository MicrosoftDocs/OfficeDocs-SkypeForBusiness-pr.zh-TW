---
title: 啟用使用者進行直接路由
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解如何啟用使用者進行Microsoft Teams 電話路由。
ms.openlocfilehash: 4acf18799060d6cc89e477109e916b5bf0d8401a
ms.sourcegitcommit: 2e8daa3511cd198b3e0d43b153dd37a59cb21692
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2022
ms.locfileid: "62763328"
---
# <a name="enable-users-for-direct-routing"></a>啟用使用者進行直接路由

本文將說明如何啟用使用者進行直接路由。 這是下列步驟中的步驟 2，用於配置直接路由：

- 步驟 1。 [連線 SBC 電話系統並驗證連接](direct-routing-connect-the-sbc.md) 
- **步驟 2.啟用使用者直接路由 (**   本文) 
- 步驟 3. [設定語音路由](direct-routing-voice-routing.md)
- 步驟 4. [將數位轉換成替代格式](direct-routing-translate-numbers.md) 


若要瞭解設定直接路由所需的所有步驟，請參閱 [設定直接路由](direct-routing-configure.md)。

當您準備好啟用使用者進行直接路由時，請遵循下列步驟： 

1. 在中建立使用者Microsoft 365並指派電話系統授權。  
2. 確保使用者位於線上。
3. 設定電話號碼並啟用企業語音。 
4. 指派Teams模式給使用者。

## <a name="create-a-user-and-assign-the-license"></a>建立使用者並指派授權

在 Microsoft 365 中建立新使用者有兩Microsoft 365。 不過，Microsoft 建議貴組織選擇一個選項以避免路由問題： 

- 在內部部署 Active Directory 中建立使用者，並同步該使用者至雲端。 請參閱[整合您的內部部署目錄與Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect)。
- 直接在 Microsoft 365 系統管理中心 中Microsoft 365 系統管理中心。 請參閱個別或大量新增使用者至Microsoft 365[或Office 365 - 系統管理協助](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)。 

如果您的 商務用 Skype Online 部署與 商務用 Skype 2015 或 Lync 2010 或 2013 內部部署並存，唯一支援的選項是在內部部署 Active Directory 中建立使用者，並同步處理使用者至雲端 (選項 1) 。 

有關授權需求的資訊，請參閱規劃直接路由 [中的](direct-routing-plan.md#licensing-and-other-requirements) 授權 [和其他需求](direct-routing-plan.md)。

## <a name="ensure-that-the-user-is-homed-online"></a>確保使用者位於線上 

此步驟適用于商務用 Skype Server 企業語音使用者移至 Teams路由。

直接路由需要使用者連線。 您可以查看 RegistrarPool 參數來檢查，該參數需要在 infra.lync.com 中設定值。 Microsoft 建議將使用者移至直接路由時，將 LineURI 從內部部署變更為線上，但Teams變更。 

1. 連線 PowerShell 會話Microsoft Teams PowerShell 會話。

2. 發出命令： 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    如果 OnPremLineUriManuallySet 設定為 False，而 LineUri 會填上 <E.164 電話號碼>，該電話號碼會指派至內部部署並同步處理至 Microsoft 365。 如果您想要在線上管理電話號碼，請使用內部部署 商務用 Skype 管理命令命令程式清理參數，然後同步處理至 Microsoft 365，然後使用 PowerShell Teams電話號碼。 

1. 從 商務用 Skype命令命令： 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null
    ``` 
 > [!NOTE]
 > 請勿將 EnterpriseVoiceEnabled 設為 False，因為不需要這麼做，如果舊版 商務用 Skype 電話使用中，且租使用者混合式設定已設定為 UseOnPremDialPlan $True，這可能會導致撥號方案標準化問題。 
    
   將變更同步到 Microsoft 365 預期輸出 `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` 為：

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```
 > [!NOTE]
 > 您必須先在線上管理使用者的所有電話屬性，才能將內部部署商務用 Skype[環境](/skypeforbusiness/hybrid/decommission-on-prem-overview)。 

## <a name="configure-the-phone-number-and-enable-enterprise-voice"></a>設定電話號碼並啟用企業語音 

建立使用者並指派授權之後，您必須設定使用者的線上電話設定。 請注意，使用者雲端語音信箱自動進行配置;不需要執行其他配置。

1. 連線 PowerShell 會話Microsoft Teams PowerShell 會話。 

2. 下一個步驟取決於您是管理使用者內部部署或線上的電話號碼。 如果您管理內部部署的電話號碼，則必須使用內部部署 商務用 Skype 管理命令殼、控制台，或決定在取消命令之後如何管理屬性中說明的其中一種方法。[ ](/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes)

   - 如果您是在內部部署管理使用者的電話號碼，您必須使用下列命令，確保使用者企業語音線上啟用：

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -EnterpriseVoiceEnabled $true
       ```
       
   - 如果您是在線上管理使用者的電話號碼，您必須使用 PowerShell 中的下列命令，將電話號碼指派給使用者Teams。 使用者會自動企業語音命令啟用： 
 
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -PhoneNumber <phone number> -PhoneNumberType DirectRouting
       ```
    
       例如，若要新增使用者「Spencer Low」的電話號碼，請輸入下列專案： 

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388797" -PhoneNumberType DirectRouting
       ```
       如果使用者 "Spencer Low" 和 "Stacy Quinn" 共用相同的底數與唯一副檔名，請輸入下列
    
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388701;ext=1001" -PhoneNumberType DirectRouting
       Set-CsPhoneNumberAssignment -Identity "stacy.quinn@contoso.com" -PhoneNumber "+14255388701;ext=1002" -PhoneNumberType DirectRouting
       ```

    Microsoft 建議但不要求將電話號碼配置為包含國家/地區代碼的完整 E.164 電話號碼。 您可以使用分機來設定電話號碼。 當底數的查詢會返回多個結果時，這些副檔名會用來查詢使用者。 此功能可讓公司以相同的基本號碼和唯一分機來設定電話號碼。 若要成功進行尋找，邀請必須包含具有分機的完整號碼，如下所示：
    
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```


## <a name="configure-sending-calls-directly-to-voicemail"></a>設定將通話直接傳送至語音信箱

直接路由可讓您結束通話給使用者，並直接傳送給使用者的語音信箱。 如果您想要將通話直接傳送至語音信箱，請將不透明=app：語音信箱附加至要求 URI 標頭。 例如，「sip：user@yourdomain.com;不透明=app：語音信箱」。 Teams不會收到通話通知，通話會直接連接到使用者的語音信箱。

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>指派Teams模式給使用者，以確保通話在 Microsoft Teams

直接路由要求使用者進入Teams模式，以確保來電會撥入Teams用戶端。 若要將使用者置於Teams模式，請指派他們 TeamsUpgradePolicy 的「UpgradeToTeams」實例。 詳細資訊，請參閱 [為 IT 系統管理員升級策略](upgrade-to-teams-on-prem-implement.md)。 如果貴組織商務用 Skype Server，請參閱下列文章，以瞭解 Skype 與 Teams 之間的[互通性：移](migration-interop-guidance-for-teams-with-skype.md)商務用 Skype。

## <a name="see-also"></a>另請參閱

[規劃直接路由](direct-routing-plan.md)

[設定直接路由](direct-routing-configure.md)
