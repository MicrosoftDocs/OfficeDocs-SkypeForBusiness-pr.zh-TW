---
title: 啟用使用者進行直接路由
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
description: 瞭解如何允許使用者使用 Microsoft Phone System 直接路由。
ms.openlocfilehash: 972bd8d5e01a050a67978560b8de272439fda40d
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421308"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>允許使用者進行直接路由、語音和語音信箱

本文說明如何讓使用者使用電話系統直接路由。  這是進行直接路由的下列步驟之步驟 2：

- 步驟 1。 [使用 Microsoft Phone System 連接 SBC 並驗證連接](direct-routing-connect-the-sbc.md) 
- **步驟 2。啟用使用者進行直接路由、語音和語音**   信箱 (本文) 
- 步驟 3。 [設定語音路由](direct-routing-voice-routing.md)
- 步驟 4。 [將數位轉換成替代格式](direct-routing-translate-numbers.md) 


有關設定直接路由所需之所有步驟的資訊，請參閱設定 [直接路由](direct-routing-configure.md)。

當您準備好啟用使用者進行直接路由時，請遵循下列步驟： 

1. 在 Microsoft 365 或 Office 365 中建立使用者，並指派電話系統授權。 
2. 確保使用者位於商務用 Skype Online 中。 
3. 設定電話號碼，並啟用企業語音和語音信箱。 
4. 指派 Teams 模式給使用者。

## <a name="create-a-user-and-assign-the-license"></a>建立使用者並指派授權 

在 Microsoft 365 或 Office 365 中建立新使用者有兩個選項。 不過，Microsoft 建議貴組織選擇一個選項以避免路由問題： 

- 在內部部署 Active Directory 中建立使用者，並同步使用者至雲端。 請參閱[整合內部部署目錄與 Azure Active Directory。](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)
- 直接在 Microsoft 365 系統管理中心建立使用者。 請參閱個別或大量新增使用者至 [Microsoft 365 或 Office 365 - 系統管理協助](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)。 

如果您的商務用 Skype Online 部署與商務用 Skype 2015 或 Lync 2010 或 2013 內部部署並存，則唯一支援的選項是在內部部署 Active Directory 中建立使用者，並同步處理使用者至雲端 (選項 1) 。 

有關授權需求的資訊，請參閱方案直接路由 [中的](direct-routing-plan.md#licensing-and-other-requirements) 授權 [和其他需求](direct-routing-plan.md)。

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a>確保使用者位於線上，且電話號碼未從內部部署 (適用于啟用商務用 Skype Server Enterprise Voice 的使用者移移至 Teams 直接路由) 

直接路由需要使用者連線上網。 您可以查看 RegistrarPool 參數來檢查，其值必須位於 infra.lync.com 域中。 OnPremLineUriManuallySet 參數也應該設為 True。 這是使用商務用 Skype Online PowerShell 來配置電話號碼，並啟用企業語音和語音信箱的方式。

1. 連線商務用 Skype Online PowerShell 會話。

2. 發出命令： 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    如果 OnPremLineUriManuallySet 設定為 False，且 LineUri 填上 <E.164 電話號碼>，請使用內部部署商務用 Skype 管理命令程式清除參數，然後再使用商務用 Skype Online PowerShell 設定電話號碼。 

1. 從商務用 Skype 管理命令： 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   將變更同步到 Office 365 之後，預期輸出 `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` 為：

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>設定電話號碼並啟用企業語音和語音信箱 

在您建立使用者並指派授權之後，下一個步驟是設定使用者的電話號碼和語音信箱。 

若要新增電話號碼並啟用語音信箱：
 
1. 連線商務用 Skype Online PowerShell 會話。 

2. 發出命令： 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    例如，若要新增使用者「Spencer Low」的電話號碼，請輸入下列專案： 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    如果使用者 "Spencer Low" 和 "Stacy Quinn" 共用相同的底數與唯一的副檔名，請輸入下列專案
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    建議但並非必要的是，使用的電話號碼會以完整的 E.164 電話號碼與國碼進行配置。 支援設定電話號碼與分機，當底數的查詢會返回多個結果時，會用來查詢使用者。 這可讓公司設定相同基本號碼和唯一分機的電話號碼。 若要成功進行查找，邀請必須包含完整號碼和擴充功能，如下所示：
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > 如果使用者的電話號碼是在內部部署管理，請使用內部部署商務用 Skype 管理命令命令程式或控制台來設定使用者的電話號碼。 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>將來電直接傳送至語音信箱

直接路由可讓您結束通話給使用者，並直接傳送至使用者的語音信箱。 如果您想要直接將通話傳送至語音信箱，請將不透明=app：語音信箱附加至要求 URI 標頭。 例如，"sip：user@yourdomain.com;opaque=app：voicemail"。 在這種情況下，Teams 使用者不會收到通話通知，通話會直接連接到使用者的語音信箱。

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>指派 Teams 模式給使用者，以確保通話能夠進入 Microsoft Teams

直接路由要求使用者進入 Teams 僅模式，以確保來電會進入 Teams 用戶端。 若要將使用者置於 Teams 模式，請指派 TeamsUpgradePolicy 的「UpgradeToTeams」實例給他們。 詳細資訊請參閱適用于 [IT 系統管理員的升級策略](upgrade-to-teams-on-prem-implement.md)。 如果貴組織使用商務用 Skype Server 或商務用 Skype Online，請參閱下列文章，瞭解 Skype 與 Teams 之間的互通性：移移與商務用 [Skype 的互通性](migration-interop-guidance-for-teams-with-skype.md)。

## <a name="see-also"></a>另請參閱

[規劃直接路由](direct-routing-plan.md)

[設定直接路由](direct-routing-configure.md)
