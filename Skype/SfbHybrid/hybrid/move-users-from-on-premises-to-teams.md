---
title: 將使用者從 商務用 Skype Server 2019 移至 Teams
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
search.appverid: MET150
ms.custom: ''
description: 摘要：瞭解如何移轉使用者設定，並將使用者移至 Teams。
ms.openlocfilehash: d29fa49e3521e93cb1818c70adb37cfb5019660b
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705842"
---
# <a name="move-users-from-on-premises-to-teams"></a>將使用者從內部部署移動至 Teams

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

當使用者從內部部署移至僅限 Teams 時，使用者的商務用 Skype住家會從內部部署移至線上，且會使用 mode=TeamsOnly 將使用者指派給 TeamsUpgradePolicy。  使用者從內部部署移至 TeamsOnly 模式後：

- 所有來自其他使用者的通話和聊天 (不論是從商務用 Skype® 用戶端或 Teams 傳送)，都會到達使用者的 Teams 用戶端。
- 使用者將能夠與使用商務用 Skype® (不論是線上或內部部署) 的其他使用者交互操作。
- 使用者將能夠與同盟組織中的使用者進行通訊。
- 該使用者排程的新會議為 Teams 會議。
- 使用者仍然可以加入任何商務用 Skype® 用戶端會議。 不過，從 2022 年 10 月開始，混合式組織中的 TeamsOnly 使用者只能匿名加入商務用 Skype會議。 如需詳細資訊，請參閱 [淘汰後預期會發生什麼事](/microsoftteams/skype-for-business-online-retirement#what-to-expect-post-retirement)。
- 使用者預先安排好的會議將從內部部署移轉至 Teams。
- 在使用者第一次登入之後，即可以在 Teams 中使用已存在內部部署的連絡人。
- 使用者無法從商務用 Skype起始通話或聊天，也無法在商務用 Skype中排程新的會議。 如果他們嘗試開啟商務用 Skype用戶端，系統會將他們重新導向以使用 Teams，如下所示。 如果未安裝 Teams 用戶端，系統會使用其瀏覽器將其導向至 Teams 的 Web 版本。<br><br>
    ![將使用者重新導向至 Teams 的訊息。](../media/go-to-teams-page.png)

移動任何使用者之前，請務必檢閱將使用者移至雲端的 [必要條件](move-users-between-on-premises-and-cloud.md#prerequisites) 。 也請務必檢閱[使用 Teams 與商務用 Skype的組織移轉和互通性指引](/microsoftteams/migration-interop-guidance-for-teams-with-skype)。


> [!NOTE]
> 應在內部部署 SfB 帳戶上停用整合連絡人存放區，以便將連絡人移至 Teams。

> [!IMPORTANT]
>
> - 使用 Move-CsUser 將使用者從內部部署移至雲端時，系統會自動為使用者指派 TeamsOnly 模式，而且無論是否 `-MoveToTeams` 實際指定切換，其內部部署會議都會自動轉換成 Teams 會議。  (這包括從 Lync Server 2013 移轉，其中從未有 `-MoveToTeams` switch.) 先前若未指定此參數，使用者會從內部部署商務用 Skype Server中轉換為 商務用 Skype Online，且其模式會保持不變。 這已在準備淘汰 商務用 Skype Online 時變更。
> - 在內部部署與 Teams 之間移動使用者，現在 *需要* 更新內部部署元件的最小版本，商務用 Skype Server或不再依賴 商務用 Skype Online 舊版基礎結構的 Lync Server。 如需詳細資訊，請參閱 [必要條件](move-users-between-on-premises-and-cloud.md#prerequisites)。

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>將使用者直接從內部部署商務用 Skype移至僅限 Teams

商務用 Skype Server和 Lync Server 2013 中的內部部署系統管理工具可讓您使用 PowerShell 中的 Move-CsUser Cmdlet 或 商務用 Skype Server 主控台，在單一步驟中將使用者從內部部署移至 TeamsOnly 模式，如下所述。 不論使用哪個版本的 商務用 Skype Server 或 Lync Server，現在都不再需要指定 `-MoveToTeams` 直接從內部部署移至 Teams 的切換和行為。 

您必須在內部部署環境和雲端服務 (Microsoft 365 或 Office 365) 中擁有足夠的許可權，如[必要的系統管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。 您可以使用在這兩個環境中具有許可權的單一帳戶，或是使用內部部署認證啟動內部部署商務用 Skype Server管理命令介面視窗，並使用 `-Credential` 參數來指定具有必要系統管理角色的 Microsoft 365 認證。

此外，除了 商務用 Skype Online) 之外，您還必須確定使用者已獲得 Teams (的授權。 請勿停用 商務用 Skype Online 授權。

### <a name="move-to-teams-using-move-csuser"></a>使用 Move-CsUser 移動至 Teams

Move-CsUser 可從內部部署商務用 Skype 伺服器管理命令介面 PowerShell 視窗或 Lync 伺服器管理命令介面 PowerShell 視窗取得。 若要使用 Move-CsUser 將使用者移動至 TeamsOnly 模式：
- 使用 參數指定要移動的 `Identity` 使用者。
- `-Target`指定值為 「sipfed.online.lync」 的 參數。 <span>com「 (或類似值，如果您的租使用者是政府雲端) 。
- 如果您在內部部署和雲端服務 (Microsoft 365) 中沒有一個帳戶具有足夠的許可權，請使用 `-credential` 參數在 Microsoft 365 中提供具有足夠許可權的帳戶。
- 如果在 Microsoft 365 中具有許可權的帳戶不會以 「onmicrosoft」 結尾。 <span>com「， you must specify the `-HostedMigrationOverrideUrl` parameter， with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).
- 請確定執行內部部署系統管理工具的電腦使用最新 CU 作為 商務用 Skype Server 或 Lync Server 2013 版本，以確保 OAuth 用於驗證。 

下列 Cmdlet 序列可用來將使用者移至 TeamsOnly，並假設 Microsoft 365 認證是個別的帳戶，並提供作為Get-Credential提示的輸入。 無論 `-MoveToTeams` 是否指定參數，行為都相同。

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> 由於有不同情況需要不同的參數，因此大部分情況下的預設命令為：

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>使用商務用 Skype 伺服器控制台移動至 Teams

1. 開啟商務用 Skype Server 主控台應用程式。
2. 在左側導覽中，選擇 [ **使用者]**。
3. 使用 **[尋找]** 來找出您想要移動至 Teams 的使用者。
4. 選取使用者，然後從清單上方的 **[動作]** 下拉式清單中，選擇 **[將選取的使用者移至 Teams]** 或 **[將選取的使用者移至商務用 Skype Online]**。   這兩個選項現在都會將使用者直接移至 TeamsOnly。
5. 在精靈中，按 **[下一步]**。
6. 如果出現提示，請使用以 .onmicrosoft.com 結尾且具有足夠權限的帳戶登入 Microsoft 365。
7. 按一下 **[下一步]**，然後再按 **[下一步]** 來移動使用者。
8. 有關成功或失敗的狀態訊息會在主要控制台應用程式的頂端提供，而不是在精靈中提供。
    
    
## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>通知您的商務用 Skype內部部署使用者即將移至 Teams

商務用 Skype Server 2015 與 CU8 中的內部部署系統管理工具，以及 2019 商務用 Skype Server，可讓您通知內部部署商務用 Skype使用者即將移至 Teams。 當您啟用這些通知時，使用者會在其商務用 Skype用戶端中看到通知 (Win32、Mac、Web 和行動裝置) ，如下所示。 如果使用者按一下 [ **試試看]** 按鈕，Teams 用戶端會在安裝時啟動;否則，使用者會在其瀏覽器中流覽至 Teams 的 Web 版本。 根據預設，當通知啟用時，Win32 商務用 Skype用戶端會以無訊息方式下載 Teams 用戶端，讓豐富型用戶端在將使用者移至 TeamsOnly 模式之前可供使用。 不過，您也可以停用此行為。  通知是使用 的內部部署版本 `TeamsUpgradePolicy` 來設定，而 Win32 用戶端的無訊息下載則是透過內部 `TeamsUpgradeConfiguration` 部署 Cmdlet 來控制。


![即將移至 Teams 的通知。](../media/teams-upgrade-notification.png)

若要通知內部部署使用者他們即將升級至 Teams，請使用 NotifySfBUsers=true 建立新的 TeamsUpgradePolicy 實例。 然後將該原則指派給您想要通知的使用者，方法是直接將原則指派給使用者，或是在網站、集區或全域層級設定原則。 下列 Cmdlet 會建立並授與使用者層級原則：

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

透過 商務用 Skype Win32 用戶端自動下載 Teams 是透過內部部署 TeamsUpgradeConfiguration Cmdlet 搭配 DownloadTeams 參數來控制。 您可以在全域、月臺和集區層級上建立此設定。 例如，下列命令會建立 Redmond1 網站的組態：

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

根據預設，DownloadTeams 的值為 True;不過，只有在指定使用者的 NotifySfbUser = True 時， *才會* 接受此動作。

## <a name="see-also"></a>另請參閱

[Move-CsUser](/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy
)

[搭配使用 Teams 與商務用 Skype 之組織的移轉和互通性指引](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[與商務用 Skype 共存](/microsoftteams/coexistence-chat-calls-presence)
