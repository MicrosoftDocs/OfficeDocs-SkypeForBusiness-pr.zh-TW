---
title: 啟用使用者的直接路由
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
description: 瞭解如何啟用使用者Microsoft Teams 電話直接路由。
ms.openlocfilehash: edf02077bf5c15da56fe7894d1faec2a9b87b0d5
ms.sourcegitcommit: 9968ef7d58c526e35cb58174db3535fd6b2bd1db
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/09/2022
ms.locfileid: "65284078"
---
# <a name="enable-users-for-direct-routing"></a>啟用使用者的直接路由

本文說明如何啟用使用者的直接路由。 這是設定直接路由的下列步驟 2 步驟 2：

- 步驟 1. [使用 電話系統 連線 SBC 並驗證連線](direct-routing-connect-the-sbc.md) 
- **步驟 2.在本文 (啟用使用者的直接路**   由) 
- 步驟 3. [設定語音路由](direct-routing-voice-routing.md)
- 步驟 4. [將數位翻譯成替代格式](direct-routing-translate-numbers.md) 


如需設定直接路由所需所有步驟的相關資訊，請參閱 [設定直接路由](direct-routing-configure.md)。

當您準備好讓使用者使用直接路由時，請依照下列步驟執行： 

1. 在 Microsoft 365 中建立使用者，並指派電話系統授權。  
2. 確定使用者已在線上使用。
3. 設定電話號碼並啟用企業語音。 
4. 指派Teams模式給使用者。

## <a name="create-a-user-and-assign-the-license"></a>建立使用者並指派授權

在 Microsoft 365 中建立新使用者有兩種選項。 不過，Microsoft 建議您的組織選擇一個選項以避免路由問題： 

- 在 內部部署的 Active Directory 中建立使用者，並將使用者同步至雲端。 請參閱[整合內部部署目錄與Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect)。
- 直接在Microsoft 365 系統管理中心中建立使用者。 請參閱[個別或大量新增使用者至Microsoft 365或Office 365 - 系統管理說明](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)。 

如果您的 商務用 Skype Online 部署與 商務用 Skype 2015 或 Lync 2010 或 2013 內部部署並存，唯一支援的選項是在 內部部署的 Active Directory 中建立使用者，並將使用者同步處理至雲端 (選項 1) 。 

