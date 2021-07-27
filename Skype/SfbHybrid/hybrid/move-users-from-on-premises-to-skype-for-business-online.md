---
title: 將使用者從內部部署移動至商務用 Skype Online
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
description: 瞭解如何將使用者移至商務用 Skype 線上。
ms.openlocfilehash: fcb1d508230c4faa18da4a473d9e24d384b047a6
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/21/2021
ms.locfileid: "53509944"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>將使用者從內部部署移動至商務用 Skype Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

在您將使用者從內部部署移至商務用 Skype online 後，使用者會與商務用 Skype 線上互動以取得其功能。 您可以在線上商務用 Skype 使用任何存在於內部部署的連絡人，而且所有在未來組織之使用者的現有會議都會更新，讓連結指向商務用 Skype 線上。 如果使用者已啟用音訊會議，則會議也會包含撥入座標。  若要將內部部署環境中的使用者移至商務用 Skype 線上，請使用 Move-CsUser Cmdlet 或商務用 Skype Server 控制台，這兩者都是內部部署工具。 

移動任何使用者之前，請務必先檢查 [必要條件](move-users-between-on-premises-and-cloud.md#prerequisites) ，將使用者移至雲端。

> [!NOTE]
> 在準備即將淘汰的商務用 Skype 線上狀態時，Microsoft 已簡化組織移至 Teams 的方式。 將使用者從內部部署移至雲端時，使用者現在會自動指派 TeamsOnly 模式，並將其來自內部部署的會議 automtically 轉換為 Teams 會議，就如同 `-MoveToTeams` 已指定參數一樣，不論該參數是否實際指定。  在線上退休商務用 Skype 之前，需要將使用者從內部部署移至商務用 Skype 線上的組織，可在 *使用者移至 TeamsOnly 後*，更新使用者的模式，以兩個步驟完成。 不過，在不久的未來，將不會再將 TeamsOnly 的模式指派給位於雲端中的使用者。  
 
## <a name="move-users-with-move-csuser"></a>使用 Move-CsUser 移動使用者 

您可以從內部部署商務用 Skype 管理命令介面 PowerShell 視窗中取得 Move-CsUser。 您必須在內部部署環境和 Microsoft 365 組織中具有足夠的許可權，如[所需的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)所述。 您可以在兩個環境中使用具有許可權的單一帳戶，也可以使用內部部署認證來啟動內部部署商務用 Skype Server 管理命令介面視窗，並使用 `-Credential` 參數，以必要的管理角色來指定 Microsoft 365 帳戶的認證。

若要使用 Move-CsUser 將使用者移至線上：

- 使用 Identity 參數指定要移動的使用者。
- 指定-Target 參數的值為 "sipfed <span> "。com "。
- 如果您在內部部署和 Microsoft 365 中沒有一個具有足夠許可權的帳戶，請使用-credential 參數提供具有足夠許可權的帳戶，在 Microsoft 365 中。
- 如果 Microsoft 365 中具有許可權的帳戶不是以「name.onmicrosoft.com17」結尾。 <span>com "，則您必須指定-HostedMigrationOverrideUrl 參數，並在[必要的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述的值正確。

您可以使用下列 Cmdlet 順序，將使用者移至商務用 Skype 線上，並將租使用者預設模式指派給使用者。 它假設 Microsoft 365 身分憑證是個別帳戶，並提供給 Get-Credential 提示的輸入。

```PowerShell
# From an on-premises Skype for Business Server or Lync Server 2013 management shell window, run:
 
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
 
# And then from a Teams PowerShell window, remove TeamsOnly mode by running: 
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName $null
```

如果系統管理員帳戶為 MFA (Multi-Factor 驗證) 啟用，請勿指定-Credential 參數。 系統會提示系統管理員輸入認證。

## <a name="move-users-with-skype-for-business-server-control-panel-and-teams-admin-center"></a>使用商務用 Skype Server 控制台和 Teams 系統管理中心移動使用者

1. 開啟商務用 Skype Server 的 [控制台] 應用程式。
2. 在左側導覽中，選擇 [ **使用者**]。
3. 使用 [**尋找**] 來找出使用者 (s) 您想要移至商務用 Skype 線上。
4. 選取 [使用者 (s) ]，然後從清單上方的 [**動作**] 下拉式功能表中，選擇 [**將選取的使用者移至商務用 Skype** ] 或 [**將選取的使用者移至 Teams**]。 任一選項最初都會將使用者移至 TeamsOnly 模式，但在移動之後，您可以指派另一種模式。 
5. 在精靈中，按 **[下一步]**。
6. 如果出現提示，請以 onmicrosoft.com 結尾的帳戶登入 Microsoft 365，且具有足夠的許可權。
7. 按 **[下一步** **]，然後再一** 次移動使用者。
8. 請注意，關於成功或失敗的狀態訊息是在主要控制台應用程式的頂端，而不是在嚮導中提供。
9. 開啟 Teams 系統管理中心，並選取左側導覽欄中的 [使用者]。 
10. 按一下 listview 中所需的使用者。 
11. 在顯示 **Teams 升級** 的區段中，按一下 [**編輯**]。
12. 在右側快顯視窗中，選取所需的共存模式，然後 **按一下 [** 套用]。
 

## <a name="see-also"></a>另請參閱

[Move-CsUser](/powershell/module/skype/move-csuser)
