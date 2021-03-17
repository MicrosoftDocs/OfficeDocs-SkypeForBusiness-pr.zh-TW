---
title: 將使用者從商務用 Skype Server 2019 移至團隊
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
description: 摘要：瞭解如何遷移使用者設定，以及將使用者移至團隊。
ms.openlocfilehash: c84cdbe5f91816ddfabd476540e47f3d1871a427
ms.sourcegitcommit: 360c78c66386fe00afe535681f51254eda886edf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/17/2021
ms.locfileid: "50836980"
---
# <a name="move-users-from-on-premises-to-teams"></a>將使用者從內部部署移動至 Teams

當使用者從內部部署移至團隊時，使用者的商務用 Skype 首頁會從內部部署移至線上，且會為使用者指派 TeamsUpgradePolicy with mode = TeamsOnly。  使用者從內部部署移至 TeamsOnly 模式後：

- 所有來自其他使用者的來電和聊天 (是否從商務用 Skype 或小組) 傳送至使用者的團隊用戶端。
- 使用者將能夠與使用商務用 Skype (的其他使用者互動，不論是線上或內部部署) 。
- 使用者將能夠與同盟組織中的使用者進行通訊。
- 由該使用者排程的新會議為小組會議。
- 使用者仍可加入任何商務用 Skype 會議。
- 預定未來的使用者預先存在的會議會從內部部署遷移至團隊。
- 在使用者第一次登入後，小組中將會立即提供內部部署的連絡人。
- 使用者無法從商務用 Skype 發起通話或交談，也不能在商務用 Skype 中排程新的會議。 如果他們嘗試開啟商務用 Skype 用戶端，他們將會重新導向為使用小組，如下所示。 若未安裝團隊用戶端，將會使用瀏覽器將其導向至小組的 web 版本。<br><br>
    ![將使用者重新導向至小組的郵件](../media/go-to-teams-page.png)

