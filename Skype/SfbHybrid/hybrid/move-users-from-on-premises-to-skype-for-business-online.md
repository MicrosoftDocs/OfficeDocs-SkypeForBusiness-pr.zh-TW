---
title: 移動使用者從內部部署商務用 skype
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
description: 了解如何將使用者移至 Skype，商務 online。
ms.openlocfilehash: 6653ca8fe7082f0cabd2057c078f7d0d8d6f0389
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726753"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>移動使用者從內部部署商務用 skype

移動使用者從內部部署用 skype for Business Online 之後，使用者互動與 Skype for Business Online 其功能。 Skype for Business Online 中，將可使用任何存在於內部部署的連絡人和任何現有的會議使用者召集的未來會更新，以使連結指向商務用 Skype。 如果使用者已啟用音訊會議，會議也會包含電話撥入式座標。  若要將使用者從內部部署環境移至 Skype，商務，請使用 Move-csuser cmdlet 或 Skype for Business Server Control Panel，這兩種都是內部部署工具。 

才可繼續任何使用者，請務必檢閱[必要條件](move-users-between-on-premises-and-cloud.md#prerequisites)，將使用者移至雲端。
 
## <a name="move-users-with-move-csuser"></a>使用 Move-csuser 移動使用者 

Move-csuser 是來自商務 Management Shell PowerShell 視窗，內部部署商務用 Skype。 [所需的系統管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)所述，您必須具有足夠的權限，這兩個內部部署環境中也如所示的 Office 365 租用戶。 您可以使用單一帳戶的權限在這兩個環境中，或者您可以使用內部部署認證，啟動 Business Server 管理命令介面視窗內部部署商務用 Skype，並使用`-Credential`參數，以指定必要的 Office 365 系統管理角色與 Office 365 帳戶的認證。

將使用者移至線上使用 Move-csuser:

- 指定使用者移動使用 Identity 參數。
- 指定-Target 參數具有值 「 sipfed.online.lync。<span>com"。
- 如果您不具備一個帳戶具有足夠權限兩者在內部部署和 Office 365 中，使用-credential 參數，以提供具有足夠的權限，在 Office 365 中的帳戶。
- 如果使用 Office 365 中的權限的帳戶未結束於 」 on.microsoft。<span>com 」，然後如所述[所需的系統管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)，您必須使用正確的值指定-HostedMigrationOverrideUrl 參數。

 > [!NOTE]
 > 您必須決定正確的 HostedMigrationOverrideUrl 值租用戶。 這可以藉由瀏覽至商務版系統管理中心舊版商務用 Skype 輕鬆完成。 決定的前置詞-XXXXXXX.online.lync.com 查詢和新增 /HostedMigration/hostedmigrationservice.svc。 例如：https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc一旦您已識別值，將其用於 $url 變數，如下所示。

下列指令程式順序可以用來移動使用者 skype 線上商務，並假設的 Office 365 認證是不同的帳戶，並提供做為 Get-credential 出現提示時輸入。

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

如果啟用 MFA （多重要素驗證） 的系統管理員帳戶，未指定-Credential 參數。 系統管理員會被提示輸入認證。

## <a name="move-users-with-skype-for-business-server-control-panel"></a>與 Skype for Business Server Control Panel 移動使用者 

1. 開啟 Skype for Business 伺服器控制項] 面板應用程式。
2. 在左導覽中，選擇 [**使用者**]。
3. 若要找出您想要將移至 Skype for Business Online 使用者使用 [**尋找**]。
4. 選取的使用者，然後從清單上方的 [**動作**] 下拉式清單，選擇 [**移至商務用 Skype 的所選的使用者**。
5. 在精靈中，按 **[下一步]**。
6. 如果出現提示，以登入 Office 365，結束於帳戶。 onmicrosoft.com 且具有足夠的權限。
7. 按一下 [**下一步**，然後**下一步**一個更多時間來移動使用者。
8. 請注意，在主要 [控制台] 應用程式，而不是以精靈頂端提供有關成功或失敗的狀態訊息。

## <a name="see-also"></a>另請參閱

[Move-csuser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
