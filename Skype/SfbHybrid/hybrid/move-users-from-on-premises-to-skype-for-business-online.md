---
title: 將使用者從內部部署移至商務用 Skype Online
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
description: 瞭解如何將使用者移至商務用 Skype Online。
ms.openlocfilehash: 74816ae4c67f62cabad018a344b4b1800bd84444
ms.sourcegitcommit: 3c40bdd228ef88967cdf689100f2030f6997d9d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2019
ms.locfileid: "36715891"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>將使用者從內部部署移至商務用 Skype Online

在您將使用者從內部部署移至商務用 Skype Online 之後, 使用者就能與商務用 Skype Online 互動以取得其功能。 您可以在商務用 Skype Online 中使用內部部署的任何連絡人, 以及針對未來所組織的任何現有會議進行更新, 讓連結指向商務用 Skype Online。 如果使用者已啟用音訊會議, 會議也會包含撥入座標。  若要將使用者從內部部署環境移至商務用 Skype Online, 請使用 Move-csuser Cmdlet 或商務用 Skype Server 控制台, 這兩者都是內部部署工具。 

在移動任何使用者之前, 請務必先檢查[先決條件](move-users-between-on-premises-and-cloud.md#prerequisites), 才能將使用者移至雲端。
 
## <a name="move-users-with-move-csuser"></a>移動 Move-csuser 的使用者 

您可以從內部部署商務用 Skype Management Shell PowerShell 視窗中取得 Move-csuser。 您在內部部署環境以及 Office 365 租使用者中都必須具備足夠的許可權, 如[所需的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。 您可以使用單一帳戶, 在這兩個環境中都有許可權, 或者您可以在內部部署的商務用 Skype Server Management Shell 視窗中, 使用`-Credential`參數指定 Office 365 的認證。具有必要的 Office 365 系統管理角色的帳戶。

若要使用移動流覽 Move-csuser 將使用者移至線上:

- 使用身分識別參數指定要移動的使用者。
- 指定-Target 參數, 其值為 "sipfed. lync。<span>com "。
- 如果您沒有一個帳戶在內部部署和 Office 365 中都有足夠的許可權, 請使用-credential 參數, 在 Office 365 中提供具有足夠許可權的帳戶。
- 如果 Office 365 中具有許可權的帳戶不是以 "on." 結尾。<span>com ", 則您必須指定-HostedMigrationOverrideUrl 參數, 並在[所需的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中描述正確的值。

 > [!NOTE]
 > 您必須為租使用者判斷正確的 HostedMigrationOverrideUrl 值。 您可以流覽到舊版商務用 Skype 系統管理中心來輕鬆地完成此動作。 決定首碼-XXXXXXX.online.lync.com 和 append/HostedMigration/hostedmigrationservice.svc。 例如: https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc一旦您識別出該值, 就會將它用於 $url 變數, 如下所示。

下列 Cmdlet 序列可用來將使用者移至商務用 Skype Online, 並假設 Office 365 認證是獨立的帳戶, 並提供取得認證提示的輸入。

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

如果系統管理員帳戶已啟用 MFA (多重要素驗證), 請勿指定-Credential 參數。 系統會提示系統管理員輸入認證。

## <a name="move-users-with-skype-for-business-server-control-panel"></a>在商務用 Skype Server 的 [控制台] 中移動使用者 

1. 開啟商務用 Skype Server 的 [控制台] 應用程式。
2. 在左側導覽中, 選擇 [**使用者**]。
3. 使用 [**尋找**], 找出您想要移至商務用 Skype Online 的使用者。
4. 選取使用者, 然後從清單上方的 [**動作**] 下拉式清單中, 選擇 [**將選取的使用者移至商務用 Skype Online**]。
5. 在嚮導中, 按一下 **[下一步]**。
6. 如果出現提示, 請以 onmicrosoft.com 結尾的帳戶登入 Office 365, 且具有足夠的許可權。
7. 按一下 **[下一步**], 然後再按一次, 以移動使用者。 ****
8. 請注意, 關於成功或失敗的狀態訊息是在主要控制台 app 的頂端提供, 而不是在嚮導中。

## <a name="see-also"></a>另請參閱

[移動流覽 Move-csuser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)
