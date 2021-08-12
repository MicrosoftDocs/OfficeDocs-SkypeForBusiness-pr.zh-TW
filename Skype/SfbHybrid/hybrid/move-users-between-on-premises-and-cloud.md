---
title: 在內部部署和雲端之間移動使用者
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 摘要：在內部部署中為混合式啟用的商務用 Skype Server，您可以在內部部署環境與雲端之間移動使用者。
ms.openlocfilehash: 31695b7fa21f4fc873afa6b94bbefa58bbfbdb7b7d22f6da5c6eb972627c8cb8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54334535"
---
# <a name="move-users-between-on-premises-and-cloud"></a>在內部部署和雲端之間移動使用者

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

在已啟用混合式商務用 Skype Server 的內部部署中，您可以在內部部署環境和 Teams 之間移動使用者。 無論使用者是位於內部部署或雲端中，都將視為使用者的商務用 Skype 首頁：

- 位於內部部署的使用者會與內部部署商務用 Skype 伺服器互動。
- 位於線上的使用者可能會與 Teams 服務互動。

*Teams 使用者本身就擁有商務用 Skype 首頁，不論他們是否使用商務用 Skype。* 如果您有內部部署商務用 Skype 同時使用 Teams (並排) 的使用者，則這些使用者位於內部部署。 在內部部署商務用 Skype 的 Teams 使用者無法從其 Teams 用戶端與商務用 Skype 使用者互動，也不能從 Teams 與同盟組織中的使用者通訊。 這類功能只有在使用者從商務用 Skype 內部部署移至線上，且進行 TeamsOnly 時，才會完全可用。 強烈建議您將使用者移至 TeamsOnly 模式，以確保所有傳入聊天和通話的路由都位於其 Teams 用戶端。 如需詳細資訊，請參閱[使用 Teams 搭配商務用 Skype 之組織的商務用 Skype 和遷移與互通性指南](/microsoftteams/migration-interop-guidance-for-teams-with-skype) [Teams 共存](/microsoftteams/coexistence-chat-calls-presence)。

## <a name="prerequisites"></a>先決條件

將使用者移至 TeamsOnly 模式的必要條件：

- 組織必須正確設定 Azure AD 連線，並依照[Configure AZURE ad 連線](configure-azure-ad-connect.md)中所述，同步處理使用者的所有相關屬性。
- 必須設定商務用 Skype 混合式，如[Configure 商務用 Skype 混合](configure-federation-with-skype-for-business-online.md)式中所述。
- 使用者必須已獲指派授權 Teams 和商務用 Skype 線上 (方案 2) 。 商務用 Skype 線上撤銷後，仍然需要商務用 Skype 線上授權。  此外：
    - 如果使用者已在內部部署中啟用電話撥入式會議，依預設，使用者在線上移動使用者之前，還必須在 Teams 中指派音訊會議授權。 使用者一旦移轉到雲端，就會在雲端中佈建 [音訊會議]。 如果因某些原因而想要將使用者移至雲端，但不使用音訊會議功能，您可以在 `Move-CsUser` 中指定 `BypassAudioConferencingCheck` 參數，以覆寫此勾選。
    - 如果使用者已在內部部署中啟用企業語音，使用者在線上移動使用者之前，必須先在 Teams 中指派電話系統授權。 使用者一旦移轉到雲端，就會在雲端中佈建 [電話系統]。 若由於某些原因您想要將使用者移至雲端，但未使用電話系統功能，您可以在中指定參數，以覆寫此檢查 `BypassEnterpriseVoiceCheck` `Move-CsUser` 。


## <a name="moving-users"></a>移動使用者

從內部部署移動使用者至雲端時：

- Teams 使用者可與商務用 Skype 的使用者進行互通性，如果他們 TeamsOnly，也能與其他組織同盟。

- 從內部部署的連絡人會移至 Teams。

- 其組織的現有會議會遷移至線上：如果使用者直接移至 TeamsOnly (請參閱下列) 、會議會轉換成 Teams 會議，否則會議仍然存在商務用 Skype 但會進行遷移，以供線上（而非內部部署）。  會議移轉會同步發生，並在移動使用者之後約 90 分鐘開始。  若要判斷會議移轉狀態，可以使用 [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms)。 請注意，不會移動會議之前上傳的任何內容。

若要將使用者移至 Teams，請使用 Move-CsUser Cmdlet 或商務用 Skype 系統管理員控制台，這兩者都是內部部署工具。 這些工具支援下列移動路徑：