如需授權需求的相關資訊，請參閱[方案直接路由](direct-routing-plan.md)中的[授權和其他需求](direct-routing-plan.md#licensing-and-other-requirements)。

## <a name="ensure-that-the-user-is-homed-online"></a>確定使用者已在線上使用 

此步驟適用于商務用 Skype Server 企業語音已啟用移轉至Teams直接路由的使用者。

直接路由需要將使用者設為連線上網。 您可以查看註冊機構Pool 參數，此參數必須在 infra.lync.com 網域中具有值。 當您將使用者移轉到直接路由時，Microsoft 建議您將 LineURI 從內部部署變更為線上 Teams，但不需要。 

1. 連線Microsoft Teams PowerShell 會話。

2. 發出命令： 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUri,LineUri
    ``` 
    如果 OnPremLineUri 已填入 <E.164 電話號碼>，則電話號碼已在內部部署中指派並同步處理至Microsoft 365。 如果您要線上管理電話號碼，請先清除使用內部部署商務用 Skype管理命令介面的參數，然後同步處理至Microsoft 365，再使用 Teams PowerShell 設定電話號碼。 

1. 從商務用 Skype管理命令介面發出命令： 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null
    ``` 
 > [!NOTE]
 > 請勿將 EnterpriseVoiceEnabled 設為 False，因為不需要這麼做，如果舊版商務用 Skype手機在使用中，且租使用者混合式組態是以 UseOnPremDialPlan $True設定，這可能會導致撥號對應表正規化問題。 
    
   將變更同步處理至Microsoft 365之後，預期的結果 `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUri,LineUri` 為：

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURI                        : 
   LineURI                              : 
   ```
 > [!NOTE]
 > 在您[解碼](/skypeforbusiness/hybrid/decommission-on-prem-overview)內部部署商務用 Skype環境之前，必須先在線上管理所有使用者的手機屬性。 

## <a name="configure-the-phone-number-and-enable-enterprise-voice"></a>設定電話號碼並啟用企業語音 

在您建立使用者並指派授權之後，您必須設定使用者的線上電話設定。 使用者的雲端語音信箱設定是自動的，不需要執行其他設定。

您可以使用系統管理中心或使用 Teams Teams PowerShell 來設定電話號碼。

### <a name="use-teams-admin-center"></a>使用Teams系統管理中心

1. 移至 **[使用者**  ->  **管理使用者]**。

2. 選取使用者。

2. 在 [**帳戶****一般資訊] 底** 下，選取 **[編輯]**。

3. 在 **[指派電話號碼**] 底下的 **[電話號碼類型**] 下拉式功能表中，選取 [**直接路由]**。

4. 如果適用，請輸入指定的電話號碼和電話號碼分機。

5. 選取 [ **套用]。**

帳戶一般資訊現在會將指派的電話號碼和直接路由顯示為電話號碼類型。


### <a name="use-powershell"></a>使用 PowerShell

1. 連線至 Microsoft Teams PowerShell 會話。 

2. 接下來的步驟取決於您是在內部部署或線上管理使用者的電話號碼。 如果您管理的是內部部署電話號碼，您必須使用內部部署商務用 Skype管理命令介面、主控台，或是其中一個方法在[解除委任後決定如何管理屬性](/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes)中所述。

   - 如果您在內部部署管理使用者的電話號碼，您必須使用下列命令確保該使用者已企業語音線上啟用：

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -EnterpriseVoiceEnabled $true
       ```
       
   - 如果您正在線上管理使用者的電話號碼，您必須使用Teams PowerShell 中的下列命令，將電話號碼指派給使用者。 使用者會企業語音命令自動啟用： 
 
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -PhoneNumber <phone number> -PhoneNumberType DirectRouting
       ```
    
       例如，若要為使用者新增電話號碼「低，請輸入下列專案： 

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388797" -PhoneNumberType DirectRouting
       ```
       如果使用者「文檔不足」和「Stacy 作業者」共用具有唯一擴充功能的相同基數，請輸入下列內容：
    
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388701;ext=1001" -PhoneNumberType DirectRouting
       Set-CsPhoneNumberAssignment -Identity "stacy.quinn@contoso.com" -PhoneNumber "+14255388701;ext=1002" -PhoneNumberType DirectRouting
       ```

    Microsoft 建議但不要求將電話號碼設定為包含國碼的完整 E.164 電話號碼。 您可以使用分機號碼來設定電話號碼。 當對底數的查閱傳回多個結果時，這些延伸模組會用來查詢使用者。 這項功能可讓公司設定具有相同底數和唯一分機號碼的電話號碼。 若要查閱成功，邀請必須包含具有分機的完整號碼，如下所示：
    
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```


## <a name="configure-sending-calls-directly-to-voicemail"></a>設定直接將通話傳送到語音信箱

直接路由可讓您結束對使用者的通話，並直接傳送到使用者的語音信箱。 如果您想要將通話直接傳送到語音信箱，請將不透明=app：語音信箱附加到要求 URI 標頭。 例如，「sip：user@yourdomain.com;opaque=app：voicemail」。 Teams使用者不會收到通話通知。 相反地，通話會直接連線到使用者的語音信箱。

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>將Teams僅限模式指派給使用者，以確保通話以Microsoft Teams

直接路由要求使用者處於Teams只有模式，以確保來電進入Teams用戶端。 若要讓使用者處於Teams只有模式，請指派 TeamsUpgradePolicy 的「UpgradeToTeams」實例給他們。 如需詳細資訊，請參閱 [IT 系統管理員的升級策略](upgrade-to-teams-on-prem-implement.md)。 如果您的組織使用商務用 Skype Server，請參閱下列文章，瞭解Skype與Teams之間的互通性相關資訊：[移轉與商務用 Skype互通性](migration-interop-guidance-for-teams-with-skype.md)。

## <a name="see-also"></a>另請參閱

[規劃直接路由](direct-routing-plan.md)

[設定直接路由](direct-routing-configure.md)
