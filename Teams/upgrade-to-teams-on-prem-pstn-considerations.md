---
title: 從 Teams 升級到 PSTN 商務用 Skype
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 升級至商務用 Skype語音Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 77c4c30c86375fbf72822e244737f8a77000d9bc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617149"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>從內部部署升級至 Teams PSTN 商務用 Skype PSTN 考慮

本文將說明公用交換電話網絡 (PSTN) 升級至 PSTN 時Teams。

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

此外，下列文章說明重要的升級概念和共存行為：

- [Teams和商務用 Skype](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [共存模式 - 參照](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 用戶端體驗和遵從共存模式](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - 只有在電話系統模式Teams使用者帳戶指派升級Teams，才能在 Teams 中使用。  
 > - 只有在電話系統 SfB 模式商務用 Skype為使用者帳戶指派升級Teams，才能在 商務用 Skype中使用帳戶。 
 > - 電話系統以群島模式為使用者帳戶指派升級Teams，則不支援此選項。
 > - 系統不會移轉任何呼叫轉商務用 Skype小組通話群組和委派設定，而且必須重新建立Teams。
 > - 有關雲端語音功能Microsoft Teams概觀，以及協助決定哪一種 Microsoft 語音解決方案適合您的組織，請參閱規劃您的Teams[解決方案](cloud-voice-landing-page.md)。


## <a name="pstn-calling-scenarios"></a>PSTN 通話案例

移至 TeamsOnly 模式時，有四種可能的通話案例：

- [使用 Microsoft 通話商務用 Skype Online 中的使用者](#from-skype-for-business-online-with-microsoft-calling-plans)。 升級後，此使用者會繼續擁有 Microsoft 通話方案。

- [Online 中的使用者商務用 Skype](#from-skype-for-business-online-with-on-premises-voice)內部部署語音功能，商務用 Skype內部部署或雲端連接器版本。 使用者的升級至Teams使用者移向直接路由，以確保 TeamsOnly 使用者具有 PSTN 功能。

- [使用 商務用 Skype](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)內部部署的使用者企業語音，該使用者將會移往線上並保持內部部署 PSTN 連線。  將此使用者移Teams需要將使用者的內部部署 商務用 Skype 帳戶移至雲端，並協調使用者移轉至直接路由。 

- 使用 商務用 Skype 內部部署[的使用者企業語音，](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)該使用者將會移往線上，並且使用 Microsoft 通話方案。  將該使用者移轉至 Teams 需要將使用者的內部部署 商務用 Skype 帳戶移至雲端，並協調該移動與 A) 該使用者電話號碼的埠到 Microsoft 通話方案，或 B) 從可用區域指派新訂閱者號碼。

本文僅提供高層次概觀。 如要詳細資訊，請參閱[電話系統路由和](direct-routing-landing-page.md)[通話方案。](calling-plan-landing-page.md) 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>從 商務用 Skype Online 與 Microsoft 通話方案 

這是涉及語音最簡單的升級案例。 

1. 請確定使用者已指派授權Teams授權。 根據預設，當您指派 Microsoft 365 或 Office 365 授權時，Teams會啟用，因此除非您先前停用 Teams 授權，否則不需要執行任何動作。

2.  如果使用者已經有包含電話號碼的 Microsoft 通話方案，則唯一必要的變更是在 TeamsUpgradePolicy 中指派使用者 TeamsOnly 模式。  在指派 TeamsOnly 模式之前，傳入的 PSTN 通話會登入使用者商務用 Skype用戶端。 升級至 TeamsOnly 模式之後，傳入的 PSTN 通話會登入使用者的用戶端Teams。  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>從 商務用 Skype Online 與內部部署語音

在此情境中，使用者已在 商務用 Skype Online 中，但他們的 PSTN 連線是內部部署，無論是使用混合商務用 Skype Server模式或雲端連接器版本。 使用 PSTN 功能將這些使用者移入 TeamsOnly 模式，表示讓他們能夠進行直接路由，其中 PSTN 主幹會透過內部部署會話邊界控制器 (SBC) ，直接連接到雲端中的直接路由服務。

以下列出基本步驟。  步驟 1-4 會以建議的順序列出，但可以以任何順序完成。 關鍵在於在步驟 5 之前應完成所有步驟。

1. 如果您要將租使用者範圍的政策設定為其中一種商務用 Skype模式，請務必如先前所述，明確指派任何現有的群島使用者，以將群島模式指派給他們。

2. 設定您的租使用者進行直接路由。 請參閱 [直接路由的每個租使用者組配置的摘要](#summary-of-per-tenant-configuration-of-direct-routing)。

3. 如果需要，請Teams這些使用者的各種 (例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等 ) 。 這一點隨時都可以完成，但如果您想要確保使用者在升級時擁有正確的組式，最好在使用者升級至 TeamsOnly 模式之前執行這項操作。

4. 準備選取的使用者進行語音移移： 
   - 如有需要，請指派Teams授權。  假設使用者已在 商務用 Skype Online 內部部署語音中運作，則使用者商務用 Skype方案 2 以及 Microsoft 電話系統。 讓這兩個方案保持啟用狀態，商務用 Skype線上方案 2 授權。  
   - 指派所需的 OnlineVoiceRoutingPolicy。 

5. 升級使用者：這些步驟必須協調一致。 

   - 在 Microsoft 365 或 Office 365 中，將使用者升級至 TeamsOnly 模式 (Grant-CsTeamsUpgradePolicy) 。
   - 在 SBC 上，設定語音路由以將來電傳送至直接路由，而非內部部署中繼伺服器，以啟用來電。


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>從商務用 Skype Server內部部署 ，使用 企業語音，到直接路由

在此情境中，使用者仍然位於內部商務用 Skype，而且他們的 PSTN 連接也是內部部署。 使用 PSTN 功能將這些使用者移往 TeamsOnly 模式，即表示啟用這些使用者進行直接路由，然後將使用者移至雲端。 
 
以下列出基本步驟。  步驟 1-5 會以建議的順序列出，但可以以任何順序完成。 關鍵在於在步驟 6 之前完成所有步驟。

1. 如果您將整個租使用者範圍的政策設定為其中一個 商務用 Skype 模式，請務必像先前所述，明確指派群島模式，以將現有群島使用者指派給這些使用者。

2. 如果您尚未這麼做，請為混合式[商務用 Skype 組織](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。

3. 設定您的租使用者進行直接路由。 請參閱 [直接路由的每個租使用者組配置的摘要](#summary-of-per-tenant-configuration-of-direct-routing)。

4. 如果需要，請Teams這些使用者設定各種 (例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等 ) 。 這一點隨時都可以完成，但如果您想要確保使用者在升級時擁有正確的配置，最好在使用者升級至 TeamsOnly 之前執行這項操作。

5. 如有需要，Microsoft 365或Office 365授權。  使用者應該同時擁有 Teams 商務用 Skype方案 2，以及 電話系統。 如果 商務用 Skype方案 2 停用，請重新啟用。  

6. 升級使用者：這些步驟必須協調一致。 

   - 使用內部部署和商務用 Skype，使用 -MoveToTeams Move-CsUser執行所有操作。 如果您使用的是不支援 -MoveToTeams 切換的 商務用 Skype Server 版本，請先執行 Move-CsUser，然後在租使用者遠端 PowerShell 或 Teams 管理主控台中指派 TeamsOnly 模式。

   - 在 SBC 上，設定語音路由以將來電傳送至直接路由，而非內部部署中繼伺服器，以啟用來電。 

   - 在 Microsoft 365或Office 365：指派相關的 OnlineVoiceRoutingPolicy 以啟用撥出通話。 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>從 商務用 Skype Server內部部署，使用 企業語音，到 Microsoft 通話方案

在此情境中，使用者仍然位於內部商務用 Skype，而且他們的 PSTN 連接也是內部部署。 使用 PSTN 功能將這些使用者移往 TeamsOnly 模式，即表示將使用者移往雲端，並將他們的號碼從舊的電信公司移往 Microsoft 通話方案，或指派新號碼給使用者。 

以下列出基本步驟。步驟 1-5 會以建議的順序列出，但可以以任何順序完成。 關鍵在於在步驟 6 之前完成所有步驟。 

1. 如果您將整個租使用者範圍的政策設定為其中一個 商務用 Skype 模式，請務必像先前所述，明確指派群島模式，以將現有群島使用者指派給這些使用者。 

2. 如果您尚未這麼做，請為混合式[商務用 Skype 組織](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。 

3. 如果需要，請Teams這些使用者的各種 (例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等 ) 。 這一點隨時都可以完成，但如果您想要確保使用者在升級時擁有正確的配置，最好在使用者升級至 TeamsOnly 之前執行這項操作。 

4. 如有需要，Microsoft 365或Office 365授權。使用者應該同時擁有 Teams 商務用 Skype方案 2，以及 電話系統。 如果 商務用 Skype方案 2 停用，請重新啟用。  

5. 取得使用者的電話號碼。  (詳細資料請參閱 [管理](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)貴組織的電話號碼 .) 

   - 如果您要重新使用這些號碼，請提交一份移植要求給您的電信公司。  
   - 或者，您也可以直接從 Microsoft 取得新號碼。 

6. 升級使用者，並根據需要指派 LineUri。 使用內部部署商務用 Skype工具，使用 -MoveToTeams Move-CsUser執行此動作。  

    - 如果您要將數位移植到 Microsoft，您應該協調此作業的時機，以在埠出現時執行。 

    - 如果您使用的是 Microsoft 的新號碼，您必須變更使用者的 LineUri。 在使用 Set-CsOnlineVoiceUser 將使用者移至線上之後，必須執行這項操作。  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>直接路由的每個租使用者組組摘要 

1. 請檢閱此清單， (SBC) 直接路由功能支援會話邊界 [控制器](direct-routing-border-controllers.md)。 您也必須確保您擁有正確的固件版本。  

2. 將內部部署 SBC 與 Teams路由服務配對。 詳細資料請參閱[將 SBC 配對至](direct-routing-configure.md)電話系統。 

3. 此組式基本上是內部部署配置的鏡像。 線上組組包括： 
   - OnlineVoiceRoutingPolicy (根據內部部署 VoiceRoutingPolicy 從 商務用 Skype Online 移移使用者，以及使用 企業語音) 從內部部署移移使用者的 VoicePolicy。
   - OnlinePSTNUsage 物件 (內部部署 PSTN 使用量) 。 
   - OnlineVoiceRoute 物件 (內部部署 VoiceRoute) 。 

詳細資訊，請參閱設定 [直接路由](direct-routing-configure.md)。 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>在移移期間管理 EnterpriseVoiceEnabled 屬性 

無論使用直接路由還是 Microsoft 通話方案，使用者都必須在 Azure AD 中擁有 EnterpriseVoiceEnabled=true，使用者必須具有 PSTN 功能。  EnterpriseVoiceEnabled (「啟用 EV") 是一種屬性 (而非存在於內部部署目錄和雲端) 之策略) 。 雲端中的值對Teams。  啟用 EV 的方式設定為 True 的確切邏輯取決於下列案例： 

- 如果使用者在內部部署 商務用 Skype Server 中已啟用 EV，且在使用 Move-CsUser 將使用者移至雲端之前，已指派 電話系統 授權給使用者，則線上使用者會以 EV-enabled=true 進行配置。 

- 如果現有的 TeamsOnly 或 商務用 Skype Online 使用者被指派電話系統授權，則啟用 EV 的使用者預設不會設為 true。  如果內部部署使用者是在指派授權之前移至雲端，電話系統的情況。 在這兩種情況下，系統管理員都必須指定下列 Cmdlet： 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>相關連結

[規劃您的Teams語音解決方案](cloud-voice-landing-page.md)

[針對與應用程式一起使用Teams的組織的移商務用 Skype](migration-interop-guidance-for-teams-with-skype.md) 

[設定商務用 Skype Server或Microsoft 365之間的Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用會議移移服務 (MMS) ](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
