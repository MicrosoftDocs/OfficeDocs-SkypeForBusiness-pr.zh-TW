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
ms.openlocfilehash: ac32c4037cf275d9a6a7545701c1899742d8fd12
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705872"
---
# <a name="move-users-between-on-premises-and-cloud"></a>在內部部署和雲端之間移動使用者

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

在商務用 Skype Server的內部部署中，商務用 Skype的使用者也可以使用 Teams，但並非所有 Teams 功能都可供這類使用者使用，只要他們設定為使用內部部署商務用 Skype Server部署即可。 這些使用者稱為「常用」內部部署，而當這些使用者位於內部部署時，某些 Teams 功能無法使用，例如：
- 無法透過使用者的 Teams 用戶端與其他組織中的使用者進行同盟通話和聊天
- 透過使用者的 Teams 用戶端與組織中使用商務用 Skype用戶端的其他使用者進行 Interop 通訊。
- 如果使用者獲指派電話系統授權) ，則 PSTN 通話功能 (。

若要取得完整的 Teams 功能，這些使用者必須從內部部署商務用 Skype移至雲端，此時使用者會變成 TeamsOnly。 將使用者從內部部署移至雲端的動作，會將使用者的共同存在模式設定為 TeamsOnly。 一旦使用者移至雲端，他們就是 TeamsOnly，這表示所有傳入的聊天和通話都會進入其 Teams 用戶端。 如需詳細資訊，請參閱[Teams 與商務用 Skype共存](/microsoftteams/coexistence-chat-calls-presence)和移轉，[以及搭配使用 Teams 與商務用 Skype之組織的互通性指引](/microsoftteams/migration-interop-guidance-for-teams-with-skype)。

若要將使用者從內部部署商務用 Skype Server部署移至雲端，需要[設定商務用 Skype混合式](/skypeforbusiness/hybrid/plan-hybrid-connectivity)。  啟用混合式部署之後，您可以將使用者從內部部署環境移至雲端，使其成為 TeamsOnly，如下所述。 如有必要，您也可以將 TeamsOnly 使用者移回內部部署 Skype 以進行 Bsuiness 部署。 



## <a name="prerequisites"></a>先決條件

將使用者移至 TeamsOnly 模式的必要條件：

- 組織必須正確設定 Azure AD Connect，並同步處理使用者的所有相關屬性，如設定 [Azure AD Connect](configure-azure-ad-connect.md)中所述。
- 商務用 Skype混合式必須設定，如設定[商務用 Skype混合式](configure-federation-with-skype-for-business-online.md)中所述。
- 使用者必須獲指派 Teams 和 商務用 Skype Online (方案 2) 的授權。 即使在商務用 Skype Online 淘汰之後，仍需要商務用 Skype Online 授權。  此外：
    - 如果使用者已在內部部署環境中啟用撥入式會議，則使用者也必須在 Teams 中指派音訊會議授權，才能將使用者移至線上。 使用者一旦移轉到雲端，就會在雲端中佈建 [音訊會議]。 
    - 如果使用者已在內部部署環境中啟用企業語音，則使用者必須在 Teams 中指派 Teams 電話授權，才能讓使用者上線。 移轉至雲端之後，將會為雲端中的電話系統布建使用者。 
  
自 2022 年 7 月 31 日起，若要在內部部署與雲端之間移動使用者，您必須使用下列最低版本的 商務用 Skype Server 或 Lync Server：

</br>
</br>

|內部部署產品|必要的最低版本|必要的最小組建|
|---|---|---|
|商務用 Skype Server 2019| CU6 |7.0.2046.385|
|商務用 Skype Server 2015| CU12|6.0.9319.619|
|Lync Server 2013| CU10 搭配 Hotfix 7|5.0.8308.1182|

</br>
</br>

## <a name="moving-users"></a>移動使用者

從內部部署移動使用者至雲端時：

- 使用者會變成 TeamsOnly 使用者，這表示使用者：
   -  接收並起始 Teams 用戶端中的所有聊天和通話。
   -  排程 Teams 中的所有會議。
   -  無法在商務用 Skype中起始聊天或通話，或排程會議。
   -  可以加入商務用 Skype未來已經有或已收到的會議。 不過，在 Microsoft 移除指定 TeamsOnly 使用者的 商務用 Skype Online 基礎結構之後，TeamsOnly 使用者只能匿名加入商務用 Skype會議。 從 2022 年 10 月開始，將使用者從內部部署移至僅限混合式組織中的 Teams，將不再使用 商務用 Skype Online 基礎結構來布建。 如果邀請這些使用者參加商務用 Skype會議，則必須匿名加入。 如需詳細資訊，請參閱[具有商務用 Skype Server內部部署的組織指引](/MicrosoftTeams/skype-for-business-online-retirement.md#guidance-for-organizations-with-on-premises-deployments-of-skype-for-business-server)。

- 使用者已啟用與商務用 Skype使用者的互通性，也可以與其他組織同盟。
- 內部部署的連絡人會移至 Teams。
- 他們在未來安排的現有會議會轉換成 Teams 會議。 會議移轉會同步發生，並在移動使用者之後約 90 分鐘開始。  若要判斷會議移轉狀態，可以使用 [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms)。 在會議之前上傳的任何內容不會移動。
- 獲指派 Teams 電話授權的使用者可以在正確設定後存取 PSTN 功能。
 
若要將使用者移至 Teams，請使用 Move-CsUser Cmdlet 或商務用 Skype 管理員 主控台，這兩者都是內部部署工具。 這些工具支援下列移動路徑：

- [從內部部署商務用 Skype Server () 至僅限 Teams](move-users-from-on-premises-to-teams.md)。
- [從線上 (Teams 是否只) ，到內部部署](move-users-from-the-cloud-to-on-premises.md)。


> [!NOTE] 
>  不論使用哪個版本的 商務用 Skype Server 或 Lync Server，直接從內部部署移至僅限 Teams 的行為都是自動的。 不再需要指定 `-MoveToTeams` 中的 切換 `Move-CsUser` ，即可將使用者直接從內部部署移至 TeamsOnly。 先前，如果未指定此參數，則使用者會從內部部署商務用 Skype Server的住家轉換為 商務用 Skype Online，且其模式會保持不變。 現在，使用 將使用者從內部部署移至雲 `Move-CsUser` 端時，使用者會自動獲指派 TeamsOnly 模式，且其來自內部部署的會議會自動轉換成 Teams 會議，就如同已指定參數一樣 `-MoveToTeams` ，不論是否已實際指定切換。 


## <a name="required-administrative-credentials"></a>所需的系統管理認證

若要在內部部署與雲端之間移動使用者，您必須在內部部署商務用 Skype Server環境和 Teams 組織中使用具有足夠許可權的帳戶。 您可以使用一個具有所有必要許可權的帳戶，也可以使用兩個帳戶。 如果您使用兩個帳戶，則會使用內部部署認證來存取內部部署工具，然後在這些工具中，您會為 Teams 系統管理帳戶提供額外的認證。  

- 在內部部署環境中，執行移動的使用者必須在 商務用 Skype Server 中擁有 CSServerAdministrator、CsUserAdministrator 和 RTCUniversalUserAdmins 角色。
- 在 Teams 中，執行移動的使用者必須至少是下列其中一個角色的成員：
  - 全域管理員角色
  - Teams 系統管理員角色
  - 商務用 Skype系統管理員角色。  

    > [!Important]
    > - 如果您使用商務用 Skype 管理員 主控台，系統會提示您提供具有適當角色之 Microsoft 365 帳戶的認證，如上所述。 您必須提供以 .onmicrosoft.com 結尾的帳戶。 如果無法這麼做，請使用 Move-CsUser Cmdlet。
    >- 如果您在 PowerShell 中使用 Move-CsUser，您可以使用結尾為 .onmicrosoft.com 的帳戶，或使用任何同步處理至 Azure AD 的內部部署帳戶，前提是您也可以在 Cmdlet 中指定 HostedMigrationOverrideUrl 參數。 裝載移轉覆寫 URL 的值是下列 URL 的變體： https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>在上述 URL 中，將 XX 取代為兩個或三個字元，如下所示：
    >   - 在 Teams PowerShell 會話中，執行下列 Cmdlet：<br>`Get-CsTenant | ft ServiceInstance`
    >   - 產生的值會是下列格式：<br>`MicrosoftCommunicationsOnline/YYYY-XX-ZZ`
    >   - 兩個或三個字元的程式碼是包含在 YYYY-XX-ZZ 區段中的 XX。 如果它是兩個字元的程式碼，則會是數位，後面接著數位 (例如 4A) 。 如果是三個字元的程式碼，則會是兩個字母，後面接著一個數位 (，例如 JP1) 。 例如 NOAM-4A-S7。


## <a name="voice-configuration-requirements"></a>語音設定需求

如果使用者已在內部部署環境中設定企業語音，則當您將使用者移至線上時，您必須協調更新其語音設定。 或者，您可以在沒有電話語音功能的情況下進行移轉。 
- 您可以更新使用者的電話語音提供者，以使用 [Microsoft 通話方案](/microsoftteams/calling-plans-for-office-365)。 這是使用者將使用 Teams 或商務用 Skype用戶端的選項。
- 您可以繼續使用內部部署 PSTN 提供者：
  - 將使用 Teams 的語音使用者必須設定為 [直接路由](/microsoftteams/direct-routing-plan)。 只有在使用者從內部部署移至線上之後，才能使用直接路由。

如需混合式環境中電話語音選項的詳細資訊，包括可支援性矩陣，請參閱具有 [PSTN 連線的混合式環境中的使用者帳戶](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)。

## <a name="other-considerations"></a>其他考量事項

內部部署和線上環境中的原則 (例如，控制訊息、會議、通話行為) 互不相干。 您可以考慮在環境中設定任何原則，並將它們指派給使用者，再將該使用者從內部部署移至雲端，讓他們在移轉至線上時擁有正確的設定。

## <a name="see-also"></a>另請參閱

[將使用者從內部部署移動至 Teams](move-users-from-on-premises-to-teams.md)

[設定會議移轉服務 (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[規劃直接路由](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