- [從商務用 Skype Server (內部部署) 直接 Teams](move-users-from-on-premises-to-teams.md) (也會將其移至商務用 Skype 線上) 。  不論使用的是哪個版本的商務用 Skype Server 或 Lync Server，都現在只會自動從內部部署移至 Teams 的行為。 您不再需要指定 `-MoveToTeams` 參數來取得此行為。  
- [從 [線上] (Teams 是否只或不) ）為內部部署](move-users-from-the-cloud-to-on-premises.md)。

> [!NOTE] 
> 您不再需要在 Move-CsUser 中指定-MoveToTeams 參數，將使用者直接從內部部署移至 TeamsOnly。 先前若未指定此參數，則會將使用者轉換為位於商務用 Skype Server 內部部署，以商務用 Skype 線上，而且其模式仍保持不變。 現在，當您使用 Move-CsUser 將使用者從內部部署移至雲端時，系統會自動為使用者指派 TeamsOnly 模式，並將其來自內部部署的會議自動轉換成 Teams 會議， `-MoveToTeams` 不論該參數是否實際已指定。 
> 

## <a name="required-administrative-credentials"></a>所需的系統管理認證

若要在內部部署與雲端之間移動使用者，您必須在內部部署商務用 Skype Server 環境和 Teams 組織中使用具有足夠許可權的帳戶。 您可以使用一個具有所有必要許可權的帳戶，也可以使用兩個帳戶，在這種情況下，您可以使用內部部署認證來存取內部部署工具，然後在這些工具中，您會為 Teams 系統管理帳戶提供額外的認證。  

- 在內部部署環境中，執行移動的使用者必須具有商務用 Skype Server 中的 CSServerAdministrator 角色。
- 在 Teams 中，執行移動的使用者必須符合下列其中一個條件：
  - 使用者是全域系統管理員角色的成員。
  - 使用者是 Teams 管理員和使用者管理員角色的成員。
  - 使用者是商務用 Skype 管理員和使用者管理員角色的成員。  

    > [!Important]
    > - 如果您使用商務用 Skype 系統管理員控制台，系統會提示您使用適當的角色為 Microsoft 365 帳戶提供認證，如上所述。 您必須提供一個以 onmicrosoft.com 結尾的帳戶。 如果無法做到，請使用 Move-CsUser Cmdlet。
    >- 如果您是在 PowerShell 中使用 Move-CsUser，您可以使用 onmicrosoft.com 中的任何內部部署帳戶，也可以使用任何已同步處理至 Azure AD 的內部部署帳戶，前提是您也在 Cmdlet 中指定 HostedMigrationOverrideUrl 參數。 裝載的遷移覆寫 URL 的值為下列 URL: 的 variant。 https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>在上述 URL 中，以兩個或三個字元取代 XX，如下所示：
    >   - 在 Teams PowerShell 會話中，執行下列 Cmdlet：<br>`Get-CsTenant|ft identity`
    >   - 產生的值會是下列格式：<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >   - 這兩位數的程式碼是區段中包含的 XX，DC = lyncXX001。 如果是兩個字元的代碼，它會是數位後接數位 (例如 0a) 。 如果是三個字元的代碼，它會是兩個字母后接數位 (例如 jp1) 。 在所有情況下，您會在 XX 碼之後立即看到001。


## <a name="voice-configuration-requirements"></a>語音設定需求

如果使用者已在內部部署中為 enterprise voice 設定，則在您將使用者移至線上時，您必須協調更新其語音設定，或者，您也可以在不含電話語音功能的情況下進行遷移。 可用的選項取決於使用者在線上時使用 Teams 還是商務用 Skype 用戶端：

- 您可以將使用者的電話語音提供者更新為使用 [Microsoft 通話方案](/microsoftteams/calling-plans-for-office-365)。 這是使用者是否會使用 Teams 或商務用 Skype 用戶端的選項。
- 您可以繼續使用內部部署 PSTN 提供者：
  - 將使用 Teams 的語音使用者必須設定進行[直接路由](/microsoftteams/direct-routing-plan)。 只有在使用者從內部部署移至線上後，才能使用直接路由。
  - 在線上移動之後，將使用商務用 Skype 用戶端的語音使用者必須設定商務用 Skype 混合式語音功能。

如需混合式環境中電話語音選項的詳細資訊，以及支援性清單，請參閱 [使用 PSTN 連線的混合式環境中的使用者帳戶](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)。

## <a name="other-considerations"></a>其他考量事項

內部部署和線上環境中的原則 (例如，控制訊息、會議、通話行為) 互不相干。 您可以考慮在環境中設定任何原則，並將其指派給使用者，然後再將該使用者從內部部署移至雲端，使其在遷移到線上時立即具備正確的設定。

## <a name="see-also"></a>另請參閱

[將使用者從內部部署移動至 Teams](move-users-from-on-premises-to-teams.md)

[設定會議移轉服務 (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[規劃直接路由](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
