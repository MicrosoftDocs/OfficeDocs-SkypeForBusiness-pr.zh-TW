---
title: 從商務用 Skype 內部部署（Microsoft 團隊）升級至團隊
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 從商務用 Skype 升級至 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 075960ef47f5d708a72cabc8e3c492786c2a5112
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940649"
---
# <a name="pstn-considerations-when-upgrading-to-teams-mdash-for-it-administrators"></a>升級至 &mdash; IT 系統管理員小組的 PSTN 考慮

本文將說明升級至小組時的公用交換電話網絡 (PSTN) 考慮。 本文是說明 IT 系統管理員升級概念與實現的第六個專案。  

- [概觀](upgrade-to-teams-on-prem-overview.md)
- [升級方法](upgrade-to-teams-on-prem-upgrade-methods.md)
- [管理升級的工具](upgrade-to-teams-on-prem-tools.md)
- [使用商務用 Skype 內部部署之組織的其他考慮事項](upgrade-to-teams-on-prem-considerations.md)
- [實施您的升級](upgrade-to-teams-on-prem-implement.md)
- **公用交換電話網絡 (PSTN) 考慮** (本文) 

此外，下列文章說明重要的升級概念與共存行為：

- [團隊與商務用 Skype 的共存](upgrade-to-teams-on-prem-coexistence.md)
- [共存模式-參考](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 用戶端體驗和遵從共存模式](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > 只有在使用者處於 TeamsOnly 模式時，才會支援將電話系統與團隊一起使用。  如果使用者使用的是孤島模式，則只有商務用 Skype 支援電話系統。 


## <a name="pstn-calling-scenarios"></a>PSTN 通話案例

移至 TeamsOnly 模式時，有四種可能的通話案例：

- [商務用 Skype Online 中的使用者，包含 Microsoft 通話方案](#from-skype-for-business-online-with-microsoft-calling-plans)。 升級時，此使用者將會繼續進行 Microsoft 通話計畫。

- [商務用 Skype Online 中的使用者，](#from-skype-for-business-online-with-on-premises-voice) 可透過商務用 skype 內部部署或雲端連接器版本使用內部部署語音功能。 使用者在小組中的升級需要與使用者遷移以直接傳送路由，以確保 TeamsOnly 使用者有 PSTN 功能。

- [在商務用 Skype 內部部署中使用企業語音的使用者](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)，他們將會移至線上並保留內部部署 PSTN 連線。  將此使用者遷移至團隊需要將使用者的內部部署商務用 Skype 帳戶移至雲端，並將使用者的遷移轉移至直接傳送路線。 

- [在商務用 Skype 內部部署中使用企業語音的使用者](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)，他們將會移至線上並使用 Microsoft 通話方案。  將此使用者遷移至小組需要將使用者的內部部署商務用 Skype 帳戶移至雲端，並將該使用者電話號碼的埠與) 的埠進行協調，) 從可用的地區指派新的訂閱者號碼。

本文僅提供高層次的概覽。 如需詳細資訊，請參閱 [手機系統 Direct 路由](direct-routing-landing-page.md) 與 [通話方案](calling-plan-landing-page.md)。 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>使用 Microsoft 通話方案從商務用 Skype Online 

這是包括語音在內的最簡單的升級案例。 

1. 請確定使用者已獲指派團隊授權。 根據預設，當您指派 Microsoft 365 或 Office 365 授權時，系統會啟用團隊，所以除非您先前已停用團隊授權，否則不需要採取任何動作。

2.  如果使用者已有電話號碼的 Microsoft 通話方案，唯一的必要變更是在 TeamsUpgradePolicy 中指派使用者 TeamsOnly 模式。  在指派 TeamsOnly 模式之前，傳入的 PSTN 呼叫將會居住在使用者的商務用 Skype 用戶端。 升級至 TeamsOnly 模式之後，傳入的 PSTN 呼叫會集中在使用者的團隊用戶端中。  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>從商務用 Skype Online （含內部部署語音）

在這種情況下，使用者已經在商務用 Skype Online 中，但其 PSTN 連線是內部部署的，在混合模式或雲端連接器版本中使用商務用 Skype 伺服器。 透過 PSTN 功能將這些使用者遷移至 TeamsOnly 模式，就是透過內部部署會話邊界控制器 (SBC) ，讓 PSTN trunks 直接連線到雲端中的直接路由服務。

下列基本步驟如下所示。  步驟1-4 會列在建議的順序中，但它們可以以任何順序完成。 金鑰是所有這些都應該在步驟5之前完成。

1. 如果您要將租使用者的原則設定為其中一個商務用 Skype 模式，請務必透過明確指派 grandfather 任何現有的孤島使用者，如前面所述。

2. 針對直接路由設定您的租使用者。 請參閱 [直接路由的每個租使用者配置摘要](#summary-of-per-tenant-configuration-of-direct-routing)。

3. 如有需要，請針對這些使用者設定各種小組原則 (例如，TeamsMessagingPolicy、TeamsMeetingPolicy 等）。 ) 。 您可以隨時完成這項作業，但如果您想要確保使用者在升級時有正確的設定，最好在將使用者升級至 TeamsOnly 模式前執行此動作。

4. 準備選取要語音遷移的使用者： 
   - 如有需要，請指派 [團隊授權]。  假設使用者已在商務用 Skype Online 內部部署語音中運作，則使用者已經有商務用 Skype 方案2以及 Microsoft 手機系統。 讓這些方案保持啟用，包括商務用 Skype Online 方案2授權。  
   - 指派所需的 OnlineVoiceRoutingPolicy。 

5. 升級使用者：必須協調這些步驟。 

   - 在 Microsoft 365 或 Office 365 中，將使用者升級為 TeamsOnly 模式 (授與 CsTeamsUpgradePolicy) 。
   - 在 SBC 中，將語音路由設定為直接路由（而不是內部部署的中繼伺服器）傳送呼叫來啟用撥入通話。


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>從商務用 Skype Server 內部部署（含企業語音）到直接路由

在這種情況下，使用者仍然是在商務用 Skype 內部部署中，而且其 PSTN 連線也是內部部署。 使用 PSTN 功能將這些使用者遷移至 TeamsOnly 模式，可以讓他們直接路由，然後將使用者移至雲端。 
 
下列基本步驟如下所示。  步驟1-5 會列在建議的順序中，但它們可以以任何順序完成。 金鑰是所有這些都應該在步驟6之前完成。

1. 如果您要將租使用者的原則設定為其中一個商務用 Skype 模式，請務必 grandfather 現有的孤島使用者，方法是將其明確指派給其孤島模式（如前面所述）。

2. 如果您尚未這麼做，請 [針對商務用 Skype 混合式設定組織](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。

3. 針對直接路由設定您的租使用者。 請參閱 [直接路由的每個租使用者配置摘要](#summary-of-per-tenant-configuration-of-direct-routing)。

4. 如有需要，請針對這些使用者設定不同的小組原則 (例如 TeamsMessagingPolicy、TeamsMeetingPolicy 等）。 ) 。 您可以隨時完成這項作業，但如果您想要確保使用者在升級時有正確的設定，最好在將使用者升級至 TeamsOnly 前進行。

5. 如有需要，請指派 Microsoft 365 或 Office 365 授權。  使用者應該同時擁有 [小組] 和 [商務用 Skype Online 方案 2]，以及 [電話系統]。 如果商務用 Skype Online 方案2已停用，請重新啟用它。  

6. 升級使用者：必須協調這些步驟。 

   - 使用內部部署商務用 Skype 工具，以-MoveToTeams 開關執行移動 Move-csuser。 如果您使用的是不支援-MoveToTeams 開關的商務用 Skype Server 版本，請先執行 Move-Move-csuser，然後在租使用者遠端 PowerShell 或團隊管理主控台中指派 TeamsOnly 模式。

   - 在 SBC 中，將語音路由設定為直接路由（而不是內部部署的中繼伺服器）傳送呼叫來啟用撥入通話。 

   - 在 Microsoft 365 或 Office 365 中：指派相關的 OnlineVoiceRoutingPolicy 來啟用撥出通話。 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>從商務用 Skype Server 內部部署（含企業語音）到 Microsoft 通話方案

在這種情況下，使用者仍然是在商務用 Skype 內部部署中，而且其 PSTN 連線也是內部部署。 透過 PSTN 功能將這些使用者遷移至 TeamsOnly 模式，意味著將使用者移至雲端，並將其號碼從舊的運營商移植到 Microsoft 通話方案，或為使用者指派新的號碼。 

下列基本步驟如下所示。步驟1-5 會列在建議的順序中，但它們可以以任何順序完成。 金鑰是所有這些都應該在步驟6之前完成。 

1. 如果您要將租使用者的原則設定為其中一個商務用 Skype 模式，請務必 grandfather 現有的孤島使用者，方法是將其明確指派給其孤島模式（如前面所述）。 

2. 如果您尚未這麼做，請 [針對商務用 Skype 混合式設定組織](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)。 

3. 如有需要，請針對這些使用者設定各種小組原則 (例如，TeamsMessagingPolicy、TeamsMeetingPolicy 等）。 ) 。 您可以隨時完成這項作業，但如果您想要確保使用者在升級時有正確的設定，最好在將使用者升級至 TeamsOnly 前進行。 

4. 如有需要，請指派 Microsoft 365 或 Office 365 授權。使用者應該同時擁有 [小組] 和 [商務用 Skype Online 方案 2]，以及 [電話系統]。 如果商務用 Skype Online 方案2已停用，請重新啟用它。  

5. 為您的使用者取得電話號碼。  (如需詳細資訊，請參閱 [管理貴組織的電話號碼](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)。 ) 

   - 如果您要重複使用這些號碼，請將移植要求提交給您的運營商。  
   - 或者，您也可以直接從 Microsoft 取得新號碼。 

6. 升級使用者並視需要指派 LineUri。 使用內部部署商務用 Skype 工具，以-MoveToTeams 開關執行移動 Move-csuser。  

    - 如果您要將號碼移植到 Microsoft，您應該將這個作業的時間調整為在埠出現時進行。 

    - 如果您使用的是 Microsoft 的新號碼，您需要變更該使用者的 LineUri。 這必須在使用者使用設定 CsOnlineVoiceUser 進行線上移動之後進行。  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>直接路由的每個租使用者配置摘要 

1. 透過查看 [此清單](direct-routing-border-controllers.md)，確保您的會話邊界控制器 (SBC) 支援直接路由。 您也必須確定您的固件版本正確。  

2. 將您的內部部署 SBC 與團隊直向路由服務配對。 如需詳細資訊，請參閱將 [SBC 與電話系統的直接路由服務](direct-routing-configure.md)。 

3. 此設定實質上是內部部署設定的鏡像。 線上配置包括： 
   - 如果您是從商務用 Skype Online 遷移使用者，且從使用企業語音) 的內部部署遷移使用者，請根據 VoicePolicy 來 OnlineVoiceRoutingPolicy 根據內部部署 VoiceRoutingPolicy 的 (。
   - OnlinePSTNUsage 物件 (根據內部部署的 PSTN 使用量) 。 
   - OnlineVoiceRoute 物件 (基於內部部署 VoiceRoute) 。 

如需詳細資訊，請參閱 [設定直接路由](direct-routing-configure.md)。 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>在遷移期間管理 EnterpriseVoiceEnabled 屬性 

無論是使用直接路由或 Microsoft 通話方案，使用者在 Azure AD 中都必須有 EnterpriseVoiceEnabled = true，才能讓使用者擁有 PSTN 功能。  EnterpriseVoiceEnabled ( "EV-enabled" ) 是一個 (不在內部部署目錄和雲端中的原則) 的屬性。 雲端中的值是對團隊而言重要的。  如何將 EV 啟用的確切邏輯設定為 true，視下列情況而定： 

- 如果使用者在內部部署商務用 Skype 伺服器中啟用 EV，且在將使用者移至雲端且使用 Move-csuser 時，系統會為使用者指派電話系統授權，則會使用 EV-enabled = true 來預配線上使用者。 

- 如果現有的 TeamsOnly 或商務用 Skype Online 使用者已獲指派電話系統授權，則 EV-enabled 預設不會設定為 true。  如果在指派電話系統授權之前，將內部部署使用者移至雲端，也會發生這種情況。 不論是哪一種情況，管理員都必須指定下列 Cmdlet： 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>相關連結

[與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南](migration-interop-guidance-for-teams-with-skype.md) 

[在商務用 Skype Server 與 Microsoft 365 或 Office 365 之間設定混合式連接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在內部部署和雲端之間移動使用者](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[設定您的共存與升級設定](setting-your-coexistence-and-upgrade-settings.md)

[授與 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用會議遷移服務 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

