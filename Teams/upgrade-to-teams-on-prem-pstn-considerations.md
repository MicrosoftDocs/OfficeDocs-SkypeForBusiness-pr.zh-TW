---
title: 從伺服器升級到 PSTN Teams PSTN 商務用 Skype
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 從 商務用 Skype 升級到 Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c19c1860c3a351cd7ed6a6240e20dc253f204ab1
ms.sourcegitcommit: bc686eedb37e565148d0c7a61ffa865aaca37d20
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/24/2022
ms.locfileid: "62180886"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>從內部部署升級至 Teams PSTN 商務用 Skype PSTN 考慮

本文將說明公用交換電話網絡 (PSTN) 升級至 PSTN 時Teams。

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

下列文章說明重要的升級概念和共存行為：

- [Teams和商務用 Skype](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [共存模式 - 參照](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 用戶端體驗和遵從共存模式](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - 只有在電話系統模式Teams使用者帳戶指派升級Teams，才能在 Teams使用。  
 > - 只有在電話系統 SfB 模式商務用 Skype為使用者帳戶指派升級Teams，才能在 商務用 Skype中使用新版。 
 > - 電話系統，當使用者帳戶被指派一個使用 Islands 模式Teams升級策略時，系統不支援這項功能。
 > - 系統不會移轉任何呼叫轉商務用 Skype小組通話群組和委派設定，而且必須重新建立Teams。
 > - 有關雲端語音功能Microsoft Teams概觀，以及協助決定哪一種 Microsoft 語音解決方案適合您的組織，請參閱規劃您的Teams[解決方案](cloud-voice-landing-page.md)。


## <a name="pstn-calling-scenarios"></a>PSTN 通話案例

移至 TeamsOnly 模式時，有四種可能的通話案例：

- [使用 Microsoft 通話商務用 Skype Online 中的使用者](#from-skype-for-business-online-with-microsoft-calling-plans)。 升級後，此使用者會繼續擁有 Microsoft 通話方案。

- [Online 中的商務用 Skype，](#from-skype-for-business-online-with-on-premises-voice)透過內部部署或雲端連接器版本商務用 Skype內部部署語音功能。 若要確保 TeamsOnly 使用者具有 PSTN 功能，您必須協調使用者的升級Teams使用者移至直接路由。

- 使用 商務用 Skype 內部部署[的使用者企業語音，](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)他們將移往線上並保持內部部署 PSTN 連線。  若要將該使用者移Teams，您必須將使用者的內部部署 商務用 Skype 帳戶移至雲端，並協調使用者移轉至直接路由。 

- [使用 商務用 Skype](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)內部部署的使用者企業語音，該使用者將會移往線上，並且使用 Microsoft 通話方案。  若要將該使用者移Teams，您必須將使用者的內部部署帳戶商務用 Skype雲端。 您必須與 A 協調移動) 將該使用者的電話號碼移轉至 Microsoft 通話方案，或 B) 從可用區域指派新的訂閱者號碼。

本文僅提供高層級概觀。 如要詳細資訊，請參閱電話系統[路由和](direct-routing-landing-page.md)[通話方案。](calling-plan-landing-page.md) 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>從 商務用 Skype Online 與 Microsoft 通話方案 

此案例是涉及語音最簡單的升級案例。 

1. 請確定使用者已指派授權Teams授權。 根據預設，當您指派授權或Microsoft 365授權Office 365，Teams啟用。 除非您先前已停用Teams授權，否則不需要執行任何動作。

2.  如果使用者已經有包含電話號碼的 Microsoft 通話方案，則唯一必要的變更是在 TeamsUpgradePolicy 中指派使用者 TeamsOnly 模式。 指派 TeamsOnly 模式之前，傳入的 PSTN 通話會登入使用者商務用 Skype用戶端。 升級至 TeamsOnly 模式之後，傳入的 PSTN 通話會登入使用者的用戶端Teams中。  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>從 商務用 Skype Online 與內部部署語音

在此情境中，使用者已在 商務用 Skype Online 中。 使用者的 PSTN 連接是內部部署，無論是使用混合商務用 Skype Server模式或雲端連接器版本。 若要將這些使用者遷移到具有 PSTN 功能的 TeamsOnly 模式，您必須啟用使用者進行直接路由。 透過直接路由，PSTN 主幹會透過您的內部部署會話邊界控制器和 SBC (直接路由) 。

以下列出基本步驟。  步驟 1-4 會以建議的順序列出，但可以按照任何循序執行。 這些步驟應在步驟 5 之前完成。

1. 如果您要將租使用者範圍的政策設定為其中一種 商務用 Skype 模式，請務必像先前所述，明確指派任何現有的群島使用者，以將群島模式指派給他們。

2. 設定您的租使用者進行直接路由。 請參閱 [直接路由的每個租使用者組配置的摘要](#summary-of-per-tenant-configuration-of-direct-routing)。

3. 如果需要，請Teams這些使用者的各種 (，例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等等) 。 您隨時都可以設定 poicies。 不過，如果您想要確保使用者在升級時擁有正確的設定，請先設定這些策略，再將使用者升級至 TeamsOnly 模式。

4. 準備選取的使用者進行語音移移： 
   - 如有需要，請指派Teams授權。  假設使用者在 Online 內部部署商務用 Skype中已經運作，則使用者已經擁有商務用 Skype方案 2 和 Microsoft 電話系統。 讓這兩個方案保持啟用狀態，商務用 Skype線上方案 2 授權。  
   - 指派所需的 OnlineVoiceRoutingPolicy。 

5. 升級使用者：這些步驟必須協調一致。 

   - 在 Microsoft 365 或 Office 365，將使用者升級至 TeamsOnly 模式 (Grant-CsTeamsUpgradePolicy) 。
   - 在 SBC 上，設定語音路由以將來電傳送至直接路由，而非內部部署中繼伺服器，以啟用來電。


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>從 商務用 Skype Server內部部署，使用 企業語音，到直接路由

在此情境中，使用者仍位於內部商務用 Skype中。 使用者的 PSTN 連接也是內部部署。 若要將該使用者移轉至具有 PSTN 功能的 TeamsOnly 模式，您必須啟用使用者進行直接路由，然後將使用者移至雲端。 
 
以下列出基本步驟。 步驟 1-5 會以建議的順序列出，但可以按照任何循序執行。 您必須在步驟 6 之前完成步驟 1-5。

1. 如果您將整個租使用者範圍的政策設定為其中一種 商務用 Skype 模式，請務必像先前所述，明確指派群島模式，以將現有的群島使用者外派。

2. 如果您尚未這麼做，請針對混合式[設定商務用 Skype組織](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。

3. 設定您的租使用者進行直接路由。 請參閱 [直接路由的每個租使用者組配置的摘要](#summary-of-per-tenant-configuration-of-direct-routing)。

4. 如果需要，請Teams這些使用者的各種 (，例如 TeamsMessagingPolicy、TeamsMeetingPolicy) 。 您隨時都可以設定策略。 不過，如果您想要確保使用者在升級時擁有正確的設定，請先設定這些策略，再將使用者升級至 TeamsOnly。

5. 如有需要，Microsoft 365或Office 365授權。  使用者應該同時擁有 Teams 商務用 Skype方案 2 和 電話系統。 如果 商務用 Skype方案 2 停用，請重新啟用。  

6. 升級使用者：這些步驟必須協調一致。 

   - 使用內部部署工具商務用 Skype ，使用 -MoveToTeams Move-CsUser執行所有操作。 如果您使用的是不支援 -MoveToTeams 切換的 商務用 Skype Server 版本，請先執行 Move-CsUser，然後在租使用者遠端 PowerShell 或 Teams 管理主控台中指派 TeamsOnly 模式。

   - 在 SBC 上，設定語音路由以將來電傳送至直接路由，而非內部部署中繼伺服器，以啟用來電。 

   - 在 Microsoft 365或Office 365：指派相關的 OnlineVoiceRoutingPolicy 以啟用撥出通話。 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>從商務用 Skype Server內部部署、企業語音到 Microsoft 通話方案

在此情境中，使用者仍位於內部商務用 Skype中。 使用者的 PSTN 連接也是內部部署。 若要將該使用者移轉至具有 PSTN 功能的 TeamsOnly 模式，您必須將使用者移至雲端，並將他們的號碼從舊的電信公司移轉至 Microsoft 通話方案，或指派新號碼給使用者。 

以下列出基本步驟。步驟 1-5 會以建議的順序列出，但可以按照任何循序執行。 您必須在步驟 6 之前完成步驟 1-5。 

1. 如果您將整個租使用者範圍的政策設定為其中一種 商務用 Skype 模式，請務必像先前所述，明確指派群島模式，以將現有的群島使用者外派。 

2. 如果您尚未這麼做，請針對混合式[設定商務用 Skype組織](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。 

3. 如果需要，請Teams這些使用者的各種 (，例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等等) 。 您隨時都可以設定策略。 不過，如果您想要確保使用者在升級時擁有正確的設定，請先設定這些策略，再將使用者升級至 TeamsOnly。 

4. 如有需要，Microsoft 365或Office 365授權。使用者應該同時擁有 Teams 商務用 Skype方案 2 和 電話系統。 如果 商務用 Skype方案 2 停用，請重新啟用。  

5. 取得使用者的電話號碼。  (詳細資料請參閱 [管理](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)貴組織的電話號碼 。) 

   - 如果您要重新使用號碼，請提交一份移植要求給電信公司。  
   - 或者，您也可以直接從 Microsoft 取得新號碼。 

6. 升級使用者，並根據需要指派 LineUri。 使用內部部署商務用 Skype工具，使用 -MoveToTeams Move-CsUser執行所有操作。  

    - 如果您要將數位移植到 Microsoft，您應該協調此作業的時機，以在埠出現時執行。 

    - 如果您使用的是 Microsoft 的新號碼，您必須使用 Set-CsPhoneNumberAssignment，在使用者移至線上後，變更使用者的 LineUri。  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>直接路由的每個租使用者組組摘要 

1. 請檢閱此清單， (SBC) 直接路由支援會話邊界 [控制器](direct-routing-border-controllers.md)。 另外，請確保您擁有正確版本的固件。  

2. 將內部部署 SBC 與 Teams路由服務配對。 詳細資料請參閱[將 SBC 配對至](direct-routing-configure.md)電話系統。 

3. 此組式基本上是內部部署配置的鏡像。 線上組組包括： 
   - OnlineVoiceRoutingPolicy (根據內部部署 VoiceRoutingPolicy 從 商務用 Skype Online 移移使用者，以及使用 企業語音) 從內部部署移移使用者的 VoicePolicy。
   - OnlinePSTNUsage 物件 (內部部署 PSTN 使用量) 。 
   - OnlineVoiceRoute 物件 (內部部署 VoiceRoute) 。 

詳細資訊，請參閱設定 [直接路由](direct-routing-configure.md)。 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>在移移期間管理 EnterpriseVoiceEnabled 屬性 

無論使用直接路由還是 Microsoft 通話方案，使用者都必須在 Azure AD 中擁有 EnterpriseVoiceEnabled=true，使用者必須具有 PSTN 功能。  EnterpriseVoiceEnabled (「啟用 EV") 是一個屬性 (而不是存在於內部部署目錄) 和雲端中的策略) 。 雲端中的值對Teams。  啟用 EV 的方式設定為 True 的確切邏輯取決於下列案例： 

- 如果使用者在內部部署 商務用 Skype Server 中已啟用 EV，且在使用 Move-CsUser 將使用者移至雲端之前，已指派 電話系統 授權給使用者，則線上使用者會以 EV-enabled=true 進行配置。 

- 如果現有 TeamsOnly 或 商務用 Skype Online 使用者被指派電話系統授權，則根據預設，啟用 EV 的使用者不會設為 true。 如果內部部署使用者是在指派授權之前移至雲端，電話系統的情況。 在這兩種情況下，系統管理員都必須指定下列 Cmdlet： 

  ```PowerShell
  Set-CsPhoneNumberAssignment -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>相關連結

[規劃您的Teams語音解決方案](cloud-voice-landing-page.md)

[適用于使用應用程式與Teams之組織的移商務用 Skype](migration-interop-guidance-for-teams-with-skype.md) 

[設定商務用 Skype Server或Microsoft 365之間的Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存和升級設定](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用會議移 (MMS) ](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
