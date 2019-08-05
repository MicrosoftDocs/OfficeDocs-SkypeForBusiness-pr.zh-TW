---
title: 在內部部署與雲端之間移動使用者
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
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
description: '摘要: 在已啟用混合式商務用 Skype Server 的內部部署中, 您可以在內部部署環境和雲端 (無論是 Microsoft 團隊或商務用 Skype Online) 之間移動使用者。'
ms.openlocfilehash: b7e3ecc46af5a3043848d9291394c0bff7835883
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185455"
---
# <a name="move-users-between-on-premises-and-cloud"></a>在內部部署與雲端之間移動使用者

在已啟用混合式商務用 Skype Server 的內部部署中, 您可以在內部部署環境和雲端 (無論是 Microsoft 團隊或商務用 Skype Online) 之間移動使用者。 使用者是否位於內部部署或雲端, 稱為使用者的商務用 Skype 家用版:

- 內部部署的使用者會與內部部署的商務用 Skype 伺服器互動。
- 以線上為宿主的使用者可能會與商務用 Skype Online 服務互動。

*團隊使用者本身就擁有商務用 skype 家用版, 不論他們使用的是商務用 Skype 還是不使用商務用 Skype。* 如果您使用的是內部部署的商務用 Skype 使用者, 而這些使用者也是使用團隊 (並排), 這些使用者就會駐留在內部部署。 在內部部署商務用 Skype 的小組使用者, 無法從其小組用戶端與商務用 Skype 使用者進行交互操作, 也不能從小組與聯盟組織中的使用者進行通訊。 此功能只有在使用者從商務用 Skype (在內部) 移至線上時才可使用。 當您將使用者移至 [線上] 時, 您可以允許他們使用商務用 Skype Online (以及 (選擇性) 團隊), 或者您只能將其設為小組成員。 如果您的組織已在使用團隊, 強烈建議您將他們移至 [僅限團隊] 模式, 這將確保所有傳入聊天和通話的路由都在其團隊用戶端中。 如需更多詳細資料, 請參閱[與商務用 skype 共存的小組](/microsoftteams/coexistence-chat-calls-presence), 以及與[商務用 Skype 搭配使用團隊之組織的互通性指導](/microsoftteams/migration-interop-guidance-for-teams-with-skype)方針。

## <a name="prerequisites"></a>先決條件

將使用者移至雲端的先決條件 (無論是僅適用于商務用 Skype 或僅限團隊模式):

- 組織必須正確設定 Azure AD Connect, 並如 [[設定 AZURE Ad Connect]](configure-azure-ad-connect.md)中所述, 同步處理使用者的所有相關屬性。
- 必須設定商務用 skype 混合式, 如[設定商務用 skype 混合](configure-federation-with-skype-for-business-online.md)式中所述。
- 使用者必須獲指派商務用 Skype Online 的授權 (方案 2), 如果他們要使用團隊, 他們也必須擁有團隊授權。  另外：
    - 如果使用者已在內部部署中啟用電話撥入式會議, 預設情況下, 使用者也必須在 Office 365 中指派音訊會議授權, 才能執行將使用者移至線上。 遷移到雲端之後, 使用者將會在雲端中為音訊會議進行預配。 如果您想要將使用者移至雲端, 但不使用音訊會議功能, 您可以在中`BypassAudioConferencingCheck` `Move-CsUser`指定參數來覆寫此檢查。
    - 如果使用者已在內部部署中啟用企業語音, 預設情況下, 使用者必須具備在 Office 365 中指派的電話系統授權, 才能將使用者移至線上。 一旦遷移到雲端, 就會為雲端的電話系統提供使用者。 如果您想要將使用者移至雲端但不使用電話系統功能, 您可以在中`BypassEnterpriseVoiceCheck` `Move-CsUser`指定參數來覆寫此檢查。


## <a name="moving-users"></a>移動使用者

當使用者從內部部署移至雲端時:

- 使用者開始在雲端使用商務用 Skype Online 服務, 以取得任何商務用 Skype 功能。
- 團隊使用者可與商務用 Skype 使用者進行互通性, 而且也可以與其他組織聯盟。
- 從內部部署的連絡人會移至雲端 (無論是商務用 Skype 或團隊)。
- 在未來排程的現有會議會遷移至 [線上]: 如果使用者直接移到 TeamsOnly (請參閱下方), 會議會轉換成團隊會議, 否則會議會保持商務用 Skype, 但會進行遷移, 所以線上託管, 而不是內部部署。  以非同步方式遷移會議, 並在移動使用者後開始大約90分鐘。  若要判斷會議遷移的狀態, 您可以使用[csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms)。 請注意, 在會議提前上傳的任何內容都不會移動。

若要在內部部署與雲端 (無論是團隊或商務用 Skype Online) 之間移動使用者, 請使用 Move-csuser Cmdlet 或商務用 Skype 系統管理控制台, 這兩者都是內部部署工具。 這些工具支援三種不同的移動路徑:

