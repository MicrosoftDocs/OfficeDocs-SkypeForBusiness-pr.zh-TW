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
description: 摘要：在內部部署中為混合式啟用商務用 Skype Server 的內部部署，您可以在內部部署環境與雲端之間移動使用者（不論是 Microsoft 團隊或商務用 Skype Online）。
ms.openlocfilehash: eede6062bd9d03a2d9d6062a6dacb861ce37e14c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221123"
---
# <a name="move-users-between-on-premises-and-cloud"></a>在內部部署和雲端之間移動使用者

在啟用混合式的商務用 Skype Server 內部部署中，您可以在內部部署環境和雲端之間移動使用者 (無論是移至 Microsoft Teams 或商務用 Skype Online)。 無論使用者是位於內部部署或雲端中，都將視為使用者的商務用 Skype 首頁：

- 位於內部部署的使用者會與內部部署商務用 Skype 伺服器互動。
- 已在線上狀態的使用者可以跟與商務用 Skype Online 服務互動。

*小組使用者本身擁有商務用 skype 的首頁，不論他們是否使用商務用 Skype。* 如果您有內部部署商務用 Skype 的使用者，且該使用者同時使用團隊（並列），這些使用者便會位於內部部署環境。 具有商務用 Skype 之商務用 Skype 的團隊使用者不具備從其團隊用戶端與商務用 Skype 使用者互動的能力，也無法與同盟組織中的使用者進行通訊。 這類功能只有在使用者從商務用 Skype （內部）移至線上時才可用。 當您將使用者移至線上時，您可以允許他們使用商務用 Skype Online (或 Teams)，或僅使用 Teams Only。 如果組織已經使用 Teams，強烈建議您將其移至 TeamsOnly 模式，這會確保所有路由傳送的傳入聊天和通話都會到達其 Teams 用戶端。 如需詳細資訊，請參閱使用團隊與商務用[skype 結合使用](/microsoftteams/migration-interop-guidance-for-teams-with-skype)之[商務用 skype](/microsoftteams/coexistence-chat-calls-presence)和遷移的團隊和相關的指導方針。

## <a name="prerequisites"></a>必要條件

將使用者移至雲端（不論是僅限商務用 Skype 或僅限小組模式）的必要條件：

- 組織必須正確地設定 Azure AD Connect，並依照[Configure AZURE Ad connect](configure-azure-ad-connect.md)中所述的方式，同步處理使用者的所有相關屬性。
- 必須設定商務用 skype 混合（如[設定商務用 skype 混合](configure-federation-with-skype-for-business-online.md)式中所述）。
- 必須為使用者指派商務用 Skype Online (方案2) 的授權，而如果要使用 Teams，使用者也必須擁有 Teams 的授權。  此外：
    - 如果使用者已在內部部署中啟用電話撥入式會議，則預設情況下，使用者在執行移動使用者的線上之前，還必須在 Microsoft 365 或 Office 365 中指派音訊會議授權。 使用者一旦移轉到雲端，就會在雲端中佈建 [音訊會議]。 若由於某些原因您想要將使用者移至雲端，但未使用音訊會議功能，您可以在中指定參數，以覆寫此檢查 `BypassAudioConferencingCheck` `Move-CsUser` 。
    - 如果使用者已在內部部署中啟用 Enterprise Voice，使用者在線上移動使用者之前，必須先在 Microsoft 365 或 Office 365 中指派電話系統授權。 使用者一旦移轉到雲端，就會在雲端中佈建 [電話系統]。 若由於某些原因您想要將使用者移至雲端，但未使用電話系統功能，您可以在中指定參數，以覆寫此檢查 `BypassEnterpriseVoiceCheck` `Move-CsUser` 。


## <a name="moving-users"></a>移動使用者

從內部部署移動使用者至雲端時：

- 使用者開始在雲端中的商務用 Skype Online 服務，以使用任何商務用 Skype 功能。
- Teams 使用者可與商務用 Skype 使用者互通，並可與其他組織同盟。
- 從內部部署的連絡人會移至雲端（商務用 Skype 或小組）。
- 其組織的現有會議會遷移至線上：如果使用者直接移至 TeamsOnly （請參閱以下）、會議會轉換為小組會議，否則會議會保留商務用 Skype，但是會進行遷移，以供線上（而非內部部署）。  會議移轉會同步發生，並在移動使用者之後約 90 分鐘開始。  若要判斷會議移轉狀態，可以使用 [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms)。 請注意，不會移動會議之前上傳的任何內容。

若要在內部部署與雲端之間移動使用者（不論是團隊或商務用 Skype Online），請使用 Move-CsUser Cmdlet 或商務用 Skype 系統管理員控制台，這兩者都是內部部署工具。 這些工具支援三種不同的移動路徑：

