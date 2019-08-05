---
title: 將使用者從商務用 Skype Server 2019 移至團隊
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
description: '摘要: 瞭解如何將使用者設定遷移並將使用者移至團隊。'
ms.openlocfilehash: 1a0b126537c02376eaf28f40e843295aa5582dd3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185446"
---
# <a name="move-users-from-on-premises-to-teams"></a>將使用者從內部部署移至團隊

當使用者從內部部署移至 [團隊] 時, 使用者的商務用 Skype 家用版會從 [內部部署] 移至 [線上], 而使用者會獲指派 mode = TeamsOnly 的 TeamsUpgradePolicy。  使用者從內部部署移至 TeamsOnly 模式後:

- 來自其他使用者的所有來電及聊天 (無論是從商務用 Skype 或團隊傳送), 都將居住在使用者的團隊用戶端中。
- 使用者將能夠與其他使用商務用 Skype 的使用者進行交互操作 (無論是線上或內部部署)。
- 使用者將能夠與同盟組織中的使用者進行通訊。
- 由該使用者排程的新會議為 [團隊會議]。
- 使用者仍然可以加入任何商務用 Skype 會議。
- 已排程未來的使用者預先存在的會議將會從內部部署到團隊。
- 在使用者第一次登入時, 小組中不久就會提供與內部部署的連絡人。
- 使用者無法從商務用 Skype 啟動通話或聊天, 也無法在商務用 Skype 中排程新的會議。 如果他們嘗試開啟商務用 Skype 用戶端, 就會將它們重新導向為使用團隊, 如下所示。 如果未安裝團隊用戶端, 則會使用瀏覽器將其導向至團隊的網頁版本。<br><br>
    ![將使用者重新導向至團隊的郵件](../media/go-to-teams-page.png)