移動任何使用者之前，請務必先檢查 [必要條件](move-users-between-on-premises-and-cloud.md#prerequisites) ，將使用者移至雲端。 此外，請務必查看 [使用團隊搭配商務用 Skype 的組織遷移和互通性指導](/microsoftteams/migration-interop-guidance-for-teams-with-skype)方針。


> [!NOTE]
> 應停用部署 SfB 帳戶的整合連絡人存放區，以將連絡人移至小組。


有兩種方法可以將使用者從內部部署移至小組：

- 如果您使用的是商務用 Skype Server 2015 CU8 之前的版本，則移動會需要兩個步驟 (若有需要，您可以將其腳本撰寫成一個步驟（如有需要）) ：
  - [將使用者從商務用 Skype Server (內部) 移至商務用 Skype Online](move-users-from-on-premises-to-skype-for-business-online.md)。
  - 一旦使用者位於商務用 Skype Online 中，請將使用者 TeamsUpgradePolicy 指派為 mode = TeamsOnly。 若要授與 TeamsOnly 模式，請從商務用 Skype Online PowerShell 視窗執行下列 Cmdlet： `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- 如果您有來自商務用 Skype Server 2015 的系統管理工具 CU8 或更新版本，您可以使用以上的方法，也可以使用下列所述的一個步驟進行移動。 此外，您可以選擇性地在商務用 Skype 用戶端中提供通知，然後再將其移至小組，並選擇性地讓商務用 Skype 用戶端自行下載團隊用戶端。

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>僅在內部部署至小組，直接從商務用 Skype 移動使用者

在商務用 Skype 2015 Server 中的內部部署系統管理工具（含 CU8）和商務用 Skype Server 2019，可讓您在單一步驟中使用 PowerShell 或商務用 Skype Server [控制台] 中的 Move-CsUser Cmdlet，將使用者移至 [僅限團隊模式] 模式，如下所述。

### <a name="move-to-teams-using-move-csuser"></a>移至使用 Move-CsUser 的小組

您可以從內部部署商務用 Skype 管理命令介面 PowerShell] 視窗中取得 Move-CsUser。 下列步驟和所需的許可權與將使用者移至商務用 Skype Online 的方式相同，唯一不同的是，您也必須指定 MoveToTeams 參數，此外，除了商務用 Skype Online) 之外，還必須為使用者授與 (小組的授權。

在內部部署環境和雲端服務中，您必須具有足夠的許可權， (Microsoft 365 或 Office 365) ，如 [所需的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)所述。 您可以在兩個環境中使用具有許可權的單一帳戶，也可以使用內部部署認證來啟動內部部署商務用 Skype Server 管理命令介面視窗，並使用 `-Credential` 參數來指定使用必要系統管理角色之 Microsoft 365 或 Office 365 帳戶的認證。

若要使用 Move-CsUser 將使用者移至僅限小組模式：

- 使用參數指定要移動的使用者 `Identity` 。
- 指定-Target 參數的值為 "sipfed <span> "。com "。
- 指定 `MoveToTeams` 參數。
- 如果您在內部部署和雲端服務 (Microsoft 365 或 Office 365) 上都沒有一個具有足夠許可權的帳戶，請使用 `-credential` 參數提供 Office 365 中具有足夠許可權的帳戶。
- 如果在 Microsoft 365 或 Office 365 中具有許可權的帳戶不是以「name.onmicrosoft.com17」結尾。 <span>com "，您必須指定 `-HostedMigrationOverrideUrl` 參數，並在 [必要的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述的值正確。

下列指令程式順序可用來將使用者移至 TeamsOnly，並假設 Microsoft 365 或 Office 365 身分憑證是個別的帳戶，並提供做為 Get-Credential 提示的輸入。

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> 在不同的情況下，需要不同的參數，大多數案例的預設命令為：

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>移至使用商務用 Skype Server 的小組控制台

1. 開啟商務用 Skype Server [控制台] 應用程式。
2. 在左側導覽中，選擇 [ **使用者**]。
3. 使用 [ **尋找** ] 來找出使用者 (s) 您想要移至小組。
4. 選取 [使用者 (s) ]，然後從清單上方的 [ **動作** ] 下拉式清單中，選擇 [ **將選取的使用者移至小組**]。
5. 在精靈中，按 **[下一步]**。
6. 如果出現提示，請以 onmicrosoft.com 結尾的帳戶登入 Microsoft 365 或 Office 365，具有足夠的許可權。
7. 按 **[下一步** **]，然後再一** 次移動使用者。
8. 請注意，關於成功或失敗的狀態訊息是在主要控制台應用程式的頂端，而不是在嚮導中提供。

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>通知您的商務用 Skype 內部部署使用者即將進行的移動到團隊

商務用 Skype Server 2015 中的內部部署系統管理工具與 CU8，以及商務用 Skype Server 2019 中的內部部署系統管理工具，可讓您通知即將進行的內部部署商務用 Skype 使用者即將進行的移動到團隊。 當您啟用這些通知時，使用者會在其商務用 Skype 用戶端 (Win32、Mac、web 及行動) 中看到通知，如下所示。 如果使用者按一下 [ **Try it** ] 按鈕，將會在安裝團隊用戶端時將其啟動;否則，使用者會在其瀏覽器中流覽至小組的 web 版本。 依預設，啟用通知時，Win32 商務用 Skype 用戶端無訊息地下載團隊用戶端，以便在將使用者移至僅限小組模式之前可使用豐富型用戶端;不過，您也可以停用此行為。  使用內部部署版本設定通知 `TeamsUpgradePolicy` ，且 Win32 用戶端的無訊息下載是透過內部部署 Cmdlet 來控制的 `TeamsUpgradeConfiguration` 。

> [!TIP]
> 部分伺服器可能需要重新開機，以在商務用 Skype 2015 中使用 CU8。

![即將到來移至小組的通知](../media/teams-upgrade-notification.png)

若要通知內部部署使用者，他們很快就會升級為小組，使用 NotifySfBUsers = true 來建立新的 TeamsUpgradePolicy 實例。 然後，您可以將原則直接指派給使用者，或透過設定網站、集區或全域層級的原則，將該原則指派給您想要通知的使用者。 下列 Cmdlet 會建立並授與使用者層級原則：

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

透過商務用 Skype Win32 用戶端自動下載小組是透過內部部署 TeamsUpgradeConfiguration Cmdlet 搭配 DownloadTeams 參數來控制。 您可以在全域、網站及集區層級建立此設定。 例如，下列命令會建立網站 Redmond1 的設定：

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

DownloadTeams 的值預設為 True;不過，只有在指定的使用者 NotifySfbUser = True 時， *才* 會使用此參數。

## <a name="see-also"></a>請參閱

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[授與 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[搭配使用 Teams 與商務用 Skype 之組織的移轉和互通性指引](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[與商務用 Skype 共存](/microsoftteams/coexistence-chat-calls-presence)
