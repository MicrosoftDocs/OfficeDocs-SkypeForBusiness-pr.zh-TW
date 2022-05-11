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
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 摘要：在已啟用混合式商務用 Skype Server的內部部署中，您可以在內部部署環境與雲端之間移動使用者。
ms.openlocfilehash: 15e237fdf54854a86216bc3890ae26209449c146
ms.sourcegitcommit: d847256fca80e4e8954f767863c880dc8472ca04
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2022
ms.locfileid: "65304001"
---
# <a name="move-users-between-on-premises-and-cloud"></a>在內部部署和雲端之間移動使用者

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

在已啟用混合式商務用 Skype Server的內部部署中，您可以在內部部署環境與Teams之間移動使用者。 無論使用者是位於內部部署或雲端中，都將視為使用者的商務用 Skype 首頁：

- 位於內部部署的使用者會與內部部署商務用 Skype伺服器互動。
- 上線的使用者可以與Teams服務互動。

*不論使用者是否使用商務用 Skype，Teams使用者原本就擁有商務用 Skype主機。* 如果您有同時使用Teams () 的內部部署商務用 Skype使用者，這些使用者會位於內部部署。 Teams內部部署商務用 Skype使用者無法與其Teams用戶端中的商務用 Skype使用者互通，也無法從Teams與同盟組織中的使用者通訊。 只有在使用者從內部部署移至內部部署商務用 Skype，並讓 TeamsOnly 上線之後，才能完整使用這類功能。 建議您將使用者移至 TeamsOnly 模式，這可確保所有傳入聊天和通話的路由都會落在其Teams用戶端中。 如需詳細資訊，[請參閱Teams與商務用 Skype](/microsoftteams/coexistence-chat-calls-presence)和移轉共存，[以及使用Teams與商務用 Skype的組織互通性指引](/microsoftteams/migration-interop-guidance-for-teams-with-skype)。

## <a name="prerequisites"></a>必要條件

將使用者移至 TeamsOnly 模式的必要條件：

- 組織必須正確設定 Azure AD 連線，並同步處理使用者的所有相關屬性，如設定[Azure AD 連線](configure-azure-ad-connect.md)中所述。
- 商務用 Skype混合式必須設定，如設定[商務用 Skype混合式](configure-federation-with-skype-for-business-online.md)中所述。
- 使用者必須獲指派Teams的授權，商務用 Skype Online (方案 2) 。 即使在 商務用 Skype Online 淘汰之後，仍需要 商務用 Skype Online 授權。  此外：
    - 如果已在內部部署中啟用使用者的撥入式會議，則使用者也必須在Teams中指派音訊會議授權，才能將使用者移至線上。 使用者一旦移轉到雲端，就會在雲端中佈建 [音訊會議]。 
    - 如果使用者已在內部部署環境中啟用企業語音，則使用者必須在Teams中指派電話系統授權，才能將使用者移至線上。 移轉至雲端之後，系統會為雲端中的電話系統布建使用者。 


## <a name="moving-users"></a>移動使用者

從內部部署移動使用者至雲端時：

- Teams使用者能夠與商務用 Skype使用者互通性，而且如果他們是 Teams，他們也可以與其他組織同盟。

- 內部部署的連絡人會移至Teams。

- 他們在未來安排的現有會議會轉換成Teams會議。 會議移轉會同步發生，並在移動使用者之後約 90 分鐘開始。  若要判斷會議移轉狀態，可以使用 [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms)。 在會議之前上傳的任何內容不會移動。

若要將使用者移至Teams，請使用 Move-CsUser Cmdlet 或商務用 Skype系統管理員主控台，這兩者都是內部部署工具。 這些工具支援下列移動路徑：

- [從商務用 Skype Server (內部部署) 直接到僅Teams](move-users-from-on-premises-to-teams.md)。  不論使用哪一版的 商務用 Skype Server 或 Lync Server，直接從內部部署移至僅Teams的行為現在都是自動的。 您不再需要指定 `-MoveToTeams` 參數來取得此行為。  
- [從線上 (是否只Teams) 到內部部署](move-users-from-the-cloud-to-on-premises.md)。

