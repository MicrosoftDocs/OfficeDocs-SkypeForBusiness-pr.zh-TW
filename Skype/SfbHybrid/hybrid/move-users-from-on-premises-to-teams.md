---
title: 將使用者從商務用 Skype Server 2019 移至 Teams
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
description: 摘要：瞭解如何遷移使用者設定，以及將使用者移至 Teams。
ms.openlocfilehash: 1b5a2f909a05ffd30902ca4ca32dc5b5621b3013e779cece3f0ffcd2dada731e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324702"
---
# <a name="move-users-from-on-premises-to-teams"></a>將使用者從內部部署移動至 Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

當使用者從內部部署移至 Teams 時，使用者的商務用 Skype home 會從內部部署移至線上，且會為使用者指派 mode = TeamsOnly 的 TeamsUpgradePolicy。  使用者從內部部署移至 TeamsOnly 模式後：

- 所有來自其他使用者的來電和聊天 (不論是從商務用 Skype 或 Teams) 傳送，都將會在使用者的 Teams 用戶端中土地。
- 使用者將能夠與使用商務用 Skype (線上或內部部署) 的其他使用者互動。
- 使用者將能夠與同盟組織中的使用者進行通訊。
- 由該使用者排程的新會議 Teams 會議。
- 使用者仍然可以加入任何商務用 Skype 會議。
- 預定未來的使用者預先存在的會議會從內部部署遷移至 Teams。
- 在使用者第一次登入之後，就可以在 Teams 中取得已存在內部部署的連絡人。
- 使用者無法從商務用 Skype 發起通話或交談，也無法在商務用 Skype 中排程新的會議。 如果他們嘗試開啟商務用 Skype 用戶端，將會重新導向為使用 Teams，如下所示。 若未安裝 Teams 用戶端，將會使用瀏覽器將其導向 Teams 的網頁版本。<br><br>
    ![將使用者重新導向至 Teams 的郵件](../media/go-to-teams-page.png)

移動任何使用者之前，請務必先檢查 [必要條件](move-users-between-on-premises-and-cloud.md#prerequisites) ，將使用者移至雲端。 此外，請務必查看[使用 Teams 搭配商務用 Skype 組織的遷移和互通性指導](/microsoftteams/migration-interop-guidance-for-teams-with-skype)方針。


> [!NOTE]
> 應停用部署 SfB 帳戶的整合連絡人存放區，以將連絡人移至 Teams。

> [!IMPORTANT]
>當您使用 Move-CsUser 將使用者從內部部署移至雲端時，使用者現在會自動被指派 TeamsOnly 模式，而且來自內部部署的會議會自動轉換為 Teams 會議，不論該 `-MoveToTeams` 參數是否實際指定。  (這包括從 Lync Server 2013 進行遷移，其絕對不會有 `-MoveToTeams` 此參數。 ) 先前若未指定此參數，則會將使用者轉換為位於商務用 Skype Server 內部部署中以商務用 Skype 線上，而且其模式仍保持不變。 這項功能最近已變更，準備退休的商務用 Skype 線上。


## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>將使用者直接從商務用 Skype 內部部署移至 Teams

商務用 Skype Server 和 Lync Server 2013 中的內部部署系統管理工具可讓您在單一步驟中使用 PowerShell 或商務用 Skype Server 控制台中的 Move-CsUser Cmdlet，將使用者移至 TeamsOnly 模式，如下所述。 `-MoveToTeams`不論使用的是哪個版本的商務用 Skype Server 或 Lync Server，都不再需要指定參數的參數和從內部部署直接移至 Teams 的行為。 

在內部部署環境和雲端服務 (都必須具備足夠的許可權，Microsoft 365 或 Office 365) ，如[必要的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)所述。 您可以在兩個環境中使用具有許可權的單一帳戶，也可以使用內部部署認證來啟動內部部署商務用 Skype Server 管理命令介面視窗，並使用 `-Credential` 參數指定具有必要系統管理角色之 Microsoft 365 的認證。

此外，除了商務用 Skype 線上) 之外，還必須確定已授與使用者 Teams (的授權。 請勿停用商務用 Skype 線上授權。

### <a name="move-to-teams-using-move-csuser"></a>使用 Move-CsUser 移至 Teams

您可以從內部部署商務用 Skype Server 管理命令介面 PowerShell] 視窗或從 Lync Server 管理命令介面 PowerShell 視窗中取得 Move-CsUser。 若要使用 Move-CsUser 將使用者移至 TeamsOnly 模式：
- 使用參數指定要移動的使用者 `Identity` 。
- 指定 `-Target` 值為 "sipfed <span> " 的參數。com "。
- 如果您在內部部署和雲端服務 (Microsoft 365) 中沒有一個帳戶具有足夠的許可權，請使用 `-credential` 參數提供 Microsoft 365 中具有足夠許可權的帳戶。
- 如果 Microsoft 365 中具有許可權的帳戶不會以 "name.onmicrosoft.com17" 結尾。 <span>com "，您必須指定 `-HostedMigrationOverrideUrl` 參數，並在[必要的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述的值正確。

