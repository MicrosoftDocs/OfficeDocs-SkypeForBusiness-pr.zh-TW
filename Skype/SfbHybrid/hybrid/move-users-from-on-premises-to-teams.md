---
title: 將使用者從 Skype for Business Server 2019 移至 Teams
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
description: 摘要： 了解如何移轉使用者設定，並將使用者移至 Teams。
ms.openlocfilehash: c719741323c0e1bc8435adf10364356d069e8774
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726743"
---
# <a name="move-users-from-on-premises-to-teams"></a>將使用者從內部部署移至 Teams

當使用者從內部部署移至 [僅小組時，使用者的 Skype 商務首頁移從內部部署至 online 並指派給使用者 TeamsUpgradePolicy 搭配 mode = TeamsOnly。  之後使用者從移動內部部署到 TeamsOnly 模式：

- 所有內送呼叫和聊天室的其他使用者 （無論是從 Skype 傳送基於商業或小組），將會在使用者的 microsoft Teams 用戶端推送。
- 使用者將能夠與其他使用商務用 Skype （無論是線上或內部） 的使用者交互操作。
- 使用者將能夠彼此通訊同盟組織中的使用者。
- 使用該使用者排定新會議是 Teams 會議。
- 使用者仍然可以加入任何 Skype for Business 會議。
- 使用者的既有會議排定在未來將從內部部署移轉到小組。
- 連絡人已經存在於內部部署中可用的小組使用者第一次登入之後，很快就。
- 使用者無法起始通話或聊天從商務用 Skype，也可以排程商務用 Skype 中的新會議。 如果使用者嘗試開啟 Skype 商務用戶端，系統將會重新導向至使用 Teams，如下所示。 如果未安裝 microsoft Teams 用戶端，他們將會進入小組使用其瀏覽器網頁版。<br><br>
    ![將使用者重新導向至 Teams 的郵件](../media/go-to-teams-page.png)

才可繼續任何使用者，請務必檢閱[必要條件](move-users-between-on-premises-and-cloud.md#prerequisites)，將使用者移至雲端。 也請務必檢閱[移轉及組織使用 Teams 與商務用 Skype 互通性指導](/microsoftteams/migration-interop-guidance-for-teams-with-skype)。


> [!NOTE]
> 整合的連絡人存放區應該停用內部 SfB 帳戶移至 Teams 連絡人。


有兩種方法可以將使用者從內部部署移至小組：

- 如果您使用版本早於 Skype for Business Server 2015 CU8，移動要求 （其中可以寫成指令碼完成一起以單一步驟中，若有需要） 兩個步驟：
  - [將使用者從 Skype for Business Server （內部） 商務用 skype 移動](move-users-from-on-premises-to-skype-for-business-online.md)。
  - 一旦使用者位於 skype for Business Online，指派給使用者 TeamsUpgradePolicy 模式 = TeamsOnly。 若要授與 TeamsOnly 模式，請執行下列指令程式從 Skype for Business Online PowerShell 視窗：`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- 如果您有從 Skype for Business Server 2015 CU8 或更新版本的系統管理工具，您可以使用，與上述方法，或者您可以執行此移動一個步驟如下所示。 此外，您可以選擇性地提供商務用戶端之前將他們移至 [僅 Teams 商務用 Skype 中的通知，以及 （選用） 有 Teams 用戶端透過 Skype 商務用戶端自動下載。

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>僅小組內部移動使用者直接從商務用 Skype

在商務用 Skype Server 2015 與 CU8，以及 skype for Business Server 2019 中，內部部署系統管理工具可讓您將使用者從內部部署移至 Teams 只在單一步驟中使用 Move-csuser cmdlet，在 PowerShell 中的，或是用 Skype for Business Se 模式rver 控制台] 中，如下所示。

### <a name="move-to-teams-using-move-csuser"></a>移至 Teams 使用 Move-csuser

Move-csuser 是來自商務 Management Shell PowerShell 視窗，內部部署商務用 Skype。 所需權限與執行下列步驟會將使用者移至 Skype for Business Online，您還必須指定 MoveToTeams 參數，而您必須確定，使用者也已授與授權 （除了商務用 Skype 的 teams 的相同Online)。

[所需的系統管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)所述，您必須具有足夠的權限，在內部部署環境和 Office 365 租用戶中。 您可以使用單一帳戶的權限在這兩個環境中，或者您可以使用內部部署認證，啟動 Business Server 管理命令介面視窗內部部署商務用 Skype，並使用`-Credential`參數，以指定必要的 Office 365 系統管理角色與 Office 365 帳戶的認證。

若要將使用者移至 Teams 只使用 Move-csuser 的模式：

- 指定使用者移動使用`Identity`參數。
- 指定-Target 參數具有值 「 sipfed.online.lync。<span>com"。
- 指定`MoveToTeams`切換。
- 如果您不具備一個帳戶具有足夠權限兩者在內部部署和 Office 365 中，使用`-credential`參數，以提供具有足夠的權限，在 Office 365 中的帳戶。
- 如果使用 Office 365 中的權限的帳戶未結束於 」 onmicrosoft。<span>com 」，您必須指定`-HostedMigrationOverrideUrl`具有正確的值做為[所需的系統管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)> 中所述的參數。

下列指令程式順序可以用來將使用者移至 TeamsOnly，並假設的 Office 365 認證是不同的帳戶，並提供做為 Get-credential 出現提示時輸入。

    ```
    $cred=Get-Credential
    $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
    ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>移至 Teams 使用 Skype for Business Server Control Panel

1. 開啟 Skype for Business 伺服器控制項] 面板應用程式。
2. 在左導覽中，選擇 [**使用者**]。
3. 若要找出您想要將移至小組的使用者使用 [**尋找**]。
4. 選取的使用者，然後再從清單上方的 [**動作**] 下拉式清單，選擇 [**移到 Teams 的所選的使用者**。
5. 在精靈中，按 **[下一步]**。
6. 如果出現提示，以登入 Office 365，結束於帳戶。 onmicrosoft.com 且具有足夠的權限。
7. 按一下 [**下一步**，然後**下一步**一個更多時間來移動使用者。
8. 請注意，在主要 [控制台] 應用程式，而不是以精靈頂端提供有關成功或失敗的狀態訊息。

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>通知您 Skype for Business 上內部部署使用者即將移動到 Teams 的

在商務用 Skype Server 2015 與 CU8，以及 skype for Business Server 2019 中，內部部署系統管理工具可讓您以通知他們即將來臨的移至 Teams 的商務使用者內部部署商務用 Skype。 當您啟用這些通知時，使用者會看到其 Skype 商務用戶端 （Win32、 Mac、 web 和行動） 中的通知，如下所示。 若已安裝; 如果使用者按一下 [**再**] 按鈕，將會啟動 microsoft Teams 用戶端否則，使用者會巡覽至 Teams 網頁版在其瀏覽器中。 根據預設，通知啟用時，Win32 Skype for Business 的用戶端以無訊息方式下載 microsoft Teams 用戶端使豐富型用戶端可再將使用者移至只 Teams 模式;不過，您可以也停用此行為。  使用內部部署版的設定通知`TeamsUpgradePolicy`，Win32 用戶端的無訊息下載控制透過內部部署和`TeamsUpgradeConfiguration`指令程式。

> [!TIP]
> 某些伺服器可能需要重新開機，此功能在 Skype for Business 2015 CU8 中運作。

![即將移動到 Teams 的通知](../media/teams-upgrade-notification.png)

若要通知的內部使用者，他們會推出升級成小組，建立 TeamsUpgradePolicy 的新執行個體與 NotifySfBUsers = true。 然後將該原則指派給您想要通知，藉由將原則指派給使用者直接或透過網站、 集區，或全域層級設定此原則的使用者。 下列指令程式建立，並授與使用者層級的原則：

```
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

自動下載透過 Skype 商務 Win32 用戶端的小組是透過內部部署 TeamsUpgradeConfiguration 指令程式，搭配 DownloadTeams 參數控制。 您建立此組態的全域、 網站及集區層級。 例如，下列命令會建立 Redmond1 網站的設定：

`New-CsTeamsUpgradeConfiguration -Identity “site:redmond1”`

根據預設，DownloadTeams 的值為 True;不過，它是*只*接受如果 NotifySfbUser = True 針對指定的使用者。

## <a name="see-also"></a>另請參閱

[Move-csuser](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[授與 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[搭配使用 Teams 與商務用 Skype 之組織的移轉和互通性指引](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[商務用 Skype 共存](/microsoftteams/coexistence-chat-calls-presence)