- [從商務用 Skype 伺服器 (內部部署) 到商務用 Skype Online](move-users-from-on-premises-to-skype-for-business-online.md)。
- [從商務用 Skype Server (內部部署) 直接直接給小組](move-users-from-on-premises-to-teams.md)(這也會將其移至商務用 Skype Online)。  在商務用 Skype Server 2019, 以及商務用 Skype Server 2015 的累積更新8中, 您可以直接從內部部署到團隊的選項。 使用舊版商務用 Skype Server 的組織只能將使用者移至 [商務用 Skype Online], 然後在他們線上時將 TeamsOnly 模式套用至這些使用者。
- [從線上 (無論是團隊), 到內部部署](move-users-from-the-cloud-to-on-premises.md)。

## <a name="required-administrative-credentials"></a>所需的管理認證

若要在內部部署與雲端之間移動使用者, 您必須在內部部署商務用 Skype Server 環境以及 Office 365 租使用者中, 使用具有足夠許可權的帳戶。 您可以使用一個擁有所有必要許可權的帳戶, 或者您可以使用兩個帳戶 (在這種情況下, 您可以使用內部部署認證存取內部部署工具), 然後在這些工具中, 您可以為 Office 365 提供其他認證系統管理帳戶。  

- 在內部部署環境中, 執行移動的使用者必須擁有商務用 Skype Server 中的 CSServerAdminstrator 角色。
- 在 Office 365 中, 執行移動的使用者必須是全域系統管理員, 或者必須同時擁有商務用 Skype 系統管理員和使用者管理員角色。  

    > [!Important]
    > - 如果您使用的是商務用 Skype 系統管理控制台, 系統會提示您提供具有適當角色的 Office 365 帳戶的認證, 如上所述。 您必須提供以 onmicrosoft.com 結尾的帳戶。 如果無法這樣做, 請使用 Move-csuser Cmdlet。
    >- 如果您是在 PowerShell 中使用 Move-csuser, 您可以使用 onmicrosoft.com 結尾的帳戶, 或者, 您也可以使用任何已同步處理到 Azure AD 的內部部署帳戶 (前提是您也在 Cmdlet 中指定 HostedMigrationOverrideUrl 參數). 裝載的 [遷移覆蓋] URL 的值是下列 URL 的變種:https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>在上述 URL 中, 以兩個或三個字元取代 XX, 如下所示:
    >   - 在商務用 Skype Online PowerShell 會話中, 請執行下列 Cmdlet:<br>`Get-CsTenant|ft identity`
    >    - 產生的值將會是下列格式:<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - 兩位數或三位數的代碼是包含在區段中的 XX, 即 DC = lyncXX001。 如果它是雙字元代碼, 則它會是一個數位, 後接一個數位 (例如 0a)。 如果是由三個字元組成的代碼, 則會使用兩個字母, 後接一個數位 (例如 jp1)。 在任何情況下, 您都會在 XX 程式碼後立即看到001。


## <a name="voice-configuration-requirements"></a>語音配置需求

如果使用者是在內部部署中針對企業語音進行設定, 則您必須在將其移至線上時協調更新其語音設定, 或者, 或者, 您也可以在不需電話功能的情況下, 將其遷移。 可用的選項取決於使用者是否要在線上使用團隊或商務用 Skype 用戶端:

- 您可以更新使用者的電話服務提供者, 以使用[Microsoft 通話方案](/microsoftteams/calling-plans-for-office-365)。 無論使用者是否使用團隊或商務用 Skype 用戶端, 都可以選擇此選項。
- 您可以繼續使用內部部署的 PSTN 提供者:
  - 必須針對[直接路由](/microsoftteams/direct-routing-plan)設定要使用團隊的語音使用者。 只有在使用者從內部部署移至線上之後, 才能使用直接路由。
  - 在線上移動之後, 會使用商務用 Skype 用戶端的語音使用者, 必須針對商務用 Skype 混合式語音功能進行設定。

如需混合式環境中電話語音選項的詳細資訊, 以及可支援性矩陣, 請參閱[混合式環境中具有 PSTN 連線的使用者帳戶](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)。

## <a name="other-considerations"></a>其他考慮

內部部署和線上環境中的原則 (例如控制訊息、會議和通話行為) 都是獨立的。 您可能會想要考慮在環境中設定任何原則, 並將其指派給使用者, 然後再將該使用者從內部部署移至雲端, 讓它們在一開始遷移至線上前就能有正確的配置。

## <a name="see-also"></a>另請參閱

[將使用者從內部部署移至商務用 Skype Online](move-users-from-on-premises-to-skype-for-business-online.md)

[將使用者從內部部署移至團隊](move-users-from-on-premises-to-teams.md)

[設定會議遷移服務 (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[規劃直接路由](/microsoftteams/direct-routing-plan)

[移動流覽 Move-csuser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)