在移動任何使用者之前, 請務必先檢查[先決條件](move-users-between-on-premises-and-cloud.md#prerequisites), 才能將使用者移至雲端。 此外, 請務必參閱[與商務用 Skype 搭配使用團隊之組織的遷移與互通性指導](/microsoftteams/migration-interop-guidance-for-teams-with-skype)方針。

有兩種方法可以將使用者從內部部署移至團隊:

- 如果您使用的是商務用 Skype Server 2015 CU8 之前的版本, 則移動需要兩個步驟 (如果需要, 可以將其腳本化為單一步驟):
  - [將使用者從商務用 Skype Server (內部部署) 移至商務用 Skype Online](move-users-from-on-premises-to-skype-for-business-online.md)。
  - 當使用者駐留在商務用 Skype Online 中時, 請以 mode = TeamsOnly 指派使用者 TeamsUpgradePolicy。 若要授與 TeamsOnly 模式, 請從商務用 Skype Online PowerShell 視窗中執行下列 Cmdlet:`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- 如果您有商務用 Skype Server 2015 CU8 或更新版本的系統管理工具, 您可以使用上述方法, 或者您可以按照下文所述, 在一個步驟中移動。 此外, 您可以選擇性地在商務用 Skype 用戶端中提供通知, 然後再將其移至團隊, 以及選擇性地讓商務用 Skype 用戶端自行下載 [團隊用戶端]。

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>將使用者直接從商務用 Skype 移至團隊

在商務用 Skype Server 2015 中使用 CU8 以及商務用 Skype Server 2019 中的內部部署系統管理工具, 您可以使用 PowerShell 或商務用 Skype Se 中的 Move-csuser Cmdlet, 在單一步驟中, 將使用者從內部部署移至 [僅限團隊模式]rver [控制台], 如下所述。

### <a name="move-to-teams-using-move-csuser"></a>使用移動 Move-csuser 移至團隊

您可以從內部部署商務用 Skype Management Shell PowerShell 視窗中取得 Move-csuser。 下列步驟與需要的許可權與將使用者移至商務用 Skype Online 的方式相同, 除了您必須指定 MoveToTeams 開關之外, 您必須確保使用者也已獲授與其他團隊的授權 (除了商務用 Skype)線上)。

在內部部署環境和 Office 365 租使用者中, 您必須具備足夠的許可權, 如[所需的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。 您可以使用單一帳戶, 在這兩個環境中都有許可權, 或者您可以在內部部署的商務用 Skype Server Management Shell 視窗中, 使用`-Credential`參數指定 Office 365 的認證。具有必要的 Office 365 系統管理角色的帳戶。

若要使用移動 Move-csuser 將使用者移至 [僅限團隊] 模式:

- 使用`Identity`參數指定要移動的使用者。
- 指定-Target 參數, 其值為 "sipfed. lync。<span>com "。
- 指定`MoveToTeams`開關。
- 如果您沒有一個帳戶在內部部署和 Office 365 中都有足夠的許可權, 請使用`-credential`參數, 在 Office 365 中提供擁有足夠許可權的帳戶。
- 如果 Office 365 中具有許可權的帳戶不是以 "on." 結尾。<span>com ", 您必須使用正確`-HostedMigrationOverrideUrl`的值來指定參數, 如[所需的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。

下列 Cmdlet 序列可用來將使用者移至 TeamsOnly, 並假設 Office 365 認證是獨立的帳戶, 並提供取得認證提示的輸入。

    ```
    $cred=Get-Credential
    $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
    ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 的 [控制台] 移至 [小組]

1. 開啟商務用 Skype Server 的 [控制台] 應用程式。
2. 在左側導覽中, 選擇 [**使用者**]。
3. 使用 [**尋找**], 找出您想要移至團隊的使用者。
4. 選取使用者, 然後從清單上方的 [**動作**] 下拉式清單中, 選擇 [**將選取的使用者移至團隊**]。
5. 在嚮導中, 按一下 **[下一步]**。
6. 如果出現提示, 請以 onmicrosoft.com 結尾的帳戶登入 Office 365, 且具有足夠的許可權。
7. 按一下 **[下一步**], 然後再按一次, 以移動使用者。 ****
8. 請注意, 關於成功或失敗的狀態訊息是在主要控制台 app 的頂端提供, 而不是在嚮導中。

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>向小組通知您的商務用 Skype 內部部署使用者

商務用 Skype Server 2015 的內部部署系統管理工具使用 CU8, 以及商務用 Skype Server 2019, 讓您向小組通知內部部署的商務用 Skype 使用者。 當您啟用這些通知時, 使用者將會在其商務用 Skype 用戶端 (Win32、Mac、web 和 mobile) 中看到通知, 如下所示。 如果使用者按一下 [**試用**] 按鈕, 則團隊用戶端會在已安裝時啟動;否則, 使用者會在其瀏覽器中流覽至團隊的網頁版本。 根據預設, 當啟用通知時, Win32 商務用 Skype 用戶端會以無訊息方式下載團隊用戶端, 以便在將使用者移至 [僅限團隊] 模式之前提供豐富的用戶端。不過, 您也可以停用這種行為。  通知是使用內部部署版本進行設定`TeamsUpgradePolicy`, 而 Win32 用戶端的無提示下載則是透過內部部署`TeamsUpgradeConfiguration` Cmdlet 來控制。

![即將到來的移至團隊的通知](../media/teams-upgrade-notification.png)

若要通知內部部署使用者即將升級至團隊, 請使用 NotifySfBUsers = true 建立新的 TeamsUpgradePolicy 實例。 然後, 將該原則指派給您要通知的使用者, 方法是將原則直接指派給使用者, 或在 [網站]、[池] 或 [全域] 層級設定原則。 下列 Cmdlet 會建立並授與使用者層級原則:

```
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

透過商務用 Skype Win32 用戶端自動下載團隊是透過使用 DownloadTeams 參數的內部部署 TeamsUpgradeConfiguration Cmdlet 來控制。 您可以在全域、網站和池層級建立此設定。 例如, 下列命令會為 site Redmond1 建立配置:

`New-CsTeamsUpgradeConfiguration -Identity “site:redmond1”`

根據預設, DownloadTeams 的值為 True;不過, 只有指定使用者的 NotifySfbUser = True 時,*才能*使用此選項。

## <a name="see-also"></a>另請參閱

[移動流覽 Move-csuser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)

[授與 CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy
)

[與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[在商務用 Skype 中共存](/microsoftteams/coexistence-chat-calls-presence)
