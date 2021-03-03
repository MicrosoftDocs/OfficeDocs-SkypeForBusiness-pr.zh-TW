---
title: 從商務用 Skype 升級到 Teams 時，PSTN 的考慮
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 從商務用 Skype 升級到 Teams 的語音考慮
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9887eec2a99fec9a6f4964899c6e631046b28897
ms.sourcegitcommit: 54140f6f8f2279a0eaf2e9c79699d6cff306791c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2021
ms.locfileid: "50410568"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>從商務用 Skype 內部部署升級到 Teams 的 PSTN 考慮

本文將說明公用交換電話網路 (PSTN) 升級到 Teams 時考慮的考慮。   


此外，下列文章說明重要的升級概念和共存行為：

- [Teams 和商務用 Skype 的共存](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [共存模式 - 參照](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 用戶端體驗和遵從共存模式](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - 只有在使用者使用 TeamsOnly 模式時，才支援在 Teams 使用電話系統。  如果使用者是在群島模式，則只有商務用 Skype 才支援電話系統。 
 > - 商務用 Skype 的任何呼叫呼叫轉班、小組通話群組和委派設定不會移轉，而且必須重新建立 Teams。
 > - 有關 Microsoft Teams 雲端語音功能的一般概觀，以及協助決定哪一種 Microsoft 語音解決方案適合您的組織，請參閱規劃 [您的 Teams 語音解決方案](cloud-voice-landing-page.md)。


## <a name="pstn-calling-scenarios"></a>PSTN 通話案例

使用 TeamsOnly 模式時，有四種可能的通話案例：

- [商務用 Skype Online 中的使用者，具有 Microsoft 通話方案](#from-skype-for-business-online-with-microsoft-calling-plans)。 升級後，此使用者會繼續擁有 Microsoft 通話方案。

- [商務用 Skype Online 中的](#from-skype-for-business-online-with-on-premises-voice) 使用者，透過商務用 Skype 內部部署或雲端連接器版本提供內部部署語音功能。 使用者升級至 Teams 時，必須協調使用者移至直接路由，以確保 TeamsOnly 使用者具有 PSTN 功能。

- [商務用 Skype](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)內部部署與企業語音的使用者，將會移往線上並保持內部部署 PSTN 連線。  將此使用者移轉至 Teams 需要將使用者的內部部署商務用 Skype 帳戶移至雲端，並協調使用者移轉至直接路由的移轉。 

- [商務用 Skype](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)內部部署與企業語音的使用者，將會移往線上，並且使用 Microsoft 通話方案。  將此使用者移轉至 Teams 需要將使用者的內部部署商務用 Skype 帳戶移至雲端，並且使用 A) 將該使用者電話號碼的埠移轉至 Microsoft 通話方案，或 B) 從可用地區指派新的訂閱者號碼來協調移動。

本文僅提供高層級概觀。 詳細資訊請參閱電話[系統直接路由和](direct-routing-landing-page.md)[通話方案](calling-plan-landing-page.md)。 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>從商務用 Skype Online 與 Microsoft 通話方案 

這是涉及語音的最簡單升級案例。 

1. 請確定使用者已指派 Teams 授權。 根據預設，當您指派 Microsoft 365 或 Office 365 授權時，Teams 會啟用，因此除非您先前停用 Teams 授權，否則不需要執行任何動作。

2.  如果使用者已經有包含電話號碼的 Microsoft 通話方案，則唯一必要的變更是在 TeamsUpgradePolicy 中指派使用者 TeamsOnly 模式。  指派 TeamsOnly 模式之前，來電 PSTN 會進入使用者的商務用 Skype 用戶端。 升級到 TeamsOnly 模式之後，傳入 PSTN 通話將會進入使用者的 Teams 用戶端。  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>從商務用 Skype Online 與內部部署語音

在此情境中，使用者已經在商務用 Skype Online 中，但他們的 PSTN 連線是在內部部署，不論是在混合式模式中使用商務用 Skype Server，還是使用雲端連接器版本。 使用 PSTN 功能將這些使用者移入 TeamsOnly 模式，即表示讓他們能夠直接路由，其中 PSTN 中繼會透過內部部署會話邊界控制器 (SBC) 直接連接至雲端中的直接路由服務。

基本步驟如下所列。  步驟 1 到 4 會列在建議的順序中，但可以按照任何順序完成。 關鍵在於，所有步驟都應該在步驟 5 之前完成。

1. 如果您要將全租使用者政策設定為其中一種商務用 Skype 模式，請務必像先前所述，明確指派群島模式給任何現有群島使用者。

2. 設定您的租使用者進行直接路由。 請參閱 [直接路由的每個租使用者組配置的摘要](#summary-of-per-tenant-configuration-of-direct-routing)。

3. 如果需要，請為這些使用者設定各種 Teams (例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等 ) 。 這隨時都可以完成，但如果您想要確保使用者在升級時擁有正確的組式，最好在使用者升級至 TeamsOnly 模式之前執行這項操作。

4. 準備特定使用者進行語音移移： 
   - 如有需要，請指派 Teams 授權。  假設使用者已經在商務用 Skype Online 內部部署語音中運作，則使用者已經有商務用 Skype 方案 2 以及 Microsoft Phone System。 讓這兩個方案保持啟用狀態，包括商務用 Skype Online 方案 2 授權。  
   - 指派您想要的 OnlineVoiceRoutingPolicy。 

5. 升級使用者：這些步驟應協調一致。 

   - 在 Microsoft 365 或 Office 365 中，將使用者升級至 TeamsOnly 模式 (Grant-CsTeamsUpgradePolicy) 。
   - 在 SBC 上，設定語音路由以將來電傳送至直接路由，而不是內部部署仲裁伺服器，以啟用來電。


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>從商務用 Skype Server 內部部署、企業語音到直接路由

在此情境中，使用者仍位於商務用 Skype 內部部署，且其 PSTN 連接也是內部部署。 使用 PSTN 功能將這些使用者移往 TeamsOnly 模式，即表示啟用這些使用者進行直接路由，然後將使用者移往雲端。 
 
基本步驟如下所列。  步驟 1-5 會列在建議的順序中，但可以按照任何順序完成。 關鍵在於，所有步驟都應該在步驟 6 之前完成。

1. 如果您將全租使用者政策設定為其中一種商務用 Skype 模式，請務必像先前所述，明確指派群島模式給現有群島使用者。。

2. 如果您尚未這麼做，請設定商務用 [Skype 混合式組織](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。

3. 設定您的租使用者進行直接路由。 請參閱 [直接路由的每個租使用者組配置的摘要](#summary-of-per-tenant-configuration-of-direct-routing)。

4. 如果需要，請為這些使用者設定各種 Teams (例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等 ) 。 這隨時都可以完成，但如果您想要確保使用者在升級時擁有正確的組配置，最好在使用者升級至 TeamsOnly 之前執行這項操作。

5. 如有需要，指派 Microsoft 365 或 Office 365 授權。  使用者應該同時擁有 Teams 和商務用 Skype Online 方案 2，以及電話系統。 如果商務用 Skype Online 方案 2 已停用，請重新啟用。  

6. 升級使用者：這些步驟應協調一致。 

   - 使用內部部署商務用 Skype 工具，Move-CsUser -MoveToTeams 切換來執行。 如果您使用的是不支援 -MoveToTeams 切換的商務用 Skype Server 版本，請先執行 Move-CsUser，然後在租使用者遠端 PowerShell 或 Teams 系統管理主控台中指派 TeamsOnly 模式。

   - 在 SBC 上，設定語音路由以將來電傳送至直接路由，而不是內部部署仲裁伺服器，以啟用來電。 

   - 在 Microsoft 365 或 Office 365 中：指派相關的 OnlineVoiceRoutingPolicy 以啟用撥出電話。 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>從商務用 Skype Server 內部部署、企業語音到 Microsoft 通話方案

在此情境中，使用者仍位於商務用 Skype 內部部署，且其 PSTN 連接也是內部部署。 使用 PSTN 功能將這些使用者移往 TeamsOnly 模式是指將使用者移動至雲端，並將他們的號碼從舊的電信公司移往 Microsoft 通話方案，或指派新的號碼給使用者。 

基本步驟如下所列。步驟 1-5 會列在建議的順序中，但可以按照任何順序完成。 關鍵在於，所有步驟都應該在步驟 6 之前完成。 

1. 如果您將全租使用者政策設定為其中一種商務用 Skype 模式，請務必像先前所述，明確指派群島模式給現有群島使用者。。 

2. 如果您尚未這麼做，請設定商務用 [Skype 混合式組織](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。 

3. 如果需要，請為這些使用者設定各種 Teams (例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等 ) 。 這隨時都可以完成，但如果您想要確保使用者在升級時擁有正確的組配置，最好在使用者升級至 TeamsOnly 之前執行這項操作。 

4. 如有需要，指派 Microsoft 365 或 Office 365 授權。使用者應該同時擁有 Teams 和商務用 Skype Online 方案 2，以及電話系統。 如果商務用 Skype Online 方案 2 已停用，請重新啟用。  

5. 取得使用者的電話號碼。  ([請參閱管理貴](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)組織的電話號碼 .) 

   - 如果您要重新使用這些號碼，請提交埠要求給電信公司。  
   - 或者，您可以直接從 Microsoft 取得新號碼。 

6. 升級使用者，並需要指派 LineUri。 使用內部部署商務用 Skype 工具，Move-CsUser -MoveToTeams 切換來執行。  

    - 如果您要將號碼埠至 Microsoft，您應協調此作業在埠出現時的時間。 

    - 如果您使用的是 Microsoft 的新號碼，您必須變更使用者的 LineUri。 您必須在使用 Set-CsOnlineVoiceUser 將使用者移至線上之後，完成這項操作。  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>直接路由的每個租使用者組配置的摘要 

1. 請檢閱此清單， (直接路由) SBC 的會話邊界[控制器。](direct-routing-border-controllers.md) 您也必須確保您擁有正確的版本。  

2. 將內部部署 SBC 與 Teams 直接路由服務配對。 詳情請參閱將 [SBC 與電話系統直接路由服務配對](direct-routing-configure.md)。 

3. 此組配置基本上就是內部部署配置的鏡像。 線上組配置包含： 
   - OnlineVoiceRoutingPolicy (根據內部部署 VoiceRoutingPolicy ，如果從商務用 Skype Online 移移使用者，並且根據 VoicePolicy 使用企業語音) 從內部部署移使用者。
   - OnlinePSTNUsage 物件 (內部部署 PSTN 使用量) 。 
   - OnlineVoiceRoute 物件 (內部部署 VoiceRoute) 。 

詳細資訊請參閱設定 [直接路由](direct-routing-configure.md)。 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>在移移期間管理 EnterpriseVoiceEnabled 屬性 

無論使用直接路由或 Microsoft 通話方案，使用者都必須在 Azure AD 中擁有 EnterpriseVoiceEnabled=true，使用者必須能夠使用 PSTN 功能。  EnterpriseVoiceEnabled ("EV-enabled") 是屬性 (而非同時存在於內部部署目錄和雲端中的) 策略) 。 雲端中的值對 Teams 很重要。  啟用 EV 的方式設定為 True 的確切邏輯取決於下列案例： 

- 如果使用者在內部部署商務用 Skype Server 中已啟用 EV，且在使用 Move-CsUser 將使用者移至雲端之前，電話系統授權已指派給使用者，線上使用者就會使用 EV-enabled=true 進行設置。 

- 如果現有 TeamsOnly 或商務用 Skype Online 使用者被指派電話系統授權，則啟用 EV 的預設值不會設為 True。  如果內部部署使用者是在指派電話系統授權之前移至雲端，也是這種情況。 在這兩種情況下，系統管理員都必須指定下列 Cmdlet： 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>相關連結

[規劃您的 Teams 語音解決方案](cloud-voice-landing-page.md)

[適用于將 Teams 與商務用 Skype 一起使用的組織之移移和互通性指南](migration-interop-guidance-for-teams-with-skype.md) 

[設定商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式連接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用會議移 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

