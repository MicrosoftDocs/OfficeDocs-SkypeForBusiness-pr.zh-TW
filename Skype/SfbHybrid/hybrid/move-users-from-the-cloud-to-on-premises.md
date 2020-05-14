---
title: 將使用者從雲端移至內部部署
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
description: 瞭解如何將使用者從商務用 Skype Online 移至內部部署。
ms.openlocfilehash: 64a5561fda35669be6ce7718c3ec037dcb8b9264
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221333"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>將使用者從雲端移至內部部署 

如有需要，您可以將先前從內部部署遷移的使用者移至雲端（不論只使用商務用 Skype Online 或小組），都可以移回內部部署。 若要將使用者從商務用 Skype Online 或 TeamsOnly 模式移回商務用 Skype Server 的內部部署部署，請使用 Move-CsUser Cmdlet 或商務用 Skype Server 控制台，這兩者都是內部部署工具。 當您將使用者移回內部部署時，您必須決定要將使用者移至哪一個集區。

> [!Important]
> 如果使用者先前處於 TeamsOnly 模式，而且您使用的是舊版商務用 Skype Server 2015 與 CU8，您也必須為該使用者移除 TeamsUpgradePolicy 的 TeamsOnly 模式指派。 內部部署使用者不得具有 mode = TeamsOnly。  後續版本的商務用 Skype Server 會自動移除此指派。 如需詳細資訊，請參閱[授與 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)。

## <a name="prerequisites"></a>必要條件

- 組織必須正確設定 Azure AD Connect，並同步處理使用者的所有相關屬性，如[Configure AZURE AD Connect](configure-azure-ad-connect.md)中所述。
- 從線上移回內部部署的使用者，必須已存在於內部部署 Active Directory 中。
- 必須設定商務用 skype 混合（如[設定商務用 skype 混合](configure-federation-with-skype-for-business-online.md)式中所述）。

## <a name="moving-users-back-to-on-premises"></a>將使用者移回內部部署

一旦您將使用者從雲端移回內部部署：

- 使用者會與您的商務用 Skype Server 部署進行互動，以進行其功能。 
- 任何存在於商務用 Skype Online 或小組中的連絡人，都將遷移至商務用 Skype Server。 這兩組連絡人會合並，然後再遷移回內部部署。  此外，預先存在於小組中的連絡人仍會保留在小組中。
- 如果使用者也使用小組，他們將無法與商務用 Skype 使用者互動，也無法與同盟組織中的使用者進行通訊。
- 商務用 Skype Online 中的會議*不*會自動遷移回內部部署。 使用者應重新排定其會議，如果需要，也應使用[會議遷移工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)。

### <a name="move-users-with-move-csuser"></a>使用 Move-CsUser 移動使用者

您可以從內部部署商務用 Skype 管理命令介面 PowerShell] 視窗中取得 Move-CsUser。 您必須在內部部署環境中具有足夠的許可權，以及雲端服務組織（Microsoft 365 或 Office 365），如[必要的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)所述。 您可以在兩個環境中使用具有許可權的單一帳戶，也可以使用內部部署認證來啟動內部部署商務用 Skype Server 管理命令介面視窗，並使用 `-Credential` 參數來指定使用必要系統管理角色之 Microsoft 365 或 Office 365 帳戶的認證。

若要使用 Move-CsUser 將使用者移至內部部署：

- 使用 Identity 參數指定要移動的使用者。
- 使用要主控使用者之所需內部部署集區的完整功能變數名稱，指定-Target 參數。
- 如果您在內部部署和雲端服務（Microsoft 365 或 Office 365）中沒有一個具有足夠許可權的帳戶，請使用-credential 參數提供具有足夠許可權的帳戶在 Microsoft 365 或 Office 365 中。
- 如果在 Microsoft 365 或 Office 365 中具有許可權的帳戶不是以「on.microsoft.com」結尾，您必須指定-HostedMigrationOverrideUrl 參數，並在[必要的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述的值正確。

下列指令程式順序可用來將使用者移至商務用 Skype Server，並假設 Microsoft 365 或 Office 365 身分憑證是個別的帳戶，並提供做為 Get-Credential 提示的輸入。

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台移動使用者

1. 開啟商務用 Skype Server [控制台] 應用程式。
2. 在左側導覽中，選擇 [**使用者**]。
3. 使用 [**尋找**] 來找出您想要移回到內部部署的使用者。
4. 選取使用者，然後從清單上方的 [**動作**] 下拉式清單中，選擇 [**將選取的使用者移至內部部署**]。
5. 在嚮導中，選取將主控使用者的使用者集區，然後按 **[下一步]**。
6. 如果出現提示，請以 onmicrosoft.com 結尾的帳戶登入 Microsoft 365 或 Office 365，具有足夠的許可權。
7. 按 **[下一步** **]，然後再一**次移動使用者。
8. 請注意，關於成功或失敗的狀態訊息是在主要控制台應用程式的頂端，而不是在嚮導中提供。

### <a name="removing-teamsonly-mode"></a>移除 TeamsOnly 模式

如果您使用的版本低於商務用 Skype 2015 與 CU8，且使用者會移回內部部署的 TeamsOnly 模式，您必須先移除 UpgradeToTeams 實例， `TeamsUpgradePolicy` 然後才能移動使用者內部部署。 您可以使用不同的模式明確授與原則，或只為該使用者移除現有的原則指派，以使用通用原則（只要您租使用者的全域原則不是 UpgradeToTeams）。

若要移除使用者的 TeamsUpgradePolicy 指派，請從商務用 Skype Online PowerShell 視窗執行下列 Cmdlet：

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

或者，若要指派另一個沒有 mode = TeamsOnly 的 TeamsUpgradePolicy 實例，您可以指定所需實例的名稱做為 Cmdlet 中 PolicyName 參數的值。 若要查看 TeamsUpgradePolicy 的可用實例清單，請執行 CsTeamsUpgradePolicy。


## <a name="see-also"></a>另請參閱

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
