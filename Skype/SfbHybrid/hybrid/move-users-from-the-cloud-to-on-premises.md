---
title: 將使用者從雲端移至內部部署
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
description: 瞭解如何將使用者從商務用 Skype Online 移至內部部署。
ms.openlocfilehash: 16e4419bfd8ea073c04d0b3c4a402455097e4ad5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185443"
---
# <a name="move-users-from-the-cloud-to-on-premises"></a>將使用者從雲端移至內部部署 

如有需要, 您可以將先前從內部部署遷移的使用者移至雲端 (無論是只使用商務用 Skype Online 或團隊), 還是都能回到內部部署。 若要將使用者從商務用 Skype Online 或 TeamsOnly 模式移回內部部署的商務用 Skype Server, 請使用 Move-csuser Cmdlet 或商務用 Skype Server 控制台, 這兩者都是內部部署工具。 當您將使用者移回內部部署的部署時, 您必須決定要將使用者移至哪個池。

> [!Important]
> 如果使用者先前處於 TeamsOnly 模式, 而您使用的是舊版商務用 Skype Server 2015 與 CU8 的版本, 則您也必須移除該使用者的 TeamsUpgradePolicy TeamsOnly 模式指派。 內部部署使用者不得具有 mode = TeamsOnly。  後續版本的商務用 Skype Server 會自動移除此作業。 如需詳細資訊, 請參閱[授與 CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy)。

## <a name="prerequisites"></a>先決條件

- 組織必須正確設定 Azure AD Connect, 並同步處理使用者的所有相關屬性, 如[[設定 AZURE AD Connect]](configure-azure-ad-connect.md)中所述。
- 在內部部署 Active Directory 中, 從線上移回內部部署的使用者必須已經存在。
- 必須設定商務用 skype 混合式, 如[設定商務用 skype 混合](configure-federation-with-skype-for-business-online.md)式中所述。

## <a name="moving-users-back-to-on-premises"></a>將使用者移回內部部署

一旦您將使用者從雲端移回內部部署:

- 使用者會與您的商務用 Skype 伺服器部署互動, 瞭解其功能。 
- 在商務用 Skype Online 或團隊中存在的任何連絡人, 都會遷移到商務用 Skype 伺服器。 這兩組連絡人會合並, 然後再遷移回內部部署。  此外, 小組中預先存在的連絡人仍會保留在小組中。
- 如果使用者也使用團隊, 就無法與商務用 Skype 使用者進行交互操作, 也無法與聯盟組織中的使用者通訊。
- 商務用 Skype Online 中的會議*不*會自動轉移回內部部署。 使用者應該重新安排其會議, 或視需要使用[會議遷移工具](https://support.office.com/en-us/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)。

### <a name="move-users-with-move-csuser"></a>移動 Move-csuser 的使用者

您可以從內部部署商務用 Skype Management Shell PowerShell 視窗中取得 Move-csuser。 在內部部署環境以及 Office 365 租使用者中, 您必須具備足夠的許可權, 如[所需的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述。 您可以使用單一帳戶, 在這兩個環境中都有許可權, 或者您可以在內部部署的商務用 Skype Server Management Shell 視窗中使用內部部署認證, 並使用`-Credential`參數來指定 Office 365 的認證。具有必要的 Office 365 系統管理角色的帳戶。

若要使用移動 Move-csuser 將使用者移至內部部署:

- 使用身分識別參數指定要移動的使用者。
- 指定-Target 參數以及要承載使用者之所需內部部署池的完整功能變數名稱。
- 如果您沒有一個帳戶在內部部署和 Office 365 中都有足夠的許可權, 請使用-credential 參數, 在 Office 365 中提供具有足夠許可權的帳戶。
- 如果 Office 365 許可權的帳戶不是以 "on.microsoft.com" 結尾, 您必須使用正確的值來指定-HostedMigrationOverrideUrl 參數 (如[所需的管理認證](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)中所述)。

下列 Cmdlet 序列可用來將使用者移至商務用 Skype Server, 並假設 Office 365 認證是獨立的帳戶, 並提供取得認證提示的輸入。

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target pool.corp.contoso.com -Credential $cred -HostedMigrationOverrideUrl $url
```

### <a name="move-users-with-the-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 的 [控制台] 移動使用者

1. 開啟商務用 Skype Server 的 [控制台] 應用程式。
2. 在左側導覽中, 選擇 [**使用者**]。
3. 使用 [**尋找**], 找出您想要移回內部部署的使用者。
4. 選取使用者, 然後從清單上方的 [**動作**] 下拉式清單中, 選擇 [**將選取的使用者移至內部部署**]。
5. 在嚮導中, 選取將主持使用者的使用者池, 然後按 **[下一步]**。
6. 如果出現提示, 請以 onmicrosoft.com 結尾的帳戶登入 Office 365, 且具有足夠的許可權。
7. 按一下 **[下一步**], 然後再按一次, 以移動使用者。 ****
8. 請注意, 關於成功或失敗的狀態訊息是在主要控制台 app 的頂端提供, 而不是在嚮導中。

### <a name="removing-teamsonly-mode"></a>移除 TeamsOnly 模式

如果您使用的是早于商務用 Skype 2015 的版本, 且 CU8 是在 TeamsOnly 模式中將使用者移回內部部署, 則您必須移除 UpgradeToTeams 實例, `TeamsUpgradePolicy`才能在內部部署上移動使用者。 您可以明確地將原則授與其他模式, 或只是移除該使用者的現有原則指派, 以使用全域原則 (只要您的租使用者全域原則不是 UpgradeToTeams)。

若要移除使用者的 TeamsUpgradePolicy 指派, 請從商務用 Skype Online PowerShell 視窗中執行下列 Cmdlet:

`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName $null`

或者, 若要指派另一個沒有 mode = TeamsOnly 的 TeamsUpgradePolicy 實例, 您可以在 Cmdlet 中將所需實例的名稱指定為 PolicyName 參數的值。 若要查看 TeamsUpgradePolicy 的可用實例清單, 請執行 CsTeamsUpgradePolicy。


## <a name="see-also"></a>另請參閱

[移動流覽 Move-csuser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)