下列指令程式順序可用來將使用者移至 TeamsOnly，並假設 Microsoft 365 認證是個別帳戶，並提供給 Get-Credential 提示的輸入。 不論是否指定參數，行為都相同 `-MoveToTeams` 。

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> 在不同的情況下，需要不同的參數，大多數案例的預設命令為：

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台移至 Teams

1. 開啟商務用 Skype Server 的 [控制台] 應用程式。
2. 在左側導覽中，選擇 [ **使用者**]。
3. 使用 [**尋找**] 來找出要移至 Teams 的使用者 (s) 。
4. 選取 [使用者 (s) ]，然後從清單上方的 [**動作**] 下拉式功能表中，選擇 [**將選取的使用者移至**]，Teams 或 **將選取的使用者移動到商務用 Skype 線上**。   這兩個選項現在都會直接將使用者直接移至 TeamsOnly。
5. 在精靈中，按 **[下一步]**。
6. 如果出現提示，請以 onmicrosoft.com 結尾的帳戶登入 Microsoft 365，且具有足夠的許可權。
7. 按 **[下一步** **]，然後再一** 次移動使用者。
8. 請注意，關於成功或失敗的狀態訊息是在主要控制台應用程式的頂端，而不是在嚮導中提供。
    
    
## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>將即將進行的商務用 Skype 內部部署使用者通報 Teams

使用 CU8 商務用 Skype Server 2015 中的內部部署系統管理工具，以及商務用 Skype Server 2019，可讓您通知內部部署商務用 Skype 使用者的即將到來移至 Teams。 當您啟用這些通知時，使用者會在其商務用 Skype 用戶端 (Win32、Mac、web 及行動) 中看到通知，如下所示。 如果使用者按一下 [ **Try it** ] 按鈕，將會在安裝 Teams 用戶端時將其啟動;否則，使用者會在其瀏覽器中流覽至 Teams 的 web 版本。 根據預設，當啟用通知時，Win32 商務用 Skype 用戶端會無訊息地下載 Teams 用戶端，以便在將使用者移至 TeamsOnly 模式之前能夠使用豐富型用戶端;不過，您也可以停用此行為。  使用內部部署版本設定通知 `TeamsUpgradePolicy` ，且 Win32 用戶端的無訊息下載是透過內部部署 Cmdlet 來控制的 `TeamsUpgradeConfiguration` 。

> [!TIP]
> 部分伺服器可能需要重新開機，以使用 CU8 商務用 Skype 2015。

![即將到來移至 Teams 的通知](../media/teams-upgrade-notification.png)

若要通知內部部署使用者即將升級為 Teams，請使用 NotifySfBUsers = true 建立 TeamsUpgradePolicy 的新實例。 然後，您可以將原則直接指派給使用者，或透過設定網站、集區或全域層級的原則，將該原則指派給您想要通知的使用者。 下列 Cmdlet 會建立並授與使用者層級原則：

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

透過 TeamsUpgradeConfiguration 商務用 Skype Win32 用戶端，可透過使用 DownloadTeams 參數的內部部署 Cmdlet 來控制自動下載 Teams。 您可以在全域、網站及集區層級建立此設定。 例如，下列命令會建立網站 Redmond1 的設定：

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

DownloadTeams 的值預設為 True;不過，只有在指定的使用者 NotifySfbUser = True 時， *才* 會使用此參數。

## <a name="see-also"></a>另請參閱

[Move-CsUser](/powershell/module/skype/move-csuser)

[授與 CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy
)

[搭配使用 Teams 與商務用 Skype 之組織的移轉和互通性指引](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[與商務用 Skype 共存](/microsoftteams/coexistence-chat-calls-presence)
