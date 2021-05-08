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
ms.openlocfilehash: 8c028044fe8c4b808a419503091f9ecf767cfe4d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237959"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>將使用者從內部部署移動至商務用 Skype Online

在您將使用者從內部部署移至商務用 Skype online 後，使用者會與商務用 Skype 線上互動以取得其功能。 您可以在線上商務用 Skype 使用任何存在於內部部署的連絡人，而且所有在未來組織之使用者的現有會議都會更新，讓連結指向商務用 Skype 線上。 如果使用者已啟用音訊會議，則會議也會包含撥入座標。  若要將內部部署環境中的使用者移至商務用 Skype 線上，請使用 Move-CsUser Cmdlet 或商務用 Skype Server 控制台，這兩者都是內部部署工具。 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

移動任何使用者之前，請務必先檢查 [必要條件](move-users-between-on-premises-and-cloud.md#prerequisites) ，將使用者移至雲端。
 
## <a name="move-users-with-move-csuser"></a>使用 Move-CsUser 移動使用者 

您可以從內部部署商務用 Skype 管理命令介面 PowerShell 視窗中取得 Move-CsUser。 您必須在內部部署環境中和 Microsoft 365/Office 365 組織中具備足夠的許可權，如[所需的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)所述。 您可以在兩個環境中使用具有許可權的單一帳戶，也可以使用內部部署認證來啟動內部部署商務用 Skype Server 管理命令介面視窗，並使用 `-Credential` 參數，指定 Microsoft 365 或 Office 365 帳戶的認證，以具備必要的管理角色。

若要使用 Move-CsUser 將使用者移至線上：

- 使用 Identity 參數指定要移動的使用者。
- 指定-Target 參數的值為 "sipfed <span> "。com "。
- 如果您在內部部署和 Office 365 中沒有一個具有足夠許可權的帳戶，請使用-credential 參數提供具有足夠許可權的帳戶，在 Office 365 中。
- 如果 Office 365 中具有許可權的帳戶不是以「name.onmicrosoft.com17」結尾。 <span>com "，則您必須指定-HostedMigrationOverrideUrl 參數，並在[必要的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述的值正確。

您可以使用下列 Cmdlet 順序，將使用者移至商務用 Skype 線上。 它假設 Microsoft 365 或 Office 365 身分憑證是個別的帳戶，並以 Get-Credential 提示的輸入提供。

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

如果系統管理員帳戶為 MFA (Multi-Factor 驗證) 啟用，請勿指定-Credential 參數。 系統會提示系統管理員輸入認證。

## <a name="move-users-with-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台移動使用者 

1. 開啟商務用 Skype Server 的 [控制台] 應用程式。
2. 在左側導覽中，選擇 [ **使用者**]。
3. 使用 [**尋找**] 來找出使用者 (s) 您想要移至商務用 Skype 線上。
4. 選取 [使用者 (s) ]，然後從清單上方的 [**動作**] 下拉式功能表中，選擇 [**將選取的使用者移至線上商務用 Skype**]。
5. 在精靈中，按 **[下一步]**。
6. 如果出現提示，請以 onmicrosoft.com 結尾的帳戶登入 Microsoft 365 或 Office 365，且具有足夠的許可權。
7. 按 **[下一步** **]，然後再一** 次移動使用者。
8. 請注意，關於成功或失敗的狀態訊息是在主要控制台應用程式的頂端，而不是在嚮導中提供。

## <a name="see-also"></a>另請參閱

[Move-CsUser](/powershell/module/skype/move-csuser)