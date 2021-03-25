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
description: 瞭解如何啟用使用者 Microsoft Phone System Direct Routing。
ms.openlocfilehash: 858b9073106945d414c2dbe56a16e6cecd104ee7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122217"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>啟用使用者進行直接路由、語音和語音信箱

本文將說明如何啟用使用者進行電話系統直接路由。  這是下列步驟中的步驟 2，用於配置直接路由：

- 步驟 1. [使用 Microsoft Phone 系統連接 SBC 並驗證連接](direct-routing-connect-the-sbc.md) 
- **步驟 2.啟用使用者直接路由、語音和語音信箱 (**   本文) 
- 步驟 3. [設定語音路由](direct-routing-voice-routing.md)
- 步驟 4. [將數位轉換成替代格式](direct-routing-translate-numbers.md) 


若要瞭解設定直接路由所需的所有步驟，請參閱 [設定直接路由](direct-routing-configure.md)。

當您準備好啟用使用者進行直接路由時，請遵循下列步驟： 

1. 在 Microsoft 365 或 Office 365 中建立使用者，並指派電話系統授權。 
2. 確保使用者位於商務用 Skype Online 中。 
3. 設定電話號碼，並啟用企業語音和語音信箱。 
4. 將 Teams Only 模式指派給使用者。

## <a name="create-a-user-and-assign-the-license"></a>建立使用者並指派授權 

在 Microsoft 365 或 Office 365 中建立新使用者有兩個選項。 不過，Microsoft 建議貴組織選擇一個選項以避免路由問題： 

- 在內部部署 Active Directory 中建立使用者，並同步該使用者至雲端。 請參閱 [整合您的內部部署目錄與 Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect)。
- 直接在 Microsoft 365 系統管理中心建立使用者。 請參閱個別或大量新增使用者至 [Microsoft 365 或 Office 365 - 系統管理協助](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)。 

如果您的商務用 Skype Online 部署與商務用 Skype 2015 或 Lync 2010 或 2013 內部部署並存，唯一支援的選項是在內部部署 Active Directory 中建立使用者，並同步處理使用者至雲端 (選項 1) 。 

有關授權需求的資訊，請參閱規劃直接路由 [中的](direct-routing-plan.md#licensing-and-other-requirements) 授權 [和其他需求](direct-routing-plan.md)。

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a>確保使用者位於線上，且電話號碼不會從內部部署 (適用于商務用 Skype Server Enterprise Voice 的使用者移至 Teams Direct 路由) 

直接路由需要使用者連線。 您可以查看 RegistrarPool 參數，此參數需要在 infra.lync.com 中。 OnPremLineUriManuallySet 參數也應該設為 True。 這是使用商務用 Skype Online PowerShell 來組態電話號碼，並啟用企業語音和語音信箱來達到此目的。

1. 連線商務用 Skype Online PowerShell 會話。

2. 發出命令： 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    如果 OnPremLineUriManuallySet 設定為 False，而 LineUri 會填上 <E.164 電話號碼>，請在使用商務用 Skype Online PowerShell 設定電話號碼之前，先使用內部部署商務用 Skype 管理命令程式清理參數。 

1. 從商務用 Skype 管理命令命令發出： 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   在變更同步到 Office 365 之後，預期 `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` 輸出為：

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>設定電話號碼並啟用企業語音和語音信箱 

建立使用者並指派授權之後，下一個步驟就是設定使用者的電話號碼和語音信箱。 

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
    如果使用者 "Spencer Low" 和 "Stacy Quinn" 共用相同的底數與唯一副檔名，請輸入下列
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    建議但不需要，使用的電話號碼會以完整的 E.164 電話號碼與國碼進行配置。 支援使用擴充功能來設定電話號碼，當針對基本號碼進行查詢時，會用來查詢使用者。 這可讓公司以相同的基本號碼和唯一分機來設定電話號碼。 若要成功進行尋找，邀請必須包含具有分機的完整號碼，如下所示：
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > 如果使用者的電話號碼是在內部部署中管理，請使用內部部署商務用 Skype 管理命令程式或控制台來設定使用者的電話號碼。 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>直接將通話傳送至語音信箱

直接路由可讓您結束通話給使用者，並直接傳送至使用者的語音信箱。 如果您想要將通話直接傳送至語音信箱，請將不透明=app：語音信箱附加至要求 URI 標頭。 例如，"sip：user@yourdomain.com;不透明=app：語音信箱」。 在這種情況下，Teams 使用者不會收到通話通知，通話會直接連接到使用者的語音信箱。

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>將 Teams Only 模式指派給使用者，以確保通話在 Microsoft Teams 中登陸

直接路由要求使用者進入 Teams Only 模式，以確保來電會陸入 Teams 用戶端。 若要讓使用者進入 Teams Only 模式，請指派他們 TeamsUpgradePolicy 的 「UpgradeToTeams」實例。 詳細資訊，請參閱 [IT 系統管理員的升級策略](upgrade-to-teams-on-prem-implement.md)。 如果貴組織使用商務用 Skype Server 或商務用 Skype Online，請參閱下列文章，以瞭解 Skype 與 Teams 之間的互通性：移移及與商務用 [Skype 的互通性](migration-interop-guidance-for-teams-with-skype.md)。

## <a name="see-also"></a>另請參閱

[規劃直接路由](direct-routing-plan.md)

[設定直接路由](direct-routing-configure.md)