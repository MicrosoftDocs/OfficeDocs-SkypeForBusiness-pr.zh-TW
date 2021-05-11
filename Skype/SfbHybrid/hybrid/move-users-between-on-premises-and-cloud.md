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
description: 摘要：在內部部署中為混合式啟用的商務用 Skype Server，您可以在內部部署環境與雲端之間移動使用者 (是否要 Microsoft Teams 或在其退休) 之前商務用 Skype 線上。
ms.openlocfilehash: 8fce1799ba3e10f2e96b8beab0fbde7805c7c229
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305953"
---
# <a name="move-users-between-on-premises-and-cloud"></a>在內部部署和雲端之間移動使用者

在已啟用混合式商務用 Skype Server 的內部部署中，您可以在內部部署環境與雲端之間移動使用者 (是否 Microsoft Teams 或在其退休) 之前商務用 Skype 線上。 無論使用者是位於內部部署或雲端中，都將視為使用者的商務用 Skype 首頁：

- 位於內部部署的使用者會與內部部署商務用 Skype 伺服器互動。
- 已在線上狀態的使用者可以跟與商務用 Skype Online 服務互動。

*Teams 使用者本身商務用 Skype 首頁，不論他們是否使用商務用 Skype。* 如果您有內部部署商務用 Skype 同時使用 Teams (並排) 的使用者，則這些使用者位於內部部署。 在內部部署商務用 Skype 的 Teams 使用者無法從其 Teams 用戶端與商務用 Skype 使用者互動，也不能從 Teams 與同盟組織中的使用者通訊。 這類功能只有在使用者從商務用 Skype 內部部署移至線上，且進行 TeamsOnly 時，才會完全可用。 當您將使用者移至線上時，您可以允許他們使用商務用 Skype Online (或 Teams)，或僅使用 Teams Only。 強烈建議您將使用者移至 [僅 Teams] 模式，以確保所有傳入聊天和通話的路由都位於其 Teams 用戶端。 如需詳細資訊，請參閱[使用 Teams 搭配商務用 Skype 之組織的商務用 Skype 和遷移與互通性指南](/microsoftteams/migration-interop-guidance-for-teams-with-skype) [Teams 共存](/microsoftteams/coexistence-chat-calls-presence)。

## <a name="prerequisites"></a>必要條件

將使用者移至雲端的必要條件 (是否只 Teams 模式或在其退休) 之前商務用 Skype 線上：

- 組織必須正確設定 Azure AD 連線，並依照[Configure AZURE ad 連線](configure-azure-ad-connect.md)中所述，同步處理使用者的所有相關屬性。
- 必須設定商務用 Skype 混合式，如[Configure 商務用 Skype 混合](configure-federation-with-skype-for-business-online.md)式中所述。
- 使用者必須已獲指派授權 Teams 和商務用 Skype 線上 (方案 2) 。 商務用 Skype 線上退休後，仍然需要商務用 Skype Online licese。  此外：
    - 如果使用者已在內部部署中啟用電話撥入式會議，依預設，使用者在線上移動使用者之前，還必須在 Teams 中指派音訊會議授權。 使用者一旦移轉到雲端，就會在雲端中佈建 [音訊會議]。 若由於某些原因您想要將使用者移至雲端，但未使用音訊會議功能，您可以在中指定參數，以覆寫此檢查 `BypassAudioConferencingCheck` `Move-CsUser` 。
    - 如果使用者已在內部部署中啟用企業語音，使用者在線上移動使用者之前，必須先在 Teams 中指派電話系統授權。 使用者一旦移轉到雲端，就會在雲端中佈建 [電話系統]。 若由於某些原因您想要將使用者移至雲端，但未使用電話系統功能，您可以在中指定參數，以覆寫此檢查 `BypassEnterpriseVoiceCheck` `Move-CsUser` 。


## <a name="moving-users"></a>移動使用者

從內部部署移動使用者至雲端時：

- Teams 使用者可與商務用 Skype 的使用者進行互通性，如果他們 TeamsOnly，也能與其他組織同盟。
- 使用者開始在雲端中的商務用 Skype Online 服務，以使用任何商務用 Skype 功能。
- 從內部部署的連絡人會移至雲端 (，以 Teams 或商務用 Skype 線上) 。
- 其組織的現有會議會遷移至線上：如果使用者直接移至 TeamsOnly (請參閱下列) 、會議會轉換成 Teams 會議，否則會議仍然存在商務用 Skype 但會進行遷移，以供線上（而非內部部署）。  會議移轉會同步發生，並在移動使用者之後約 90 分鐘開始。  若要判斷會議移轉狀態，可以使用 [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms)。 請注意，不會移動會議之前上傳的任何內容。

若要在內部部署與雲端之間移動使用者 (是否 Teams 或商務用 Skype 線上) ，請使用 Move-CsUser 指令程式或商務用 Skype 系統管理員控制台，兩者都是內部部署工具。 這些工具支援三種不同的移動路徑：

- [從商務用 Skype Server (內部部署) 直接 Teams](move-users-from-on-premises-to-teams.md) (也會將其移至商務用 Skype 線上) 。  只從內部部署移至 Teams 的選項 *目前* 可用於商務用 Skype Server 2019 及商務用 Skype Server 2015 累計更新8。 使用舊版商務用 Skype Server 的組織可以一開始將使用者移至商務用 Skype Online，然後在使用者上線時為他們套用 TeamsOnly 模式，便能將使用者移至 TeamsOnly。 

> [!NOTE] 
> 在 Move-CsUser 中指定-MoveToTeams 參數之後，將不再需要將使用者直接從內部部署移至 TeamsOnly。 目前如果未指定此參數，則會將使用者轉換為位於商務用 Skype Server 內部部署，以商務用 Skype 線上，且其模式保持不變。 淘汰後，將使用者從內部部署移至雲端並使用 Move-CsUser 時，系統會自動指派使用者 TeamsOnly 模式，並將其來自內部部署的會議 automtically 轉換成 Teams 會議，不論是否實際指定參數，都如同已指定-MoveToTeams 參數。 我們預計此功能會在實際退休2021年7月31日之前發佈。

- [從商務用 Skype Server (內部部署) 到商務用 Skype 線上](move-users-from-on-premises-to-skype-for-business-online.md)。 此選項不久將不再可用。
- [從 [線上] (Teams 是否只或不) ）為內部部署](move-users-from-the-cloud-to-on-premises.md)。

## <a name="required-administrative-credentials"></a>所需的系統管理認證

若要在內部部署與雲端之間移動使用者，您必須在內部部署商務用 Skype Server 環境和 Teams 組織中使用具有足夠許可權的帳戶。 您可以使用一個具有所有必要許可權的帳戶，也可以使用兩個帳戶，在這種情況下，您可以使用內部部署認證來存取內部部署工具，然後在這些工具中，您會為 Teams 系統管理帳戶提供額外的認證。  

- 在內部部署環境中，執行移動的使用者必須具備商務用 Skype Server 中的 CSServerAdminstrator 角色。
- 在 Teams 中，執行移動的使用者必須符合下列其中一個條件：
  - 使用者是全域系統管理員角色的成員。
  - 使用者是 Teams 系統管理員角色和使用者管理員角色的成員。
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

## <a name="see-also"></a>請參閱

[將使用者從內部部署移動至 Teams](move-users-from-on-premises-to-teams.md)

[將使用者從內部部署移動至商務用 Skype Online](move-users-from-on-premises-to-skype-for-business-online.md)

[設定會議移轉服務 (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[規劃直接路由](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