- [從商務用 Skype Server （內部部署）到商務用 Skype Online](move-users-from-on-premises-to-skype-for-business-online.md)。
- [從商務用 Skype 伺服器（內部部署）直接向小組](move-users-from-on-premises-to-teams.md)（也就是將其移至商務用 skype Online）。  在商務用 Skype Server 2019 中可使用 [僅限從內部自行移至小組] 選項，以及商務用 Skype Server 2015 的累計更新8。 使用舊版商務用 Skype Server 的組織可以一開始將使用者移至商務用 Skype Online，然後在使用者上線時為他們套用 TeamsOnly 模式，便能將使用者移至 TeamsOnly。
- [從 [線上] （不論是否僅限小組）到 [內部部署](move-users-from-the-cloud-to-on-premises.md)]。

## <a name="required-administrative-credentials"></a>所需的系統管理認證

若要在內部部署與雲端之間移動使用者，您必須在內部部署商務用 Skype 伺服器環境和 Microsoft 365 或 Office 365 組織中使用具有足夠許可權的帳戶。 您可以使用一個具有所有必要許可權的帳戶，也可以使用兩個帳戶，在這種情況下，您會使用內部部署認證來存取內部部署工具，然後在這些工具中，您會為 Microsoft 365 或 Office 365 系統管理帳戶提供額外的認證。  

- 在內部部署環境中，執行移動的使用者必須具備商務用 Skype Server 中的 CSServerAdminstrator 角色。
- 在 Microsoft 365 和 Office 365 中，執行移動的使用者必須是全域系統管理員或同時具有商務用 Skype 管理員和使用者管理員角色。  

    > [!Important]
    > - 如果您使用的是商務用 Skype 系統管理員控制台，系統會提示您使用適當的角色為 Microsoft 365 或 Office 365 帳戶提供認證，如上所述。 您必須提供一個以 onmicrosoft.com 結尾的帳戶。 如果無法做到，請使用 Move-CsUser Cmdlet。
    >- 如果您是在 PowerShell 中使用 Move-CsUser，您可以使用 onmicrosoft.com 中的任何內部部署帳戶，也可以使用任何已同步處理至 Azure AD 的內部部署帳戶，前提是您也在 Cmdlet 中指定 HostedMigrationOverrideUrl 參數。 裝載的遷移覆寫 URL 的值為下列 URL: 的 variant。https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>在上述 URL 中，以兩個或三個字元取代 XX，如下所示：
    >   - 在商務用 Skype Online PowerShell 會話中，執行下列 Cmdlet：<br>`Get-CsTenant|ft identity`
    >    - 產生的值會是下列格式：<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - 這兩位數的程式碼是區段中包含的 XX，DC = lyncXX001。 如果是兩個字元的代碼，它會是一個數位後接數位（如0a）。 如果是三個字元的代碼，它會是兩個字母后接一位數（例如 jp1）。 在所有情況下，您會在 XX 碼之後立即看到001。


## <a name="voice-configuration-requirements"></a>語音設定需求

如果使用者已在內部部署中為 enterprise voice 設定，則在您將使用者移至線上時，您必須協調更新其語音設定，或者，您也可以在不含電話語音功能的情況下進行遷移。 可用的選項取決於使用者是否要在線上時使用團隊或商務用 Skype 用戶端：

- 您可以將使用者的電話語音提供者更新為使用[Microsoft 通話方案](/microsoftteams/calling-plans-for-office-365)。 這是使用者是否要使用團隊或商務用 Skype 用戶端的選項。
- 您可以繼續使用內部部署 PSTN 提供者：
  - 必須針對[直接路由](/microsoftteams/direct-routing-plan)設定要使用小組的語音使用者。 只有在使用者從內部部署移至線上後，才能使用直接路由。
  - 在線上移動商務用 Skype 用戶端後，必須為商務用 Skype 混合語音功能設定語音使用者。

如需混合式環境中電話語音選項的詳細資訊，以及支援性清單，請參閱[使用 PSTN 連線的混合式環境中的使用者帳戶](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)。

## <a name="other-considerations"></a>其他考量事項

內部部署和線上環境中的原則 (例如，控制訊息、會議、通話行為) 互不相干。 您可以考慮在環境中設定任何原則，並將其指派給使用者，然後再將該使用者從內部部署移至雲端，使其在遷移到線上時立即具備正確的設定。

## <a name="see-also"></a>另請參閱

[將使用者從內部部署移動至商務用 Skype Online](move-users-from-on-premises-to-skype-for-business-online.md)

[將使用者從內部部署移動至 Teams](move-users-from-on-premises-to-teams.md)

[設定會議移轉服務 (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[規劃直接路由](/microsoftteams/direct-routing-plan)

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