> [!NOTE] 
> 不再需要在 Move-CsUser 中指定 -MoveToTeams 參數，即可將使用者直接從內部部署移至 TeamsOnly。 先前，如果未指定此參數，則使用者會從內部部署商務用 Skype Server的住家轉換為 商務用 Skype Online，且其模式會保持不變。 現在，使用 Move-CsUser 將使用者從內部部署移至雲端時，系統會自動指派 TeamsOnly 模式，且其來自內部部署的會議會自動轉換為Teams會議，就如同已指定參數一樣 `-MoveToTeams` ，不論是否實際指定參數。 
> 

## <a name="required-administrative-credentials"></a>所需的系統管理認證

若要在內部部署與雲端之間移動使用者，您必須在內部部署商務用 Skype Server環境和Teams組織中使用具有足夠許可權的帳戶。 您可以使用一個具有所有必要許可權的帳戶，也可以使用兩個帳戶。 如果您使用兩個帳戶，則會使用內部部署認證來存取內部部署工具，然後在這些工具中，您會為Teams系統管理帳戶提供額外的認證。  

- 在內部部署環境中，執行移動的使用者必須在 商務用 Skype Server 中擁有 CSServerAdministrator、CsUserAdministrator 和 RTCUniversalUserAdmins 角色。
- 在Teams中，執行移動的使用者必須至少是下列其中一個角色的成員：
  - 全域管理員角色
  - Teams系統管理員角色
  - 商務用 Skype系統管理員角色。  

    > [!Important]
    > - 如果您使用商務用 Skype系統管理員主控台，系統會提示您提供具有適當角色之Microsoft 365帳戶的認證，如上所述。 您必須提供以 .onmicrosoft.com 結尾的帳戶。 如果無法這麼做，請使用 Move-CsUser Cmdlet。
    >- 如果您在 PowerShell 中使用 Move-CsUser，您可以使用結尾為 .onmicrosoft.com 的帳戶，或使用任何同步處理至 Azure AD 的內部部署帳戶，前提是您也可以在 Cmdlet 中指定 HostedMigrationOverrideUrl 參數。 裝載移轉覆寫 URL 的值是下列 URL 的變體： https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>在上述 URL 中，將 XX 取代為兩個或三個字元，如下所示：
    >   - 在 Teams PowerShell 會話中，執行下列 Cmdlet：<br>`Get-CsTenant | ft ServiceInstance`
    >   - 產生的值會是下列格式：<br>`MicrosoftCommunicationsOnline/YYYY-XX-ZZ`
    >   - 兩個或三個字元的程式碼是包含在 YYYY-XX-ZZ 區段中的 XX。 如果它是兩個字元的程式碼，則會是數位，後面接著數位 (例如 4A) 。 如果是三個字元的程式碼，則會是兩個字母，後面接著一個數位 (，例如 JP1) 。 例如 NOAM-4A-S7。


## <a name="voice-configuration-requirements"></a>語音設定需求

如果使用者已在內部部署環境中設定企業語音，則當您將使用者移至線上時，您必須協調更新其語音設定。 或者，您可以在沒有電話語音功能的情況下進行移轉。 可用的選項取決於使用者在上線後，是否會使用Teams或商務用 Skype用戶端：

- 您可以更新使用者的電話語音提供者，以使用 [Microsoft 通話方案](/microsoftteams/calling-plans-for-office-365)。 這是使用者將使用Teams或商務用 Skype用戶端的選項。
- 您可以繼續使用內部部署 PSTN 提供者：
  - 將使用Teams的語音使用者必須設定直接[路由](/microsoftteams/direct-routing-plan)。 只有在使用者從內部部署移至線上之後，才能使用直接路由。
  - 將商務用 Skype用戶端移至線上之後，語音使用者必須設定為商務用 Skype 混合式語音功能。

如需混合式環境中電話語音選項的詳細資訊，包括可支援性矩陣，請參閱具有 [PSTN 連線的混合式環境中的使用者帳戶](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)。

## <a name="other-considerations"></a>其他考量事項

內部部署和線上環境中的原則 (例如，控制訊息、會議、通話行為) 互不相干。 您可以考慮在環境中設定任何原則，並將它們指派給使用者，再將該使用者從內部部署移至雲端，讓他們在移轉至線上時擁有正確的設定。

## <a name="see-also"></a>另請參閱

[將使用者從內部部署移動至 Teams](move-users-from-on-premises-to-teams.md)

[設定會議移轉服務 (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[規劃直接路由](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
